---
title: Tworzenie reguły Kanban dla wielu działań
description: W tej procedurze pokazano, jak utworzyć regułę Kanban, która obejmuje wiele działań z przepływu produkcji.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68cac0f581e786cdb3801e03fb60db7bc05ffb2f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434942"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Tworzenie reguły Kanban dla wielu działań

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak utworzyć regułę Kanban, która obejmuje wiele działań z przepływu produkcji. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.


## <a name="create-a-new-kanban-rule"></a>Utwórz nową regułę Kanban
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
2. Kliknij przycisk Nowy.
3. W polu Strategia uzupełniania wybierz opcję „Zaplanowane”.
4. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Wybierz czynność SpeakerAssemblyAndPolish.  
5. Zaznacz pole wyboru Wiele działań.
    * Celem jest umieszczenie więcej niż jednego działania w regule Kanban. Wybierasz ścieżkę w przepływie produkcji z chwilą wybrania ostatniego działania w planie.  
6. W polu Ostatnie działanie planu wprowadź lub wybierz wartość.
    * Wybierz opcję SpeakerTestAndPackaging. Po zaznaczeniu wartości automatycznie zostanie otwarta strona. Wybierz przepływ Kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging. Kliknij przycisk OK.  
7. Rozwiń sekcję Szczegóły.
8. W polu Produkt wprowadź lub wybierz wartość.
    * Wybierz towar L0006.  

## <a name="create-kanban-and-view-jobs"></a>Tworzenie reguły Kanban i wyświetlanie zadań
1. Rozwiń sekcję Karty Kanban.
2. Kliknij przycisk Dodaj.
3. W polu Liczba nowych kart Kanban wpisz wartość „1”.
    * Spowoduje to utworzenie jednej karty Kanban.  
4. W polu Ilość produktu ustaw wartość „3”.
    * W zadaniu Kanban będą przetwarzane 3 produkty.  
5. W polu Data/godzina wykonania wprowadź datę i godzinę.
    * Można wprowadzić wartość Dzisiaj.  
6. Kliknij przycisk Utwórz.
7. Kliknij przycisk Szczegóły.
    * Należy zauważyć, że karta Kanban ma dwa zadania przetwarzania z przepływu produkcji. Pierwsze z nich to SpeakerAssemblyAndPolish, a drugim jest SpeakerTestAndPackaging.  
    * To jest ostatni krok!  

