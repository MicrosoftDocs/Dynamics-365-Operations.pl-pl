---
title: Zmienianie reguł Kanban dla zadań procesu
description: Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba77197f51b871f452c2aa94320aa2a68cf314df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255380"
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