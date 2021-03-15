---
title: Przywróć stan zadania Kanban
description: Ta procedura skupia się na cofnięciu błędnego stanu zadania w systemie Kanban.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bc147ec517b8141b4764f67d21b4c4a2e4d6e6e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981163"
---
# <a name="revert-kanban-job-status"></a>Przywróć stan zadania Kanban

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na cofnięciu błędnego stanu zadania w systemie Kanban. Jest to przydatne w przypadku, gdy operator maszyny zaktualizuje niewłaściwe zadanie lub ustawi przez pomyłkę niewłaściwy stan. W tej procedurze zadanie w systemie Kanban jest rejestrowane jako przygotowane przez pomyłkę, a stan zostanie przywrócony. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla kierownika produkcji lub operatora maszyny w firmie stosującej zasady produkcji oszczędnej.


## <a name="open-process-board-for-the-work-cell"></a>Otwieranie tablicy procesów komórki roboczej
1. Przejdź do tablicy Kanban pokazującej zadania przetwarzania.
2. W polu Komórka robocza wprowadź lub wybierz wartość.
    * Zaznacz komórkę roboczą 1260.  

## <a name="prepare-kanban-job"></a>Przygotowanie zadania w systemie Kanban
1. Kliknij przycisk Przygotuj.
    * Jeśli nie możesz kliknąć przycisku Przygotuj, ponieważ jest on wyszarzony, upewnij się, że wybrane zadanie w systemie Kanban ma stan Zaplanowane, co jest wskazywane przez pustą ikonę na karcie Kanban. Jeśli przygotowanie się nie powiedzie, upewnij się, że wszystkie materiały na liście pobrania są dostępne.  
2. Na liście zaznacz przygotowane zadanie.
    * Wybierz pierwsze zadanie, które właśnie zostało przygotowane.  
    * Należy zauważyć, że stan zadania to „przygotowane”, co jest wskazane trójkątem wewnątrz ikony karty Kanban.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Przywracanie stanu przygotowanego zadania w systemie Kanban
1. Na liście oznacz wybrany wiersz.
    * Wybierz pierwsze zadanie, które właśnie zostało przygotowane.  
2. W okienku akcji kliknij pozycję Produkcja.
3. Kliknij opcję Przywrócenie stanu.
    * Można użyć alternatywnej reguły Kanban, gdy są spełnione następujące warunki:  - Strategia uzupełniania jest taka sama dla obu reguł.  - Wersja przepływu produkcji jest taka sama dla obu reguł.  - Dostarczany produkt jest taki sam dla obu reguł.  - Wszelkie działania poprzedzające skonfigurowane dla ostatniego działania w regułach Kanban muszą być takie same w obu regułach.  - Te same wymiary dostarczanych zapasów muszą być skonfigurowane dla obu reguł.  - Jednostka załadunkowa musi mieć stan Nie przypisano.  - Konfiguracja kart Kanban zdarzeń musi być taka sama.  
    * Upewnij się, że nowy stan to Zaplanowane.  
4. Kliknij przycisk OK.
5. Na liście usuń oznaczenie wybranego wiersza.
    * Wybierz to samo zadanie.  
    * Należy zauważyć, że stan zadania w systemie kanban został przywrócony do Zaplanowane, co jest wskazywane przez pustą ikonę na karcie Kanban.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]