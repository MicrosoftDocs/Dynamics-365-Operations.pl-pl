---
title: Konfigurowanie dzierżawy B2C w usłudze Commerce
description: W tym temacie opisano sposób konfigurowania dzierżawcy Azure Active Directory (Azure AD) dzierżawców biznesowych (B2C) dla uwierzytelniania witryny użytkownika w programie Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BriShoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: b017b0f91960be1504134f6d46878fce956de203
ms.sourcegitcommit: 8a1621327568edf49758b70964e0a3e637527e1b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2020
ms.locfileid: "3497175"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Konfigurowanie dzierżawy B2C w usłudze Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania dzierżawcy Azure Active Directory (Azure AD) dzierżawców biznesowych (B2C) dla uwierzytelniania witryny użytkownika w programie Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Dynamics 365 Commerce używa Azure AD B2C do obsługi przenoszonych poświadczeń i przepływów uwierzytelniania użytkowników. Użytkownik może zarejestrować się, zalogować się i zresetować swoje hasło za pośrednictwem tych przepływów. Azure AD B2C przechowuje poufne informacje o uwierzytelnianiu użytkownika, takie jak nazwa użytkownika i hasło. Rekord użytkownika w dzierżawie B2C będzie przechowywał zarówno rekord konta lokalnego B2C, jak i rekord dostawcy tożsamości socjalnej B2C. Te rekordy B2C zostaną połączone z rekordem odbiorcy w środowisku Commerce.

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a>Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze AAD w portalu Azure

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/).
1. W menu portalu Azure wybierz polecenie **Utwórz zasób**. Należy pamiętać o użyciu subskrypcji i katalogu, który będzie połączony ze środowiskiem Commerce.

    ![Utwórz zasób w portalu Azure](./media/B2CImage_1.png)

1. Przejdź do **Tożsamość \> Azure Active Directory B2C**.
1. Na stronie **Utwórz nowego B2C dzierżawę lub Połącz z istniejącą stroną dzierżawy**, Skorzystaj z jednej z poniższych opcji, która najlepiej pasuje do potrzeb firmy:

    - **Utwórz nową dzierżawę B2C Azure AD**: Ta opcja służy do utworzenia nowej dzierżawy B2C w usłudze AAD.
        1. Wybierz **Stwórz nową dzierżawę B2C Azure AD**.
        1. W obszarze **Nazwa organizacji** wprowadź nazwę organizacji.
        1. W obszarze **początkowa nazwa domeny** wprowadź początkową nazwę domeny.
        1. W przypadku **kraju lub regionu** wybierz kraj lub region.
        1. Wybierz przycisk **Utwórz**, aby utworzyć dzierżawę.

     ![Tworzenie nowej dzierżawy Azure AD](./media/B2CImage_2.png)

     - **Połącz istniejącą dzierżawę B2C Azure AD z moją subskrypcją systemu Azure**: Tę opcję należy użyć, jeśli istnieje już dzierżawa B2C Azure AD, do której ma zostać utworzone łącze.
        1. Wybierz **łącze do istniejącej dzierżawy B2C Azure AD do mojej subskrypcji systemu Azure**.
        1. W **Dzierżawa B2C Azure AD** wybierz odpowiednią dzierżawę B2C. Jeśli w polu wyboru zostanie wyświetlona wiadomość „nie znaleziono dzierżawców B2C”, nie masz istniejącej uprawnionej dzierżawy B2C i będzie konieczne utworzenie nowej.
        1. W **Grupie zasobów** wybierz opcję **Utwórz nową**. Wprowadź **nazwę** grupy zasobów, która będzie zawierać dzierżawcę, wybierz **lokalizację grupy zasobów**, a następnie wybierz pozycję **Utwórz**.

    ![Wybierz łącze do istniejącej dzierżawy B2C Azure AD do subskrypcji systemu Azure](./media/B2CImage_3.png)

1. Po utworzeniu nowego katalogu B2C Azure AD (może to chwilę potrwać) na pulpicie nawigacyjnym pojawi się łącze do nowego katalogu. To łącze spowoduje przekierowanie do strony „Witamy w B2C usługi Azure Active Directory”.

    ![Połącz z nowym katalogiem usługi AAD](./media/B2CImage_4.png)

> [!NOTE]
> Jeśli masz wiele subskrypcji na koncie systemu Azure lub skonfigurowano dzierżawcę B2C bez łączenia z aktywną subskrypcją, transparent do **rozwiązywania problemów** poinformuje dzierżawcę o połączeniu z subskrypcją. Wybierz komunikat rozwiązywania problemów i postępuj zgodnie z instrukcjami, aby rozwiązać problem z subskrypcją.

Poniższy obraz przedstawia przykład transparentu B2C Azure AD **Rozwiązywanie problemów**.

![Ostrzeżenie pokazujące katalog, który nie ma aktywnej subskrypcji](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Tworzenie aplikacji B2C

Po utworzeniu dzierżawy B2C użytkownik utworzy aplikację B2C w dzierżawie w celu interakcji z akcjami Commerce.

Aby utworzyć aplikację B2C, należy wykonać następujące czynności.

1. W portalu Azure wybierz opcję **aplikacje**, a następnie wybierz opcję **Dodaj**.
1. W polu **Nazwa** wprowadź nazwę żądanej aplikacji B2C w usłudze AAD.
1. W obszarze **Aplikacji sieci Web/API sieci Web** dla **Dołącz aplikację sieci Web/API sieci Web** wybierz **Tak**.
1. W przypadku **Zezwól na dorozumiany przepływ** wybierz opcję **Tak** (wartość domyślna).
1. W obszarze **Adres URL odpowiedzi** wprowadź dedykowane adresy URL odpowiedzi. Patrz [Adresu URL odpowiedzi](#reply-urls) poniżej w celu znalezienia informacji na temat adresów URL oraz jak je formatować.
1. Aby **włączyć macierzystego klienta**, wybierz **nie** (wartość domyślną).
1. Wybierz opcję **Utwórz**.

### <a name="reply-urls"></a>Adresy URL odpowiedzi

Adresy URL odpowiedzi są ważne, ponieważ udostępniają one listę dozwolonych domen zwracanych, gdy witryna odwołuje się do funkcji B2C w usłudze Azure AD w celu uwierzytelnienia użytkownika. Zezwala to na powrót uwierzytelnionego użytkownika z powrotem do domeny, z której się zalogował (domena witryny). 

W polu **adres URL odpowiedzi** na ekranie **B2C Azure AD — Aplikacje \> Nowa aplikacja** należy dodać osobne wiersze dla domeny witryny i (po zainicjowaniu środowiska) wygenerowany w systemie handlowym adres URL. Te adresy URL muszą zawsze mieć prawidłowy format adresu URL i muszą być tylko podstawowymi adresami URL (nie można kończyć ukośnikami ani ścieżkami). Następnie należy dołączyć ciąg ``/_msdyn365/authresp`` do podstawowych adresów URL, tak jak w poniższych przykładach.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (domena powinna być całkowicie zgodna z domeną e-commerce. Jeśli korzystasz z wielu domen, musisz dodać ten adres URL dla każdej domeny.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Tworzenie zasad przepływów użytkownika

Przepływy użytkowników to zasady, które B2C Azure AD stosuje w celu zapewnienia bezpiecznego logowania, zapisywania się, edytowania profilu i zapomnienia hasła użytkownika. Dynamics 365 Commerce używa tych przepływów do wykonywania akcji związanych z zasadami dotyczącymi interakcji z dzierżawcą B2C Azure AD. Gdy użytkownik współpracuje z tymi zasadami, są one przekierowywane do dzierżawy B2C Azure AD w celu wykonania akcji.

W B2C Azure AD dostępne są trzy podstawowe typy przepływu użytkownika:
- Rejestracja i logowanie
- Edytowanie profilu
- Resetowanie hasła

Można wybrać Używanie domyślnego przepływu użytkownika dostarczonego przez Azure AD, który będzie wyświetlał stronę hostowaną przez B2C AAD. Alternatywnie można utworzyć stronę HTML umożliwiającą sterowanie wyglądem i działaniem tych funkcji przepływu pracy użytkownika. 

Aby dostosować strony zasad użytkowników dla systemu Dynamics 365 Commerce, należy zapoznać się z tematami [Konfigurowanie niestandardowych stron logowania użytkowników](custom-pages-user-logins.md). Aby uzyskać dodatkowe informacje, należy zapoznać się z tematem [Dostosowywanie interfejsu środowiska użytkownika w B2C Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Utwórz zasadę przepływu użytkownika rejestracji i logowania

Aby utworzyć zasady przepływu użytkownika dla rejestracji i logowania, wykonaj następujące kroki.

1. W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.
1. Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.
1. Na karcie **zalecane** wybierz opcję **Rejestracja i logowanie**.
1. W polu **Nazwa** wprowadź nazwę zasady. Ta nazwa będzie wyświetlana następnie z prefiksem przypisanym przez portal (na przykład „B2C_1_”).
1. W obszarze **dostawcy tożsamości** zaznacz odpowiednie pole wyboru.
1. W obszarze **uwierzytelnianie wieloczynnikowe** wybierz odpowiedni wybór dla firmy. 
1. W obszarze **atrybuty użytkownika i oświadczenia** wybierz opcje, aby w razie potrzeby zebrać atrybuty lub roszczenia zwrotów. W rozwiązaniu Commerce są wymagane następujące opcje domyślne:

    | **Zbierz atrybuty** | **Roszczenie zwrotu** |
    | ---------------------- | ----------------- |
    | Adres e-mail          | Adresy e-mail   |
    | Imię             | Imię        |
    |                        | Dostawca tożsamości |
    | Nazwisko                | Nazwisko           |
    |                        | Identyfikator obiektu użytkownika  |

1. Wybierz opcję **Utwórz**.

Poniższy obraz przedstawia przykład B2C Azure AD rejestracji i logowania w przepływie użytkownika.

![Ustawienia zasad rejestracji i logowania](./media/B2CImage_11.png)

Poniższy rysunek przedstawia opcję **Uruchom przepływ** użytkownika w B2C Azure AD rejestracja i logowanie w przepływie pracy użytkownika.

![Uruchom opcję przepływu użytkownika w przepływie zasad](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a>Tworzenie zasady przepływu użytkowników dla edycji profilu

Aby utworzyć zasady przepływu użytkownika dla edycji profilu, wykonaj następujące kroki.

1. W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.
1. Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.
1. Na karcie **zalecane** wybierz opcję **Edycja profilu**.
1. W polu **Nazwa** wprowadź przepływ użytkownika edycji profilu. Ta nazwa będzie wyświetlana następnie z prefiksem przypisanym przez portal (na przykład „B2C_1_”).
1. W obszarze **dostawcy tożsamości** wybierz opcję **Zaloguj się do konta lokalnego**.
1. W obszarze **Atrybuty użytkownika** zaznacz jedno z następujących pól wyboru:
    - **Adresy e-mail** (tylko **Roszczenie zwrotu**)
    - **Imię** (**Zbierz atrybuty** i **roszczenie zwrotne**)
    - **Dostawca tożsamości** (tylko **roszczenie zwrotne**)
    - **Nazwisko** (**Zbierz atrybuty** i **roszczenie zwrotne**)
    - **Identyfikator obiektu użytkownika** (tylko **roszczenie zwrotne**)
1. Wybierz opcję **Utwórz**.

Poniższy obraz przedstawia przykład przepływu użytkownika edytującego profil w B2C Azure AD.

![Tworzenie przepływu użytkowników dla edycji profilu](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Tworzenie zasady przepływu użytkowników dla resetowania hasła

Aby utworzyć zasady przepływu użytkownika dla resetowania hasła, wykonaj następujące kroki.

1. W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.
1. Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.
1. Na karcie **zalecane** wybierz opcję **Reset hasła**.
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

## <a name="add-social-identity-providers-optional"></a>Dodaj dostawców tożsamości społecznościowych (opcjonalnie)

Dostawcy tożsamości społecznościowych umożliwiają użytkownikom uwierzytelnianie przy użyciu ich kont społecznościowych. Dodawanie uwierzytelniania dostawcy tożsamości społecznościowej jest opcjonalne w programie Dynamics 365 Commerce. 

Jeśli uwierzytelnianie dostawcy tożsamości społecznościowej nie zostanie dodane, domyślne profile B2C Azure AD będą głównymi profilami bazy danych użytkownika. Użytkownicy będą mogli wybrać własną nazwę użytkownika (preferowany adres e-mail) i określić hasło. B2C Azure AD będą uwierzytelniać użytkowników bezpośrednio. 

Jeśli zostanie dodane uwierzytelnianie dostawcy tożsamości społecznej, a użytkownik wybierze jednego z oferowanych dostawców tożsamości społecznych, jednostka nadal zostanie utworzona w dzierżawie B2C Azure AD. B2C Azure AD będzie wówczas uwierzytelniać poświadczenia użytkownika za pomocą dostawcy tożsamości społecznościowej.

> [!NOTE]
> W trakcie logowania dostawca tożsamości tworzy rekord w dzierżawie B2C, ale w innym formacie niż konta lokalne, ponieważ będzie wywoływać odwołanie do zewnętrznego dostawcy tożsamości społecznościowej w celu uwierzytelnienia. Użytkownik może używać tego samego adresu e-mail dla dostawców tożsamości społecznych, co oznacza, że nazwa użytkownika poczty e-mail używana do uwierzytelniania może nie być unikatowa dla dzierżawcy. B2C Azure AD wymusza, aby użytkownicy mieli unikatowy adres e-mail tylko na lokalnych kontach B2C.

Zanim będzie można dodać dostawcę tożsamości społecznościowej do uwierzytelniania, należy przejść do portalu dostawcy tożsamości i skonfigurować aplikację dostawcy tożsamości zgodnie z instrukcją w dokumentacji B2C Azure AD. Poniżej znajduje się lista łączy do dokumentacji.

- [Amazon](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Jeden dzierżawca)](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Konto Microsoft](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Dodaj i skonfiguruj dostawcę tożsamości społecznościowej

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
1. Aby dołączyć zasadę przepływu użytkowników logowania/rejestracji, wybierz każdego dostawcę tożsamości skonfigurowanego dla swojego konta. Aby je przetestować, wybierz opcję **Uruchom przepływ użytkownika** dla każdego dostawcy tożsamości. Na nowej karcie zostanie wyświetlona strona logowania z wyświetlonym polem wyboru nowego dostawcy tożsamości.

Na poniższym obrazie pokazano przykłady **dodawania dostawcy tożsamości** i **konfigurowania ekranów dostawcy tożsamości społecznościowych** w B2C Azure AD.

![Dodawanie dostawcy tożsamości społecznościowej do aplikacji](./media/B2CImage_14.png)

Poniższy rysunek przedstawia przykład wyboru dostawców tożsamości na stronie **dostawców tożsamości** B2C Azure AD.

![Wybierz każdego dostawcę tożsamości społecznościowych, który ma być włączony dla zasady](./media/B2CImage_16.png)

Poniższy obraz przedstawia przykład domyślnego ekranu logowania z wyświetlonym przyciskiem logowania dostawcy tożsamości społecznościowej.

![Przykładowy domyślny ekran logowania z wyświetlonym przyciskiem logowania dostawcy tożsamości społecznościowej](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD

Po wykonaniu powyższej procedury B2C Azure AD, aplikacja B2C Azure AD musi być zarejestrowana w środowisku Dynamics 365 Commerce.

Aby zaktualizować centralę za pomocą nowych informacji B2C Azure AD, wykonaj następujące kroki.

1. W module Commerce przejdź do **udostępnionych parametrów modułu Commerce** i wybierz pozycję **dostawcy tożsamości** w lewym menu.
1. W obszarze **dostawcy tożsamości** wykonaj następujące czynności:
    1. W polu **wystawca** wprowadź adres URL wystawcy dostawcy tożsamości. Aby znaleźć adres URL wystawcy, przeczytaj [Uzyskaj adres URL wystawcy](#obtain-issuer-url) poniżej.
    1. W polu **nazwa** wprowadź nazwę rekordu wystawcy.
    1. W polu **typ** wprowadź **B2C Azure AD (id_token)**.
1. W obszarze **jednostki uzależnione**, z zaznaczonym powyższym elementem dostawcy tożsamości B2C, wykonaj następujące czynności:
    1. W polu **ClientID** wprowadź swój identyfikator aplikacji B2C. Tę nazwę można znaleźć w polu **identyfikator aplikacji** na stronie właściwości aplikacji B2C.
    1. W polu **typ** wprowadź wartość **publiczne**.
    1. W polu **typ użytkownika** wprowadź wartość **Odbiorca**.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W polu Wyszukiwanie w module Commerce należy wyszukać **harmonogram dystrybucji**
1. W menu nawigacji w lewym panelu na stronie **harmonogramy dystrybucji** wybierz zadanie **Konfiguracja globalna 1110**.
1. W okienku akcji wybierz opcję **Uruchom teraz**.

### <a name="obtain-issuer-url"></a>Uzyskaj adres URL wystawcy

Aby uzyskać adres URL wystawcy dostawcy tożsamości, wykonaj następujące kroki.

1. Utwórz adres URL metadanych w poniższym formacie przy użyciu dzierżawy i zasad B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Przykład: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``
1. Wprowadź adres URL metadanych na pasku adresu przeglądarki.
1. W metadanych Skopiuj adres URL wystawcy dostawcy tożsamości (wartość dla **„wystawca”**).
    - Przykład: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce

Po zakończeniu konfigurowania dzierżawy B2C Azure AD należy skonfigurować dzierżawę B2C w module kreatora witryny Commerce. Kroki konfiguracyjne obejmują zbieranie informacji o aplikacji B2C z portalu Azure, wprowadzenie do konstruktora witryn informacji o aplikacji B2C, a następnie skojarzenie aplikacji B2C z witryną i kanałem.

### <a name="collect-the-required-application-information"></a>Zbierz wymagane informacje o aplikacji

Aby zebrać wymagane informacje o aplikacji, wykonaj następujące kroki.

1. W portalu Azure przejdź do **Strony głównej \> B2C Azure AD — aplikacje**.
1. Wybierz aplikację, a następnie w lewym okienku nawigacji wybierz **właściwości**, aby uzyskać szczegółowe informacje o aplikacji.
1. W polu **identyfikator aplikacji** Zbierz identyfikator aplikacji B2C utworzonej w dzierżawie B2C. Zostanie to później wprowadzone jako **identyfikator GUID klienta** w module Konstruktor witryn.
1. W obszarze **adres URL odpowiedzi** Zbierz adres URL odpowiedzi.
1. Przejdź do **Strona główna \> B2C Azure AD — przepływy użytkownika (zasady)**, a następnie Zbierz nazwy poszczególnych zasad przepływu użytkowników.

Poniższy rysunek przedstawia przykład strony **B2C Azure AD — aplikacje**.

![Przejdź do aplikacji B2C w dzierżawie](./media/B2CImage_19.png)

Poniższy rysunek przedstawia przykład strony aplikacji **Właściwości** w B2C Azure AD. 

![Kopiuj identyfikator aplikacji z właściwości aplikacji B2C](./media/B2CImage_21.png)

Poniższy obraz przedstawia przykład zasad przepływu użytkowników na stronie **B2C Azure AD — przepływy użytkownika (zasady)**.

![Zbierz nazwy poszczególnych przepływów zasad B2C](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a>Umożliwia wprowadzenie informacji dotyczących aplikacji dzierżawczej usługi AAD B2C do modułu Commerce

Przed skojarzeniem dzierżawy B2C Azure AD z witrynami należy wprowadzić szczegóły dzierżawy B2C w module konstruktora witryn Commerce.

Aby dodać informacje dotyczące aplikacji dzierżawczej usługi B2C AAD do systemu Commerce, wykonaj następujące kroki.

1. Zaloguj się jako administrator do modułu konstruktora witryn Commerce dla swojego środowiska.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia dzierżawcy**, aby ją rozwinąć.
1. W obszarze **Ustawienia dzierżawy** wybierz pozycję **Ustawienia B2C**. 
1. W oknie głównym obok **Aplikacje B2C**wybierz opcję **Zarządzaj**. (Jeśli Twoja dzierżawa jest wyświetlana na liście aplikacji B2C, została ona już dodana przez administratora systemu. Sprawdź, czy elementy w kroku 6 są zgodne z aplikacją B2C.)
1. Wybierz **Dodaj aplikację B2C**.
1. Wprowadź w wyświetlonym formularzu następujące wymagane elementy, używając wartości ze swojej dzierżawy B2C i aplikacji. Pola, które nie są wymagane (bez gwiazdki), mogą pozostać puste.

    - **Nazwa aplikacji**: Nazwa aplikacji B2C, na przykład „Fabrikam B2C”.
    - **Nazwa dzierżawy**: nazwa dzierżawy funkcji B2C (na przykład „fabrikam”, jeśli domena jest wyświetlana jako „fabrikam.onmicrosoft.com” dla dzierżawcy B2C). 
    - **Identyfikator zasady zapominania hasła**: identyfikator zasady przepływu użytkownika zapominania hasła, na przykład „B2C_1_PasswordReset”.
    - **Identyfikator zasad logowania rejestracji**: Identyfikator zasad tworzenia konta i logowania użytkownika, na przykład „B2C_1_signup_signin”.
    - **Identyfikator GUID klienta**: Identyfikator aplikacji B2C, na przykład „22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6”.
    - **Identyfikator zasad edycji profilu**: Identyfikator zasad przepływu użytkownika edycji profilu, na przykład „B2C_1A_ProfileEdit”.

1. Kliknij przycisk **OK**. Na liście powinna być widoczna nazwa aplikacji B2C.
1. Wybierz **Zapisz**, żeby zapisać zmiany.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Skojarz aplikację B2C z witryną i kanałem

> [!WARNING]
> Jeśli witryna jest już skojarzona z aplikacją B2C, zmiana w innej aplikacji B2C spowoduje usunięcie bieżących odwołań ustanowionych dla użytkowników już zarejestrowanych w tym środowisku. W przypadku zmiany wszelkie poświadczenia skojarzone z aktualnie przypisaną aplikacją B2C nie będą dostępne dla użytkowników. 
> 
> Aplikację B2C należy aktualizować tylko wtedy, gdy jest ustawiany kanał aplikacji B2C po raz pierwszy lub jeśli użytkownik chce, aby użytkownicy mogli ponownie rejestrować się z nowymi poświadczeniami w tym kanale z nową aplikacją B2C. Należy zachować ostrożność podczas kojarzenia kanałów z aplikacjami B2C i jasno określać nazwy aplikacji. Jeśli kanał nie jest skojarzony z aplikacją B2C w poniższych krokach, użytkownicy logujący się do tego kanału witryny będą wprowadzani do aplikacji B2C, która jest wyświetlana **domyślnie** na liście aplikacji B2C **Ustawienia dzierżawcy \> Ustawienia B2C**.

Aby skojarzyć aplikację B2C z witryną i kanałem, wykonaj poniższe kroki.

1. Przejdź do swojej witryny w module konstruktora witryn Commerce.
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.
1. W obszarze **Ustawienia witryny** wybierz opcję **kanały**.
1. W oknie głównym w obszarze **kanały**wybierz kanał.
1. W okienku właściwości kanału z prawej strony wybierz nazwę aplikacji B2C z menu rozwijanego **wybierz aplikację B2C**.
1. Wybierz opcję **Zamknij**, a następnie wybierz opcję **Zapisz i opublikuj**.

## <a name="additional-b2c-information"></a>Informacje dodatkowe o B2C

### <a name="customer-migration"></a>Migracja odbiorcy

Jeśli rozważasz Migrowanie rekordów klientów z poprzedniej platformy dostawców tożsamości, skontaktuj się z zespołem Dynamics 365 Commerce, aby przejrzeć potrzeby dotyczące migracji odbiorców.

Aby uzyskać dodatkową dokumentację B2C Azure AD dotyczącą migracji klientów, należy zapoznać się z tematem [Migrowanie użytkowników do B2C Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Zasady niestandardowe

Aby uzyskać dodatkowe informacje dotyczące dostosowywania interakcji B2C Azure AD i przepływów zasad ponad to, co jest oferowane przez zasady standardowe B2C, zapoznać się z [zasadami niestandardowymi w B2C Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrator pomocniczy

W sekcji **użytkownicy** dzierżawy B2C można dodać opcjonalne pomocnicze konto administratora. Może to być konto bezpośrednie lub konto ogólne. Jeśli trzeba udostępnić konto w zasobach zespołu, można również utworzyć wspólne konto. Ze względu na wagę danych przechowywanych w B2C Azure AD, wspólne konto powinno być ściśle monitorowane zgodnie z zasadami zabezpieczeń firmy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Przekaż adresy URL przekierowań luzem](upload-bulk-redirects.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
