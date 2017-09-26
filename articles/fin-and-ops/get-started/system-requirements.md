---
title: "Wymagania systemowe dotyczące wdrożeń w chmurze"
description: "W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń chmurowych."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 46eacb2a01c3bfcc7144c7d8c39ee0189fd72e16
ms.contentlocale: pl-pl
ms.lasthandoff: 08/04/2017

---

# <a name="system-requirements-for-cloud-deployments"></a>Wymagania systemowe dotyczące wdrożeń w chmurze

[!include[banner](../includes/banner.md)]

W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń chmurowych. Przed zainstalowaniem programu Finance and Operations w razie potrzeby sprawdź, czy system, na którym pracujesz, co najmniej spełnia minimalne wymagania sieciowe, sprzętowe i programowe.

## <a name="supported-web-browsers"></a>Obsługiwane przeglądarki
Aplikacja internetowa może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:

-   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Google Chrome (najnowsza publicznie dostępna wersja) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10
-   Apple Safari (najnowsze publicznie dostępna wersja) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) albo na iPadzie firmy Apple

Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania. 

> [!NOTE]
> -   Aby umożliwić przechwytywanie zrzutów ekranu przez Rejestrator zadań i umieszczanie ich w generowanych dokumentach programu Microsoft Word, należy zainstalować wstępną wersję rozszerzenia dla przeglądarki Chrome. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce. Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows). Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.
> -   Projektant raportów dla raportowania finansowego jest uruchamiany jako aplikacji ClickOnce. Wymaga zgodnego 64-bitowego systemu operacyjnego. Jeśli używasz przeglądarki Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta Projektanta raportów. Jeśli używasz przeglądarki Chrome w trybie Incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb Incognito.
> -   Aby wyświetlać podgląd plików PDF, zalecamy używanie przeglądarek takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Obsługiwane przeglądarki dla aplikacji Retail Cloud POS

Aplikacja Retail Cloud POS może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:

-   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Chrom (najnowsza publicznie dostępna wersja) w systemie Windows 10, Windows 8.1 lub Windows 7

## <a name="network-requirements"></a>Wymagania sieciowe
-   Program Finance and Operations jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych Microsoft Azure zawierającego usługę Finance and Operations. Zaleca się przetestowanie opóźnienia w sieci na stronie <http://www.azurespeed.com>.
-   Wymagania dotyczące przepustowości dla programu Finance and Operations zależą od konkretnego scenariusza. Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s). Jednak zalecamy wyższą przepustowość dla scenariuszy z dużymi obciążeniami przesyłania danych, takich jak scenariusze z używaniem obszarów roboczych czy obejmujące rozbudowaną personalizację.

Ogólnie rzecz biorąc program Finance and Operations jest zoptymalizowany dla Internetu. Liczba rund od klienta przeglądarkowego do centrum danych Azure jest bardzo mała, a wszystkie przesyłane dane są skompresowane. 

> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Klienci, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, powinni używać wersji zapoznawczej programu Finance and Operations.

## <a name="net-framework-requirements"></a>Wymagania dotyczące środowiska .NET Framework
Program Finance and Operations wymaga środowiska Microsoft .NET Framework w wersji 4.6.2 dla wszystkich aplikacji ClickOnce, takich jak agent rozsyłania dokumentów. Instrukcje instalacji znajdują się w temacie [Instalowanie środowiska .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office
Następujące aplikacje pakietu Microsoft Office są obsługiwane we wdrożeniach chmurowych i lokalnych programu Finance and Operations:

-   Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej informacji na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.

## <a name="retail-modern-pos-requirements"></a>Wymagania dotyczące programu Retail Modern POS

> [!NOTE]
> Jeśli aplikacja Retail Modern POS będzie używać bazy danych w trybie offline, komputer musi spełniać wszystkie wymagania systemowe dla programu Microsoft SQL Server. Baza danych offline programu Retail Modern POS będzie współpracować z programami Microsoft SQL Server 2012 z dodatkiem Service Pack 3 lub nowszym, Microsoft SQL Server 2014 z dodatkiem Service Pack 2 lub nowszym i Microsoft SQL Server 2016. Zalecamy, aby zawsze używać najnowszej dostępnej wersji i instalować wszystkie najnowsze dodatki Service Pack.

### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Aplikacja Retail Modern POS jest 32-bitowa, ale będzie działała w architekturach x86 i x64.
-   Aplikacja Retail Modern POS jest obsługiwana w systemie Windows 10 tylko w wydaniach Pro, Enterprise i Enterprise Long Term Servicing Branch (LTSB).

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

-   Minimalna obsługiwana rozdzielczość wynosi 1280 × 1024 piksele.
-   Komputer, na którym jest uruchamiany program Retail Modern POS, musi spełniać następujące wymagania:

    -   Musi mieć co najmniej dwurdzeniowy procesor o taktowaniu co najmniej 2 gigaherców (GHz).
    -   Musi mieć najmniej 3 gigabajty (GB) pamięci o dostępie swobodnym (RAM).
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

-   Oprogramowanie łącznika systemu Microsoft Dynamics AX ma dwie osobne wersje instalacyjne — jedną dla usługi Async Server Connector i jedną dla usługi Real-Time Service dla systemu Dynamics AX 2012 R3.
-   Oba składniki są 32-bitowymi aplikacjami, ale będą działały w architekturach x86 i x64.
-   Oba składniki są obsługiwane w następujących systemach operacyjnych:

    -   Windows 7 w wydaniach Professional, Enterprise i Ultimate
    -   Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded
    -   Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB
    -   Microsoft Windows Server 2012 R2 i Microsoft Windows Server 2016

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe
-   2 GB pamięci RAM (zalecane 4 GB pamięci RAM)
-   Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)
-   Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)

## <a name="requirements-for-development-on-local-vms"></a>Wymagania dotyczące instalowania na lokalnych maszynach wirtualnych
Szczegółowe informacje o wymaganiach dotyczących instalowania na lokalnych maszynach wirtualnych (VM) zawiera temat [Maszyny wirtualne uruchamiane lokalnie](../dev-tools/access-instances.md).


## <a name="see-also"></a>Informacje dodatkowe

[Pobieranie kopii ewaluacyjnej programu Dynamics 365 for Finance and Operations Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

