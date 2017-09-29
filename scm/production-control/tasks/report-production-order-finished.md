--- 
title: "Zgłaszanie zlecenia produkcyjnego jako zakończonego"
description: "W tej procedurze pokazano sposób raportowania zlecenia produkcyjnego jako ukończonego."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ff651be006b4bbe205aa9937bd7927e37a83a558
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="report-a-production-order-as-finished"></a>Zgłaszanie zlecenia produkcyjnego jako zakończonego

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób raportowania zlecenia produkcyjnego jako ukończonego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to szósta z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.


## <a name="report-a-production-order-as-finished"></a>Zgłaszanie zlecenia produkcyjnego jako zakończonego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
    * Zaznacz zlecenie produkcyjne, które ma stan Rozpoczęto.  
2. W okienku akcji kliknij opcję Zlecenie produkcyjne.
3. Po zakończeniu kliknij opcję Raport.
    * Na tej stronie można potwierdzić ilość ukończonego produktu, która ma zostać zgłoszona jako gotowa.  
4. Kliknij kartę Ogólne.
5. W polu Ilość dobrych ustaw wartość „18”.
6. W polu Ilość wadliwych ustaw wartość „2”.
7. W polu Powód błędu wybierz opcję „Materiał”.
8. Zaznacz lub wyczyść pole wyboru Zakończ zadanie.
9. Zaznacz lub wyczyść pole wyboru Akceptacja błędu.
10. Kliknij przycisk OK.

## <a name="verify-the-report-as-finished-journal"></a>Weryfikowanie arkusz zgłoszonych wyrobów gotowych
1. W okienku akcji kliknij pozycję Widok.
2. Kliknij opcję Zgłoszone jako gotowe.
3. Na liście oznacz wybrany wiersz.
4. Na liście kliknij łącze w wybranym wierszu.
    * Arkusz zgłoszonych wyrobów gotowych jest księgowany. Jeśli chcesz dokonać korekt w arkuszu, można ręcznie utworzyć nowy arkusz, gdzie można dokonać zmian.  

