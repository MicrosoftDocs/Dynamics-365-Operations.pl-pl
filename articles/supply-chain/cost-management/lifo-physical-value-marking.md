---
title: LIFO z wartością fizyczną i oznaczeniami
description: Ostatni na wejściu — pierwszy na wyjściu (Last in, first out; LIFO) to model magazynu, w którym ostatnie (najnowsze) przyjęcia na magazyn są wydawane jako pierwsze. Rozchody zapasów są rozliczane w kolejności odwrotnej do odbierania towarów w magazynie, na podstawie daty transakcji magazynowej.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1acc103291c5d648ac7e179a598348cd9cc2a93
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135578"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]

Last in, first out (LIFO) to metoda zarządzania zapasami i ich wyceny, w której zapasy, które zostały wyprodukowane lub nabyte jako ostatnie, są sprzedawane, wykorzystywane lub usuwane w pierwszej kolejności. Podczas procesu zamknięcia inwentaryzacji w Microsoft Dynamics 365 Supply Chain Management system tworzy rozrachunki, w których ostatnie przyjęcie jest dopasowywane do pierwszego wydania, i tak dalej. Rozliczenia i zasada współmierności oparte są na dacie finansowej transakcji inwentaryzacyjnych. Wstępna ocena rozliczeń i korekt może być dokonana poprzez uruchomienie procesu przeliczania inwentarza.

Możesz obejść zasadę LIFO, oznaczając transakcje inwentaryzacyjne tak, by odbiór konkretnej pozycji był rozliczany z konkretnym wydaniem. Okresowe zamknięcie inwentaryzacji jest wymagane, gdy używasz modelu inwentaryzacji LIFO do tworzenia rozrachunków i korygowania wartości wydań zgodnie z zasadą LIFO. Dopóki nie przeprowadzisz procesu zamknięcia inwentarza, transakcje wydania są wyceniane według średniej bieżącej z momentu aktualizacji fizycznej i finansowej. Jeśli nie używasz znakowania, średnia krocząca jest obliczana w momencie przeprowadzania fizycznej lub finansowej aktualizacji.

Poniższe przykłady ilustrują wpływ stosowania LIFO w trzech konfiguracjach:

- LIFO bez opcji **Włącz wartość fizyczną**
- LIFO z opcją **Włącz wartość fizyczną**
- Model LIFO z zaznaczaniem

## <a name="lifo-without-the-include-physical-value-option"></a>Model LIFO bez opcji Włącz wartość fizyczną

W tym przykładzie pole wyboru **Uwzględnij wartość fizyczną** jest wyczyszczony w grupie modeli pozycji dla zwolnionego produktu. Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji)
- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o metodę LIFO pierwsza zaktualizowana finansowo sprawa zostanie rozliczona z ostatnim zaktualizowanym finansowo pokwitowaniem, i tak dalej. W tym przykładzie jedno rozliczenie jest tworzone między 5b a 3b. Korekta o 14,00 USD zostanie wprowadzona do 3b, a ostateczny koszt wyniesie 30,00 USD.

Poniższa ilustracja pokazuje efekt użycia modelu zapasów FIFO do tej serii transakcji, gdy nie jest używana opcja **Włącz wartość fizyczną**.

![LIFO bez opcji Włącz wartość fizyczną.](./media/lifo-without-including-physical-value.png)

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każda data w diagramie jest oddzielona cienką, czarną, pionową linią. Data jest podana na dole diagramu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="lifo-with-the-include-physical-value-option"></a>Model LIFO z opcją Włącz wartość fizyczną

Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupy modeli pozycji**, system używa zarówno fizycznej, jak i finansowej transakcji przyjęcia do obliczenia średniego kroczącego kosztu własnego. W razie potrzeby system dokona również korekt w fizycznie zaktualizowanej transakcji dotyczącej rozchodu. Po usunięciu zaznaczenia z pola wyboru **Włącz wartość fizyczną** przy zamknięciu magazynu z zastosowaniem metody LIFO wg daty rozliczone zostaną jedynie transakcje zaktualizowane finansowo.

Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 16,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 3b. Wydanie finansowe zapasów dla ilości 1 szt. w cenie nabycia 16,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 23,67 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o metodę LIFO pierwsza zaktualizowana finansowo sprawa zostanie rozliczona z ostatnim zaktualizowanym finansowo pokwitowaniem, i tak dalej. W tym przykładzie jedno rozliczenie jest tworzone między 3b a 5b. Korekta o 14,00 USD zostanie wprowadzona do 3b, a ostateczny koszt wyniesie 30,00 USD. Dodatkowo transakcja 6a zostanie skorygowana względem transakcji przyjęcia 4a. System nie rozliczy tych transakcji, ponieważ przyjęcie jest zaktualizowane fizycznie, ale nie finansowo. Zamiast tego, tylko korekta w wysokości 1,33 USD zostanie zaksięgowana do transakcji fizycznej emisji, a wynikowy skorygowany koszt będzie wynosił 25,00 USD.

Poniższa ilustracja pokazuje efekty modelu magazynu LIFO na tę serię transakcji, gdy używana jest opcja **Włącz wartość fizyczną**.

![LIFO z opcją Włącz wartość fizyczną.](./media/lifo-with-included-physical-value.png)

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każda data w diagramie jest oddzielona cienką, czarną, pionową linią. Data jest podana na dole diagramu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="lifo-with-marking"></a>LIFO z oznaczaniem

Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Ponieważ zamówienie jest pilne, trzeba zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy.

Trzeba się upewnić, że koszt tej pozycji magazynowej zostanie uwzględniony w marży (lub koszcie własnym sprzedaży, COGS) na tej fakturze za zamówienie sprzedaży. Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Jeśli to zamówienie sprzedaży zostanie przypisane do takiego zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury, koszt sprzedanych towarów wyniesie 120 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych.

Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie.

Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Możesz wykonać to oznaczenie z linii zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**, wybierając **Zapasy \> Oznaczenie** na skróconej karcie **Wiersze zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**.

Można też zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów.

Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3c. Inwentaryzacyjna emisja finansowa dla 3b jest oznaczona jako inwentaryzacyjna emisja finansowa dla 2b.
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji)
- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o zasadę oznaczania, która wykorzystuje metodę LIFO, oznaczone transakcje są rozliczane między sobą. W tym przykładzie, 3b jest rozliczane z 2b, a korekta o 6,00 USD jest księgowana na 3b, aby wartość wynosiła 22,00 USD. W tym przykładzie nie są dokonywane żadne dodatkowe rozliczenia, ponieważ zamknięcie tworzy rozliczenia tylko dla transakcji zaktualizowanych finansowo.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 17,50 USD.

Poniższa ilustracja pokazuje wpływ modelu magazynowego LIFO na tę serię transakcji, jeśli używane są oznaczenia między przychodem i rozchodem.

![LIFO z oznaczaniem.](./media/lifo-with-marking.png)

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każda data w diagramie jest oddzielona cienką, czarną, pionową linią. Data jest podana na dole diagramu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej.
- Rozliczenia i oznaczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
