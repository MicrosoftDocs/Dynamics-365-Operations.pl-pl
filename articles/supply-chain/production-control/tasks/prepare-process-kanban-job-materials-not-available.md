---
title: Przygotowanie zadania procesu w systemie Kanban, gdy materiały nie są dostępne dla komórki roboczej
description: Ta procedura jest zorientowana na przygotowanie zadania przetwarzania w systemie Kanban, gdy niektóre materiały są niedostępne w komórce roboczej i z tego względu konieczne jest ich pobranie z magazynu.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bba9e5cb7dfddd2a80a37e7a57fdf94a91341e8f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843632"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>Przygotowanie zadania procesu w systemie Kanban, gdy materiały nie są dostępne dla komórki roboczej

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura jest zorientowana na przygotowanie zadania przetwarzania w systemie Kanban, gdy niektóre materiały są niedostępne w komórce roboczej i z tego względu konieczne jest ich pobranie z magazynu. Warunkiem wstępnym utworzenia tej procedury jest wykonanie procedury „Przygotowanie zadania przetwarzania w systemie Kanban, gdy materiały są dostępne”. Ta procedura jest przeznaczona dla operatora maszyny. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Kontrola produkcji > Kanban > Tablica Kanban dla zadań procesu.
2. W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz komórkę roboczą 1250.  
4. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz opcję Kanban 000356.  
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Na liście usuń zaznaczenie wiersza 4 lub wybierz wiersz 4, jeśli nie wykonano zadania „Przygotowanie zadania przetwarzania w systemie Kanban, gdy materiały są dostępne”.  
6. Przełącz rozwinięcie sekcji Lista pobrania.
    * Ikona barku wpisu w stanie dostaw wskazuje, że w komórce roboczej brakuje 48 sztuk towaru P0002.  

## <a name="transfer-materials-to-work-cell"></a>Przenoszenie materiałów do komórki roboczej
1. Przełącz rozwinięcie sekcji Zadania przenoszenia.
2. Użyj szybkiego filtru, aby filtrować na podstawie pola Numer pozycji z wartością „P0002”.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Kliknij przycisk Rozpocznij.
    * Przenoszenie jest w toku.  
5. Kliknij przycisk Wykonaj.
    * Towar P0002 jest teraz dostępny na liście pobrania dla zadania w systemie Kanban. Oznacza to, że możemy przygotować kartę Kanban ze wszystkimi niezbędnymi materiałami.  
6. Kliknij przycisk Przygotuj.
    * Zwróć uwagę na ikonę w polu Stan zadania, która wskazuje, że zadanie jest gotowe.  

