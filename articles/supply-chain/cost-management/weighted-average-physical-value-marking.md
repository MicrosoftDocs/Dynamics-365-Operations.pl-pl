---
title: Średnia ważona z wartością fizyczną i oznaczeniami
description: Średnia ważona jest modelem magazynowym opierającym się na zasadzie średniej ważonej, gdzie rozchody magazynowe są szacowane na podstawie średniej wartości towarów przyjętych do magazynu podczas okresu zamykania magazynu plus dostępnych zapasów z poprzedniego okresu.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c80dcdc08432bb68478827c8763735e644aa4a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675299"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Średnia ważona z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]

Średnia ważona jest modelem magazynu opartym na średniej, która wynika z mnożenia każdego składnika (transakcji towaru) przez współczynnik (koszt własny) odzwierciedlający jego ważność (ilość). Innym sposobem jest to, że średnia ważona to model magazynu, który przypisuje koszt transakcji wydania na podstawie średniej wartości wszystkich zapasów otrzymanych w okresie plus dostępnych zapasów z poprzedniego okresu.

Gdy zamykanie magazynu jest uruchamiane przy użyciu modelu magazynu średniej ważonej, można utworzyć rozliczenie na dwa sposoby. Zazwyczaj wszystkie wpływy są rozliczane z rozchodem wirtualnym, który zawiera całkowitą otrzymaną ilość i wartość. Wydaniu wirtualnemu odpowiada przyjęcie wirtualne, z którym wydania są rozliczane. W ten sposób wszystkie wydania mają ten sam średni koszt. Połączenie wirtualnego wydania i przyjęcia można traktować jak wirtualne przesunięcie, które jest nazywane *„średnim ważonym zamykającym przesunięciem w magazynie”*. Ta metoda rozliczania jest nazywana rozliczeniem *sumowania średniej ważonej*. Jeśli istnieje tylko jedno przyjęcie, można nim rozliczyć wszystkie wydania. W takim przypadku nie będą tworzone wirtualne przesunięcia. Ta metoda rozliczania jest określana jako rozliczenie *bezpośrednie*. Każdy zapas dostępny po zamknięciu magazynu jest wyceniany przy średniej ważonej z poprzedniego okresu i uwzględniany w obliczaniu średniej ważonej w następnym okresie.

Można zastąpić zasadę średniej ważonej, oznaczając transakcje magazynowe, tak aby przychód określonego towaru był rozliczany z określonym rozchodem. Okresowe zamknięcie zapasów jest wymagane, gdy model zapasów ze średnią ważoną jest używany do tworzenia rozliczeń i korygowania wartości rozchodów zgodnie z zasadą średniej ważonej. Dopóki nie przeprowadzisz procesu zamknięcia inwentarza, transakcje wydania są wyceniane według średniej bieżącej z momentu aktualizacji fizycznej i finansowej. Jeśli nie używasz znakowania, średnia krocząca jest obliczana w momencie przeprowadzania fizycznej lub finansowej aktualizacji.

W metodzie wyceny zapasów na podstawie średniej ważonej obliczenie odbywa się zgodnie z poniższym wzorem:

- Średnia ważona = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = Ilość transakcji  
P = cena transakcji

Rozliczenia to księgowania dotyczące zamknięcia magazynu, które dostosowują wartość rozchodów do właściwej średniej ważonej na dzień zamknięcia. Poniższy przykład przedstawia skutek zastosowania metody średniej ważonej w pięciu różnych konfiguracjach:

- Bezpośrednie rozliczenie średniej ważonej bez opcji **Włącz wartość fizyczną**
- Sumaryczne rozliczenie średniej ważonej bez opcji **Włącz wartość fizyczną**
- Bezpośrednie rozliczenie średniej ważonej z opcją **Włącz wartość fizyczną**
- Sumaryczne rozliczenie średniej ważonej z opcją **Włącz wartość fizyczną**
- Średnia ważona z oznaczeniem

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Bezpośrednie rozliczenie średniej ważonej bez opcji Włącz wartość fizyczną

Zasada bezpośredniego rozliczania tworzy rozliczenia bezpośrednio między przychodami i rozliczeniami bez tworzenia dodatkowych transakcji magazynowych. System wykorzystuje tę zasadę bezpośredniego rozliczania w następujących sytuacjach:

- w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
- w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

W tym przykładzie pole wyboru **Uwzględnij wartość fizyczną** jest wyczyszczony w grupie modeli **pozycji dla zwolnionego produktu**. Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 20,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 4a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 4b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 5a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 6\. Wykonywane jest zamknięcie magazynu. W oparciu o metodę średniej ważonej system stosuje metodę rozliczenia bezpośredniego, ponieważ tylko jeden przykwitowanie został finansowo zaktualizowany w tym okresie. W tym przykładzie jedna osada jest tworzona między 1b a 3b, a druga między 1b i 4b. Nie zostanie dokonana korekta, ponieważ średnia bieżąca jest taka sama jak średnia ważona.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady bezpośredniego rozliczania bez opcji **Włącz wartość fizyczną**.

![Średnia ważona — rozrachunek bezpośredni bez uwzględniania wartości fizycznej.](media/weighted-average-direct-settlement-without-include-physical-value.png)

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

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Sumaryczne rozliczenie średniej ważonej bez opcji Włącz wartość fizyczną

Gdy w okresie występuje wiele wpływów, średnia ważona wykorzystuje zasadę rozliczenia sumarycznego, w której wszystkie wpływy w okresie zamknięcia są sumowane w transakcji o nazwie *średnie ważone zamknięcie zapasów*. Wszystkie przychody dla danego okresu będą rozliczone z rozchodami nowo utworzonej transakcji magazynowej. Wszystkie rozchody dla danego okresu będą rozliczone z przychodem nowej transakcji magazynowej. Jeśli po zamknięciu magazynu pozostała wartość dostępnych zapasów, wartość dostępnych zapasów jest uwzględniana w transakcji przychodu transakcji zamknięcia magazynu średniej ważonej.

Poniższe transakcje są przedstawione na poniższym rysunku:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 7\. Wykonywane jest zamknięcie magazynu.
- 7a. Finansowy rozchód transakcja zamknięcia magazynu średniej ważonej zostaje utworzony w celu zsumowania płatności wszystkich przychodów finansowych magazynu.
  - Transakcja 1b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 10,00.
  - Transakcja 2b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 22.00.
  - Transakcja 5b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 30,00.
  - Transakcja 7a. tworzony jest dla ilości 3 z rozliczeniem 62,00 USD. Transakcja jest przeciwstawna do sumy trzech transakcji przychodów, które zostały finansowo zaktualizowane w tym okresie.
- 7b. Średni ważony finansowy przychód zamknięcia magazynu jest tworzony jako kompensacja finansowo zaksięgowanych rozchodów.
  - Transakcja 3b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 20,67. Ta transakcja jest korygowana przez USD 4.67, aby wartość oryginalna USD 16.00 do 20,67 była średnią ważoną finansowo zaksięgowanych transakcji w okresie.
  - Transakcja 7b. jest tworzony dla ilości 1 z kwotą rozliczoną 20,67 USD w celu skompensowania 3b. Ta transakcja kompensuje sumę jednej transakcji wydania, która jest aktualizowana finansowo w danym okresie.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady sumarycznego rozliczania bez opcji **Włącz wartość fizyczną**.

![Średnia ważona — rozrachunek sumaryczny bez uwzględniania wartości fizycznej.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

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

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Bezpośrednie rozliczenie średniej ważonej z opcją Włącz wartość fizyczną

Parametr **Włącz wartość fizyczną** działa w inny sposób w modelu magazynowym średniej ważonej niż w poprzednich wersjach systemu. Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru w formularzu **Grupa modeli pozycji**, system użyje fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej ruchomej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. Podczas zamykania magazynu finansowo zaktualizowane przychody będą uwzględniane tylko w obliczeniach średniej ważonej.

Poniższe transakcje są przedstawione na poniższym rysunku:

- 1a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 20,00 USD.
- 3a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 3b. Wydanie finansowe zapasów dla ilości 1 szt. w cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 4a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 4b. Wydanie finansowe zapasów dla ilości 1 szt. w cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 5a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 6\. Wykonywane jest zamknięcie magazynu. W oparciu o metodę średniej ważonej system stosuje metodę rozliczenia bezpośredniego, ponieważ tylko jeden przykwitowanie został finansowo zaktualizowany w tym okresie. W tym przykładzie jedna osada jest tworzona między 1b a 3b, a druga między 1b i 4b. Każda transakcja 3b i 4b jest korygowana o -5,00 USD, aby uzyskać wartość 10,00 USD.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady bezpośredniego rozliczania z opcją **Włącz wartość fizyczną**.

![Średnia ważona — rozrachunek bezpośredni z uwzględnianiem wartości fizycznej.](media/weighted-average-direct-settlement-with-include-physical-value.png)

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

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Sumaryczne rozliczenie średniej ważonej z opcją Włącz wartość fizyczną

Parametr **Włącz wartość fizyczną** działa w inny sposób dla średniej ważonej niż w starszych wersjach. Zaznacz pole **Włącz wartość fizyczną** dla towaru na stronie **Grupa modeli pozycji**. Wtedy system będzie używał fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej kroczącej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. Podczas zamykania magazynu finansowo zaktualizowane przychody będą uwzględniane tylko w obliczeniach średniej ważonej. Zaleca się comiesięczne zamykanie magazynu w przypadku stosowania modelu magazynowego średniej ważonej. W tym przykładzie rozliczenia sumarycznego średniej ważonej model magazynowy jest oznaczony i zawiera wartość fizyczną.

Poniższe transakcje są przedstawione na poniższym rysunku:

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
- 7\. Wykonywane jest zamknięcie magazynu.
- 7a. Finansowy rozchód transakcja zamknięcia magazynu średniej ważonej zostaje utworzony w celu zsumowania płatności wszystkich przychodów finansowych magazynu.
  - Transakcja 1b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 10,00.
  - Transakcja 2b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 22.00.
  - Transakcja 5b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 30,00.
  - Transakcja 7a. tworzony jest dla ilości 3 z rozliczeniem 62,00 USD.  
- 7b. Średni ważony finansowy przychód zamknięcia zapasów jest tworzony jako kompensacja finansowo zamkniętych transakcji rozchodu.
  - Transakcja 3b jest rozliczana dla ilości 1 z kwotą rozliczonych USD 20,67. Ta transakcja jest korygowana przez USD 4.67, aby wartość oryginalna USD 16.00 do 20,67 była średnią ważoną finansowo zaksięgowanych transakcji w okresie.
  - Transakcja 7b. jest tworzony dla ilości 1 z kwotą rozliczoną 20,67 USD w celu skompensowania 3b.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej i zasady sumarycznego rozliczania bez opcji **Włącz wartość fizyczną**.

![Średnia ważona — rozrachunek sumaryczny z uwzględnianiem wartości fizycznej.](media/weighted-average-summarized-settlement-with-include-physical-value.png)

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

## <a name="weighted-average-with-marking"></a>Średnia ważona z oznaczeniem

Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu.

Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Zamówienie jest pilne, trzeba będzie zatem zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Należy się więc upewnić, że koszt towaru zostanie uwzględniony przy obliczaniu marży (lub w koszcie sprzedanych towarów) w przypadku realizacji danego zamówienia sprzedaży.

Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Na przykład dokument zamówienia sprzedaży jest oznaczony do zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury. KWS wyniesie 120,00 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych.

Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie.

Transakcja przyjęcia jest oznaczona dla transakcji wydania. Wtedy metoda wyceny wybrana w grupie modeli towarów dla danego towaru jest pomijana, a transakcje są rozliczane względem siebie.

Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Można to zrobić z wiersza zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**.

Można zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów.

Poniższe transakcje są przedstawione na poniższym rysunku:

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
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o zasadę znakowania wykorzystującą metodę średniej ważonej, oznaczone transakcje są rozliczane względem siebie. W tym przykładzie, 3b jest rozliczane z 2b, a korekta o 6,00 USD jest księgowana na 3b, aby wartość wynosiła 22,00 USD. W tym przykładzie nie są dokonywane żadne dodatkowe rozliczenia, ponieważ zamknięcie tworzy rozliczenia tylko dla transakcji zaktualizowanych finansowo.

Poniższy wykres obrazuje tę serię transakcji ze skutkami zastosowania modelu magazynowego średniej ważonej z oznaczeniem.

![Średnia ważona z oznaczaniem.](media/weighted-average-with-marking.png)

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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
