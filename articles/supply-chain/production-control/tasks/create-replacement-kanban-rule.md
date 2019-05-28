---
title: Tworzenie zastępczej reguły Kanban
description: Ta procedura skupia się na zastąpieniu istniejącej reguły Kanban nową regułą Kanban w określonym dniu.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c8a9367d4796999857e473bcbe36a709d534f3b0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564070"
---
# <a name="create-a-replacement-kanban-rule"></a>Tworzenie zastępczej reguły Kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na zastąpieniu istniejącej reguły Kanban nową regułą Kanban w określonym dniu. Jest to przydatne, gdy zmiany w przepływie produkcji lub regułach uzupełnienia muszą być skoordynowane i zaplanowane. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni produkcję z nowym przepływem lub regułą uzupełniania. To zadanie powoduje zastąpienie reguły Kanban 000022 nową regułą, która określa zwiększenie maksymalnej ilości z 48 do 100 sztuk.


## <a name="select-a-kanban-rule-to-replace"></a>Wybieranie reguły Kanban do zastąpienia
1. Przejdź do okna Reguły Kanban.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz regułę Kanban 000022.  

## <a name="create-a-replacement-kanban-rule"></a>Tworzenie zastępczej reguły Kanban
1. Kliknij opcję Przywróć regułę Kanban.
2. W polu Data obowiązywania wprowadź datę i godzinę.
    * Wybierz datę w przyszłości, na przykład jeden tydzień od teraz. Jest to data i godzina, kiedy nowa reguła Kanban stanie się aktywna i zastąpi starą regułę Kanban.  
    * Jeśli reguła Kanban zmienia ścieżkę w przepływie produkcji, można wybrać inne działanie.  W tej procedurze użyjemy działania bez zmian.  
3. Kliknij przycisk OK.
    * Zwróć uwagę, że została utworzona nowa reguła Kanban, aby zastąpić dotychczasową regułę Kanban 000022.  
    * Data wejścia w życie jest ustawiana zgodnie z datą wybraną podczas zamiany reguły Kanban.  
4. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz zastępowaną regułę Kanban 000022.  
    * Zwróć uwagę, że zastąpiona reguła Kanban ma taką samą datę jak data ważności, ponieważ jest to dzień, kiedy reguła wygasa.  
5. Na liście zaznacz wiersz 1.
    * Zaznacz nową regułę Kanban na szczycie listy. Jest to reguła Kanban o najwyższym numerze.  
6. Na liście kliknij łącze w wybranym wierszu.
    * Kliknij numer reguły Kanban, aby otworzyć regułę.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Modyfikowanie ilości maksymalnej dla nowej reguły Kanban
1. W polu Ilość maksymalna ustaw wartość „100”.
    * Rozwiń skróconą kartę Ilości, aby wyświetlić pole Ilość maksymalna. Zmiana maksymalnej ilości na 100 pozwoli na przetwarzanie maksymalnie 100 kart Kanban.    Jest to ostatni krok w tym zadaniu.  

