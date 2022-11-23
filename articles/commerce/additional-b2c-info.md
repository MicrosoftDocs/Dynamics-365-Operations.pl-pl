---
title: Informacje dodatkowe o B2C
description: Ten artykuł zawiera dodatkowe informacje dotyczące sposobu ustawiania dzierżawcy B2C w Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785271"
---
# <a name="additional-b2c-information"></a>Informacje dodatkowe o B2C

[!include [banner](includes/banner.md)]

Ten artykuł zawiera dodatkowe informacje dotyczące sposobu ustawiania dzierżawcy B2C w Microsoft Dynamics 365 Commerce.

### <a name="customer-migration"></a>Migracja odbiorcy

Jeśli rozważasz Migrowanie rekordów klientów z poprzedniej platformy dostawców tożsamości, skontaktuj się z zespołem Dynamics 365 Commerce, aby przejrzeć potrzeby dotyczące migracji odbiorców.

Aby uzyskać dodatkową dokumentację B2C Azure AD dotyczącą migracji klientów, należy zapoznać się z tematem [Migrowanie użytkowników do B2C Azure Active Directory](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Zasady niestandardowe

Aby uzyskać dodatkowe informacje dotyczące dostosowywania interakcji B2C Azure AD i przepływów zasad ponad to, co jest oferowane przez zasady standardowe B2C, zapoznać się z [zasadami niestandardowymi w B2C Azure Active Directory](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrator pomocniczy

W sekcji **użytkownicy** dzierżawy B2C można dodać opcjonalne pomocnicze konto administratora. Może to być konto bezpośrednie lub konto ogólne. Jeśli trzeba udostępnić konto w zasobach zespołu, można również utworzyć wspólne konto. Ze względu na wagę danych przechowywanych w B2C Azure AD, wspólne konto powinno być ściśle monitorowane zgodnie z zasadami zabezpieczeń firmy.

### <a name="set-up-a-custom-sign-in-domain"></a>Konfigurowanie niestandardowej domeny logowania

Azure AD B2C umożliwia skonfigurowanie niestandardowej domeny logowania dla dzierżawy Azure AD B2C. Aby uzyskać instrukcje, zobacz temat [Włączanie domen niestandardowych dla Azure Active Directory B2C](/azure/active-directory-b2c/custom-domain). 

W przypadku korzystania z niestandardowej domeny logowania, należy ją wprowadzić do Konstruktora witryn commerce.

Aby wprowadzić niestandardową domenę logowania w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. W prawym górnym rogu narzędzia do tworzenia witryn wybierz przełącznik witryn, a następnie wybierz **Zarządzaj witrynami**.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia dzierżawcy \> Ustawienia uwierzytelniania witryny**.
1. W sekcji **profilów uwierzytelniania witryny** wybierz pozycję **Zarządzaj**.
1. W menu wysuwu po prawej stronie wybierz przycisk **Edytuj** (symbol symbolu skrótu) obok profilu uwierzytelniania witryny, dla którego chcesz wprowadzić niestandardową domenę.
1. W oknie dialogowym **Edytowanie profilu uwierzytelniania** witryny w obszarze **Domena niestandardowa logowania** wprowadź niestandardową domenę logowania (na przykład „login.fabrikam.com”).

> [!WARNING]
> Podczas aktualizowania niestandardowej domeny dla dzierżawy Azure AD B2C zmiana wpływa na szczegóły wystawcy dzierżawy dla wygenerowanego tokenu. Szczegóły wystawcy będą zawierać domenę niestandardową, a nie domyślną domenę dostarczaną przez Azure AD B2C. Inna konfiguracja **Wydawca** w Commerce headquarters (**Handel detaliczny i handel \> Konfiguracja Headquarters \> Parametry \> Parametry wspólne dla handlu \> Dostawcy tożsamości**) zmienia sposób interakcji systemu z użytkownikami witryny, potencjalnie tworzenie nowego rekordu klienta, jeśli użytkownik uwierzytelnia się wobec nowego wystawcy. Wszelkie niestandardowe zmiany domeny należy dokładnie przetestować przed przełączeniem do niestandardowej domeny w środowisku Azure AD B2C na żywo.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
