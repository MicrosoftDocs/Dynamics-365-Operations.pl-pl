---
title: "Wizualne planowanie zadań na potrzeby lean manufacturing"
description: "Ten temat zawiera informacje o tablicy harmonogramu Kanban, której planista produkcji może używać do kontrolowania i optymalizowanie planu produkcji dla zadań Kanban."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisulaization
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: johanhoffmann
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 1a3f43c2812cdf1c9f5c564bc86abe4fcc90b8a3
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017

---

# Wizualne planowanie zadań na potrzeby lean manufacturing
<a id="visual-scheduling-for-lean-manufacturing" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o tablicy harmonogramu Kanban, której planista produkcji może używać do kontrolowania i optymalizowanie planu produkcji dla zadań Kanban.

Ten temat zawiera informacje o tablicy harmonogramu Kanban, której planista produkcji może używać do kontrolowania i optymalizowanie planu produkcji dla zadań Kanban.

Tablica harmonogramu Kanban umożliwia planiście produkcji kontrolowanie i optymalizowanie planu produkcji dla zadań Kanban. Nadaje przejrzystości przepływowi zadań w systemie Kanban i stanowi dla planisty produkcji narzędzie, które optymalizuje i dostosowuje plan produkcji dla komórki roboczej produkcji oszczędnej.

## Wizualne planowanie zadań w systemie Kanban
<a id="visual-scheduling-of-kanban-jobs" class="xliff"></a>
Zadanie Kanban może się składać z jednego lub wielu zadań Kanban. Istnieją dwa typy zadań Kanban:

-   Przetwarzaj
-   Przenoszenie

Planować można tylko zadania typu **Przetwarzanie**. Zadanie w systemie Kanban i jego właściwości, takie jak czas działania, są definiowane w przepływie Kanban produkcji. W przepływie Kanban produkcji zadanie Kanban jest również przypisane do komórki roboczej. Dzienne zdolności produkcyjne komórki roboczej są obliczana na podstawie zdolności produkcyjnych komórki ustawionych w grupie zasobów. Następnie są korygowane przez dzienny czas pracy w powiązanym kalendarzu. Podczas planowania zadania Kanban są dla niego wczytywane zdolności produkcyjne komórki roboczej. Tablica harmonogramu Kanban zawiera następujące główne elementy:

-   Graficzny przegląd planu produkcji w komórce roboczej produkcji oszczędnej. Ten przegląd pokazuje zaplanowane zadania przetwarzania Kanban w zdefiniowanych okresach.
-   Narzędzie umożliwiające planowanie niezaplanowanych zadań Kanban i zmianę harmonogramów uprzednio zaplanowanych zadań.

## Tablica harmonogramu Kanban
<a id="kanban-schedule-board" class="xliff"></a>
Strona **Tablica harmonogramu Kanban** zawiera siedem głównych elementów, jak pokazano na poniższej ilustracji. 

![Tablica harmonogramu Kanban](./media/kanban-schedule-board-1024x554.png)
1.  Okienko akcji
2.  Pola filtrowania
3.  Przycisk nieplanowanych zadań
4.  Węzeł okresu
5.  Zadanie w systemie Kanban
6.  Pasek zdolności produkcyjnych
7.  Skala czasu

### Wyświetlanie skali czasu
<a id="view-the-time-scale" class="xliff"></a>

Tablica jest podzielona na okresy, z których każdy jest reprezentowany jako węzeł (4). Węzły okresów są wyświetlane na osi pionowej, a oś pozioma reprezentuje skalę czasu (7) pokazującą długość okresów. Okres ma długość jednego dnia lub tygodnia. Długość okresu zależy od konfiguracji komórki roboczej zaznaczonej na tablicy harmonogramu Kanban (2). Dla każdego węzła okresu tablica harmonogramu Kanban wskazuje, ile zaplanowanych zadań Kanban będzie ładowanych w okresie. Wyświetlany jest również wskaźnik maksymalnej produktywności w okresie. Jeśli zaplanowana produktywność przekracza maksymalną dostępną przepustowość, okres jest uważany za przeciążony i pojawia się czerwony symbol ostrzegawczy. Zaplanowane zadanie Kanban pojawia się w okresie, który ma zaplanowane czasy rozpoczęcia i zakończenia (5). Długość zadania jest równa czasowi działania. Zadania Kanban są wyświetlane jako nakładające się w okresie, jeżeli ich czasy działań przekraczają czas taktu komórki roboczej.

### Wyświetlanie stanu zadania
<a id="view-job-status" class="xliff"></a>

Więcej informacji o zadaniu Kanban jest dostępnych w etykietce narzędzia wyświetlanej po umieszczeniu wskaźnika myszy nad zadaniem. Symbol informuje o stanie zadania. Na przykład symbol zegara wskazuje, że zadanie Kanban jest zaległe.

### Używanie kolorów do wyświetlania tablicy harmonogramu Kanban
<a id="use-colors-to-view-the-kanban-schedule-board" class="xliff"></a>

Aby wzmocnić wyrazistość podglądu oferowanego przez tablicę harmonogramu Kanban, można używać kolorów do odróżniania zadań Kanban. Kolor zadania Kanban jest konfigurowany w grupie harmonogramów produkcji oszczędnej, gdzie można agregować produkty, które powinny zostać wyprodukowane w tej samej sekwencji. Przycisk **Użyj kolorów motywu** znajdujący się na karcie **Tablica** w okienku akcji umożliwia przechodzenie między kolorami motywu aplikacji a kolorami skonfigurowanymi w grupie harmonogramów produkcji oszczędnej. Dla każdego okresu pasek zdolności produkcyjnych (6) wskazuje, dla ilu godzin dostępnych w okresie zostały załadowane zadania Kanban. Jeśli okres jest nadmiernie obciążony, pasek zdolności produkcyjnych jest grubszy i ma kolor czerwony. Wszystkie te funkcje są dostępne na karcie **Tablica** w okienku akcji (1) w górnej części strony **Tablica harmonogramu Kanban**.

## Planowanie nieplanowanych zadań
<a id="plan-unplanned-jobs" class="xliff"></a>
Nieplanowane zadania Kanban można planować z okna dialogowego **Planowanie nieplanowanych zadań**. Aby otworzyć to okno dialogowe, kliknij przycisk **Nieplanowane zadania** pokazujący bieżącą liczbę niezaplanowanych zadań. Alternatywnie kliknij przycisk **Planowanie nieplanowanych zadań** na karcie **Tablica** w okienku akcji. Okno dialogowe pokazuje listę niezaplanowanych zadań Kanban dla komórki roboczej. Można użyć pola **Filtr**, aby filtrować według wszystkich pól w siatce. Na przykład można wyfiltrować zadania Kanban według określonego produktu. Po wyfiltrowaniu listy zadań, które chcesz zaplanować, zaznacz je na liście i kliknij przycisk **OK**. Aby planować zadania przy użyciu funkcji automatycznego planowania, w opcji **Automatyczne planowanie** ustaw wartość **Tak**. W takim przypadku zadania są planowane w okresach według ich terminów ukończenia. Można również planować zadania według okresów. Wystarczy zaznaczyć okres w polu **Okres**. Poniższa ilustracja zawiera przykładowe okno dialogowe **Planowanie nieplanowanych zadań**. 

![Okno dialogowe Planowanie nieplanowanych zadań](./media/plan-unplanned-jobs-1024x564.png)

## Ustalanie kolejności zadań Kanban w tym samym okresie
<a id="sequence-kanban-jobs-within-the-same-period" class="xliff"></a>
W granicach okresu można zmienić kolejność jednego lub więcej wybranych zadań. Ta funkcja może być przydatna, jeśli chcesz nadać priorytet niektórym zadaniom w okresie. Można też ustalić kolejność dla zadań mających takie same atrybuty produktów w celu usprawnienia wykonywania zadań. Kolejność można zmieniać za pomocą operacji przeciągania i upuszczania lub za pomocą elementów menu **Wstecz** i **Dalej** na karcie **Tablica** w okienku akcji.

## Zmiana przypisania zadań Kanban między okresami
<a id="reassign-kanban-jobs-across-periods" class="xliff"></a>
Zadania można przepisywać z jednego okresu do drugiego. Ta funkcja może być przydatna, jeśli okres jest przeciążony i chcesz przenieść część obciążenia do okresów z rezerwami zdolności produkcyjnych. Przypisanie zadań można zmieniać za pomocą operacji przeciągania i upuszczania lub za pomocą elementów menu **Następny okres** i **Poprzedni okres** na karcie **Tablica** w okienku akcji.

## Otwieranie tablicy harmonogramu Kanban
<a id="open-the-kanban-schedule-board" class="xliff"></a>
Tablicę harmonogramu Kanban można otworzyć przy użyciu elementu menu na następujących stronach:

-   Strona **Strefa produkcyjna**
-   Strona **Planowanie zadań Kanban**
-   Strona **Wizualizacja przepływu produkcji**


Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Lean manufacturing — planowanie zadań w systemie Kanban](lean-manufacturing-kanban-job-scheduling.md)


