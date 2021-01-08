---
title: Wykonywanie zadań procesu w systemie Kanban
description: Ta procedura skupia się na wykonywaniu zadań procesu w systemie Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1c32b577007c400f3528a110436eb97aaabefe2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435270"
---
# <a name="execute-kanban-process-jobs"></a>Wykonywanie zadań procesu w systemie Kanban

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na wykonywaniu zadań procesu w systemie Kanban. Pierwsze zadanie zostało ukończone z oczekiwaną ilością i nie zawiera błędów. Drugie zadanie zostało ukończone z błędami. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla operatora maszyny.


## <a name="select-a-kanban-job"></a>Wybieranie zadania Kanban
1. Wybierz kolejno opcje Kontrola produkcji > Kanban > Tablica Kanban dla zadań procesu.
2. W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Kliknij wiersz z grupą zasobów 1250. Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zadania komórki roboczej 1250.
    * Zaznacz wiersz, który ma stan Zaplanowane zadanie.  

## <a name="complete-a-job-with-expected-quantity"></a>Kończenie zadania z oczekiwaną ilością
1. Rozwiń lub zwiń sekcję Szczegóły.
    * Ta sekcja zawiera ważne informacje dotyczące numeru karty, numeru towaru, ilości zamówionej i nazwy działania.  
2. Rozwiń lub zwiń sekcje Instrukcje produkcji.
    * W tej sekcji są wyświetlane instrukcje produkcji dla działania. Instrukcjami mogą być teksty, obrazy, rysunki i inne dokumenty.  
3. Kliknij przycisk Rozpocznij.
    * Wybierz zadanie, które nie zostało zakończone. Użyj ikon stanu w polu Stan zadania, aby wyświetlić stan zadania.      
4. Kliknij przycisk Wykonaj.
    * Zadanie jest zakończone z oczekiwaną jakością.  

## <a name="complete-a-job-with-errors"></a>Kończenie zadania z błędami
1. Kliknij przycisk Rozpocznij.
    * Po zakończeniu zadania następne zadanie na liście jest wybierane automatycznie. Dlatego nie ma potrzeby zaznaczania zadania przed kliknięciem przycisku Uruchom.  
2. W okienku akcji kliknij pozycję Produkcja.
3. Kliknij opcję Zakończ (szczegóły).
4. Na liście oznacz wybrany wiersz.
5. W polu Ilość wadliwych wprowadź liczbę.
6. W polu Ilość dobrych wprowadź liczbę.
7. Kliknij przycisk OK.

