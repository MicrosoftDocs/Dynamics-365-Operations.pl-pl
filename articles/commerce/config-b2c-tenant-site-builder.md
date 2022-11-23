---
title: Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce
description: W tym artykule opisano sposób konfigurowania dzierżawy typu business-to-consumer (B2C) w narzędziu do tworzenia witryn Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785316"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania dzierżawy typu business-to-consumer (B2C) w narzędziu do tworzenia witryn Microsoft Dynamics 365 Commerce.

Po zakończeniu konfigurowania dzierżawy B2C Azure AD należy skonfigurować dzierżawę B2C w module kreatora witryny Commerce. Kroki konfiguracyjne obejmują zbieranie informacji o aplikacji B2C z portalu Azure, wprowadzenie do konstruktora witryn informacji o aplikacji B2C, a następnie skojarzenie aplikacji B2C z witryną i kanałem.

### <a name="collect-the-required-application-information"></a>Zbierz wymagane informacje o aplikacji

Aby zebrać wymagane informacje o aplikacji, wykonaj następujące kroki.

1. W portalu Azure przejdź do **Strony głównej \> B2C Azure AD — rejestracja aplikacji**.
1. Wybierz aplikację, a następnie w lewym okienku nawigacji wybierz **Przegląd**, aby uzyskać szczegółowe informacje o aplikacji.
1. W odnośniku **Identyfikator aplikacji (klient)** Zbierz identyfikator aplikacji B2C utworzonej w dzierżawie B2C. Zostanie to później wprowadzone jako **identyfikator GUID klienta** w module Konstruktor witryn.
1. Wybierz **Przekieruj adresy URL** i pobierz adres URL odpowiedzi pokazany dla twojej strony (adres URL odpowiedzi wpisany podczas konfiguracji).
1. Przejdź do **Strona główna \> B2C Azure AD — przepływy użytkownika**, a następnie Zbierz pełne nazwy poszczególnych zasad przepływu użytkowników.

Poniższy rysunek przedstawia przykład strony przeglądowej **B2C Azure AD — rejestracje aplikacji**.

![Azure AD B2C — strona przeglądu rejestracji aplikacji z zaznaczonym ID aplikacji (klienta)](./media/ClientGUID_Application_AzurePortal.png)

Poniższy obraz przedstawia przykład zasad przepływu użytkowników na stronie **B2C Azure AD — przepływy użytkownika (zasady)**.

![Zbierz nazwy poszczególnych przepływów zasad B2C.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Umożliwia wprowadzenie informacji dotyczących aplikacji dzierżawczej usługi Azure AD B2C do modułu Commerce

Przed skojarzeniem dzierżawy B2C Azure AD z witrynami należy wprowadzić szczegóły dzierżawy B2C w module konstruktora witryn Commerce.

Aby dodać informacje dotyczące aplikacji dzierżawczej usługi B2C Azure AD do systemu Commerce, wykonaj następujące kroki.

1. Zaloguj się jako administrator do modułu konstruktora witryn Commerce dla swojego środowiska.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia dzierżawcy**, aby ją rozwinąć.
1. W **obszarze Ustawienia dzierżawcy** wybierz **konfigurację uwierzytelniania witryny**. 
1. W głównym oknie obok **profilów uwierzytelniania witryny** wybierz pozycję **Zarządzaj**. (Jeśli dzierżawca pojawia się na liście profili uwierzytelniania witryny, oznacza to, że został już dodany przez administratora. Sprawdź, czy elementy w kroku 6 poniżej są zgodne z zamierzoną konfiguracją B2C. Nowy profil można również utworzyć przy użyciu podobnych dzierżaw lub aplikacji usługi Azure AD B2C w celu uwzględnienia drobnych różnic, takich jak różne identyfikatory zasad użytkownika).
1. Wybierz **Dodaj profil uwierzytelniania witryny**.
1. Wprowadź w wyświetlonym formularzu następujące wymagane elementy, używając wartości ze swojej dzierżawy B2C i aplikacji. Pola, które nie są wymagane (bez gwiazdki), mogą pozostać puste.

    - **Nazwa aplikacji**: Nazwa aplikacji B2C, na przykład „Fabrikam B2C”.
    - **Nazwa dzierżawy**: nazwa dzierżawy funkcji B2C (na przykład „fabrikam”, jeśli domena jest wyświetlana jako „fabrikam.onmicrosoft.com” dla dzierżawcy B2C). 
    - **Identyfikator zasady zapominania hasła**: identyfikator zasady przepływu użytkownika zapominania hasła, na przykład „B2C_1_PasswordReset”.
    - **Identyfikator zasad logowania rejestracji**: Identyfikator zasad tworzenia konta i logowania użytkownika, na przykład „B2C_1_signup_signin”.
    - **Identyfikator GUID klienta**: Identyfikator aplikacji B2C, na przykład „22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6”.
    - **Identyfikator zasad edycji profilu**: Identyfikator zasad przepływu użytkownika edycji profilu, na przykład „B2C_1A_ProfileEdit”.

1. Kliknij przycisk **OK**. Na liście powinna być widoczna nazwa aplikacji B2C.
1. Wybierz **Zapisz**, żeby zapisać zmiany.

Opcjonalne niestandardowe **pole domeny logowania** powinno być używane tylko podczas konfigurowania niestandardowej domeny dla dzierżawy usługi Azure AD B2C. Aby uzyskać dodatkowe informacje i uwagi dotyczące korzystania z pola **Logowanie domeny niestandardowej**, zobacz [Dodatkowe informacje B2C](additional-b2c-info.md).

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Skojarz aplikację B2C z witryną i kanałem

> [!WARNING]
> - Jeśli witryna jest już skojarzona z aplikacją B2C, zmiana w innej aplikacji B2C spowoduje usunięcie bieżących odwołań ustanowionych dla użytkowników już zarejestrowanych w tym środowisku. W przypadku zmiany wszelkie poświadczenia skojarzone z aktualnie przypisaną aplikacją B2C nie będą dostępne dla użytkowników. 
> - Aplikację B2C należy aktualizować tylko wtedy, gdy jest ustawiany kanał aplikacji B2C po raz pierwszy lub jeśli użytkownik chce, aby użytkownicy mogli ponownie rejestrować się z nowymi poświadczeniami w tym kanale z nową aplikacją B2C. Należy zachować ostrożność podczas kojarzenia kanałów z aplikacjami B2C i jasno określać nazwy aplikacji. Jeśli kanał nie jest skojarzony z aplikacją B2C w poniższych krokach, użytkownicy logujący się do tego kanału witryny będą wprowadzani do aplikacji B2C, która jest wyświetlana **domyślnie** na liście aplikacji B2C **Ustawienia dzierżawcy \> Ustawienia B2C**.

Aby skojarzyć aplikację B2C z witryną i kanałem, wykonaj poniższe kroki.

1. Przejdź do swojej witryny w module konstruktora witryn Commerce.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.
1. W obszarze **Ustawienia witryny** wybierz opcję **kanały**.
1. W oknie głównym w obszarze **kanały** wybierz kanał.
1. W okienku właściwości kanału z prawej strony wybierz nazwę aplikacji B2C z menu rozwijanego **wybierz aplikację B2C**.
1. Wybierz opcję **Zamknij**, a następnie wybierz opcję **Zapisz i opublikuj**.

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w Commerce, przejdź do [Informacje dodatkowe o B2C](additional-b2c-info.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
