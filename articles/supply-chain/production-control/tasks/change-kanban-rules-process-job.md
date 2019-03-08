---
title: Zmienianie reguł Kanban dla zadań procesu
description: Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38d9ff0a7d6aeb0a589fd6b9ab34b818c46644cc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "314953"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Zmienianie reguł Kanban dla zadań procesu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban. Jest to przydatne do wyrównywania obciążenia zasobów lub w przypadku awarii. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla planisty w firmie stosującej zasady produkcji oszczędnej odpowiedzialnego za strumień wartości.


## <a name="copy-kanban-rule"></a>Kopiowanie reguły Kanban
1. Przejdź do okna Reguły Kanban.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz regułę Kanban zdarzeń 000022 dla produktu L0001.  
3. Kliknij opcję Duplikuj regułę Kanban.
4. Kliknij przycisk OK.

## <a name="change-kanban-rule"></a>Modyfikacja reguły Kanban
1. Zamknij stronę.
2. Przejdź do okna Planowanie zadań Kanban.
3. Na liście oznacz wybrany wiersz.
    * Wybierz wiersz z kartą Kanban 000177.  
4. Kliknij opcję Użyj alternatywnej reguły Kanban.
5. Kliknij przycisk Dalej.
6. W polu Reguła Kanban wprowadź lub wybierz wartość.
    * Wybierz utworzoną wcześniej regułę Kanban. Jest to reguła Kanban o najwyższym numerze.  
7. Kliknij przycisk Zakończ.
    * Teraz zadanie w systemie Kanban używa innej reguły Kanban. Może to być przydatne do wyrównywania obciążenia komórek roboczych.  

