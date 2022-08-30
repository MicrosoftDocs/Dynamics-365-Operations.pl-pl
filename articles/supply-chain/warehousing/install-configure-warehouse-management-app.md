---
title: Instalowanie i łączenie aplikacji mobilnej Warehouse Management
description: W tym artykule opisano sposób instalowania aplikacji mobilnej Zarządzanie magazynem na każdym urządzeniu przenośnym i konfigurowania jej w celu nawiązania połączenia ze środowiskiem aplikacji Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d6131d205e650c0de88b85434629ed9537c2a0b1
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335654"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Instalowanie i łączenie aplikacji mobilnej Warehouse Management

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób pobierania i instalowania aplikacji mobilnej Zarządzanie magazynem na każdym urządzeniu przenośnym i konfigurowania jej w celu nawiązania połączenia ze środowiskiem aplikacji Supply Chain Management. Poszczególne urządzenia można konfigurować ręcznie lub można importować ustawienia połączenia za pośrednictwem pliku lub przez skanowanie kodu QR.

## <a name="system-requirements"></a>Wymagania systemowe

Aplikacja mobilna Zarządzanie magazynem jest dostępna w systemach operacyjnych Windows i Google Android. Aby można było używać aplikacji, na urządzeniach przenośnych musi być zainstalowany jeden z poniższych systemów operacyjnych:

- Windows 10 (Uniwersalna platforma systemu Windows \[UWP\]), aktualizacja 1809 z października 2018 r. (kompilacja 10.0.17763) lub nowsza wersja
- Android 4.4 lub nowsza wersja

## <a name="turn-warehouse-management-mobile-app-features-on-or-off-in-supply-chain-management"></a>Włączanie lub wyłączanie funkcji aplikacji mobilnej Warehouse Management w Supply Chain Management

Aby korzystać z aplikacji mobilnej Warehouse Management, dla systemu muszą być włączone *ustawienia użytkownika, ikony i tytuły kroku nowej funkcji aplikacji magazynowej*. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Ustawienia użytkownika, ikony i tytuły kroków dla nowej aplikacji magazynowej* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="get-the-warehouse-management-mobile-app"></a>Pobieranie aplikacji mobilnej Zarządzanie magazynem

W przypadku mniejszych wdrożeń możesz chcieć zainstalować aplikację na każdym urządzeniu z odpowiedniego sklepu, a następnie ręcznie skonfigurować połączenie z używanymi środowiskami.

W przypadku większych wdrożeń można zautomatyzować wdrażanie i / lub konfigurację aplikacji, co może być wygodniejsze, jeśli zarządzasz wieloma urządzeniami. Można na przykład używać rozwiązania do zarządzania urządzeniami przenośnymi i aplikacji przenośnych, takich jak [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Aby uzyskać informacje na temat dodawania aplikacji za pomocą usługi Intune, zapoznaj się z tematem [Dodawanie aplikacji do usługi Microsoft Intune](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Instalowanie aplikacji ze sklepu aplikacji

Najłatwiejszym sposobem zainstalowania aplikacji na jednym urządzeniu jest zainstalowanie jej ze sklepu z aplikacjami, który zawsze udostępnia najnowszą ogólnie dostępną wersję. Usługa Microsoft Intune może także pobierać aplikacje ze sklepów aplikacji. Aby zainstalować aplikację ze sklepu aplikacji, użyj jednego z następujących łączy:

- **Windows (UWP):** [Zarządzanie magazynem w Microsoft Store](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Zarządzanie magazynem dla sklepu Google Play](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Pobierz aplikację z aplikacji Microsoft App Center

Alternatywą dla instalacji ze sklepu z aplikacjami jest pobranie aplikacji z Microsoft App Center. Centrum aplikacji udostępnia pakiety do zainstalowania, które można załadować. Oprócz bieżącej wersji App Center umożliwia również pobieranie poprzednich wersji i może udostępniać wersje zapoznawcze z nadchodzącymi funkcjami, które można wypróbować. Aby pobrać bieżące, poprzednie lub podglądowe wersje aplikacji mobilnej Zarządzanie magazynem z Microsoft App Center, użyj jednego z poniższych łączy:

- **Windows (UWP):** [Zarządzanie magazynem (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    Aby uzyskać instrukcje dotyczące instalowania pobranego pakietu na urządzeniu z systemem Windows, a następnie konfigurowania wymaganych certyfikatów, zobacz [Instalowanie kompilacji z witryny App Center](/appcenter/distribution/installation).

- **Android:** [Zarządzanie magazynem (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Jeśli pobierasz wersję zapoznawczą, musisz wykonać kilka dodatkowych czynności, aby ją zainstalować. Aby uzyskać szczegółowe informacje, zobacz temat [Testowanie aplikacji dla systemu Android](/appcenter/distribution/testers/testing-android).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory

Aby umożliwić aplikacji mobilnej Zarządzanie magazynem interakcję z konkretnym serwerem Supply Chain Management, należy zarejestrować aplikację usługi internetowej w usłudze dla dzierżawy aplikacji Supply Chain Management w usłudze Azure Active Directory (Azure AD). Poniższa procedura przedstawia jeden ze sposobów wykonania tego zadania. Aby uzyskać szczegółowe informacje i rozwiązania alternatywne, zobacz linki pod opisem procedury.

1. W przeglądarce internetowej przejdź do strony [https://portal.azure.com](https://portal.azure.com/).
1. Wprowadź nazwę i hasło użytkownika z dostępem do subskrypcji platformy Azure.
1. W witrynie Azure Portal w lewym okienku nawigacji wybierz pozycję **Azure Active Directory**.

    ![Azure Active Directory.](media/app-connect-azure-aad.png "Usługa Azure Active Directory")

1. Upewnij się, że pracujesz z wystąpieniem usługi Azure AD używanym przez aplikację Supply Chain Management.
1. Na liście **Zarządzaj** wybierz pozycję **Rejestracje aplikacji**.

    ![Rejestracje aplikacji.](media/app-connect-azure-register.png "Rejestracje aplikacji")

1. Na pasku narzędzi wybierz pozycję **Nowa rejestracja**, aby otworzyć kreatora **Rejestrowanie aplikacji**.
1. Wprowadź nazwę aplikacji, wybierz pozycję **Tylko konta w tym katalogu organizacyjnym**, a następnie wybierz pozycję **Zarejestruj**.

    ![Kreator rejestrowania aplikacji.](media/app-connect-azure-register-wizard.png "Kreator rejestrowania aplikacji")

1. Zostanie otwarta nowa rejestracja aplikacji. Zanotuj wartość pola **Identyfikator aplikacji (klienta)**, ponieważ będzie ona potrzebna później. W dalszej części tego artykułu ten identyfikator będzie określany jako *identyfikator klienta*.

    ![Identyfikator aplikacji (klienta).](media/app-connect-azure-app-id.png "Identyfikator aplikacji (klienta)")

1. Na liście **Zarządzaj** wybierz pozycję **Certyfikat i wpisy tajne**. Następnie wybierz jeden z poniższych przycisków, w zależności od tego, w jaki sposób chcesz skonfigurować aplikację do uwierzytelniania. (Aby uzyskać więcej informacji, zapoznaj się z sekcją [Uwierzytelnianie przy użyciu certyfikatu lub wpisu tajnego klienta](#authenticate) w dalszej części tego artykułu).

    - **Przekaż certyfikat** — umożliwia przekazywanie certyfikatu, który ma być używany jako wpis tajny. Zalecamy stosowanie tego podejścia, ponieważ jest ono bezpieczniejsze i można je również automatyzować w większym stopniu. Jeśli uruchamiasz aplikację mobilną Zarządzanie magazynem na urządzeniach z systemem Windows, zanotuj wartość pola **Odcisk palca** pokazaną po przekazaniu certyfikatu. Ta wartość będzie potrzebna podczas konfigurowania certyfikatu na urządzeniach z systemem Windows.
    - **Nowy wpis tajny klienta** — umożliwia utworzenie klucza przez wprowadzenie opisu i czasu trwania dla klucza w sekcji **Hasła**, a następnie wybranie pozycji **Dodaj**. Utwórz kopię klucza i zapisz go w bezpiecznym miejscu.

    ![Certyfikat i wpisy tajne.](media/app-connect-azure-authentication.png "Certyfikat i wpisy tajne")

Aby uzyskać więcej informacji na temat konfigurowania aplikacji usług internetowych w usłudze Azure AD, zapoznaj się z następującymi zasobami:

- Aby uzyskać instrukcje dotyczące konfigurowania aplikacji usług internetowych w usłudze Azure AD przy użyciu programu Windows PowerShell, zapoznaj się z tematem [Instrukcje: używanie Azure PowerShell do tworzenia jednostki usługi przy użyciu certyfikatu](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Aby uzyskać kompletne informacje dotyczące ręcznego tworzenia aplikacji usługi internetowej w usłudze Azure AD, zapoznaj się z następującymi artykułami:

    - [Przewodnik Szybki start: Rejestrowanie aplikacji na platformie tożsamości firmy Microsoft](/azure/active-directory/develop/quickstart-register-app)
    - [Instrukcje: korzystanie z portalu do tworzenia aplikacji usługi Azure AD i nazwy głównej usługi, która może uzyskiwać dostęp do zasobów](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a><a name="user-azure-ad"></a>Tworzenie i konfigurowanie konta użytkownika w programie Supply Chain Management

Aby aplikacja Supply Chain Management mogła korzystać z aplikacji Azure AD, wykonaj następujące kroki.

1. Utwórz użytkownika odpowiadającego poświadczeniom użytkownika dla aplikacji mobilnej Zarządzanie magazynem:

    1. W aplikacji Supply Chain Management wybierz kolejno pozycje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
    1. Utwórz użytkownika.
    1. Przypisz rolę *Użytkownik urządzenia przenośnego dla magazynu* do użytkownika.

    ![Przypisz użytkownika urządzenia przenośnego dla magazynu.](media/app-connect-app-users.png "Przypisywanie użytkownika urządzenia przenośnego dla magazynu")

1. Skojarz aplikację usługi Azure AD z użytkownikiem aplikacji mobilnej Zarządzanie magazynem:

    1. Przejdź do pozycji **Administrowanie systemem \> Ustawienia \> Aplikacje usługi Azure Active Directory**.
    1. Wybierz opcję **Nowy** w okienku akcji, aby utworzyć wiersz.
    1. W polu **Identyfikator klienta** wprowadź identyfikator klienta, który został zanotowany w poprzedniej sekcji.
    1. W polu **Nazwa** wprowadź nazwę.
    1. W polu **Identyfikator użytkownika** wybierz właśnie utworzony identyfikator użytkownika.

    ![Aplikacje usługi Azure Active Directory.](media/app-connect-aad-apps.png "Aplikacje usługi Azure Active Directory")

> [!TIP]
> Jednym ze sposobów użycia tych ustawień jest utworzenie identyfikatora klienta na platformie Azure dla każdego urządzenia fizycznego, a następnie dodanie każdego identyfikatora klienta do strony **aplikacji usługi Azure Active Directory**. W przypadku utraty urządzenia będzie można łatwo usunąć ich dostęp do aplikacji Supply Chain Management przez usunięcie identyfikatora klienta z tej strony. (Ta metoda działa, ponieważ poświadczenia połączenia zapisane na każdym urządzeniu określają również identyfikator klienta, zgodnie z opisem w dalszej części tego artykułu).
>
> Ponadto domyślny język, format liczby i ustawienia stref czasowych dla każdego identyfikatora klienta są określone przez preferencje ustawione dla zmapowanej w tym miejscu wartości **identyfikatora użytkownika**. Z tego względu można użyć tych preferencji, aby ustalić domyślne ustawienia dla każdego urządzenia lub kolekcji urządzeń, na podstawie identyfikatora klienta. Jednak te ustawienia domyślne zostaną zastąpione, jeśli są także zdefiniowane dla *konta użytkownika aplikacji magazynu*, którego pracownik używa do zalogowania się na urządzeniu. (Aby uzyskać więcej informacji zobacz temat [Konta użytkownika urządzenia przenośnego](mobile-device-work-users.md)).

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Uwierzytelnianie przy użyciu certyfikatu lub wpisu tajnego klienta

Uwierzytelnianie za pomocą usługi Azure AD zapewnia bezpieczny sposób połączenia urządzenia przenośnego z aplikacją Supply Chain Management. Uwierzytelnianie można przeprowadzić przy użyciu wpisu tajnego klienta lub certyfikatu. Jeśli zaimportujesz ustawienia połączenia, zalecamy użycie certyfikatu zamiast wpisu tajnego klienta. Ponieważ wpis tajny klienta musi być zawsze przechowywany w bezpieczny sposób, nie można go importować z pliku ustawień połączenia ani z kodu QR, jak opisano w dalszej części tego artykułu.

Certyfikaty mogą być używane jako wpisy tajne w celu udowodnienia tożsamości aplikacji w przypadku żądania tokenu. Publiczna część certyfikatu jest przekazywana do rejestracji aplikacji w witrynie Azure Portal, podczas gdy pełny certyfikat musi zostać wdrożony na każdym urządzeniu, na którym zainstalowano aplikację mobilną Zarządzanie magazynem. Organizacja jest odpowiedzialna za zarządzanie certyfikatem w kategorii wymiany itd. Można używać certyfikatów z podpisem własnym, ale zawsze należy używać certyfikatów bez możliwości eksportowania.

Certyfikat musi zostać udostępniony lokalnie na każdym urządzeniu, na którym działa aplikacja mobilna Zarządzanie magazynem. Aby uzyskać informacje dotyczące sposobu zarządzania certyfikatami urządzeń kontrolowanych przez usługę Intune w przypadku korzystania z usługi Intune, zapoznaj się z tematem [Używanie certyfikatów do uwierzytelniania w usłudze Microsoft Intune](/mem/intune/protect/certificates-configure).

## <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Konfiguracja aplikacji mobilnej Warehouse Management do zarządzania jednostkami skali chmury i brzegowymi

Kilka dodatkowych kroków jest wymaganych, jeśli planujecie uruchomić aplikację mobilną Warehouse Management na jednostce skali w chmurze lub na urządzeniu brzegowym. Instrukcje: [Konfiguracja aplikacji mobilnej Warehouse Management do zarządzania jednostkami skali chmury i brzegowymi](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md).

## <a name="configure-the-application-by-importing-connection-settings"></a>Konfigurowanie aplikacji przez zaimportowanie ustawień połączenia

Aby ułatwić obsługę i wdrażanie aplikacji na wielu urządzeniach przenośnych, można zaimportować ustawienia połączenia, zamiast ręcznie wprowadzać je na każdym urządzeniu. W tej sekcji opisano sposób tworzenia i importowania ustawień.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Tworzenie pliku lub kodu QR ustawień połączenia

Ustawienia połączenia można zaimportować z pliku lub kodu QR. W obu przypadkach trzeba najpierw utworzyć plik ustawień, w którym jest używany format i składnia notacji JavaScript Object Notation (JSON). Plik musi zawierać listę połączeń zawierającą poszczególne połączenia do dodania. W poniższej tabeli zestawiono parametry, które należy określić w pliku ustawień połączenia.

| Parametr | opis |
|---|---|
| ConnectionName | Określ nazwę ustawienia połączenia. Tekst może mieć maksymalnie 20 znaków. Ponieważ ta wartość jest unikatowym identyfikatorem ustawienia połączenia, upewnij się, że jest ona unikatowa na liście. Jeśli na urządzeniu istnieje już połączenie o takiej samej nazwie, zostanie ono zastąpione przez ustawienia z importowanego pliku. |
| ActiveDirectoryClientAppId | Podaj identyfikator klienta zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Określ główny adres URL aplikacji Supply Chain Management. |
| ActiveDirectoryTenant | Określ nazwę domeny usługi Azure AD używaną z serwerem aplikacji Supply Chain Management. Ta wartość ma postać `https://login.windows.net/<your-Azure-AD-domain-name>`. Oto przykład: `https://login.windows.net/contosooperations.onmicrosoft.com`. Więcej informacji na temat znajdowania nazwy domeny w usłudze Azure AD można znaleźć w temacie [Lokalizowanie identyfikatorów ważnych dla użytkownika](/partner-center/find-ids-and-domain-names). |
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

Zazwyczaj do dystrybuowania plików ustawień połączenia na każde zarządzane urządzenie jest używane narzędzie do zarządzania urządzeniami lub odpowiedni skrypt. Jeśli podczas zapisywania pliku ustawień połączenia na każdym urządzeniu zostanie użyta domyślna nazwa i lokalizacja, aplikacja mobilna Zarządzanie magazynem automatycznie zaimportuje plik, nawet podczas pierwszego uruchomienia po zainstalowaniu aplikacji. Jeśli używasz niestandardowej nazwy lub lokalizacji pliku, użytkownik aplikacji musi określić wartości podczas pierwszego uruchomienia. Aplikacja będzie nadal korzystać z wybranej nazwy i lokalizacji w terminie późniejszym.

Każde ponowne uruchomienie aplikacji spowoduje ponowne zaimportowanie ustawień połączenia z ich poprzedniej lokalizacji w celu ustalenia, czy zostały wprowadzone jakiekolwiek zmiany. Aplikacja zaktualizuje tylko te połączenia, które mają takie same nazwy jak połączenia w pliku ustawień połączenia. Utworzone przez użytkownika połączenia używające innych nazw nie zostaną zaktualizowane.

Nie można usunąć połączenia przy użyciu pliku ustawień połączenia.

Jak wspomniano, domyślna nazwa pliku to *connections.json*. Domyślna lokalizacja pliku zależy od tego, czy jest używane urządzenie z systemem Windows czy urządzenie z systemem Android:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

Zazwyczaj ścieżki są tworzone automatycznie po pierwszym uruchomieniu aplikacji. Można je jednak utworzyć ręcznie, jeśli przed instalacją trzeba przenieść plik ustawień połączenia na urządzenie.

> [!NOTE]
> Jeśli aplikacja zostanie odinstalowana, ścieżka domyślna i jej zawartość zostaną usunięte.

### <a name="import-the-connection-settings"></a>Importowanie ustawień połączenia

Wykonaj poniższe kroki, aby zaimportować ustawienia połączenia z pliku lub kodu QR.

1. Uruchom aplikację mobilną Zarządzanie magazynem na urządzeniu przenośnym. Przy pierwszym uruchomieniu aplikacji jest wyświetlana wiadomość powitania. Wybierz opcję **Wybierz połączenie**.

    ![Wiadomość powitalna.](media/app-configure-welcome-screen.png "Wiadomość powitalna")

1. W przypadku importowania ustawień połączenia z pliku z użyciem domyślnej nazwy i lokalizacji zapisania pliku aplikacja mogła już odnaleźć plik. W tym przypadku przejdź do kroku 4. W przeciwnym razie wybierz opcję **Skonfiguruj połączenie**, a następnie przejdź do kroku 3.

    ![Konfiguruj połączenie.](media/app-configure-set-up-connection.png "Konfiguruj połączenie")

1. W oknie dialogowym **Ustawienia połączenia** wybierz opcję **Dodaj z pliku** lub **Dodaj z kodu QR**, w zależności od sposobu importowania ustawień:

    - Jeśli importujesz ustawienia połączenia z pliku, wybierz polecenie **Dodaj z pliku**, przejdź do pliku na urządzeniu lokalnym i wybierz go. Jeśli wybierzesz lokalizację niestandardową, aplikacja zapisze ją i automatycznie użyje jej przy następnym uruchomieniu.
    - Jeśli importujesz ustawienia połączenia przez skanowanie kodu QR, wybierz pozycję **Dodaj z kodu QR**. Aplikacja monituje o uprawnienie do korzystania z aparatu urządzenia. Po udzieleniu uprawnienia aparat zostanie uruchomiony i można będzie używać go do skanowania. W zależności od jakości aparatu urządzenia i złożoności kodu QR może się okazać, że uzyskanie poprawnego skanu jest trudne. W takim przypadku spróbuj zmniejszyć złożoność kodu QR, generując tylko jedno połączenie na kod QR. (Obecnie do skanowania kodu QR można używać tylko kamery urządzenia).

    ![Menu ustawień połączenia.](media/app-configure-connection-setup-flyout.png "Menu ustawień połączenia")

1. Po pomyślnym załadowaniu ustawień połączenia zostanie wyświetlone wybrane połączenie.

    ![Załadowane ustawienia połączenia.](media/app-configure-select-connection.png "Załadowane ustawienia połączenia")

1. Jeśli używasz urządzenia z systemem Android i certyfikatu do uwierzytelniania, urządzenie monituje o wybranie certyfikatu.

    ![Wybieranie monitu o certyfikat na urządzeniu z systemem Android.](media/app-configure-select-certificate.png "Wybieranie monitu o certyfikat na urządzeniu z systemem Android")

1. Aplikacja łączy się z serwerem Supply Chain Management i pokazuje stronę rejestracji.

    ![Strona logowania.](media/app-configure-sign-in-page.png "Strona logowania")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Ręczne konfigurowanie aplikacji

Jeśli nie masz pliku lub kodu QR, aplikację w urządzeniu można ręcznie skonfigurować tak, aby łączyła się z serwerem programu Supply Chain Management za pośrednictwem aplikacji usługi Azure AD.

1. Uruchom aplikację mobilną Zarządzanie magazynem na urządzeniu przenośnym.
1. Jeśli aplikacja jest uruchomiona w **trybie pokazu**, wybierz opcję **Ustawienia połączenia**. Jeśli strona **logowania** jest wyświetlana w momencie uruchomienia aplikacji, wybierz pozycję **Zmień połączenie**.
1. Wybierz opcję **Skonfiguruj połączenie**.

    ![Konfiguruj połączenie.](media/app-configure-set-up-connection.png "Konfiguruj połączenie")

1. Wybierz opcję **Wprowadź ręcznie**.

    ![Menu ustawień połączenia.](media/app-configure-connection-setup-flyout.png "Menu ustawień połączenia")

    Zostanie wyświetlona strona **Nowe połączenie** z ustawieniami wymaganymi do ręcznego wprowadzania szczegółów połączenia.

    ![Pola połączenia ręcznego.](media/app-configure-input-manually.png "Pola połączenia ręcznego")

1. Podaj poniższe informacje:

    - **Użyj klucza tajnego klienta** — tę opcję należy ustawić na _Tak_, aby do uwierzytelniania za pomocą programu Supply Chain Management był używany klucz tajny klienta. Wartość _Nie_ będzie używana do uwierzytelniania za pomocą certyfikatu. (Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service) wcześniej w tym artykule).
    - **Nazwa połączenia** — wprowadź nazwę nowego połączenia. Ta nazwa będzie wyświetlana w polu **Wybierz połączenie** przy następnym otwarciu ustawień połączenia. Wprowadzana nazwa musi być unikatowa. (Mówiąc inaczej, musi się ona różnić od wszystkich innych nazw połączeń przechowywanych na urządzeniu, jeśli są na nim przechowywane inne nazwy połączeń).
    - **Identyfikator klienta usługi Active Directory** — podaj identyfikator klienta zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).
    - **Klucz tajny klienta usługi Active Directory** — to pole jest dostępne tylko wtedy, gdy opcja **Użyj klucza tajnego klienta** została ustawiona na wartość _Tak_. Wprowadź klucz tajny klienta zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).
    - **Odcisk palca usługi Active Directory** — to pole jest dostępne tylko na urządzeniach z systemem Windows i tylko wtedy, gdy opcja **Użyj klucza tajnego klienta** została ustawiona na wartość _Nie_. Wprowadź odcisk palca certyfikatu zanotowany podczas konfigurowania ustawień usługi Azure AD w sekcji [Tworzenie aplikacji usługi internetowej w usłudze Azure Active Directory](#create-service).
    - **Zasób usługi Active Directory** — określ główny adres URL programu Supply Chain Management.

        > [!IMPORTANT]
        > Tej wartości nie należy kończyć ukośnikiem (/).

    - **Dzierżawa usługi Active Directory** — wprowadź nazwę domeny usługi Azure AD używanej na serwerze programu Supply Chain Management. Ta wartość ma postać `https://login.windows.net/<your-Azure-AD-domain-name>`. Oto przykład: `https://login.windows.net/contosooperations.onmicrosoft.com`. Więcej informacji na temat znajdowania nazwy domeny w usłudze Azure AD można znaleźć w temacie [Lokalizowanie identyfikatorów ważnych dla użytkownika](/partner-center/find-ids-and-domain-names).

        > [!IMPORTANT]
        > Tej wartości nie należy kończyć ukośnikiem (/).

    - **Firma** — wprowadź osobę prawną (firmę) zdefiniowaną w programie Supply Chain Management, z którą ma się łączyć aplikacja.

1. Kliknij przycisk **Zapisz** w prawym górnym rogu strony.
1. Jeśli używasz urządzenia z systemem Android i certyfikatu do uwierzytelniania, urządzenie monituje o wybranie certyfikatu.
1. Aplikacja łączy się z serwerem Supply Chain Management i pokazuje stronę rejestracji.

## <a name="remove-access-for-a-device"></a>Usuwanie dostępu urządzenia

Jeśli urządzenie zostanie zgubione lub dostanie się w niepowołane ręce, należy usunąć z niego dostęp do programu Supply Chain Management. Następujące kroki opisują zalecany proces usuwania dostępu.

1. Przejdź do pozycji **Administrowanie systemem \> Ustawienia \> Aplikacje usługi Azure Active Directory**.
1. Usuń wiersz odpowiadający urządzeniu, z którego chcesz usunąć dostęp. Zanotuj identyfikator klienta, który został użyty dla urządzenia, ponieważ będzie on potrzebny później.

    Jeśli zarejestrowano tylko jeden identyfikator klienta, a wiele urządzeń używa tego samego identyfikatora klienta, musisz wypchnąć nowe ustawienia połączenia na te urządzenia. W przeciwnym razie utracą one dostęp.

1. Zaloguj się do witryny Azure Portal pod adresem [https://portal.azure.com](https://portal.azure.com/).
1. W lewym okienku nawigacyjnym wybierz pozycję **Active Directory** i upewnij się, że jesteś w poprawnym katalogu.
1. Na liście **Zarządzaj** wybierz pozycję **Rejestracje aplikacji**, a następnie wybierz aplikację, którą chcesz skonfigurować. Pojawi się strona **Ustawienia** z informacjami o konfiguracji.
1. Upewnij się, że identyfikator klienta jest zgodny z identyfikatorem klienta zanotowanym w kroku 2.
1. Na pasku narzędzi wybierz pozycję **Usuń**.
1. W wyświetlonym oknie komunikatu potwierdzenia wybierz przycisk **Tak**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Ustawienia użytkownika urządzenia przenośnego](mobile-device-user-settings.md)
- [Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management](step-icons-titles.md)
- [Konfiguracja aplikacji mobilnej Warehouse Management do zarządzania jednostkami skali chmury i brzegowymi](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
