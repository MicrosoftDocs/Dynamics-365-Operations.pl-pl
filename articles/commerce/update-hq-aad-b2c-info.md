---
title: Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD
description: W tym artykule opisano sposób aktualizowania centrali Microsoft Dynamics 365 Commerce headquarters o nowe informacje dotyczące firmy-konsumenta (B2C) Azure Active Directory (Azure AD).
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785325"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób aktualizowania centrali Microsoft Dynamics 365 Commerce headquarters o nowe informacje dotyczące firmy-konsumenta (B2C) Azure Active Directory (Azure AD).

Po wykonaniu powyższej procedury B2C Azure AD, aplikacja B2C Azure AD musi być zarejestrowana w środowisku Dynamics 365 Commerce.

Aby zaktualizować centralę za pomocą nowych informacji B2C Azure AD, wykonaj następujące kroki.

1. W module Commerce przejdź do **udostępnionych parametrów modułu Commerce** i wybierz pozycję **dostawcy tożsamości** w lewym menu.
1. W obszarze **dostawcy tożsamości** wykonaj następujące czynności:
    1. W polu **wystawca** wprowadź ciąg wystawcy dostawcy tożsamości. Aby znaleźć ciąg wystawcy, zobacz temat [Uzyskiwanie ciągu wystawcy dla konfiguracji centrali poniżej](#obtain-issuer-string-for-headquarters-setup).
    1. W polu **nazwa** wprowadź nazwę rekordu wystawcy.
    1. W polu **typ** wprowadź **B2C Azure AD (id_token)**.
1. W obszarze **jednostki uzależnione**, z zaznaczonym powyższym elementem dostawcy tożsamości B2C, wykonaj następujące czynności:
    1. W polu **ClientID** wprowadź identyfikator aplikacji B2C, który można znaleźć w polu **Identyfikator aplikacji** na stronie właściwości aplikacji B2C.
    1. W polu **typ** wprowadź wartość **publiczne**.
    1. W polu **typ użytkownika** wprowadź wartość **Odbiorca**.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W polu Wyszukiwanie w module Commerce należy wyszukać **harmonogram dystrybucji**
1. W menu nawigacji w lewym panelu na stronie **harmonogramy dystrybucji** wybierz zadanie **Konfiguracja globalna 1110**.
1. W okienku akcji wybierz opcję **Uruchom teraz**.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Uzyskiwanie ciągu wystawcy dla ustawień centrali

Aby uzyskać ciąg wystawcy dostawcy tożsamości, wykonaj następujące kroki.

1. Na stronie Azure AD B2C portalu Azure przejdź do przepływu użytkownika **Rejestracja i logowanie**.
1. Wybierz **układy stron** w menu nawigacji po lewej stronie, w obszarze **Nazwa układu** wybierz pozycję **Zunifikowane konto** lub strona logowania, a następnie wybierz polecenie **Uruchom przepływ użytkownika**.
1. Upewnij się, że aplikacja jest ustawiona zgodnie z zamierzaną aplikacją Azure AD utworzoną powyżej, a następnie wybierz łącze przepływu użytkownika, które pojawia się pod nagłówkiem **Uruchom przepływ użytkownika**, który zawiera ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``. (Nie zaznaczaj **Uruchom przepływ użytkownika**) Zostanie otwarta nowa karta przedstawiająca metadane dla zasad w celu zbierania ciągu wystawcy.
1. Na stronie metadanych wyświetlanej w karcie przeglądarki skopiuj ciąg wystawcy dostawcy tożsamości (wartość **wystawcy** rozpoczynającą się od „https://” i kończący się literą „/v2.0/” ), który jest podobny do poniższego przykładu.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**LUB**: Aby ręcznie utworzyć ten sam adres URL metadanych, należy wykonać następujące kroki.

1. Utwórz adres URL metadanych w poniższym formacie przy użyciu dzierżawy i zasad B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Przykład: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``
1. Wprowadź adres URL metadanych na pasku adresu przeglądarki.
1. W metadanych Skopiuj adres URL wystawcy dostawcy tożsamości (wartość dla **„wystawca”**).
    - Przykład: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w Commerce, przejdź do [Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
