---
title: "Wymagania systemowe dla wdrożeń lokalnych"
description: "W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń lokalnych."
author: kfend
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 25a6f326c57e84d6a7c356ac5407be7ed3095f83
ms.openlocfilehash: 5edc6f0b2240e9dd2d3b72a13f35e96f016aa013
ms.contentlocale: pl-pl
ms.lasthandoff: 10/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Wymagania systemowe dla wdrożeń lokalnych

[!include[banner](../includes/banner.md)]

W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń lokalnych. Przed zainstalowaniem programu Finance and Operations w razie potrzeby sprawdź, czy system, na którym pracujesz, co najmniej spełnia minimalne wymagania sieciowe, sprzętowe i programowe.

## <a name="network-requirements"></a>Wymagania sieciowe
Program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lokalne wdrożenie) może pracować w sieciach używających protokołu internetowego w wersji 4 (IPv4) lub protokołu internetowego w wersji 6 (IPv6). Podczas planowania systemu należy wziąć pod uwagę środowisko sieciowe oraz postępować według następujących wytycznych.

### <a name="network-response-time"></a>Czas reakcji sieci
Poniższa tabela zawiera listę minimalnych wymagań sieciowych dla połączenia między przeglądarką sieci Web a serwerem obiektów aplikacji (AOS) oraz połączenia między serwerem AOS a bazą danych w lokalnym systemie.

| Wartość     | Od przeglądarki sieci Web do serwera AOS                      | Od serwera AOS do bazy danych |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| Przepustowość | 50 kilobajtów na sekundę (kB/s) dla każdego użytkownika | 100 megabajtów na sekundę (MB/s) |
| Opóźnienie   | Mniej niż 250-300 milisekund (ms)     | Mniej niż 1 ms (tylko sieć lokalna [LAN]). Serwer AOS i baza danych muszą być w tej samej lokalizacji. |

- Program Finance and Operations (wdrażany lokalnie) jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych zawierającego usługę Finance and Operations.
- Wymagania dotyczące przepustowości dla programu Finance and Operations (lokalnego wdrożenia) zależą od konkretnego scenariusza. Typowe scenariusze wymagają przepustowości ponad 50 kB/s między przeglądarką a serwerem programu Finance and Operations. Jednak zalecamy większą przepustowość dla scenariuszy z dużymi obciążeniami przesyłania danych, takich jak scenariusze z używaniem obszarów roboczych czy obejmujące rozbudowaną personalizację. Konkretnie wymagana przepustowość zależy od użycia.

Nie są obsługiwane wdrożenia, gdzie serwer AOS i baza danych programu Microsoft SQL Server znajdują się w różnych centrach danych. Serwer AOS i baza danych programu SQL Server muszą być w tej samej lokalizacji. 

Ogólnie rzecz biorąc program Finance and Operations jest zoptymalizowany do ograniczania rund komunikacji między przeglądarką a serwerem. Liczba rund od klienta przeglądarkowego do centrum danych wynosi zero lub jeden dla każdej interakcji z użytkownikiem, a wszystkie przesyłane dane są skompresowane.

> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Zalecamy używanie realistycznej symulacji w nieprodukcyjnym środowisku programu Finance and Operations jako najlepszego miernika wydajności w konkretnym przypadku. 

### <a name="lan-environments"></a>Środowiska LAN
W środowiskach sieci LAN narzędzie Pulpit zdalny Microsoft zawarte w systemie Microsoft Windows Server nie jest konieczne do nawiązywania połączenia z programem Finance and Operations. Niemniej jednak może być wymagane do operacji serwisowania na maszynach wirtualnych tworzących wdrożenie serwera.

### <a name="wan-environments"></a>Środowiska WAN
W środowiskach sieci rozległych (WAN) narzędzie Pulpit zdalny zawarte w systemie Windows Server nie jest konieczne do nawiązywania połączenia z programem Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Wymagania dotyczące łączności z Internetem
Program Finance and Operations (lokalne wdrożenie) nie wymaga, aby stacje robocze użytkowników miały połączenie z Internetem. Jednak niektóre funkcje nie będą dostępne bez połączenia internetowego.

|                    |   |
|--------------------|---|
| **Klient przeglądarkowy** | Scenariusz intranetowy bez łączności z Internetem jest aspektem projektowym w opcji wdrożenia lokalnego. Niektóre funkcje wymagające usług chmurowych, takich jak Pomoc i biblioteki przewodników po zadaniach w usłudze Microsoft Dynamics Lifecycle Services (LCS), nie będą dostępne. |
| **Serwer**         | Warstwa serwera AOS lub platformy Microsoft Azure Service Fabric musi być w stanie komunikować się z usługą LCS. Lokalny klient przeglądarkowy nie wymaga dostępu do Internetu. |
| **Telemetria**      | W przypadku długich przerw w łączności mogą zostać utracone dane telemetryczne. Przerwy w łączności z usługą LCS nie wpływają na funkcjonalność lokalnych aplikacji. |
| **Usługa LCS**            | Łączność z usługą LCS jest wymagana do wdrożenia programu, wdrożenia kodu źródłowego i czynności serwisowych. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Przesyłanie danych telemetrycznych do chmury
Większość danych telemetrycznych jest przechowywanych lokalnie i można uzyskać do nich dostęp za pomocą narzędzia Podgląd zdarzeń w systemie Microsoft Windows. Niewielki podzbiór zdarzeń telemetrycznych jest przekazywany do procesu telemetrii Microsoft w chmurze w celach diagnostycznych. Dane klientów i dane użytkowników umożliwiające identyfikację konkretnych osób nie są częścią danych telemetrycznych wysyłanych do firmy Microsoft. Nazwy maszyn wirtualnych są wysyłane do firmy Microsoft, aby pomóc w zarządzaniu środowiskami i diagnostyce z poziomu portalu LCS.

## <a name="domain-requirements"></a>Wymagania dotyczące domen
Podczas instalowania programu Finance and Operations (lokalnie) należy wziąć pod uwagę następujące wymagania dotyczące domen:

- Maszyny wirtualne zawierające składniki programu Finance and Operations (lokalnego wdrożenia) muszą należeć do domeny usługi Active Directory. Usługa Active Directory Domain Services (AD DS) musi być skonfigurowana w trybie natywnym.
- Maszyny wirtualne, na których są uruchomione składniki programu Finance and Operations (lokalnego wdrożenia), muszą mieć skonfigurowany wzajemny dostęp. Dostęp ten jest konfigurowany w usłudze AD DS. 
- Kontroler domeny musi zawierać system Microsoft Windows Server 2012 R2 lub nowszy, a poziomem funkcjonalności domeny musi być 2012 R2 lub wyższy.

## <a name="hardware-requirements"></a>Wymagania sprzętowe
W tym rozdziale opisano sprzęt wymagany do obsługi programu Finance and Operations (lokalnego wdrożenia).

Faktyczne wymagania sprzętowe różnią się w zależności od konfiguracji systemu, składu danych oraz aplikacji i funkcji, które mają być używane. Poniżej wymieniono kilka czynników, które mogą wpłynąć na dobór sprzętu dla programu Finance and Operations (lokalnego wdrożenia):

- Liczba transakcji na godzinę
- Liczba równocześnie aktywnych użytkowników

## <a name="minimum-infrastructure-requirements"></a>Minimalne wymagania w zakresie infrastruktury
Program Finance and Operations (lokalne wdrożenie) wykorzystuje platformę Service Fabric do obsługi usług serwera AOS, zadań wsadowych, zarządzania danymi, Management Reporter i Environment Orchestrator. 

Program SQL Server musi być w konfiguracji wysokiej dostępności HADRON, która ma co najmniej dwa węzły z przeznaczeniem produkcyjnym.

Poniższa ilustracja przestawia zalecaną minimalną liczbę węzłów w klastrze usługi Service Fabric.

[![Zalecana liczba węzłów dla klastra usługi Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Wymagania dotyczące procesorów i pamięci RAM
W poniższych tabelach podano liczbę procesorów i ilość pamięci o dostępie swobodnym (RAM), jakie są wymagane dla każdej roli koniecznej w tej opcji wdrożenia. Aby uzyskać więcej informacji, zobacz zalecane minimalne wymagania dla samodzielnego klastra platformy Service Fabric opisane w temacie [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Jeśli na tym samym komputerze jest zainstalowane inne oprogramowanie firmy Microsoft, system musi również spełniać wymagania sprzętowe związane tego oprogramowania. Jeśli na tym samym komputerze, na którym działa serwer AOS, są zainstalowane inne aplikacje serwerowe, zalecamy ograniczyć im używanie maksymalnie 1 gigabajta (GB) pamięci RAM.

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

**Minimalne szacowane zapotrzebowanie na elementy infrastruktury dla wdrożeń produkcyjnych i piaskownicy\***

| Topologia                                        | Rola                          | Liczba wystąpień |
|-------------------------------------------------|-------------------------------|---------------------|
| Produkcja                                      | Serwer obiektów aplikacji (zarządzanie danymi, zadania wsadowe)  | 3                   |
|                                                 | Program Management Reporter           | 2                   |
|                                                 | usługi SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator\*\*              | 3                   |
| Piaskownica                                         | Serwer obiektów aplikacji, zarządzanie danymi, zadania wsadowe   | 2                   |
|                                                 | Program Management Reporter           | 1                   |
|                                                 | usługi SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator                  | 3                   |
| *Sumarycznie topologie produkcyjna i piaskownicy* |                               | *16*                |

\* Liczby w tej tabeli są obecnie weryfikowane przez naszych klientów używających wersji zapoznawczych i mogą zostać skorygowane na podstawie informacji zwrotnych od tych klientów.

\*\* Orchestrator jest wyznaczony jako główny typ węzła i będzie używany również do uruchamiania usług platformy Service Fabric.

**Wstępne szacunki dotyczące programu SQL Server działającego w systemach zaplecza i usługi AD DS**

<table>
<thead>
<tr>
<th></th>
<th>Rola</th>
<th>Maszyny wirtualne/wystąpienia</th>
<th>Rdzenie</th>
<th>Razem liczba rdzeni</th>
<th>Pamięć na każde wystąpienie (GB)</th>
<th>Pamięć razem (GB)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Wspólna infrastruktura</strong></td>
<td>Sewer SQL*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>Serwer plików/sieć magazynowania/pamięć masowa o wysokiej dostępności</td>
<td colspan="5"><p>Pamięć masowa w systemach zaplecza musi się opierać na dyskach półprzewodnikowych (SSD) działających w sieci magazynowania (SAN) środowiska uruchomieniowego.</p>
<p>Zapotrzebowanie na zasoby i przepustowość wyrażona liczbą operacji wejścia/wyjścia na sekundę (IOPS) są oparte na wielkości obciążenia pracą.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48</td>
</tr>
<tr>
<td><em>Sumarycznie wspólna infrastruktura</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\*Parametry komputerów z programem SQL Server mocno zależą od obciążeń pracą. Aby uzyskać więcej informacji, zobacz [Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Magazynowanie

- **Serwer AOS** — program Finance and Operations (w lokalnym wdrożeniu) używa udziału bloku komunikatów serwera (SMB) w wersji 3.0 do przechowywania nieuporządkowanych danych. Aby uzyskać więcej informacji, zobacz [Bezpośrednie miejsca do magazynowania w systemie Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** — dopuszczalne są następujące opcje:

    - Konfiguracja o wysokiej dostępności z dyskiem SSD
    - Sieć magazynowania (SAN) zoptymalizowana dla przepustowości wymaganych w przetwarzaniu transakcji online (OLTP)
    - Konfiguracja o dużej wydajności z pamięcią masową dołączaną bezpośrednio (DAS) 

- **Liczna operacji we/wy na sekundę w programie SQL Server i podczas zarządzania danymi** — Pamięć masowa dla zarządzania danymi i programu SQL Server powinna obsługiwać co najmniej 2000 operacji IOPS. Wskaźnik IOPS w środowisku produkcyjnym zależy od wielu czynników. Aby uzyskać więcej informacji, zobacz [Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych](hardware-sizing-on-premises-environments.md).
- **Operacje IOPS na maszynach wirtualnych** — Każda maszyna wirtualna musi obsługiwać co najmniej 100 operacji zapisu IOPS.

## <a name="virtual-host-requirements"></a>Wymagania dotyczące hostów wirtualnych
Podczas konfigurowania hostów wirtualnych dla środowiska Finance and Operations (wdrożenia lokalnego) zapoznaj się z wytycznymi w tematach [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) oraz [Opisu klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Każdy host wirtualny powinien mieć wystarczającą liczbę rdzeni dla szacowanego zapotrzebowania na elementy infrastruktury. Jest możliwych wiele zaawansowanych konfiguracji, gdzie program SQL Server znajduje się na fizycznym urządzeniu, a wszystkie inne składniki są zwirtualizowane. Jeśli program SQL Server jest zwirtualizowany, podsystem dysku powinien mieć konfigurację szybkiej sieci magazynowania (SAN) lub równoważną. We wszystkich przypadkach upewnij się, że podstawowa konfiguracja hosta wirtualnego jest wysoce dostępna i nadmiarowa. We wszystkich przypadkach podczas stosowania wirtualizacji nie należy wykonywać migawek maszyn wirtualnych.

## <a name="software-requirements-for-all-server-computers"></a>Wymagania programowe dla wszystkich komputerów serwerów
Następujące oprogramowanie musi się znajdować na komputerze, zanim będzie można zainstalować jakiekolwiek składniki programu Finance and Operations (lokalnego wdrożenia):

- Microsoft .NET Framework w wersji 4.5.1 lub nowszej
- Service Fabric

Aby uzyskać więcej informacji, zobacz [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Obsługiwane serwerowe systemy operacyjne
W poniższej tabeli wymieniono serwerowe systemy operacyjne, które są obsługiwane przez składniki środowiska Finance and Operations.

| System operacyjny                                     | Notatki |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Datacenter lub Standard | Te wymagania dotyczą bazy danych i klastra usługi Service Fabric zawierającego serwer obiektów aplikacji. |

## <a name="software-requirements-for-database-servers"></a>Wymagania programowe dla serwerów baz danych

- Obsługiwane są tylko 64-bitowe wersje programu SQL Server 2016.
- W środowisku produkcyjnym zaleca się, aby zainstalować najnowszą aktualizację zbiorczą (CU) dla używanej wersji programu SQL Server.
- Program Finance and Operations (lokalne wdrożenie) obsługuje sortowanie w formacie Unicode, które ignoruje wielkości liter, uwzględnia akcenty, uwzględnia znaki kana i ignoruje szerokość. Sortowanie musi być zgodne z ustawieniami regionalnymi systemu Windows na komputerach zawierających wystąpienia serwera AOS. Jeśli konfigurujesz nową instalację, zalecamy wybranie sortowania systemu Windows zamiast sortowania programu SQL Server. Aby uzyskać więcej informacji na temat wybierania sposobu sortowania dla bazy danych programu SQL Server, zobacz [Dokumentacja programu SQL Server](/sql/sql-server/sql-server-technical-documentation).

W poniższej tabeli wymieniono wersje programu SQL Server, które są obsługiwane przez bazy danych środowiska Finance and Operations. Aby uzyskać więcej informacji, zobacz minimalne wymagania sprzętowe dla programu [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Zapotrzebowanie                                                      | Notatki |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition lub Enterprise Edition | Aby zapoznać się z wymaganiami sprzętowymi programu SQL Server 2016, zobacz [Wymagania sprzętowe i programowe dla instalacji programu SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-application-object-server-aos"></a>Wymagania dotyczące oprogramowania dla serwera obiektów aplikacji (AOS) 
- SQL Server Integation Services (SSIS)

## <a name="software-requirements-for-reporting-server-bi"></a>Wymagania dotyczące oprogramowania serwera raportowania (BI)
- SQL Server Reporting Services (SSRS)

## <a name="software-requirements-for-client-computers"></a>Wymagania programowe dla komputerów klienckich
Aplikacja sieci web Finance and Operations może być uruchamiana na dowolnym urządzeniu z przeglądarką sieci web zgodną ze standardem HTML 5.0. Oto kilka konkretnych kombinacji urządzeń/przeglądarek potwierdzonych przez Microsoft:

- Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
- Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
- Google Chrome (najnowsza publicznie dostępna wersja) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10
- Apple Safari (najnowsze publicznie dostępna wersja) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) albo na iPadzie firmy Apple

## <a name="software-requirements-for-active-directory-federation-services"></a>Wymagania programowe dla usługi Active Directory Federation Services 
Jest wymagana usługa Active Directory Federation Services (AD FS) w środowisku Windows Server 2016.

Kontroler domeny musi zawierać system Windows Server 2012 R2 lub nowszy, a poziomem funkcjonalności domeny musi być 2012 R2 lub wyższy. Aby uzyskać więcej informacji na temat poziomów funkcjonalnych domen, zobacz następujące strony:

- [Co to są poziomy funkcjonalności w usłudze Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Omówienie poziomów funkcjonalności w usłudze Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office
Następujące aplikacje pakietu Microsoft Office są obsługiwane we wdrożeniach chmurowych i lokalnych programu Finance and Operations:

-   Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej informacji na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Wymagania sprzętowe i programowe dla składników sprzedaży detalicznej
Obecnie program Finance and Operations (lokalne wdrożenie) obecnie nie zawiera żadnych składników sprzedaży detalicznej.

