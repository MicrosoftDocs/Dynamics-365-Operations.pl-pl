---
title: Określanie sekwencji zadań produkcji procesowej
description: Ta procedura wykorzystuje farby dla przykładu prezentującego sposób ustawienia kolejności planowanych zamówień zgodnie z priorytetem koloru i rozmiaru paczki.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage, PMFSeqReqRoute, PMFSeqReqRouteChanges, PMFSeqReqSchedDetailsFactBox, PMFSequenceGroup, PMFSequenceItemTable, PMFSequenceTable, PmfSeqWrkCtrCapRes
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e54cfa60fa9efd511aef8c074484b9b1a738e8cb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572752"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Określanie sekwencji zadań produkcji procesowej

[!include [banner](../../includes/banner.md)]

Ta procedura wykorzystuje farby dla przykładu prezentującego sposób ustawienia kolejności planowanych zamówień zgodnie z priorytetem koloru i rozmiaru paczki. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USPI. Ta procedura jest przeznaczona dla planisty produkcji.


## <a name="run-master-planning-for-uspi"></a>Wykonywanie planowania głównego dla firmy USPI
1. Wybierz kolejno opcje Planowanie główne > Planowanie główne > Uruchom > Planowanie główne.
2. W polu Plan główny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz opcję Plan główny.  
4. Kliknij przycisk OK.
    * Spowoduje to rozpoczęcie planowania głównego, łącznie z procesem ustalania kolejności operacji. Proces może potrwać kilka minut.  

## <a name="view-planned-orders-for-the-paint-products"></a>Wyświetlanie planowanych zamówień na farby
1. Wybierz kolejno opcje Planowanie główne > Planowanie główne > Zamówienia planowane.
2. Rozwiń pole informacji Szczegóły pozycji.
3. Rozwiń pole informacji Szczegóły harmonogramu.
4. W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz opcję Plan główny.  
6. Na liście kliknij łącze w wybranym wierszu.
7. Użyj szybkiego filtru, aby filtrować na podstawie pola Numer pozycji z wartością „P300”.
    * Odblokuj, aby przewinąć w prawo i zobaczyć datę zamówienia oraz datę dostawy. Zwróć uwagę, że te towary mają datę zamówienia Dzisiaj, a daty dostawy zamówień planowanych nie są ustawione w kolejności pod względem priorytetu koloru i rozmiaru paczki, jak to widać w nazwie produktu. Można umieścić wskaźnik myszy nad numerem towaru, aby zobaczyć nazwę produktu i priorytet.  

## <a name="sequence-planned-orders-for-paint"></a>Ustawianie kolejności planowanych zamówień na farby
1. Zamknij stronę.
2. Wybierz kolejno opcje Planowanie główne > Planowanie główne > Kolejne planowane zlecenia.
3. Rozwiń pole informacji Szczegóły pozycji.
4. Rozwiń pole informacji Szczegóły harmonogramu.
    * Uwaga: Tutaj widać, że daty/godziny rozpoczęcia planowanych zamówień są ustawione w kolejności według koloru i rozmiaru paczki w przedziale czasu 28 dni. Te okresy są definiowane przez liczbę w polu Kampania. Formularz zamówienia planowanego sekwencji działa jak typowy formularz zamówienia planowanego i planista produkcji może tutaj akceptować zamówienia planowane.  
5. Zaznacz wszystkie wiersze.
6. Kliknij przycisk Akceptuj.
    * Spowoduje to aktualizację planowanych zamówień o wybraną akcję sekwencji Opóźnij lub Przejdź dalej.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Weryfikowanie kolejności planowanych zamówień
1. Zamknij stronę.
2. Wybierz kolejno opcje Planowanie główne > Planowanie główne > Zamówienia planowane.
3. Rozwiń pole informacji Szczegóły pozycji.
4. Rozwiń pole informacji Szczegóły harmonogramu.
5. W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz opcję Plan główny.  
7. Na liście kliknij łącze w wybranym wierszu.
8. Użyj szybkiego filtru, aby filtrować na podstawie pola Numer pozycji z wartością „P300”.
    * Zwróć uwagę, że zamówienia są teraz ustawione w kolejności według priorytetu koloru i rozmiaru, a planowane zamówienia rozpoczynają się od najwcześniejszej daty zamówienia i daty dostawy. Sprawdź poprawność zawartości kolumny Data zamówienia lub pola Data rozpoczęcia w polu informacji Szczegóły harmonogramu.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]