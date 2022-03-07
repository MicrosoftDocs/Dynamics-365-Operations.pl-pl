---
title: FIFO z wartością fizyczną i oznaczeniami
description: Pierwszy na wejściu — pierwszy na wyjściu (First in, first out; FIFO) to model magazynu, w którym wcześniejsze nabycia są wydawane w pierwszej kolejności. Finansowo zaktualizowane elementy z magazynu są rozliczane z pierwszymi finansowo zaktualizowanymi przychodami do magazynu, na podstawie daty finansowej transakcji magazynowej.
author: AndersGirke
manager: tfehr
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 54682
ms.assetid: dc0e2855-83a0-41a7-a398-3c7852597d1a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1322d43d536bf7ff4c40fcdecebbd95a46f70d2d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435203"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]

Pierwszy na wejściu — pierwszy na wyjściu (First in, first out; FIFO) to model magazynu, w którym wcześniejsze nabycia są wydawane w pierwszej kolejności. Finansowo zaktualizowane elementy z magazynu są rozliczane z pierwszymi finansowo zaktualizowanymi przychodami do magazynu, na podstawie daty finansowej transakcji magazynowej. 

Jeśli używany jest model FIFO, nie trzeba używać reguły FIFO. Zamiast tego można oznaczać transakcje magazynowe, dla których określony przychód towaru będzie rozliczony z określonym rozchodem. Zaleca się okresowe zamykanie magazynu podczas używania modelu magazynowego FIFO wg daty.. Poniższe przykłady ilustrują wpływ stosowania FIFO w trzech konfiguracjach:

-   FIFO bez opcji **Włącz wartość fizyczną**
-   FIFO z opcją **Włącz wartość fizyczną**
-   FIFO z oznaczaniem

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO bez opcji Włącz wartość fizyczną
W tym przykładzie FIFO grupa modelu towaru nie jest oznaczona i nie zawiera wartości fizycznej. Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 2 i po koszcie 10,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 2 i po koszcie 10,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5a. Fizyczne wydanie z magazynu ilości równej 1 o jednostkowym koszcie własnym równym 20,00 zł (średnia krocząca transakcji zaktualizowanych finansowo).
-   5b. Finansowe wydanie z magazynu ilości równej 1 o jednostkowym koszcie własnym równym 15,00 zł (średnia krocząca transakcji zaktualizowanych finansowo).
-   6. Wykonywane jest zamknięcie magazynu. Zgodnie z metodą FIFO, pierwszy finansowo zaktualizowany rozchód będzie rozliczony z pierwszym finansowo zaktualizowanym przychodem. Dla transakcji wydania zostaje dokonana korekta równa 5,00 USD.

Nowy średni bieżący koszt własny odzwierciedla średnią finansowo zaktualizowanych transakcji. Poniższe ilustracje pokazują efekty modelu magazynu FIFO na tę serię transakcji, gdy opcja **Włącz wartość fizyczną** nie jest używana. 

![Model FIFO bez uwzględniania wartości fizycznej](./media/fifowithoutincludephysicalvalue.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO z opcją Włącz wartość fizyczną
Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupa modeli pozycji**, system używa zarówno fizycznej, jak i finansowej transakcji przyjęcia do obliczenia średniego kroczącego kosztu własnego. W razie potrzeby system dokona również korekt w fizycznie zaktualizowanej transakcji dotyczącej rozchodu. Po usunięciu zaznaczenia z pola wyboru **Włącz wartość fizyczną** przy zamknięciu magazynu z zastosowaniem metody FIFO na dzień rozliczone zostaną jedynie transakcje zaktualizowane finansowo. Na ilustracji przedstawiono następujące transakcje:

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
-   7. Wykonywane jest zamknięcie magazynu. Zgodnie z metodą FIFO, finansowa transakcja rozchodu będzie skorygowana lub rozliczona z pierwszym zaktualizowanym przychodem, finansowym lub fizycznym.

Transakcja 5b będzie rozliczona z transakcją przychodu 1b. Wystąpi korekta kwoty 11,25 USD dla tej transakcji rozchodu. Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 27,50 USD. Poniższa ilustracja pokazuje efekty modelu magazynu FIFO na tę serię transakcji, gdy używana jest opcja **Włącz wartość fizyczną**. 

![Model FIFO z uwzględnianiem wartości fizycznej](./media/fifowithincludephysicalvalue.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="fifo-with-marking"></a>FIFO z oznaczaniem
Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Ponieważ zamówienie jest pilne, trzeba zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Trzeba się upewnić, że koszt tej pozycji magazynowej zostanie uwzględniony w marży (lub koszcie własnym sprzedaży, COGS) na tej fakturze za zamówienie sprzedaży. Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Jeśli to zamówienie sprzedaży zostanie przypisane do takiego zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury, koszt sprzedanych towarów wyniesie 120 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie. Jeśli transakcja przyjęcia odpowiada transakcji wydania, metoda wyceny określona w grupie modeli towaru jest ignorowana, a system dokonuje wzajemnego rozliczenia tych transakcji. Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Można to zrobić z wiersza zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**. Można też zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów. Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 21,25 USD (średnia ruchoma zaktualizowanych finansowo i fizycznie transakcji).
-   5b. Finansowy rozchód magazynowy w ilości 1 zostaje przypisany do przychodu magazynowego z pozycji 2b przed zaksięgowaniem transakcji. Transakcja jest zaksięgowana z kosztem własnym 20,00 USD za sztukę.
-   6a. Fizyczny rozchód magazynowy w ilości 1 i po koszcie własnym 21,25 USD.
-   7. Wykonywane jest zamknięcie magazynu. Finansowo zaktualizowana transakcja FIFO została przypisana do istniejącego przychodu magazynowego, obie transakcje są zatem rozliczane względem siebie i nie ma miejsca żadna korekta.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 27,50 USD. Poniższa ilustracja pokazuje wpływ modelu magazynowego FIFO na tę serię transakcji, jeśli używane są oznaczenia między przychodem i rozchodem. 

![Model FIFO z oznaczaniem](./media/fifowithmarking.gif) 

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.




