---
title: Konfigurowanie wielu dzierżawców B2C w środowisku Commerce
description: W tym temacie opisano sposób konfigurowania wielu dzierżawców (B2C) na kanał Microsoft Azure Active Directory (Azure AD) na potrzeby uwierzytelniania użytkowników w środowisku specjalnym w ramach systemu Dynamics 365 Commerce.
author: BrianShook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: a372561b8a6cdca8e1a3dc362009379884f1a3414330f3f056d4c3af7703a132
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736411"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Konfigurowanie wielu dzierżawców B2C w środowisku Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania wielu dzierżawców (B2C) Microsoft Azure Active Directory (Azure AD) na potrzeby uwierzytelniania użytkowników na kanał w środowisku specjalnym w ramach systemu Dynamics 365 Commerce.

Dynamics 365 Commerce używa tożsamości w chmurze B2C usługi Azure AD do obsługi poświadczeń użytkowników i przepływów uwierzytelniania. Użytkownicy mogą skorzystać z przepływów uwierzytelniania, aby zarejestrować się, zalogować i zresetować hasło. Azure AD B2C przechowuje poufne informacje o uwierzytelnianiu użytkownika, takie jak jego nazwa użytkownika i hasło. Rekord użytkownika jest unikatowy dla każdego dzierżawcy B2C i używa zarówno poświadczeń nazwy użytkownika (adresu e-mail), jak i poświadczeń dostawcy tożsamości społecznościowych.

W większości przypadków w środowisku Commerce jest używana jedna dzierżawa B2C Azure AD. Klienci usługi Commerce mogą następnie tworzyć i publikować wiele oddziałów w tym samym środowisku Commerce, a w tych witrynach będą używane te same poświadczenia klientów. Jeśli jednak oddział w środowisku powinny być traktowane jako różne marki i są widoczne dla użytkowników jako osobne firmy, można skonfigurować dzierżawcę B2C dla kanału używanego w przypadku separacji oddział/Marka.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Zagadnienia dotyczące konfigurowania wielu dzierżawców B2C na kanał

Często, gdy każdy kanał lub oddział jest traktowany jako oddzielna firma, najlepszą opcją w odniesieniu do przepływów uwierzytelniania użytkowników w handlu jest użycie oddzielnych firm. Jeśli jednak chcesz zachować każdy kanał/oddział w tym samym środowisku i firmie, ale chcesz mieć osobne uwierzytelnianie użytkowników dla każdego oddziału, przed kontynuowaniem należy wziąć pod uwagę następujące kwestie:

- Użytkownicy będą mieć własne odrębne poświadczenia dla każdego kanału/oddziału.

    Ta sama osoba może mieć dwa oddzielne konta na kanał/oddział, ponieważ każde konto będzie unikatowym wpisem w oddzielnej dzierżawie B2C.

- W środowisku Microsoft Dynamics dla wyszukiwania rekordów globalnych zostaną zwrócone osobne rekordy odbiorców.

    Jeśli użytkownik korzysta z tego samego adresu e-mail w kanałach/oddziałach, globalne wyszukiwania klientów zwrócą wyniki dla każdego kanału/oddziału. (Zostanie wyświetlony wskaźnik kanału.)

- Książka adresowa może być użyta do grupowania użytkowników, dzięki czemu można ich śledzić dla każdego kanału.
- Zwiększenie liczby rekordów klientów na kanał może wzrosnąć, a ten wzrost może wpłynąć na wydajność globalnego wyszukiwania odbiorców.
- Dzierżawy B2C muszą być dokładnie zamapowane na kanał, aby ułatwić uniknięcie sytuacji, w której klienci rejestrują się do niewłaściwej dzierżawy. W przeciwnym razie mogą wystąpić pomyłki lub problemy z śledzeniem.

Na poniższej ilustracji przedstawiono wielu dzierżawców B2C w środowisku Commerce.

![Wielu dzierżawców B2C w środowisku Commerce.](media/MultiB2C_In_Environment.png)

Jeśli użytkownik zdecyduje, że firma wymaga odrębnych dzierżawców B2C na kanał w tym samym środowisku handlowym, należy wykonać procedury opisane w poniższych sekcjach, aby zażądać tej funkcji.

## <a name="configure-b2c-tenants-in-your-environment"></a>Konfiguruj dzierżawy B2C w swoim środowisku

Aby skonfigurować dzierżawy B2C w środowisku, należy wykonać odpowiednie procedury opisane w tej sekcji.

### <a name="add-an-azure-ad-b2c-tenant"></a>Dodaj dzierżawcę B2C Azure AD

Aby dodać dzierżawcę B2C Azure AD do środowiska, wykonaj następujące kroki.

1. Zaloguj się do modułu tworzenia witryn Commerce w swoim środowisku jako administrator systemu. Aby skonfigurować dzierżawców B2C Azure AD, musisz być administratorem systemu dla środowiska Commerce.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia dzierżawcy**, aby ją rozwinąć.
1. Wybierz kolejno opcje **Konfiguracja B2C** i **Zarządzanie**.
1. Wybierz **Dodaj aplikację B2C**, a następnie wprowadź następujące informacje:

    - **Nazwa aplikacji**: należy wprowadzić nazwę, która powinna być używana dla aplikacji w kontekście zarządzania nią w Commerce. Zaleca się używanie nazwy aplikacji, która została wybrana podczas konfigurowania aplikacji B2C Azure AD w portalu Azure. W ten sposób można ograniczyć pomyłki podczas zarządzania dzierżawcami B2C w systemie Commerce.
    - **Nazwa dzierżawcy**: należy wprowadzić nazwę dzierżawcy B2C, która jest wyświetlana w portalu Azure.
    - **Identyfikator zasad zapominania hasła**: Wprowadź identyfikator zasad (nazwę zasad w portalu Azure).
    - **Identyfikator zasad rejestracji logowania**: Wprowadź identyfikator zasad (nazwę zasad w portalu Azure).
    - **Identyfikator GUID klienta**: należy wprowadzić identyfikator dzierżawcy B2C Azure AD, który jest wyświetlany w portalu Azure (nie identyfikator aplikacji dla dzierżawcy B2C).
    - **Identyfikator zasad edycji profilu**: Wprowadź identyfikator zasad (nazwę zasad w portalu Azure).

1. Po zakończeniu wprowadzania tych informacji wybierz przycisk **OK**, aby zapisać zmiany. Twoja nowa dzierżawa B2C Azure AD powinna teraz pojawić się na liście w obszarze **Zarządzanie aplikacjami B2C**.

> [!NOTE]
> Należy pozostawić takie pola, jak **zakres**, **nieinteraktywny identyfikator zasad**, **nieinteraktywny identyfikator klienta**, **niestandardowa domena logowania**, a **identyfikator zasad rejestracji** pusty, chyba że zespół Dynamics 365 Commerce poinstruuje użytkownika o jego ustawienie.


### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Zarządzaj lub usuwaj dzierżawcę B2C Azure AD

1. Zaloguj się do modułu tworzenia witryn Commerce w swoim środowisku jako administrator systemu. Aby skonfigurować dzierżawców B2C Azure AD, musisz być administratorem systemu dla środowiska Commerce.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia dzierżawcy**, aby ją rozwinąć.
1. Wybierz kolejno opcje **Konfiguracja B2C** i **Zarządzanie**.
1. Aby edytować dzierżawcę B2C, wybierz obok niego symbol ołówka. Aby usunąć dzierżawcę B2C, wybierz obok niego symbol kosza.
1. Wybierz opcję **Zapisz**, a następnie wybierz opcję **Publikuj**, aby aktywować zmiany.

> [!WARNING]
> Jeśli dzierżawa B2C jest skonfigurowana dla witryny aktywnej/opublikowanej, użytkownicy mogli być zalogowani przy użyciu kont obecnych w dzierżawie. Jeśli usuniesz skonfigurowanego dzierżawcy w menu **Ustawienia dzierżawy \> Dzierżawca B2C**, usuniesz skojarzenie tej dzierżawy B2C z witryn, które są skojarzone z dowolnymi kanałami dzierżawcy. W takim przypadku użytkownicy mogą nie mieć możliwości logowania się do swoich kont. Z tego względu należy zachować wyjątkową ostrożność podczas usuwania skonfigurowanego dzierżawcy.
>
> Po usunięciu skonfigurowanego dzierżawcy, dzierżawa B2C i rekordy będą nadal przechowywane, ale konfiguracja systemu Commerce w tej dzierżawie zostanie zmieniona lub usunięta. Użytkownicy próbujący zarejestrować się lub zalogować się do witryny będą tworzyć nowy rekord konta w domyślnej lub nowo skojarzonej dzierżawie B2C, skonfigurowanej dla kanału witryny.

## <a name="configure-your-channel-with-a-b2c-tenant"></a>Konfigurowanie kanału za pomocą dzierżawcy B2C

1. Zaloguj się do modułu tworzenia witryn Commerce w swoim środowisku jako administrator systemu. Aby skonfigurować dzierżawców B2C Azure AD, musisz być administratorem systemu dla środowiska Commerce.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.
1. Wybierz **kanały**, a następnie wybierz kanał do skonfigurowania.
1. W okienku właściwości po prawej stronie w polu **wybierz aplikację B2C** wybierz skonfigurowaną dzierżawę B2C Azure AD, która ma być używana dla tego kanału.
1. Na pasku poleceń wybierz opcję **Zapisz i Opublikuj**, aby zatwierdzić nową lub zaktualizowaną konfigurację.

> [!WARNING]
> Jeśli zostanie zmieniona aplikacja B2C przypisana do kanału, użytkownik usunie bieżące odwołania, które zostały utworzone dla wszystkich użytkowników, którzy już się zapisali w środowisku. W takim przypadku wszelkie poświadczenia skojarzone z aktualnie przypisaną aplikacją B2C nie będą dostępne dla użytkowników. Dlatego też należy zmienić konfigurację B2C kanału Azure AD tylko w przypadku skonfigurowania kanału po raz pierwszy i gdy jeszcze żaden użytkownik nie mógł się zarejestrować. W przeciwnym razie użytkownicy mogą musieli zarejestrować się ponownie w celu ustanowienia rekordu w nowej dzierżawie B2C Azure AD.
## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
