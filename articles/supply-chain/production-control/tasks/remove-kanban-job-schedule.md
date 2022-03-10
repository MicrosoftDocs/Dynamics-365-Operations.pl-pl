---
title: Usuwanie zadania systemu Kanban z harmonogramu
description: Ta procedura skupia się na usunięciu zaplanowanego zadania przetwarzania w systemie Kanban z harmonogramu poprzez przywrócenie stanu zadania do Niezaplanowane.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 838270189e08065f791c9e58888351025e0a6df8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573640"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Usuwanie zadania systemu Kanban z harmonogramu

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na usunięciu zaplanowanego zadania przetwarzania w systemie Kanban z harmonogramu poprzez przywrócenie stanu zadania do Niezaplanowane. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji.


## <a name="find-a-planned-kanban-job"></a>Znajdowanie zaplanowanego zadania w systemie Kanban
1. Wybierz kolejno opcje Kontrola produkcji > Kanban > Planowanie zadań Kanban.
2. W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz komórkę roboczą 1250.  
4. Kliknij opcję Wybierz.
5. W polu Wyświetl stan zadania zaznacz opcję „Zaplanowane”.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Usuwanie zaplanowanego zadania systemu Kanban z harmonogramu
1. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz zadanie, które ma stan Zaplanowane, na przykład zadanie z 19 grudnia 2012 roku.  
2. W okienku akcji kliknij opcję Plan.
3. Kliknij opcję Przywróć stan zadania.
4. Kliknij przycisk OK.
    * Spowoduje to przywrócenie bieżącego stanu zadania z „Zaplanowane” na „Niezaplanowane” i usunięcie go z tablicy procesów.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]