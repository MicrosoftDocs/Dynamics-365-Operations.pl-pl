---
title: Wymagania systemowe
description: W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 724ee7ec29f8a9c4e8cc0b244193cd6c83c37f03
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Wymagania systemowe
<a id="system-requirements" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

Obsługiwane przeglądarki
<a id="supported-web-browsers" class="xliff"></a>
----------------------

Aplikacja internetowa może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:

-   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Google Chrome (najnowsza publicznie dostępna wersja) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10
-   Apple Safari (najnowsze publicznie dostępna wersja) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) albo na iPadzie firmy Apple

Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania. 

**Uwagi:**

-   Aby umożliwić przechwytywanie obrazów przez Rejestrator zadań i umieszczanie ich w generowanych dokumentach programu Microsoft Word, należy zainstalować wstępną wersję rozszerzenia dla przeglądarki Chrome. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
-   Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce. Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows). Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.
-   Projektant raportów dla raportowania finansowego jest uruchamiany jako aplikacji ClickOnce. Wymaga zgodnego 64-bitowego systemu operacyjnego. Jeśli używasz przeglądarki Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta projektanta raportów. Jeśli używasz przeglądarki Chrome w trybie incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb incognito.
-   Aby wyświetlać podgląd plików PDF, zalecamy używanie przeglądarek takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.


### Obsługiwane przeglądarki dla aplikacji Retail Cloud POS
<a id="supported-web-browsers-for-retail-cloud-pos" class="xliff"></a>

Aplikacja Retail Cloud POS może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:

-   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Chrom (najnowsza publicznie dostępna wersja) w systemie Windows 10, Windows 8.1 lub Windows 7

## Wymagania sieciowe
<a id="network-requirements" class="xliff"></a>
-   Dynamics 365 for Finance and Operations Enterprise Edition jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych Microsoft Azure zawierającego usługę Finance and Operations. Zaleca się przetestowanie opóźnienia w sieci na stronie <http://www.azurespeed.com>.
-   Wymagania dotyczące przepustowości zależą od konkretnego scenariusza. Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s). Jednak dla scenariuszy z dużymi obciążeniami przesyłania danych, takich jak używanie obszarów roboczych czy scenariusze obejmujące rozbudowaną personalizację, zaleca się większą przepustowość sieci.

Ogólnie rzecz biorąc program Finance and Operations jest zoptymalizowany dla Internetu. Liczba rund od klienta przeglądarkowego do centrum danych Azure jest mała, a wszystkie przesyłane dane są skompresowane. 

**Ostrzeżenie:** Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest trudne do obliczenia. Dla odbiorców, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, użyj wersji zapoznawczej programu Finance and Operations.

## Wymagania dotyczące środowiska .NET Framework
<a id="net-framework-requirements" class="xliff"></a>
Wszystkie aplikacje ClickOnce, takie jak agent rozsyłania dokumentów, wymagają środowiska .NET Framework w wersji 4.6.2. Instrukcje instalacji znajdują się w temacie [Instalowanie środowiska .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## Obsługiwane aplikacje pakietu Microsoft Office
<a id="supported-microsoft-office-applications" class="xliff"></a>
-   Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej szczegółów na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.

## Wymagania dotyczące programu Retail Modern POS
<a id="retail-modern-pos-requirements" class="xliff"></a>
### Obsługiwane systemy operacyjne
<a id="supported-operating-systems" class="xliff"></a>

-   Aplikacja Retail Modern POS jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail Modern POS jest obsługiwana w systemie Windows 10 tylko w wydaniach Pro, Enterprise i Enterprise Long Term Servicing Branch (LTSB).

### Minimalne wymagania systemowe
<a id="minimum-system-requirements" class="xliff"></a>

-   Minimalna obsługiwana rozdzielczość wynosi 1280 × 1024 piksele.
-   Komputer, na którym jest uruchamiany program Retail Modern POS, musi spełniać następujące wymagania:
    -   Musi mieć co najmniej dwurdzeniowy procesor o taktowaniu co najmniej 2 gigaherców (GHz).
    -   Musi mieć najmniej 3 gigabajty (GB) pamięci RAM.
    -   Musi mieć dostęp do Internetu.

## Wymagania dotyczące programu Retail hardware station
<a id="retail-hardware-station-requirements" class="xliff"></a>
### Obsługiwane systemy operacyjne
<a id="supported-operating-systems" class="xliff"></a>

-   Aplikacja Retail hardware station jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail hardware station jest obsługiwana w następujących systemach operacyjnych:
    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate **Uwaga:** System Windows 7 jest obsługiwany tylko wtedy, jeśli w systemie ręcznie zainstalowano przeglądarkę Internet Explorer 11.
    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB

### Minimalne wymagania systemowe
<a id="minimum-system-requirements" class="xliff"></a>

Komputer musi spełniać wszystkie wymagania systemowe dotyczące instalowania i używania następujących składników:

-   Internetowe usługi informacyjne (IIS)
-   Sprzęt innych firm

## Wymagania dotyczące programu Retail Store Scale Unit
<a id="retail-store-scale-unit-requirements" class="xliff"></a>
### Obsługiwane systemy operacyjne
<a id="supported-operating-systems" class="xliff"></a>

-   Aplikacja Retail Store Scale Unit jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail Store Scale Unit jest obsługiwana w następujących systemach operacyjnych:
    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate
    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB

### Minimalne wymagania systemowe
<a id="minimum-system-requirements" class="xliff"></a>

-   4 GB pamięci RAM
-   Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

### Zalecane wymagania systemowe
<a id="recommended-system-requirements" class="xliff"></a>

-   6 GB pamięci RAM
-   Procesor i7 o szczytowej szybkości każdego rdzenia 2,4 GHz (lub równoważny) (zalecane są cztery rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

## Wymagania dotyczące aplikacji łącznika
<a id="connector-requirements" class="xliff"></a>
### Obsługiwane systemy operacyjne
<a id="supported-operating-systems" class="xliff"></a>

-   Oprogramowanie łącznika systemu Microsoft Dynamics AX ma dwie osobne wersje instalacyjne — **Usługa Async Server Connector** i **Usługa Real-Time service dla systemu Dynamics AX 2012 R3**.
-   Oba składniki są 32-bitowymi aplikacjami, ale będą działały w architekturach x86 i x64.
-   Oba składniki są obsługiwane w następujących systemach operacyjnych:
    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate
    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB
    -   Windows Server 2012 R2, Windows Server 2016

### Minimalne wymagania systemowe
<a id="minimum-system-requirements" class="xliff"></a>

-   2 GB pamięci RAM, zalecane 4 GB pamięci RAM
-   Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

## Wymagania dotyczące instalowania na lokalnych maszynach wirtualnych
<a id="requirements-for-development-on-local-vms" class="xliff"></a>
Szczegółowe informacje o wymaganiach dotyczących instalowania na lokalnych maszynach wirtualnych (VM) zawiera temat [Maszyny wirtualne uruchamiane lokalnie](../dev-tools/access-instances.md).

Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Pobieranie kopii ewaluacyjnej programu Dynamics 365 for Finance and Operations Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)





