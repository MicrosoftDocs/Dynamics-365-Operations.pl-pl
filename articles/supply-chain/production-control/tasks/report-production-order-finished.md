---
title: Zgłaszanie zlecenia produkcyjnego jako zakończonego
description: W tej procedurze pokazano sposób raportowania zlecenia produkcyjnego jako ukończonego.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93193e6365bcf82fbbf93af81e2581a358899fa1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434916"
---
# <a name="report-a-production-order-as-finished"></a>Zgłaszanie zlecenia produkcyjnego jako zakończonego

[!include [banner](../../includes/banner.md)]

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

