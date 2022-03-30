---
title: Średnia ważona data z uwzględnieniem wartości fizycznej i znakowania
description: Średnia ważona z datą jest modelem magazynu opartym na zasadzie średniej ważonej, w którym towary magazynowe są szacowane na podstawie średniej wartości towarów przyjętych na magazyn dla każdego dnia osobno w okresie zamknięcia magazynu.
author: AndersGirke
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cf2206863d891eceb9c65ff879da3f9f72032b1
ms.sourcegitcommit: fcded93fc6c27768a24a3d3dc5cc35e1b4eff22b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392008"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Średnia ważona data z uwzględnieniem wartości fizycznej i znakowania

[!include [banner](../includes/banner.md)]

*Data średniej ważonej* to model inwentaryzacji oparty na średniej obliczanej poprzez pomnożenie każdego składnika (transakcji na pozycji) przez współczynnik (cenę nabycia lub koszt wytworzenia) odzwierciedlający jego znaczenie (ilość) w każdym dniu okresu. Innymi słowy, ten model inwentaryzacji przypisuje koszt transakcji wydania na podstawie średniej wartości wszystkich zapasów otrzymywanych każdego dnia, powiększonej o zapasy znajdujące się na stanie z dnia poprzedniego.

Podczas zamykania inwentaryzacji przy użyciu modelu średniej ważonej daty inwentaryzacji można zastosować dwie metody tworzenia rozliczenia. Zazwyczaj wszystkie wpływy są rozliczane z emisją wirtualną, która zawiera całkowitą ilość i wartość otrzymanych wpływów. Ta wirtualna sprawa ma odpowiadający jej wirtualny paragon, z którego są rozliczane sprawy. W ten sposób wszystkie sprawy mają taki sam średni koszt każdego dnia. Wirtualne wydanie i wirtualne przyjęcie można uznać za wirtualne przeniesienie. To wirtualne przeniesienie jest nazywane zamknięciem *magazynu średniej ważonej*. Dlatego ta metoda określana jest jako *sumowania średniej ważonej*. Jeśli jest tylko jeden paragon, wszystkie sprawy można rozliczać na jego podstawie i nie tworzy się przelewu wirtualnego. Ta metoda rozliczania jest określana jako rozliczenie *bezpośrednie*. Wszelkie zapasy, które są w posiadaniu po zamknięciu inwentaryzacji, są wyceniane według średniej ważonej z ostatniego dnia poprzedniego okresu i uwzględniane w kalkulacji średniej ważonej na następny okres.

Można obejść zasadę średniej ważonej daty, oznaczając transakcje inwentaryzacyjne w taki sposób, aby przyjęcie konkretnej pozycji było rozliczane z konkretnym wydaniem. Okresowe zamknięcie zapasów jest wymagane, gdy model zapasów ze średnią ważoną datą jest używany do tworzenia rozliczeń i korygowania wartości rozchodów zgodnie z zasadą średniej ważonej daty. Dopóki nie przeprowadzisz zamknięcia inwentarza, transakcje wydania są wyceniane według średniej bieżącej z momentu aktualizacji fizycznej i finansowej. Jeśli nie używasz znakowania, średnia krocząca jest obliczana w momencie przeprowadzania fizycznej lub finansowej aktualizacji.

Metoda kalkulacji kosztów zapasów według średniej ważonej według daty jest obliczana każdego dnia przy użyciu następującego wzoru:

*Koszt* = \[(*Q*<sub>*b*</sub> × *P*<sub>*b*</sub>) + &#x2211;<sub>*n*</sub>(*Q*<sub>*n*</sub> × *P*<sub>*n*</sub>)\] ÷ (*Q*<sub>*b*</sub> + &#x2211;<sub>*n*</sub>*Q*<sub>*n*</sub>)

- *Q* = Ilość transakcji
- *P* = cena transakcji

Innymi słowy, średni ważony koszt jest równy początkowej ilości razy cena początkowa plus suma każdej ilości przychodu pomnożona przez jej cenę przychodu, wszystkie podzielone przez początkową ilość plus sumę ilości przyjęć.

Podczas zamknięcia zapasów kalkulacja jest wykonywana codziennie w okresie zamknięcia.

> [!NOTE]
> Aby uzyskać więcej informacji o rozliczeniach, zobacz [Zamknięcie inwentarza](inventory-close.md).

Poniższe przykłady pokazują efekt użycia średniej ważonej daty z pięcioma konfiguracjami:

- Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji **Włącz wartość fizyczną**
- Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji **Włącz wartość fizyczną**
- Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień z opcją **Włącz wartość fizyczną**
- Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień z opcją **Włącz wartość fizyczną**
- Średnia ważona na dzień z przypisaniem

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną

Zasada bezpośredniego rozliczania tworzy rozliczenia bezpośrednio między przychodami i rozliczeniami bez tworzenia dodatkowych transakcji magazynowych. System wykorzystuje tę zasadę bezpośredniego rozliczania w następujących sytuacjach:

- w danym okresie zaksięgowano jedną transakcję dotyczącą przychodów oraz co najmniej jedną transakcję dotyczącą rozchodów lub
- w danym okresie zaksięgowano wyłącznie rozchody, a w magazynie znajdują się zapasy z poprzedniego okresu zamknięcia.

W tym przykładzie pole wyboru **Uwzględnij wartość fizyczną** jest wyczyszczony w grupie modeli **pozycji dla zwolnionego produktu**. Poniższy diagram przedstawia te transakcje:

**Dzień 1:**

- 1a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 20,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 10,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).

**Dzień 2:**

- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 20,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).

**Dzień 3:**

- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o metodę średniej ważonej daty system stosuje metodę bezpośredniego rozliczenia na 30 grudnia (12/30), ponieważ tylko jeden paragon jest aktualizowany finansowo 30 grudnia. W tym przykładzie tworzone jest jedno rozliczenie między transakcjami 1b i 3b. Korekta USD 10.00 w celu zrównania wartości transakcji z 3b do 20,00. Nie dokonano korekty ani rozliczenia 31 grudnia (12/31), ponieważ 31 grudnia nie zaktualizowano finansowo rozliczeniu.

Poniższy diagram przedstawia tę serię transakcji oraz skutki zastosowania modelu zapasów ze średnią ważoną i zasady rozliczenia bezpośredniego bez opcji **Włącz wartość fizyczną**.

![Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**Objaśnienie wykresu:**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Daty są rozdzielane przez zużytą czarna pionowe wiersze. Daty są zapisane na dole diagramu.
- Zamknięcia zapasów są reprezentowane przez czerwone pionowe linie przerywane.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną

Jeśli w okresie występuje wiele przyjęć, średnia ważona data wykorzystuje zasadę rozliczenia sumarycznego, w której wszystkie przychody w ciągu jednego dnia są sumowane w transakcji o nazwie *średnie ważone zamknięcie zapasów*. Wszystkie wpływy na dany dzień zostaną rozliczone z rozchodami nowo utworzonej transakcji magazynowej. Wszystkie sprawy na dany dzień zostaną rozliczone po otrzymaniu transakcji z nową inwentaryzacją. Jeśli po zamknięciu magazynu pozostała wartość dostępnych zapasów, wartość dostępnych zapasów jest uwzględniana w transakcji przychodu transakcji zamknięcia magazynu średniej ważonej.

Poniższy diagram przedstawia te transakcje:

**Dzień 1:**

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).

**Dzień 2:**

- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).

**Dzień 3:**

- 7\. Wykonywane jest zamknięcie magazynu.
- 7a. Finansowy rozchód transakcja zamknięcia magazynu średniej ważonej zostaje utworzony w celu zsumowania płatności wszystkich przychodów finansowych magazynu.

    - Transakcja 1b jest rozliczana dla ilości 1 z kwotą rozliczeniową 10,00 USD.
    - Transakcja 2b jest rozliczana dla ilości 1 z kwotą rozliczeniową 22,00 USD.
    - Transakcja 7a jest tworzona dla ilości 2 sztuk z kwotą rozliczenia 32,00 USD. Transakcja jest przeciwstawna do sumy dwóch transakcji przychodów, które zostały finansowo zaktualizowane w tym okresie.

- 7b. Średni ważony finansowy przychód zamknięcia magazynu jest tworzony jako kompensacja finansowo zaksięgowanych rozchodów.

    - Transakcja 3b jest rozliczana dla ilości 1 z kwotą rozliczeniową 16,00 USD. Transakcja ta nie jest korygowana, ponieważ jest to średnia ważona transakcji finansowych zaksięgowanych na dzień 1 grudnia (12/1).
    - Transakcja 7b jest tworzona dla ilości 2 z kwotą finansową 32,00 USD i kwotą rozliczoną 16,00 USD w celu skompensowania transakcji 3b. Ta transakcja kompensuje sumę jednej transakcji wydania, która jest aktualizowana finansowo w danym okresie. Transakcja pozostaje otwarta, ponieważ nadal jest dostępne.

Na poniższym diagramie przedstawiono powyższe transakcje oraz efekt zastosowania w ich przypadku modelu magazynu opartego na średniej ważonej i zasady rozliczenia sumarycznego bez opcji **Włącz wartość fizyczną**.

![Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień bez opcji Włącz wartość fizyczną.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**Objaśnienie wykresu:**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Daty są rozdzielane przez zużytą czarna pionowe wiersze. Daty są zapisane na dole diagramu.
- Zamknięcia zapasów są reprezentowane przez czerwone pionowe linie przerywane.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Rozliczenie bezpośrednie z zastosowaniem średniej ważonej na dzień z opcją Włącz wartość fizyczną

W bieżącej wersji produktu opcja **Włącz wartość fizyczną** działa inaczej w modelu inwentaryzacji ze średnią ważoną datą niż we wcześniejszych wersjach. Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupa modeli pozycji**, system użyje fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej ruchomej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. W okresie zamknięcia magazynu finansowo zaktualizowane przychody będą uwzględniane wyłącznie w przypadku obliczania średniej ważonej.

Poniższy diagram przedstawia te transakcje:

**Dzień 1:**

- 1a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 10 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 10 i po koszcie 20,00 USD.
- 3a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 3b. Wydanie finansowe zapasów dla ilości 1 szt. w cenie nabycia 15,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).

**Dzień 2:**

- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 21,25 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).

**Dzień 3:**

- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o metodę średniej ważonej daty system stosuje metodę bezpośredniego rozliczenia na 30 grudnia (12/30), ponieważ tylko jeden paragon jest aktualizowany finansowo 30 grudnia. W tym przykładzie tworzone jest jedno rozliczenie między transakcjami 1b i 3b. Nie dokonano korekty w wydaniu z dnia 12/30. Ponadto na dzień 31 grudnia nie dokonuje się korekty ani rozliczenia, ponieważ na dzień 31 grudnia nie ma żadnych zaktualizowanych finansowo wydań.

Poniższy diagram przedstawia tę serię transakcji oraz skutki zastosowania modelu zapasów ze średnią ważoną i zasady rozliczenia bezpośredniego z opcją **Włącz wartość fizyczną**.

![Średnie ważone rozliczenie bezpośrednie z Uwzględnij wartość fizyczną.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**Objaśnienie wykresu:**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Daty są rozdzielane przez zużytą czarna pionowe wiersze. Daty są zapisane na dole diagramu.
- Zamknięcia zapasów są reprezentowane przez czerwone pionowe linie przerywane.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Rozliczenie sumaryczne z zastosowaniem średniej ważonej na dzień z opcją Włącz wartość fizyczną

W bieżącej wersji produktu opcja **Włącz wartość fizyczną** działa inaczej ze średnią ważoną niż we wcześniejszych wersjach. Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupa modeli pozycji**, system użyje fizycznie zaktualizowanych przyjęć podczas obliczania szacowanego kosztu własnego (średniej ruchomej). W danym okresie rozchody będą księgowane według takiego szacowanego kosztu własnego. W okresie zamknięcia magazynu finansowo zaktualizowane przychody będą uwzględniane wyłącznie w przypadku obliczania średniej ważonej. W przypadku korzystania ze średniej ważonej modelu zapasów zalecamy comiesięczne zamknięcie zapasów. W tym przykładzie rozliczenia sumarycznego ze średnią ważoną z datą model zapasów jest oznaczony tak, aby zawierał wartość fizyczną.

Poniższy diagram przedstawia te transakcje:

**Dzień 1:**

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 16,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 3b. Wydanie finansowe zapasów dla ilości 1 szt. w cenie nabycia 16,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).

**Dzień 2:**

- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 23,67 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).

**Dzień 3:**

- 7\. Wykonywane jest zamknięcie magazynu.
- 7a. Finansowy rozchód transakcja zamknięcia magazynu średniej ważonej zostaje utworzony w celu zsumowania płatności wszystkich przychodów finansowych magazynu.

    - Transakcja 1b jest rozliczana dla ilości 1 z kwotą rozliczeniową 10,00 USD.
    - Transakcja 2b jest rozliczana dla ilości 1 z kwotą rozliczeniową 22,00 USD.
    - Transakcja 7a jest tworzona dla ilości 2 sztuk z kwotą rozliczenia 32,00 USD. Transakcja jest przeciwstawna do sumy dwóch transakcji przychodów, które zostały finansowo zaktualizowane w tym okresie.

- 7b. Średni ważony finansowy przychód zamknięcia magazynu jest tworzony jako kompensacja finansowo zaksięgowanych rozchodów.

    - Transakcja 3b jest rozliczana dla ilości 1 z kwotą rozliczeniową 16,00 USD. Transakcja ta nie jest korygowana, ponieważ jest to średnia ważona transakcji finansowych zaksięgowanych na dzień 1 grudnia (12/1).
    - Transakcja 7b jest tworzona dla ilości 2 z kwotą finansową 32,00 USD i kwotą rozliczoną 16,00 USD w celu skompensowania transakcji 3b. Ta transakcja kompensuje sumę jednej transakcji wydania, która jest aktualizowana finansowo w danym okresie. Transakcja pozostaje otwarta, ponieważ nadal jest dostępne.

Poniższy diagram przedstawia tę serię transakcji oraz skutki zastosowania modelu średniej ważonej zapasów i zasady rozliczenia sumarycznego bez opcji **Włącz wartość fizyczną**.

![Średnie ważone sumaryczne rozliczenie z Uwzględnij wartość fizyczną.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**Objaśnienie wykresu:**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Daty są rozdzielane przez zużytą czarna pionowe wiersze. Daty są zapisane na dole diagramu.
- Zamknięcia zapasów są reprezentowane przez czerwone pionowe linie przerywane.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="weighted-average-date-when-marking-is-used"></a>Średnia ważona na dzień z przypisaniem

Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Możesz użyć oznaczania, gdy chcesz mieć pewność co do dokładnego kosztu zapasów, gdy transakcja jest księgowana lub wykonywane jest zamknięcie zapasów.

Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Zamówienie jest pilne, trzeba będzie zatem zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Trzeba się upewnić, że koszt tej pozycji magazynowej zostanie uwzględniony w marży (lub koszcie własnym sprzedaży, COGS) na tej fakturze za zamówienie sprzedaży.

Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Jeśli dokument zamówienia sprzedaży jest oznaczony w zamówieniu zakupu przed zaksięgowaniem dokumentu dostawy lub faktury, KWS wyniesie 120,00 USD zamiast bieżącego średniego kosztu bieżącego towaru. Jeśli oznakowanie nastąpi po zaksięgowaniu dokumentu dostawy lub faktury zamówienia sprzedaży, KWS zostaną zaksięgowane według średniej kroczącej kosztu własnego.

Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie.

Jeśli transakcja przyjęcia jest oznaczona jako transakcja wydania, metoda wyceny wybrana dla grupy modeli towaru zostanie pominięta, a system dokona wzajemnego rozliczenia tych transakcji.

Można zaznaczyć transakcję rozchodu do przyjęcia przed zaksięgowaniem transakcji. Możesz to zrobić z wiersza zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**.

Można też zaznaczyć transakcję rozchodu do przyjęcia po zaksięgowaniu transakcji. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów.

Poniższy diagram przedstawia te transakcje:

**Dzień 1:**

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3c. Finansowy rozchód magazynowy dla transakcji 3b jest oznaczony jako finansowy rozchód magazynowy dla transakcji 2b.

**Dzień 2:**

- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).

**Dzień 3:**

- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o zasadę znakowania wykorzystującą metodę średniej ważonej, oznaczone transakcje są rozliczane względem siebie. W tym przykładzie transakcja 3b jest rozliczana z transakcją 2b, a korekta o 6,00 USD jest księgowana w transakcji 3b, aby uzyskać wartość 22,00 USD. W tym przykładzie nie są dokonywane żadne dodatkowe rozliczenia, ponieważ zamknięcie tworzy rozliczenia tylko dla transakcji zaktualizowanych finansowo.

Poniższy diagram przedstawia tę serię transakcji oraz skutki zastosowania modelu średniej ważonej zapasów z oznaczeniem.

![Średnia ważona z oznaczeniem.](media/weighted-average-date-with-marking.png)

**Objaśnienie wykresu:**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Daty są rozdzielane przez zużytą czarna pionowe wiersze. Daty są zapisane na dole diagramu.
- Zamknięcia zapasów są reprezentowane przez czerwone pionowe linie przerywane.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
