---
title: Rejestrowanie prowizji od sprzedaży
description: W tym temacie objaśniono sposób obliczania i rejestrowania prowizji od sprzedaży.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4334fcd996f32b00bb399d3df5c43eb6bf50ab28
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010705"
---
# <a name="register-sales-commissions"></a>Rejestrowanie prowizji od sprzedaży

[!include [banner](../../includes/banner.md)]

W tym temacie objaśniono sposób obliczania i rejestrowania prowizji od sprzedaży. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem tego przewodnika wykonaj przewodnik o nazwie „Konfigurowanie reguł dla prowizji od sprzedaży”, aby się upewnić, że wszystkie niezbędne obliczenia prowizji są skonfigurowane.

Zwróć uwagę na odbiorcę i numery towarów wybrane dla procesu naliczania prowizji i używaj ich, kiedy w przewodniku pojawi się monit o utworzenie zamówienia sprzedaży.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Fakturowanie zamówienia sprzedaży kwalifikującego sprzedawcę do prowizji
1. W okienku nawigacji przejdź do **Moduły > Sprzedaż i marketing >Wszystkie zamówienia sprzedaży**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto odbiorcy** wybierz odpowiedni rekord z menu rozwijanego.
4. Kliknij przycisk **OK**.
5. W okienku akcji kliknij pozycję **Opcje**.
6. Wybierz **Zmień widok**.
7. Wybierz **Widok nagłówka**.
8. Rozwiń sekcję **Ustawienia**.

    - Wartość w polu **Grupa sprzedaży** reprezentuje grupę z przypisanym jednym lub więcej przedstawicielami handlowymi. Osoby w grupie są tymi, które otrzymają prowizję podczas fakturowania zamówienia, zgodnie ze wstępnie zdefiniowanymi stawkami i rozdziałem.   
    - Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.  
    - Grupa sprzedaży jest również kopiowana do wiersza zamówienia sprzedaży. Można ją zmienić, tak aby była inna niż podana w nagłówku i/lub różniła się między wierszami.  
    - Wartość w polu **Grupa prowizji** reprezentuje grupę utworzoną dla jednego lub więcej odbiorców w celu śledzenia prowizji.   
    - Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.   

9. W okienku akcji kliknij pozycję **Opcje**.
10. Wybierz **Zmień widok**.
11. Wybierz **Widok wiersza**.
12. W menu rozwijanym pola **Kod towaru** wybierz towar skonfigurowany dla prowizji. 
13. W polu **Ilość** wpisz liczbę. Zwróć uwagę na kwotę netto w wierszu. Reprezentuje ona przychody ze sprzedaży, które w tym przykładzie są podstawą do obliczania prowizji.  
14. Wybierz opcję **Zapisz**.
15. W okienku akcji kliknij pozycję **Faktura**.
16. Wybierz **Faktura**.
17. Rozwiń sekcję **Parametry**.
18. W polu **Ilość** zaznacz opcję **Wszystko**.
19. W polu **Księgowanie** wybierz opcję **Tak**.
20. Wybierz **OK**, a następnie kliknij przycisk **OK** w następnym okienku. Zaksięgowanie transakcji może zająć ok. minutę. Poczekaj na zakończenie przetwarzania i nie zamykaj w tym czasie strony.  

## <a name="review-the-registered-sales-commissions"></a>Przegląd zarejestrowanych prowizji od sprzedaży
1. W okienku akcji wybierz opcję **Faktura**, a następnie ponownie wybierz opcję **Faktura**.
2. W okienku akcji wybierz opcję **Faktura**, a następnie wybierz opcję **Transakcje prowizji**.

    - Na karcie **Przegląd** są wyświetlane wiersze reprezentujące kwoty prowizji należne przedstawicielom handlowym skojarzonym z fakturowanym zamówieniem sprzedaży. Przyjrzyjmy się szczegółom.  
    - Jeśli użyto przewodnika „Konfigurowanie reguł dla prowizji od sprzedaży” w celu skonfigurowania grupy **prowizji sprzedaży**, istnieje dwoje sprzedawców, którzy otrzymają prowizje od sprzedaży, a prowizja jest dzielona równo między nich.  
    - W tym przykładzie suma prowizji jest obliczana jako procent przychodu ze sprzedaży (kwota netto wiersza zamówienia).  
3. Zamknij stronę.
4. Wybierz **Załącznik**. Można przejrzeć transakcje załącznika dla kwot prowizji, które zostały zaksięgowane na wstępnie zdefiniowanych kontach wydatków z tytułu prowizji i należnych prowizji.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]