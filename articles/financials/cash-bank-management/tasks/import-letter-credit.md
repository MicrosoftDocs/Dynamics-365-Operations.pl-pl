---
title: Akredytywa importowa
description: Ta procedura poprowadzi przez proces tworzenia akredytywy importowej.
author: kweekley
manager: AnnBe
ms.date: 02/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72a50b2cdda5d66e8aa4660f914e6f5e51531b5f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842024"
---
# <a name="import-letter-of-credit"></a>Akredytywa importowa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura poprowadzi przez proces tworzenia akredytywy importowej. Następujące ustawienia należy skonfigurować przed wykonaniem tej procedury: instrument bankowy, profile księgowania, umowa instrumentu bankowego oraz dane bankowe dostawcy.

Ta procedura wykorzystuje firmę demonstracyjną USMF.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Tworzenie zamówienia zakupu z akredytywą
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wprowadź lub wybierz wartość.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Rozwiń sekcję Ogólne.
7. W polu Oddział wprowadź lub wybierz wartość.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Magazyn wprowadź lub wybierz wartość.
10. Na liście kliknij łącze w wybranym wierszu.
11. W polu Data księgowania wpisz datę.
12. W polu Data dostawy wpisz datę.
    * Uwaga: Wybierz pole „Typ dokumentu bankowego” z wartością „Akredytywa”.  
13. Kliknij przycisk OK.
14. W polu Numer towaru wprowadź lub wybierz wartość.
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Na liście kliknij łącze w wybranym wierszu.
17. Rozwiń sekcję Szczegóły wiersza.
18. Kliknij kartę Dostawa.
19. W polu Data dostawy wpisz datę.
20. W polu Potwierdzona data dostawy wpisz datę.
21. Wprowadź liczbę w polu Cena jednostkowa.
    * Wprowadź szczegóły akredytywy.  
22. W okienku akcji kliknij pozycję Zarządzaj.
23. Kliknij opcję Akredytywa/inkaso importowe.
24. W polu Data zgłoszenia wprowadź datę i godzinę.
    * Sprawdź, czy pole „Konto bankowe” zawiera domyślne aktywne konto bankowego, co zależy od daty zgłoszenia.  
25. W polu Numer dokumentu banku wpisz wartość.
26. W polu Data otrzymania wprowadź datę i godzinę.
27. Rozwiń sekcję Dokument bankowy.
28. W polu Data wygaśnięcia wprowadź datę i godzinę.
29. Rozwiń sekcję Szczegóły banku.
30. W polu Bank doradczy wprowadź lub wybierz wartość.
31. Na liście kliknij łącze w wybranym wierszu.
32. Kliknij przycisk Zapisz.
33. Kliknij opcję Pobierz wysyłki zamówienia zakupu.
34. Zamknij stronę.
35. W okienku akcji kliknij pozycję Zakup.
36. Kliknij przycisk Potwierdź.
37. W okienku akcji kliknij pozycję Zarządzaj.
38. Kliknij opcję Akredytywa/inkaso importowe.
39. Kliknij przycisk Przetwarzaj.
40. Kliknij przycisk Potwierdź.
    * Sprawdź, czy saldo instrumentu zmniejsza kwotę zamówienia zakupu.  W tym przykładzie kwota zakupu = 500,00, limit instrumentu = 10000,00, dlatego saldo instrumentu = 9500,00.  
41. Zamknij stronę.
42. Wprowadź liczbę w polu Cena jednostkowa.
43. Kliknij przycisk Zapisz.
44. W okienku akcji kliknij pozycję Zakup.
45. Kliknij przycisk Potwierdź.
    * Skoryguj akredytywę ze względu na zmianę ceny jednostkowej.  
46. W okienku akcji kliknij pozycję Zarządzaj.
47. Kliknij opcję Akredytywa/inkaso importowe.
    * Skoryguj akredytywę ze względu na zmianę ceny jednostkowej zakupu.  
48. Kliknij przycisk Przetwarzaj.
49. Kliknij przycisk Zmiana.
50. Kliknij przycisk Usuń.
51. Kliknij przycisk Tak.
52. Kliknij opcję Pobierz wysyłki zamówienia zakupu.
53. Kliknij przycisk Przetwarzaj.
54. Kliknij przycisk Potwierdź.
    * Sprawdź, czy saldo instrumentu zmniejsza kwotę zamówienia zakupu.  W tym przykładzie zmodyfikowana kwota zakupu = 600,00, limit instrumentu = 10000,00, dlatego saldo instrumentu = 9400,00.  
55. Zamknij stronę.

## <a name="post-packing-slip"></a>Księgowanie dokumentu dostawy
1. W okienku akcji kliknij pozycję Odbierz.
2. Kliknij opcję Dokument przyjęcia produktów.
3. W polu PurchParmTable_Num wpisz wartość.
    * Wybierz numer wysyłki utworzonej z odniesieniem do akredytywy.  
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Data dokumentu przyjęcia produktów wpisz datę.
6. Kliknij przycisk OK.
7. Zamknij stronę.
8. Zamknij stronę.

## <a name="verify-import-letter-of-credit-status"></a>Weryfikacja stanu akredytywy importowej
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
    * Zweryfikuj stan akredytywy importowej.     
4. Zamknij stronę.
5. Zamknij stronę.

## <a name="post-purchase-invoice"></a>Księgowanie faktury zakupu
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.
    * Wybierz zamówienie zakupu, które zostało utworzone z akredytywą.  
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij pozycję Faktura.
5. Kliknij opcję Faktura.
6. W polu Numer wpisz wartość.
7. W polu Numer wysyłki wprowadź lub wybierz wartość.
8. Na liście kliknij łącze w wybranym wierszu.
9. Wprowadź datę w polu Data faktury.
10. Kliknij przycisk Aktualizuj stan uzgadniania.
11. Kliknij przycisk Księguj.
12. Zamknij stronę.
13. Zamknij stronę.

## <a name="verify-import-letter-of-credit-status"></a>Weryfikacja stanu akredytywy importowej
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
    * Zweryfikuj akredytywę importową2.  
    * Sprawdzanie poprawności: Stan wysyłki = Zafakturowana  Szczegóły instrumentu bankowego  
4. Kliknij przycisk Wyświetl.
5. Kliknij opcję Drukuj zgłoszenie.
6. Kliknij przycisk OK.
    * Sprawdź, czy zgłoszenie akredytywy jest drukowane.  
7. Zamknij stronę.
8. Zamknij stronę.
9. Zamknij stronę.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Księgowanie arkusza płatności dostawcy dla utworzonej faktury zakupu z akredytywą
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wprowadź lub wybierz wartość.
4. Na liście kliknij łącze w wybranym wierszu.
5. Kliknij przycisk Wiersze.
6. W polu Data wprowadź datę.
7. W polu Konto podaj żądane wartości.
8. Kliknij opcję Rozlicz transakcje.
9. Rozwiń sekcję Sumy.
10. W polu Pokaż wybierz opcję.
    * Sprawdź, czy pola Numer dokumentu banku i Numer wysyłki zostały zaktualizowane.  
11. Zaznacz pole wyboru Zaznacz.
12. Kliknij przycisk OK.
13. Kliknij kartę Płatność.
    * Sprawdź, czy pola Numer dokumentu banku i Numer wysyłki zostały zaktualizowane.  
14. Kliknij przycisk Księguj.
15. Zamknij stronę.
16. Zamknij stronę.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Weryfikacja stanu akredytywy importowej po zapłacie faktury
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
    * Zweryfikuj stan akredytywy importowej.   
4. Zamknij stronę.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Weryfikacja raportu o limicie i wykorzystaniu instrumentu bankowego
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Zapytania i raporty > Akredytywy lub poręczenia > Raport produktów bankowych i wykorzystania.
2. Rozwiń sekcję Rekordy do uwzględnienia.
3. Kliknij przycisk Filtr.
    * W polu Kryteria wpisz wymagane konto bankowe.  
4. W polu Kryteria wprowadź lub wybierz wartość.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk OK.
7. Kliknij przycisk OK.
    * Sprawdź raport zawierający listę transakcji.  
    * Sprawdź, czy w raporcie znajdują się transakcje z numerem dokumentu banku, limit instrumentu, wykorzystaną kwotą i kwotą salda instrumentu.  
8. Zamknij stronę.

