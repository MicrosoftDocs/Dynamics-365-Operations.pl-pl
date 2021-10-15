---
title: Metody uzupełniania zapasów i modyfikacja ilości
description: Ten temat zawiera informacje na temat metod uzupełniania zapasów w optymalizacji planowania. Wyjaśnia również, w jaki sposób wielokrotność zamówienia dla produktu wpływa na wynik.
author: ChristianRytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 017dabb46265769bf727056a9bf1a8c0cfdc99f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567302"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Metody uzupełniania zapasów i modyfikacja ilości

[!include [banner](../../includes/banner.md)]

Ten temat zawiera informacje na temat metod uzupełniania zapasów w optymalizacji planowania. Wyjaśnia również, w jaki sposób wielokrotność zamówienia dla produktu wpływa na wynik.

Metody uzupełniania zapasów są również znane jako metody pokrycia i metody wielkości partii.

## <a name="coverage-codes"></a>Kody zapotrzebowania

Planowanie optymalizacji można skonfigurować w taki sposób, aby korzystało z różnych metod uzupełniania zapasów. Metody uzupełniania zapasów są technikami, które system wykorzystuje do obliczania zapotrzebowania na dany produkt. Metody uzupełniania są zdefiniowane przez kody zakresu, które można ustawić na grupie zakresu lub na produkcie.

Następujące kody pokrycia mogą być użyte w optymalizacji planowania:

- **Na okres** — metoda uzupełniania zapasów łączy całe zapotrzebowanie na dany okres w jedno zamówienie na dany produkt. Zamówienie zostanie zaplanowane na pierwszy dzień okresu, a jego ilość będzie spełniać zapotrzebowania netto w ustalonym okresie. Okres rozpoczyna się od pierwszego zapotrzebowania na produkt i obejmuje zdefiniowany okres w czasie. Następny okres rozpocznie się od kolejnych wymagań dotyczących produktu. Kod pokrycia *Okres* jest często stosowany w przypadku nieprzewidywalnych losowań zapasów, produktów uzależnionych od pory roku lub produktów o wysokich kosztach. Na poniższej ilustracji pokazano przykład.

    ![Przykład użycia kodu zapotrzebowania okresowego.](./media/coverage-code-period.png "Przykład użycia kodu zapotrzebowania okresowego")

- **Wymaganie** — w metodzie uzupełniania zapasów system tworzy planowane zlecenie zakupu, przesunięcia lub produkcji na zapotrzebowanie na dany produkt. Ta metoda jest używana dla drogich produktów, które mają nieregularny popyt. Kod *Zapotrzebowania* jest często używany w przypadku produktów konfigurowalnych lub scenariuszy produkcji na zamówienie. Na poniższej ilustracji pokazano przykład.

    ![Przykład użycia kodu zapotrzebowania wymagania.](./media/coverage-code-requirement.png "Przykład użycia kodu zapotrzebowania wymagania")

- **Minimum/Maksimum** — metoda uzupełniania zapasów jest oparta na poziomie zapasów. Określa uzupełnianie zapasów do określonego poziomu, gdy przewidywany poziom zapasów na stanie jest poniżej określonego progu. Ilość uzupełniania zapasów będzie różnicą między maksymalnym poziomem i przewidywanym poziomem zapasów. Kod zapotrzebowania *minimum/maksimum* jest często używany dla przewidywalnego rysunku zapasów, wysokich biegaczy, lub tańszych produktów. Na poniższej ilustracji pokazano przykład.

    ![Przykład użycia kodu pokrycia min./max.](./media/coverage-code-min-max.png "Przykład użycia kodu pokrycia min./max.")

- **Ręczna** — w metodzie uzupełniania system nie sugeruje zleceń zakupu, przesunięcia, czy produkcji produktu. Zamiast tego, planista produktu jest odpowiedzialny za tworzenie wymaganych zamówień w celu uzupełnienia produktu. Kod zapotrzebowania *ręcznego* jest często używany w przypadku produktów, których nie chce używać wygenerowane przez system planowane zamówienia.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Wpływ ilości zamówienia z domyślnych ustawień zamówienia

Na stronie **Domyślne ustawienie zamówienia** dla wydanego produktu można określić każde z następujących ustawień ilości na szybkich kartach **Zamówienie**, **Zapasy** i **Zamówienie sprzedaży**. (Skrócona karta **Inwentaryzacja** jest używana zarówno dla zleceń transferowych jak i zleceń produkcyjnych.)

- **Wiele** — planowane zamówienia będą wielokrotnością tej ilości.

    Na przykład, jeśli pole **Wielokrotność** jest ustawione na *5*, zamówienie może dotyczyć ilości 5, 10, 15, 20 itd.

- **Minimalna ilość zamówienia** — zamówienia planowane nie będą mniejsze niż określona wartość.

    Na przykład, jeśli w polu **Minimalna ilość zamówienia** jest ustawiona wartość *10*, zostanie utworzone zamówienie planowane na ilość 10, nawet jeśli do spełnienia popytu są wymagane tylko cztery.

- **maksymalna ilość zamówienia** — zamówienia planowane nie będą większe niż określona wartość. Jeśli zapotrzebowanie jest większe niż wartość **Max. ilość zamówienia**, zostanie utworzonych wiele planowanych zamówień, aby je pokryć.

    Jeśli np. w polu **Maks. ilość zamówienia** ustawiono wartość *100*, a zapotrzebowanie wynosi 450, to zostaną utworzone cztery planowane zamówienia na ilość 100 i jedno planowane zamówienie na ilość 50.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Przykłady uzupełniania zapasów z wykorzystaniem kodu min./maks.

Jeśli nie podasz wartości w polu **Wielokrotność** dla produktu na stronie **Domyślne ustawienia zamówienia** i jeśli korzystasz z metody uzupełniania *Min./Max*. , wtedy optymalizacja planowania uzupełni zapas do określonego poziomu, gdy przewidywany poziom na rękę jest poniżej określonego progu.

W przypadku zdefiniowania ilości wielokrotności, wartość metody odnawiania *min./maks.* zmienia swoje zachowanie i bierze pod uwagę wartość **Wielokrotność**.

Innymi słowy, optymalizacja planowania będzie nadal uzupełniać zapasy do zdefiniowanego maksymalnego poziomu, gdy przewidywany poziom na rękę jest mniejszy niż zdefiniowany poziom minimalny. Ilość uzupełnienia musi być jednak wielokrotnością wartości **Wielokrotność**.

Jeśli ilość uzupełnienia (różnica pomiędzy poziomem maksymalnym a przewidywanym poziomem na stanie) nie jest wielokrotnością zdefiniowanej ilości wielokrotnej, optymalizacja planowania używa pierwszej możliwej wartości, która wraz z przewidywanym poziomem na stanie będzie poniżej poziomu maksymalnego. Jeśli suma jest mniejsza niż poziom minimalny, optymalizacja planowania wykorzystuje pierwszą wartość, która wraz z przewidywanym stanem magazynowym będzie powyżej poziomu maksymalnego.

Poniższe podrozdziały zawierają kilka przykładów, które pokazują, jak wielokrotne zamawianie produktu wpływa na wynik metody uzupełniania zapasów *min./maks.* .

### <a name="example-1"></a>Przykład 1

Produkt ma następującą konfigurację:

- **Kod objęcia świadczeniem:** *Minimum/Maksimum*.
- **Minimum:** *15*
- **Maksimum:** *22*
- **Wielokrotność:** *0*

Istnieje 10 sztuk zapasów na rękę dla produktu, a nie ma innego popytu lub podaży.

Po uruchomieniu planowania głównego tworzone jest planowane zamówienie na 12 sztuk w celu uzupełnienia zapasów do maksymalnej ilości.

### <a name="example-2"></a>Przykład 2

Produkt ma następującą konfigurację:

- **Kod objęcia świadczeniem:** *Minimum/Maksimum*.
- **Minimum:** *15*
- **Maksimum:** *22*
- **Wielokrotność:** *5*

Istnieje 10 sztuk zapasów na rękę dla produktu, a nie ma innego popytu lub podaży.

Po uruchomieniu planowania głównego tworzone jest planowane zamówienie na 10 sztuk (ponieważ 15 sztuk z uzupełnienia plus 10 sztuk z zapasów na stanie przekroczy ilość maksymalną).

### <a name="example-3"></a>Przykład 3

Produkt ma następującą konfigurację:

- **Kod objęcia świadczeniem:** *Minimum/Maksimum*.
- **Minimum:** *21*
- **Maksimum:** *24*
- **Wielokrotność:** *5*

Istnieje 10 sztuk zapasów na rękę dla produktu, a nie ma innego popytu lub podaży.

Po uruchomieniu planowania głównego tworzone jest planowane zamówienie na 15 sztuk (ponieważ 10 sztuk z uzupełnienia plus 10 sztuk z zapasów na stanie będzie mniejsze od ilości minimalnej).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
