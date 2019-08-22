---
title: Usuwanie zadania systemu Kanban z harmonogramu
description: Ta procedura skupia się na usunięciu zaplanowanego zadania przetwarzania w systemie Kanban z harmonogramu poprzez przywrócenie stanu zadania do Niezaplanowane.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0018bafd731ac7a0d74a41869251a2897d553de
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838566"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Usuwanie zadania systemu Kanban z harmonogramu

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

