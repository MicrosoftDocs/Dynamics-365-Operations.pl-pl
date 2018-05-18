---
title: "Zasoby rozwiązania Operations"
description: "Zasoby operacyjne wykonują działania projektu lub procesu produkcji. Zasoby mogą być różnego typu i mieć różne możliwości."
author: sorenva
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OpResLifecycleManagementWorkspace, WrkCtrCapability
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c4018632e5e20470948ee59e4bb2a1cab905d829
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="operations-resources"></a>Zasoby rozwiązania Operations

[!include [banner](../includes/banner.md)]

Zasoby operacyjne wykonują działania projektu lub procesu produkcji. Zasoby mogą być różnego typu i mieć różne możliwości. 

<a name="operations-resources"></a>Zasoby rozwiązania Operations
--------------------

Zasobami operacyjnymi są maszyny, narzędzia, pracownicy, zakłady, obszary fizyczne lub dostawcy wykonujący działania w ramach projektu lub procesu produkcyjnego. Zasoby mogą być różnego typu i mieć różne zdolności produkcyjne.

-   **Dostawca** — Zasób operacyjny, który wykonuje działania w ramach projektu lub procesu produkcji. Przykładem jest podwykonawca. Łącząc zasoby dostawcy z kontem dostawcy, można generować zakupy dla podwykonawców na podstawie wierszy listy składowej (BOM) lub wierszy produkcji.
-   **Zasoby ludzkie** — pracownik w projekcie lub produkcji, który wykonuje działania samodzielnie lub jako operator narzędzia lub maszyny. Jeśli używasz funkcji zasobów ludzkich, zasoby ludzkie można połączyć z pracownikiem. Aparat planowania może następnie przydzielić zasoby na podstawie kompetencji określonych dla danego pracownika.
-   **Maszyna** — maszyny lub inne urządzenia produkcyjne, wymagane w procesie produkcji.
-   **Narzędzie** — przyrząd lub urządzenie, które jest zwykle używane wraz z innym zasobem do wykonania działania w projekcie lub w produkcji.
-   **Lokalizacja** — fizyczna lokalizacji o określonym rozmiarze, która jest wymagana do wykonania działania. Przykładem jest obszar montażowy.
-   **Zakład** — budynek lub stała struktura wymagane do wykonania działania.

## <a name="calendars"></a>Kalendarze
Kalendarz może być przypisany do zasobu operacyjnego i określać zdolności produkcyjne (w godzinach) danego zasobu. Czas pracy zasobu operacyjnego jest określany przez kalendarz przypisany do grupy zasobów, której częścią jest dny zasób operacyjny. Można ustawić datę rozpoczęcia i zakończenia dla przypisanego kalendarza. Następnie można przypisać więcej niż jeden kalendarz do zasobu operacyjnego. Daty przypisanych kalendarzy nie mogą się nakładać, a zasób operacyjny może być przypisany tylko do jednego kalendarza w danym czasie. **Uwaga:** Jeśli nie ma obowiązujących kalendarzy roboczych dla grupy zasobów, na przykład w sytuacji, gdy ostatni przypisany lub jedyny przypisany kalendarza stracił ważność, nie można już uzyskać dostępu do zasobów, które są przypisane do grupy zasobów dla planowania produkcji i planowania operacji. Można również przypisać kalendarz do grupy zasobów w celu określenia godzin pracy dla grupy zasobów i wszystkich zasobów operacyjnych przypisanych do danej grupy. Wydajność grupy zasobów jest obliczana jako suma zdolności produkcyjne poszczególnych zasobów operacyjnych przypisanych do danej grupy zasobów. Kalendarz przypisany do grupy zasobów może się zmieniać w czasie.

## <a name="resource-capabilities"></a>Możliwości zasobu
Zdolność produkcyjna zdolność zasobu operacyjnego do wykonania określonego działania. Następnie można przypisać jedną lub więcej zdolności produkcyjnych do zasobu operacyjnego. Aparat planowania przydziela zasoby przez dopasowanie zapotrzebowań na zasoby w każdym działaniu do zdolności produkcyjnych dostępnych zasobów operacyjnych. Zdolności produkcyjne można przypisać do wszystkich typów zasobów operacyjnych (**Narzędzie**, **Dostawca**, **Maszyna**, **Zasoby ludzkie**, **Lokalizacja**, lub **Zakład**). Aby przypisać zdolności produkcyjne do zasobów operacyjnych na czas określony, wybierz daty rozpoczęcia i zakończenia w przypisaniu zdolności produkcyjnych. Aby uzyskać dodatkowe informacje, zobacz [Zdolności produkcyjne zasobu](resource-capabilities.md).

## <a name="resource-groups"></a>Grupy zasobów
Grupa zasobów to zbiór zasobów operacyjnych reprezentujących dokładność, z jaką chcesz zaplanować zasoby przy użyciu metody planowania operacji. Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych rozgraniczanych przez żółte linie w wydziale produkcji. Grupa zasobów definiuje oddział, jednostkę produkcyjną i kontekst magazynu dla zasobów operacyjnych przypisanych do grupy. Zasób operacyjny można zaplanować tylko wtedy, gdy jest przypisany do grupy zasobów i tylko w oddziale, w którym znajduje się grupa zasobów. Nie trzeba przydzielać zasobów operacyjnych, które można utworzyć, do grupy zasobów. Ale zasób operacyjny musi zostać przypisany do grupy zasobów zanim będzie można zaplanować dla niego wykonanie pracy. Zasoby operacyjne można przypisać do grupy zasobów przez ograniczony czas. Zasób operacyjny można też przypisać do wielu grup zasobów, tak aby można było go współużytkować w wielu oddziałach. Jednak daty rozpoczęcia i zakończenia nie mogą się nakładać. Innymi słowy nie można przypisać zasobu operacyjnego do dwóch różnych grup zasobów w tym samym czasie. Zmiany w przypisaniach grup zasobów są wprowadzane tylko w przypadku nowej alokacji zasobów. Rezerwacje zdolności produkcyjnych dla zadań, operacji i prognozy godzin projektu, które są już zaplanowane, nie ulegną zmianie. **Uwaga:** po przypisaniu zasobów operacyjnych typu **dostawcy** do grupy zasobów, wszystkie zasoby operacyjne przypisane do grupy zasobów muszą mieć typ **dostawcy** i muszą być połączone z tym samym kontem dostawcy.

## <a name="production-units"></a>Jednostki produkcyjne
Jednostka produkcyjna jest to jednostka administracyjna, która jest zbiorem grupy zasobów. Jednostka produkcyjna może zawierać wiele grup zasobów, ale grupa zasobów może być przypisana tylko do jednej jednostki produkcyjnej. Jednostka produkcyjna odzwierciedla fizyczny układ zasobów produkcji i nie ma wpływu na transakcje ani na sposób ich przeprowadzania. Jednostkę produkcyjną należy skojarzyć z oddziałem. Do jednostki produkcyjnej można też przypisać magazyn pobrania oraz magazyn przechowywania. Za pomocą jednostki produkcyjnej można konsolidować i filtrować dane związane z produkcją. Na przykład kierownik zakładu produkcyjnego może uzyskać przegląd nierównego obciążenia pracą i dostępnych zdolności produkcyjnych określonej jednostki produkcyjnej. Jednostkę produkcyjną przypisaną do grupy zasobów można zmienić. Można też usunąć jednostkę produkcyjną. Te zmiany jednostki produkcyjnej są jednak wprowadzane tylko w wypadku nowych zamówień, utworzonych po uruchomieniu planowania głównego. Aby zastosować modyfikację jednostki produkcyjnej w odniesieniu do już istniejących zamówień, trzeba to zrobić ręcznie.

## <a name="resource-scheduling"></a>Planowanie zasobów
Zasoby operacyjne są przypisywane do działań na etapie planowania projektu lub produkcji. Dostępne są dwie metody planowania: planowanie operacji i planowanie zadań. W przypadku korzystania z planowania operacji, każda operacja lub działanie w projekcie są planowane dla grupy zasobów, zawierającej zasoby operacyjne, które odpowiadają zapotrzebowaniom na zasoby określonym dla danej operacji. Jeśli zasób operacyjny jest wymagany do operacji, proces planowania rezerwuje zdolności produkcyjne tylko w określonym zasobie w grupie. Planowanie zadań jest bardziej szczegółowe niż planowanie operacji. Planowanie zadań umożliwia rozbicie każdej operacji na pojedyncze zadania. Zadania te są następnie przypisywane do zasobów operacyjnych, które będą je wykonywać. Planowanie rezerwuje zdolności produkcyjne w grupie zasobów na podstawie godzin pracy zdefiniowanych w marszrucie produkcji lub działaniach projektu. Jeśli są ograniczone zdolności produkcyjne, harmonogram zależy od dostępności zasobów operacyjnych wymaganych do zakończenia działania. W przypadku planowania operacji zdolności produkcyjne grupy zasobów są sumą dostępnych zdolności produkcyjnych zasobów operacyjnych przypisanych do tej grupy. Rezerwacje zdolności produkcyjnych, które już istnieją dla zasobów operacyjnych, są uznawane za niedostępne zdolności produkcyjne. Jeśli jest za mało zdolności produkcyjnych do produkcji, zlecenia produkcyjne mogą być opóźnione lub nawet wstrzymane. Na stronie **zasobów**można zdefiniować kilka właściwości, które kontrolują sposób rezerwowania zdolności produkcyjnych:

-   **Zdolności produkcyjne** — umożliwia określenie zdolności produkcyjnych zasobu operacyjnego na godzinę w jednostce miary.
-   **Zdolności produkcyjne partii** — umożliwia określenie maksymalnej liczby sztuk do przetworzenia przez zasób operacyjny na przebieg.
-   **Procent wydajności** — umożliwia określenie wydajności oczekiwanej od zasobu operacyjnego. Procent wydajności dostosowuje produktywność zasobu operacyjnego i wpływa na czas zarezerwowany dla zasobu. Czasy realizacji dla operacji, które korzystają z zasobu operacyjnego, również są odpowiednio korygowane. Poniżej przedstawiono formułę, która służy do obliczania: Godzina planowania = Czas × 100 ÷ Procent wydajności. *Czas* obejmuje zarówno czas procesu, jak i czas przezbrajania.
-   **Planowanie operacji — procent** — umożliwia określenie maksymalnego procentu zdolności produkcyjnych zasobu operacyjnego, jaki ma być wykorzystywany w planowaniu operacji. Wartość powinna być niższa niż 100 procent, aby możliwa była zmiana wydajności podczas planowania zadań.
-   **Ograniczone zdolności produkcyjne** — Ustaw w tej opcji wartość **Tak**, jeśli zasób operacyjny ma być planowany na podstawie rzeczywistych dostępnych zdolności produkcyjnych, a istniejące rezerwacje zdolności produkcyjnych mają zostać uwzględnione. Jeśli w opcji zostanie ustawiona wartość **Nie**, zakłada się, że zasób operacyjny ma nieograniczone zdolności produkcyjne i może być rezerwowany ponad możliwości.
-   **Ograniczone właściwości** — Ustaw w tej opcji wartość **Tak**, jeśli zasób operacyjny ma być planowany na podstawie rzeczywistej dostępnej zdolności produkcyjnej z uwzględnieniem właściwości planowania czasu pracy.
-   **Wyłączne** — Ustaw w tej opcji wartość **Tak**, jeśli nie chcesz, żeby zasób operacyjny był dostępny dla innego zadania lub operacji przed zakończeniem bieżącej produkcji. Oznacza to, że zasób operacyjny nie może być używany, nawet w przypadku przerw w czasie pracy zasobu.
-   **Zasób w wąskim gardle** — umożliwia definiowanie zasobu operacyjnego jako zasób w wąskim gardle. W przypadku zaznaczenia pola **Ograniczone zdolności produkcyjne** i pola **Planowanie wąskich gardeł** na stronie **Plany główne** zasób w wąskim gardle jest planowany przy użyciu ograniczonych zdolności produkcyjnych.

Aby zaplanować wykorzystanie wielu zasobów operacyjnych jednocześnie, na przykład w trakcie operacji w produkcji, należy określić wymagania dla różnych zasobów poprzez użycie operacji głównych i dodatkowych. Następnie można także zarezerwować wiele zasobów operacyjnych, które mają różne zdolności produkcyjne. Zasób operacyjny zaplanowany dla operacji głównej określa czas trwania działania.

## <a name="lean-work-cells"></a>Komórki robocze produkcji oszczędnej
Można określić, że grupa zasobów jest komórką robocza produkcji oszczędnej. Grupy zasobów mogą następnie być częścią przepływu produkcji. Określając grupę zasobów jako komórkę roboczą produkcji oszczędnej, możesz również uniemożliwić alokacje grupy zasobów i przypisanych do niej zasobów operacyjnych do operacji w zleceniu produkcyjnym lub prognozie godzin projektu. Dla poszczególnych grup zasobów, które mają pełnić rolę komórki roboczej produkcji oszczędnej trzeba określić następujące informacje:

-   **Kalendarz** — kalendarz roboczy komórki roboczej, która musi mieć właściwość standardowego dnia roboczego.
-   **Lokalizacja i magazyn pobrania** — domyślna lokalizacja służąca do pobierania materiału do działania.
-   **Lokalizacja i magazyn wydania** — domyślna lokalizacja, w której znajdują się wszystkie produkty wyjściowe komórki roboczej.
-   **Kategoria kosztu czasu wykonania** — ta kategoria musi być zdefiniowana dla komórki roboczej w przypadku uwzględnienia w wycenie bezpośredniej robocizny.

Jeżeli grupa zasobów jest używana jako komórka robocza produkcji oszczędnej, zdolności produkcyjne tej komórki roboczej są określane bezpośrednio w grupie zasobów. W związku z tym nie trzeba przydzielać zasobów operacyjnych do grupy zasobów. Tylko gdy komórka robocza jest zarządzana przez podwykonawcę, zasób operacyjny typu **dostawcy** musi być przypisany do komórki roboczej. Jeśli zasób operacyjny zostanie przypisany do grupy zasobów oznaczonej jako komórka robocza, zdolności produkcyjne komórki roboczej nie zmienią się.

## <a name="costing-resources"></a>Zasoby wyceny
Podczas definiowania działania, takiego jak operacja marszruty lub prognoza godzin projektu, można określić wymagania dla określonych zasobów operacyjnych lub grup zasobów. Można jednak również określić zapotrzebowanie na zasób operacyjny określonego typu lub zasób operacyjny o określonej zdolności produkcyjnej lub żądanych kompetencjach. Z tego powodu rzeczywiste przypisanie zasobów nie zostanie ukończone zanim zakończy się planowanie działań i rezerwacja zdolności produkcyjnych. W związku z tym w przypadku operacji marszruty można określić, że szacowanie i obliczanie BOM muszą być oparte na określonych zasobach operacyjnych. Te zasoby operacyjne są nazywane zasobami wyceny. Można także przenosić kategorii kosztu i czasy operacji z zasobu wyceny do działania. Podczas planowania operacji, szacowania i kalkulacje BOM są wykonywane przy użyciu rzeczywiście zaplanowanego zasobu operacyjnego.




