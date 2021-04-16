---
title: Stornowanie
description: Stornowanie to praktyka używania liczb ujemnych, aby odwrócić oryginalne zapisy na koncie arkusza.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 1219713
ms.search.region: Czech Republic, Germany, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e1d5b0ae6191204b7dd3be4e9c446d704263e67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832677"
---
# <a name="storno-accounting"></a>Stornowanie

[!include [banner](../includes/banner.md)]

Stornowanie to praktyka używania liczb ujemnych, aby odwrócić oryginalne zapisy na koncie arkusza.

*Stornowanie* to praktyka używania ujemnych liczb po stronie winien lub ma, aby odwrócić oryginalne zapisy na koncie arkusza. Ponieważ księgowi zazwyczaj zapisują pozycje storna czerwonym atramentem, ta praktyka księgowa jest również znana jako *storno czerwone*. Za pomocą stornowania można anulować dokument z niepoprawnymi kwotami, ale po anulowaniu należy zawsze wprowadzić poprawne kwoty dokumentu.

## <a name="example"></a>Przykład
Księgowy księguje fakturę od dostawcy na 120 USD. W procesie realizacji płatności okazało się, że księgowy wprowadził przez pomyłkę kwotę 120 USD zamiast 102 USD. Teraz księgowy musi utworzyć storno dla oryginalnego dokumentu, a następnie utworzyć poprawną fakturę na 102 USD. Aby uzyskać więcej informacji, zobacz [Omówienie faktur od dostawców](../accounts-payable/vendor-invoices-overview.md). W poniższej tabeli przedstawiono ogólny wpis storna.

| **Identyfikator dokumentu** | **Konto** | **Strona debetowa** | **Strona kredytowa** | **Komentarz**                  |
|-----------------|-------------|-----------|------------|------------------------------|
| Faktura0001     | Konto zakupu   | 120       |            | Oryginalna faktura (błędna) |
| Faktura0001     | Konto dostawcy  |           | 120        | Oryginalna faktura (błędna) |
|                 |             |           |            |                              |
| Storno0001      | Konto zakupu   | -120     |            | Storno                       |
| Storno0001      | Konto dostawcy  |           | -120      | Storno                       |
|                 |             |           |            |                              |
| Faktura0002     | Konto zakupu   | 102       |            | Poprawna faktura              |
| Faktura0002     | Konto dostawcy  |           | 102        | Poprawna faktura              |

W tym przykładzie saldo wyciągu pokazuje następujące dane.

| Konto    | Strona debetowa | Strona kredytowa | Bilansowe |
|------------|-------|--------|---------|
| Konto zakupu  | 102   | 0      | 102     |
| Konto dostawcy | 0     | 102    | -102    |

## <a name="differences-between-storno-and-reverse-entries"></a>Różnica między zapisami stornującymi a korygującymi
Istnieją dwa sposoby poprawiania wpisów księgowania – wycofanie i storno. Podczas używania wpisu korygującego jest generowana kopia oryginalnego wpisu ogólnego na odwrotnych kontach debetowych i kredytowych, a kwoty zachowują pierwotny znak. Jeśli używasz storna, system tworzy kopię oryginalnego wpisu ogólnego, ale kwoty są rejestrowane ze znakiem minusa. W poniższej tabeli przedstawiono ogólny wpis storna.

| **Identyfikator dokumentu** | **Konto** | **Strona debetowa** | **Strona kredytowa** | **Komentarz**                  |
|-----------------|-------------|-----------|------------|------------------------------|
| Faktura0001     | Konto zakupu   | 120       |            | Oryginalna faktura (błędna) |
| Faktura0001     | Konto dostawcy  |           | 120        | Oryginalna faktura (błędna) |
|                 |             |           |            |                              |
| Wycofanie0001     | Konto zakupu   |           | 120        | Wycofaj                      |
| Wycofanie0001     | Konto dostawcy  | 120       |            | Wycofaj                      |
|                 |             |           |            |                              |
| Faktura0002     | Konto zakupu   | 102       |            | Poprawna faktura              |
| Faktura0002     | Konto dostawcy  |           | 102        | Poprawna faktura              |

W tym przykładzie saldo wyciągu pokazuje następujące dane.

| Konto    | Strona debetowa | Strona kredytowa | Bilansowe |
|------------|-------|--------|---------|
| Konto zakupu  | 222   | 120    | 102     |
| Konto dostawcy | 120   | 222    | -102    |

Należy zauważyć, że salda są takie same dla wycofania i storna. Różnią się obroty po stronach winien i ma, ponieważ wpis korygujący tworzy nadmiarowy obrót po obu stronach. Wpis korygujący jest używany w krajach/regionach, gdzie rzadko używa się obrotu. W pozostałych krajach/regionach stosuje się stornowanie.

## <a name="partial-storno"></a>Storno częściowe
*Storno częściowe* to praktyka księgowa używania ujemnych liczb po stronie winien lub ma, aby odwrócić część oryginalnych zapisów na koncie arkusza. Niektóre kraje/regiony pozwalają na używanie storna częściowego. Na przykład księgowy księguje fakturę od dostawcy na 120 USD. W procesie realizacji płatności okazało się, że księgowy przez pomyłkę wpisał błędny numer kolejny. Oryginalna fakturą na 102 USD ma błąd w numeracji. Używając funkcji storna częściowego, księgowy powinien utworzyć storno na 18 USD. W poniższej tabeli przedstawiono ogólny wpis storna częściowego.

| **Identyfikator dokumentu** | **Konto** | **Strona debetowa** | **Strona kredytowa** | **Komentarz**                  |
|-----------------|-------------|-----------|------------|------------------------------|
| Faktura0001     | Konto zakupu   | 120       |            | Oryginalna faktura (błędna) |
| Faktura0001     | Konto dostawcy  |           | 120        | Oryginalna faktura (błędna) |
|                 |             |           |            |                              |
| Storno0001      | Konto zakupu   | 18\-      |            | Storno częściowe               |
| Storno0001      | Konto dostawcy  |           | 18\-       | Storno częściowe               |

W tym przykładzie saldo wyciągu pokazuje następujące dane.

| Konto    | Strona debetowa | Strona kredytowa | Bilansowe |
|------------|-------|--------|---------|
| Konto zakupu  | 102   | 0      | 102     |
| Konto dostawcy | 0     | 102    | -102    |

Storno częściowe może powodować problem na oryginalnie drukowanym formularzu. Jeśli istnieje różnica między datą oryginalnego dokumentu a datą storna, może być trudne ustalenie dokładnej kwoty w walucie. W efekcie storno częściowe jest dozwolone tylko w niektórych dokumentach. Dynamics 365 Finance zawiera funkcjonalność storna częściowego dla dokumentów i krajów/regionów, gdzie jest ona dozwolona.

## <a name="how-to-enter-storno-on-journal-lines"></a>Jak wprowadzić storno w wierszach arkusza
Aby wprowadzić zapis stornujący, wpisz kwotę po stronie winien lub ma ze znakiem minusa w wierszu arkusza. Wartość w polu **Korekta** jest ustawiana w trakcie procesu księgowania. 

## <a name="how-storno-is-displayed"></a>Sposób wyświetlania storna
Finance traktuje ujemne kwoty arkuszy w szczególny sposób. Wpis arkusza finansowego, transakcja odbiorcy, transakcja dostawcy i inne typy transakcji zawierają funkcję storna, jak pokazano poniżej.

<table>
<thead>
<tr class="row-1">
<th class="column-1" rowspan="2">Dane wprowadzone przez użytkownika w wierszu arkusza</th>
<th class="column-2" colspan="2">Zasada przechowywania</th>
<th class="column-4" colspan="2">Reguła wyświetlania</th>
<th class="column-6" colspan="3">Wpływ na sprawozdanie</th>
</tr>
<tr class="row-1">
<th class="column-2">Pole korekty</th>
<th class="column-3">Pole kwoty</th>
<th class="column-4">Kwota w walucie transakcji</th>
<th class="column-5">Ilość</th>
<th class="column-6">Kolumna Winien</th>
<th class="column-7">Kolumna Ma</th>
<th class="column-8">Kolumna salda</th>
</tr>
</thead>
<tbody>
<tr class="row-2">
<td class="column-1"> Strona debetowa</td>
<td class="column-2">Nr</td>
<td class="column-3">0&gt;</td>
<td class="column-4" align="right">Ilość</td>
<td class="column-5" align="right">Ilość</td>
<td class="column-6">Zwiększa</td>
<td class="column-7"></td>
<td class="column-8">Zwiększa</td>
</tr>
<tr class="row-3">
<td class="column-1"> Strona kredytowa</td>
<td class="column-2">Nr</td>
<td class="column-3">0&lt;</td>
<td class="column-4" align="right">-Kwota</td>
<td class="column-5" align="right">Ilość</td>
<td class="column-6"></td>
<td class="column-7">Zwiększa</td>
<td class="column-8">Zmniejsza</td>
</tr>
<tr class="row-4">
<td class="column-1">-Winien</td>
<td class="column-2">Tak</td>
<td class="column-3">0&gt;</td>
<td class="column-4" align="right">+Kwota</td>
<td class="column-5" align="right">-Kwota</td>
<td class="column-6">Zmniejsza</td>
<td class="column-7"></td>
<td class="column-8">Zwiększa</td>
</tr>
<tr class="row-5">
<td class="column-1">-Ma</td>
<td class="column-2">Tak</td>
<td class="column-3">0&lt;</td>
<td class="column-4" align="right">-Kwota</td>
<td class="column-5" align="right">-Kwota</td>
<td class="column-6"></td>
<td class="column-7">Zmniejsza</td>
<td class="column-8">Zmniejsza</td>
</tr>
</tbody>
</table>

Można dostosować wyświetlanie storna w formularzach, siatkach, kolumnach i polach. Na przykład można wyłączyć wyświetlanie znaku lub zmienić dopełnianie dla kwot ujemnych. Można również używać pola **Korekta** ze wszystkimi ustawieniami wyświetlania. Jeśli pole **Korekta** ma ustawioną wartość „tak”, jest zapisem stornującym.

![Kwoty storna we wpisach w arkuszu](./media/journal-storno.png)

## <a name="how-documents-create-storno"></a>Jak dokumenty tworzą storna
Niektóre dokumenty powodują tworzenie transakcji anulowania. Na przykład przeszacowania w walucie obcej dla dokumentów księgi głównej, rozrachunków z dostawcami i rozrachunków z odbiorcami powodują anulowanie niezrealizowanych dodatnich i ujemnych różnic kursowych. Aby uzyskać więcej informacji, zajrzyj do [Przeszacowanie w walucie obcej dla księgi głównej](../general-ledger/foreign-currency-revaluation-general-ledger.md) dla [Przeszacowanie w walucie obcej dla rozrachunków z odbiorcami i rozrachunków z dostawcami](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md). Po utworzeniu transakcji anulowania zostaną utworzone nowe transakcje z niezrealizowanymi dodatnimi i ujemnymi różnicami kursowymi. Transakcje anulowania są również tworzone dla zapasów. Aby uzyskać więcej informacji, zobacz [Zamknięcie zapasów](../../supply-chain/cost-management/inventory-close.md). Istnieją dokumenty pozwalające anulować uprzednio zaksięgowany dokument. Na przykład użytkownik może utworzyć fakturę korygującą w celu anulowania uprzednio utworzonej faktury. Do tworzenia transakcji storna lub wycofania dokumenty wykorzystują określone parametry. Na przykład przeszacowanie w walucie obcej tworzy transakcje wycofania lub storna przy użyciu parametru korekty księgi głównej. Faktura korygująca dla odbiorcy tworzy transakcję wycofania lub storna przy użyciu parametru korekty na fakturze korygującej dostępnego w module rozrachunków z odbiorcami.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]