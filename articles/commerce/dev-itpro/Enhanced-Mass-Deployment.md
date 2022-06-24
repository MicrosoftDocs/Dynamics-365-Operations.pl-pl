---
title: Masowe wdrażanie zapieczętowanych składników samoobsługi rozwiązania Commerce
description: W tym artykule opisano, jak używać struktury dla instalatorów składników samoobsługowych do instalacji dyskretnych i wdrożeń usług.
author: jashanno
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: a679d78db3ad5bd9cccbd4ab6a7026bd07890f55
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898586"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Masowe wdrażanie zapieczętowanych składników samoobsługi rozwiązania Commerce

[!include [banner](../includes/banner.md)]

Ten artykuł dotyczy uszczelnionych ram, instalatorów komponentów, które są wydawane co miesiąc, począwszy od wersji 10.0.18, i które są udostępniane w bibliotece Shared asset w usłudze Microsoft Dynamics Lifecycle Services (LCS). Należy zwrócić uwagę, że pierwszych kilka wersji tych nowych instalatorów jest oznaczonych jako **(Wersja zapoznawcza)**. Jednak jedynym celem tego przeznaczenia jest rozróżnianie nowych instalatorów, podczas gdy firma Microsoft określa, czy istnieją dodatkowe wymagania dotyczące ich funkcji. Nie oznacza to, że instalatorzy nie są prawidłowi dla produkcji. Zgodnie z wydaniami tych nowych instalatorów firma Microsoft planuje przestać starszych (starszych) instalatorów w lub w końca październiku 2023 roku. 

W tym artykule wyjaśniono, jak używać nowych instalatorów do wykonywania instalacji dyskretnej i obsługi aktualizacji przy użyciu argumentów wiersza polecenia. Argumenty te pozwalają na masowe rozmieszczanie na kilka sposobów.

> [!NOTE]
> Nowy samoobsługowy, zapieczętowany instalator nie będzie dostępny w programie Headquarters i będzie można go pobrać tylko za pośrednictwem usługi LCS.

## <a name="delimiters-for-mass-deployment"></a>Ograniczniki masowego wdrażania

W poniższej tabeli przedstawiono ograniczniki, których można użyć w wykonaniu wiersza polecenia.


| Separator                 | Opis |
|---------------------------|-------------|
| --AadTokenIssuerPrefix | Prefiks dla wystawcy tokena Microsoft Azure Active Directory (Azure AD). |
| --AsyncClientAadClientId | Identyfikator Azure AD klienta, którego usługi Async Client powinny używać podczas komunikacji z programem Headquarters. |
| --AsyncClientAppInsightsInstrumentationKey | Klucz instrumentacji interfejsu Async Client AppInsights. |
| --AsyncClientCertFullPath | W pełni sformatowana ścieżka URN, która używa odcisku palca jako metryki wyszukiwania lokalizacji certyfikatu usługi Async Client Identity, która powinna być używana do uwierzytelniania w komunikacji Azure AD z programem Headquarters. Jest to na przykład `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` poprawnie sformatowany adres URL. Wartość **\<MyThumbprint\>** zostanie zastąpiona odciskiem palca certyfikatu, który ma być używany. Nie należy używać tego parametru razem z parametrem **-AsyncClientCertThumbprint**. |
| --AsyncClientCertThumbprint | Odcisk palca certyfikatu usługi Async Client Identity, który powinien być używany do uwierzytelniania w celu komunikacji Azure AD z programem Headquarters. Ten odcisk palca zostanie użyty do przeszukania lokalizacji i nazwy **LocalMachine/My store**, aby znaleźć właściwy certyfikat do użycia. Nie należy używać tego parametru razem z parametrem **-AsyncClientCertFullPath**. |
| --ClientAppInsightsInstrumentationKey | Klucz instrumentacji interfejsu Client AppInsights. |
| --CloudPosAppInsightsInstrumentationKey | Klucz instrumentacji Cloud POS AppInsights. |
| --Konfiguracja | Plik konfiguracji, który powinien być używany podczas instalacji. Przykładem nazwy pliku jest **Contoso.CommerceScaleUnit.xml**. |
| --CposAadClientId | Identyfikator Azure AD klienta, który ma być używać w programie Cloud POS podczas aktywacji urządzenia. Ten parametr nie jest wymagany dla wdrożeń lokalnych. |
| --Urządzenie | Identyfikator urządzenia wyświetlany na stronie **Urządzenia** w programie Headquarters. |
| --EnvironmentId | Identyfikator środowiska. |
| --HardwareStationAppInsightsInstrumentationKey | Klucz instrumentacji aplikacji Hardware Station AppInsights. |
| --Zainstaluj | Parametr określający, czy powinien być zainstalowany składnik dostarczany przez tego instalatora. Ten parametr nie jest wymagany. |
| --InstallOffline | W przypadku programu Modern POS ten parametr określa także, że baza danych w trybie offline powinna być także zainstalowana i skonfigurowana. Użyj również parametru **-SQLServerName**. W przeciwnym razie Instalator spróbuje znaleźć domyślne wystąpienie spełniające wymagania wstępne. |
| --Port | Port, który powinien być skojarzony z katalogiem wirtualnym programu Retail Server i używany przez ten katalog. Jeśli żaden port nie zostanie ustawiony, zostanie użyty port domyślny 443. |
| --Kasa | Identyfikator rejestru wyświetlany na stronie **Rejestry** w programie Headquarters. |
| --RetailServerAadClientId | Identyfikator Azure AD klienta, którego usługi Retail Server powinny używać podczas komunikacji z programem Headquarters. |
| --RetailServerAadResourceId | Identyfikator zasobu aplikacji Retail Server Azure AD, który powinien być używany podczas aktywacji urządzenia. Ten parametr nie jest wymagany dla wdrożeń lokalnych. |
| --RetailServerCertFullPath | W pełni sformatowana ścieżka URN, która używa odcisku palca jako metryki wyszukiwania certyfikatu usługi Retail Server Identity, która powinna być używana do uwierzytelniania w komunikacji Azure AD z programem Headquarters. Na przykład `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` to poprawnie sformatowany URN, w którym wartość **\<MyThumbprint\>** zostanie zastąpiona odciskiem palca certyfikatu, którego należy użyć. Nie należy używać tego parametru razem z parametrem **-RetailServerCertThumbprint**. |
| --RetailServerCertThumbprint | Odcisk palca certyfikatu usługi Retail Server Identity, który powinien być używany do uwierzytelniania w celu komunikacji Azure AD z programem Headquarters. Ten odcisk palca zostanie użyty do przeszukania lokalizacji i nazwy **LocalMachine/My store**, aby znaleźć właściwy certyfikat do użycia. Nie należy używać tego parametru razem z parametrem **-RetailServerCertFullPath**. |
| --RetailServerURL | Adres URL usługi Retail Server, który powinien być użyciu przez Instalatora. (Ten adres URL jest również znany jako adres URL Commerce Scale Unit \[CSU\]). W przypadku Modern POS ta wartość będzie używana podczas aktywacji urządzenia. |
| --SkipAadCredentialsCheck| Przełącznik wskazujący, czy sprawdzanie wstępnie wymaganego poświadczenia Azure AD powinno zostać pominięte. Domyślna wartość to **false**. |
| --SkipCertCheck | Przełącznik wskazujący, czy należy pominąć sprawdzanie wymagań wstępnych certyfikatu. Domyślna wartość to **false**. |
| --SkipIisCheck | Przełącznik wskazujący, czy należy pominąć sprawdzanie wymagań wstępnych Internetowych usług informacyjnych (IIS). Domyślna wartość to **false**. |
| --SkipNetFrameworkCheck | Przełącznik wskazujący, czy należy pominąć sprawdzanie wymagań wstępnych .NET Framework. Domyślna wartość to **false**. |
| --SkipScaleUnitHealthcheck | Przełącznik wskazujący, czy sprawdzanie kondycji zainstalowanych składników powinno zostać pominięte. Domyślna wartość to **false**. |
| --SkipSChannelCheck | Przełącznik wskazujący, czy należy pominąć sprawdzanie wymagań wstępnych bezpiecznego kanału. Domyślna wartość to **false**. |
| --SkipSqlFullTextCheck | Przełącznik wskazujący, czy należy pominąć sprawdzanie poprawności wymagania wstępnego programu SQL Server wymagającego wyszukiwania pełnotekstowego. Domyślna wartość to **false**. |
| --SkipSqlServerCheck | Przełącznik wskazujący, czy należy pominąć sprawdzanie wymagań wstępnych SQL Server. Domyślna wartość to **false**. |
| --SqlServerName | Nazwa serwera SQL. Jeśli ta nazwa nie jest określona, Instalator spróbuje znaleźć domyślne wystąpienie. |
| --SslcertFullPath | W pełni sformatowana ścieżka URN, która używa odcisku palca jako metryki wyszukiwania lokalizacji certyfikatu, która powinna być używana do szyfrowania ruchu HTTP w jednostce skali. Na przykład `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` to poprawnie sformatowany URN, w którym wartość **\<MyThumbprint\>** zostanie zastąpiona odciskiem palca certyfikatu, którego należy użyć. Nie należy używać tego parametru razem z parametrem **-SslCertThumbprint**. |
| --SslCertThumbprint | Odcisk palca certyfikatu, który powinien być używany do szyfrowania ruchu HTTP w jednostce skalowania. Ten odcisk palca zostanie użyty do przeszukania lokalizacji i nazwy **LocalMachine/My store**, aby znaleźć właściwy certyfikat do użycia. Nie należy używać tego parametru razem z parametrem **-SslCertFullPath**. |
| --StoreSystemAosUrl | Adres URL Headquarters (AOS). |
| --StoreSystemChannelDatabaseId | Identyfikator bazy danych kanału (nazwa). |
| --TenantId | Identyfikator dzierżawy Azure AD. |
| --TransactionServiceAzureAuthority | Urząd usługi Transaction Service Azure AD. |
| --TransactionServiceAzureResource | Zasób usługi Transaction Service Azure AD. |
| --TrustSqlServerCertificate | Przełącznik wskazujący, czy certyfikat serwera powinien być zaufany podczas nawiązywania połączenia z programem SQL Server. Aby uniknąć zagrożeń bezpieczeństwa, wdrożenia produkcyjne nigdy nie powinny dostarczać tutaj wartości **true**. Domyślna wartość to **false**. |
| --Verbosity | Poziom rejestrowania wymagany podczas instalacji. Zazwyczaj ta wartość nie powinna być używana. |
| --WindowsPhoneAppInsightsInstrumentationKey | Klucz instrumentacji aplikacji Hardware Station AppInsights. |

## <a name="general-overview"></a>Przegląd ogólny

Nowa platforma dla instalatorów samoobsługowych ma różne funkcje i ulepszenia. Nowa konfiguracja obecnie generuje instalatorów tylko dla programu Modern POS, stacji sprzętowej i serwera CSU (obsługiwanego samodzielnie). Ważne jest, aby zrozumieć podstawowe użycie wiersza polecenia przez zapieczętowanych instalatorów, które powinno wyglądać podobnie do używanego w poniższym przykładzie. 
 
```Console
<Component Installer Name>.exe install --<Parameter Name> "<Parameter Information>"
```

Instalator wymaga **zainstalowania** (lub **odinstalowania**) parametrów oraz wszystkich parametrów specyficznych dla tej instalacji. **Parametr Nazwa powinien** zawierać wszelkie potrzebne parametry, takie jak rejestr, adres URL CSU lub informacje o certyfikacie. **Parametr Informacje** powinien zawierać wszelkie dodatkowe informacje o parametrach.

Zapieczętowana tabela została utworzona w celu umożliwienia następujących modyfikacji:
- **Zapieczętowana** — nowa framework instalatora całkowicie oddziela instalatorów składników podstawowych dystrybuowanych przez firmę Microsoft od dostosowań opartych na możliwościach rozszerzania. Dostosowania będą instalowane później, ale zostaną wówczas odblokowane w odniesieniu do aktualizacji (tak, aby aktualizacje mogły być dozwolone tylko dla składnika podstawowego firmy Microsoft, tylko dla dostosowań lub dla obu tych elementów).
- **Bez GUI** – nie ma już interfejsu użytkownika (UI). Zamiast tego dla każdego instalatora składników istnieje całkowicie sterowany wiersz polecenia plik wykonywalny. Ta zmiana jest jedną z kilku kluczowych zmian lub funkcji używanych do skoncentrowania nowej struktury instalatora na korzystanie z funkcji masowego wdrażania.
- **Logowanie bardziej zaawansowane** — rozszerzone dzienniki instalatora umożliwiają lepszą weryfikację ukończenia lub niepowodzenia instalacji, wykonanych kroków oraz wygenerowanych ostrzeżeń lub błędów.
- **Oczyszczanie** — W nowej struktury instalatorzy składników działają zgodnie z zachowaniem oczyszczania katalogów instalacyjnych, czyszcząc pełną zawartość folderu składników przed zainstalowaniem nowych składników. Dzięki temu żadne pliki nie zostaną pozostawione, co może spowodować problemy lub uniemożliwić pomyślną instalację.

Do nowej struktury nie zostały przeniesione trzy składniki: wirtualny symulator urządzeń peryferyjnych, usługa Async Server Connector Service (używana w przypadku obsługi systemu Dynamics AX 2012 R3) oraz zamiennik usługi Real-time Service (używane dla obsługi systemu Dynamics AX 2012 R3).

> [!NOTE]
> Instalatorzy są przechowywani lokalnie i zachowywani.  Z czasem ważne jest, aby zarządzać zatrzymanymi instalatorami lub usuwać je, aby nie zużyto miejsca na dysku. Zaleca się, aby zachować bieżącego instalatora dla składników podstawowych i wszystkich instalatorów rozszerzeń w najnowszej wersji, aby zachować odzyskiwanie w wyjątkowoj sytuacji.

## <a name="migration"></a>Migracja

Migracja ze starych instalatorów składników struktury samoobsługowej do nowych instalatorów składników struktury wymaga odinstalowania starych składników.

- **Modern POS** – Nowa framework Instalatora spowodowała, że aplikacja otrzymuje nowy identyfikator podpisu aplikacji. Dlatego przed zainstalowaniem nowego składnika Programu Modern POS jest wymagane pełne odinstalowywanie starych składników. Z powodu wymagania dotyczącego pełnego odinstalowywania aktywacja urządzenia będzie wymagana ponownie. (Ponowna aktywacja urządzenia jest wymaganiem czasowym, pod warunkiem, że odinstalowywanie nie nastąpi ponownie)
- **Stacja sprzętowa** – Nowa struktura instalatora, jako witryna sieci web usług IIS, wymaga przeróbki struktury folderu podstawowego. Dlatego przed zainstalowaniem nowego składnika stacji sprzętowej frameworku wymagana jest pełna dezinstalacja starych składników.
- **Jednostka skalowania Commerce Scale Unit (CSU, hostowane samodzielnie)** — jako serii witryn sieci Web usług IIS nowa struktura Instalatora wymaga przeróbki struktury folderu podstawowego.  W związku z tym przed zainstalowaniem nowego składnika CSU (hostingu własnego) wymagana jest pełna dezinstalacja starych składników.

## <a name="modern-pos"></a>Modern POS

### <a name="before-you-begin"></a>Przed rozpoczęciem

Bardzo ważne jest usunięcie starego, samoobsługowego składnika programu Modern POS. Aby uzyskać więcej informacji, zobacz kroki migracji we wcześniejszej części tego artykułu.

### <a name="examples-of-silent-deployment"></a>Przykłady wdrożenia w trybie dyskretnym

W tej sekcji pokazano przykłady poleceń używanych do instalowania programu Modern POS.

#### <a name="silently-install-modern-pos"></a>Po cichu zainstaluj Modern POS

Następujące polecenie w trybie dyskretnym instaluje (lub aktualizuje) program Modern POS. Zawiera standardową strukturę poleceń, która jest używana do dyskretnego obsługi aktualnie zainstalowanych składników. W strukturze są używane wartości podstawowe **&lt;InstallerName&gt;.exe**.

W przypadku wniosku o instalację poniższe podstawowe polecenia mają dostęp do dostępnych opcji. Zdecydowanie zaleca się, aby to polecenie było używane podczas pierwszego testowania lub używania Instalatora.

```Console
CommerceModernPOS.exe --help install
```

> [!NOTE]
> Plik konfiguracji nie jest wymagany dla programu Modern POS. Instalator ma teraz parametry (pokazane wcześniej w tym artykule) dla różnych wartości, które są używane podczas aktywacji urządzenia.

Poniższe polecenie określa wszystkie parametry, które powinny być używane podczas aktywacji urządzenia po zainstalowaniu aplikacji Modern POS. W tym przykładzie jest używana **Houston-3**, która jest powszechnie używaną wartością w danych demonstracyjnych Dynamics 365 Commerce.

```Console
CommerceModernPOS.exe install --Register "Houston-3" --Device "Houston-3" --RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

Poniższe polecenie określa parametry, które powinny być używane do instalowania i konfigurowania bazy danych offline. Program SQL Server jest określony razem z plikiem konfiguracji, który ma być używany.

```Console
CommerceModernPOS.exe install --InstallOffline --SQLServerName "SQLExpress" --Config "ModernPOS.Houston-3.xml"
```

Te pojęcia można łączyć w celu uzyskania pożądanego wyniku instalacji.

## <a name="hardware-station"></a>Stacja sprzętowa

### <a name="before-you-begin"></a>Przed rozpoczęciem

Bardzo ważne jest, aby usunąć stary składnik samoobsługowej stacji sprzętowej. Aby uzyskać więcej informacji, zobacz kroki migracji we wcześniejszej części tego artykułu. Nie istnieje już narzędzie do informacji o kontach handlowców. W zamian informacje o koncie handlowca są instalowane podczas parowania terminalu w programie POS ze stacją sprzętową. Podczas testowania tego instalatora po raz pierwszy zdecydowanie zaleca się uruchomienie następującego polecenia:

```Console
CommerceHardwareStation.exe --help install
```

### <a name="examples-of-silent-deployment"></a>Przykłady wdrożenia w trybie dyskretnym

W tej sekcji przedstawiono przykłady poleceń używanych do instalacji stacji sprzętowej.

#### <a name="silently-install-hardware-station"></a>Po cichu zainstaluj stację sprzętową

Następujące polecenie dyskretnie instaluje (lub aktualizuje) stację sprzętową. Ma standardową strukturę poleceń, która służy do obsługi aktualnie zainstalowanych komponentów. W strukturze są używane wartości podstawowe **&lt;InstallerName&gt;.exe**.

Następujące polecenie podstawowe uruchamia Instalatora plików wykonywalnych.

```Console
HardwareStation.exe install --Port 443 --StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" --StoreSystemChannelDatabaseID "Houston" --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> Plik konfiguracyjny nie jest wymagany dla stacji sprzętowej. Instalator ma teraz parametry (pokazane wcześniej w tym artykule) dla różnych wymaganych wartości.

Poniższe polecenie określa wszystkie parametry wymagane do pomijania testów wymagań wstępnych podczas standardowej instalacji. 

> [!NOTE]
> Pomijanie czeków nie jest zalecane bez konieczności szczegółowego testowania przed terminem lub w sytuacjach programisty.

```Console
HardwareStation.exe install --SkipFirewallUpdate --SkipOPOSCheck --SkipVersionCheck --SkipURLCheck --Config "HardwareStation.Houston.xml"
```

Jak zwykle, często łączy się i dopasowuje te koncepcje, aby uzyskać pożądane wyniki instalacji.

## <a name="commerce-scale-unit-self-hosted"></a>Architektura Commerce Scale Unit (własny serwer)

Podczas testowania tego instalatora po raz pierwszy zdecydowanie zaleca się uruchomienie następującego polecenia:

```Console
CommerceStoreScaleUnitSetup.exe --help install
```

### <a name="before-you-begin"></a>Przed rozpoczęciem

Bardzo ważne jest, aby usunąć stary samoobsługowy składnik CSU (samoobsługowy). Aby uzyskać więcej informacji, zobacz kroki migracji we wcześniejszej części tego artykułu.

### <a name="examples-of-silent-deployment"></a>Przykłady wdrożenia w trybie dyskretnym

W tej sekcji przedstawiono przykłady poleceń używanych do instalowania jednostki CSU (obsługiwanej samodzielnie).

#### <a name="silently-install-csu-self-hosted"></a>Instalowanie w trybie dyskretnym csu (obsługiwanego samodzielnie)

Następujące polecenie dyskretnie instaluje (lub aktualizuje) CSU (samohostowany). Zawiera standardową strukturę poleceń, która jest używana do dyskretnego obsługi aktualnie zainstalowanych składników. W strukturze są używane wartości podstawowe **&lt;InstallerName&gt;.exe**.

W porównaniu z innymi instalatorami sklepu internetowego jednostka skalowania Commerce Scale Unit (CSU) jest bardziej złożona i wymaga zbyt dużej ilości dodatkowych informacji. Następujące polecenie stanowi polecenie minimum (z parametrami) potrzebne do uruchomienia Instalatora plików wykonywalnych, gdy brak pliku konfiguracji.

```Console
CommerceScaleUnit.exe install --port 446 --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> Plik konfiguracji jest nadal wymagany dla csu (obsługiwanego samodzielnie).

Następujące polecenie jest bardziej dokładne i zawiera instalatora plików wykonywalnych z alternatywnymi parametrami.

```Console
CommerceScaleUnit.exe install --Port 446 --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Verbosity 0 --Config "Contoso.StoreSystemSetup.xml"
```

Poniższe polecenie określa wszystkie parametry wymagane do pomijania testów wymagań wstępnych podczas standardowej instalacji. 

> [!NOTE]
> Pomijanie czeków nie jest zalecane bez konieczności szczegółowego testowania przed terminem lub w sytuacjach programisty.


```Console
CommerceScaleUnit.exe installer --skipscaleunithealthcheck --skipcertcheck --skipaadcredentialscheck --skipschannelcheck --skipiischeck --skipnetcorebundlecheck --skipsqlservercheck --skipnetframeworkcheck --skipversioncheck --skipurlcheck --Config "Contoso.StoreSystemSetup.xml" --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate
```

Te pojęcia można łączyć w celu uzyskania pożądanego wyniku instalacji.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
