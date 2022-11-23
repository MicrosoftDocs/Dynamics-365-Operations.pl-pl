---
title: Tworzenie aplikacji B2C
description: W tym artykule opisano sposób tworzenia aplikacji B2C w portalu Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785289"
---
# <a name="create-a-b2c-application"></a>Tworzenie aplikacji B2C

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób tworzenia aplikacji B2C w portalu Microsoft Azure.

Po utworzeniu dzierżawy B2C użytkownik utworzy aplikację B2C w nowej dzierżawie Azure Active Directory (Azure AD) B2C w celu interakcji z Commerce.

Aby utworzyć aplikację B2C, należy wykonać następujące czynności.

1. W portalu Azure przejdź do **Rejestracja aplikacji** i wybierz opcję **Nowa rejestracja**.
1. W obszarze **Nazwa** wprowadź nazwę aplikacji Azure AD B2C.
1. W obszarze **Obsługiwane typy kont** wybierz **Konta w dowolnym dostawcy tożsamości lub katalogu organizacyjnym (do uwierzytelniania użytkowników za pomocą przepływów użytkownika)**.
1. Dla **Przekierowywania URI** wprowadź dedykowane adresy URL odpowiedzi jako typ sieci **Web**. Patrz [Adresy URL odpowiedzi](#reply-urls) poniżej w celu znalezienia informacji na temat adresów URL oraz jak je formatować. Przekierowanie URI/odpowiedź URL musi być wprowadzone aby umożliwić przekierowania z Azure AD B2C z powrotem na twoją stronę kiedy użytkownik się uwierzytelni. Adres URL odpowiedzi może być dodany podczas procesu rejestracji lub może być dodany później poprzez wybranie linku **Dodaj URI przekierowania** z menu **Przegląd** w sekcji **Przegląd** w aplikacji B2C.
1. Aby uzyskać **Uprawnienia**, wybierz opcję **Udziel zgody administratora na urpawnienia openid i offline_access**.
1. Wybierz opcję **Zarejestruj**.
1. Wybierz nowo utworzoną aplikację i przejdź do menu **uwierzytelniania**. 
1. Jeśli wprowadzono adres URL odpowiedzi, pod **Przepływy jawne i hybrydowe** zaznacz obie opcje **Tokeny dostępu** i **Tokeny identyfikacyjne**, aby włączyć je dla aplikacji, a następnie wybierz **Zapisz**. Jeśli adres URL odpowiedzi nie został wprowadzony podczas rejestracji, może on również zostać dodany na tej stronie poprzez wybranie **Dodaj platformę**, wybranie **Sieć**, a następnie wpisanie przekierowującego URI aplikacji. W sekcji **Niejawne udzielenie i przepływy hybrydowe** będzie można wybrać zarówno opcję **Dostęp tokenowy**, jak i **Identyfikatory tokenów**.
1. Przejdź do menu **Przegląd** portalu Azure i skopiuj **Identyfikator aplikacji (klienta)**. Należy zwrócić uwagę na ten identyfikator dla późniejszych kroków konfiguracji (później jako identyfikator **GUID klienta**).

Aby uzyskać dodatkowe informacje dotyczące rejestracji aplikacji w usługach Azure AD B2C, zobacz [Nowe możliwości rejestracji aplikacji w Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>Adresy URL odpowiedzi

Adresy URL odpowiedzi są ważne, ponieważ udostępniają one listę dozwolonych domen zwracanych, gdy witryna odwołuje się do funkcji B2C w usłudze Azure AD w celu uwierzytelnienia użytkownika. Zezwala to na powrót uwierzytelnionego użytkownika z powrotem do domeny, z której się zalogował (domena witryny). 

W polu **adres URL odpowiedzi** na ekranie **B2C Azure AD — Aplikacje \> Nowa aplikacja** należy dodać osobne wiersze dla domeny witryny i (po zainicjowaniu środowiska) wygenerowany w systemie handlowym adres URL. Te adresy URL muszą zawsze mieć prawidłowy format adresu URL i muszą być tylko podstawowymi adresami URL (nie można kończyć ukośnikami ani ścieżkami). Następnie należy dołączyć ciąg ``/_msdyn365/authresp`` do podstawowych adresów URL, tak jak w poniższych przykładach.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (domena powinna być całkowicie zgodna z domeną e-commerce. Jeśli korzystasz z wielu domen, musisz dodać ten adres URL dla każdej domeny.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w Commerce, przejdź do [Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
