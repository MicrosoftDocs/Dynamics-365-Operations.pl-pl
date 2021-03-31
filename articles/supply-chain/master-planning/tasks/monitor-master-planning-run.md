---
title: Monitorowanie przebiegu planowania głównego
description: W tym temacie opisano sposób, w jaki terminarz produkcji może sprawdzić, czy proces planowania głównego jest w toku.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2dea87ac106e79339b8cb6bb2c28e36e35de4a1a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226106"
---
# <a name="monitor-a-master-planning-run"></a>Monitorowanie przebiegu planowania głównego

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Użycie wykresu Gantta do wizualizacji postępu planowania głównego

Na stronie **przegląd postępu planowania głównego** można wyświetlić szczegóły historycznego planowania głównego jako wykresu Gantta. Ta funkcja może pomóc w zrozumieniu czasu poświęcanego na różne fazy planowania głównego. W przypadku bieżącego aktywnego zadania planowania na stronie **przegląd postępu planowania głównego** można używać strony do śledzenia postępu i wyświetlania szacowanego czasu pozostałego.

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a>Włączanie funkcji wizualizacji postępu planowania głównego i korzystanie z niej

Aby skorzystać z tej funkcji, wykonaj następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** na liście na **nowej** karcie Wybierz opcję **Wizualizacja postępu planowania głównego** z listy. Jeśli funkcja nie jest wyświetlana na **nowej** karcie, sprawdź, czy **nie jest włączona** i **wszystkie** karty.
1. Wybierz **Włącz teraz**. Możesz też wybrać **harmonogram**, a następnie wybrać czas, w którym funkcja ma być włączona

Na stronie **przegląd postępu planowania głównego** planowania głównego można wyświetlić zarówno zadania planowania historycznego, jak i aktywne zadania planowania. 

Aby wyświetlić zadania planowania historycznego, dostępne są dwie opcje 

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**, a następnie w okienku akcji wybierz opcję **historia**. Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**
1. Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne** na kafelku planowanie główne kliknij pozycję **historia** Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**

Aby wyświetlić zadania planowania aktywnego, dostępne są dwie opcje 
1. Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne**, w okienku akcji wybierz **Proces planowania produktów niegotowych**. Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**.
1. Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne** na kafelku planowanie główne kliknij pozycję **Zobacz postęp**. Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**

Uwaga zadania aktywne można wyświetlać tylko w przypadku przetwarzania zadania planowania.

### <a name="analyze-a-master-planning-job"></a>Analizowanie zadania planowania głównego

Na wykresie Gantta można rozwinąć każdy z poniższych procesów planowania, aby wyświetlić dodatkowe szczegóły dotyczące czasu trwania:

- Przygotowanie
- Usuwanie i wstawianie danych
- Planowanie zapotrzebowania
- Opóźnienia
- Komunikaty akcji
- Finalizacja
- Automatyczne akceptowanie

Wykres Gantta jest przydatnym narzędziem, jeśli ma być wyświetlany wpływ użycia komunikatów akcji.

#### <a name="navigation-in-the-gantt-chart"></a>Nawigacja na wykresie Gantta

- Aby rozwinąć zaznaczoną grupę i wyświetlić szczegóły, należy wybrać znak plus (**+**) w widoku drzewa.
- Aby zwinąć zaznaczoną grupę, należy wybrać znak minus (**-**) w widoku drzewa.
- Do nawigacji można wykorzystać klawiaturę. Za pomocą klawiszy **Strzałka w górę** i **Strzałka w dół** można przechodzić między wierszami. Za pomocą klawiszy **Strzałka w prawo** i **Strzałka w lewo** można rozwijać i zwijać grupy.
- Aby otworzyć lub zamknąć wszystkie poziomy na wykresie Gantta, wybierz opcję **Rozwiń wszystkie** lub **Zwiń wszystko**.
- Aby wyświetlić odpowiedni czas przetwarzania, umieść wskaźnik myszy nad zadaniem. (Zadania są najniższym poziomem wykresu Gantta.)

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>Umożliwia wyświetlenie dodatkowego przebiegu planowania głównego w celu porównania zadań

Po wybraniu zadania planowania głównego w polu **Pokaż dodatkowe uruchomienie planowania głównego** można wyświetlić dodatkowy przebieg planowania głównego na wykresie Gantta i porównać te dwa zadania.

#### <a name="bom-level-display"></a>Wyświetlanie na poziomie BOM

Poziomy BOM są wyświetlane w różny sposób do planowania zapotrzebowania, opóźnień, akcji i akceptacji.

- **Planowanie zapotrzebowania** — poziomy BOM są wyświetlane zgodnie z oczekiwaniami. Są one obliczane od góry do dołu.

    **Przykład:** poziom BOM 0, 1, 2

- **Opóźnienia** — poziomy BOM są wyświetlane jako poziomy BOM planowania zapotrzebowania pomnożone przez-1. (Innymi słowy, ze znakiem ujemnym.)

    **Przykład:** poziom BOM –2, –1, 0

- **Komunikat akcji** — poziomy BOM są wyświetlane zgodnie z oczekiwaniami. Są one obliczane od góry do dołu.

    **Przykład:** poziom BOM 0, 1, 2

- **Automatyczne akceptowanie** — poziomy BOM są wyświetlane jako 999 minus poziom BOM planowania zapotrzebowania.

    **Przykład:** poziom BOM 999, 998, 997

W poniższej tabeli podsumowano zachowanie.

| Wyświetlany poziom BOM | Pozycja gotowa | Składnik podrzędny | Surowiec |
|---|---|---|---|
| Planowanie zapotrzebowania | 0 | 1 | 2 |
| Opóźnienia | 0 | -1 | -2 |
| Komunikat akcji | 0 | 1 | 2 |
| Automatyczne akceptowanie | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Postęp wizualizacji

W przypadku wyświetlenia aktualnie uruchomionego zadania planowania głównego postęp jest pokazywany za pośrednictwem kolorów na wykresie Gantta. Poniższe kolory dotyczą niebieskiego motywu. W przypadku innych kompozycji kolorów kolory są różne.

- **Ciemnoniebieski** — zadania planowania zakończonego
- **Pomarańczowy** — zadanie, które jest obecnie w toku.
- **Jasnoniebieski** — oszacowanie pozostałych zadań.

Kolor jest pokazywany tylko na najniższym poziomie na wykresie Gantta. Wybierz opcję **Rozwiń wszystko**, aby wyświetlić wszystkie zadania w ramach zadania planowania głównego. Oszacowanie pozostałych zadań jest oparte na historycznych zadaniach planowania głównego.

## <a name="run-master-planning-and-track-processing-time"></a>Uruchamianie planowania głównego i czasu przetwarzania śledzenia

1. Na domyślnym pulpicie nawigacyjnym wybierz opcję **Planowanie główne**.
1. W polu **Plan** wprowadź lub wybierz wartość.
1. Wybierz opcję **Uruchom**.
1. W opcji **Śledź czas przetwarzania** ustaw wartość **Tak**.
1. W polu **Liczba wątków** wprowadź liczbę.
1. W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.
1. W siatce wybierz wiersz, w którym **pole** w polu ma wartość **kod towaru**.
1. Wprowadź wartość w polu **Kryterium**.
1. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]