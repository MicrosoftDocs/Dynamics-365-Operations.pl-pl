--- 
title: "Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień"
description: "W tej procedurze pokazano sposób wprowadzania odpowiedzi na ZO, oceniania i porównywania ofert, a następnie przyznawania realizacji oferty jednemu z dostawców."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d7c76eab2cca4e15c13dd9f79432b9c6d81071a2
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób wprowadzania odpowiedzi na ZO, oceniania i porównywania ofert, a następnie przyznawania realizacji oferty jednemu z dostawców. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Przed rozpoczęciem trzeba mieć ZO z dwoma wierszami, które zostało wysłane co najmniej do dwóch dostawców. Można utworzyć takie niezbędne ZO za pomocą procedury „Tworzenie zapytania ofertowego”. Przed wykonaniem tej procedury należy skonfigurować kryteria punktowania.


## <a name="enter-a-reply-from-a-vendor"></a>Wprowadzanie odpowiedzi od dostawcy
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.
2. Zaznacz ZO o stanie Wysłane, a następnie kliknij łącze na numerze sprawy zapytania ofertowego.
    * ZO powinno było zostać wysłane co najmniej do 2 dostawców.  
3. Kliknij nagłówek i przejdź do listy dostawców.
4. Wybierz dostawcę, dla którego chcesz wprowadzić odpowiedź na ZO.
5. Kliknij opcję Wprowadź odpowiedź.
6. W okienku akcji kliknij pozycję Odpowiedz.
7. Kliknij opcję Kopiuj dane do odpowiedzi.
    * Ta akcja spowoduje skopiowanie wybranych danych, na przykład ilości ze sprawy ZO do odpowiedzi na ZO. Alternatywnie można pominąć tę akcję i wypełnić wszystkie pola odpowiedzi ręcznie podczas edytowania odpowiedzi.  
8. Kliknij przycisk Edytuj.
9. Wprowadź liczbę w polu Cena jednostkowa.
10. Wybierz drugi wiersz oferty.
11. Wprowadź liczbę w polu Cena jednostkowa.

## <a name="score-the-bid"></a>Ocenianie oferty
1. Kliknij nagłówek i przejdź do punktacji oferty.
2. Rozwiń sekcję Punktowanie oferty.
3. W polu Punktacja wprowadź liczbę dla jednego z kryteriów punktowania.
    * Po umieszczeniu wskaźnika myszy nad jednym z kryteriów punktowania pojawia się etykietka narzędzia pokazująca zakres punktów, w którym trzeba się zmieścić. W tej demonstracji można dodać liczbę z zakresu od 1 do 5 do każdego z kryteriów.  
4. Zaznacz inne kryterium punktowania.
5. W polu Punktacja wprowadź liczbę.
6. Rozwiń sekcję Kwestionariusze.
    * Jeśli sprawa ZO zawiera kwestionariusz, który został wysłany do dostawców, można wprowadzić ich odpowiedzi w sekcji kwestionariuszy.  
7. Zamknij stronę.

## <a name="enter-a-reply-for-another-vendor"></a>Wprowadzanie odpowiedzi od innego dostawcy
1. Wybierz następnego dostawcę, usuwając zaznaczenie dostawcy, dla którego właśnie wprowadzono odpowiedź, a następnie zaznaczając wiersz następnego dostawcy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Kliknij opcję Wprowadź odpowiedź.
4. Kliknij opcję Kopiuj dane do odpowiedzi.
5. Kliknij przycisk Edytuj.
6. Wprowadź liczbę w polu Cena jednostkowa.
7. Wybierz drugi wiersz oferty.
8. Wprowadź liczbę w polu Cena jednostkowa.

## <a name="score-the-second-bid"></a>Ocenianie drugiej oferty
1. Kliknij nagłówek i przejdź do punktacji oferty.
2. W polu Punktacja wprowadź liczbę.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. W polu Punktacja wprowadź liczbę.

## <a name="compare-the-replies"></a>Porównywanie odpowiedzi
1. W okienku akcji kliknij pozycję Ogólne.
2. Kliknij opcję Porównaj odpowiedzi.
3. W polu Ranga wprowadź liczbę.
    * Ta strona pokazuje oferty z nagłówkami i wierszami oraz łączny wynik punktowy na poziomie nagłówka. Wiersze można porównywać poprzez sortowanie ich w siatce, tak aby porównywalne wiersze znalazły się obok siebie. Znajdują się tu również następujące informacje:   Ilość: Ilość oferowana przez dostawcę. Ta ilość może nie być równa ilości określonej w ZO.   Kwota netto: Cena wskazana przez dostawcę, po odjęciu rabatów dla towarów w wierszu.   Odchylenie: Liczba dni różnicy między datą dostawy w ofercie lub wierszu a wymaganą datą dostawy w nagłówku lub wierszu zapytania ofertowego.   Dla każdej oferty można wprowadzić rangę.  
4. Zaznacz wiersz nagłówka dla drugiej oferty, którą chcesz sklasyfikować.
5. W polu Ranga wprowadź liczbę.
6. Kliknij przycisk Zapisz.

## <a name="reject-a-bid"></a>Odrzucanie oferty
1. Zaznacz wiersz nagłówka dla oferty, którą odrzucić.
    * Można zaakceptować, odrzucić albo zwrócić tylko jedną ofertę lub wiersz jednej oferty na raz.  
2. Zaznacz pole wyboru Zaznacz.
    * Zaznaczenie pola wyboru Zaznacz w nagłówku oferty spowoduje oznaczenie również wszystkich wierszy. Można również oznaczyć podzbiór wierszy oferty, aby odrzucić lub zaakceptować tylko je. Można zaakceptować ofertę jednego dostawcy dla niektórych wierszy ZO, a następnie przyznać realizację pozostałych wierszy ZO innemu dostawcy. Trzeba to jednak zrobić w 2 krokach, po jednej ofercie na raz. Jeśli istnieją wiersze alternatywne, można zaakceptować jedynie oryginalny wiersz oferty lub jego alternatywę, ale nie oba.  
3. Kliknij przycisk Odrzuć.
4. Kliknij przycisk Parametry, aby otworzyć rozwijane okno dialogowe.
5. W polu Przyczyna odrzucenia wprowadź lub wybierz wartość.
    * Przyczyna odrzucenia będzie przechowywana w odpowiedzi.  
6. Kliknij przycisk OK.
7. Kliknij przycisk OK.
8. Zamknij stronę.
9. Zamknij stronę.
10. Odśwież stronę.

## <a name="accept-a-bid"></a>Akceptowanie oferty
1. Wybierz ofertę, którą chcesz zaakceptować, a następnie kliknij łącze w polu Zapytanie ofertowe.
2. W okienku akcji kliknij pozycję Odpowiedz.
3. Kliknij przycisk Akceptuj.
    * Po oznaczeniu określonych wierszy czynność akceptacji obejmie tylko te wiersze. Jeśli chcesz zaakceptować wszystkie wiersze oferty, nie trzeba oznaczać wierszy.  
4. Kliknij przycisk Parametry, aby otworzyć rozwijane okno dialogowe.
    * Dzięki temu można zarejestrować przyczynę zaakceptowania oferty. Przyczyna będzie przechowywana w ofercie.  
5. W polu Przyczyna akceptacji wprowadź lub wybierz wartość.
6. Kliknij przycisk OK.
7. Kliknij przycisk OK.
    * Po kliknięciu przycisku OK zostanie wygenerowane zamówienie zakupu na podstawie wierszy objętych akceptacją ZO. Jeśli istnieją inne oferty, które nie zostały przetworzone (zaakceptowane, odrzucone lub zwrócone), system wyświetli monit o odrzucenie pozostałych ofert.  

## <a name="view-the-purchase-order-thats-been-generated"></a>Wyświetlanie wygenerowanego zamówienia zakupu
1. W okienku akcji kliknij pozycję Ogólne.
2. Kliknij opcję Zamówienie zakupu.
    * Tutaj widać zamówienie zakupu wygenerowane w momencie akceptacji oferty.  
3. Zamknij stronę.
4. Zamknij stronę.
5. Zamknij stronę.
6. Zamknij stronę.


