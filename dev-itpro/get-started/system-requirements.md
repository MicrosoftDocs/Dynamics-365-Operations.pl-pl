---
title: Wymagania systemowe
description: "Ten temat zawiera listę wymagań systemowych dla bieżącej wersji programu Microsoft Dynamics 365 dla operacji."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Wymagania systemowe

Ten temat zawiera listę wymagań systemowych dla bieżącej wersji programu Microsoft Dynamics 365 dla operacji.

<a name="supported-web-browsers"></a>Obsługiwane przeglądarki
----------------------

Usługi Microsoft Dynamics 365 dla aplikacji sieci web operacji można uruchomić w dowolnym z następujących przeglądarek sieci web, które są uruchamiane w określonych systemach operacyjnych:

-   Microsoft Edge (Najnowsza wersja publicznie dostępnych) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Google Chrome (najnowszej wersji publicznie dostępnych) na 10 systemu Windows, Windows 8.1, Windows 8, Windows 7 lub 10 węzła Google komputera typu tablet
-   Apple Safari (Najnowsza wersja publicznie dostępne) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) lub Apple iPad

Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania. **Uwagi:**

-   Aby przechwycić obrazy, które są generowane na podstawie Rejestrator zadań i uwzględnić je w dokumentach programu Microsoft Word, musi mieć rozszerzenie Chrome zainstalowany. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   Edytor przepływu pracy jest uruchamiany jako aplikacji ClickOnce. Tylko Microsoft Edge i Internet Explorer (w wersji systemu Microsoft Windows) obsługuje aplikacji ClickOnce. Aplikacja ClickOnce edytora przepływu pracy wymaga 64-bitowych zgodnym systemem operacyjnym.
-   Projektant raportów do raportowania finansowego jest uruchamiana jako aplikacji ClickOnce. Wymaga 64-bitowych zgodnym systemem operacyjnym. Jeśli używasz Chrome, należy zainstalować rozszerzenie ClickOnce w celu pobrania kliencie projektant raportu. Jeśli używasz Chrome w trybie incognito, upewnij się, że rozszerzenie ClickOnce jest również włączona dla trybu incognito.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Obsługiwane przeglądarki dla aplikacji Retail Cloud POS

Program Retail POS chmura dla usługi Dynamics 365 dla operacji można uruchomić w dowolnym z następujących przeglądarek sieci web, które są uruchamiane w określonych systemach operacyjnych:

-   Microsoft Edge (Najnowsza wersja publicznie dostępnych) w systemie Windows 10
-   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
-   Chrom (najnowszej wersji publicznie dostępnych) na 10 systemu Windows, Windows 8.1 lub Windows 7

## <a name="network-requirements"></a>Wymagania sieciowe
-   Dynamics 365 dla operacji jest przeznaczona dla sieci z opóźnieniem mniej niż 150 milisekund (ms). Jest to czas oczekiwania z przeglądarki klienta do centrum danych Microsoft Azure, obsługującym 365 Dynamics dla operacji. Zaleca się przetestowanie czasu oczekiwania w sieci o <http://www.azurespeed.com>.
-   Wymagania związane z przepustowością dla usługi Dynamics 365 dla operacji są zależne od danego scenariusza. Najbardziej typowe scenariusze wymagają przepustowości ponad 50 kilobajtów na sekundę (KB/s). Dla scenariuszy, które mają wymagania dużym obciążeniu, takich jak obszary robocze lub scenariusze obejmujące rozbudowane możliwości dostosowania większej przepustowości jest jednak zalecane.

Na ogół 365 Dynamics dla operacji jest zoptymalizowany dla Internetu. Liczba odwołań z przeglądarki klienta do centrum danych Azure jest bardzo mały, a cały ładunek jest skompresowany. **Ostrzeżenie:** nie obliczyć wymagań dotyczących przepustowości z lokalizacji klienta przez pomnożenie liczby użytkowników przez minimalnych wymagań dotyczących przepustowości. Współbieżne używanie danej lokalizacji jest bardzo trudne do obliczenia. Dla klientów, którzy zwracają uwagę wymagania związane z przepustowością Użyj wersja zapoznawcza systemu Dynamics 365 dla operacji.

## <a name="net-framework-requirements"></a>Wymagania.NET Framework
Dynamics 365 dla operacji wymaga.NET Framework w wersji 4.6.2 dla wszystkich kliknij-raz aplikacji, takich jak dokument agenta routingu. Aby uzyskać instrukcje dotyczące instalacji, zobacz [instalowanie.NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje Microsoft Office
-   Aby uruchomić program Microsoft Excel i dodatki programu Word, musi mieć Microsoft Office 2016 dla systemu Windows lub Mac zainstalowany. Aby uzyskać więcej szczegółów na temat wymagania dotyczące wersji, zobacz [Rozwiązywanie problemów z integracją Office](/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Aby wyświetlić dokumenty, które są generowane przez do eksportu do programu Excel lub do wywozu do funkcji programu Word, należy mieć pakiet Microsoft Office 2007 lub nowszy.

## <a name="retail-modern-pos-requirements"></a>Wymagania nowoczesnego punktu sprzedaży sieci sprzedaży
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Program Retail POS nowoczesnych jest aplikacją 32-bitową, ale będzie działał na architekturach x86 i x64.
-   Nowoczesny punkt sprzedaży jest obsługiwany tylko w wersji Windows 10 Pro, Enterprise i Enterprise długi termin obsługi oddziału (LTSB).

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

-   Minimalna obsługiwana rozdzielczość jest 1280 × 1024.
-   Komputer, który uruchamia program Retail POS nowoczesnych na musi spełniać następujące wymagania:
    -   Musi on mieć, co najmniej dwurdzeniowy procesor, który jest uruchamiany w nie mniej niż 2 gigaherc (GHz).
    -   Musi on mieć, co najmniej 3 gigabajtów (GB) pamięci RAM.
    -   Musi mieć dostęp do Internetu.

## <a name="retail-hardware-station-requirements"></a>Wymagania stacji sprzętu sieci sprzedaży
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Stacja sprzętowa sprzedaży detalicznej jest aplikacją 32-bitową, ale będzie działał na architekturach zarówno x86, jak i x64.
-   Stacja sprzętowa sprzedaży detalicznej jest obsługiwany w następujących systemach operacyjnych:
    -   Wersje systemu Windows 7 Professional, Enterprise i Ultimate **Uwaga:** Windows 7 jest obsługiwany tylko wtedy, gdy program Internet Explorer 11 ręcznie jest zainstalowana w systemie.
    -   Aktualizacja systemu Windows 8.1 1 w wersji Professional, Enterprise i osadzone
    -   Wersje systemu Windows 10 Pro, Enterprise i Enterprise LTSB

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

Komputer musi spełniać wszystkie wymagania systemowe dotyczące instalowania i używania następujących elementów:

-   Internetowe usługi informacyjne (IIS)
-   Sprzętu innych firm

## <a name="retail-store-scale-unit-requirements"></a>Wymagania jednostki skali sklepu sieci sprzedaży
### <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

-   Jednostka skali sprzedaży detalicznej jest aplikacją 32-bitową, ale będzie działał na architekturach x86 i x64.
-   Jednostka skali sprzedaży detalicznej jest obsługiwany w następujących systemach operacyjnych:
    -   Wersje systemu Windows 7 Professional, Enterprise i Ultimate
    -   Aktualizacja systemu Windows 8.1 1 w wersji Professional, Enterprise i osadzone
    -   Wersje systemu Windows 10 Pro, Enterprise i Enterprise LTSB

### <a name="minimum-system-requirements"></a>Minimalne wymagania systemowe

-   4 GB pamięci RAM
-   1,6 GHz Szczytowa szybkość Procesora na jeden rdzeń (minimum są dwa rdzenie.)
-   Co najmniej 10 GB wolnego miejsca (bazy danych kanałów można wymagać dużej ilości miejsca).

### <a name="recommended-system-requirements"></a>Zalecane wymagania systemowe

-   6 GB pamięci RAM
-   2,4 prędkość GHz i7 (lub równoważna) piku Procesora na każdy rdzeń (cztery rdzenie są zalecane.)
-   Co najmniej 10 GB wolnego miejsca (bazy danych kanałów można wymagać dużej ilości miejsca).

## <a name="requirements-for-development-on-local-vms"></a>Wymagania dotyczące rozwoju na lokalne maszyny wirtualne
Szczegółowe informacje o wymaganiach dotyczących rozwoju lokalnego maszyn wirtualnych (VMs), [maszyny Wirtualnej z systemem lokalnych](/dynamics365/operations/dev-itpro/dev-tools/access-instances#vm-that-is-running-in-premises).

<a name="see-also"></a>Informacje dodatkowe
--------

[Pobierz kopia ewaluacyjna systemu Dynamics 365 dla operacji](/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


