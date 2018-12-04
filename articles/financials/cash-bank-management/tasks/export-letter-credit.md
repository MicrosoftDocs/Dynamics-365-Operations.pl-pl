--- 
title: Akredytywa eksportowa
description: Ta procedura poprowadzi przez proces tworzenia akredytywy eksportowej.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 730a6cc6ed4872f8d0ad92b89665587f472f6791
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="export-letter-of-credit"></a>Akredytywa eksportowa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura poprowadzi przez proces tworzenia akredytywy eksportowej.

Akredytywa jest umową wystawianą przez bank, w której bank wyraża zgodę na zapłatę w imieniu nabywcy, jeśli zostaną spełnione warunki umowy między nabywcą a sprzedawcą.



Przed uruchomieniem tej procedury wykonaj procedury „Konfigurowanie instrumentów bankowych i profilów księgowania” oraz „Akredytywa_Tworzenie umowy instrumentu bankowego”. Aby pomyślnie wykonać tę procedurę, należy zaznaczyć firmę demonstracyjną USMF.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Tworzenie zamówienia sprzedaży dla akredytywy
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Rozwiń lub zwiń sekcję Ogólne.
7. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Zaznacz oddział, w którym jest składowany towar przeznaczony do wydania.  
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Zaznacz magazyn, w którym jest składowany towar przeznaczony do wydania.  
10. Na liście kliknij łącze w wybranym wierszu.
    * Uwaga: Wybierz pole Typ dokumentu bankowego z wartością „Akredytywa”.  
11. W polu Typ dokumentu bankowego wybierz opcję „Akredytywa”.
12. Rozwiń lub zwiń sekcję Dostawa.
    * W polu Kontrola daty dostawy wybierz wartość Brak.  
13. W polu Żądana data odbioru wpisz datę.
14. Kliknij przycisk OK.
15. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Zaznacz towar, który ma zostać wydany/sprzedany.  
16. Na liście znajdź i zaznacz odpowiedni rekord.
17. Na liście kliknij łącze w wybranym wierszu.
18. W polu Cena jednostkowa wpisz liczbę.
19. Rozwiń lub zwiń sekcję Szczegóły wiersza.
20. Kliknij kartę Dostawa.
21. W polu Żądana data wysyłki wpisz datę.
22. W polu Potwierdzona data wysyłki wpisz datę.
23. W okienku akcji kliknij pozycję Zarządzaj.
24. Kliknij opcję Akredytywa.
25. W polu Numer dokumentu banku wpisz wartość.
26. W polu Data wygaśnięcia wprowadź datę i godzinę.
27. Rozwiń lub zwiń sekcję Szczegóły banku.
28. W polu Bank wystawiający kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
29. Na liście kliknij łącze w wybranym wierszu.
30. W polu Bank doradczy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
31. Na liście znajdź i zaznacz odpowiedni rekord.
32. Na liście kliknij łącze w wybranym wierszu.
33. Kliknij opcję Pobierz wysyłki zamówień sprzedaży.
34. Kliknij opcję Wystaw dokument bankowy.
35. Zamknij stronę.

## <a name="post-packing-slip"></a>Księgowanie dokumentu dostawy
1. W okienku akcji kliknij opcję Pobierz i zapakuj.
2. Kliknij opcję Księguj dokument dostawy.
3. Rozwiń lub zwiń sekcję Parametry.
4. W polu Ilość zaznacz opcję „Wszystko”.
5. Rozwiń lub zwiń sekcję Ustawienia.
6. W polu Data dokumentu dostawy wprowadź datę.
7. Wybierz numer wysyłki.
8. Na liście kliknij łącze w wybranym wierszu.
9. Kliknij przycisk OK.
10. Kliknij przycisk OK.

## <a name="post-sales-invoice"></a>Księgowanie faktury sprzedaży
1. W okienku akcji kliknij pozycję Faktura.
2. Kliknij opcję Faktura.
3. Rozwiń lub zwiń sekcję Przegląd.
4. Wybierz numer wysyłki.
5. Na liście kliknij łącze w wybranym wierszu.
6. Rozwiń lub zwiń sekcję Ustawienia.
7. Wprowadź datę w polu Data faktury.
8. Kliknij przycisk OK.
9. Kliknij przycisk OK.

## <a name="shipment-document-submitted-status"></a>Stan przesłania dokumentu wysyłki
1. W okienku akcji kliknij pozycję Zarządzaj.
2. Kliknij opcję Akredytywa.
3. Rozwiń lub zwiń sekcję Wiersze.
    * Uwaga: Pole „Dokument przesłany” powinno być ustawione na wartość „Tak”.  

## <a name="verify-export-letter-of-credit"></a>Weryfikacja akredytywy eksportowej
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa eksportowa i inkaso importowe.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
    * Sprawdź, czy akredytywa eksportowa ma w polu Stan wysyłki wartość „Zafakturowane”.  

## <a name="customer-payment"></a>Płatność od odbiorcy
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk Wiersze.
7. W polu Data wprowadź datę.
8. W polu Konto podaj żądane wartości.
9. Kliknij opcję Rozliczenie.
10. Zaznacz pole wyboru w nagłówku formantu Sumy.
    * Uwaga: W polu Pokaż ustaw wartość „Akredytywa”.  
11. Na liście znajdź i zaznacz odpowiedni rekord.
12. Zaznacz lub wyczyść pole wyboru Zaznacz.
13. Kliknij przycisk OK.
14. Kliknij kartę Płatność.
    * Sprawdź informacje w polach Numer dokumentu banku i Numer wysyłki.  
15. Kliknij przycisk Księguj.

## <a name="verify-export-letter-of-credit-after-payment"></a>Sprawdzanie poprawności akredytywy eksportowej po zapłacie
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa eksportowa i inkaso importowe.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
    * Sprawdź, czy Stan wysyłki = Płatność otrzymana, a kwota salda = 0,00.  


