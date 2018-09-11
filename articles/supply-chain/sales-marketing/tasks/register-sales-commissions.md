--- 
title: "Rejestrowanie prowizji od sprzedaży"
description: "W tej procedurze pokazano sposób obliczania i rejestrowania prowizji od sprzedaży."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5535f1627526b97ddc9ca2c210db4e332782d656
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="register-sales-commissions"></a>Rejestrowanie prowizji od sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób obliczania i rejestrowania prowizji od sprzedaży. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem tego przewodnika wykonaj przewodnik o nazwie „Konfigurowanie reguł dla prowizji od sprzedaży”, aby się upewnić, że wszystkie niezbędne obliczenia prowizji są skonfigurowane.

Zwróć uwagę na odbiorcę i numery towarów wybrane dla procesu naliczania prowizji i używaj ich, kiedy w przewodniku pojawi się monit o utworzenie zamówienia sprzedaży.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Fakturowanie zamówienia sprzedaży kwalifikującego sprzedawcę do prowizji
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk OK.
7. W okienku akcji kliknij pozycję Opcje.
8. Kliknij przycisk Zmień widok.
9. Kliknij opcję Widok nagłówka.
10. Rozwiń sekcję Ustawienia.
    * Wartość w polu Grupa sprzedaży reprezentuje grupę z przypisanym jednego lub więcej przedstawicielami handlowymi. Osoby w grupie są tymi, które otrzymają prowizję podczas fakturowania zamówienia, zgodnie ze wstępnie zdefiniowanymi stawkami i rozdziałem.   Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.  Grupa sprzedaży jest również kopiowana do wiersza zamówienia sprzedaży. Można ją zmienić, tak aby była inna niż podana w nagłówku i/lub różniła się między wierszami.  
    * Wartość w polu Grupa prowizji reprezentuje grupę utworzoną dla jednego lub więcej odbiorców w celu śledzenia prowizji.   Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.   
11. W okienku akcji kliknij pozycję Opcje.
12. Kliknij przycisk Zmień widok.
13. Kliknij opcję Widok wiersza.
14. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście zaznacz towar, który skonfigurowano dla prowizji. 
16. Wprowadź liczbę w polu Ilość.
    * Zwróć uwagę na kwotę netto w wierszu. Reprezentuje ona przychody ze sprzedaży, które w tym przykładzie są podstawą do obliczania prowizji.  
17. Kliknij przycisk Zapisz.
18. W okienku akcji kliknij pozycję Faktura.
19. Kliknij opcję Faktura.
20. Rozwiń sekcję Parametry.
21. W polu Ilość zaznacz opcję Wszystko.
22. W polu Księgowanie wybierz opcję Tak.
23. Kliknij przycisk OK.
24. Kliknij przycisk OK.
    * Zaksięgowanie transakcji może zająć ok. minutę. Poczekaj na zakończenie przetwarzania — nie zamykaj w tym czasie strony.  

## <a name="review-the-registered-sales-commissions"></a>Przegląd zarejestrowanych prowizji od sprzedaży
1. W okienku akcji kliknij pozycję Faktura.
2. Kliknij opcję Faktura.
3. W okienku akcji kliknij pozycję Faktura.
4. Kliknij opcję Transakcje prowizji.
    * Na karcie Przegląd są wyświetlane wiersze reprezentujące kwoty prowizji należne przedstawicielom handlowym skojarzonym z fakturowanym zamówieniem sprzedaży. Przyjrzyjmy się szczegółom.     
    * Jeśli użyto przewodnika „Konfigurowanie reguł dla prowizji od sprzedaży” w celu skonfigurowania grupy prowizji sprzedaży, istnieje dwoje sprzedawców, którzy otrzymają prowizje od sprzedaży, a prowizja jest dzielona równo między nich.  
    * W tym przykładzie suma prowizji jest obliczana jako procent przychodu ze sprzedaży (kwota netto wiersza zamówienia).   
5. Zamknij stronę.
6. Kliknij opcję Załącznik.
    * Można przejrzeć transakcje załącznika dla kwot prowizji, które zostały zaksięgowane na wstępnie zdefiniowanych kontach wydatków z tytułu prowizji i należnych prowizji.  


