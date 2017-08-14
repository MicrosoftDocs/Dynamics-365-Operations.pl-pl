---
title: Wymagania systemowe
description: "W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń lokalnych i chmurowych."
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: pl-pl
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Wymagania systemowe

[!include[banner](../includes/banner.md)]


W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń chmurowych i lokalnych. Przed zainstalowaniem programu Finance and Operations w razie potrzeby sprawdź, czy system, na którym pracujesz, co najmniej spełnia minimalne wymagania sieciowe, sprzętowe i programowe.


## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office
Następujące aplikacje pakietu Office są obsługiwane we wdrożeniach chmurowych i lokalnych programu Finance and Operations.
-   Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej szczegółów na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Wymagania systemowe specyficzne dla wdrożeń chmurowych
## <a name="network-requirements"></a>Wymagania sieciowe
-   Program Finance and Operations jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych Microsoft Azure zawierającego usługę Finance and Operations. Zaleca się przetestowanie opóźnienia w sieci na stronie <http://www.azurespeed.com>.
-   Wymagania dotyczące przepustowości dla programu Finance and Operations zależą od konkretnego scenariusza. Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s). Jednak dla scenariuszy z dużymi obciążeniami przesyłania danych, takich jak używanie obszarów roboczych czy scenariusze obejmujące rozbudowaną personalizację, zaleca się większą przepustowość sieci.

Ogólnie rzecz biorąc program Finance and Operations jest zoptymalizowany dla Internetu. Liczba rund od klienta przeglądarkowego do centrum danych Azure jest bardzo mała, a wszystkie przesyłane dane są skompresowane. 

> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Dla odbiorców, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, użyj wersji zapoznawczej programu Finance and Operations.

## <a name="net-framework-requirements"></a>Wymagania dotyczące środowiska .NET Framework
Program Finance and Operations wymaga środowiska .NET Framework w wersji 4.6.2 dla wszystkich aplikacji ClickOnce, takich jak agent rozsyłania dokumentów. Instrukcje instalacji znajdują się w temacie [Instalowanie środowiska .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Obsługiwane przeglądarki
Aplikacja internetowa może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:


-   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Google Chrome (najnowsza publicznie dostępna wersja) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10
-   Apple Safari (najnowsze publicznie dostępna wersja) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) albo na iPadzie firmy Apple

Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania. 

> [!NOTE]
> -   Aby umożliwić przechwytywanie obrazów przez Rejestrator zadań i umieszczanie ich w generowanych dokumentach programu Microsoft Word, należy zainstalować wstępną wersję rozszerzenia dla przeglądarki Chrome. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce. Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows). Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.
> -   Projektant raportów dla raportowania finansowego jest uruchamiany jako aplikacji ClickOnce. Wymaga zgodnego 64-bitowego systemu operacyjnego. Jeśli używasz przeglądarki Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta projektanta raportów. Jeśli używasz przeglądarki Chrome w trybie incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb incognito.
> -   Aby wyświetlać podgląd plików PDF, zalecamy używanie przeglądarek takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Obsługiwane przeglądarki dla aplikacji Retail Cloud POS

Aplikacja Retail Cloud POS może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:

-   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Chrom (najnowsza publicznie dostępna wersja) w systemie Windows 10, Windows 8.1 lub Windows 7

## <a name="retail-modern-pos-requirements"></a>Wymagania dotyczące programu Retail Modern POS
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Aplikacja Retail Modern POS jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail Modern POS jest obsługiwana w systemie Windows 10 tylko w wydaniach Pro, Enterprise i Enterprise Long Term Servicing Branch (LTSB).

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

-   Minimalna obsługiwana rozdzielczość wynosi 1280 × 1024 piksele.
-   Komputer, na którym jest uruchamiany program Retail Modern POS, musi spełniać następujące wymagania:
    -   Musi mieć co najmniej dwurdzeniowy procesor o taktowaniu co najmniej 2 gigaherców (GHz).
    -   Musi mieć najmniej 3 gigabajty (GB) pamięci RAM.
    -   Musi mieć dostęp do Internetu.

## <a name="retail-hardware-station-requirements"></a>Wymagania dotyczące programu Retail hardware station
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Aplikacja Retail hardware station jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail hardware station jest obsługiwana w następujących systemach operacyjnych:
    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate 
    
    > [!NOTE]
    > System Windows 7 jest obsługiwany tylko wtedy, jeśli w systemie ręcznie zainstalowano przeglądarkę Internet Explorer 11.

    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

Komputer musi spełniać wszystkie wymagania systemowe dotyczące instalowania i używania następujących składników:

-   Internetowe usługi informacyjne (IIS)
-   Sprzęt innych firm

## <a name="retail-store-scale-unit-requirements"></a>Wymagania dotyczące programu Retail Store Scale Unit
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Aplikacja Retail Store Scale Unit jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail Store Scale Unit jest obsługiwana w następujących systemach operacyjnych:
    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate
    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

-   4 GB pamięci RAM
-   Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

### <a name="recommended-system-requirements"></a>Zalecane wymagania systemowe

-   6 GB pamięci RAM
-   Procesor i7 o szczytowej szybkości każdego rdzenia 2,4 GHz (lub równoważny) (zalecane są cztery rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

## <a name="connector-requirements"></a>Wymagania dotyczące aplikacji łącznika
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Oprogramowanie łącznika systemu Microsoft Dynamics AX ma dwie osobne wersje instalacyjne — **Usługa Async Server Connector** i **Usługa Real-Time service dla systemu Dynamics AX 2012 R3**.
-   Oba składniki są 32-bitowymi aplikacjami, ale będą działały w architekturach x86 i x64.
-   Oba składniki są obsługiwane w następujących systemach operacyjnych:
    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate
    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB
    -   Windows Server 2012 R2, Windows Server 2016

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

-   2 GB pamięci RAM, zalecane 4 GB pamięci RAM
-   Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

## <a name="requirements-for-development-on-local-vms"></a>Wymagania dotyczące instalowania na lokalnych maszynach wirtualnych
Szczegółowe informacje o wymaganiach dotyczących instalowania na lokalnych maszynach wirtualnych (VM) zawiera temat [Maszyny wirtualne uruchamiane lokalnie](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Wymagania systemowe dla wdrożeń lokalnych

## <a name="network-requirements"></a>Wymagania sieciowe
Program Finance and Operations (lokalne wdrożenie) może pracować w sieciach używających protokołu internetowego w wersji 4 (IPv4) lub protokołu internetowego w wersji 6 (IPv6). Podczas planowania systemu należy wziąć pod uwagę środowisko sieciowe oraz postępować według następujących wytycznych.

### <a name="network-response-time"></a>Czas reakcji sieci
Poniższa tabela zawiera listę minimalnych wymagań sieciowych dla połączenia między przeglądarką sieci Web a serwerem obiektów aplikacji (AOS) oraz połączenia między serwerem AOS a bazą danych w lokalnym systemie.

| Wartość     | Od przeglądarki sieci Web do serwera AOS | Od serwera AOS do bazy danych                                            |
|-----------|--------------------|------------------------------------------------------------|
| Przepustowość | 50 kB/s na użytkownika   | 100 MB/s                                                   |
| Opóźnienie   | < 250-300 ms       | < 1 ms (tylko sieć LAN). Serwer AOS i baza danych muszą być w tej samej lokalizacji. |

- Program Finance and Operations (wdrażany lokalnie) jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych zawierającego usługę Finance and Operations.
- Wymagania dotyczące przepustowości dla programu Finance and Operations (lokalnego wdrożenia) zależą od konkretnego scenariusza. Typowe scenariusze wymagają przepustowości ponad 50 kilobajtów na sekundę (kB/s) między przeglądarką a serwerem programu Finance and Operations. Jednak dla scenariuszy z dużymi obciążeniami przesyłania danych, takich jak używanie obszarów roboczych czy scenariusze obejmujące rozbudowaną personalizację, zaleca się większą przepustowość sieci uwzględniającą konkretne zastosowanie.
Nie są obsługiwane wdrożenia, gdzie serwer AOS i baza danych programu SQL Server znajdują się w różnych centrach danych. Serwer AOS i baza danych programu SQL Server muszą być w tej samej lokalizacji. Ogólnie rzecz biorąc program Finance and Operations jest zoptymalizowany do ograniczania rund komunikacji między przeglądarką a serwerem. Liczba rund od klienta przeglądarkowego do centrum danych wynosi zero lub jeden dla każdej interakcji z użytkownikiem, a wszystkie przesyłane dane są skompresowane.

> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Zalecamy używanie realistycznej symulacji w nieprodukcyjnym środowisku programu Finance and Operations jako najlepszego miernika wydajności w konkretnym przypadku. 

### <a name="lan-environments"></a>Środowiska LAN
W środowiskach sieci lokalnych (LAN) narzędzie Pulpit zdalny Microsoft zawarte w systemie Microsoft Windows Server nie jest konieczne do nawiązywania połączenia z programem Finance and Operations. Niemniej jednak może być wymagane do operacji serwisowania na maszynach wirtualnych tworzących wdrożenie serwera.

### <a name="wan-environments"></a>Środowiska WAN
W środowiskach sieci rozległych (WAN) narzędzie Pulpit zdalny zawarte w systemie Windows Server nie jest konieczne do nawiązywania połączenia z programem Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Wymagania dotyczące łączności z Internetem
Program Finance and Operations (lokalne wdrożenie) nie wymaga, aby stacje robocze użytkowników końcowych miały połączenie z Internetem. Jednak niektóre funkcje nie będą dostępne bez połączenia internetowego.

| Klient przeglądarkowy | Scenariusz intranetowy bez łączności z Internetem jest aspektem projektowym w opcji wdrożenia lokalnego. Niektóre funkcje wymagające usług chmurowych, takich jak Pomoc i biblioteki przewodników po zadaniach w usłudze LCS, nie będą dostępne. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Serwer         | Warstwa serwera AOS lub platformy Service Fabric musi być w stanie komunikować się z usługą LCS. Lokalny klient przeglądarkowy nie wymaga dostępu do Internetu.                                                                                |
| Telemetria      | W przypadku długich przerw w łączności mogą zostać utracone dane telemetryczne. Przerwy w łączności z usługą LCS nie wpływają na funkcjonalność lokalnych aplikacji.                                                |
| Usługa LCS            | Łączność z usługą LCS jest wymagana do wdrożenia programu, wdrożenia kodu źródłowego i czynności serwisowych.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Przesyłanie danych telemetrycznych do chmury
Większość danych telemetrycznych jest przechowywanych lokalnie i można uzyskać do nich dostęp za pomocą narzędzia Podgląd zdarzeń w systemie Microsoft Windows. Niewielki podzbiór zdarzeń telemetrycznych jest przekazywany do procesu telemetrii Microsoft w chmurze w celach diagnostycznych. Dane klientów i dane użytkowników końcowych umożliwiające identyfikację konkretnych osób nie są częścią danych telemetrycznych wysyłanych do firmy Microsoft. Nazwy maszyn wirtualnych są wysyłane do firmy Microsoft, aby pomóc w zarządzaniu środowiskami i diagnostyce z poziomu portalu LCS.

## <a name="domain-requirements"></a>Wymagania dotyczące domen
Podczas instalowania programu Finance and Operations (lokalnie) należy wziąć pod uwagę następujące wymagania dotyczące domen:

- Maszyny wirtualne zawierające składniki programu Finance and Operations (lokalnego wdrożenia) muszą należeć do domeny usługi Active Directory. Usługa Active Directory Domain Services (AD DS) musi być skonfigurowana w trybie natywnym.
- Maszyny wirtualne, na których są uruchomione składniki programu Finance and Operations (lokalnego wdrożenia), muszą mieć skonfigurowany wzajemny dostęp w usłudze Active Directory Domain Services. 
- Kontroler domeny musi być wyposażony w system Microsoft Windows Server 2016.

## <a name="hardware-requirements"></a>Wymagania sprzętowe
W tym rozdziale opisano sprzęt wymagany do obsługi programu Finance and Operations (lokalnego wdrożenia).
Faktyczne wymagania sprzętowe różnią się w zależności od konfiguracji systemu, składu danych oraz aplikacji i funkcji, które mają być używane. Poniżej wymieniono kilka czynników, które mogą wpłynąć na dobór sprzętu dla programu Finance and Operations (lokalnego wdrożenia):

- Liczba transakcji na godzinę.
- Liczba równocześnie aktywnych użytkowników.

## <a name="minimum-infrastructure-requirements"></a>Minimalne wymagania w zakresie infrastruktury
Program Finance and Operations (lokalne wdrożenie) wykorzystuje platformę Microsoft Azure Service Fabric do obsługi usług serwera AOS, zadań wsadowych, zarządzania danymi, Management Reporter i Environment Orchestrator. W klastrze platformy Service Fabric nie ma usługi Microsoft SQL Server Reporting Services (SSRS).
Program SQL Server musi być skonfigurowany w układzie wysokiej dostępności HADRON, który ma co najmniej dwa węzły z przeznaczeniem produkcyjnym.
Poniższa ilustracja przestawia zalecaną minimalną liczbę węzłów w klastrze usługi Service Fabric.

[![zalecana liczba węzłów dla klastra usługi service fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Wymagania dotyczące procesorów i pamięci RAM
W poniższej tabeli podano liczbę procesorów i ilość pamięci o dostępie swobodnym (RAM), jakie są wymagane dla każdej roli koniecznej w tej opcji wdrożenia. Aby uzyskać więcej informacji, przeczytaj zalecane minimalne wymagania dla samodzielnego klastra platformy Service Fabric opisane w temacie [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Jeśli na tym samym komputerze jest zainstalowane inne oprogramowanie firmy Microsoft, system musi również spełniać wymagania sprzętowe związane tego oprogramowania. Zalecamy, aby inne aplikacje serwerowe na tym samym komputerze, na którym działa serwer AOS, wykorzystywały maksymalnie 1 gigabajt (GB) pamięci RAM.

**Szacowane zapotrzebowanie na elementy infrastruktury według roli i typu topologii**

| Topologia   | Rola (typ węzła)              | Zalecana liczba rdzeni procesora | Zalecana ilość pamięci (GB) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Produkcja | Serwer obiektów aplikacji, zarządzanie danymi, zadania wsadowe   | 8                           | 24                      |
|            | Program Management Reporter           | 4                           | 16                      |
|            | usługi SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |
| Piaskownica    | Serwer obiektów aplikacji, zarządzanie danymi, zadania wsadowe   | 4                           | 24                      |
|            | Program Management Reporter           | 4                           | 16                      |
|            | usługi SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |

**Minimalne szacowane zapotrzebowanie na elementy infrastruktury dla wdrożeń produkcyjnych i piaskownicy**\*

| Topologia                                  | Rola                          | Liczba wystąpień |
|-------------------------------------------|-------------------------------|---------------------|
| Produkcja                                | Serwer obiektów aplikacji (zarządzanie danymi, zadania wsadowe)  | 3                   |
|                                           | Program Management Reporter           | 2                   |
|                                           | usługi SQL Server Reporting Services | 1                   |
|                                           | Orchestrator\*\*                | 3                   |
| Piaskownica                                   | Serwer obiektów aplikacji, zarządzanie danymi, zadania wsadowe   | 2                   |
|                                           | Program Management Reporter           | 1                   |
|                                           | usługi SQL Server Reporting Services | 1                   |
|                                           | Orchestrator                  | 3                   |
| *Sumarycznie topologie produkcyjna i piaskownicy* |                               | 16                  |

\*Te liczby są obecnie weryfikowane przez naszych klientów używających wersji zapoznawczych i na podstawie informacji zwrotnych mogą zostać skorygowane.

\*\*Orchestrator jest wyznaczony jako główny typ węzła i będzie używany również do uruchamiania usług platformy Service Fabric.

**Wstępne szacunki dotyczące programu SQL Server działającego w systemach zaplecza i usługi AD**

[![Wstępne szacunki dotyczące programu SQL Server działającego w systemach zaplecza i usługi AD](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*Parametry komputerów z programem SQL Server mocno zależą od obciążeń pracą. Aby uzyskać więcej informacji, zobacz rozdział [Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych](#Hardware-sizing-for-on-premises-environments).

## <a name="storage"></a>Magazynowanie

- **Serwer AOS** — program Finance and Operations (w lokalnym wdrożeniu) będzie używał udziału bloku komunikatów serwera (SMB) w wersji 3.0 do przechowywania nieuporządkowanych danych. Aby uzyskać więcej informacji, zobacz [Bezpośrednie miejsca do magazynowania w systemie Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** — Dostępne opcje:
    - Konfiguracja o wysokiej dostępności z dyskiem półprzewodnikowym (SSD).
    - Sieć magazynowania (SAN) zoptymalizowana pod kątem przepustowości protokołu OLTP.
    - Konfiguracja o dużej wydajności z pamięcią masową dołączaną bezpośrednio (DAS). 
- **Liczna operacji we/wy na sekundę w programie SQL i podczas zarządzania danymi** — Pamięć masowa dla zarządzania danymi i programu SQL Server powinna obsługiwać co najmniej 2000 operacji we/wy na sekundę (IOPS). Wskaźnik IOPS w środowisku produkcyjnym zależy od wielu czynników. Aby uzyskać więcej informacji, zobacz rozdział „Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych”. 
- **Liczba operacji we/wy na sekundę na maszynach wirtualnych** — Każda maszyna wirtualna powinna obsługiwać co najmniej 100 operacji zapisu we/wy na sekundę.

## <a name="virtual-host-requirements"></a>Wymagania dotyczące hostów wirtualnych
Podczas konfigurowania hostów wirtualnych dla środowiska Finance and Operations (wdrożenia lokalnego) zapoznaj się z następującymi wytycznymi: [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) oraz [Opisu klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Każdy host wirtualny powinien mieć wystarczającą liczbę rdzeni dla szacowanego zapotrzebowania na elementy infrastruktury. Jest możliwych wiele zaawansowanych konfiguracji, gdzie program SQL Server znajduje się na fizycznym urządzeniu, a wszystkie inne składniki są zwirtualizowane. Jeśli program SQL Server jest zwirtualizowany, podsystem dysku powinien mieć konfigurację szybkiej sieci magazynowania (SAN) lub równoważną. We wszystkich przypadkach upewnij się, że podstawowa konfiguracja hosta wirtualnego jest wysoce dostępna i nadmiarowa. We wszystkich przypadkach podczas stosowania wirtualizacji nie należy wykonywać migawek maszyn wirtualnych.

## <a name="software-requirements-for-all-server-computers"></a>Wymagania programowe dla wszystkich komputerów serwerów
Następujące oprogramowanie musi się znajdować na komputerze, zanim będzie można zainstalować jakiekolwiek składniki programu Finance and Operations (lokalnego wdrożenia):

- Microsoft .NET Framework w wersji 4.5.1 lub nowszej
- Service Fabric Aby uzyskać więcej informacji, zobacz [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Obsługiwane serwerowe systemy operacyjne
W poniższej tabeli wymieniono serwerowe systemy operacyjne, które są obsługiwane przez składniki środowiska Finance and Operations.

| System operacyjny                                     | Notatki                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Datacenter lub Standard | Te wymagania dotyczą bazy danych i klastra usługi Service Fabric zawierającego serwer obiektów aplikacji. |

## <a name="software-requirements-for-database-servers"></a>Wymagania programowe dla serwerów baz danych

- Obsługiwane są tylko 64-bitowe wersje programu SQL Server 2016.
- W środowisku produkcyjnym zaleca się, aby zainstalować najnowszą aktualizację zbiorczą (CU) dla używanej wersji programu SQL Server.
- Program Finance and Operations (lokalne wdrożenie) obsługuje sortowanie w formacie Unicode, które ignoruje wielkości liter, uwzględnia akcenty, uwzględnia znaki kana i ignoruje szerokość. Sortowanie musi być zgodne z ustawieniami regionalnymi systemu Windows na komputerach zawierających wystąpienia serwera AOS. Jeśli konfigurujesz nową instalację, zalecamy wybranie sortowania systemu Windows zamiast sortowania programu SQL Server. Aby uzyskać więcej informacji na temat wybierania sposobu sortowania dla bazy danych programu SQL Server, zobacz [Dokumentacja programu SQL Server](/sql/sql-server/sql-server-technical-documentation).
W poniższej tabeli wymieniono wersje programu SQL Server, które są obsługiwane przez bazy danych środowiska Finance and Operations. Aby uzyskać więcej informacji, zobacz minimalne wymagania sprzętowe dla programu [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Zapotrzebowanie                                                      | Notatki                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition lub Enterprise Edition | Aby zapoznać się z wymaganiami sprzętowymi programu SQL Server 2016, zobacz [Wymagania sprzętowe i programowe dla instalacji programu SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>Wymagania programowe dla komputerów klienckich
Aplikacja sieci web Finance and Operations może być uruchamiana na dowolnym urządzeniu z przeglądarką sieci web zgodną ze standardem HTML5.0. Konkretne kombinacje urządzeń/przeglądarek potwierdzone przez Microsoft obejmują m.in.:

- Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
- Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
- Google Chrome (najnowsza publicznie dostępna wersja) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10
- Apple Safari (najnowsze publicznie dostępna wersja) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) albo na iPadzie firmy Apple

## <a name="software-requirements-for-active-directory-federation-services"></a>Wymagania programowe dla usługi Active Directory Federation Services 
Active Directory Federation Services (AD FS) w środowisku Windows Server 2016

Kontroler domeny musi zawierać system Windows Server 2012 R2 lub nowszy z poziomem funkcjonalności domeny 2012 R2 lub wyższym

Aby uzyskać więcej informacji na temat poziomów funkcjonalnych domen, zobacz: 
- [Co to są poziomy funkcjonalności w usłudze Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Omówienie poziomów funkcjonalności w usłudze Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Wymagania sprzętowe i programowe dla składników sprzedaży detalicznej
Program Finance and Operations (lokalne wdrożenie) obecnie nie zawiera żadnych składników sprzedaży detalicznej.

<a name="see-also"></a>Informacje dodatkowe
--------

[Pobieranie kopii ewaluacyjnej programu Dynamics 365 for Finance and Operations Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

