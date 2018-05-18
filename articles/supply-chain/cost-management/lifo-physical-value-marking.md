---
title: "LIFO z wartością fizyczną i oznaczeniami"
description: "Ostatni na wejściu — pierwszy na wyjściu (Last in, first out; LIFO) to model magazynu, w którym ostatnie (najnowsze) przyjęcia na magazyn są wydawane jako pierwsze. Rozchody zapasów są rozliczane w kolejności odwrotnej do odbierania towarów w magazynie, na podstawie daty transakcji magazynowej."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: db6d04a64821b3b02679056f787092dc40ef4423
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="lifo-with-physical-value-and-marking"></a>LIFO z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Ostatni na wejściu — pierwszy na wyjściu (Last in, first out; LIFO) to model magazynu, w którym ostatnie (najnowsze) przyjęcia na magazyn są wydawane jako pierwsze. Rozchody zapasów są rozliczane w kolejności odwrotnej do odbierania towarów w magazynie, na podstawie daty transakcji magazynowej. 

W modelu zapasów Ostatni na wejściu — pierwszy na wyjściu (Last in, first out; LIFO) ostatnie (najnowsze) przyjęcia są wydawane jako pierwsze. Wydania z zapasów są rozliczane względem ostatnich przyjęć do zapasów na podstawie daty transakcji magazynowej. Jeśli używasz modelu LIFO, nie trzeba używać reguły LIFO. Zamiast tego można oznaczać transakcje magazynowe, tak aby określone wydania towarów były rozliczone względem określonych przyjęć. Zaleca się okresowe zamknięcia magazynu podczas używania modelu magazynu LIFO. 

Poniższe przykłady ilustrują wpływ stosowania LIFO w trzech konfiguracjach:

-   LIFO bez opcji **Włącz wartość fizyczną**
-   LIFO z opcją **Włącz wartość fizyczną**
-   Model LIFO z zaznaczaniem

## <a name="lifo-without-the-include-physical-value-option"></a>Model LIFO bez opcji Włącz wartość fizyczną
W tym przykładzie FIFO grupa modelu towaru nie jest oznaczona i nie zawiera wartości fizycznej. Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5a. Fizyczne wydanie z magazynu ilości równej 1 o jednostkowym koszcie własnym równym 20,00 zł (średnia krocząca transakcji zaktualizowanych finansowo).
-   5b. Finansowe wydanie z magazynu ilości równej 1 o jednostkowym koszcie własnym równym 20,00 zł (średnia krocząca transakcji zaktualizowanych finansowo).
-   6. Wykonywane jest zamknięcie magazynu. Na podstawie metody LIFO ostatnie zaktualizowane finansowo wydanie będzie rozliczane względem ostatniego zaktualizowanego finansowo przyjęcia. Dla transakcji wydania zostaje dokonana korekta równa 10,00 zł.

Nowa średnia krocząca kosztu własnego odzwierciedla średnią dla finansowo zaktualizowanych transakcji wynoszącą 15,00 zł. Poniższa ilustracja pokazuje efekt użycia modelu zapasów LIFO do tej serii transakcji, gdy nie jest używana opcja **Włącz wartość fizyczną**. ![Model LIFO bez uwzględniania wartości fizycznej](./media/lifowithoutincludephysicalvalue.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie Quantity@Unit.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="lifo-with-the-include-physical-value-option"></a>Model LIFO z opcją Włącz wartość fizyczną
Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupy modeli pozycji**, system używa zarówno fizycznej, jak i finansowej transakcji przyjęcia do obliczenia średniej kroczącej kosztu własnego. W razie potrzeby system dokona również korekt w fizycznie zaktualizowanej transakcji dotyczącej rozchodu. Po usunięciu zaznaczenia z pola wyboru **Włącz wartość fizyczną** przy zamknięciu magazynu z zastosowaniem metody LIFO na dzień rozliczone zostaną jedynie transakcje zaktualizowane finansowo. 

Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5a. Fizyczne wydanie z magazynu ilości równej 1 o jednostkowym koszcie własnym równym 21,25 zł (średnia krocząca transakcji zaktualizowanych finansowo i fizycznie).
-   5b. Finansowe wydanie z magazynu ilości równej 1 o jednostkowym koszcie własnym równym 21,25 zł (średnia krocząca transakcji zaktualizowanych finansowo i fizycznie).
-   6a. Fizyczny rozchód magazynowy w ilości 1 i po koszcie własnym 21,25 USD.
-   7. Wykonywane jest zamknięcie magazynu. Na podstawie metody LIFO ostatnia transakcja wydania zostaje skorygowana lub rozliczona względem ostatniego zaktualizowanego przyjęcia.

Transakcja 6a zostanie skorygowana względem transakcji przyjęcia 4b. System nie rozliczy tych transakcji, ponieważ przyjęcie jest zaktualizowane fizycznie, ale nie finansowo. W zamian dla fizycznej transakcji wydania zostanie tylko dokonana korekta równa 8,75 zł. Transakcja 5b zostanie skorygowana względem fizycznej transakcji przyjęcia 3a. System nie rozliczy tych transakcji, ponieważ nie są one obie zaktualizowane finansowo. Zamiast tego dla transakcji wydania zostanie tylko dokonana korekta równa -3,75 zł. Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 20,00 USD. 

Poniższa ilustracja pokazuje efekty modelu magazynu LIFO na tę serię transakcji, gdy używana jest opcja **Włącz wartość fizyczną**. ![Model LIFO z uwzględnianiem wartości fizycznej](./media/lifowithincludephysicalvalue.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie Quantity@Unit.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="lifo-with-marking"></a>Model LIFO z zaznaczaniem
Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Ponieważ zamówienie jest pilne, trzeba zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. 

Trzeba się upewnić, że koszt tej pozycji magazynowej zostanie uwzględniony w marży (lub koszcie własnym sprzedaży, COGS) na tej fakturze za zamówienie sprzedaży. Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Jeśli to zamówienie sprzedaży zostanie przypisane do takiego zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury, koszt sprzedanych towarów wyniesie 120 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. 

Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie. 

Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Można to zrobić z wiersza zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**. 

Można też zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów. 

Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 21,25 USD (średnia ruchoma zaktualizowanych finansowo i fizycznie transakcji).
-   5b. Finansowy rozchód magazynowy w ilości 1 zostaje przypisany do przychodu magazynowego z pozycji 2b przed zaksięgowaniem transakcji. Transakcja ta jest księgowana po koszcie własnym w wysokości 20,00 USD.
-   6a. Fizyczny rozchód magazynowy w ilości 1 i po koszcie własnym 21,25 USD.
-   7. Wykonywane jest zamknięcie magazynu. Finansowo zaktualizowana transakcja FIFO została przypisana do istniejącego przychodu magazynowego, obie transakcje są zatem rozliczane względem siebie i nie ma miejsca żadna korekta.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 27,50 USD. 

Poniższa ilustracja pokazuje wpływ modelu magazynowego LIFO na tę serię transakcji, jeśli używane są oznaczenia między przychodem i rozchodem. ![Model LIFO z oznaczaniem](./media/lifowithmarking.gif) 

**Objaśnienia do wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie Quantity@Unit.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.





