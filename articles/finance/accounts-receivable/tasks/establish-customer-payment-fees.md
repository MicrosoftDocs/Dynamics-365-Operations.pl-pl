---
title: Definiowanie opłat od płatności odbiorcy
description: Utwórz opłaty od płatności dla płatności odbiorców.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99201039c30cd9d8e900662cd9e33b0a5db8e55a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012121"
---
# <a name="establish-customer-payment-fees"></a>Definiowanie opłat od płatności odbiorcy

[!include [banner](../../includes/banner.md)]

Utwórz opłaty od płatności dla płatności odbiorców.

W zadaniu wykorzystano firmę demonstracyjną USMF.

1. W **okienku nawigacji** przejdź do **Moduły > Rozrachunki z odbiorcami > Ustawienia płatności > Opłata za płatność**.
2. Kliknij przycisk **Nowy**.
3. W polu **Identyfikator opłaty** wpisz identyfikator opłaty. Identyfikator opłaty jest wyświetlany w arkuszach płatności. Powinien być opisowy, aby użytkownicy rozumieli charakter opłaty.  
4. W polu **Nazwa** nadaj opłacie nazwę.
5. W polu **Opis opłaty** wprowadź opis opłaty.
6. W polu **Opłata** wybierz, czy opłata będzie obciążała odbiorcę czy konto księgowe. Jeśli opłata będzie naliczana odbiorcy, zaznacz opcję Odbiorca. Jeśli opłata będzie naliczana organizacji jako wydatek, zaznacz opcję Księga. Dla tego zadania wybierz opcję Odbiorca.  
7. W polu **Typ arkusza** wybierz typ arkusza, który może wykorzystywać tę opłatę. Jeśli te opłaty są używane dla płatności odbiorców, typem arkusza będzie prawdopodobnie Płatność od odbiorcy.  
8. Kliknij przycisk **Zapisz**.
9. Kliknij **Ustawienia opłat płatności**. Opcja Ustawienia opłat służy do definiowania kryteriów, według których będą naliczane opłaty od płatności.  Na przykład można określić naliczanie opłaty, gdy kontem bankowym jest USMF OPER, a metodą płatności Czek.  
10. W polu **Grupowanie** wybierz opcję Tabela, Grupa lub Wszystko, aby określić, na których kontach bankowych będzie naliczana ta opłata. Jeśli zaznaczysz opcję Wszystko, ta opłata może być obliczana dla wszystkich kont bankowych.  Jeśli wybierzesz opcję Tabela, opłata może być naliczana tylko dla wskazanego konta bankowego. Jeżeli zostanie wybrana opcja Grupa, opłata będzie naliczana tylko dla kont bankowych w wybranej grupie bankowej.  
11. W polu **Relacja bankowa** wybierz grupę bankową lub konto bankowe. Jeśli została wybrana opcja Tabela, wyszukiwanie spowoduje wyświetlenie kont bankowych. Jeśli została wybrana opcja Grupa, wyszukiwanie spowoduje wyświetlenie grup bankowej.  
12. Na liście kliknij łącze w wybranym wierszu.
13. W polu **Metoda płatności** wybierz metodę płatności, dla której ta opłata będzie obliczona. Na przykład można naliczać opłatę odbiorcom, jeśli dokonują płatności czekami a nie drogą elektroniczną.  
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. W razie potrzeby w polu **Waluta płatności** wprowadź walutę płatności. Waluta płatności służy jako dodatkowe kryterium określania, czy opłata będzie naliczana.  Na przykład bank może obciążać dodatkową opłatą płatności otrzymywane w dolarach amerykańskich, ponieważ normalnie obsługuje transakcje tylko w euro.  
16. Określ, czy opłata będzie procentem, kwotą czy interwałem.
17. W **polu Kwota/procent** wprowadź wartość procentową lub kwotę opłaty. Jeśli pole Procent/Kwota zawiera wartość Procent, wartość wprowadzona w tym polu będzie wartością procentową. Jeśli pole Procent/Kwota zawiera wartość Kwota, wartość wprowadzona w tym polu będzie kwotą. Jeśli pole Procent/Kwota zawiera wartość Interwał, należy zdefiniować warstwy na karcie Interwał.  
18. W polu **Waluta opłaty** wybierz walutę opłaty. Jest to waluta, w której zostanie utworzona opłata.  
19. Kliknij przycisk **Zapisz**.

