---
title: Instalowanie i konfigurowanie programu Microsoft Dynamics 365 for Finance and Operations &#8211; Magazynowanie
description: "W tym temacie opisano sposób instalowania i konfigurowania programu Microsoft Dynamics 365 for Finance and Operations — Magazynowanie."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 31e77b27d4bf95c997817b3a053b33119562adf8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>Instalowanie i konfigurowanie programu Microsoft Dynamics 365 for Finance and Operations &#8211; Magazynowanie

[!include[banner](../includes/banner.md)]


W tym temacie opisano sposób instalowania i konfigurowania programu Microsoft Dynamics 365 for Finance and Operations — Magazynowanie.

Finance and Operations — Magazynowanie to aplikacja dostępna w sklepach Google Play i Sklep Windows. Dla bieżącej wersji programu Finance and Operations ta aplikacja jest udostępniana jako autonomiczny składnik, co oznacza konieczność samodzielnej instalacji na urządzeniach używanych do prac magazynowych. Aby korzystać z aplikacji w swoim środowisku Finance and Operations, należy pobrać aplikację do każdego urządzenia i skonfigurować ją do łączenia się ze środowiskiem Finance and Operations. W tym temacie opisano sposób instalowania aplikacji na urządzeniach. Wyjaśniono również, jak skonfigurować aplikację, aby się łączyła ze środowiskiem Finance and Operations.

## <a name="prerequisites"></a>Wymagania wstępne
Aplikacja jest dostępna w systemach operacyjnych Windows i Android. Aby można było używać tej aplikacji, na firmowych urządzeniach musi być zainstalowany jeden z poniższych obsługiwanych systemów operacyjnych. Również trzeba mieć jedną z następujących obsługiwanych wersji programu Finance and Operations. Użyj informacji w poniższej tabeli, aby ocenić, czy Twoje środowisko sprzętowe i programowe jest gotowe do obsługi instalacji.

| Platforma                    | Wersja                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (wszystkie wersje)                                                                                                                                                   |
| Finance and Operations | Microsoft Finance and Operations wersja 1611 <br>-lub- <br>Microsoft Dynamics Dynamics AX wersja 7.0/7.0.1 i aktualizacja nr 2 platformy Microsoft Dynamics AX z poprawką KB 3210014 |

## <a name="get-the-app"></a>Pobieranie aplikacji
-   Windows (UWP): [Finance and Operations — Magazynowanie w Sklepie Windows](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android:
    - [Finance and Operations — Magazynowanie w sklepie Google Play](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - [Finance and Operations — Magazynowanie w galerii aplikacji Zebra](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-active-directory"></a>Tworzenie aplikacji usługi internetowej w usłudze Active Directory
Aby umożliwić aplikacji interakcje z konkretnym serwerem programu Finance and Operations, należy zarejestrować aplikację usługi internetowej w usłudze Azure Active Directory dla dzierżawy programu Finance and Operations. Ze względów bezpieczeństwa zaleca się utworzenie aplikacji usługi internetowej dla każdego używanego urządzenia. Aby utworzyć aplikację usługi internetowej w usłudze Active Directory Azure (Azure AD), wykonaj następujące kroki:

1.  W przeglądarce internetowej przejdź do strony <https://manage.windowsazure.com>.
2.  Wprowadź nazwę i hasło użytkownika mającego dostęp do subskrypcji usługi Azure.
3.  W portalu Azure w okienku nawigacyjnym z lewej strony kliknij przycisk **Active Directory**.[](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-example](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  W siatce zaznacz wystąpienie usługi Active Directory, które jest używane przez usługę Finance and Operations.
5.  Na górnym pasku narzędzi kliknij przycisk **Aplikacje**. [![wh-02-active-directory-applications](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  W dolnym okienku kliknij przycisk **Dodaj**. Zostanie uruchomiony kreator **Dodawanie aplikacji**.
7.  Nadaj aplikacji nazwę, a następnie wybierz opcję **Aplikacji sieci Web i/lub interfejs API sieci Web**. [![wh-03-active-directory-add-application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Wprowadź adres URL logowania, który jest adres URL Twojej aplikacji internetowej. Ten adres URL jest taki sam, jak adres URL wdrożenia, ale na końcu jest dodany przyrostek oauth. Wprowadź identyfikator URI aplikacji. Ta wartość jest wymagana, ale nie jest potrzeba do uwierzytelniania. Upewnij się, że ten identyfikator URI aplikacji nie jest symulowanym identyfikatorem URI takim jak https://contosooperations/wmapp, ponieważ użycie adresu URL wdrożenia może spowodować problemy z logowaniem w innych aplikacjach usługi AAD, takich jak dodatek programu Excel. [![WH-04-AD-add-properties3](./media/WH-04-AD-add-properties3.png)](./media/WH-04-AD-add-properties3.png)
9.  Przejdź do karty **Konfiguruj**. [![wh-05-ad-configure-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Przewiń w dół, aż zobaczysz sekcję **Uprawnienia do innych aplikacji**. Kliknij przycisk **Dodaj aplikację**. [![wh-06-ad-app-add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Na liście zaznacz pozycję **Microsoft Dynamics ERP**. W prawym górnym rogu strony kliknij przycisk **Sprawdź kompletność**. [![wh-07-ad-select-permissions](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. Na liście **Uprawnienia pełnomocnika** zaznacz wszystkie pola wyboru. Kliknij przycisk **Zapisz**. [![wh-08-ad-delegate-permissions](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Zanotuj następujące informacje:
    -   **Identyfikator klienta** — Podczas przewijania w górę strony zobaczysz pole **Identyfikator klienta**.
    -   **Klucz** — W sekcji **Klucze** utwórz klucz poprzez wybranie czasu trwania, a następnie skopiuj ten klucz. Ten klucz będzie później określany jako **klucz tajny klienta**.

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Tworzenie i konfigurowanie konta użytkownika w programie Finance and Operations
Aby umożliwić programowi Finance and Operations używanie aplikacji Azure AD, należy wykonać następujące czynności konfiguracyjne:

1.  Tworzenie nowego konta użytkownika w usłudze Active Directory Azure dla dzierżawy usługi Finance and Operations. Celem tego konta użytkownika jest uzyskanie dostępu do określonej niestandardowej usługi w aplikacji magazynowania, którą udostępnia serwer programu Finance and Operations. Po wykonaniu tej czynności będziesz mieć poświadczenia użytkownika WMDP, które składają się z adresu e-mail WMDP i hasła WMDP. Aby dowiedzieć się więcej o podstawowych czynnościach dodawania użytkowników do usług Azure AD i Finance and Operations, skorzystaj z tego samouczka: [Subskrybowanie usługi Finance and Operations](../../dev-itpro/dev-tools/sign-up-preview-subscription.md).
2.  Tworzenie użytkownika programu Finance and Operations odpowiadającego poświadczeniom użytkownika aplikacji magazynowania.
    1.  W programie Finance and Operations wybierz kolejno opcje **Administrowanie systemem** &gt; **Wspólne** &gt; **Użytkownicy**.
    2.  Utwórz nowego użytkownika.
    3.  Przypisz użytkownika urządzenia przenośnego pracującego w magazynie, jak pokazano na poniższym zrzucie ekranu. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Skojarz aplikację Active Directory Azure z użytkownikiem aplikacji magazynowania.
    1.  W programie Finance and Operations wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Aplikacje usługi Azure Active Directory**.
    2.  Utwórz nowy wiersz.
    3.  Wypełnij pole **Identyfikator klienta** (identyfikatorem uzyskanym w ostatniej sekcji), nadaj klientowi nazwę i wybierz uprzednio utworzonego użytkownika. Zaleca się znakowanie wszystkich urządzeń, tak aby w razie ich zgubienia można było na tej stronie łatwo usunąć im dostęp do programu Finance and Operations. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurowanie aplikacji
Aplikację w urządzeniu należy skonfigurować do łączenia się z serwerem programu Finance and Operations za pośrednictwem aplikacji Azure AD. W tym celu:

1.  W aplikacji przejdź do okna **Ustawienia połączenia**.
2.  Wyczyść pole **Tryb demonstracyjny**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Podaj poniższe informacje: 
    + **Identyfikator klienta usługi Azure Active Directory** — identyfikator klienta uzyskuje się w kroku 13 procedury „Tworzenie aplikacji usługi internetowej w usłudze Active Directory”. 
    + **Klucz tajny klienta usługi Azure Active Directory** — klucz tajny klienta uzyskuje się w kroku 13 procedury „Tworzenie aplikacji usługi internetowej w usłudze Active Directory”. 
    + **Zasób usługi Azure Active Directory** — zasób katalogowy usługi Azure AD opisuje adres URL głównego katalogu programu Finance and Operations. **Uwaga:**: Na końcu pola nie należy umieszczać znaku kreski ułamkowej (/). 
    + **Dzierżawca usługi Azure Active Directory** — Dzierżawa katalogu usługi Azure AD używana na serwerze programu Finance and Operations: https://login.windows.net/identyfikator-Twojej-dzierżawy-w-usłudze-AD. Na przykład: https://login.windows.net/contosooperations.onmicrosoft.com.
    <br>**Uwaga:**: Na końcu pola nie należy umieszczać znaku kreski ułamkowej (/). 
    + **Firma** — wpisz firmę zdefiniowaną w programie Finance and Operations, z którą ma się łączyć aplikacja. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Kliknij przycisk **Wstecz** w lewym górnym rogu aplikacji. Aplikacja połączy się teraz z serwerem programu Finance and Operations i zostanie wyświetlony ekran logowania dla pracownika magazynu. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Usuwanie dostępu urządzenia
Jeśli urządzenie zostanie zgubione lub dostanie się w niepowołane ręce, należy usunąć temu urządzeniu dostęp do programu Finance and Operations. Następujące kroki opisują zalecany proces usuwania dostępu.

1.  W programie Finance and Operations wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Aplikacje usługi Azure Active Directory**.
2.  Usuń wiersz odpowiadający urządzeniu, któremu chcesz cofnąć dostęp. Zanotuj wartość atrybutu **Identyfikator klienta** używany przez usuwane urządzenie.
3.  Zaloguj się w klasycznym portalu Azure pod adresem <https://manage.windowsazure.com>.
4.  Kliknij ikonę **Active Directory** w menu po lewej stronie, a następnie kliknij żądany katalog.
5.  W górnym menu kliknij przycisk **Aplikacje**, a następnie kliknij aplikację, którą chcesz skonfigurować. Zostanie wyświetlona strona **Szybki start** z funkcją rejestracji jednokrotnej i innymi informacjami konfiguracyjnymi.
6.  Kliknij kartę **Konfigurowanie**, przewiń w dół i upewnij się, że wartość **Identyfikator klienta** aplikacji jest taka sama, jak w kroku 2 w tej sekcji.
7.  Na pasku poleceń kliknij przycisk **Usuń**.
8.  W komunikacie potwierdzenia kliknij przycisk **Tak**.




