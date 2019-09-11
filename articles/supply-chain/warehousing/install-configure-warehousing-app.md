---
title: Omówienie instalowania i konfiguracji aplikacji magazynu
description: W tym temacie opisano sposób instalowania i konfigurowania programu Microsoft Dynamics 365 for Finance and Operations — Magazynowanie.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 742e8753aafca670b94c9f0361ef1dbbe42f0eb8
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2019
ms.locfileid: "1866120"
---
# <a name="install-and-configure-the-warehousing-app-overview"></a>Omówienie instalowania i konfiguracji aplikacji magazynu

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> W tym temacie opisano sposób konfigurowania modułu zarządzania magazynem dla wdrożeń w chmurze. Jeśli szukasz opisu sposobu konfigurowania modułu zarządzania magazynem dla wdrożeń lokalnych, zapoznaj się z tematem [Magazynowanie we wdrożeniach lokalnych](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


W tym temacie opisano sposób instalowania i konfigurowania programu Microsoft Dynamics 365 for Finance and Operations — Magazynowanie.

Finance and Operations — Magazynowanie to aplikacja dostępna w sklepach Google Play i Sklep Windows. Dla bieżącej wersji programu Finance and Operations ta aplikacja jest udostępniana jako autonomiczny składnik, co oznacza konieczność samodzielnej instalacji na urządzeniach używanych do prac magazynowych. Aby korzystać z aplikacji w swoim środowisku Finance and Operations, należy pobrać aplikację do każdego urządzenia i skonfigurować ją do łączenia się ze środowiskiem Finance and Operations. W tym temacie opisano sposób instalowania aplikacji na urządzeniach. Wyjaśniono również, jak skonfigurować aplikację, aby się łączyła ze środowiskiem Finance and Operations.

## <a name="prerequisites"></a>Wymagania wstępne
Aplikacja jest dostępna w systemach operacyjnych Windows i Android. Aby można było używać tej aplikacji, na firmowych urządzeniach musi być zainstalowany jeden z poniższych obsługiwanych systemów operacyjnych. Również trzeba mieć jedną z następujących obsługiwanych wersji programu Finance and Operations. Użyj informacji w poniższej tabeli, aby ocenić, czy Twoje środowisko sprzętowe i programowe jest gotowe do obsługi instalacji.

| Platforma                    | Wersja                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (wszystkie wersje)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, wersja 1611 <br>— lub — <br>Microsoft Dynamics AX w wersji 7.0/7.0.1 i aktualizacja 2 platformy Microsoft Dynamics AX z poprawką KB 3210014 |

## <a name="get-the-app"></a>Pobieranie aplikacji
-   Windows (UWP)
     - [Finance and Operations — Magazynowanie w Sklepie Windows](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations — Magazynowanie w sklepie Google Play](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> Galerii aplikacji Zebra została wycofana, co oznacza, że aplikacja Finance and Operations — Magazynowanie nie będzie już dostępna do pobrania z tej lokalizacji.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory
Aby umożliwić aplikacji interakcje z konkretnym serwerem programu Finance and Operations, należy zarejestrować aplikację usługi internetowej w usłudze Azure Active Directory dla dzierżawy programu Finance and Operations. Ze względów bezpieczeństwa zaleca się utworzenie aplikacji usługi internetowej dla każdego używanego urządzenia. Aby utworzyć aplikację usługi internetowej w usłudze Azure Active Directory (Azure AD), wykonaj następujące kroki:

1.  W przeglądarce sieci web przejdź do strony <https://portal.azure.com>.
2.  Wprowadź nazwę i hasło użytkownika mającego dostęp do subskrypcji usługi Azure.
3.  W portalu Azure w okienku nawigacyjnym z lewej strony kliknij przycisk **Azure Active Directory**.[](./media/WMA-01-active-directory-example.png)[![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)
4.  Upewnij się, że program Finance and Operations używa wystąpienia usługi Active Directory.
5.  Na liście kliknij opcję **Rejestracje aplikacji**. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  W górnym okienku kliknij opcję **Nowa rejestracja aplikacji**. Zostanie uruchomiony kreator **Dodawanie aplikacji**.
7.  Nadaj aplikacji nazwę, a następnie wybierz opcję **Aplikacji sieci Web/interfejs API sieci Web**. Wprowadź adres URL logowania, który jest adres URL Twojej aplikacji internetowej. Ten adres URL jest taki sam, jak adres URL wdrożenia, ale na końcu jest dodany przyrostek oauth. Kliknij **Utwórz**. [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  Zaznacz nową aplikację na liście. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Należy pamiętać wartość pola **Identyfikator aplikacji**, będzie potrzebna później. W dalszej części pole **Identyfikator aplikacji** będzie nazywane **Identyfikator klienta**.
10. W okienku **Ustawienia** kliknij opcję **Klucze**. Utwórz klucz poprzez wprowadzenie opisu klucza i czasu trwania w sekcji **Hasła**. 
11. Kliknij przycisk **Zapisz** i skopiuj klucz. Ten klucz będzie później określany jako **klucz tajny klienta**. [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Tworzenie i konfigurowanie konta użytkownika w programie Finance and Operations
Aby umożliwić programowi Finance and Operations używanie aplikacji Azure AD, należy wykonać następujące czynności konfiguracyjne:

1.  Tworzenie użytkownika programu Finance and Operations odpowiadającego poświadczeniom użytkownika aplikacji magazynowania.
    1.  W programie Finance and Operations wybierz kolejno opcje **Administrowanie systemem** &gt; **Wspólne** &gt; **Użytkownicy**.
    2.  Utwórz nowego użytkownika.
    3.  Przypisz użytkownika urządzenia przenośnego pracującego w magazynie, jak pokazano na poniższym zrzucie ekranu. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Skojarz aplikację Azure Active Directory z użytkownikiem aplikacji magazynowania.
    1.  W programie Finance and Operations wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Aplikacje usługi Azure Active Directory**
    2.  Utwórz nowy wiersz.
    3.  Wypełnij pole **Identyfikator klienta** (identyfikatorem uzyskanym w ostatniej sekcji), nadaj klientowi nazwę i wybierz uprzednio utworzonego użytkownika. Zaleca się znakowanie wszystkich urządzeń, tak aby w razie ich zgubienia można było na tej stronie łatwo usunąć im dostęp do programu Finance and Operations. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurowanie aplikacji
Aplikację w urządzeniu należy skonfigurować do łączenia się z serwerem programu Finance and Operations za pośrednictwem aplikacji Azure AD. W tym celu:

1.  W aplikacji przejdź do okna **Ustawienia połączenia**.
2.  Wyczyść pole **Tryb demonstracyjny**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Podaj poniższe informacje: 
    + **Identyfikator klienta usługi katalogu Azure Active** — identyfikator klienta uzyskuje się w kroku 9 procedury „Tworzenie aplikacji usługi internetowej w usłudze Active Directory”. 
    + **Klucz tajny klienta katalogu usługi Azure Active** — klucz tajny klienta uzyskuje się w kroku 11 procedury „Tworzenie aplikacji usługi internetowej w usłudze Active Directory”. 
    + **Zasób usługi Azure Active Directory** — zasób katalogowy usługi Azure AD opisuje adres URL głównego katalogu programu Finance and Operations. **Uwaga:**: Na końcu pola nie należy umieszczać znaku kreski ułamkowej (/). 
    + **Dzierżawca katalogu usługi Azure Active** — Dzierżawa katalogu usługi Azure AD używana na serwerze programu Finance and Operations: `https://login.windows.net/your-AD-tenant-ID`. Na przykład: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Uwaga:**: Na końcu pola nie należy umieszczać znaku kreski ułamkowej (/). 
    + **Firma** — wpisz firmę zdefiniowaną w programie Finance and Operations, z którą ma się łączyć aplikacja. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Kliknij przycisk **Wstecz** w lewym górnym rogu aplikacji. Aplikacja połączy się teraz z serwerem programu Finance and Operations i zostanie wyświetlony ekran logowania dla pracownika magazynu. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Aby dowiedzieć się więcej o tym, jak w programie Dynamics 365 for Finance and Operations — Magazynowanie skonfigurować skanowanie kodów kreskowych przy użyciu aparatu urządzenia komórkowego, zobacz [Skanowanie kodów kreskowych za pomocą aparatu w programie Dynamics 365 for Finance and Operations — Magazynowanie](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Usuwanie dostępu urządzenia
Jeśli urządzenie zostanie zgubione lub dostanie się w niepowołane ręce, należy usunąć temu urządzeniu dostęp do programu Finance and Operations. Następujące kroki opisują zalecany proces usuwania dostępu.

1.  W programie Finance and Operations wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Aplikacje usługi Azure Active Directory**
2.  Usuń wiersz odpowiadający urządzeniu, któremu chcesz cofnąć dostęp. Należy zapamiętać wartość pola **Identyfikator klienta** używany dla usuniętego urządzenia. Będzie ona potrzebna później.
3.  Zaloguj się do portalu Azure pod adresem <https://portal.azure.com>.
4.  W lewym menu kliknij ikonę **Active Directory** i upewnij się, że jesteś w poprawnym katalogu.
5.  Na liście kliknij opcję **Rejestracje aplikacji**, a następnie kliknij aplikację, którą chcesz skonfigurować. Zostanie wyświetlona strona **Ustawienia** z informacjami o konfiguracji.
6.  Upewnij się, że wartość **Identyfikator klienta** dla aplikacji jest taka sama, jak w kroku 2 w tej sekcji.
7.  W górnym okienku kliknij przycisk **Usuń**.
8.  W komunikacie potwierdzenia kliknij przycisk **Tak**.
