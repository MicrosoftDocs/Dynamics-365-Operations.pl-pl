---
title: "Wymagania dotyczące szacowania zapotrzebowania na sprzęt dla środowisk lokalnych"
description: "W tym temacie opisano wymagania dotyczące szacowania zapotrzebowania na sprzęt w środowisku lokalnym."
author: kfend
manager: AnnBe
ms.date: 06/23/2017
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
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: 5be9b195754d6c8315342c83451128092f64a241
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="hardware-sizing-for-on-premises-environments"></a>Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych
Przed rozpoczęciem procesu szacowania zapotrzebowania na sprzęt i infrastrukturę w środowisku lokalnym, zapoznaj się z tematami [Wymagania systemowe](system-requirements.md) oraz [Instrukcje konfigurowania i wdrażania](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md), aby dobrze poznać cechy bazowej infrastruktury. 

  **Uwaga:** Przestrzegaj najważniejszych wskazówek dotyczących konfigurowania systemu, aby uzyskać optymalną wydajność. 

Po przejrzeniu dokumentacji można rozpocząć proces szacowania wolumenu transakcji i jednoczesnych użytkowników oraz ustalania zapotrzebowania na elementy środowiska w oparciu o średnie możliwości przetwarzania na rdzeniach.

## <a name="factors-that-affect-sizing"></a>Czynniki wpływające na zapotrzebowanie na elementy infrastruktury
Wszystkie czynniki pokazane na poniższej ilustracji mają wpływ na dobór składników infrastruktury. Im bardziej szczegółowe informacje uda się zebrać, tym dokładniej można określić zapotrzebowanie. Bez danych pomocniczych oszacowanie zapotrzebowania na sprzęt będzie niedokładne. Absolutnym minimalnym wymogiem dla niezbędnych danych jest uwzględnienie szczytowego godzinowego obciążenia wierszami transakcji. 

[![Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

Patrząc od lewej do prawej, pierwszym i najważniejszym czynnikiem niezbędnym do dokładnego oszacowania zapotrzebowania na elementy infrastruktury jest profil transakcji lub charakterystyka transakcji. Zawsze należy ustalić szczytowy wolumen transakcji na godzinę. Jeśli istnieje wiele okresów szczytowych, należy je precyzyjnie zdefiniować. 

W trakcie poznawania szczegółów obciążeń wpływających na infrastrukturę trzeba również uzyskać dokładniejszą wiedzę o następujących czynnikach: 

- **Transakcje** — Na ogół transakcje mają określone wartości szczytowe w dniu/tygodniu. Najczęściej zależy to od typu transakcji. Wpisy rozliczania według czasu i wydatków zwykle wykazują skoki raz w tygodniu, podczas gdy wpisy zamówień sprzedaży są przesyłane zbiorczo poprzez integrację lub stopniowo napływają przez cały dzień. 

- **Liczba równocześnie aktywnych użytkowników** — Liczba jednoczesnych użytkowników jest drugim pod względem ważności czynnikiem przy szacowaniu zapotrzebowania na elementy infrastruktury. Nie można prawidłowo oszacować zapotrzebowania na elementy infrastruktury tylko na podstawie liczby równoczesnych użytkowników, więc jeśli są to jedyne dostępne dane, należy określić przybliżoną liczbę, a następnie ją zweryfikować po uzyskaniu dodatkowych danych. Precyzyjna definicja równoczesnych użytkowników określa, że: 
  - Nazwani użytkownicy nie są użytkownikami aktywnymi równocześnie.
  - Jednocześni użytkownicy są zawsze podzbiorem nazwanych użytkowników. 
  - Szczytowe obciążenie decyduje o maksymalnej liczbie równoczesnych użytkowników branej pod uwagę przy szacowaniu zapotrzebowania na elementy infrastruktury.
 
- Przy obliczaniu jednoczesnych użytkowników należy przyjąć, że dla każdego użytkownika są spełnione następujące warunki: 
  - Użytkownik zalogowany. 
  - Transakcje/zapytania są w toku podczas liczenia. 
  - Sesja nie jest bezczynna. 
 
- **Skład danych** — Ten czynnik dotyczy głównie sposobu zainstalowania i skonfigurowania systemu. Na przykład ile firm będzie istnieć, ile towarów, ile poziomów BOM i jak skomplikowana będzie konfiguracja zabezpieczeń. Każdy z tych czynników może mieć pewien wpływ na wydajność, dlatego ich oddziaływanie można zrównoważyć przemyślanymi wyborami składników infrastruktury. 

- **Rozszerzenia** — Dostosowania mogą być proste lub złożone. Liczba dostosowań oraz charakter złożoności i użytkowania mają zróżnicowany wpływ na wielkość niezbędnej infrastruktury. W przypadku złożonych dostosowań zalecamy przeprowadzenie ocen wydajności, aby upewnić się, że dostosowania są sprawdzone nie tylko pod kątem sprawności działania, ale także potrzeb infrastrukturalnych. Jest to jeszcze ważniejsze, gdy kod źródłowy rozszerzeń nie przestrzega najważniejszych wskazówek dotyczących wydajności i skalowalności. 

- **Raportowanie i analizy** — Te czynniki zwykle obejmują wykonywanie intensywnych zapytań w różnych bazach danych w systemach bazodanowych środowiska Finance and Operations. Zrozumienie, kiedy są wykonywane raporty najbardziej obciążające system, a następnie ich ograniczenie, pozwoli zrozumieć ich oddziaływanie na infrastrukturę. 

- **Rozwiązania innych firm** — Te rozwiązania, np. aplikacje niezależnych dostawców oprogramowania (ISV), mają takie same efekty i towarzyszące zalecenia, jak rozszerzenia. 

## <a name="sizing-your-finance-and-operations-environment"></a>Szacowanie zapotrzebowania na elementy infrastruktury środowiska Finance and Operations
Aby poznać zapotrzebowanie na elementy infrastruktury, konieczne jest ustalenie szczytowego wolumenu transakcji, który będzie przetwarzany. Większość systemów pomocniczych, takich jak Management Reporter lub usługa SSRS, są mniej newralgiczne. Dlatego ten dokument koncentruje się głównie na serwerze obiektów aplikacji (AOS) i programie SQL Server. 

**Uwaga:** Na ogół warstwy obliczeniowe są skalowalne i powinny być skonfigurowane w układzie N+1, co oznacza, jeśli szacujesz zapotrzebowanie na trzy serwery AOS, dodaj czwarty serwer AOS. Warstwa baz danych powinna być skonfigurowana w układzie wysokiej dostępności z ciągłym włączeniem. 


## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Szacowanie zapotrzebowania na elementy infrastruktury

- Od 3 do 15 tys. wierszy transakcji na godzinę na jeden rdzeń na serwerze baz danych.
- Typowa proporcja liczby rdzeni serwerów AOS do SQL wynosi 3:1 dla podstawowego serwera SQL. Zależnie od wybranej konfiguracji wysokiej dostępności są wymagane dodatkowe rdzenie. 
  - Wykonywanie operacji z dużym udziałem baz danych może pogorszyć proporcję do 2:1. 
- Następujące czynniki mają wpływ na zmienność: 
  - Używane ustawienia parametrów. 
  - Poziomy rozszerzeń. 
  - Używanie dodatkowych funkcji, takich jak dzienniki i alerty baz danych. Ekstremalne protokołowanie zdarzeń bazy danych jeszcze bardziej ograniczy przepustowość na godzinę na każdy rdzeń do poziomu poniżej 3 tysięcy wierszy. 
  - Złożoność składu danych — Na przykład różnica między prostymi planami kont a szczegółowymi, drobiazgowymi planami kont ma wpływ na przepustowość. 
  - Cechy transakcji.
  - Od 2 GB do 4 GB pamięci RAM na każdy rdzeń. 
  - Pomocnicze bazy danych na serwerze baz danych, takie jak bazy danych programu Management Reporter i usługi SSRS.
  - Tymczasowa baza danych = 15% standardowego rozmiaru bazy danych, z liczbą plików równą liczbie fizycznych procesorów. 
  - Rozmiar i przepustowości sieci SAN ustalone na podstawie łącznej liczby/wykorzystywania transakcji równoczesnych. 

### <a name="high-availability"></a>Wysoka dostępność 
Zalecamy, aby zawsze używać programu SQL Server w konfiguracji z klastrem lub dublowaniem. Drugi węzeł serwera SQL powinien mieć taką samą liczbę rdzeni, jak węzeł główny. 

### <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)
W kwestii szacowania zapotrzebowania na elementy infrastruktury dla usługi AD FS zobacz [Dokumentacja parametrów serwera usługi AD FS](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

Jest dostępny [arkusz kalkulacyjny szacowania zapotrzebowania na elementy infrastruktury](http://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx) pomagający zaplanować liczbę wystąpień we wdrożeniu.

<a name="aos-online-and-batch"></a>Serwer AOS (w trybach online i wsadowym)
----------------------

### <a name="sizing"></a>Szacowanie zapotrzebowania na elementy infrastruktury

- Szacowanie zapotrzebowania na elementy infrastruktury według wolumenu/użycia transakcji
  - Od 2 do 6 tys. wierszy na jeden rdzeń
  - 16 GB dla każdego wystąpienia
  - Standardowa obudowa — 4-24 rdzenie
  - 10-15 użytkowników z licencją Enterprise na rdzeń
  - 15-25 użytkowników z licencją Activity na rdzeń
  - 25-50 członków zespołu na rdzeń
- Przetwarzanie
   - Od 1 do 4 wątków przetwarzania wsadowego na rdzeń
   - Zapotrzebowanie na elementy infrastruktury na podstawie cech okna czasowego zadań wsadowych
- Należy zauważyć, że serwer AOS, moduł zarządzania danymi i moduł przetwarzania wsadowego podlegają tej samej roli na platformie Service Fabric. Trzeba uwzględnić zapotrzebowanie na elementy infrastruktury dla tych trzech obciążeń łącznie, a nie oddzielne, tak jak ma to miejsce w systemie Microsoft Dynamics AX 2012.
- Mają zastosowanie te same czynniki zmienności, jak dla programu SQL Server.

### <a name="high-availability"></a>Wysoka dostępność
- Upewnij się, że masz dostępne co najmniej 1–2 serwery AOS więcej, niż potrzebujesz według szacunków.
- Upewnij się, że masz dostępne co najmniej 3–4 hosty wirtualne.

## <a name="management-reporter"></a>Management Reporter
W większości przypadków powinno wystarczać minimalne wymagane zalecenie dwóch węzłów, chyba że będzie wykonywane bardzo intensywne przetwarzanie. Tylko w przypadku intensywnego użytkowania będzie potrzeba więcej niż dwóch węzłów. Dobierz liczbę węzłów odpowiednio do potrzeb.

## <a name="sql-server-reporting-services"></a>usługi SQL Server Reporting Services
W wydaniu o ogólnej dostępności można wdrożyć tylko jeden węzeł usługi SSRS. Monitoruj węzeł z usługą SSRS podczas testowania i w razie potrzeby zwiększaj liczbę rdzeni dostępnych dla usługi SSRS. Upewnij się, że masz wstępnie skonfigurowany węzeł pomocniczy dostępny na hoście wirtualnym innym niż maszyna wirtualna z usługą SSRS. Jest to ważne, jeśli wystąpi problem z maszyną wirtualną zawierającą usługę SSRS lub z hostem wirtualnym. W takim przypadku należy wymienić te zasoby. 

## <a name="environment-orchestrator"></a>Environment Orchestrator
Usługa Orchestrator zarządza wdrożeniem i pokrewną komunikacją z usługą LCS. Ta usługa jest wdrażana jako podstawowa usługa platformy Service Fabric i wymaga co najmniej trzech maszyn wirtualnych. Usługa znajduje się w tej samej lokalizacji, co usługi organizowania platformy Service Fabric. Szacując dla niej zapotrzebowanie na elementy infrastruktury, należy się kierować szczytowym obciążeniem klastra. Aby uzyskać więcej informacji, zobacz [Zagadnienia związane z planowaniem pojemności klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-capacity).  


## <a name="virtualization-and-oversubscription"></a>Wirtualizacja i nadsubskrypcja
Usługi newralgiczne, takie jak serwer AOS, powinny być umieszczone na hostach wirtualnych mających dedykowane zasoby — rdzenie, pamięć operacyjną i dyski.   


