---
title: Konfigurowanie okresów rozliczania podatku
description: W tym temacie wyjaśniono sposób konfigurowania okresów rozliczenia podatku w Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5068c121e921c1586dc6ae003c0021bf41d2254
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446804"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Konfigurowanie okresów rozliczania podatku

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania okresów rozliczenia podatku. Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki. Proces rozliczania można wykonać dla okresu rozliczeniowego za określony zakres dat. Rozliczenie obejmie wszystkie kody podatków skojarzone z okresem rozliczeniowym. W zależności od ustawień odnośnego urzędu skarbowego zobowiązania podatkowe zostaną zaksięgowana na koncie dostawcy lub Księgi głównej.

W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Otwórz w okienku nawigacji otwórz **Moduły > Podatek > Podatki pośrednie > Podatek > Okresy rozliczania podatku**.
2. Wybierz pozycję **Nowy**.
3. W polu **Okres rozliczeniowy** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Organ** wybierz urząd podatkowy otrzymujący deklaracje podatkowe i płatności za ten okres rozliczeniowy.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. W polu **Warunki płatności** wybierz odpowiedni rekord z menu rozwijanego. Odpowiedni urząd skarbowy można skonfigurować jako dostawcę, a wtedy funkcja rozliczania podatku utworzy otwartą fakturę od dostawcy. Warunki płatności decydują o terminie płatności otwartej faktury od dostawcy.  
8. Wybierz typ interwałów okresu rozliczeniowego.
9. Wprowadź liczbę jednostek interwału okresu w okresie. Na przykład kwartał ma 3 miesiące.
10. Zaznacz lub wyczyść pole wyboru **Użyj przetwarzania wsadowego w celu rozliczenia podatku**. Proces rozliczania dla okresu rozliczeniowego może być wykonywany w trybie wsadowym w tle. Jest to zalecane dla dużej liczby transakcji podatkowych w interwale okresu.  
    > [!NOTE]
    > Obecnie nie jest to obsługiwane w Hiszpanii, Japonii i Holandii.
11. Zaznacz lub wyczyść pole wyboru **Zapobiegaj generowaniu transakcji podatków przeciwstawnych**. Domyślnie system generuje transakcje podatków przeciwstawnych w trakcie rozliczania, co może spowalniać działanie, jeżeli w okresie występuje duża liczba transakcji podatkowych. Zaznaczenie tego pola wyboru uniemożliwi generowanie transakcji podatków przeciwstawnych.
12. Rozwiń kartę **Interwały okresu**.
13. Wybierz opcję **Dodaj**.
14. W polu **Od dnia** w nowym wierszu wpisz datę.
15. Wprowadź datę w polu **Do dnia**.
16. Wybierz **Nowy interwał okresu**. Po wprowadzeniu pierwszego interwału okresu nowe okresy mogą być tworzone automatycznie. Później można wrócić i dodawać nowe interwały okresu zgodnie z wymaganiami.  
17. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]