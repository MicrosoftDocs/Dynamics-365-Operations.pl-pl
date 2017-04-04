---
title: "Instalowanie i konfigurowanie usługi Microsoft Dynamics 365 dla operacji & #8211; Magazynowanie"
description: "W tym temacie opisano sposób zainstalować i skonfigurować usługi Microsoft Dynamics 365 dla operacji - składu."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Instalowanie i konfigurowanie usługi Microsoft Dynamics 365 dla operacji & #8211; Magazynowanie

W tym temacie opisano sposób zainstalować i skonfigurować usługi Microsoft Dynamics 365 dla operacji - składu.

Dynamics 365 dla operacji - składu jest to aplikacja udostępniana na sklep Play i magazynu systemu Windows. Dla bieżącej wersji programu Microsoft Dynamics 365 dla operacji ta aplikacja jest dostępna jako składnika autonomicznego, co oznacza własny wdrażania na urządzenia używane do zadań hurtowni. W celu korzystania z aplikacji w Twoim 365 Dynamics dla środowiska operacji, należy pobrać aplikację na każdym urządzeniu i skonfigurować go do łączenia się z 365 Dynamics dla środowiska operacji. W tym temacie opisano sposób instalowania aplikacji na urządzeniach. Wyjaśniono również, jak skonfigurować program, aby połączyć się z 365 Dynamics dla środowiska operacji.

## <a name="prerequisites"></a>Wymagania wstępne
Aplikacja jest dostępna w systemach operacyjnych Windows i Android. Aby używać tej aplikacji, musi mieć jedną z następujących obsługiwanych systemów operacyjnych zainstalowanych na swoich urządzeniach. Również musi mieć jedną z następujących obsługiwanych wersji systemu Dynamics 365 dla operacji. Umożliwia informacje w poniższej tabeli należy ocenić, czy sprzęt i oprogramowanie środowiska jest gotowy do obsługi instalacji.

| Platforma                    | Wersja                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (wszystkie wersje)                                                                                                                                                   |
| Dynamics 365 dla operacji | Platforma systemu Microsoft Dynamics AX i Microsoft Dynamics 365 dla operacji 1611 - czy - systemu Dynamics AX wersja 7.0/7.0.1 aktualizacji 2 z poprawką KB 3210014 |

## <a name="get-the-app"></a>Pobierz aplikację
-   Windows (UWP) - [Dynamics 365 dla operacji - składu w Sklepie Windows](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android - [Dynamics 365 dla operacji - składu na sklep Play](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

## <a name="create-a-web-service-application-in-active-directory"></a>Tworzenie aplikacji usługi sieci web w usłudze Active Directory
Aby włączyć aplikację do interakcji z konkretnego 365 Dynamics Server operacji, należy zarejestrować aplikacji usługi sieci web w Azure Active Directory dla usługi Dynamics 365 dla operacji dzierżawy. Ze względów bezpieczeństwa zaleca się tworzenia aplikacji usługi sieci web dla każdego urządzenia, którego używasz. Aby utworzyć aplikacji usługi sieci web w usłudze Active Directory Azure (Azure AD), wykonaj następujące kroki:

1.  W przeglądarce sieci web przejdź do <https://manage.windowsazure.com>.
2.  Wprowadź nazwę i hasło dla użytkownika, który ma dostęp do subskrypcji Azure.
3.  W portalu Azure w okienku nawigacyjnym z lewej strony, kliknij przycisk **usługi Active Directory**. [](./media/wh-01-active-directory-example.png)[![wh-01-active katalog przykład](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  W siatce zaznacz wystąpienie usługi Active Directory, który jest używany przez Dynamics 365 dla operacji.
5.  Na górnym pasku narzędzi, kliknij przycisk **aplikacji**. [![Wh-02-active katalog aplikacji](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  W dolnym okienku kliknij **Dodaj**. **Dodać aplikację** zostanie uruchomiony Kreator.
7.  Wprowadź nazwę aplikacji, a następnie wybierz **aplikacji sieci Web i/lub sieci web API**. [![Wh-03-Active-Directory-Add-Application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Wprowadź znak na adres URL, który jest adresem URL aplikacji w dzierżawie główny URL operacji. Adres URL logowania jest obecnie nie jest aktywnie używany w uwierzytelnianiu aplikacji, ale jest polem wymaganym. Wprowadź ten sam adres URL w polu aplikacji Identyfikatora URI. [![Wh-04-ad Dodaj właściwości](./media/wh-04-ad-add-properties.png)](./media/wh-04-ad-add-properties.png)
9.  Przejdź do **Konfigurowanie** kartę. [![Wh-05-ad skonfigurować app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Przewiń w dół, aż zobaczysz **uprawnienia do innych aplikacji** sekcji. Kliknij **dodać aplikację**. [![Wh-06-AD-App-Add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Wybierz **systemu Microsoft Dynamics ERP** na liście. Kliknij **ukończyć sprawdzania** przycisk w prawym rogu strony. [![Wh-07-ad wybierz uprawnienia](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. W **delegowanie uprawnień** listy, zaznacz wszystkie pola wyboru. Click **Save**. [![Wh-08-ad--uprawnienia pełnomocnika](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Zanotuj następujące informacje:
    -   **Identyfikator klienta** - podczas przewijania w górę strony, zobaczysz **identyfikator klienta** wyświetlane.
    -   **Klucz** - **klucze** sekcji, Utwórz klucz przez czas trwania i skopiować klucz. Ten klucz będzie później określane jako **klucz tajny klienta**.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Utworzyć i skonfigurować konto użytkownika w usłudze Dynamics 365 dla operacji
Aby włączyć 365 Dynamics dla operacji do użycia w aplikacji Azure AD, należy wykonać następujące czynności konfiguracyjne:

1.  Utwórz nowe konto użytkownika w usłudze Active Directory Azure dla usługi Dynamics 365 dla operacji dzierżawy. Celem tego konta użytkownika jest dostęp do określonej usługi niestandardowych aplikacji składu celnego, który udostępnia usługi Dynamics 365 dla operacji serwera. Po wykonaniu tej czynności, będziesz mieć poświadczenia użytkownika WMDP, które składają się z WMDP adresu e-mail i hasła WMDP. Aby dowiedzieć się o podstawowe kroki umożliwiające dodawanie użytkowników do usługi Azure AD i 365 Dynamics dla operacji, odnoszą się do tego samouczka: [zarejestrować się do usługi Microsoft Dynamics 365 subskrypcji operacji](/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Utwórz 365 Dynamics dla użytkownika operacji, który odpowiada składu poświadczeń użytkownika aplikacji.
    1.  W usłudze Dynamics 365 dla operacji, przejdź do **Administracja systemu**&gt;**wspólne**&gt;**użytkowników**.
    2.  Utwórz nowego użytkownika.
    3.  Przypisz magazynu użytkownika urządzenia przenośnego, jak pokazano na poniższym zrzucie ekranu. [![Wh-09-Add-User-Security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Kojarzenie aplikacji usługi Active Directory Azure ze składu celnego użytkownika aplikacji.
    1.  W usłudze Dynamics 365 dla operacji, przejdź do **Administracja systemu**&gt;**instalacji**&gt;**aplikacje usługi Active Directory Azure**.
    2.  Utwórz nowy wiersz.
    3.  Wprowadź **identyfikator klienta** (uzyskana w ostatniej sekcji), nadaj mu nazwę, a następnie wybierz uprzednio utworzony użytkownik. Zaleca się znakowanie wszystkich urządzeń, tak, że można łatwo usunąć ich dostęp do 365 Dynamics dla operacji na tej stronie w przypadku, gdy są one utracone. [![Wh-10-ad aplikacje formularz](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurowanie aplikacji
Należy skonfigurować aplikację na podłączenie urządzenia do 365 Dynamics dla operacji serwera za pośrednictwem aplikacji Azure AD. Aby to zrobić, wykonaj następujące kroki.

1.  W aplikacji, przejdź do **ustawienia połączenia**.
2.  Wyczyść **tryb demonstracyjny** pole. [![Wh-11-App-Connection-Settings-Demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Wprowadź następujące informacje:- **identyfikator klienta Azure Active directory** -klient uzyskuje identyfikator w kroku 13 w "Tworzenie aplikacji usługi sieci web w usłudze Active Directory". - **Klucz tajny klienta azure Active directory** -klucz tajny klienta jest uzyskane w kroku 13 w "Tworzenie aplikacji usługi sieci web w usłudze Active Directory". - **Azure Active directory zasobów** -zasobu katalogu Azure AD zebrano Dynamics 365 dla operacji głównego adresu URL. **Uwaga:**: nie należy kończyć tego pola znaku kreski ułamkowej (/). - **Dzierżawy azure Active directory** -dzierżawy katalogu Azure AD używany z Dynamics 365 dla operacji serwera: https://login.windows.net/&lt;your-AD-dzierżawcy ID&gt;. Na przykład: https://login.windows.net/contosooperations.onmicrosoft.com. 
**Uwaga:**: nie należy kończyć tego pola znaku kreski ułamkowej (/). - **Firmy** -wprowadzić podmiot prawny w usłudze Dynamics 365 dla operacji, do których ma aplikacji łączyć. [![Wh-12-app połączenia ustawienia](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Wybierz **ponownie** przycisk w lewym górnym rogu aplikacji. Aplikacja połączy się teraz z Twoim 365 Dynamics dla operacji serwera i zostanie wyświetlony ekran logowania dla pracownika magazynu. [![Wh-13-ekran logowania](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Usuwanie dostępu dla urządzenia
W przypadku urządzenie utracone lub złamany należy usunąć dostęp do Dynamics 365 dla działań dla urządzenia. Następujące kroki opisują zalecany proces, aby usunąć dostęp.

1.  W usłudze Dynamics 365 dla operacji, przejdź do **Administracja systemu**&gt;**instalacji**&gt;**aplikacje usługi Active Directory Azure**.
2.  Usuń wiersz, który odpowiada urządzenie, do którego chcesz usunąć dostęp. Należy zanotować **identyfikator klienta** używane urządzenia usunięte.
3.  Zaloguj się w wersji zapoznawczej o <https://manage.windowsazure.com>.
4.  Kliknij **usługi Active Directory** ikonę na menu po lewej stronie, a następnie kliknij żądany katalog.
5.  W górnym menu, kliknij przycisk **aplikacje**, a następnie kliknij przycisk aplikacji, którą chcesz skonfigurować. **Szybki Start** zostanie wyświetlona strona z rejestracji jednokrotnej i inne informacje o konfiguracji.
6.  Kliknij **Konfigurowanie** tab, przewiń w dół i zapewnienia, że **identyfikator klienta** aplikacji jest taki sam, jak w kroku 2 w tej sekcji.
7.  Kliknij **usunąć** przycisk paska poleceń.
8.  Kliknij **tak** w komunikacie potwierdzającym.



