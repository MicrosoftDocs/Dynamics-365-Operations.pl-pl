---
title: Tworzenie zasad przepływów użytkownika
description: W tym artykule opisano sposób tworzenia zasad przepływu użytkowników w portalu Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785307"
---
# <a name="create-user-flow-policies"></a>Tworzenie zasad przepływów użytkownika

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób tworzenia zasad przepływu użytkowników w portalu Microsoft Azure.

Przepływy użytkowników to zasady, które relacja od firmy do konsumenta (B2C) Azure Active Directory (Azure AD) stosuje w celu zapewnienia bezpiecznego logowania, zapisywania się, edytowania profilu i zapomnienia hasła użytkownika. Dynamics 365 Commerce używa tych przepływów do wykonywania akcji związanych z zasadami dotyczącymi interakcji z dzierżawcą B2C Azure AD. Gdy użytkownik współpracuje z tymi zasadami, są one przekierowywane do dzierżawy B2C Azure AD w celu wykonania akcji.

W B2C Azure AD dostępne są trzy podstawowe typy przepływu użytkownika:
- Rejestracja i logowanie
- Edytowanie profilu
- Resetowanie hasła

Można wybrać Używanie domyślnego przepływu użytkownika dostarczonego przez Azure AD, który będzie wyświetlał stronę hostowaną przez B2C Azure AD. Alternatywnie można utworzyć stronę HTML umożliwiającą sterowanie wyglądem i działaniem tych funkcji przepływu pracy użytkownika. 

Aby dostosować strony zasad użytkowników ze stronami wybudowanymi w Dynamics 365 Commerce, należy zapoznać się z tematami [Konfigurowanie niestandardowych stron logowania użytkowników](custom-pages-user-logins.md). Aby uzyskać dodatkowe informacje, należy zapoznać się z tematem [Dostosowywanie interfejsu środowiska użytkownika w B2C Azure Active Directory](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Utwórz zasadę przepływu użytkownika rejestracji i logowania

Aby utworzyć zasady przepływu użytkownika dla rejestracji i logowania, wykonaj następujące kroki.

1. W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.
1. Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.
1. Wybierzwybierz zasadę **Rejestracja i logowanie**, a wybierz werjsę **Rekomendowane**.
1. W polu **Nazwa** wprowadź nazwę zasady. Ta nazwa będzie wyświetlana następnie z prefiksem przypisanym przez portal (na przykład „B2C_1_”).
1. W zakładce **Dostawcy tożsamości**, w sekcji **Konta lokalne** wybierz **Rejestracja przez e-mail**. Uwierzytelnianie przez e-mail jest używane w większości typowych scenariuszy dla Commerce. Jeśli używasz również uwierzytelniania przez dostawców tożsamości społecznej, możesz je również wybrać w tym momencie.
1. W obszarze **uwierzytelnianie wieloczynnikowe** wybierz odpowiedni wybór dla firmy. 
1. W obszarze **atrybuty użytkownika i oświadczenia** wybierz opcje, aby w razie potrzeby zebrać atrybuty lub roszczenia zwrotów. Wybierz pozycję **Pokaż więcej...**, aby uzyskać pełną listę atrybutów i opcji roszczeń. W rozwiązaniu Commerce są wymagane następujące opcje domyślne:

    | **Zbierz atrybuty** | **Roszczenie zwrotu** |
    | ---------------------- | ----------------- |
    | Adres e-mail          | Adresy e-mail   |
    | Imię             | Imię        |
    |                        | Dostawca tożsamości |
    | Nazwisko                | Nazwisko           |
    |                        | Identyfikator obiektu użytkownika  |

1. Wybierz opcję **Utwórz**.

Poniższy obraz przedstawia przykład B2C Azure AD rejestracji i logowania w przepływie użytkownika.

![Ustawienia zasad rejestracji i logowania.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Tworzenie zasady przepływu użytkowników dla edycji profilu

Aby utworzyć zasady przepływu użytkownika dla edycji profilu, wykonaj następujące kroki.

1. W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.
1. Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.
1. Wybierz opcję **Edytowanie profilu**, a następnie wybierz wersję **Rekomendowane**.
1. W polu **Nazwa** wprowadź przepływ użytkownika edycji profilu. Ta nazwa będzie wyświetlana następnie z prefiksem przypisanym przez portal (na przykład „B2C_1_”).
1. W zakładce **Dostawcy tożsamości**, w sekcji **Konta lokalne** wybierz **Rejestracja przez e-mail**.
1. W obszarze **Atrybuty użytkownika** zaznacz jedno z następujących pól wyboru:
    
    | **Zbierz atrybuty** | **Roszczenie zwrotu** |
    | ---------------------- | ----------------- |
    |                        | Adresy e-mail   |
    | Imię             | Imię        |
    |                        | Dostawca tożsamości |
    | Nazwisko                | Nazwisko           |
    |                        | Identyfikator obiektu użytkownika  |
    
1. Wybierz opcję **Utwórz**.

Poniższy obraz przedstawia przykład przepływu użytkownika edytującego profil w B2C Azure AD.

![Przykład przepływu użytkowników edytujących profil B2C w Azure AD](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Tworzenie zasady przepływu użytkowników dla resetowania hasła

Aby utworzyć zasady przepływu użytkownika dla resetowania hasła, wykonaj następujące kroki.

1. W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.
1. Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.
1. Wybierz opcję **resetowanie hasła**, a następnie wybierz wersję **Rekomendowane**.
1. W polu **Nazwa** wprowadź nazwę przepływu użytkownika resetowania hasła.
1. W sekcji **dostawcy tożsamości** wybierz opcję **Resetuj hasło, używając adresu e-mail**.
1. Wybierz opcję **Utwórz**.
1. W obszarze **Przetwarzanie aplikacji** zaznacz jedno z następujących pól wyboru:
    - **Adresy e-mail**
    - **Imię**
    - **Nazwisko**
    - **Identyfikator obiektu użytkownika**
1. Wybierz opcję **Utwórz**.

Poniższy obraz pokazuje, gdzie ustawić **hasło resetowania przy użyciu adresu pocztowego** w przepływie użytkownika resetowania hasła B2C Azure AD.

![Ustawienie „Resetuj hasło przy użyciu adresu pocztowego” w zasadach resetowania hasła](./media/B2CImage_13.png)

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w Commerce, przejdź do [Dodaj dostawców tożsamości społecznościowych](add-social-identity-providers.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
