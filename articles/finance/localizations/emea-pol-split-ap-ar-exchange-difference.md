---
title: Podziel zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty VAT
description: W tym artykule opisano, jak podzielić zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty podatku od towarów i usług (VAT).
author: AdamTrukawka
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: atrukawk
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: ''
ms.custom: 414136
ms.openlocfilehash: 1bd7f2128152247b4bc64af196ccc88423729713
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269345"
---
# <a name="split-the-realized-exchange-difference-amount-into-the-difference-of-the-invoice-net-value-and-the-vat-amount"></a>Podziel zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty VAT

[!include [banner](../includes/banner.md)]

Funkcja **Podziel zrealizowaną różnicę kursową AP/AR na różnicę między wartością netto faktury i kwotą VAT** pozwala podzielić kwotę rozrachunków z dostawcami (punkt dostępu) i Rozrachunki z odbiorcami (AR) przeszacowanie w walucie obcej na dwie części:

- Różnica kursowa związana z wartością netto faktury (zadłużenie odbiorcy i zobowiązania dostawcy)
- Różnica kursowa powiązana z kwotą podatku VAT na fakturze

Można również zaksięgować różnice kursowe powiązane z kwotą faktury VAT na oddzielne konto księgowe zrealizowanych zysków i strat.

Ta funkcja jest dostępna tylko w firmach z polskim kontekstem kraju/regionu.

## <a name="setup"></a>Konfiguracja

### <a name="activate-the-feature"></a>Aktywowanie funkcji

W obszarze roboczym **Zarządzanie funkcjami** włącz następującą funkcję: **(Polska) Podziel zrealizowaną różnicę kursową AP/AR na różnicę między wartością netto faktury i kwotą VAT**.

### <a name="set-up-ledger-accounts"></a>Konfigurowanie kont księgi

Wykonaj poniższe kroki, aby skonfigurować konto księgowe, za pomocą którego można księgować kwotę różnicy kursowej powiązaną z kwotą podatku na fakturze.

1. Przejdź do **Księga główna** \> **Waluty** \> **Konta przeszacowania waluty**. 
2. Na stronie **Konta przeszacowania waluty** wybierz kod waluty, a następnie w polu **Księga** wybierz kod firmy.

    ![Strona Konta przeszacowania waluty.](media/Currency-revaluation-accounts.png)

2. Wybierz wiersz, w którym pole **Księgowanie** jest ustawione jako **Zrealizowana dodatnia różnica kursowa** lub **Zrealizowana ujemna różnica kursowa**.
3. Skonfiguruj konto główne i wybierz konto księgowe, na które chcesz zaksięgować zrealizowaną różnicę kursową.
4. W polu **Podatki** wybierz opcję **Wydatek**, aby zaksięgować część kwoty zrealizowanej różnicy kursowej powiązaną z kwotą podatku faktury na osobne konto księgowe wydatków. 
5. W polu **Konto księgowania podatku** wybierz to samo konto księgowe wydatków.

## <a name="post-and-settle-customer-and-vendor-transactions"></a>Księgowanie i rozliczanie transakcji odbiorcy i dostawcy

Umożliwia księgowanie i rozliczanie dokumentów w zwykły sposób. Transakcja różnic kursowych tworzona podczas rozliczania spowoduje wygenerowanie załącznika, w którym kwota różnicy kursowej powiązana z kwotą podatku jest księgowana oddzielnie na koncie księgowym wybranym w polu **Konto księgowania podatku** na stronie **Konta przeszacowania waluty**.

## <a name="known-limitations"></a>Znane ograniczenia

Nie powinieneś korzystać z tej funkcji, jeśli księgujesz faktury od dostawców za pomocą dzienników **Rejestr faktur** i **Zatwierdzanie faktur**.

## <a name="examples"></a>Przykłady

W poniższych dwóch przykładach są wyświetlane wynikowe transakcje finansowe.

### <a name="example-1"></a>Przykład 1

Wykonaj następujące czynności konfiguracyjne w firmie **DEMF**.

1. Zmień kraj/region na **POL**.
2. Na stronie **Księga** sprawdź, czy w polu **Waluta rozliczeniowa** określono wartość **EUR**.
3. Umożliwia konfigurowanie kursów wymiany walut dla **Domyślnego** typu kursu wymiany, co przedstawiono w poniższej tabeli.

    | Data             | Dolary amerykańskie (USD) | Euro (EUR) | opis        |
    |------------------|------------------|-------------|--------------------|
    | 1 stycznia 2020 r.  | 100              | 80          | 100 USD za 80 EUR |
    | 10 stycznia 2020 r. | 100              | 90          | 100 USD za 90 EUR |

4. Skonfiguruj konta księgo dla zrealizowanej różnicy kursowej na kocnie głównym i koncie księgowania podatku.

Zaksięguj poniższe transakcje.

<table>
<thead>
<tr>
<th>Wydruk pokwitowania</th>
<th>Data</th>
<th>Kwota w dolarach USD</th>
<th>Kwota w dolarach EUR</th>
<th>Załącznik</th>
<th>Kwota załącznika</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='3'>Faktura dla odbiorcy</td>
<td rowspan='3'>1 stycznia 2020 r.</td>
<td rowspan='3'>119 USD, która zawiera kwotę podatku VAT 19 USD</td>
<td rowspan='3'>95.20 EUR, która zawiera kwotę podatku VAT 15.20 EUR</td>
<td>Debet <em>AR</em></td>
<td>95.20</td>
</tr>
<tr>
<td>Kredyt <em>Wydatki</em></td>
<td>80.00</td>
</tr>
<tr>
<td>Kredyt <em>VAT</em></td>
<td>15.20</td>
</tr>
<tr>
<td rowspan='2'>Płatność od odbiorcy</td>
<td rowspan='2'>10 stycznia 2020 r.</td>
<td rowspan='2'>119 USD</td>
<td rowspan='2'>107,10 EUR</td>
<td>Debet <em>Bank</em></td>
<td>107.10</td>
</tr>
<tr>
<td>Kredyt <em>AR</em></td>
<td>107.10</td>
</tr>
<tr>
<td rowspan='3'>Faktura i rozliczenie płatności</td>
<td rowspan='3'>10 stycznia 2020 r.</td>
<td rowspan='3'>0 USD</td>
<td rowspan='3'>11,90 EUR</td>
<td>Debet <em>AR</em></td>
<td>11.90</td>
</tr>
<tr>
<td>Kredyt <em>Różnica kursowa – konto główne</em></td>
<td>10,00</td>
</tr>
<tr>
<td>Kredyt <em>Różnica kursowa – konto księgowania podatku</em></td>
<td>1.90</td>
</tr>
</tbody>
</table>

W tym przykładzie:

- 10.00 (= 11.90 × 80.00 ÷ 95.20) to różnica kursowa powiązana z wartością netto na fakturze.
- 1.90 (= 11.90 – 10.00) to różnica kursowa powiązana z wartością podatku na fakturze.

### <a name="example-2"></a>Przykład 2

Uzupełnij poniższe ustawienia, oprócz ustawień wykonanych dla przykładu 1.

1. Na stronie **Księga** w polu **Kurs wymiany banku** wybierz opcję **Średnia**. Ten kurs będzie używany do obliczania kwot podatku VAT.
2. Umożliwia konfigurowanie kursów wymiany walut dla **Średniego** typu kursu wymiany, co przedstawiono w poniższej tabeli.

    | Data             | USD | EUR | opis         |
    |------------------|-----|-----|---------------------|
    | 1 stycznia 2020 r.  | 100 | 100 | 100 USD za 100 EUR |
    | 10 stycznia 2020 r. | 100 | 110 | 100 USD za 110 EUR |

Zaksięguj poniższe transakcje.

<table>
<thead>
<tr>
<th>Wydruk pokwitowania</th>
<th>Data</th>
<th>Kwota w dolarach USD</th>
<th>Kwota w dolarach EUR</th>
<th>Załącznik</th>
<th>Kwota załącznika</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='5'>Faktura dla odbiorcy</td>
<td rowspan='5'>1 stycznia 2020 r.</td>
<td rowspan='5'>119 USD, która zawiera kwotę podatku VAT 19 USD</td>
<td rowspan='5'>95.20 EUR, która zawiera kwotę podatku VAT 19.00 EUR</td>
<td>Debet <em>AR</em></td>
<td>95.20</td>
</tr>
<tr>
<td>Kredyt <em>Wydatki</em></td>
<td>80.00</td>
</tr>
<tr>
<td>Kredyt <em>VAT</em></td>
<td>15.20</td>
</tr>
<tr>
<td>Debet <em>różnica podatki AR</em></td>
<td>3.80</td>
</tr>
<tr>
<td>Kredyt <em>różnica podatku VAT</em></td>
<td>3.80</td>
</tr>
<tr>
<td rowspan='2'>Płatność od odbiorcy</td>
<td rowspan='2'>10 stycznia 2020 r.</td>
<td rowspan='2'>119 USD</td>
<td rowspan='2'>107,10 EUR</td>
<td>Debet <em>Bank</em></td>
<td>107.10</td>
</tr>
<tr>
<td>Kredyt <em>AR</em></td>
<td>107.10</td>
</tr>
<tr>
<td rowspan='3'>Faktura i rozliczenie płatności</td>
<td rowspan='3'>10 stycznia 2020 r.</td>
<td rowspan='3'>0 USD</td>
<td rowspan='3'>11,90 EUR</td>
<td>Debet <em>AR</em></td>
<td>11.90</td>
</tr>
<tr>
<td>Kredyt <em>Różnica kursowa – konto główne</em></td>
<td>10,00</td>
</tr>
<tr>
<td>Kredyt <em>Różnica kursowa – konto księgowania podatku</em></td>
<td>1.90</td>
</tr>
</tbody>
</table>

W tym przykładzie:

- 10.00 (= 11.90 × 80.00 ÷ 95.20) to różnica kursowa powiązana z wartością netto na fakturze.
- 1.90 (= 11.90 – 10.00) to różnica kursowa powiązana z wartością podatku na fakturze.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
