---
title: Tworzenie harmonogramu zadań w systemie Kanban
description: Ta procedura skupia się na planowaniu zadań przetwarzania w systemie Kanban dla określonej komórki roboczej.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cab3af0802ae6fa942460cfdd9c0819e1d31d4b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579095"
---
# <a name="schedule-kanban-jobs"></a>Tworzenie harmonogramu zadań w systemie Kanban

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na planowaniu zadań przetwarzania w systemie Kanban dla określonej komórki roboczej. Warunkiem wstępnym utworzenia tej procedury jest wykonanie procedury „Przygotowanie zadania przetwarzania w systemie Kanban, gdy materiały są niedostępne”. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Zadanie jest przeznaczone dla kierownika zakładu produkcyjnego i planisty produkcji używających kart Kanban.


## <a name="select-kanban-jobs-for-a-work-cell"></a>Wybieranie zadań w systemie Kanban dla komórki roboczej
1. Wybierz kolejno opcje Kontrola produkcji > Kanban > Planowanie zadań Kanban.
2. Rozwiń pole informacji Zdolności produkcyjne w okresie.
    * Rozwiń pole informacji Kanban.  
3. W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście oznacz wybrany wiersz.
    * Zaznacz komórkę roboczą 1250. Spowoduje to wyfiltrowanie widoku, aby wyświetlić tylko zadania komórki roboczej 1250.  
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij opcję Wybierz.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>Planowanie zadania w systemie Kanban na pierwszy dostępny okres
1. Na liście oznacz wybrany wiersz.
    * Zaznacz pierwszy wiersz na liście, który ma status Niezaplanowane. Ikona z kropkami w polu Stan zadania wskazuje, że zadanie jest niezaplanowane.  
2. Kliknij opcję Harmonogram.
    * Spowoduje to zaplanowanie zadania w systemie Kanban na pierwszy dostępny okres.  
    * Należy zauważyć, że zadanie w systemie Kanban zostało przeniesione na koniec listy, ponieważ dodano je do okresu rozpoczynającego się dzisiaj.  
    * Jeśli okres rozpoczynający się od dnia dzisiejszego jest w pełni zarezerwowany, zadanie zostanie przeniesione do pierwszego dostępnego okresu.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>Planowanie dwóch zadań w systemie Kanban na określony dzień
1. Na liście zaznacz wiersz 1.
    * Powinno być widać, że w polu Stan zadania pierwszy wiersz ma stan Niezaplanowane.  
2. Na liście zaznacz wiersz 2.
    * Powinno być widać, że w polu Stan zadania drugi wiersz ma stan Niezaplanowane. Teraz dwa pierwsze zdania są zaznaczone.  
3. Kliknij opcję Harmonogram od daty, aby otworzyć rozwijane okno dialogowe.
4. Zaznacz lub wyczyść pole wyboru Zastąpienie reakcji na niedobór zdolności produkcyjnych.
    * Ta opcja umożliwia zastąpienie domyślnej reakcji na niedobór zdolności produkcyjnych.  
5. W polu Reakcja na niedobór zdolności produkcyjnych zaznacz opcję „Dodaj do zgłaszanego okresu”.
    * Ta opcja zapewnia dodanie zadania do żądanego okresu, nawet wtedy, gdy komórka robocza jest przeciążona.  
6. Kliknij opcję Harmonogram.
    * Należy zauważyć, że oba zadania zostały dodane do żądanego okresu.  
    * W tej sekcji Zdolności produkcyjne w okresie widać obciążenie dla każdego okresu. Pola Zużycie pokazuje zużycie zaplanowane w tym okresie. Jeśli planowane zużycie jest wyższe niż zdolności produkcyjne dostępne w tym okresie, zostanie zaznaczone przeciążone zużycie.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]