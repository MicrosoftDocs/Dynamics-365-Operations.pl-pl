--- 
title: "Transakcja poręczenia"
description: "Ta procedura poprowadzi przez proces tworzenia poręczenia."
author: kweekley
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5835469cff8295bc6486c097eaf26114fa547c00
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="letter-of-guarantee-transaction"></a>Transakcja poręczenia

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura poprowadzi przez proces tworzenia poręczenia.



Następujące zadania należy wykonać przed wykonaniem tej procedury:

- Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczenia.

- Tworzenie umowy instrumentu bankowego dla poręczenia.



Ta procedura wykorzystuje firmę demonstracyjną USMF.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Tworzenie zamówienia sprzedaży z poręczeniem
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
4. Rozwiń sekcję Ogólne.
5. W polu Oddział wprowadź lub wybierz wartość.
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Magazyn wprowadź lub wybierz wartość.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Typ dokumentu bankowego wybierz opcję „Poręczenie”.
10. Kliknij przycisk OK.
11. W polu Numer towaru wprowadź lub wybierz wartość.
12. Wprowadź liczbę w polu Cena jednostkowa.
13. Rozwiń sekcję Szczegóły wiersza.
14. Kliknij kartę Dostawa.
    * Uwaga: W polu Kontrola daty dostawy wybierz wartość Brak.  
15. W polu Żądana data wysyłki wpisz datę.
16. W polu Potwierdzona data wysyłki wpisz datę.

## <a name="process-letter-of-guaranteerequest"></a>Przetwarzanie poręczenia_Wniosek
1. W okienku akcji kliknij pozycję Zarządzaj.
2. Kliknij opcję Poręczenie.
3. W okienku akcji kliknij opcję Poręczenie.
4. Kliknij przycisk Wniosek, aby otworzyć rozwijane okno dialogowe.
5. W polu Typ wprowadź lub wybierz wartość.
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Wartość wprowadź liczbę.
8. W polu Data wygaśnięcia wprowadź datę i godzinę.
9. Kliknij przycisk OK.
10. Zamknij stronę.

## <a name="process-letter-of-guaranteesubmit-to-bank"></a>Przetwarzanie poręczenia_Prześlij do banku
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Kliknij przycisk Prześlij do banku, aby otworzyć rozwijane okno dialogowe.
4. W polu Konto bankowe wprowadź lub wybierz wartość.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk OK.

## <a name="process-letter-of-guaranteereceive-from-bank"></a>Przetwarzanie poręczenia_Otrzymaj z banku
1. Kliknij opcję Otrzymaj z banku, aby otworzyć rozwijane okno dialogowe.
2. W polu Kod banku wpisz wartość.
    * Sprawdź wartości w polach obliczeniowych Marża i Wydatki.  
3. Kliknij przycisk OK.
4. Rozwiń sekcję Akcje.
    * Sprawdź rekord „Otrzymaj z banku”.  
5. Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.
6. Kliknij przycisk Wiersze.
    * Sprawdź księgowanie wpisów w arkuszu.  
7. Zamknij stronę.

## <a name="process-letter-of-guaranteegive-to-beneficiary"></a>Przetwarzanie poręczenia_Przekaż beneficjentowi
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Na liście kliknij łącze w wybranym wierszu.
3. W okienku akcji kliknij pozycję Zarządzaj.
4. Kliknij opcję Poręczenie.
5. W okienku akcji kliknij opcję Poręczenie.
6. Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.
7. Kliknij przycisk OK.
8. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.
11. Kliknij przycisk OK.
12. Rozwiń sekcję Akcje.
    * Sprawdź rekord „Przekaż beneficjentowi”.  

## <a name="process-letter-of-guaranteeincrease-value"></a>Przetwarzanie poręczenia_Zwiększ wartość
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Na liście kliknij łącze w wybranym wierszu.
3. W okienku akcji kliknij pozycję Zarządzaj.
4. Kliknij opcję Poręczenie.
5. W okienku akcji kliknij opcję Poręczenie.
6. Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.
7. W polu Wartość do dodania wprowadź lub wybierz wartość.
8. Kliknij przycisk OK.
9. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.
10. Na liście znajdź i zaznacz odpowiedni rekord.
11. Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.
12. Kliknij przycisk OK.
13. Rozwiń sekcję Akcje.
    * Sprawdź rekord „Zwiększ wartość”.  
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.
16. Kliknij przycisk Wiersze.
    * Sprawdź zaksięgowanie wpisy w arkuszu.  

## <a name="process-letter-of-guaranteeliquidate"></a>Przetwarzanie poręczenia_Zlikwiduj
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Na liście kliknij łącze w wybranym wierszu.
3. W okienku akcji kliknij pozycję Zarządzaj.
4. Kliknij opcję Poręczenie.
5. W okienku akcji kliknij opcję Poręczenie.
6. Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.
7. Kliknij przycisk OK.
8. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.
11. Kliknij przycisk OK.
12. Rozwiń sekcję Akcje.
    * Sprawdź rekord „Zlikwiduj”.  
13. Na liście znajdź i zaznacz odpowiedni rekord.
14. Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.
15. Kliknij przycisk Wiersze.
    * Sprawdź zaksięgowanie wpisy w arkuszu.  
16. Zamknij stronę.


