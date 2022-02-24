---
title: Przenoszenie zaplanowanych zadań w systemie Kanban
description: Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu.
author: ChristianRytt
manager: tfehr
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2769a7d519e12613796025b658db0b08cdfc4fde
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961647"
---
# <a name="move-scheduled-kanban-jobs"></a>Przenoszenie zaplanowanych zadań w systemie Kanban

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji używających kart Kanban.

## <a name="select-scheduled-kanban-jobs"></a>Wybieranie zaplanowanych zadań w systemie Kanban. 

1. Wybierz kolejno opcje **Kontrola produkcji > Kanban > Planowanie zadań Kanban**. 

2. W polu **Komórka robocza** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie. 

3. Na liście oznacz wybrany wiersz. 
   - Zaznacz komórkę roboczą 1250. 
4. Kliknij opcję **Wybierz**. 

5. W polu **Wyświetl stan zadania** zaznacz opcję **Zaplanowane**. Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zaplanowane zadania Kanban. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Przenoszenie zadań w systemie Kanban do innego okresu. 

1. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz zadanie, które w polu **Planowany okres** ma stan **zaplanowanego zadania**, na przykład na dzień 20 grudnia 2012 roku. Następnie przenieś zadanie do poprzedniego okresu. 

2. Kliknij opcję **Poprzedni okres**. 

3. Kliknij **Zakończ**, aby przenieść zadanie na koniec listy zadań jako ostatniego zadanie w poprzednim okresie. 

4. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz zadanie, które w polu **Planowany okres** ma stan **zaplanowanego zadania**, na przykład na dzień 18 grudnia 2012 roku. Następnie przenieś zadanie do następnego okresu. 

5. Kliknij opcję **Następny okres**. 

6. Kliknij **Start**, aby przenieść zadanie na początek listy zadań jako pierwsze zadanie w poprzednim okresie. 

## <a name="move-a-job-within-a-period"></a>Przenoszenie zadania wewnątrz okresu. 

1. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz zadanie, które w polu **Planowany okres** ma stan zaplanowanego zadania, na przykład drugie zadanie planowane na dzień 19 grudnia 2012 roku. Następnie przenieś zadanie w granicach planowanego okresu. 

2. Kliknij opcję **W przód**. Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w dół na liście. 

3. Kliknij opcję **Wstecz**. Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w górę na liście.
