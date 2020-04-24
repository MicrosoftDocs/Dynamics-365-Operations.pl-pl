---
title: Planowanie zadań w systemie Kanban dla produkcji oszczędnej
description: Ten artykuł zawiera informacje o kontroli wizualnej nad planowaniem zadań Kanban oraz o różnych sposobach planowania zadań w systemie Kanban.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18326fdc931faf1aecd4b8b69fefed8b90c191ab
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211475"
---
# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Planowanie zadań w systemie Kanban dla produkcji oszczędnej

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o kontroli wizualnej nad planowaniem zadań Kanban oraz o różnych sposobach planowania zadań w systemie Kanban.  

Strona **Planowanie zadań Kanban** daje wizualną kontrolę nad harmonogramami komórek produkcji oszczędnej. Umożliwia wyświetlenie wszystkich zadań w systemie Kanban i oferuje wiele możliwości filtrowania. Z tej strony można przejść do wszystkich innych stron, które odnoszą się do konfiguracji i wykonania karty Kanban.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Automatyczne planowanie zadań w systemie Kanban
Planowanie może być uruchomione automatycznie, jeśli parametr **Ilość w automatycznym planowaniu** jest ustawiony w regule Kanban. Po ustawieniu parametru **Ilość w automatycznym planowaniu** na **1** zadania w systemie Kanban są planowane natychmiast po utworzeniu. Efektem jest seria operacji „first pull, first serve”. Jeśli wartość parametru **Ilość w automatycznym planowaniu** jest większa niż 1, zadania Kanban są grupowane, zanim zostaną zaplanowane. 

Takie podejście pozwala ograniczyć rozmiar zadań Kanban poniżej rzeczywistego rozmiaru partii ekonomicznej. Na przykład rozmiar partii ekonomicznej dla określonego towaru (lub rodziny towarów) wynosi 30. Zamiast tworzyć karty Kanban z ilością produktu 30, można skonfigurować regułę Kanban z ilością produktu 10 i wartością **3** dla parametru **Ilość w automatycznym planowaniu**. Choć harmonogram automatycznego planowania planuje zadania w systemie Kanban dla komórki roboczej tylko wtedy, gdy istnieją trzy nieplanowanych zadania, dla osoby planującej i kierownika hali produkcyjnej jest całkowicie jasne, że dwa nieplanowane zadania mogą oczekiwać na wykonanie. Osoba planująca lub kierownik hali produkcyjnej mogą następnie przenieść te dwa zadania do produkcji, planując je ręczne lub tworząc dodatkowe karty Kanban.

## <a name="manual-scheduling"></a>Planowanie ręczne
Do obsługi ręcznego planowania system Microsoft Dynamics AX 2012 oferuje tablicę planowania kanban. Ręczne planowanie może być połączone z planowaniem automatycznym. Tablica planowania kanban pozwala planować zadania, usuwać je z harmonogramu, zmieniać ich kolejność lub przesuwać między okresami. Zadania oparte na regule kanban, w których wartość **Automatyczne planowanie** jest większa od **0** mogą być ręcznie usuwane z harmonogramu. Zadania te zostaną jednak ponownie zaplanowane w następnym zdarzeniu planowania automatycznego (tj. podczas tworzenia nowej karty kanban). Następujące opcje są dostępne do planowania ręcznego:

-   **Harmonogram** planuje wybrane zadania według ich terminu. (Ta opcja jest podobna do automatycznego planowania).
-   **Harmonogram w przód od daty** próbuje zaplanować wybrane zadania według ich terminu ale ogranicza wynik za pomocą określonej najwcześniejszej daty początkowej.
-   **Wstecz** przenosi wybrane zaplanowane zadania wstecz w sekwencji w okresie.
-   **Wstecz** przenosi wybrane zaplanowane zadania w przód w sekwencji w okresie.
-   **Poprzedni okres** przenosi wybrane zaplanowane zadania na początek lub koniec poprzedniego okresu.
-   **Następny okres** przenosi wybrane zaplanowane zadania na początek lub koniec następnego okresu.
-   **Plan** &gt; **Przywróć stan zadania** umożliwia usunięcie zadania z harmonogramu.

## <a name="lean-scheduling-groups"></a>Grupy planowania produkcji oszczędnej
Każdy kolor odpowiada grupie planowania produkcji oszczędnej. Grupy planowania produkcji oszczędnej mogą być swobodnie definiowana jako ogólne grupy lub grupy należące do jednej komórki roboczej. Towary i wymiary mogą być swobodnie przypisywane do grupy planowania. Na przykład w komórce Malowanie grupa planowania może odpowiadać kolorowi produktu. W pracy opartej na konkretnych wymaganiach narzędziowych, towary mogą być pogrupowane według wymaganego narzędzia, a komórka robocza pakowania może grupować towary według szablonu opakowań. Stosowanie kolorów w grupach planowania produkcji oszczędnej nie jest wymagane, ale zalecane. Kolory poprawiają widoczność stanów planu. Można na przykład łatwo zobaczy, które kolory są produkowane którego dnia, i szybko ustalić sposób ewentualnej optymalizacji tej pracy.

## <a name="work-cell-capacity-and-period-capacity"></a>Zdolności produkcyjne dla komórki roboczej i okresu
Zdolności produkcyjne komórki roboczej produkcji oszczędnej są zawsze współbieżne. Innymi słowy w komórce roboczej może być aktywnych wiele zadań w tym samym czasie. Zdolności produkcyjne mogą być śledzone w dwóch trybach: produktywność i godziny.

### <a name="throughput"></a>Produktywność

Zdolności produkcyjne komórki roboczej są definiowane za pomocą średniej produktywności w okresie referencyjnym (standardowy dzień roboczy, tydzień lub miesiąc). Rzeczywiste zdolności produkcyjne na dzień lub tydzień są następie obliczane na podstawie godzin pracy z kalendarza przypisanego do komórki roboczej. Zdolności produkcyjne załadowane przez zadanie to ilość zadania skorygowana przez współczynnik produktywności towaru w komórce roboczej.

### <a name="hours"></a>Godziny

Dostępne zdolności produkcyjne według dni lub tygodni zależą od kalendarza przypisanego do komórki roboczej. Zdolności produkcyjne załadowane przez zadanie to cykl czasu działania skorygowany przez ilość (domyślna a rzeczywista ilość działania) oraz współczynnik produktywności towaru w komórce roboczej.

#### <a name="period-capacity-factbox"></a>Pole informacyjne zdolności produkcyjnych w okresie

Strona listy **Planowania zadań Kanban** zawiera pole informacyjne pokazujące dostępne i zarezerwowane zdolności produkcyjne w okresie dla wybranej komórki roboczej. W zależności od wybranego okresu harmonogramu w modelu przepływu produkcji, okresy pokazują dni lub tygodnie.

<a name="additional-resources"></a>Dodatkowe zasoby
--------



