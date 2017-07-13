---
title: "Wykres Gantta do planowania zadań"
description: "Wykres Gantta zaprojektowano w taki sposób, aby umożliwiał planistom produkcji kontrolowanie i optymalizowanie planu produkcji. Wykres Gantta obrazuje przepływ operacji i pozwala łatwo korygować harmonogram produkcji, uwzględniając niedobory materiałów lub zasobów. Pomoże to planistom najlepiej wykorzystywać dostępne zasoby, minimalizować pracę w toku oraz optymalizować czasy realizacji zleceń produkcyjnych."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage
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
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 55631c4d588c699b9e47f73190d5b01d6da3b9ec
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# Wykres Gantta do planowania zadań
<a id="gantt-chart-for-job-scheduling" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Wykres Gantta zaprojektowano w taki sposób, aby umożliwiał planistom produkcji kontrolowanie i optymalizowanie planu produkcji. Wykres Gantta obrazuje przepływ operacji i pozwala łatwo korygować harmonogram produkcji, uwzględniając niedobory materiałów lub zasobów. Pomoże to planistom najlepiej wykorzystywać dostępne zasoby, minimalizować pracę w toku oraz optymalizować czasy realizacji zleceń produkcyjnych.

Wykres Gantta zaprojektowano w taki sposób, aby umożliwiał planistom produkcji kontrolowanie i optymalizowanie planu produkcji. Wykres Gantta obrazuje przepływ operacji i pozwala łatwo korygować harmonogram produkcji, uwzględniając niedobory materiałów lub zasobów. Pomoże to planistom najlepiej wykorzystywać dostępne zasoby, minimalizować pracę w toku oraz optymalizować czasy realizacji zleceń produkcyjnych.

Wykres Gantta jest graficzną reprezentacją zaplanowanych działań w określonym przedziale czasu. Działania są planowane dla zasobów mających zdolności produkcyjne określone w kalendarzu zdolności produkcyjnych. Na wykresie Gantta mogą być prezentowane następujące typy działań.

-   Zadania ze zleceń produkcyjnych, które mają zaplanowane zadania.
-   Zadania z planowanych zleceń produkcyjnych.
-   Działania projektu o typie Prognozy dla godzin w zaplanowanych zadaniach.

Wykres Gantta można otwierać w dwóch różnych widokach — **Widok zamówień** i **Widok zasobów**[.](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true)W **widoku zamówień** działania są zgrupowane w zleceniach produkcyjnych. Może to być użyteczne na przykład w sytuacji, gdy chcesz zachować podgląd wszystkich zadań należących do tych samych zleceń. W **widoku zasobów** wszystkie zadania są zgrupowane w poszczególnych zasobach. Ten widok może być przydatny podczas optymalizowania planu na poziomie zasobów, na przykład maszyny lub grupy maszyn. Wykresy Gantta pokazane na ilustracjach poniżej znajdują się w **widoku zamówień** i **widoku zasobów** z następującymi podstawowymi elementami:

1.  Działanie na wykresie Gantta
2.  Ikona niedoboru materiału
3.  Ikona dostępności materiału
4.  Ikona daty dostawy zamówienia
5.  Pasek zdolności produkcyjnych

## Widok zamówień
<a id="order-view" class="xliff"></a>

[![orderview](./media/orderview.png)](./media/orderview.png)

## Widok zasobów
<a id="resource-view" class="xliff"></a>
[![resview](./media/resview.png)](./media/resview.png)

## Działania
<a id="activities" class="xliff"></a>
Działania są wyświetlane jako paski i uporządkowane w siatce skali czasu z zaplanowanymi godzinami rozpoczęcia i zakończenia, tak że długości pasków są proporcjonalne do czasu potrzebnego do ukończenia działania. Działania są wyświetlane według skali czasu. Można zmienić skalę czasu w menu poprzez wybranie dat początkowej i końcowej oraz jednostki czasu, na przykład godzin lub dni. Dopasowując skalę czasu, można ustawić fokus na przedziale czasu, w którym chcesz zarządzać działaniami. 

Aby uzyskać lepszy przegląd, można użyć różnych opcji sterowania kolorem działań. Można skonfigurować pojedynczy kolor dla działań, użyć motywu kolorystycznego będącego ogólnym motywem kolorystycznym używanym w aplikacji albo określić, że kolor ma być kontrolowany przez kolory zleceń produkcyjnych. 

Przedział czasu działań ma cieniowane tło. Okresy z białym cieniowaniem wskazują przedział czasu o zdefiniowanych zdolnościach produkcyjnych zasobu dla działania, natomiast okresy z szarym cieniowaniem są przedziałami czasu bez zdefiniowanych zdolności produkcyjnych. 

Z lewej strony wykresu są dodatkowe informacje o działaniu, takie jak zasób, na bazie którego zaplanowano działanie, i numer zlecenia produkcyjnego. Połączenie między zadaniami należącymi do tego samego zlecenia jest wyświetlane ze strzałką. 

W oknie dialogowym działania można uzyskać więcej informacji na temat działania. Aby otworzyć okno dialogowe, kliknij dwukrotnie działanie lub wybierz menu **Informacje**. W oknie dialogowym działania widać zaplanowane daty rozpoczęcia i zakończenia oraz informacje czasowe mówiące o tym, które materiały mają być zużywane przez działanie. 

Działania można grupować przy użyciu funkcji Poziomy grupowania. Poziomy grupowania są hierarchiczne i mogą służyć do logicznego grupowania działań. Na przykład jeśli masz układ, w którym działania produkcyjne są pogrupowane według oddziałów, jednostek produkcyjnych, grup zasobów i zasobów, za pomocą funkcji Poziomy grupowania można zgrupować działania zgodnie z tym układem. Poziomy grupowania można rozwijać i zwijać indywidualnie lub zbiorczo dla wszystkich poziomów na wykresie, używając przycisków **Rozwiń wszystko** i **Zwiń wszystko** dostępnych w menu. Można także skonfigurować automatyczne rozwijanie i zwijanie poziomów grupowania po otwarciu wykresu.

### Dostępność materiałów
<a id="material-availability" class="xliff"></a>

Wykres Gantta można skonfigurować w taki sposób, aby dostarczał planiście szczegółowych informacjami o stanie materiałów dla poszczególnych działań. Może to być na przykład przydatne, jeśli materiał jest opóźniony i ma wpływ na wypełnienie planu produkcji. W takim przypadku problemy z materiałem zostaną wyróżnione na wykresie Gantta, aby pomóc planistom zrozumieć konsekwencje i wprowadzić niezbędne zmiany. 

Zadanie będzie wyświetlane z ikoną niedoboru materiału, jeśli zaplanowana data rozpoczęcia zadania jest późniejsza niż data dostępności materiałów zużywanych w zadaniu. Data dostępności materiałów jest obliczana na podstawie informacji o oznaczaniu transakcji w dynamicznym planie głównym. Na przykład ikona niedoboru materiałów pojawi się w zadaniu zużywającym materiał oznaczony względem zamówienia zakupu, w którym istnieje przyjęcie późniejsze niż planowana data rozpoczęcia zadania.

### Wskaźnik daty dostępności materiałów
<a id="indicator-of-material-availability-date" class="xliff"></a>

Podczas konfigurowania wykresu, aby wyświetlał zadania z niedoborami materiałów, może być również wyświetlana ikona pokazujące datę dostępność materiałów dla zadania. Ikona będzie wyświetlana tylko wtedy, gdy data dostępności materiałów mieści się w zdefiniowanym przedziale czasu wykresu. Jeśli data dostępności materiałów wykracza poza zdefiniowany przedział czasu, bardziej szczegółowe informacje o dostępności materiałów można pobrać z listy materiałów w oknie dialogowym zadania. Na liście jest także ikona pokazująca opóźnione materiały dla zadania. Można zmienić harmonogram wykonania zadania, używając daty dostępności materiałów jako daty rozpoczęcia.

### Wskaźnik daty dostawy zamówienia
<a id="indicator-of-order-delivery-date" class="xliff"></a>

Ta ikona wskazuje datę dostawy dla zlecenia produkcyjnego. Ikona jest widoczna tylko w widoku zamówień.

### Pasek zdolności produkcyjnych
<a id="capacity-bar" class="xliff"></a>

Wykres można skonfigurować tak, aby wyświetlał pasek zdolności produkcyjnych zasobu. Ten pasek obrazuje zdolności produkcyjne zasobu dla działania w zdefiniowanym przedziale czasu wykresu. Pasek zdolności produkcyjnych nie jest wyświetlany dla okresów, w których zasób nie jest zarezerwowany. W okresach, w których są zarezerwowane całe zdolności produkcyjne zasobu, pasek zdolności produkcyjnych ma jednolite wypełnienie. W okresach, w których zasób jest zarezerwowany ponad swoje zdolności produkcyjne, pasek jest grubszy i ma czerwony kolor. Na przykład jeśli dwa zadania nakładają się na siebie, pasek zdolności produkcyjnych będzie wskazywał rezerwację ponad możliwości w przedziale czasu, gdzie istnieje nałożenie. Pasek zdolności produkcyjnych jest aktualizowany dynamicznie podczas planowania zadania. Pasek zdolności produkcyjnych włącza się w menu **Pokaż pasek zdolności produkcyjnych**. Może być wyświetlany tylko w **widoku zasobów**. Aby uzyskać bardziej szczegółowy widok obciążenia zdolności produkcyjnych zasobu, należy użyć wykresu **Obciążenie zdolności produkcyjnych**, który można otworzyć z menu albo z menu kontekstowego wybranego działania.

## Planowanie zadań na wykresie Gantta
<a id="job-scheduling-in-the-gantt-chart" class="xliff"></a>
Wykres Gantta oferuje różne opcje umożliwiające wprowadzanie korekt w planie produkcji. Na wykresie Gantta można zmienić harmonogram działań za pomocą interakcji „przeciągnij i upuść” lub z menu harmonogramu. W procesie planowania należy wziąć pod uwagę zdolności produkcyjne zasobów, możliwości zasobów i ograniczenia materiałów.

### Planowanie zadania przy użyciu interakcji „przeciągnij i upuść”
<a id="schedule-a-job-as-a-drag-and-drop-interaction" class="xliff"></a>

Można zmienić harmonogram zadania w zdefiniowanym przedziale czasu za pomocą interakcji przeciągania i upuszczania. Harmonogram zadania można zmienić tylko w odniesieniu do tego samego zasobu oraz można planować tylko jedno zadanie na raz.

### Planowanie zadania z menu
<a id="schedule-a-job-from-the-menu" class="xliff"></a>

W menu **Planowanie zadań** można zaplanować jedno lub więcej zadań zaznaczonych na wykresie przy użyciu kierunku planowania oraz daty i godziny planowania. Są dostępne trzy kierunki planowania.

-   W przód od daty planowania
-   Wstecz od daty planowania
-   W przód od daty dostępności materiałów

Nie można zaplanować zadania poza przedziałem czasu zdefiniowanym na wykresie Gantta. Jeśli tak zrobisz, zadanie pozostanie nieplanowane i otrzymasz komunikat o błędzie „Nie można zaplanować zadania w załadowanym okresie.”

### Zaplanuj poprzednie zadania
<a id="schedule-previous-jobs" class="xliff"></a>

W sieci działań, takich jak zadania należące do tego samego zlecenia produkcyjnego, można za pomocą funkcji **Zaplanuj poprzednie zadania** zaplanować poprzednie zadania względem wybranego zadania w sieci. W poniższym przykładzie wyróżnione działanie jest wybranym zadaniem.

<table>
<tr>
<td>
Przed
</td>
<td rowspan=2>
<img src='./media/schprevjob3.png'/>
</td>
</tr>
<tr>
<td>
Po
</td>
</tr>
</table>

### Zaplanuj następne zadania
<a id="schedule-next-jobs" class="xliff"></a>

Za pomocą funkcji **Zaplanuj następne zadania** można zaplanować następne zadania względem wybranego zadania w sieci działań. W poniższym przykładzie wyróżnione działanie jest wybranym zadaniem.

<table>
<tr>
<td>
Przed
</td>
<td rowspan=2>
<img src='./media/schnxtjob.png'/>
</td>
</tr>
<tr>
<td>
Po
</td>
</tr>
</table>

### Zaplanuj zadania otaczające zadanie
<a id="schedule-around-job" class="xliff"></a>

Za pomocą funkcji **Zaplanuj zadania otaczające zadanie** można zaplanować następne i poprzednie zadania względem wybranego zadania w sieci działań. W poniższym przykładzie wyróżnione działanie jest wybranym zadaniem.

<table>
<tr>
<td>
Przed
</td>
<td rowspan=2>
<img src='./media/scharoundjob1.png'/>
</td>
</tr>
<tr>
<td>
Po
</td>
</tr>
</table>

### Rozmieść zadania
<a id="arrange-jobs" class="xliff"></a>

Za pomocą funkcji **Rozmieść** można uporządkować wybrane działania wobec tego samego zasobu. Działania te mogą się znajdować w tej samej sieci działań, ale mogą również należeć do różnych sieci. Podczas używania funkcji Rozmieść są eliminowane odstępy czasu między wybranymi działaniami. Ta funkcja może służyć do optymalizacji wykorzystania zdolności produkcyjnych zasobów.

<table>
<tr>
<td>
Przed
</td>
<td rowspan=2>
<img src='./media/arrangejobs1.png'/>
</td>
</tr>
<tr>
<td>
Po
</td>
</tr>
</table>

### Zmiana przypisania działań z jednego zasobu do innego
<a id="reassign-activities-from-one-resource-to-another" class="xliff"></a>

Zadanie można przepisać z jednego zasobu do innego. Może to być przydatne w sytuacjach, gdy maszyna jest uszkodzona lub zarezerwowana ponad swoje zdolności produkcyjne i trzeba znaleźć inny dostępny zasób, który może wykonać zadanie.

### Zmiana przypisania działania przy użyciu interakcji „przeciągnij i upuść”
<a id="reassigning-an-activity-as-a-drag-and-drop-interaction" class="xliff"></a>

W widoku **Zasób** można przepisać działanie do innego zasobu na wykresie Gantta poprzez przeciągnięcie i upuszczenie. W tym celu należy zaznaczyć wiersz, w którym działanie jest zaplanowane. Po zaznaczeniu wiersza można go przeciągnąć do zasobu na wykresie zgrupowanego na innym poziomie grupowania zasobów.

### Zmiana przypisania działania z menu Planowanie zadań
<a id="reassigning-an-activity-from-the-schedule-jobs-menu" class="xliff"></a>

Przypisanie zadania można zmienić z okna dialogowego **Zaplanuj zadanie** otwartego z menu **Zaplanuj zadanie**. Korzystając z tego menu, można tylko przepisać zadanie do zasobu, który jest już załadowany do wykresu Gantta. Jeśli zaznaczysz tylko jedno zadanie, lista rozwijana zasobu zostanie posortowana według odpowiednich zasobów. Jeśli zaznaczysz więcej zadań, na liście zasobów nie będzie żadnych informacji o odnośnych zasobach.

## Ładowanie dodatkowych zasobów do wykresu Gantta
<a id="load-additional-resources-to-the-gantt-chart" class="xliff"></a>
W **widok zasobów** masz możliwość wczytania dodatkowych zasobów do wykresu Gantta. Może to być przydatne, jeśli chcesz znaleźć alternatywny zasób dla zadania zaplanowanego na maszynie, która jest zarezerwowana ponad możliwości lub uszkodzona. Na stronie **Załaduj dodatkowe zasoby** zobaczysz listę zasobów dostępnych na dzień otwarcia listy. Jako pierwsze będą wyświetlane zasoby pasujące w odniesieniu do zadania wybranego na wykresie Gantta. Jeśli masz zaznaczonych wiele zadań, przed otwarciem listy nie będą wyświetlane żadne oznaczenia pasujących zasobów. Na stronie **Załaduj dodatkowe zasoby** można zaznaczyć jeden lub więcej zasobów, które zostaną wczytane do wykresu Gantta po potwierdzeniu wyboru. Jeśli dla wybranego zasobu nie ma żadnych zadań zaplanowanych w przedziale czasu wykresu Gantta, zasób zostanie umieszczony na poziomie grupowania zasobów u dołu listy działań na wykresie Gantta.

### Przechodzenie do wykresu Gantta
<a id="access-the-gantt-chart" class="xliff"></a>

Wykres Gantta można otworzyć z następujących stron.

| **Strona**                                                                                     | **Opis**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Lista i szczegóły zleceń produkcyjnych**                                                         | Na stronie **Lista i szczegóły zleceń produkcyjnych** można otworzyć wykres Gantta z poziomu jednego lub kilku wybranych zleceń. Otwarcie wykresu z elementu menu **Wykres Gantta** spowoduje załadowanie wszystkich zadań związanych z wybranymi zleceniami produkcyjnymi, ale również zadań z innych zleceń produkcyjnych zaplanowanych dla tych samych zasobów. Otwarcie wykresu z elementu menu **Wykres Gantta — szybki widok** spowoduje załadowanie wyłącznie zadań związanych z wybranymi zleceniami produkcyjnymi. W tym widoku nie jest możliwe planowanie zadań. |
| **Zasób**                                                                                 | Na stronie **Zasób** można otworzyć wykres Gantta z elementu menu **Wykres Gantta**. Po wybraniu tej opcji do wykresu zostaną załadowane wszystkie zadania zaplanowane dla zasobu w wybranym przedziale czasu.                                                                                                                                                                                                                                                                                                   |
| **Grupa zasobów**                                                                           | Na stronie **Grupa zasobów** można otworzyć wykres Gantta z elementu menu **Wykres Gantta**. Po wybraniu tej opcji wszystkie zasoby wybrane dla zasobu w grupie zasobów zostaną wyświetlone w wybranym przedziale czasu.                                                                                                                                                                                                                                                                                    |
| **Wykresy Gantta**                                                                             | Na stronie **Wykresy Gantta** można skonfigurować wykresy Gantta z podziałem na zasoby i grupy zasobów. Na przykład jeśli chcesz kontrolować działania produkcyjne dla określonych zbiorów zasobów lub grup zasobów, można zdefiniować odpowiednie konfiguracje na stronie **Wykresy Gantta**. Następnie można otworzyć wykres Gantta z każdej konfiguracji.                                                                                                                                                    |
| **Prognozy dla godzin** (projekt)                                                                 | Działania projektu o typie **Prognozy dla godzin** można planować jako zadania wykorzystujące zasoby. Na stronie **Prognoza dla godzin** w menu **Planowanie** można otworzyć wykres Gantta dla zlecenia, aby wyświetlić działania projektu o typie Prognozy dla godzin w zaplanowanych zadaniach.                                                                                                                                                                                                                                                             |
| **Zadania do zakończenia** (lista w obszarze roboczym **Zarządzanie halą produkcyjną**)                      | Lista Zadania do zakończenia w obszarze roboczym **Zarządzanie halą produkcyjną** pokazuje zadania ze zleceń i szarż produkcyjnych, które są w toku dla wybranych zasobów w obszarze roboczym. Za pomocą elementu menu **Wykres Gantta** można otworzyć wykres Gantta, do którego będą załadowane wszystkie zadania zaznaczone na liście.                                                                                                                                                                                |
| **Zlecenia produkcyjne do zwolnienia** (otwierana z obszaru roboczego **Zarządzanie halą produkcyjną**) | Strona Zlecenia produkcyjne do zwolnienia jest otwierana z obszaru roboczego **Zarządzanie halą produkcyjną**. Ta strona pokazuje zaplanowane zlecenia i szarże produkcyjne oczekującej na zwolnienie. Na tej stronie można otworzyć wykres Gantta dla wybranych zleceń produkcyjnych.                                                                                                                                                                                                                                                        |




