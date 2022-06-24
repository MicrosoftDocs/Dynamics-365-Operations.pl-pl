---
title: Konfiguracja stron niestandardowych do logowań użytkowników
description: W tym artykule opisano, jak budować niestandardowe strony w Microsoft Dynamics 365 Commerce, które obsługują niestandardowe logowanie dla użytkowników dzierżawców Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C).
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2c610866b896ef7648d2596e17b51d1935a78dee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880347"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Konfiguracja stron niestandardowych do logowań użytkowników

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak budować niestandardowe strony w Microsoft Dynamics 365 Commerce, które obsługują niestandardowe logowanie dla użytkowników dzierżawców Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C).

Aby skorzystać ze stron niestandardowych, które są tworzone Dynamics 365 Commerce w celu obsługi przepływów logowania użytkowników, należy skonfigurować zasady Azure AD, które będą przywoływane w środowisku Commerce Environment. Można skonfigurować zasady B2C Azure AD „Rejestracja i logowanie”, „Edytowanie profili” i „Resetowanie hasła” za pomocą aplikacji B2C Azure AD. Do nazw dzierżawy i zasad B2C Azure AD można następnie odwoływać się podczas procesu udostępniania, który jest wykonywany dla środowiska Commerce przy użyciu usług Microsoft Dynamics Lifecycle Services (LCS).

Niestandardowe strony Commerce mogą być tworzone przy użyciu modułu logowanie, rejestracja, edycja profilu konta, resetowanie hasła lub generowanie modułów AAD. W konfiguracjach zasad B2C Azure AD w portalu Azure Portal należy odwoływać się do stron adresów URL opublikowanych dla stron niestandardowych.

> [!WARNING] 
> Azure AD B2C wycofa stare (starsze) przepływy użytkowników do 1 sierpnia 2021. Dlatego należy zaplanować migrowanie przepływów użytkownika do nowej zalecanej wersji. Nowa wersja zapewnia parzystość funkcji i nowe funkcje. Aby uzyskać więcej informacji, zobacz sekcję [Przepływy użytkowników w Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).

>Biblioteka modułów dla wersji Commerce 10.0.15 lub wyższa powinna być używana z zalecanymi przepływami użytkowników B2C. Można również używać domyślnych stron zasad użytkownika oferowanych w usłudze Azure AD B2C i umożliwiają one dodanie obrazu tła, logo i zmian koloru tła związanych z oznaczaniem marki firmy. Chociaż bardziej ograniczone możliwości projektowania, domyślne strony zasad użytkownika zapewniają funkcjonalność zasad Azure AD B2C bez tworzenia i konfigurowania dedykowanych stron niestandardowych. 

## <a name="set-up-b2c-policies"></a>Ustawianie zasad B2C

Po skonfigurowaniu dzierżawy B2C Azure AD i kojarzeniu jej ze środowiskiem Commerce, przejdź na stronę **Azure AD B2C** w portalu Azure, a następnie w menu w obszarze **Zasady** wybierz pozycję **Przepływy użytkowników (zasady)**.

![Polecenie przepływy użytkowników (zasady) w menu.](./media/B2C_CustomPage_PoliciesMenu.png)

Teraz można skonfigurować przepływy logowania użytkownika „Rejestracja i logowanie”, „Edytowanie profili” i „Resetowanie hasła”.

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Skonfiguruj zasadę „Rejestracja i logowanie”

Aby skonfigurować zasadę „Rejestracja i logowanie”, wykonaj następujące kroki.

1. Wybierz opcję **Nowy przepływ użytkownika**, wybierz **Rejestracja i logowanie**, wybierz kartę **Rekomendowany** i wybierz zasadę **Utwórz**.
1. Wprowadź nazwę zasady (na przykład **B2C\_1\_RejestracjaiLogowanie**).
1. W sekcji **Dostawcy tożsamości** wybierz dostawców tożsamości, którzy mają być używani dla zasady. Należy wybrać co najmniej opcję **Rejestracja e-mail**.
1. W kolumnie **Zbieranie atrybutów** zaznacz pola wyboru **Adres e-mail**, **Imię** i **Nazwisko**.
1. W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Dostawca tożsamości**, **Nazwisko** i **Identyfikator obiektu użytkownika**.

    ![Wybrane atrybuty i roszczenia.](./media/B2C_SignInSignUp_Attributes.png)

1. Wybierz przycisk **OK**, aby utworzyć zasadę.
1. Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**
1. Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.

    ![Strona właściwości nowej zasady.](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Nazwa zasad będzie w pełni wywoływana w środowisku Commerce. (Prefiks **B2C\_1\_** zostanie uwzględniony w odwołaniu.) Nie można zmieniać nazw zasad po ich utworzeniu. W przypadku wymiany istniejących zasad środowiska Commerce można usunąć zasady oryginalne i utworzyć nowe zasady o takiej samej nazwie. Ewentualnie, jeśli zainicjowano już obsługę środowiska, można przesłać nową nazwę zasady za pośrednictwem żądania usługi.

Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych. Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.

### <a name="configure-the-profile-editing-policy"></a>Skonfiguruj zasadę „edycji profilu”

Aby skonfigurować zasadę „edycji profilu”, wykonaj poniższe czynności.

1. Wybierz opcję **Nowy przepływ użytkownika**, wybierz **Edytowanie profilu**, wybierz kartę **Rekomendowany** i wybierz zasadę **Utwórz**.
1. Wprowadź nazwę zasady (na przykład **B2C\_1\_EditProfile**).
1. W sekcji **Dostawcy tożsamości** wybierz dostawców tożsamości, którzy mają być używani dla zasady. Należy wybrać co najmniej opcję **logowania lokalnego konta**.
1. W kolumnie **Zbieranie atrybutów** zaznacz pola wyboru **Nadana nazwa** i **Nazwisko**.
1. W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Dostawca tożsamości**, **Nazwisko** i **Identyfikator obiektu użytkownika**.
1. Wybierz przycisk **OK**, aby utworzyć zasadę.
1. Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**
1. Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.

Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych. Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.

### <a name="configure-the-password-reset-policy"></a>Skonfiguruj zasadę „resetowania hasła”

Aby skonfigurować zasadę „resetowania hasła”, wykonaj poniższe czynności.

1. Wybierz **Nowy przepływ użytkownika**, a następnie wybierz opcję **Resetuj hasło**, a następnie wybierz kartę **Rekomendowane** i kliknij przycisk **Utwórz**.
1. Wprowadź nazwę zasady (na przykład **B2C\_1\_ForgetPassword**).
1. W sekcji **dostawcy tożsamości** wybierz opcję **Resetuj hasło, używając adresu e-mail**.
1. W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Nazwisko** i **Identyfikator obiektu użytkownika**.
1. Wybierz przycisk **OK**, aby utworzyć zasadę.
1. Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**
1. Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.

Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych. Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.

## <a name="build-the-custom-pages"></a>Tworzenie niestandardowych stron

Dedykowane moduły Azure AD są zawarte w Commerce do tworzenia niestandardowych stron dla zasad użytkowników Azure AD B2C. Strony można tworzyć specjalnie dla każdego układu strony zasad użytkownika przy użyciu głównych modułów Azure AD B2C opisanych poniżej. Alternatywnie moduł **Ogólne AAD** może być używany do wszystkich układów stron i zasad w usłudze Azure AD B2C (nawet w przypadku opcji układu strony w ramach zasad niewymienionych poniżej). 

- Moduły usługi Azure AD specyficzne dla strony są powiązane z elementami wprowadzania danych renderowanymi przez usługę Azure AD B2C. Moduły te zapewniają większą kontrolę nad położeniem elementów na stronach. Jednak może być konieczne utworzenie większej liczby stron i rozszerzeń modułów, aby uwzględnić odchylenia poza domyślnymi ustawieniami opisanymi poniżej.
- Moduł **Ogólne AAD** tworzy element „div” dla usługi Azure AD B2C w celu renderowania wszystkich elementów układu strony zasad użytkownika, zapewniając większą elastyczność funkcji B2C strony, ale mniejszą kontrolę nad pozycjonowaniem i stylami (chociaż można użyć CSS pasujące do wyglądu i stylu Twojej witryny).

Możesz utworzyć pojedynczą stronę za pomocą modułu **Ogólne AAD** i używać jej dla wszystkich stron zasad użytkownika lub możesz tworzyć określone strony przy użyciu poszczególnych modułów Azure AD do logowania, rejestracji, edycji profilu, resetowania hasła, i weryfikacja resetowania hasła. Możesz również użyć kombinacji obu, używając określonych stron usługi Azure AD dla układów stron wymienionych poniżej oraz ogólnej strony modułu usługi AAD dla pozostałych układów stron w ramach tych lub innych stron zasad użytkownika.

Aby dowiedzieć się więcej o modułach Azure AD, które są dostarczane z biblioteką modułów, przeczytaj więcej na [Strony i moduły zarządzania tożsamością](identity-mgmt-modules.md).

Aby utworzyć niestandardowe strony z określonymi modułami tożsamości do obsługi logowania użytkowników, wykonaj następujące kroki.

1. Przejdź do swojej witryny w module konstruktora witryn Commerce.
1. Zbuduj następujące pięć szablonów i stron (jeśli jeszcze nie są obecne w Twojej witrynie):
    - Szablon **Zaloguj się** i strona korzystająca z modułu logowania.
    - Szablon **Zarejestruj się** i strona korzystająca z modułu rejestracji.
    - Szablon **resetowania hasła** i strona, która korzysta z modułu resetowania hasła.
    - Szablon **Potwierdzenie resetowania hasła** i strona, która korzysta z modułu potwierdzenia resetowania hasła.
    - Szablon **Edytuj profil** i stronę, która używa modułu Edytuj profil konta.

Podczas tworzenia stron postępuj zgodnie z następującymi wskazówkami:

- Dla każdej strony lub modułu należy zastosować układ i styl najlepiej odpowiadające wymaganiom biznesowym.
- Publikuj wszystkie strony i adresy URL, które muszą być używane w ustawieniach Azure AD B2C.
- Po opublikowaniu stron i adresów URL należy zebrać adresy URL, które muszą być używane w konfiguracjach zasad Azure AD B2C. A **?preloadscripts=true** sufiks zostanie dodany do każdego z adresów URL, gdy jest używany.

> [!IMPORTANT]
> Strony, do których istnieją odwołania w usłudze Azure AD B2C są obsługiwane bezpośrednio z domeny dzierżawy Azure AD B2C. Nie należy ponownie używać uniwersalnych nagłówków i stopek mających łącza względne. Ponieważ te strony będą przechowywane w domenie Azure AD B2C, gdy są używane, dla wszystkich łączy będą używane tylko bezwzględne adresy URL Zaleca się utworzenie określonego nagłówka i stopki z bezwzględnymi adresami URL dla niestandardowych stron związanych z usługą Azure AD, z usuniętymi wszystkimi modułami specyficznymi dla Commerce, które wymagają połączenia z serwerem Retail Server. Na przykład ulubione, pasek wyszukiwania, łącze logowania i moduły koszyka nie powinny być uwzględniane na żadnych stronach, które będą używane w przepływach użytkowników usługi Azure AD B2C.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Skonfiguruj zasady Azure AD B2C za pomocą niestandardowych informacji o stronie 

W portalu Azure Wróć do strony **Azure AD B2C**, a następnie w menu w obszarze **zasady** wybierz pozycję **przepływy użytkowników (zasady)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Aktualizuj zasadę „Rejestracja i logowanie w” przy użyciu niestandardowych informacji o stronie

Aktualizuj zasadę „Rejestracja i logowanie w” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.

1. W obszarze zasady **Zaloguj się i zarejestruj**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.
1. Wybierz układ **Unifikuj rejestrację i logowanie na stronie**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. W polu **Wersja układu strony** wybierz wersję **2.1.0** lub nowszą (wymaga biblioteki modułów dla wersji Commerce 10.0.15 lub nowszej).
1. Wybierz opcję **Zapisz**.
1. Wybierz układ **Strona rejestracji lokalnego konta**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL logowania. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. W polu **Wersja układu strony** wybierz wersję **2.1.0** lub nowszą (wymaga biblioteki modułów dla wersji Commerce 10.0.15 lub nowszej).
1. W sekcji **atrybuty użytkownika** wykonaj następujące kroki:
    1. W przypadku **Imię** i **Nazwiska** należy wybrać opcję **Nie** w kolumnie **Wymagane weryfikacje**.
    1. W przypadku atrybutu **Adres e-mail** zaleca się pozostawienie domyślnej wartości **Tak** wybranej w kolumnie **Wymaga weryfikacji**. Ta opcja gwarantuje, że użytkownicy zarejestrowani się pod danym adresem e-mail weryfikują, czy są jego właścicielami.
    1. W przypadku **Adres e-mail**, **Imię** i **Nazwiska** należy wybrać opcję **nie** w kolumnie **Opcjonalne**.
1. Wybierz opcję **Zapisz**.

    ![Konfiguracja zasad rejestracji na koncie lokalnym.](./media/B2C_SignInSignUp_Recommended_PageLayoutExample.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Aktualizuj zasadę „Edycja profilu” przy użyciu niestandardowych informacji o stronie

Aktualizuj zasadę „Edycja profilu” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.

1. W obszarze zasady **Edycja profilu**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.
1. Wybierz układ **Strony edycji profilu** (w zależności od ekranu może być konieczne przewijanie w dół innych opcji układu).
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL edytowania profilu. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. W **Wersja układu strony** wybierz wersję **2.1.0** lub nowszą (wymaga biblioteki modułów dla wersji Commerce 10.0.15 lub nowszej).
1. W sekcji **atrybuty użytkownika** wykonaj następujące kroki:
    1. W przypadku adresu **Imię** i **Nazwiska** należy wybrać opcję **Nie** w kolumnie **Opcjonalne**.
    1. W przypadku **Imię** i **Nazwiska** należy wybrać opcję **Nie** w kolumnie **Wymagane weryfikacje**.
1. Wybierz opcję **Zapisz**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Aktualizuj zasadę „Resetowanie hasła” przy użyciu niestandardowych informacji o stronie

Aktualizuj zasadę „Resetowanie hasła” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.

1. W obszarze zasady **resetowanie hasła**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.
1. Wybierz układ **Strona Zapomniałeś hasła**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL weryfikacji resetowania hasła. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/password-reset-verification?preloadscripts=true``.
1. W polu **Wersja układu strony** wybierz wersję **2.1.0** lub nowszą (wymaga biblioteki modułów dla wersji Commerce 10.0.15 lub nowszej).
2. Wybierz opcję **Zapisz**.
3. Wybierz układ **Strona zmień hasło**.
4. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
5. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL resetowania hasła. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/password-reset?preloadscripts=true``.
6. W polu **Wersja układu strony** wybierz wersję **2.1.0** lub nowszą (wymaga biblioteki modułów dla wersji Commerce 10.0.15 lub nowszej).
7. Wybierz opcję **Zapisz**.

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Dostosowywanie domyślnych ciągów tekstowych dla etykiet i opisów

W bibliotece modułów moduły logowania są wstępnie wypełniane domyślnymi ciągami tekstowymi dla etykiet i opisów. W okienku właściwości modułu, który jest w pracy, można dostosować ciągi. Dodatkowe ciągi znaków na stronie (takie jak **Zapomniane hasło?** tekst linku lub wezwanie do działania **Utwórz konto**) będą wymagały użycia zestawu narzędzi programistycznych Commerce (SDK) i zaktualizowania wartości w plik global.json dla modułu logowania.

Na przykład domyślny tekst dla łącza zapomnianego hasła jest **Zapomniałeś hasła?**. Poniżej przedstawiono domyślny tekst na stronie rejestracji.

![Domyślny tekst łącza zapomnianego hasła na stronie rejestracji.](./media/B2C_SignUp_ModuleFace.png)

Jednak w pliku global.json dla modułu logowania biblioteki modułów można edytować tekst, aby **Zapomniałeś hasła?**, jak pokazano na poniższej ilustracji.

![Zaktualizowany tekst łącza w pliku global.json modułu rejestrowania.](./media/B2C_CustomizingStringsForModule.png)

Po zaktualizowaniu pliku global.json i opublikowaniu zmian tekst nowego łącza jest wyświetlany w module logowanie zarówno w Commerce, jak i na stronie rejestracji online.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]