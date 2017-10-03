--- 
title: "Przenoszenie zaplanowanych zadań w systemie Kanban"
description: "Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5f101a097643fa027a667b9d6577fbe5d24ecd27
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Przenoszenie zaplanowanych zadań w systemie Kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji używających kart Kanban.


## <a name="select-scheduled-kanban-jobs"></a>Wybieranie zaplanowanych zadań w systemie Kanban
1. Wybierz kolejno opcje Produkcja > Kanban > Zarządzanie czasem zadania Kanban.
2. !MtCMR!W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie. áçêìõý!
3. Markér den valgte række på listen.
    * Zaznacz komórkę roboczą 1250.  
4. Kliknij opcję Wybierz.
5. Vælg 'Planlagt' i feltet Display job status.
    * Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zaplanowane zadania Kanban.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Przenoszenie zadań w systemie Kanban do innego okresu
1. Find og vælg den ønskede post på listen.
    * Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład na dzień 20 grudnia 2012 roku. Następnie przenieś zadanie do poprzedniego okresu.  
2. Klik på Previous period.
3. Klik på End.
    * Spowoduje to przeniesienie zadania na koniec listy zadań jako ostatniego zadania w poprzednim okresie.  
4. Find og vælg den ønskede post på listen.
    * Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład na dzień 18 grudnia 2012 roku. Następnie przenieś zadanie do następnego okresu.  
5. Klik på Next period.
6. Klik på Start.
    * Spowoduje to przeniesienie zadania na początek listy zadań jako pierwszego zadania w poprzednim okresie.  

## <a name="task-move-a-job-within-a-period"></a>Zadanie: Przenoszenie zadania wewnątrz okresu
1. Find og vælg den ønskede post på listen.
    * Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład drugie zadanie planowane na dzień 19 grudnia 2012 roku. Następnie przenieś zadanie w granicach planowanego okresu.  
2. Klik på Forward.
    * Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w dół na liście.  
3. Klik på Backward.
    * Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w górę na liście.  


