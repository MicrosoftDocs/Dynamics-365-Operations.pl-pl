--- 
title: "Ustawianie okresów rozliczania podatku"
description: "Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki."
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 81214cc52b1488bb70ac5fd6ccc817f6f979163d
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.contentlocale: pl-pl
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a>Ustawianie okresów rozliczania podatku

[!include [task guide banner](../../includes/task-guide-banner.md)]

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
14. Zaznacz lub wyczyść pole wyboru Zapobiegaj generowaniu transakcji podatków przeciwstawnych.
    * Domyślnie system generuje transakcje podatków przeciwstawnych w trakcie rozliczania, co może spowalniać działanie, jeżeli w okresie występuje duża liczba transakcji podatkowych. Zaznaczenie tego pola wyboru uniemożliwi generowanie transakcji podatków przeciwstawnych.
15. Rozwiń kartę Interwały okresu.
16. Kliknij przycisk Dodaj.
17. Na liście oznacz wybrany wiersz.
18. W polu Od dnia wprowadź datę.
19. Wprowadź datę w polu Do dnia.
20. Kliknij przycisk Nowy interwał okresu.
    * Po wprowadzeniu pierwszego interwału okresu nowe okresy mogą być tworzone automatycznie. Później można wrócić i dodawać nowe interwały okresu zgodnie z wymaganiami.  
21. Zamknij stronę.


