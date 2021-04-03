---
title: Instalowanie i łączenie aplikacji magazynowej
description: W tym temacie opisano sposób instalowania aplikacji magazynowej na każdym urządzeniu przenośnym i konfigurowania jej w celu nawiązania połączenia ze środowiskiem aplikacji Microsoft Dynamics 365 Supply Chain Management. Poszczególne urządzenia można konfigurować ręcznie lub można importować ustawienia połączenia za pośrednictwem pliku lub przez skanowanie kodu QR.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3d2920d015aab5e4f0a1966d2a2574fb659a7c80
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5486984"
---
# <a name="install-and-connect-the-warehouse-app"></a>Instalowanie i łączenie aplikacji magazynu

[!include [banner](../includes/banner.md)]

> [!NOTE]
> W tym temacie opisano sposób konfigurowania starej aplikacji magazynu. Jeśli chcesz uzyskać informacje dotyczące konfigurowania nowej aplikacji mobilnej Zarządzanie magazynem, zobacz temat [Instalowanie i łączenie aplikacji mobilnej Zarządzanie magazynem](install-configure-warehouse-management-app.md).

> [!NOTE]
> W tym temacie opisano sposób konfigurowania aplikacji magazynu dla wdrożeń w chmurze. Jeśli szukasz informacji dotyczących sposobu konfigurowania aplikacji magazynu dla wdrożeń lokalnych, zapoznaj się z tematem [Magazynowanie we wdrożeniach lokalnych](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).

Aplikacja magazynowa jest dostępna w sklepie Google Play i sklepie Microsoft Store. Jest ona udostępniana jako składnik autonomiczny. Dlatego należy ją pobrać na każde urządzenie, a następnie skonfigurować do nawiązywania połączenia ze środowiskiem aplikacji Microsoft Dynamics 365 Supply Chain Management.

W tym temacie opisano sposób instalowania aplikacji magazynowej na każdym urządzeniu przenośnym i konfigurowania jej w celu nawiązania połączenia ze środowiskiem aplikacji Supply Chain Management. Poszczególne urządzenia można konfigurować ręcznie lub można importować ustawienia połączenia za pośrednictwem pliku lub przez skanowanie kodu QR.

## <a name="system-requirements"></a>Wymagania systemowe

Aplikacja magazynowa jest dostępna w systemach operacyjnych Windows i Android. Aby używać najnowszej wersji aplikacji, na urządzeniach przenośnych musi być zainstalowany jeden z poniższych systemów operacyjnych:

- Aktualizacja Fall Creators Update 1709 systemu Windows 10 (Universal Windows Platform \[UWP\]) (kompilacja 10.0.16299) lub nowsza wersja
- Android 4.4 lub nowsza wersja

> [!NOTE]
> Jeśli musisz obsługiwać starsze urządzenia z systemem Windows, na których nie można uruchamiać najnowszej wersji systemu Windows, nadal można pobrać wersję 1.6.3.0 aplikacji magazynowej ze sklepu Microsoft Store. Ta wersja będzie działać w systemie Windows 10 (UWP) z listopadową aktualizacją Update 1511 (kompilacja 10.0.10586) lub nowszej wersji. Należy jednak pamiętać, że ta wersja aplikacji magazynowej nie obsługuje wdrożenia masowego ustawień połączenia. Dlatego należy [ręcznie skonfigurować połączenie](#config-manually) na każdym urządzeniu, na którym jest uruchamiana ta wersja aplikacji.

## <a name="get-the-warehouse-app"></a>Pobieranie aplikacji magazynowej

Aby pobrać aplikację, użyj jednego z następujących linków:

- **Windows (UWP):** [Dynamics 365 for Finance and Operations - Warehousing w sklepie Microsoft Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
- **Android:** [Warehousing - Dynamics 365 w sklepie Google Play](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

W przypadku mniejszych wdrożeń możesz zainstalować aplikację z odpowiedniego sklepu na każdym urządzeniu, a następnie ręcznie skonfigurować połączenie z używanymi środowiskami. Natomiast w aplikacji magazynowej w wersji 1.7.0.0 lub nowszej można również zautomatyzować wdrażanie i/lub konfigurację aplikacji. Takie podejście może okazać się wygodne w przypadku korzystania z rozwiązania do zarządzania urządzeniami przenośnymi i zarządzania aplikacjami mobilnymi, takiego jak usługa [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune). Aby uzyskać informacje na temat dodawania aplikacji za pomocą usługi Intune, zapoznaj się z tematem [Dodawanie aplikacji do usługi Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-add).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory

Aby umożliwić aplikacji magazynowej interakcję z konkretnym serwerem Supply Chain Management, należy zarejestrować aplikację usługi internetowej w usłudze dla dzierżawy aplikacji Supply Chain Management w usłudze Azure Active Directory (Azure AD). Poniższa procedura przedstawia jeden ze sposobów wykonania tego zadania. Aby uzyskać szczegółowe informacje i rozwiązania alternatywne, zobacz linki pod opisem procedury.

1. W przeglądarce internetowej przejdź do strony [https://portal.azure.com](https://portal.azure.com/).
1. Wprowadź nazwę i hasło użytkownika z dostępem do subskrypcji platformy Azure.
1. W witrynie Azure Portal w lewym okienku nawigacji wybierz pozycję **Azure Active Directory**.

    ![Azure Active Directory](media/app-connect-azure-aad.png "Usługa Azure Active Directory")

1. Upewnij się, że pracujesz z wystąpieniem usługi Azure AD używanym przez aplikację Supply Chain Management.
1. Na liście **Zarządzaj** wybierz pozycję **Rejestracje aplikacji**.

    ![Rejestracje aplikacji](media/app-connect-azure-register.png "Rejestracje aplikacji")

1. Na pasku narzędzi wybierz pozycję **Nowa rejestracja**, aby otworzyć kreatora **Rejestrowanie aplikacji**.
1. Wprowadź nazwę aplikacji, wybierz pozycję **Tylko konta w tym katalogu organizacyjnym**, a następnie wybierz pozycję **Zarejestruj**.

    ![Kreator rejestrowania aplikacji](media/app-connect-azure-register-wizard.png "Kreator rejestrowania aplikacji")

1. Zostanie otwarta nowa rejestracja aplikacji. Zanotuj wartość pola **Identyfikator aplikacji (klienta)**, ponieważ będzie ona potrzebna później. W dalszej części tego tematu ten identyfikator będzie określany jako *identyfikator klienta*.

    ![Identyfikator aplikacji (klienta)](media/app-connect-azure-app-id.png "Identyfikator aplikacji (klienta)")

1. Na liście **Zarządzaj** wybierz pozycję **Certyfikat i wpisy tajne**. Następnie wybierz jeden z poniższych przycisków, w zależności od tego, w jaki sposób chcesz skonfigurować aplikację do uwierzytelniania. (Aby uzyskać więcej informacji, zapoznaj się z sekcją [Uwierzytelnianie przy użyciu certyfikatu lub wpisu tajnego klienta](#authenticate) w dalszej części tego tematu).

    - **Przekaż certyfikat** — umożliwia przekazywanie certyfikatu, który ma być używany jako wpis tajny. Zalecamy stosowanie tego podejścia, ponieważ jest ono bezpieczniejsze i można je również automatyzować w większym stopniu. Jeśli uruchamiasz aplikację magazynowej na urządzeniach z systemem Windows, zanotuj wartość pola **Odcisk palca** pokazaną po przekazaniu certyfikatu. Ta wartość będzie potrzebna podczas konfigurowania certyfikatu na urządzeniach z systemem Windows.
    - **Nowy wpis tajny klienta** — umożliwia utworzenie klucza przez wprowadzenie opisu i czasu trwania dla klucza w sekcji **Hasła**, a następnie wybranie pozycji **Dodaj**. Utwórz kopię klucza i zapisz go w bezpiecznym miejscu.

    ![Certyfikat i wpisy tajne](media/app-connect-azure-authentication.png "Certyfikat i wpisy tajne")

Aby uzyskać więcej informacji na temat konfigurowania aplikacji usług internetowych w usłudze Azure AD, zapoznaj się z następującymi zasobami:

- Aby uzyskać instrukcje dotyczące konfigurowania aplikacji usług internetowych w usłudze Azure AD przy użyciu programu Windows PowerShell, zapoznaj się z tematem [Instrukcje: używanie Azure PowerShell do tworzenia jednostki usługi przy użyciu certyfikatu](https://docs.microsoft.com/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Aby uzyskać kompletne informacje dotyczące ręcznego tworzenia aplikacji usługi internetowej w usłudze Azure AD, zapoznaj się z następującymi tematami:

    - [Przewodnik Szybki start: Rejestrowanie aplikacji na platformie tożsamości firmy Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)
    - [Instrukcje: korzystanie z portalu do tworzenia aplikacji usługi Azure AD i nazwy głównej usługi, która może uzyskiwać dostęp do zasobów](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Tworzenie i konfigurowanie konta użytkownika w programie Supply Chain Management

Aby aplikacja Supply Chain Management mogła korzystać z aplikacji Azure AD, wykonaj następujące kroki.

1. Utwórz użytkownika odpowiadającego poświadczeniom użytkownika dla aplikacji magazynowej:

    1. W aplikacji Supply Chain Management wybierz kolejno pozycje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
    1. Utwórz użytkownika.
    1. Przypisz użytkownika urządzenia przenośnego dla magazynu.

    ![Przypisywanie użytkownika urządzenia przenośnego dla magazynu](media/app-connect-app-users.png "Przypisywanie użytkownika urządzenia przenośnego dla magazynu")

1. Skojarz aplikację usługi Azure AD z użytkownikiem aplikacji magazynowej:

    1. Przejdź do pozycji **Administrowanie systemem \> Ustawienia \> Aplikacje usługi Azure Active Directory**.
    1. Utwórz wiersz.
    1. Wprowadź identyfikator klienta, który zanotowano w poprzedniej sekcji, nadaj mu nazwę i wybierz właśnie utworzonego użytkownika. Zalecamy oznakowanie wszystkich urządzeń. W przypadku ich utraty będzie można łatwo usunąć ich dostęp do aplikacji Supply Chain Management z tej strony.

    ![Aplikacje usługi Azure Active Directory](media/app-connect-aad-apps.png "Aplikacje usługi Azure Active Directory")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Uwierzytelnianie przy użyciu certyfikatu lub wpisu tajnego klienta

Uwierzytelnianie za pomocą usługi Azure AD zapewnia bezpieczny sposób połączenia urządzenia przenośnego z aplikacją Supply Chain Management. Uwierzytelnianie można przeprowadzić przy użyciu wpisu tajnego klienta lub certyfikatu. Jeśli zaimportujesz ustawienia połączenia, zalecamy użycie certyfikatu zamiast wpisu tajnego klienta. Ponieważ wpis tajny klienta musi być zawsze przechowywany w bezpieczny sposób, nie można go importować z pliku ustawień połączenia ani z kodu QR, jak opisano w dalszej części tego tematu.

Certyfikaty mogą być używane jako wpisy tajne w celu udowodnienia tożsamości aplikacji w przypadku żądania tokenu. Publiczna część certyfikatu jest przekazywana do rejestracji aplikacji w witrynie Azure Portal, podczas gdy pełny certyfikat musi zostać wdrożony na każdym urządzeniu, na którym zainstalowano aplikację magazynową. Organizacja jest odpowiedzialna za zarządzanie certyfikatem w kategorii wymiany itd. Można używać certyfikatów z podpisem własnym, ale zawsze należy używać certyfikatów bez możliwości eksportowania.

Certyfikat musi zostać udostępniony lokalnie na każdym urządzeniu, na którym działa aplikacja magazynowa. Aby uzyskać informacje dotyczące sposobu zarządzania certyfikatami urządzeń kontrolowanych przez usługę Intune w przypadku korzystania z usługi Intune, zapoznaj się z tematem [Używanie certyfikatów do uwierzytelniania w usłudze Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Konfigurowanie aplikacji przez zaimportowanie ustawień połączenia

Aby ułatwić obsługę i wdrażanie aplikacji na wielu urządzeniach przenośnych, można zaimportować ustawienia połączenia, zamiast ręcznie wprowadzać je na każdym urządzeniu. W tej sekcji opisano sposób tworzenia i importowania ustawień.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Tworzenie pliku lub kodu QR ustawień połączenia

Ustawienia połączenia można zaimportować z pliku lub kodu QR. W obu przypadkach trzeba najpierw utworzyć plik ustawień, w którym jest używany format i składnia notacji JavaScript Object Notation (JSON). Plik musi zawierać listę połączeń zawierającą poszczególne połączenia do dodania. W poniższej tabeli zestawiono parametry, które należy określić w pliku ustawień połączenia.

| Parametr | opis |
| --- | --- |
| ConnectionName | Określ nazwę ustawienia połączenia. Tekst może mieć maksymalnie 20 znaków. Ponieważ ta wartość jest unikatowym identyfikatorem ustawienia połączenia, upewnij się, że jest ona unikatowa na liście. Jeśli na urządzeniu istnieje już połączenie o takiej samej nazwie, zostanie ono zastąpione przez ustawienia z importowanego pliku. |
| ActiveDirectoryClientAppId | Podaj identyfikator klienta zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Określ główny adres URL aplikacji Supply Chain Management. |
| ActiveDirectoryTenant | Określ dzierżawę usługi Azure AD używaną z serwerem aplikacji Supply Chain Management. Ta wartość ma postać `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Oto przykład: `https://login.windows.net/contosooperations.onmicrosoft.com`. |
| Firma | Określ firmę zdefiniowaną w aplikacji Supply Chain Management, z którą ma się łączyć aplikacja. |
| ConnectionType | (Opcjonalnie) Określ, czy ustawienie połączenia powinno używać certyfikatu, czy też wpisu tajnego klienta, aby połączyć się ze środowiskiem. Prawidłowe wartości to *„certificate”* i *„clientsecret”*. Domyślna wartość to *„certificate”*.<p>**Uwaga:** wpisów tajnych klienta nie można importować.</p> |
| IsEditable | (Opcjonalnie) Określ, czy użytkownik aplikacji ma mieć możliwość edytowania ustawienia połączenia. Prawidłowe wartości to *„true”* i *„false”*. Domyślna wartość to *„true”*. |
| IsDefault | (Opcjonalnie) Określ, czy połączenie jest połączeniem domyślnym. Połączenie ustawione jako połączenie domyślne zostanie automatycznie wstępnie wybrane w momencie otwarcia aplikacji. Tylko jedno połączenie można ustawić jako połączenie domyślne. Prawidłowe wartości to *„true”* i *„false”*. Domyślna wartość to *„false”*. |
| CertificateThumbprint | (Opcjonalnie) Dla urządzeń z systemem Windows można określić odcisk palca certyfikatu dla połączenia. W przypadku urządzeń z systemem Android użytkownik aplikacji musi wybrać certyfikat przy pierwszym użyciu połączenia. |

Poniższy przykład przedstawia prawidłowy plik ustawień połączenia, który zawiera dwa połączenia. Jak widać, lista połączeń (o nazwie *„ConnectionList”* w pliku) jest obiektem zawierającym macierz, w której każde połączenie jest przechowywane jako obiekt. Każdy obiekt musi być ujęty w nawiasy klamrowe ({}) i oddzielony przecinkami, a macierz musi być ujęta w nawiasy kwadratowe (\[\]).

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Możesz zapisać te informacje jako plik JSON lub wygenerować kod QR o tej samej zawartości. Jeśli zapiszesz informacje jako plik, zalecamy zapisanie go przy użyciu nazwy domyślnej, *connections.json*, zwłaszcza jeśli będzie on przechowywany w lokalizacji domyślnej na każdym urządzeniu przenośnym.

### <a name="save-the-connection-settings-file-on-each-device"></a>Zapisywanie pliku ustawień połączenia na każdym urządzeniu

Zazwyczaj do dystrybuowania plików ustawień połączenia na każde zarządzane urządzenie jest używane narzędzie do zarządzania urządzeniami lub odpowiedni skrypt. Jeśli podczas zapisywania pliku ustawień połączenia na każdym urządzeniu zostanie użyta domyślna nazwa i lokalizacja, aplikacja magazynowa automatycznie zaimportuje plik, nawet podczas pierwszego uruchomienia po zainstalowaniu aplikacji. Jeśli używasz niestandardowej nazwy lub lokalizacji pliku, użytkownik aplikacji musi określić wartości podczas pierwszego uruchomienia. Aplikacja będzie nadal korzystać z wybranej nazwy i lokalizacji w terminie późniejszym.

Każde ponowne uruchomienie aplikacji spowoduje ponowne zaimportowanie ustawień połączenia z ich poprzedniej lokalizacji w celu ustalenia, czy zostały wprowadzone jakiekolwiek zmiany. Aplikacja zaktualizuje tylko te połączenia, które mają takie same nazwy jak połączenia w pliku ustawień połączenia. Utworzone przez użytkownika połączenia używające innych nazw nie zostaną zaktualizowane.

Nie można usunąć połączenia przy użyciu pliku ustawień połączenia.

Jak wspomniano, domyślna nazwa pliku to *connections.json*. Domyślna lokalizacja pliku zależy od tego, czy jest używane urządzenie z systemem Windows czy urządzenie z systemem Android:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.Dynamics365forOperations-Warehousing_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.Dynamics365forOperationsWarehousing\files`

Zazwyczaj ścieżki są tworzone automatycznie po pierwszym uruchomieniu aplikacji. Można je jednak utworzyć ręcznie, jeśli przed instalacją trzeba przenieść plik ustawień połączenia na urządzenie.

> [!NOTE]
> Jeśli aplikacja zostanie odinstalowana, ścieżka domyślna i jej zawartość zostaną usunięte.

### <a name="import-the-connection-settings"></a>Importowanie ustawień połączenia

Wykonaj poniższe kroki, aby zaimportować ustawienia połączenia z pliku lub kodu QR.

1. Otwórz aplikację magazynową na urządzeniu przenośnym.
1. Przejdź do obszaru **Ustawienia połączenia**.
1. W opcji **Użyj trybu demonstracyjnego** ustaw wartość _Nie_.

    ![Opcja Użyj trybu demonstracyjnego](media/app-connect-app-demo-mode.png "Opcja Użyj trybu demonstracyjnego")

1. Wybierz pozycję **Wybierz plik** lub **Skanuj kod QR**, w zależności od tego, w jaki sposób chcesz zaimportować ustawienia:

    - W przypadku importowania ustawień połączenia z pliku aplikacja mogła już odnaleźć plik, jeśli nazwa domyślna i lokalizacja domyślna zostały użyte podczas zapisywania. W przeciwnym razie wybierz pozycję **Wybierz plik**, przejdź do pliku na urządzeniu lokalnym i zaznacz go. Jeśli wybierzesz lokalizację niestandardową, aplikacja zapisze ją i automatycznie użyje jej przy następnym uruchomieniu.
    - Jeśli importujesz ustawienia połączenia przez skanowanie kodu QR, wybierz pozycję **Skanuj kod QR**. Aplikacja monituje o uprawnienie do korzystania z aparatu urządzenia. Po udzieleniu uprawnienia aparat zostanie uruchomiony i można będzie używać go do skanowania. W zależności od jakości aparatu urządzenia i złożoności kodu QR może się okazać, że uzyskanie poprawnego skanu jest trudne. W takim przypadku spróbuj zmniejszyć złożoność kodu QR, generując tylko jedno połączenie na kod QR. (Obecnie do skanowania kodu QR można używać tylko kamery urządzenia).

    ![Importowanie ustawień połączenia](media/app-connect-app-select-file.png "Importowanie ustawień połączenia")

1. Po pomyślnym załadowaniu ustawień połączenia wybierz przycisk **Wstecz** (strzałka w lewo) znajdujący się w lewym górnym rogu strony.

    ![Załadowane ustawienia połączenia](media/app-connect-app-settings-loaded.png "Załadowane ustawienia połączenia")

1. Jeśli używasz urządzenia z systemem Android i certyfikatu do uwierzytelniania, urządzenie monituje o wybranie certyfikatu.

    ![Wybieranie monitu o certyfikat na urządzeniu z systemem Android](media/app-connect-app-choose-cert.png "Wybieranie monitu o certyfikat na urządzeniu z systemem Android")

1. Aplikacja łączy się z serwerem Supply Chain Management i pokazuje stronę rejestracji.

    ![Strona logowania](media/app-connect-sign-in.png "Strona logowania")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Ręczne konfigurowanie aplikacji

Aplikację w urządzeniu można ręcznie skonfigurować tak, aby łączyła się z serwerem programu Supply Chain Management za pośrednictwem aplikacji usługi Azure AD.

1. Otwórz aplikację magazynową na urządzeniu przenośnym.
1. Przejdź do obszaru **Ustawienia połączenia**.
1. W opcji **Użyj trybu demonstracyjnego** ustaw wartość _Nie_.

    ![Wyłączony tryb demonstracyjny](media/app-connect-app-select-file.png "Wyłączony tryb demonstracyjny")

1. Wybierz pole **Wybierz połączenie**, aby rozwinąć ustawienia wymagane do ręcznego wprowadzania szczegółów połączenia.

    ![Pola połączenia ręcznego](media/app-connect-manual-connect.png "Pola połączenia ręcznego")

1. Podaj poniższe informacje:

    - **Użyj klucza tajnego klienta** — tę opcję należy ustawić na _Tak_, aby do uwierzytelniania za pomocą programu Supply Chain Management był używany klucz tajny klienta. Wartość _Nie_ będzie używana do uwierzytelniania za pomocą certyfikatu. (Aby uzyskać więcej informacji, zapoznaj się z tematem [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).)
    - **Nazwa połączenia** — wprowadź nazwę nowego połączenia. Ta nazwa będzie wyświetlana w polu **Wybierz połączenie** przy następnym otwarciu ustawień połączenia. Wprowadzana nazwa musi być unikatowa. (Mówiąc inaczej, musi się ona różnić od wszystkich innych nazw połączeń przechowywanych na urządzeniu, jeśli są na nim przechowywane inne nazwy połączeń).
    - **Identyfikator klienta usługi Active Directory** — podaj identyfikator klienta zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).
    - **Klucz tajny klienta usługi Active Directory** — to pole jest dostępne tylko wtedy, gdy opcja **Użyj klucza tajnego klienta** została ustawiona na wartość _Tak_. Wprowadź klucz tajny klienta zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).
    - **Odcisk palca usługi Active Directory** — to pole jest dostępne na urządzeniach z systemem Windows tylko wtedy, gdy opcja **Użyj klucza tajnego klienta** została ustawiona na wartość _Nie_. Wprowadź odcisk palca certyfikatu zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).
    - **Zasób usługi Active Directory** — określ główny adres URL programu Supply Chain Management.

        > [!NOTE]
        > Tej wartości nie należy kończyć ukośnikiem (/).

    - **Dzierżawa usługi Active Directory** — wprowadź dzierżawę usługi Azure AD używanej na serwerze programu Supply Chain Management. Ta wartość ma postać `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Oto przykład: `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!NOTE]
        > Tej wartości nie należy kończyć ukośnikiem (/).

    - **Firma** — wprowadź firmę zdefiniowaną w programie Supply Chain Management, z którą ma się łączyć aplikacja.

1. Kliknij przycisk **Zapisz** w prawym górnym rogu strony.
1. Jeśli używasz urządzenia z systemem Android i certyfikatu do uwierzytelniania, urządzenie monituje o wybranie certyfikatu.
1. Aplikacja łączy się z serwerem Supply Chain Management i pokazuje stronę rejestracji.

## <a name="remove-access-for-a-device"></a>Usuwanie dostępu urządzenia

Jeśli urządzenie zostanie zgubione lub dostanie się w niepowołane ręce, należy usunąć z tego urządzenia dostęp do programu Supply Chain Management. Następujące kroki opisują zalecany proces usuwania dostępu.

1. Przejdź do pozycji **Administrowanie systemem \> Ustawienia \> Aplikacje usługi Azure Active Directory**.
1. Usuń wiersz odpowiadający urządzeniu, z którego chcesz usunąć dostęp. Zanotuj identyfikator klienta, który został użyty dla usuniętego urządzenia, ponieważ będzie on potrzebny później.

    Jeśli zarejestrowano tylko jeden identyfikator klienta, a wiele urządzeń używa tego samego identyfikatora klienta, musisz wypchnąć nowe ustawienia połączenia na te urządzenia. W przeciwnym razie utracą one dostęp.

1. Zaloguj się do witryny Azure Portal pod adresem [https://portal.azure.com](https://portal.azure.com/).
1. W lewym okienku nawigacyjnym wybierz pozycję **Active Directory** i upewnij się, że jesteś w poprawnym katalogu.
1. Na liście **Zarządzaj** wybierz pozycję **Rejestracje aplikacji**, a następnie wybierz aplikację, którą chcesz skonfigurować. Pojawi się strona **Ustawienia** z informacjami o konfiguracji.
1. Upewnij się, że identyfikator klienta jest zgodny z identyfikatorem klienta zanotowanym w kroku 2.
1. Na pasku narzędzi wybierz pozycję **Usuń**.
1. W wyświetlonym oknie komunikatu potwierdzenia wybierz przycisk **Tak**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]