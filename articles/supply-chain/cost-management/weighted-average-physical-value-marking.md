---
title: Średnia ważona z wartością fizyczną i oznaczeniami
description: Średnia ważona jest modelem magazynowym opierającym się na zasadzie średniej ważonej, gdzie rozchody magazynowe są szacowane na podstawie średniej wartości towarów przyjętych do magazynu podczas okresu zamykania magazynu plus dostępnych zapasów z poprzedniego okresu.
author: AndersGirke
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d94e61384ad2d0880a6d62b963e9a99518a41db1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572008"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Średnia ważona z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]

Średnia ważona jest modelem magazynowym opierającym się na zasadzie średniej ważonej, gdzie rozchody magazynowe są szacowane na podstawie średniej wartości towarów przyjętych do magazynu podczas okresu zamykania magazynu plus dostępnych zapasów z poprzedniego okresu.

Podczas operacji zamknięcia magazynu wszystkie przyjęcia są rozliczane względem wydania wirtualnego, w którym jest zapisana cała przyjęta ilość i wartość. Wydaniu wirtualnemu odpowiada przyjęcie wirtualne, z którym wydania są rozliczane. W ten sposób wszystkie wydania mają ten sam średni koszt. Połączenie wirtualnego wydania i przyjęcia można traktować jak wirtualne przesunięcie, które jest nazywane „średnim ważonym zamykającym przesunięciem w magazynie”.

Jeśli istnieje tylko jedno przyjęcie, można nim rozliczyć wszystkie wydania. W takim przypadku nie będą tworzone wirtualne przesunięcia. 

Stosując metodę średniej ważonej, można znaczyć transakcje magazynowych. Dzięki temu określone przyjęcia towarów będą rozliczane konkretnymi wydaniami, a nie według zasady średniej ważonej. 

W przypadku stosowania modelu magazynu z zasadą średniej ważonej zaleca się zamykanie magazynu co miesiąc. 

W metodzie wyceny zapasów na podstawie średniej ważonej obliczenie odbywa się zgodnie z poniższym wzorem:
-   Średnia ważona = (I1\*C1 + I2\*C2 + In\*Cn) / (I1 + I2 + In)

Transakcje magazynowe powodujące wydania z zapasów, takie jak transakcje wynikające z zamówień sprzedaży, arkuszy magazynowych i zleceń produkcyjnych, są realizowane według szacowanego kosztu własnego na dzień księgowania. Ten szacowany koszt własny jest również określany mianem średnia bieżąca. W momencie zamykania zapasów system przeanalizuje transakcje magazynowe dla poprzedniego i bieżącego okresu i określi, która z poniższych zasad zamykania powinna być zastosowana.
-   Rozliczenie bezpośrednie
-   Rozliczenie sumaryczne

Rozliczenia to księgowania dotyczące zamknięcia magazynu, które dostosowują wartość rozchodów do właściwej średniej ważonej na dzień zamknięcia. Poniższy przykład przedstawia skutek zastosowania metody średniej ważonej w pięciu różnych konfiguracjach:
-   Bezpośrednie rozliczenie średniej ważonej bez opcji Włącz wartość fizyczną
-   Sumaryczne rozliczenie średniej ważonej bez opcji Włącz wartość fizyczną
-   Bezpośrednie rozliczenie średniej ważonej z opcją Włącz wartość fizyczną
-   Sumaryczne rozliczenie średniej ważonej z opcją Włącz wartość fizyczną
-   Średnia ważona z oznaczeniem

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Bezpośrednie rozliczenie średniej ważonej bez opcji Włącz wartość fizyczną
Zasada bezpośredniego rozliczenia jest tą samą zasadą, która jest stosowana dla średniej ważonej w starszych wersjach. System rozliczy rozchody i przychody bezpośrednio. System wykorzystuje tę zasadę bezpośredniego rozliczania w określonych specyficznych sytuacjach:
-   w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
-   w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

W poniższym scenariuszu zostały zaksięgowane finansowo zaktualizowane przychód i rozchód. W okresie zamknięcia system rozliczy przyjęcie bezpośrednio względem wydania i nie będzie konieczna żadna korekta kosztu własnego wydanych towarów. Na poniższym schemacie przedstawiono następujące transakcje.
-   1a. Fizyczny przychód magazynowy zaktualizowany dla ilości 5 o wartości 10,00 USD za sztukę
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 5 o wartości 10,00 PLN za sztukę
-   2a. Fizyczny rozchód magazynowy zaktualizowany dla ilości 2 o wartości 10,00 PLN za sztukę
-   2b. Finansowy rozchód magazynowy zaktualizowany dla ilości 2 o wartości 10,00 PLN za sztukę
-   3. Zamknięcie magazynu odbywa się z wykorzystaniem metody bezpośredniego rozliczenia w celu rozliczenia finansowego przychodu magazynowego z finansowym rozchodem magazynowym.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady bezpośredniego rozliczania bez opcji Włącz wartość fizyczną. 

![Średnia ważona — rozrachunek bezpośredni bez uwzględniania wartości fizycznej.](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) 

**Objaśnienie wykresu**
- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą Zamknięcie magazynu.
- Rozliczenia, które zostały przeprowadzone do zamknięcia magazynu są przedstawione jako czerwone kropkowane strzałki, biegnące po skosie od przychodu do rozchodu.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Sumaryczne rozliczenie średniej ważonej bez opcji Włącz wartość fizyczną
Średnia ważona opiera się na zasadzie, że wszystkie przyjęcia w granicach okresu zamknięcia są sumowane do nowej transakcji zwanej średnią ważoną zamknięcia zapasów. Wszystkie przychody dla danego okresu będą rozliczone z rozchodami nowo utworzonej transakcji transferu magazynowego. Wszystkie rozchody dla danego okresu będą rozliczone z przychodem nowej transakcji transferu magazynowego. Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest dodatnia, poszczególne pozycje zapasów i ich wartość są zestawiane w ramach nowej transakcji przeniesienia magazynowego (przychód). Jeśli po zamknięciu magazynu wartość dostępnych zapasów jest ujemna, wartość zapasów jest sumą poszczególnych rozchodów, które nie zostały w pełni rozliczone. W poniższym scenariuszu zostało zaksięgowanych kilka finansowo zaktualizowanych przychodów i rozchodów. 

Podczas zamykania zapasów system wygeneruje i zaksięguje sumaryczną transakcję przeniesienia magazynowego i rozliczy wszystkie przyjęcia w okresie względem sumarycznej transakcji wydania przeniesionych zapasów. Wszystkie rozchody zaksięgowane dla danego okresu będą rozliczone z sumaryczną transakcją przychodu transferu magazynowego. Średnia ważona została obliczona jako  15,00 USD. Wydanie zostało pierwotnie zaksięgowane z szacowanym kosztem własnym 14,67 zł. W związku z tym dla wydania zostanie utworzona i zaksięgowana korekta ujemna na 0,33 zł. Z dniem zamknięcia magazynu dostępne zapasy wynoszą 3 sztuki o wartości 45,00 PLN. 

Poniższe transakcje są przedstawione na poniższym rysunku:
-   1a. Fizyczny przychód magazynowy w ilości 2 przy koszcie 11,00 PLN za sztukę.
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 2 przy koszcie 14,00 PLN za sztukę.
-   2a. Fizyczny przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 12,00 PLN za sztukę.
-   2b. Finansowy przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 16,00 PLN za sztukę.
-   3a. Fizyczny rozchód magazynowy zaktualizowany dla ilości 1 przy koszcie własnym 14,67 PLN za sztukę (średnia bieżąca).
-   3b. Finansowy rozchód magazynowy zaktualizowany dla ilości 1 przy koszcie własnym 14,67 PLN za sztukę (średnia bieżąca).
-   4a. Fizyczny przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 14,00 PLN za sztukę.
-   4b. Finansowy przychód magazynowy w ilości 1 przy koszcie 16,00 PLN za sztukę.
-   5. Wykonywane jest zamknięcie magazynu.
-   6a. Finansowy rozchód „transakcja zamknięcia magazynu średniej ważonej” zostaje utworzony w celu zsumowania płatności wszystkich przychodów finansowych magazynu.
-   6b. Finansowy przychód „transakcja zamknięcia magazynu średniej ważonej” zostaje utworzony jako przesunięcie do 5a.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady sumarycznego rozliczania bez opcji Włącz wartość fizyczną. 

![Średnia ważona — rozrachunek sumaryczny bez uwzględniania wartości fizycznej.](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Objaśnienie wykresu**
- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą Zamknięcie magazynu.
- Rozliczenia, które zostały przeprowadzone do zamknięcia magazynu są przedstawione jako czerwone kropkowane strzałki, biegnące po skosie od przychodu do rozchodu.
- Czerwone strzałki oznaczają transakcje przychodu rozliczane z transakcji rozchodu utworzoną przez system.
- Zielona strzałka reprezentuje przesunięcie transakcji przychodu wygenerowanej przez system, z którą rozliczona jest początkowo zaksięgowana transakcja rozchodu.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Bezpośrednie rozliczenie średniej ważonej z opcją Włącz wartość fizyczną
Parametr Włącz wartość fizyczną działa w inny sposób w modelu magazynowym średniej ważonej niż w poprzednich wersjach systemu. W formularzu Grupa modeli pozycji zaznacz dla towaru pole wyboru Włącz wartość fizyczną. Wtedy system będzie używał fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej kroczącej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. Podczas zamykania magazynu finansowo zaktualizowane przychody będą uwzględniane tylko w obliczeniach średniej ważonej. Zaleca się comiesięczne zamykanie magazynu w przypadku stosowania modelu magazynowego średniej ważonej. W tym przykładzie rozliczenie bezpośrednie średniej ważonej jest oznaczone i zawiera wartość fizyczną. 

Na poniższym schemacie przedstawiono następujące transakcje:
-   1a. Fizyczny przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 11,00 PLN za sztukę.
-   1b. Finansowy przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 10,00 PLN za sztukę.
-   2a. Fizyczny przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 15,00 PLN za sztukę.
-   3a. Fizyczny rozchód magazynowy zaktualizowany dla ilości 1 przy koszcie własnym 12,50 PLN za sztukę (średnia bieżąca - koszt, ponieważ fizyczna wartość przychodu jest wzięta pod uwagę).
-   3b. Finansowy rozchód magazynowy zaktualizowany dla ilości 1 przy koszcie własnym 12,50 PLN za sztukę (średnia bieżąca - koszt, ponieważ fizyczna wartość przychodu jest wzięta pod uwagę).
-   4. Wykonywane jest zamknięcie magazynu. Podczas zamknięcia zapasów system zignoruje wszystkie transakcje magazynowe, które były zaktualizowane tylko fizycznie. Zamiast tego zostanie użyta zasada bezpośredniego rozliczenia, ponieważ istnieje tylko jeden finansowy przychód. Korekta o wartości 2,50 PLN zostanie zaksięgowana do transakcji magazynowej, która została finansowo wykonana z datą zamknięcia magazynu. Po zamknięciu magazynu dostępne zapasy będą miały wartość 1 z kosztem własnym średnim ważonym 15,00 PLN.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady bezpośredniego rozliczania z opcją Włącz wartość fizyczną. 

![Średnia ważona — rozrachunek bezpośredni z uwzględnianiem wartości fizycznej.](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) 

**Objaśnienie wykresu**
- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą Zamknięcie magazynu.
- Rozliczenia, które zostały przeprowadzone do zamknięcia magazynu są przedstawione jako czerwone kropkowane strzałki, biegnące po skosie od przychodu do rozchodu.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Sumaryczne rozliczenie średniej ważonej z opcją Włącz wartość fizyczną
Parametr Włącz wartość fizyczną działa w inny sposób dla średniej ważonej niż w starszych wersjach. Zaznacz pole Włącz wartość fizyczną dla towaru na stronie Grupa modeli pozycji. Wtedy system będzie używał fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej kroczącej). Rozchody będą księgowane na podstawie szacowanego kosztu własnego podczas tego okresu. Podczas zamykania magazynu finansowo zaktualizowane przychody będąuwzględniane tylko w obliczeniu średniej ważonej. Zaleca się comiesięczne zamykanie magazynu w przypadku stosowania modelu magazynowego średniej ważonej. W tym przykładzie rozliczenia sumarycznego średniej ważonej model magazynowy jest oznaczony i zawiera wartość fizyczną. 

Poniższe transakcje są przedstawione na poniższym rysunku:
-   1a. Fizyczny przychód magazynowy w ilości 2 przy koszcie 11,00 PLN za sztukę.
-   1b. Finansowy przychód magazynowy w ilości 2 przy koszcie 14,00 PLN za sztukę.
-   2. Fizyczny przychód magazynowy w ilości 1 przy koszcie 10,00 PLN za sztukę.
-   3a. Fizyczny przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 12,00 PLN za sztukę.
-   3b. Finansowy przychód magazynowy zaktualizowany dla ilości 1 przy koszcie 16,00 PLN za sztukę.
-   4a. Fizyczny rozchód magazynowy zaktualizowany dla ilości 1 przy koszcie własnym 13,50 PLN za sztukę (średnia bieżąca - koszt, ponieważ fizyczna wartość przychodu jest wzięta pod uwagę).
-   4b. Finansowy rozchód magazynowy zaktualizowany dla ilości 1 przy koszcie własnym 13,50 PLN za sztukę (średnia bieżąca - koszt, ponieważ fizyczna wartość przychodu jest wzięta pod uwagę).
-   5a. Fizyczny przychód magazynowy w ilości 1 przy koszcie 14,00 PLN za sztukę.
-   5b. Finansowy przychód magazynowy w ilości 1 przy koszcie 16,00 PLN za sztukę.
-   6. Wykonywane jest zamknięcie magazynu. Podczas zamknięcia zapasów system pominie wszystkie transakcje magazynowe, które są zaktualizowane tylko fizycznie. Zostanie użyta zasada sumarycznego rozliczenia, ponieważ istnieje tylko jeden finansowy przychód. Korekta o wartości 1,50 PLN zostanie zaksięgowana do transakcji magazynowej, która została finansowo wykonana z datą zamknięcia magazynu. Po zamknięciu magazynu dostępne zapasy będą miały wartość 3 z kosztem własnym średnim ważonym 15,00 USD.
-   7a. Finansowy rozchód „transakcja zamknięcia magazynu średniej ważonej” zostaje utworzony w celu zsumowania płatności wszystkich przychodów finansowych magazynu.
-   7b. Finansowy przychód “transakcja zamknięcia magazynu średniej ważonej” zostaje utworzony jako przesunięcie do 5a.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady sumarycznego rozliczania bez opcji Włącz wartość fizyczną. 

![Średnia ważona — rozrachunek sumaryczny z uwzględnianiem wartości fizycznej.](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) 

**Objaśnienie wykresu**
- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@cena jednostkowa.
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład 1a. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą Zamknięcie magazynu.
- Rozliczenia, które zostały przeprowadzone do zamknięcia magazynu są przedstawione jako czerwone kropkowane strzałki, biegnące po skosie od przychodu do rozchodu.
- Czerwone strzałki oznaczają transakcje przychodu rozliczane z transakcji rozchodu utworzoną przez system.
- Zielona strzałka reprezentuje przesunięcie transakcji przychodu wygenerowanej przez system, z którym rozliczona jest początkowo zaksięgowana transakcja rozchodu.

## <a name="weighted-average-with-marking"></a>Średnia ważona z oznaczeniem
Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu. 

Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Zamówienie jest pilne, trzeba będzie zatem zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Należy się więc upewnić, że koszt towaru zostanie uwzględniony przy obliczaniu marży (lub w koszcie sprzedanych towarów) w przypadku realizacji danego zamówienia sprzedaży. 

Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Na przykład dokument zamówienia sprzedaży jest oznaczony do zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury. KWS wyniesie 120,00 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. 

Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie. 

Transakcja przyjęcia jest oznaczona dla transakcji wydania. Wtedy metoda wyceny wybrana w grupie modeli towarów dla danego towaru jest pomijana, a transakcje są rozliczane względem siebie. 

Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Można to zrobić z wiersza zamówienia sprzedaży na stronie Szczegóły zamówienia sprzedaży. Można wyświetlić otwarte transakcje przychodu na stronie Zaznaczanie. 

Można zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów. 

Na poniższym schemacie przedstawiono następujące transakcje:
-   1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
-   2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
-   3a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
-   4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   4b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
-   5a. Fizyczny rozchód magazynowy w ilości 1 przy koszcie własnym 21,25 PLN (średnia bieżąca finansowo i fizycznie zaktualizowanych transakcji).
-   5b. Finansowy rozchód magazynowy w ilości 1 jest oznaczony do przychodu magazynowego 2b przed zaksięgowaniem transakcji. Transakcja jest zaksięgowana z kosztem własnym 20,00 PLN.
-   6a. Fizyczny rozchód magazynowy w ilości 1 przy koszcie własnym  21,25 PLN za sztukę.
-   7. Następuje zamknięcie magazynu. W związku z tym, że finansowo zaktualizowana transakcja jest oznaczona do istniejącego przychodu, transakcje te są ze sobą rozliczane i nie ma żadnej korekty.

Nowa średnia ruchoma kosztów własnych odzwierciedla średnią wynikającą z fizycznie i finansowo zaktualizowanych transakcji na poziomie 27,50 USD. 

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej z oznaczeniem. 

![Średnia ważona z oznaczaniem.](./media/weightedaveragewithmarking.gif) 

**Objaśnienie wykresu**
- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Nad (lub pod) każdą strzałką pionową została podana wartość transakcji magazynowej w formacie ilość@"cena jednostkowa".
- Jeśli wartość transakcji magazynowej została podana w nawiasie, transakcja taka została zaksięgowana fizycznie w magazynie.
- Jeśli wartość transakcji magazynowej nie została podana w nawiasie, transakcja taka została zaksięgowana finansowo w magazynie.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej z etykietą Zamknięcie magazynu.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci czerwonych linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]