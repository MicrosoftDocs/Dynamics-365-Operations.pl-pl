---
title: Omówienie instalowania i konfiguracji aplikacji Magazynowanie
description: W tym temacie opisano sposób instalowania i konfigurowania aplikacji Dynamics 365 for Finance and Operations — Magazynowanie.
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
ms.openlocfilehash: df0bc9ff2405cc2f370ea777a70e005a1ff338a0
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814957"
---
# <a name="install-and-configure-the-warehousing-app-overview"></a>Omówienie instalowania i konfiguracji aplikacji Magazynowanie

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> W tym temacie opisano sposób konfigurowania modułu zarządzania magazynem dla wdrożeń w chmurze. Jeśli szukasz opisu sposobu konfigurowania modułu zarządzania magazynem dla wdrożeń lokalnych, zapoznaj się z tematem [Magazynowanie we wdrożeniach lokalnych](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


W tym temacie opisano sposób instalowania i konfigurowania aplikacji Dynamics 365 for Finance and Operations — Magazynowanie.

Aplikacja do magazynowania jest dostępna w sklepie Google Play i sklepie Windows. Dla bieżącej wersji Dynamics 365 Supply Chain Management ta aplikacja jest udostępniana jako autonomiczny składnik, co oznacza konieczność samodzielnej instalacji na urządzeniach używanych do prac magazynowych. Aby korzystać z aplikacji w swoim środowisku Finance and Operations, należy pobrać aplikację do każdego urządzenia i skonfigurować ją do łączenia się ze środowiskiem Supply Chain Management. W tym temacie opisano sposób instalowania aplikacji na urządzeniach. Wyjaśniono również, jak skonfigurować aplikację, aby się łączyła ze środowiskiem Supply Chain Management.

## <a name="prerequisites"></a>Wymagania wstępne
Aplikacja jest dostępna w systemach operacyjnych Windows i Android. Aby można było używać tej aplikacji, na firmowych urządzeniach musi być zainstalowany jeden z poniższych obsługiwanych systemów operacyjnych. Wymagana jest jedna z następujących wspomaganych wersji. Użyj informacji w poniższej tabeli, aby ocenić, czy Twoje środowisko sprzętowe i programowe jest gotowe do obsługi instalacji.

| Platforma                    | Wersja                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0, 9.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (wszystkie wersje)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, wersja 1611 <br>— lub — <br>Microsoft Dynamics AX w wersji 7.0/7.0.1 i aktualizacja 2 platformy Microsoft Dynamics AX z poprawką KB 3210014 |

## <a name="get-the-app"></a>Pobieranie aplikacji
-   Windows (UWP)
     - [Finance and Operations — Magazynowanie w Sklepie Windows](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations — Magazynowanie w sklepie Google Play](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> Galerii aplikacji Zebra została wycofana, co oznacza, że aplikacja Magazynowanie nie będzie już dostępna do pobrania z tej lokalizacji.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory
Aby umożliwić aplikacji interakcje z konkretnym serwerem Supply Chain Management, należy zarejestrować aplikację usługi internetowej w usłudze Azure Active Directory dla dzierżawy programu Supply Chain Management. Ze względów bezpieczeństwa zaleca się utworzenie aplikacji usługi internetowej dla każdego używanego urządzenia. Aby utworzyć aplikację usługi internetowej w usłudze Azure Active Directory (Azure AD), wykonaj następujące kroki:

1.  W przeglądarce sieci web przejdź do strony <https://portal.azure.com>.
2.  Wprowadź nazwę i hasło użytkownika mającego dostęp do subskrypcji usługi Azure.
3.  W portalu Azure w lewym okienku nawigacyjnym kliknij opcję **Azure Active Directory**.

    [![WMA-01-aktywny-katalog-przykład](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)

4.  Upewnij się, że program Supply Chain Management używa wystąpienia usługi Active Directory.
5.  Na liście kliknij opcję **Rejestracje aplikacji**. 

    [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)

6.  W górnym okienku kliknij opcję **Nowa rejestracja**. Zostanie uruchomiony **kreator dodawanie aplikacji**.
7.  Wprowadź nazwę aplikacji i wybierz **Tylko konta w tym katalogu organizacyjnym**. Kliknij **Zarejestruj**.  

    [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)

8.  Nowa rejestracja aplikacji zostanie otwarta. 

    [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)

9.  Należy pamiętać wartość pola **Identyfikator aplikacji**, będzie potrzebna później. W dalszej części pole **Identyfikator aplikacji** będzie nazywane **Identyfikator klienta**.
10. Kliknij łącze **Certyfikaty i wpisy tajne** w okienku **Zarządzanie**. Kliknij opcję **Nowy wpis tajny klienta**. 

    [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

11. Utwórz klucz poprzez wprowadzenie opisu klucza i czasu trwania w sekcji **Hasła**. Kliknij przycisk **Dodaj** i skopiuj klucz. Ten klucz będzie później określany jako **klucz tajny klienta**. 

    [![WMA-06-active-directory-save-key](./media/WMA-06-active-directory-save-key.png)](./media/WMA-06-active-directory-save-key.png)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Tworzenie i konfigurowanie konta użytkownika w programie Supply Chain Management
Aby umożliwić programowi Supply Chain Management używanie aplikacji Azure AD, należy wykonać następujące czynności konfiguracyjne:

1.  Tworzenie użytkownika odpowiadającego poświadczeniom użytkownika aplikacji magazynowania.
    1.  Wybierz kolejno opcje **Administrowanie systemem** &gt; **Wspólne** &gt; **Użytkownicy**.
    2.  Utwórz nowego użytkownika.
    3.  Przypisz użytkownika urządzenia przenośnego pracującego w magazynie, jak pokazano na poniższym zrzucie ekranu. 
    
        [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Skojarz aplikację Azure Active Directory z użytkownikiem aplikacji magazynowania.
    1.  W programie Supply Chain Management wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Aplikacje usługi Azure Active Directory**
    2.  Utwórz nowy wiersz.
    3.  Wypełnij pole **Identyfikator klienta** (identyfikatorem uzyskanym w ostatniej sekcji), nadaj klientowi nazwę i wybierz uprzednio utworzonego użytkownika. Zaleca się znakowanie wszystkich urządzeń, tak aby w razie ich zgubienia można było na tej stronie łatwo usunąć im dostęp do programu Supply Chain Management. 
    
        [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurowanie aplikacji
Aplikację w urządzeniu należy skonfigurować do łączenia się z serwerem programu Supply Chain Management za pośrednictwem aplikacji Azure AD. W tym celu:

1.  W aplikacji przejdź do okna **Ustawienia połączenia**.
2.  Wyczyść pole **Tryb demonstracyjny**. <br>

    [![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)

3.  Podaj poniższe informacje: 
    + **Identyfikator klienta usługi katalogu Azure Active** — identyfikator klienta uzyskuje się w kroku 9 procedury „Tworzenie aplikacji usługi internetowej w usłudze Active Directory”. 
    + **Klucz tajny klienta katalogu usługi Azure Active** — klucz tajny klienta uzyskuje się w kroku 11 procedury „Tworzenie aplikacji usługi internetowej w usłudze Active Directory”. 
    + **Zasób katalogowy usługi Azure Active directory** — zasób katalogowy usługi Azure AD opisuje adres URL głównego katalogu programu Supply Chain Management. 
    
        > [!NOTE]
        > Na końcu pola nie należy umieszczać znaku kreski ułamkowej (/). 

    + **Dzierżawca katalogu usługi Azure Active** — Dzierżawa katalogu usługi Azure AD używana na serwerze programu Supply Chain Management: `https://login.windows.net/your-AD-tenant-ID`. Na przykład: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    
        > [!NOTE]
        > Na końcu pola nie należy umieszczać znaku kreski ułamkowej (/). 
    
    + **Firma** — wpisz firmę zdefiniowaną w programie Supply Chain Management, z którą ma się łączyć aplikacja. <br>
    
    [![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)

4.  Kliknij przycisk **Wstecz** w lewym górnym rogu aplikacji. Aplikacja połączy się teraz z serwerem programu Supply Chain Management i zostanie wyświetlony ekran logowania dla pracownika magazynu.

    [![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Aby dowiedzieć się więcej o tym, jak w aplikacji Magazynowanie skonfigurować skanowanie kodów kreskowych przy użyciu aparatu urządzenia komórkowego, zobacz [Skanowanie kodów kreskowych za pomocą aparatu w programie Dynamics 365 for Finance and Operations — aplikacja Magazynowanie](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Usuwanie dostępu urządzenia
Jeśli urządzenie zostanie zgubione lub dostanie się w niepowołane ręce, należy usunąć temu urządzeniu dostęp do programu Supply Chain Management. Następujące kroki opisują zalecany proces usuwania dostępu.

1.  Wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **aplikacje Azure Active Directory**. 
2.  Usuń wiersz odpowiadający urządzeniu, któremu chcesz cofnąć dostęp. Należy zapamiętać wartość pola **Identyfikator klienta** używany dla usuniętego urządzenia. Będzie ona potrzebna później.
3.  Zaloguj się do portalu Azure pod adresem <https://portal.azure.com>.
4.  W lewym menu kliknij ikonę **Active Directory** i upewnij się, że jesteś w poprawnym katalogu.
5.  Na liście kliknij opcję **Rejestracje aplikacji**, a następnie kliknij aplikację, którą chcesz skonfigurować. Zostanie wyświetlona strona **Ustawienia** z informacjami o konfiguracji.
6.  Upewnij się, że wartość **Identyfikator klienta** dla aplikacji jest taka sama, jak w kroku 2 w tej sekcji.
7.  W górnym okienku kliknij przycisk **Usuń**.
8.  W komunikacie potwierdzenia kliknij przycisk **Tak**.
