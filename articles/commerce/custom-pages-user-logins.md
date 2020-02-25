---
title: Ustaw strony niestandardowe dla danych logowania użytkowników
description: W tym temacie opisano, jak budować niestandardowe strony w Microsoft Dynamics 365 Commerce, które obsługują niestandardowe logowanie dla użytkowników dzierżawców Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C).
author: brianshook
manager: annbe
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fe2a716d370c350c0c7e034835ff755f1ec9c6a1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001953"
---
# <a name="set-up-custom-pages-for-user-logins"></a>Konfigurowanie stron niestandardowych do logowań użytkowników


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak budować niestandardowe strony w Microsoft Dynamics 365 Commerce, które obsługują niestandardowe logowanie dla użytkowników dzierżawców Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C).

## <a name="overview"></a>Omówienie

Aby skorzystać ze stron niestandardowych, które są tworzone Dynamics 365 Commerce w celu obsługi przepływów logowania użytkowników, należy skonfigurować zasady Azure AD, które będą przywoływane w środowisku Commerce Environment. Można skonfigurować zasady B2C Azure AD „Rejestracja i logowanie”, „Edytowanie profili” i „Resetowanie hasła” za pomocą aplikacji B2C Azure AD. Do nazw dzierżawy i zasad B2C Azure AD można następnie odwoływać się podczas procesu udostępniania, który jest wykonywany dla środowiska Commerce przy użyciu usług Microsoft Dynamics Lifecycle Services (LCS).

Niestandardowe strony Commerce mogą być tworzone przy użyciu modułu logowanie, rejestracja, edycja profilu konta lub resetowanie hasła. W konfiguracjach zasad B2C Azure AD w portalu Azure Portal należy odwoływać się do stron adresów URL opublikowanych dla stron niestandardowych.

## <a name="set-up-b2c-policies"></a>Ustawianie zasad B2C

Po skonfigurowaniu dzierżawy B2C Azure AD i kojarzeniu jej ze środowiskiem Commerce, przejdź na stronę **Azure AD B2C** w portalu Azure, a następnie w menu w obszarze **Zasady** wybierz pozycję **Przepływy użytkowników (zasady)**.

![Polecenie przepływy użytkowników (zasady) w menu](./media/B2C_CustomPage_PoliciesMenu.png)

Teraz można skonfigurować przepływy logowania użytkownika „Rejestracja i logowanie”, „Edytowanie profili” i „Resetowanie hasła”.

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Skonfiguruj zasadę „Rejestracja i logowanie”

Aby skonfigurować zasadę „Rejestracja i logowanie”, wykonaj następujące kroki.

1. Wybierz opcję **Nowy przepływ użytkownika**, a następnie na karcie **Rekomendowany** wybierz zasadę **Rejestracja i logowanie**.
1. Wprowadź nazwę zasady (na przykład **B2C\_1\_RejestracjaiLogowanie**).
1. W sekcji **Dostawcy tożsamości** wybierz dostawców tożsamości, którzy mają być używani dla zasady. Należy wybrać co najmniej opcję **Rejestracja e-mail**.
1. W kolumnie **Zbieranie atrybutów** zaznacz pola wyboru **Adres e-mail**, **Imię** i **Nazwisko**.
1. W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Dostawca tożsamości**, **Nazwisko** i **Identyfikator obiektu użytkownika**.

    ![Wybrane atrybuty i roszczenia](./media/B2C_SignInSignUp_Attributes.png)

1. Wybierz przycisk **OK**, aby utworzyć zasadę.
1. Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**
1. Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.

    ![Strona właściwości nowej zasady](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Nazwa zasad będzie w pełni wywoływana w środowisku Commerce. (Prefiks **B2C\_1\_** zostanie uwzględniony w odwołaniu.) Nie można zmieniać nazw zasad po ich utworzeniu. W przypadku wymiany istniejących zasad środowiska Commerce można usunąć zasady oryginalne i utworzyć nowe zasady o takiej samej nazwie. Ewentualnie, jeśli zainicjowano już obsługę środowiska, można przesłać nową nazwę zasady za pośrednictwem żądania usługi.

Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych. Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.

### <a name="configure-the-profile-editing-policy"></a>Skonfiguruj zasadę „edycji profilu”

Aby skonfigurować zasadę „edycji profilu”, wykonaj poniższe czynności.

1. Wybierz opcję **Nowy przepływ użytkownika**, a następnie na karcie **Rekomendowany** wybierz zasadę **Edycja profilu**.
1. Wprowadź nazwę zasady (na przykład **B2C\_1\_EditProfile**).
1. W sekcji **Dostawcy tożsamości** wybierz dostawców tożsamości, którzy mają być używani dla zasady. Należy wybrać co najmniej opcję **logowania lokalnego konta**.
1. W kolumnie **Zbieranie atrybutów** zaznacz pola wyboru **Adres e-mail** i **Nazwisko**.
1. W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Dostawca tożsamości**, **Nazwisko** i **Identyfikator obiektu użytkownika**.
1. Wybierz przycisk **OK**, aby utworzyć zasadę.
1. Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**
1. Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.

Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych. Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.

### <a name="configure-the-password-reset-policy"></a>Skonfiguruj zasadę „resetowania hasła”

Aby skonfigurować zasadę „resetowania hasła”, wykonaj poniższe czynności.

1. Wybierz opcję **Nowy przepływ użytkownika**, a następnie na karcie **Podgląd** wybierz zasadę **Resetowanie hasła v1:1**.

    ![Zasada resetowania hasła v1.1 wybrana na karcie Podgląd](./media/B2C_ForgetPassword_Menu.png)

1. Wprowadź nazwę zasady (na przykład **B2C\_1\_ForgetPassword**).
1. W sekcji **dostawcy tożsamości** wybierz opcję **Resetuj hasło, używając adresu e-mail**.
1. W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Nazwisko** i **Identyfikator obiektu użytkownika**.

    ![Wybrane roszczenia](./media/B2C_ForgetPassword_Attributes.png)

1. Wybierz przycisk **OK**, aby utworzyć zasadę.
1. Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**
1. Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.

Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych. Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.

## <a name="build-the-custom-pages"></a>Tworzenie niestandardowych stron

Aby utworzyć niestandardowe strony do obsługi podpisów użytkowników, wykonaj następujące kroki.

1. W narzedziu autorskim Commerce przejdź do swojej witryny.
1. Utwórz następujące pięć szablonów i pięć stron:

    - Szablon **Zaloguj się** i strona korzystająca z modułu logowania.
    - Szablon **Zarejestruj się** i strona korzystająca z modułu rejestracji.
    - Szablon **resetowania hasła** i strona, która korzysta z modułu resetowania hasła.
    - Szablon **Potwierdzenie resetowania hasła** i strona, która korzysta z modułu potwierdzenia resetowania hasła.
    - Szablon **Edytuj profil** i stronę, która używa modułu Edytuj profil konta

Podczas tworzenia stron postępuj zgodnie z następującymi wskazówkami:

- Dla każdej strony lub modułu należy zastosować układ i styl najlepiej odpowiadające wymaganiom biznesowym.
- Publikuj wszystkie strony i adresy URL, które muszą być używane w ustawieniach Azure AD B2C.
- Po opublikowaniu stron i adresów URL należy zebrać adresy URL, które muszą być używane w konfiguracjach zasad Azure AD B2C. A **?preloadscripts=true** sufiks zostanie dodany do każdego z adresów URL, gdy jest używany.

> [!IMPORTANT]
> Nie należy ponownie używać uniwersalnych nagłówków i stopek mających łącza względne. Ponieważ te strony będą przechowywane w domenie Azure AD B2C, gdy są używane, dla wszystkich łączy będą używane tylko bezwzględne adresy URL

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Skonfiguruj zasady Azure AD B2C za pomocą niestandardowych informacji o stronie 

W portalu Azure Wróć do strony **Azure AD B2C**, a następnie w menu w obszarze **zasady** wybierz pozycję **przepływy użytkowników (zasady)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Aktualizuj zasadę „Rejestracja i logowanie w” przy użyciu niestandardowych informacji o stronie

Aktualizuj zasadę „Rejestracja i logowanie w” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.

1. W obszarze zasady **Zaloguj się i zarejestruj**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.
1. Wybierz układ **Unifikuj rejestrację i logowanie na stronie**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.
1. Wybierz układ **Strona rejestracji lokalnego konta**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL logowania. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.
1. W sekcji **atrybuty użytkownika** wykonaj następujące kroki:

    1. W przypadku **adresu e-mail**, **imienia** i **nazwiska** należy wybrać opcję **nie** w polu **wymagane weryfikacje**.
    1. W przypadku adresu **imienia** i **nazwiska** należy wybrać opcję **nie** w polu **opcjonalne**.

    ![Konfiguracja zasad rejestracji na koncie lokalnym](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Aktualizuj zasadę „Edycja profilu” przy użyciu niestandardowych informacji o stronie

Aktualizuj zasadę „Edycja profilu” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.

1. W obszarze zasady **Edycja profilu**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.
1. Wybierz układ **strony edytowania profilu**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL edytowania profilu. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.
1. W sekcji **atrybuty użytkownika** wykonaj następujące kroki:

    1. W przypadku **adresu e-mail** i **imienia**  należy wybrać opcję **nie** w polu **wymagane weryfikacje**.
    1. W przypadku adresu **imienia** i **nazwiska** należy wybrać opcję **nie** w polu **opcjonalne**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Aktualizuj zasadę „Resetowanie hasła” przy użyciu niestandardowych informacji o stronie

Aktualizuj zasadę „Resetowanie hasła” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.

1. W obszarze zasady **resetowanie hasła**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.
1. Wybierz układ **strona nowego hasła**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL resetowania hasła. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.
1. Wybierz układ **strony weryfikacji konta**.
1. Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.
1. W polu **Identyfikator URI strony niestandardowej** wprowadź pełny adres URL weryfikacji resetowania hasła. Dołącz sufiks **?preloadscripts=true**. Na przykład wpisz ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Dostosowywanie domyślnych ciągów tekstowych dla etykiet i opisów

W przypadku zestawu początkowy zestaw moduły logowania są wstępnie wypełniane domyślnymi ciągami tekstowymi dla etykiet i opisów. Można dostosować te ciągi w zestawie SDK (Software Development Kit), aktualizując wartości w pliku Global. JSON systemu logowania w module.

Na przykład domyślny tekst dla łącza zapomnianego hasła jest **Zapomniałeś hasła?**. Poniżej przedstawiono domyślny tekst na stronie rejestracji.

![Domyślny tekst łącza zapomnianego hasła na stronie rejestracji](./media/B2C_SignUp_ModuleFace.png)

Jednak w pliku global.json dla początkowego zestawu dzienników w module można edytować tekst, aby **Zapomniałeś hasła?**, jak pokazano na poniższej ilustracji.

![Zaktualizowany tekst łącza w pliku global.json modułu rejestrowania](./media/B2C_CustomizingStringsForModule.png)

Po zaktualizowaniu pliku global.json i opublikowaniu zmian tekst nowego łącza jest wyświetlany w module logowanie zarówno w Commerce, jak i na stronie rejestracji online.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
