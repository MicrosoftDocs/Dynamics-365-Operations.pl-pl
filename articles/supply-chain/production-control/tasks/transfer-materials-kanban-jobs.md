---
title: Przenoszenie materiałów za pomocą zadań systemu Kanban
description: Ta procedura skupia się na wycofywaniu zadania przeniesienia materiałów w systemie Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcab5d27d1e5bb2f86910fe083168e7b97c52e2f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148816"
---
# <a name="transfer-materials-with-kanban-jobs"></a>Przenoszenie materiałów za pomocą zadań systemu Kanban

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na wycofywaniu zadania przeniesienia materiałów w systemie Kanban. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla pracownika magazynu.


## <a name="display-transfer-jobs"></a>Wyświetlanie zadań przeniesienia
1. Wybierz kolejno opcje Kontrola produkcji > Kanban > Tablica Kanban zadań przeniesienia.
2. Rozwiń lub zwiń sekcję Filtry.
    * W sekcji Filtry można określić, które zadania mają być widoczne, filtrując według przepływu produkcji, nazwy działania, magazynu i lokalizacji źródłowej oraz magazynu i lokalizacji docelowej.  
3. W polu Z magazynu wpisz „11”.
4. W polu Do lokalizacji wpisz „12”.

## <a name="start-a-transfer-job"></a>Rozpocznij zadanie przeniesienia
1. Na liście usuń zaznaczenie wybranego wiersza, jeśli takie istnieje.
2. Na liście zaznacz wiersz 4.
    * Zaznacz pierwsze zadanie o stanie Niezaplanowane. Upewnij się, że jest to jedyne zaznaczone zadanie.  
3. Kliknij przycisk Rozpocznij.
    * Należy zauważyć, że ikona wskazuje rozpoczęcie zadania.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Wybór drugiego zadania przeniesienia i zmiana ilości
1. Na liście znajdź i zaznacz odpowiedni rekord.
    * Można mieć zaznaczonych wiele zadań, ale na razie zaznacz tylko wiersz 5.  
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Upewnij się, że zadanie w poprzednim kroku jest jednym zaznaczonym zadaniem. Anuluj zaznaczenie wszystkich innych zadań.  
3. Zanotuj wartość z pola Ilość zadania w celu późniejszego wykorzystania
4. W polu Ilość zadania ustaw wartość „30”.
    * Zwróć uwagę na ostrzeżenie! Nie możesz przenieść 30. Zgodnie z ustawieniami reguły Kanban możesz przenieść tylko oryginalną ilość.  
5. Użyj wartości zanotowanej uprzednio z pola Ilość zadania.
    * W polu Ilość zadania ustaw poprzednią wartość.  

## <a name="start-the-second-transfer-job"></a>Rozpoczynanie drugiego zadania przeniesienia
1. Kliknij przycisk Rozpocznij.
    * Spowoduje to rozpoczęcie przeniesienia określonego w zadaniu w wierszu 5.  

## <a name="complete-both-transfer-jobs"></a>Kończenie obu zadań przeniesienia
1. Na liście zaznacz wiersz 4.
    * Teraz są wybrane dwa zadania przeniesienia, w wierszach 4 i 5.  
2. Kliknij przycisk Wykonaj.
    * Spowoduje to zakończenie przeniesienia w obu zadaniach.  

