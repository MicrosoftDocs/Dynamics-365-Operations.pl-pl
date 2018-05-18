---
title: "LIFO wg daty z wartością fizyczną i oznaczeniami"
description: "Ostatnie przyszło, pierwsze wyszło na dzień (LIFO na dzień) to model magazynu oparty na metodzie LIFO. Rozchody zapasów są rozliczane w kolejności odwrotnej do odbierania towarów w magazynie, na podstawie daty transakcji magazynowej. W metodzie LIFO wg daty jeśli nie ma żadnego przyjęcia przed wydaniem, wydanie jest rozliczane względem dowolnego przyjęcia po dacie wydania. Kilka rozchodów tego samego dnia można rozliczyć w kolejności ostatni rozchód, ostatnie przyjęcie."
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
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0b94d3f23c929c45a67894bd08706144c9226491
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="lifo-date-with-physical-value-and-marking"></a>LIFO wg daty z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Ostatnie przyszło, pierwsze wyszło na dzień (LIFO na dzień) to model magazynu oparty na metodzie LIFO. Rozchody zapasów są rozliczane w kolejności odwrotnej do odbierania towarów w magazynie, na podstawie daty transakcji magazynowej. W metodzie LIFO wg daty jeśli nie ma żadnego przyjęcia przed wydaniem, wydanie jest rozliczane względem dowolnego przyjęcia po dacie wydania. Kilka rozchodów tego samego dnia można rozliczyć w kolejności ostatni rozchód, ostatnie przyjęcie. 

W modelu magazynowym LIFO wg daty, jeśli nie ma przyjęcia przed rozchodem, rozchód jest rozliczany z dowolnego przyjęcia po dacie rozchodu. Kilka rozchodów tego samego dnia można rozliczyć w kolejności ostatni rozchód, ostatnie przyjęcie. Jeśli używany jest model LIFO wg daty, nie trzeba używać reguły LIFO wg daty. Zamiast tego można oznaczać transakcje magazynowe, dla których określony przychód towaru będzie rozliczony z określonym rozchodem. 

Zaleca się okresowe zamykanie magazynu podczas używania modelu magazynowego LIFO wg daty. 

Poniższe przykłady ilustrują wpływ stosowania LIFO wg daty w trzech konfiguracjach:

-   LIFO wg daty bez opcji **Włącz wartość fizyczną**
-   LIFO wg daty z opcją **Włącz wartość fizyczną**
-   LIFO na dzień z przypisaniem

## <a name="lifo-date-without-the-include-physical-value-option"></a>LIFO wg daty bez opcji Włącz wartość fizyczną
W tym przykładzie FIFO grupa modelu towaru nie jest oznaczona i nie zawiera wartości fizycznej. Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 15,00 USD (średnia ruchoma zaktualizowanych finansowo transakcji).
-   4b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 15,00 USD (średnia ruchoma zaktualizowanych finansowo transakcji).
-   5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   6. Wykonywane jest zamknięcie magazynu. W ramach metody LIFO wg dnia miejsce najpóźniej finansowo zaktualizowany rozchód zostanie rozliczony względem mającego miejsce najpóźniej finansowo zaktualizowanego przychodu na dzień. W przypadku transakcji dotyczącej rozchodu zostanie dokonana korekta w wysokości 5,00 USD. Wspomniane transakcje zostaną rozliczone względem siebie.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z finansowo zaktualizowanych transakcji na poziomie 15,00 USD. 

Poniższa ilustracja pokazuje efekty modelu magazynu LIFO wg daty, gdy nie jest używana opcja **Włącz wartość fizyczną**. ![Data LIFO z uwzględnianiem wartości fizycznej](./media/lifodatewithoutincludephysicalvalue.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie Quantity@Unitprice.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="lifo-date-with-the-include-physical-value-option"></a>LIFO wg daty z opcją Włącz wartość fizyczną
Można zaznaczyć pole wyboru **Włącz wartość fizyczną** dla towaru na stronie **Grupy modeli towaru**. W tym przypadku system używa zarówno fizycznej, jak i finansowej transakcji przyjęcia do obliczenia średniej kroczącej kosztu własnego. W razie potrzeby system dokona również korekt w fizycznie zaktualizowanej transakcji dotyczącej rozchodu. Po usunięciu zaznaczenia z pola wyboru **Włącz wartość fizyczną** przy zamknięciu magazynu z zastosowaniem metody LIFO wg daty rozliczone zostaną jedynie transakcje zaktualizowane finansowo. 

W tym przykładzie FIFO grupa modelu towaru jest oznaczona i zawiera wartość fizyczną. 

Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 18,33 USD (średnia ruchoma zaktualizowanych finansowo transakcji).
-   4b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 18,33 USD (średnia ruchoma zaktualizowanych finansowo transakcji).
-   5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   6. Wykonywane jest zamknięcie magazynu. W ramach metody LIFO wg daty mający miejsce najpóźniej zaktualizowany rozchód zostanie skorygowany lub rozliczony względem mającego miejsce najpóźniej zaktualizowanego przychodu na dzień. Wspomniane transakcje nie zostaną rozliczone względem siebie, ponieważ transakcja dotycząca finansowego przychodu jest skorygowana względem transakcji zaktualizowanej fizycznie. Zamiast tego, w przypadku transakcji dotyczącej rozchodu zostanie dokonana korekta w wysokości 6,67 USD.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z finansowo zaktualizowanych transakcji na poziomie 20,00 USD. 

Poniższa ilustracja pokazuje efekty modelu magazynu LIFO, gdy używana jest opcja **Włącz wartość fizyczną**. ![Data LIFO z uwzględnianiem wartości fizycznej](./media/lifodatewithincludephysicalvalue.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie Quantity@Unitprice.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="lifo-date-with-marking"></a>LIFO na dzień z przypisaniem
Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. 

Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Zlecenie jest pilne, trzeba będzie zatem zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Trzeba się upewnić, że koszt tej pozycji magazynowej zostanie uwzględniony w marży (lub koszcie własnym sprzedaży, COGS) na tej fakturze za zamówienie sprzedaży. 

Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Jeśli to zamówienie sprzedaży zostanie przypisane do takiego zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury, koszt sprzedanych towarów wyniesie 120 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. 

Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie. 

Na przykład transakcja przyjęcia jest oznaczona dla transakcji wydania. W takim przypadku metoda wyceny zdefiniowania w grupie modeli towaru dla danej pozycji jest pomijana, a transakcje są rozliczane względem siebie. 

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

Poniższa ilustracja pokazuje efekty modelu magazynu LIFO, gdy używane jest oznaczanie między przychodami i rozchodami towarów. ![Data LIFO z oznaczaniem](./media/lifodatewithmarking.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie Quantity@Unitprice.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.





