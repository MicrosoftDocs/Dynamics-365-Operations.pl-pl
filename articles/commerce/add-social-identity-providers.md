---
title: Dodaj dostawców tożsamości społecznościowych
description: W tym artykule opisano sposób dodawania dostawców tożsamości społecznościowych w portalu Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785280"
---
# <a name="add-social-identity-providers"></a>Dodaj dostawców tożsamości społecznościowych

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób dodawania dostawców tożsamości społecznościowych w portalu Microsoft Azure.

Dostawcy tożsamości społecznościowych umożliwiają użytkownikom uwierzytelnianie przy użyciu ich kont społecznościowych. Dodawanie uwierzytelniania dostawcy tożsamości społecznościowej jest opcjonalne w programie Dynamics 365 Commerce. 

Jeśli uwierzytelnianie dostawcy tożsamości społecznościowej nie zostanie dodane, domyślne profile B2C Azure Active Directory (Azure AD) będą głównymi profilami bazy danych użytkownika. Użytkownicy będą mogli wybrać własną nazwę użytkownika (preferowany adres e-mail) i określić hasło. B2C Azure AD będą uwierzytelniać użytkowników bezpośrednio. 

Jeśli zostanie dodane uwierzytelnianie dostawcy tożsamości społecznej, a użytkownik wybierze jednego z oferowanych dostawców tożsamości społecznych, jednostka nadal zostanie utworzona w dzierżawie B2C Azure AD. B2C Azure AD będzie wówczas uwierzytelniać poświadczenia użytkownika za pomocą dostawcy tożsamości społecznościowej.

> [!NOTE]
> W trakcie logowania dostawca tożsamości tworzy rekord w dzierżawie B2C, ale w innym formacie niż konta lokalne, ponieważ będzie wywoływać odwołanie do zewnętrznego dostawcy tożsamości społecznościowej w celu uwierzytelnienia. Użytkownik może używać tego samego adresu e-mail dla dostawców tożsamości społecznych, co oznacza, że nazwa użytkownika poczty e-mail używana do uwierzytelniania może nie być unikatowa dla dzierżawcy. B2C Azure AD wymusza, aby użytkownicy mieli unikatowy adres e-mail tylko na lokalnych kontach B2C.

Zanim będzie można dodać dostawcę tożsamości społecznościowej do uwierzytelniania, należy przejść do portalu dostawcy tożsamości i skonfigurować aplikację dostawcy tożsamości zgodnie z instrukcją w dokumentacji B2C Azure AD. Poniżej znajduje się lista łączy do dokumentacji.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Jeden dzierżawca)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Konto Microsoft](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Dodaj i skonfiguruj dostawcę tożsamości społecznościowej

> [!NOTE]
> Dodawanie dostawców tożsamości społecznościowych to opcjonalny krok podczas konfigurowania dzierżawy B2C w Microsoft Dynamics 365 Commerce.

Aby dodać i skonfigurować dostawcę tożsamości społecznościowej, należy wykonać następujące kroki.  

1. W portalu Azure przejdź do **dostawców tożsamości**.
1. Wybierz opcję **Dodaj**. Pojawi się ekran **Dodaj dostawcę tożsamości**.
1. W polu **Nazwa** wprowadź nazwę, która ma być wyświetlana użytkownikom na ekranie logowania.
1. W obszarze **Typ dostawcy tożsamości** wybierz dostawcę tożsamości z listy.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Skonfiguruj tego dostawcę tożsamości**, aby uzyskać dostęp do ekranu **Konfigurowanie dostawcy tożsamości społecznych**.
1. W obszarze **Identyfikator klienta** wprowadź identyfikator klienta, który został otrzymany z konfiguracji aplikacji dostawcy tożsamości.
1. W obszarze **Nazwa tajna klienta** wprowadź nazwę tajną klienta, która została otrzymana z konfiguracji aplikacji dostawcy tożsamości.
1. Dołącz przepływ użytkownika dla logowania w zasadach rejestracji:
1. Przejdź do **B2C Azure AD — przepływy tożsamości \> {zasady logowania rejestracji użytkowników} \> Dostawcy tożsamości**.
1. Aby dołączyć zasadę przepływu użytkowników logowania/rejestracji, wybierz każdego dostawcę tożsamości skonfigurowanego dla swojego konta. Aby przetestować przepływy, wybierz opcję **Uruchom przepływ użytkownika** dla każdego dostawcy tożsamości. Na nowej karcie zostanie wyświetlona strona logowania z wyświetlonym polem wyboru nowego dostawcy tożsamości.

Na poniższym obrazie pokazano przykłady **dodawania dostawcy tożsamości** i **konfigurowania ekranów dostawcy tożsamości społecznościowych** w B2C Azure AD.

![Dodawanie dostawcy tożsamości społecznościowej do aplikacji.](./media/B2CImage_14.png)

Poniższy rysunek przedstawia przykład wyboru dostawców tożsamości na stronie **dostawców tożsamości** B2C Azure AD.

![Wybierz każdego dostawcę tożsamości społecznościowych, który ma być włączony dla zasady.](./media/B2CImage_16.png)

Poniższy obraz przedstawia przykład domyślnego ekranu logowania z wyświetlonym przyciskiem logowania dostawcy tożsamości społecznościowej.

> [!NOTE]
> Jeśli w usługach commerce wbudowywały strony niestandardowe, trzeba dodać przyciski dostawców tożsamości społecznościowych, korzystając z funkcji możliwości rozszerzania biblioteki modułów Commerce. Ponadto podczas konfigurowania aplikacji z określonym dostawcą tożsamości społecznościowych w niektórych przypadkach adres URL lub ciągi konfiguracji mogą być wielkość liter. Zapoznaj się z instrukcjami połączenia z dostawcą tożsamości społecznościowych, aby uzyskać więcej informacji.
 
![Przykładowy domyślny ekran logowania z wyświetlonym przyciskiem logowania dostawcy tożsamości społecznościowej.](./media/B2CImage_17.png)

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w usługach Commerce, przejdź [Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
