--- 
title: "Definiowanie opłat od płatności odbiorcy"
description: "Utwórz opłaty od płatności dla płatności odbiorców."
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 659f4560747cea73c61a9b748a980946ca252bd6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="establish-customer-payment-fees"></a>Definiowanie opłat od płatności odbiorcy

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utwórz opłaty od płatności dla płatności odbiorców.

W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Opłata.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator opłaty wpisz identyfikator opłaty.
    * Identyfikator opłaty jest wyświetlany w arkuszach płatności. Powinien być opisowy, aby użytkownicy rozumieli charakter opłaty.  
4. W polu Nazwa nadaj opłacie nazwę.
5. W polu Opis opłaty wprowadź opis opłaty.
6. Określ, czy opłata będzie obciążała odbiorcę czy konto księgowe.
    * Jeśli opłata będzie naliczana odbiorcy, zaznacz opcję Odbiorca. Jeśli opłata będzie naliczana organizacji jako wydatek, zaznacz opcję Księga. Dla tego zadania wybierz opcję Odbiorca.  
7. Wybierz typ arkusza, w którym można używać tej opłaty od płatności.
    * Jeśli te opłaty są używane dla płatności odbiorców, typem arkusza będzie prawdopodobnie Płatność od odbiorcy.  
8. Kliknij przycisk Zapisz.
9. Kliknij opcję Ustawienia opłat.
    * Opcja Ustawienia opłat służy do definiowania kryteriów, według których będą naliczane opłaty od płatności.  Na przykład można określić naliczanie opłaty, gdy kontem bankowym jest USMF OPER, a metodą płatności Czek.  
10. Zaznacz opcję Tabela, Grupa lub Wszystko, aby określić, na których kontach bankowych będzie naliczana ta opłata.
    * Jeśli zaznaczysz opcję Wszystko, ta opłata może być obliczana dla wszystkich kont bankowych.  Jeśli wybierzesz opcję Tabela, opłata może być naliczana tylko dla wskazanego konta bankowego. Jeżeli zostanie wybrana opcja Grupa, opłata będzie naliczana tylko dla kont bankowych w wybranej grupie bankowej.  
11. Zaznacz grupę bankową lub konto bankowe.
    * Jeśli została wybrana opcja Tabela, wyszukiwanie spowoduje wyświetlenie kont bankowych. Jeśli została wybrana opcja Grupa, wyszukiwanie spowoduje wyświetlenie grup bankowej.  
12. Na liście kliknij łącze w wybranym wierszu.
13. Zaznacz metodę płatności, w której opłata będzie naliczana.
    * Na przykład można naliczać opłatę odbiorcom, jeśli dokonują płatności czekami a nie drogą elektroniczną.  
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. W razie potrzeby wprowadź walutę płatności.
    * Waluta płatności służy jako dodatkowe kryterium określania, czy opłata będzie naliczana.  Na przykład bank może obciążać dodatkową opłatą płatności otrzymywane w dolarach amerykańskich, ponieważ normalnie obsługuje transakcje tylko w euro.  
16. Określ, czy opłata będzie procentem, kwotą czy interwałem.
17. Wprowadź procent lub kwotę opłaty.
    * Jeśli pole Procent/Kwota zawiera wartość Procent, wartość wprowadzona w tym polu będzie wartością procentową. Jeśli pole Procent/Kwota zawiera wartość Kwota, wartość wprowadzona w tym polu będzie kwotą. Jeśli pole Procent/Kwota zawiera wartość Interwał, należy zdefiniować warstwy na karcie Interwał.  
18. W polu Waluta opłaty wybierz walutę opłaty.
    * Jest to waluta, w której zostanie utworzona opłata.  
19. Kliknij przycisk Zapisz.


