---
title: Średnia ważona z datą
description: Średnia ważona z datą jest modelem magazynu opartym na zasadzie średniej ważonej, w którym towary magazynowe są szacowane na podstawie średniej wartości towarów przyjętych na magazyn dla każdego dnia osobno w okresie zamknięcia magazynu.
author: AndersGirke
manager: tfehr
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d36f60a13fbee91100e406150e7f5ca890320436
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982264"
---
# <a name="weighted-average-date"></a>Średnia ważona z datą

[!include [banner](../includes/banner.md)]

Średnia ważona z datą to model zapasów oparty na zasadzie średniej ważonej. W tej metodzie wydania z zapasów są wyceniane na podstawie średniej wartości towarów przyjętych do zapasów w każdym dniu w okresie zamknięcia zapasów. 

Podczas zamknięcia zapasów przy użyciu średniej ważonej z datą wszystkie dzienne przyjęcia są rozliczane względem wirtualnego wydania. To wirtualne wydanie zawiera łączną przyjętą ilość i wartość w danym dniu. Dla wirtualnego rozchodu istnieje odpowiadający mu wirtualny przychód, z którego zostanie rozliczony. W ten sposób wszystkie wydania mają ten sam średni koszt. Wirtualny rozchód i przychód mogą być postrzegane jako wirtualne przeniesienie na podstawie *średniej ważonej zamknięcia magazynu*. 

Jeśli do tego dnia miało miejsce tylko jedno przyjęcie, nie trzeba obliczać średniej. Ponieważ wszystkie wydania są rozliczane względem tego przyjęcia, nie zostanie utworzone wirtualne przeniesienie. Podobnie, jeśli nastąpił tylko rozchód, nie ma przychodów do obliczania średniej i wirtualne przeniesienie nie zostanie utworzone. W przypadku używania średniej ważonej z datą można oznaczać transakcje magazynowe, tak aby określone przyjęcia towarów były rozliczone względem określonych wydań. W takim przypadku nie używaj reguły średniej ważonej z datą. W przypadku używania modelu magazynowego średniej ważonej z datą zaleca się comiesięczne zamykanie magazynu. 

Średnia ważona na dzień na potrzeby wyceny zapasów jest obliczana w następujący sposób: 

Średnia ważona = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q*n* × P*n*\]) ÷ (Q1 + Q2 + Q*n*) 

Podczas zamknięcia zapasów obliczenia są wykonywane na każdy dzień okresu zamknięcia, zgodnie z poniższą ilustracją. 

![Model codziennego obliczania średniej ważonej z datą](./media/weightedaveragedatedailycalculationmodel.gif) 

Transakcje magazynowe powodujące wydania z zapasów, takie jak transakcje wynikające z zamówień sprzedaży, arkuszy magazynowych i zleceń produkcyjnych, są realizowane według szacowanego kosztu własnego na dzień księgowania. Ten szacowany koszt własny jest również określany mianem średniej kroczącej kosztu własnego. W dniu zamknięcia zapasów system analizuje transakcje magazynowe za poprzednie okresy, poprzednie dni i bieżący dzień. Ta analiza służy określaniu, która z poniższych zasad zamknięcia ma zostać użyta:

-   Rozliczenie bezpośrednie
-   Rozliczenie sumaryczne

Rozliczenia to księgowania dotyczące zamknięcia magazynu, które dostosowują wartość rozchodów do właściwej średniej ważonej na dzień zamknięcia. 

**Uwaga:** Aby uzyskać więcej informacji o rozliczeniach, zobacz artykuł o zamknięciu zapasów. Poniższe przykłady ilustrują skutek zastosowania metody średniej ważonej w pięciu konfiguracjach:

-   Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji **Włącz wartość fizyczną**
-   Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji **Włącz wartość fizyczną**
-   Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień z opcją **Włącz wartość fizyczną**
-   Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień z opcją **Włącz wartość fizyczną**
-   Średnia ważona na dzień z przypisaniem

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną
Zasada bezpośredniego rozliczenia stosowana w tej wersji jest tą samą zasadą, która jest stosowana dla średniej ważonej w poprzednich wersjach. System rozliczy rozchody i przychody bezpośrednio. System wykorzystuje tę zasadę bezpośredniego rozliczania w określonych sytuacjach:

-   w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
-   w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

W poniższym scenariuszu zostały zaksięgowane finansowo zaktualizowane przychód i rozchód. Podczas zamknięcia zapasów system rozlicza przyjęcie bezpośrednio względem wydania i nie będzie konieczna żadna korekta kosztu własnego przy wydaniu towarów. 

Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy zaktualizowany dla ilości 5 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 5 i po koszcie 10,00 USD.
-   2a. Fizyczny rozchód magazynowy zaktualizowany dla ilości 2 i po koszcie 10,00 USD.
-   2b. Finansowy rozchód magazynowy zaktualizowany dla ilości 2 i po koszcie 10,00 USD.
-   3. Zamknięcie magazynu zostało wykonane z zastosowaniem metody rozliczenia bezpośredniego, aby rozliczyć finansowy przychód magazynowy względem finansowego rozchodu magazynowego.

![Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) 

**Objaśnienie ilustracji:**

-   Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
-   Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
-   Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
-   Nad lub pod każdą strzałką pionową jest podana wartość transakcji magazynowej w formacie *Ilość*@*Cena jednostkowa*.
-   Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
-   Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
-   Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
-   Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
-   Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
-   Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną
Średnia ważona jest oparta na zasadzie, że wszystkie przyjęcia w okresie zamknięcia są sumowane do nowej transakcji przeniesienia zapasów. Ta transakcja jest znana jako*średnia ważona zamknięcia magazynu*. Wszystkie przychody dla danego dnia będą rozliczone z rozchodami nowo utworzonej transakcji transferu magazynowego. Wszystkie rozchody dla danego dnia będą rozliczone z przychodem nowej transakcji transferu magazynowego. Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest dodatnia, poszczególne pozycje zapasów i ich wartość są zestawiane w ramach nowej transakcji przeniesienia magazynowego (przychód). Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest ujemna, wartość zapasów jest sumą poszczególnych rozchodów, które nie zostały w pełni rozliczone. 

W poniższym scenariuszu w okresie zamknięcia zostały zaksięgowane finansowo zaktualizowane przychód i rozchód. Podczas zamknięcia zapasów system ocenia poszczególne dni w celu określenia sposobu potraktowania każdego dnia na zamknięciu. 

Na ilustracji przedstawiono następujące transakcje: 

**Dzień 1:**

-   1a. Fizyczny przychód magazynowy zaktualizowany dla ilości 3 i po koszcie 15,00 USD.
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 3 i po koszcie 15,00 USD.
-   2a. Fizyczny rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.
-   2b. Finansowy rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.

W pierwszym dniu system zastosuje metodę rozliczenia bezpośredniego. 

**Dzień 2:**

-   3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.
-   3b. finansowy rozchód z magazynu — ilość 1, bieżący koszt średni 15.00 zł

W drugim dniu system zastosuje metodę rozliczenia bezpośredniego. 

**Dzień 3:**

-   4a. Fizyczny rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.
-   4b. finansowy rozchód z magazynu — ilość 1, bieżący koszt średni 15.00 zł
-   5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 17,00 USD.
-   5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 17,00 USD.

Wykonywane jest zamknięcie magazynu. Musi zostać zastosowana metoda rozliczenia bezpośredniego, ponieważ wystąpiło wiele przyjęć obejmujących wiele dni.

-   7a. W ramach opartej na średniej ważonej transakcji zamknięcia magazynu tworzony jest finansowy rozchód magazynowy w ilości 2 i po koszcie 32,00 USD w celu zsumowania rozliczeń wszystkich otwartych finansowych przychodów magazynowych mających miejsce do danego dnia.
-   7b. W ramach opartej na średniej ważonej transakcji zamknięcia magazynu tworzony jest finansowy przychód magazynowy w ilości 2 w celu skompensowania pozycji 7a.

System generuje i księguje sumaryczną transakcję przeniesienia zapasów. Ponadto system rozlicza wszystkie przyjęcia w danym dniu i dostępne zapasy z poprzednich dni względem sumarycznej transakcji wydania przeniesionych zapasów. Wszystkie rozchody w danym dniu zostaną rozliczone względem sumarycznej transakcji przyjęcia do magazynu. Średni ważony koszt własny zostanie obliczony na poziomie 16,00 USD. Rozchód zostanie skorygowany o 1,00 USD, aby równał się kosztowi średniemu ważonemu. Nowy średni ruchomy koszt własny wyniesie 16,00. 

Na poniższym schemacie przedstawiono powyższe transakcje oraz efekt zastosowania w ich przypadku modelu magazynu opartego na średniej ważonej i zasady rozliczenia sumarycznego bez opcji **Włącz wartość fizyczną**. 

![Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Objaśnienie ilustracji**

-   Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
-   Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
-   Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
-   Nad lub pod każdą strzałką pionową jest podana wartość transakcji magazynowej w formacie *Ilość*@*Cena jednostkowa*.
-   Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
-   Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
-   Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
-   Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
-   Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
-   Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.
-   Czerwone linie zakończone strzałkami przedstawiają transakcje dotyczące przychodu rozliczane względem utworzonych przez system transakcji dotyczących rozchodu.
-   Biegnąca ukośnie zielona linia zakończona strzałkami przedstawia wygenerowaną przez system kompensującą transakcję dotyczącą przychodu, względem której została rozliczona pierwotnie zaksięgowana transakcja dotycząca rozchodu.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień z opcją Włącz wartość fizyczną
Zasada bezpośredniego rozliczenia stosowana w tej wersji jest tą samą zasadą, która jest stosowana dla średniej ważonej na dzień w poprzednich wersjach. System rozliczy rozchody i przychody bezpośrednio. System wykorzystuje tę zasadę bezpośredniego rozliczania w określonych sytuacjach:

-   w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
-   w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupa modeli pozycji**, system użyje fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej ruchomej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. W okresie zamknięcia magazynu finansowo zaktualizowane przychody będą uwzględniane wyłącznie w przypadku obliczania średniej ważonej.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień z opcją Włącz wartość fizyczną
Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupa modeli pozycji**, system użyje fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej ruchomej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. W okresie zamknięcia magazynu finansowo zaktualizowane przychody będą uwzględniane wyłącznie w przypadku obliczania średniej ważonej. Bezpośrednie rozliczenie średniej ważonej opiera się na zasadzie, że wszystkie przychody w ramach okresu zamknięcia są sumowane do nowej transakcji transferu magazynowego, zwanej *średnią ważoną zamknięcia magazynu*. Wszystkie przychody dla danego dnia będą rozliczone z rozchodami nowo utworzonej transakcji transferu magazynowego. Wszystkie rozchody dla danego dnia będą rozliczone z przychodem nowej transakcji transferu magazynowego. Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest dodatnia, poszczególne pozycje zapasów i ich wartość są zestawiane w ramach nowej transakcji przeniesienia magazynowego (przychód). Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest ujemna, wartość zapasów jest sumą poszczególnych rozchodów, które nie zostały w pełni rozliczone.

## <a name="weighted-average-date-when-marking-is-used"></a>Średnia ważona na dzień z przypisaniem
Oznaczanie to proces, który pozwala połączyć transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. 

Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Zamówienie jest pilne, trzeba będzie zatem zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Należy się więc upewnić, że koszt towaru zostanie uwzględniony przy obliczaniu marży (lub w koszcie sprzedanych towarów) w przypadku realizacji danego zamówienia sprzedaży. Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Dokument zamówienia sprzedaży jest oznaczony do zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury. KWS wyniesie 120,00 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie. Jeśli transakcja dotycząca przychodu jest oznaczona do transakcji dotyczącej rozchodu, metoda wyceny określona w grupie modeli towaru, do której należy dana pozycja, zostanie pominięta. Zamiast tego system dokona wzajemnego rozliczenia tych transakcji. 

Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Można to zrobić z wiersza zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**. Można zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów. Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie własnym 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie własnym 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie własnym 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie własnym 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie własnym 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie własnym 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie własnym 30,00 USD.
-   5a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 21,25 USD (średnia ruchoma zaktualizowanych finansowo i fizycznie transakcji).
-   5b. Finansowy rozchód magazynowy w ilości 1 zostaje przypisany do przychodu magazynowego z pozycji 2b przed zaksięgowaniem transakcji. Transakcja ta jest księgowana po koszcie własnym w wysokości 20,00 USD.
-   6a. Fizyczny rozchód magazynowy w ilości 1 i po koszcie własnym 21,25 USD.
-   7. Wykonywane jest zamknięcie magazynu. Finansowo zaktualizowana transakcja została przypisana do istniejącego przychodu magazynowego, obie transakcje są zatem rozliczane względem siebie i nie ma miejsca żadna korekta.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 27,50 USD. Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynu wykorzystującego metodę średniej ważonej na dzień z oznaczeniem.

![średnia ważona na dzień z przypisaniem.](./media/weightedaveragedatewithmarking.gif) 

**Objaśnienie ilustracji:**

-   Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
-   Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
-   Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
-   Nad lub pod każdą strzałką pionową jest podana wartość transakcji magazynowej w formacie *Ilość*@*Cena jednostkowa*.
-   Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
-   Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
-   Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
-   Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
-   Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
-   Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.




