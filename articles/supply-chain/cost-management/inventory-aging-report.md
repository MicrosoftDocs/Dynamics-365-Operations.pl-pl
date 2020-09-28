---
title: Przykłady i logika raportu wiekowania zapasów
description: W tym temacie przedstawiono przykłady przedstawiające sposób interpretacji wyników raportu wiekowania zapasów.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759551"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Przykłady i logika raportu wiekowania zapasów

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono przykłady przedstawiające sposób interpretacji wyników raportu **Wiekowania zapasów**. Ten raport umożliwia kategoryzowanie dostępnych ilości i wartości zapasów dla wybranego towaru lub grupy towarów do kilku przedziałów okresów. W tym temacie przedstawiono również wewnętrzną logikę raportu.

W przykładach w tym temacie przedstawiono wyniki prezentowane w standardowym raporcie **Wiekowania zapasów**. Zasadniczo zalecamy jednak korzystanie z wersji [raportu przechowywania raportu o starzeniu się zapasów](inventory-aging-report-storage.md), zwłaszcza gdy masz wiele produktów i magazynów, które muszą zostać przetworzone. Przechowywanie raportów wiekowania zapasów powoduje zapisanie wszystkich generowanych raportów, wyświetlenie wyników w postaci strony interakcyjnej i wykresu oraz umożliwia wyeksportowanie dowolnego zapisanego raportu.

## <a name="sample-data-that-is-used-in-these-examples"></a>Przykładowe dane używane w tych przykładach

Przykłady przedstawione w tym temacie są oparte na przykładowych danych transakcji magazynowych opisanych w tej sekcji.

### <a name="storage-dimension-setup"></a>Konfiguracja wymiarów magazynowania

Przykładowy system zawiera następujące ustawienia wymiarów magazynowania:

| Imię i nazwisko      | Aktywna | Magazyn | Magazyn finansowy |
|-----------|--------|--------------------|---------------------|
| Oddział      | Tak    | Tak                | Tak                 |
| Magazyn | Tak    | Tak                | Nr                  |

### <a name="inventory-model"></a>Model magazynu

W przypadku systemu przykładowego model magazynu dla zwolnionych produktów to *FIFO*, a ustawienie **Koszt własny** dla modelu magazynu to *Włączanie wartości fizycznej*.

### <a name="inventory-transactions"></a>Transakcje zapasów

Przykładowy system zawiera następujące transakcje magazynowe dla zwolnionego produktu o numerze towaru *1000*.

| Odwołanie      | Oddział | Magazyn | Przychód   | Wystawienie | Data fizycznej transakcji | Data finansowa | Ilość | Kwota kosztu | Fizyczna wartość kosztu |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Zamówienie zakupu | 1    | 11        | Zakupione |       | 15 marca      | 15 marca       | 10       | 1 000       | 1 000                |
| Zamówienie zakupu | 2    | 21        | Zakupione |       | 15 marca      | 15 marca       | 10       | 2,000       | 2,000                |
| Zamówienie zakupu | 1    | 11        | Odebrane  |       | 15 kwietnia      |                | 5        |             | 375                  |
| Zamówienie przeniesienia | 1    | 11        |           | Sprzedane  | 2 maja         | 2 maja          | -5       | -458,33     | -458,33              |
| Zamówienie przeniesienia | 1    | 12        | Zakupione |       | 2 maja         | 2 maja          | 5        | 458.33      | 458.33               |
| Zamówienie sprzedaży    | 1    | 12        |           | Sprzedane  | 3 maja         | 3 maja          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Sposób obliczania ilości i kwot w każdym przedziale okresów

Korzystając z przykładowych danych opisanych w poprzednich sekcjach, można uruchomić raport **Wiekowania zapasów**, który ma następujące ustawienia:

- **Data:** *9 maj 2020*
- **Oddział:** *Widok*
- **Magazyn:** *Nie*
- **Kod pozycji:** *Razem*
- **Okres wiekowania:** należy uzupełnić to pole, aby były generowane pakiety miesięczne.

W takim przypadku zawartość generowanego raportu będzie podobna do poniższego przykładu.

<table>
<thead>
<tr>
    <th rowspan="2">Identyfikator pozycji</th>
    <th rowspan="2">Oddział</th>
    <th rowspan="2">Ilość dostępnych zapasów</th>
    <th rowspan="2">Dostępna wartość</th>
    <th rowspan="2">Ilość wartości zapasów</th>
    <th rowspan="2">Wartość zapasów</th>
    <th rowspan="2">Średni koszt jednostkowy</th>
    <th colspan="2">8/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 - 1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1:Ilość</th>
    <th>P1:Kwota</th>
    <th>P2:Ilość</th>
    <th>P2:Kwota</th>
    <th>P3:Ilość</th>
    <th>P3:Kwota</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 Razem</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

W tym przykładzie przedstawiono następujące szczegóły:

- Wartości **Ilość wartości zapasów**, **Wartość zapasów** oraz **Średnie koszty jednostkowe**, które są wyświetlane w raporcie, są wartościami dla wymiaru magazynu finansowego (w tym przypadku **Oddział**).

    Na przykład w przypadku oddziału 1 raport zawiera następujące informacje:

    - Wartość **Ilość wartości zapasów** wynosi *14* (= 10 + 5 – 5 + 5 – 1).
    - Wartość **Wartość zapasów** wynosi *1283,33* (= 1000 + 375 – 458,33 + 458,33 – 91,67).
    - Wartość **Średni koszt jednostkowy** wynosi *91,67*.
    - Wartość **Dostępna wartość** oraz wartość **Kwota** w każdym przedziale okresu są obliczane przy użyciu wartości **Średni koszt jednostkowy**.

- Raport określa ilość zapasów dla każdego przedziału okresu, sumując łączną ilość zapasów dla każdego przedziału okresu. Następnie stosuje regułę FIFO (First on) do odliczenia łącznej wydanej ilości, niezależnie od modelu magazynu, który jest używany przez towary.

Jeśli ten sam raport zostanie uruchomiony ponownie, ale tym razem ustaw pole **Oddział** i **Magazyn** na *Wyświetlanie*, nowy raport będzie wyglądał następująco.

<table>
<thead>
<tr>
    <th rowspan="2">Identyfikator pozycji</th>
    <th rowspan="2">Oddział</th>
    <th rowspan="2">Magazyn</th>
    <th rowspan="2">Ilość dostępnych zapasów</th>
    <th rowspan="2">Dostępna wartość</th>
    <th rowspan="2">Ilość wartości zapasów</th>
    <th rowspan="2">Wartość zapasów</th>
    <th rowspan="2">Średni koszt jednostkowy</th>
    <th colspan="2">8/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 - 1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1:Ilość</th>
    <th>P1:Kwota</th>
    <th>P2:Ilość</th>
    <th>P2:Kwota</th>
    <th>P3:Ilość</th>
    <th>P3:Kwota</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 Razem</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

W tym momencie oddział 1 dzieli się na dwa wiersze, jeden dla magazynu 11 i drugi dla magazynu 12. Jednak wartości **Ilość wartości zapasów**, **Wartość zapasów** oraz **Średnie koszty jednostkowe** są takie same, ponieważ **Magazyn** nie jest finansowym wymiarem magazynowym.

Ponadto należy zauważyć, że dystrybucja ilości oddziału 1 jest inna. W pierwszym uruchomionym raporcie system zignorował zamówienie przeniesienia, które miało miejsce w tym samym oddziale, i odznaczył ilość na fakturze sprzedaży z przedziału czasu **31/3/2020-1/3/2020** w oddziale 1. Jednak w nowym raporcie system odliczy ilość z faktury sprzedaży z przedziału czasu **8/5/2020-1/5/2020** w magazynie 12.

## <a name="effects-of-inventory-closing"></a>Skutki zamknięcia zapasów

W przypadku uruchomienia operacji zamykania magazynu w systemie można ponownie uruchomić poprzedni raport, ale w polu **Na dzień** zostanie ustawiona wartość *31 maja 2020*, zostaną przedstawione następujące wyniki:

- Wartości w polach **Wartość zapasów** i **Średni koszt jednostkowy** są aktualizowane.
- Wartość **Dostępna wartość** i wszystkie wartości **Kwota** w każdym przedziale okresu są odpowiednio aktualizowane.

Nowy raport będzie przypominał następujący przykład.

<table>
<thead>
<tr>
    <th rowspan="2">Identyfikator pozycji</th>
    <th rowspan="2">Oddział</th>
    <th rowspan="2">Magazyn</th>
    <th rowspan="2">Ilość dostępnych zapasów</th>
    <th rowspan="2">Dostępna wartość</th>
    <th rowspan="2">Ilość wartości zapasów</th>
    <th rowspan="2">Wartość zapasów</th>
    <th rowspan="2">Średni koszt jednostkowy</th>
    <th colspan="2">31/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 - 1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1:Ilość</th>
    <th>P1:Kwota</th>
    <th>P2:Ilość</th>
    <th>P2:Kwota</th>
    <th>P3:Ilość</th>
    <th>P3:Kwota</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 Razem</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>
