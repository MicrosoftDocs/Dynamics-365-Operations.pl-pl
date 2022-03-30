---
title: Tworzenie witryny handlu elektronicznego
description: W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 37734e2ceea3a50c70a2f7945329d4a9cf660cc6
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2022
ms.locfileid: "8402782"
---
# <a name="create-an-e-commerce-site"></a>Tworzenie witryny handlu elektronicznego

[!include [banner](includes/banner.md)]

W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.

Po nadaniu licencji na funkcje Dynamics 365 Commerce, funkcja konstruktora witryn zostanie wdrożona wraz z witryną startową, którą można wykorzystać jako podstawę dla własnego oddziału. Jeśli jednak użytkownik chce rozpocząć od zera lub chce stworzyć drugą witrynę, musi utworzyć nową witrynę w środowisku tworzenia witryn. 

## <a name="site-creation-prerequisites"></a>Wymagania wstępne dotyczące tworzenia witryny

Użytkownik konstruktora lokacji musi mieć konto użytkownika Microsoft Azure Active Directory (Azure AD) uwzględnione w grupie zabezpieczeń Azure AD przypisanej do administratorów systemu handlu elektronicznego. Aby uzyskać więcej informacji, zobacz [Wdrażanie nowej dzierżawy usługi e-commerce](deploy-ecommerce-site.md).

> [!NOTE]
> Użytkownicy-gości usługi Azure AD mogą mieć różne uprawnienia dostępu w dzierżawie usługi Azure AD. Nawet jeśli użytkownik jest uwzględniony w grupie zabezpieczeń Azure AD przypisanej dla administratorów systemu handlu elektronicznego, użytkownik-gość może wymagać dostosowania ustawień uprawnień usługi Azure AD **Użytkownicy zewnętrzni** w celu utworzenia witryny handlu elektronicznego w aplikacji Commerce. 

Aby dostosować ustawienia usługi Azure AD **Zewnętrzni użytkownicy**, wykonaj następujące kroki.

1. W portalu Azure przejdź do dzierżawy usługi Azure AD.
1. Przejdź do **ustawień użytkownika \> Użytkownicy zewnętrzni** i wybierz łącze **Zarządzaj ustawieniami współpracy zewnętrznej**. Spowoduje to otwarcie strony **Ustawienia współpracy zewnętrznej**, na której można ustawić dostęp użytkownika-gościa, ustawienia zapraszania gościa i ograniczenia współpracy. 
1. Dostosuj ustawienia współpracy zewnętrznej zgodnie z zasadami zabezpieczeń firmy. 

## <a name="set-up-your-site"></a>Konfigurowanie witryny

Aby skonfigurować witrynę, wykonaj następujące czynności.

1. Otwórz środowisko budowania witryn. Łącze do kreatora witryn w usłudze Microsoft Lifecycle Services (LCS) można znaleźć na stronie Funkcje środowiska w Commerce.
1. Następnie na stronie głównej dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**.
1. W oknie dialogowym **Nowa witryna** wprowadź następujące informacje.

| Pole                               | Opis |
|-------------------------------------|-------------|
| Nazwa witryny                           | Umożliwia wprowadzenie nazwy wyświetlanej, która powinna być używana w odniesieniu do danej witryny w środowisku tworzenia witryn. Ta nazwa jest widoczna tylko w środowisku autorskim i nie będzie wyświetlana klientom. |
| Grupa zabezpieczeń administratora witryny | Określ grupę zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zarządza użytkownikami dysponującymi rolą administratora witryny w tej witrynie. |
| Kanał domyślny (numer jednostki operacyjnej) | Wybierz sklep internetowy, który będzie pełnić tę witrynę jako sklep sieci Web. Jeśli chcesz, aby witryna e-Commerce obsługiwała wiele sklepów internetowych, musisz skojarzyć te sklepy z serwisem w **Ustawieniach witryny** po skonfigurowaniu witryny. |
| Język domyślny                            | Umożliwia określenie domyślnego języka dla tego sklepu i rynku online. Sklep internetowy może obsługiwać wiele języków. Jeśli chcesz obsługiwać wiele języków dla tego sklepu internetowego lub innego sklepu internetowego, możesz skonfigurować tę obsługę w **Ustawieniach witryny** po skonfigurowaniu witryny.  |
| Domena                              | Wybierz nazwę domeny, która będzie służyć jako domena dla tego sklepu internetowego. Jeśli nie skonfigurowano żadnych domen w usłudze LCS, to pole można pozostawić puste. Po skonfigurowaniu domeny w usługi LCS, należy ją dodać do swojego sklepu internetowego w **Ustawieniach witryny**.  |
| Ścieżka                              | Jeśli witryna obsługuje więcej niż jeden język dla danej nazwy domeny, użyj pola ścieżki, aby utworzyć unikalny adres URL witryny dla tej kombinacji domeny i języka. Jeśli język określony w polu **Język domyślny** jest jedynym językiem, który będzie obsługiwany dla tej domeny, lub będzie używany domyślny język po zlokalizowaniu witryny w dodatkowych językach, zaleca się pozostawienie tego pola pustego. |

Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **Produkty**. Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego. Możesz także użyć menu rozwijanego w lewym górnym rogu strony, aby uzyskać dostęp do przydzielonych produktów według kategorii.

## <a name="rename-your-site"></a>Zmiana nazwy witryny

Aby zmienić nazwę witryny w kreatorze witryn, wykonaj poniższe kroki.

1. Aby otworzyć widok listy witryn, wybierz Opcję **Przełączania witryn** w prawym górnym rogu, a następnie wybierz pozycję **Zarządzaj witrynami**. 
1. Zaznacz pole wyboru obok witryny, której nazwę chcesz zmienić, a następnie wybierz pozycję **Zmień nazwę** na pasku poleceń.
1. W oknie dialogowym **Nowa nazwa witryny**, wprowadź nazwę, a następnie wybierz **OK**. Lista witryn zostanie zaktualizowana tak, by pokazywała ich nową nazwę.

## <a name="delete-a-site"></a>Usunięcie witryny

Aby usunąć witrynę w Kreatorze witryn, wykonaj następujące kroki.

1. Aby otworzyć widok listy witryn, wybierz Opcję **Przełączania witryn** w prawym górnym rogu, a następnie wybierz pozycję **Zarządzaj witrynami**.
1. Wybierz witrynę, którą chcesz usunąć, a następnie wybierz pozycję **Usuń** na pasku poleceń.
1. W oknie dialogowym **Usuń \<site name\>** wprowadź nazwę witryny, a następnie wybierz **Usuń**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
