---
title: "Średnia ważona z datą"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 2016-01-07 19 - 58 - 01
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d05059f1b1da12ec27bd83d43275c82ac6130590
ms.lasthandoff: 03/29/2017


---

# <a name="weighted-average-date"></a>Średnia ważona z datą



Średnia ważona z datą to model zapasów oparty na zasadzie średniej ważonej. W tej metodzie wydania z zapasów są wyceniane na podstawie średniej wartości towarów przyjętych do zapasów w każdym dniu w okresie zamknięcia zapasów. Podczas zamknięcia zapasów przy użyciu średniej ważonej z datą wszystkie dzienne przyjęcia są rozliczane względem wirtualnego wydania. To wirtualne wydanie zawiera łączną przyjętą ilość i wartość w danym dniu. Dla wirtualnego rozchodu istnieje odpowiadający mu wirtualny przychód, z którego zostanie rozliczony. W ten sposób wszystkie wydania mają ten sam średni koszt. Wirtualny rozchód i przychód mogą być postrzegane jako wirtualne przeniesienie na podstawie *średniej ważonej zamknięcia magazynu*. Jeśli do tego dnia miało miejsce tylko jedno przyjęcie, nie trzeba obliczać średniej. Ponieważ wszystkie wydania są rozliczane względem tego przyjęcia, nie zostanie utworzone wirtualne przeniesienie. Podobnie, jeśli nastąpił tylko rozchód, nie ma przychodów do obliczania średniej i wirtualne przeniesienie nie zostanie utworzone. W przypadku używania średniej ważonej z datą można oznaczać transakcje magazynowe, tak aby określone przyjęcia towarów były rozliczone względem określonych wydań. W takim przypadku nie używaj reguły średniej ważonej z datą. W przypadku używania modelu magazynowego średniej ważonej z datą zaleca się comiesięczne zamykanie magazynu. Poniższa formuła służy do obliczania Data średnia ważona metoda wyceny: średnia ważona = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q*n* × P*n*\]) ÷ (Q1 + Q2 + Q*n*) podczas zamknięcia magazynu obliczenie jest wykonywane codziennie przez okres zamknięcia, jak pokazano na poniższej ilustracji. ![Model codziennego obliczania średniej ważonej z datą](./media/weightedaveragedatedailycalculationmodel.gif) Transakcje magazynowe powodujące wydania z zapasów, takie jak transakcje wynikające z zamówień sprzedaży, arkuszy magazynowych i zleceń produkcyjnych, są realizowane według szacowanego kosztu własnego na dzień księgowania. Ten szacowany koszt własny jest również określany mianem średniej kroczącej kosztu własnego. W dniu zamknięcia magazynu system analizuje transakcji magazynowych dla poprzednich okresów, dni poprzedniego i bieżącego dnia. Ta analiza służy określaniu, która z poniższych zasad zamknięcia ma zostać użyta:

-   Rozliczenie bezpośrednie
-   Rozliczenie sumaryczne

Rozliczenia to księgowania dotyczące zamknięcia magazynu, które dostosowują wartość rozchodów do właściwej średniej ważonej na dzień zamknięcia. **Uwaga:** uzyskać więcej informacji na temat rozliczeń, zobacz artykuł o zapasów Zamknij. Poniższe przykłady ilustrują skutek zastosowania metody średniej ważonej w pięciu konfiguracjach:

-   Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji **Włącz wartość fizyczną**
-   Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji **Włącz wartość fizyczną**
-   Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień z opcją **Włącz wartość fizyczną**
-   Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień z opcją **Włącz wartość fizyczną**
-   Średnia ważona na dzień z przypisaniem

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną
Bieżąca wersja używa tej samej zasadzie rozliczenia bezpośredni, który został użyty do średniej ważonej we wcześniejszych wersjach. System rozliczy rozchody i przychody bezpośrednio. System używa tej zasady bezpośredniego rozstrzygnięcia w określonych sytuacjach:

-   w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
-   w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

W poniższym scenariuszu zostały zaksięgowane finansowo zaktualizowane przychód i rozchód. Podczas zamknięcia magazynu system rozlicza przychód bezpośrednio względem problemu, a nie na koszt własny jest konieczne dostosowanie w kwestii. Na ilustracji przedstawiono następujące transakcje:

-   1a. Fizyczny przychód magazynowy zaktualizowany dla ilości 5 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 5 i po koszcie 10,00 USD.
-   2a. Fizyczny rozchód magazynowy zaktualizowany dla ilości 2 i po koszcie 10,00 USD.
-   2b. Finansowy rozchód magazynowy zaktualizowany dla ilości 2 i po koszcie 10,00 USD.
-   3. Zamknięcie magazynu zostało wykonane z zastosowaniem metody rozliczenia bezpośredniego, aby rozliczyć finansowy przychód magazynowy względem finansowego rozchodu magazynowego.

![Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) **Klucz do ilustracji:**

-   Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
-   Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
-   Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
-   Powyżej lub poniżej każdej pionowej strzałki określono wartość transakcji magazynowych w formie *ilość*@*ceny jednostkowej*.
-   Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
-   Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
-   Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
-   Each vertical arrow is labeled with a sequential identifier, such as *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
-   Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
-   Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną
Średnia ważona jest oparta na zasadzie, że wszystkie przychody w okresie zamknięcia są podsumowane w nowej transakcji przesunięcia zapasów. Ta transakcja jest znana jako*średnia ważona zamknięcia magazynu*. Wszystkie przychody dla danego dnia będą rozliczone z rozchodami nowo utworzonej transakcji transferu magazynowego. Wszystkie rozchody dla danego dnia będą rozliczone z przychodem nowej transakcji transferu magazynowego. Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest dodatnia, poszczególne pozycje zapasów i ich wartość są zestawiane w ramach nowej transakcji przeniesienia magazynowego (przychód). Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest ujemna, wartość zapasów jest sumą poszczególnych rozchodów, które nie zostały w pełni rozliczone. W poniższym scenariuszu w okresie zamknięcia zostały zaksięgowane finansowo zaktualizowane przychód i rozchód. Podczas zamknięcia magazynu system sprawdza każdego dnia, aby określić, jak każdego dnia powinny być traktowane przez zamknięcie. Na ilustracji przedstawiono następujące transakcje: **Dzień 1:**

-   1a. Fizyczny przychód magazynowy zaktualizowany dla ilości 3 i po koszcie 15,00 USD.
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 3 i po koszcie 15,00 USD.
-   2a. Fizyczny rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.
-   2b. Finansowy rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.

System użyje metodę rozliczenia bezpośredni na dzień 1. **Dzień 2:**

-   3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.
-   3b. finansowy rozchód z magazynu — ilość 1, bieżący koszt średni 15.00 zł

System użyje metodę rozliczenia bezpośredni w dniu 2. **Dzień 3:**

-   4a. Fizyczny rozchód magazynowy w ilości 1 po koszcie średnim ruchomym 15,00 USD.
-   4b. finansowy rozchód z magazynu — ilość 1, bieżący koszt średni 15.00 zł
-   5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 17,00 USD.
-   5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 17,00 USD.

Wykonywane jest zamknięcie magazynu. Musi zostać zastosowana metoda rozliczenia bezpośredniego, ponieważ wystąpiło wiele przyjęć obejmujących wiele dni.

-   7a. W ramach opartej na średniej ważonej transakcji zamknięcia magazynu tworzony jest finansowy rozchód magazynowy w ilości 2 i po koszcie 32,00 USD w celu zsumowania rozliczeń wszystkich otwartych finansowych przychodów magazynowych mających miejsce do danego dnia.
-   7b. W ramach opartej na średniej ważonej transakcji zamknięcia magazynu tworzony jest finansowy przychód magazynowy w ilości 2 w celu skompensowania pozycji 7a.

System generuje i księgowanie transakcji magazynowych podsumowane transferu. Ponadto system rozlicza wszystkie wpływy na dzień i dostępnych zapasów dla poprzednich dni przed transakcji rozchodów magazynowych podsumowane transferu. Wszystkie rozchody w danym dniu zostaną rozliczone względem sumarycznej transakcji przyjęcia do magazynu. Średni ważony koszt własny zostanie obliczony na poziomie 16,00 USD. Rozchód zostanie skorygowany o 1,00 USD, aby równał się kosztowi średniemu ważonemu. Nowy średni ruchomy koszt własny wyniesie 16,00. Na poniższym schemacie przedstawiono powyższe transakcje oraz efekt zastosowania w ich przypadku modelu magazynu opartego na średniej ważonej i zasady rozliczenia sumarycznego bez opcji **Włącz wartość fizyczną**. ![Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) **Klucz do ilustracji:**

-   Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
-   Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
-   Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
-   Powyżej lub poniżej każdej pionowej strzałki określono wartość transakcji magazynowych w formie *ilość*@*ceny jednostkowej*.
-   Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
-   Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
-   Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
-   Each vertical arrow is labeled with a sequential identifier, such as *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
-   Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
-   Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.
-   Czerwone linie zakończone strzałkami przedstawiają transakcje dotyczące przychodu rozliczane względem utworzonych przez system transakcji dotyczących rozchodu.
-   Biegnąca ukośnie zielona linia zakończona strzałkami przedstawia wygenerowaną przez system kompensującą transakcję dotyczącą przychodu, względem której została rozliczona pierwotnie zaksięgowana transakcja dotycząca rozchodu.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień z opcją Włącz wartość fizyczną
Bieżąca wersja używa tej samej zasadzie rozliczenia bezpośredni Data średnia ważona, który jest używany we wcześniejszych wersjach. System rozliczy rozchody i przychody bezpośrednio. System używa tej zasady bezpośredniego rozstrzygnięcia w określonych sytuacjach:

-   w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
-   w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

Jeśli wybierzesz **Włącz wartość fizyczną** pole wyboru dla elementu na **grupy modeli towaru** strony, system używa fizycznie zaktualizowanych potwierdzeń podczas obliczania szacowany koszt własny lub systemem średniej. W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. W okresie zamknięcia magazynu finansowo zaktualizowane przychody będą uwzględniane wyłącznie w przypadku obliczania średniej ważonej.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień z opcją Włącz wartość fizyczną
Jeśli wybierzesz **Włącz wartość fizyczną** pole wyboru dla elementu na **grupy modeli towaru** strony, system używa fizycznie zaktualizowanych potwierdzeń podczas obliczania szacowany koszt własny lub systemem średniej. W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. W okresie zamknięcia magazynu finansowo zaktualizowane przychody będą uwzględniane wyłącznie w przypadku obliczania średniej ważonej. Bezpośrednie rozliczenie średniej ważonej opiera się na zasadzie, że wszystkie przychody w ramach okresu zamknięcia są sumowane do nowej transakcji transferu magazynowego, zwanej *średnią ważoną zamknięcia magazynu*. Wszystkie przychody dla danego dnia będą rozliczone z rozchodami nowo utworzonej transakcji transferu magazynowego. Wszystkie rozchody dla danego dnia będą rozliczone z przychodem nowej transakcji transferu magazynowego. Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest dodatnia, poszczególne pozycje zapasów i ich wartość są zestawiane w ramach nowej transakcji przeniesienia magazynowego (przychód). Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest ujemna, wartość zapasów jest sumą poszczególnych rozchodów, które nie zostały w pełni rozliczone.

## <a name="weighted-average-date-when-marking-is-used"></a>Średnia ważona na dzień z przypisaniem
Oznakowanie to proces, który pozwala powiązać transakcję rozchodu do transakcji przychodu. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Zamówienie jest pilne, trzeba będzie zatem zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Należy się więc upewnić, że koszt towaru zostanie uwzględniony przy obliczaniu marży (lub w koszcie sprzedanych towarów) w przypadku realizacji danego zamówienia sprzedaży. Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Dokument zamówienia sprzedaży jest oznaczony do zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury. KWS wyniesie 120,00 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie. Jeśli transakcja dotycząca przychodu jest oznaczona do transakcji dotyczącej rozchodu, metoda wyceny określona w grupie modeli towaru, do której należy dana pozycja, zostanie pominięta. Zamiast tego system rozlicza te transakcje do siebie nawzajem. Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Można to zrobić z wiersza zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**. Można zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów. Na ilustracji przedstawiono następujące transakcje:

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

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 27,50 USD. Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynu wykorzystującego metodę średniej ważonej na dzień z oznaczeniem. ![Średnia ważona z datą z oznaczaniem](./media/weightedaveragedatewithmarking.gif) **Klucz do ilustracji:**

-   Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
-   Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
-   Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
-   Powyżej lub poniżej każdej pionowej strzałki określono wartość transakcji magazynowych w formie *ilość*@*ceny jednostkowej*.
-   Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
-   Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
-   Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
-   Each vertical arrow is labeled with a sequential identifier, such as *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
-   Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą *Zamknięcie magazynu*.
-   Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.



