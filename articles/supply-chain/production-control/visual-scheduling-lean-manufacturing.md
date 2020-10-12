---
title: Wizualne planowanie zadań na potrzeby lean manufacturing
description: Ten temat zawiera informacje o tablicy harmonogramu Kanban, której planista produkcji może używać do kontrolowania i optymalizowanie planu produkcji dla zadań Kanban.
author: johanhoffmann
manager: tfehr
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization, KanbanBoardUnplannedJobs
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6710dcb1cb53e7221b03b35ceee5ac8e055b6dd2
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826413"
---
# <a name="visual-scheduling-for-lean-manufacturing"></a>Wizualne planowanie zadań na potrzeby lean manufacturing

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o tablicy harmonogramu Kanban, której planista produkcji może używać do kontrolowania i optymalizowanie planu produkcji dla zadań Kanban.

Ten temat zawiera informacje o tablicy harmonogramu Kanban, której planista produkcji może używać do kontrolowania i optymalizowanie planu produkcji dla zadań Kanban.

Tablica harmonogramu Kanban umożliwia planiście produkcji kontrolowanie i optymalizowanie planu produkcji dla zadań Kanban. Nadaje przejrzystości przepływowi zadań w systemie Kanban i stanowi dla planisty produkcji narzędzie, które optymalizuje i dostosowuje plan produkcji dla komórki roboczej produkcji oszczędnej.

## <a name="visual-scheduling-of-kanban-jobs"></a>Wizualne planowanie zadań w systemie Kanban
Zadanie Kanban może się składać z jednego lub wielu zadań Kanban. Istnieją dwa typy zadań Kanban:

-   Przetwarzaj
-   Przenoszenie

Planować można tylko zadania typu **Przetwarzanie**. Zadanie w systemie Kanban i jego właściwości, takie jak czas działania, są definiowane w przepływie Kanban produkcji. W przepływie Kanban produkcji zadanie Kanban jest również przypisane do komórki roboczej. Dzienne zdolności produkcyjne komórki roboczej są obliczana na podstawie zdolności produkcyjnych komórki ustawionych w grupie zasobów. Następnie są korygowane przez dzienny czas pracy w powiązanym kalendarzu. Podczas planowania zadania Kanban są dla niego wczytywane zdolności produkcyjne komórki roboczej. Tablica harmonogramu Kanban zawiera następujące główne elementy:

-   Graficzny przegląd planu produkcji w komórce roboczej produkcji oszczędnej. Ten przegląd pokazuje zaplanowane zadania przetwarzania Kanban w zdefiniowanych okresach.
-   Narzędzie umożliwiające planowanie niezaplanowanych zadań Kanban i zmianę harmonogramów uprzednio zaplanowanych zadań.

## <a name="kanban-schedule-board"></a>Tablica harmonogramu Kanban
Strona **Tablica harmonogramu Kanban** zawiera siedem głównych elementów, jak pokazano na poniższej ilustracji. 

![Tablica harmonogramu Kanban](./media/kanban-schedule-board-1024x554.png)
1.  Okienko akcji
2.  Pola filtrowania
3.  Przycisk nieplanowanych zadań
4.  Węzeł okresu
5.  Zadanie w systemie Kanban
6.  Pasek zdolności produkcyjnych
7.  Skala czasu

### <a name="view-the-time-scale"></a>Wyświetlanie skali czasu

Tablica jest podzielona na okresy, z których każdy jest reprezentowany jako węzeł (4). Węzły okresów są wyświetlane na osi pionowej, a oś pozioma reprezentuje skalę czasu (7) pokazującą długość okresów. Okres ma długość jednego dnia lub tygodnia. Długość okresu zależy od konfiguracji komórki roboczej zaznaczonej na tablicy harmonogramu Kanban (2). Dla każdego węzła okresu tablica harmonogramu Kanban wskazuje, ile zaplanowanych zadań Kanban będzie ładowanych w okresie. Wyświetlany jest również wskaźnik maksymalnej produktywności w okresie. Jeśli zaplanowana produktywność przekracza maksymalną dostępną przepustowość, okres jest uważany za przeciążony i pojawia się czerwony symbol ostrzegawczy. Zaplanowane zadanie Kanban pojawia się w okresie, który ma zaplanowane czasy rozpoczęcia i zakończenia (5). Długość zadania jest równa czasowi działania. Zadania Kanban są wyświetlane jako nakładające się w okresie, jeżeli ich czasy działań przekraczają czas taktu komórki roboczej.

### <a name="view-job-status"></a>Wyświetlanie stanu zadania

Więcej informacji o zadaniu Kanban jest dostępnych w etykietce narzędzia wyświetlanej po umieszczeniu wskaźnika myszy nad zadaniem. Symbol informuje o stanie zadania. Na przykład symbol zegara wskazuje, że zadanie Kanban jest zaległe.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>Używanie kolorów do wyświetlania tablicy harmonogramu Kanban

Aby wzmocnić wyrazistość podglądu oferowanego przez tablicę harmonogramu Kanban, można używać kolorów do odróżniania zadań Kanban. Kolor zadania Kanban jest konfigurowany w grupie harmonogramów produkcji oszczędnej, gdzie można agregować produkty, które powinny zostać wyprodukowane w tej samej sekwencji. Przycisk **Użyj kolorów motywu** znajdujący się na karcie **Tablica** w okienku akcji umożliwia przechodzenie między kolorami motywu aplikacji a kolorami skonfigurowanymi w grupie harmonogramów produkcji oszczędnej. Dla każdego okresu pasek zdolności produkcyjnych (6) wskazuje, dla ilu godzin dostępnych w okresie zostały załadowane zadania Kanban. Jeśli okres jest nadmiernie obciążony, pasek zdolności produkcyjnych jest grubszy i ma kolor czerwony. Wszystkie te funkcje są dostępne na karcie **Tablica** w okienku akcji (1) w górnej części strony **Tablica harmonogramu Kanban**.

## <a name="plan-unplanned-jobs"></a>Planowanie nieplanowanych zadań
Nieplanowane zadania Kanban można planować z okna dialogowego **Planowanie nieplanowanych zadań**. Aby otworzyć to okno dialogowe, kliknij przycisk **Nieplanowane zadania** pokazujący bieżącą liczbę niezaplanowanych zadań. Alternatywnie kliknij przycisk **Planowanie nieplanowanych zadań** na karcie **Tablica** w okienku akcji. Okno dialogowe pokazuje listę niezaplanowanych zadań Kanban dla komórki roboczej. Można użyć pola **Filtr**, aby filtrować według wszystkich pól w siatce. Na przykład można wyfiltrować zadania Kanban według określonego produktu. Po wyfiltrowaniu listy zadań, które chcesz zaplanować, zaznacz je na liście i kliknij przycisk **OK**. Aby planować zadania przy użyciu funkcji automatycznego planowania, w opcji **Automatyczne planowanie** ustaw wartość **Tak**. W takim przypadku zadania są planowane w okresach według ich terminów ukończenia. Można również planować zadania według okresów. Wystarczy zaznaczyć okres w polu **Okres**. Poniższa ilustracja zawiera przykładowe okno dialogowe **Planowanie nieplanowanych zadań**. 

![Okno dialogowe Planowanie nieplanowanych zadań](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Ustalanie kolejności zadań Kanban w tym samym okresie
W granicach okresu można zmienić kolejność jednego lub więcej wybranych zadań. Ta funkcja może być przydatna, jeśli chcesz nadać priorytet niektórym zadaniom w okresie. Można też ustalić kolejność dla zadań mających takie same atrybuty produktów w celu usprawnienia wykonywania zadań. Kolejność można zmieniać za pomocą operacji przeciągania i upuszczania lub za pomocą elementów menu **Wstecz** i **Dalej** na karcie **Tablica** w okienku akcji.

## <a name="reassign-kanban-jobs-across-periods"></a>Zmiana przypisania zadań Kanban między okresami
Zadania można przepisywać z jednego okresu do drugiego. Ta funkcja może być przydatna, jeśli okres jest przeciążony i chcesz przenieść część obciążenia do okresów z rezerwami zdolności produkcyjnych. Przypisanie zadań można zmieniać za pomocą operacji przeciągania i upuszczania lub za pomocą elementów menu **Następny okres** i **Poprzedni okres** na karcie **Tablica** w okienku akcji.

## <a name="open-the-kanban-schedule-board"></a>Otwieranie tablicy harmonogramu Kanban
Tablicę harmonogramu Kanban można otworzyć przy użyciu elementu menu na następujących stronach:

-   Strona **Strefa produkcyjna**
-   Strona **Planowanie zadań Kanban**
-   Strona **Wizualizacja przepływu produkcji**


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Planowanie zadań w systemie Kanban na potrzeby lean manufacturing](lean-manufacturing-kanban-job-scheduling.md)

