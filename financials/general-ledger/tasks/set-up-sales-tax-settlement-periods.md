--- 
title: "Ustawianie okresów rozliczania podatku"
description: "Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7aa40362278a0a032e909574a59f842840fb9860
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a>Ustawianie okresów rozliczania podatku

[!include[task guide banner](../../includes/task-guide-banner.md)]

Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki. Proces rozliczania można wykonać dla okresu rozliczeniowego za określony zakres dat. Rozliczenie obejmie wszystkie kody podatków skojarzone z okresem rozliczeniowym. W zależności od ustawień odnośnego urzędu skarbowego zobowiązania podatkowe zostaną zaksięgowana na koncie dostawcy lub Księgi głównej.



W zadaniu wykorzystano firmę demonstracyjną USMF.



1. Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Okresy rozliczania podatku.
2. Kliknij przycisk Nowy.
3. W polu Okres rozliczeniowy wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Organ wybierz urząd podatkowy otrzymujący deklaracje podatkowe i płatności za ten okres rozliczeniowy.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Warunki płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Odpowiedni urząd skarbowy można skonfigurować jako dostawcę, a wtedy funkcja rozliczania podatku utworzy otwartą fakturę od dostawcy. Warunki płatności decydują o terminie płatności otwartej faktury od dostawcy.  
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. Wybierz typ interwałów okresu rozliczeniowego.
12. Wprowadź liczbę jednostek interwału okresu w okresie. Na przykład kwartał ma 3 miesiące.
13. Zaznacz lub wyczyść pole wyboru Użyj przetwarzania wsadowego w celu rozliczenia podatku.
    * Proces rozliczania dla okresu rozliczeniowego może być wykonywany w trybie wsadowym w tle. Jest to zalecane dla dużej liczby transakcji podatkowych w interwale okresu.  
14. Rozwiń kartę Interwały okresu.
15. Kliknij przycisk Dodaj.
16. Na liście oznacz wybrany wiersz.
17. W polu Od dnia wprowadź datę.
18. Wprowadź datę w polu Do dnia.
19. Kliknij przycisk Nowy interwał okresu.
    * Po wprowadzeniu pierwszego interwału okresu nowe okresy mogą być tworzone automatycznie. Później można wrócić i dodawać nowe interwały okresu zgodnie z wymaganiami.  
20. Zamknij stronę.


