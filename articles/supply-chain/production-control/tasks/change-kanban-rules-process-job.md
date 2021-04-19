---
title: Zmienianie reguł Kanban dla zadań procesu
description: Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2bdbbbf8a8b3d1596c251224cba996c0631050c4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829313"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Zmienianie reguł Kanban dla zadań procesu

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]