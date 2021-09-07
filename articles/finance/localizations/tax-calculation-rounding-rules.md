---
title: Reguły zaokrąglania obliczania podatku
description: Ten temat zawiera informacje dotyczące reguł zaokrąglania w parametrach obliczania podatku usługi obliczania podatku.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 38760879d84d8262cc1e8395c59bcbc0429bc753
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7347692"
---
# <a name="tax-calculation-rounding-rules"></a>Reguły zaokrąglania obliczania podatku

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące sposobu działania reguł zaokrąglania w parametrach obliczania podatku usługi obliczania podatku.

> [!NOTE] 
> Gdy usługa obliczania podatku jest włączona, reguły zaokrąglania na stronach **Kod podatku** i **Grupa podatków** nie skutkują.

Konfigurację reguł zaokrąglania dla usługi obliczania podatku można wyświetlić w sekcji **Reguła zaokrąglania podatku** na skróconej karcie **Obliczanie** na karcie **Ogólne** strony **Parametry obliczania podatku** (**Podatek** \> **Konfiguracja** \> **Konfiguracja podatku** \> **Parametry obliczania podatku**).

[![Konfiguracja reguły zaokrąglania na stronie Parametry obliczania podatku](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

Pola **Precyzja zaokrąglania** i **Metoda zaokrąglania** określają sposób zaokrąglania kwot w ładunku z usługi obliczania podatku.

## <a name="rounding-precision"></a>Dokładność zaokrąglania

Pola **Precyzja zaokrąglania** obsługują wartość do sześciu miejsc dziesiętnych. Jeśli na przykład w polu **Precyzja zaokrąglania** zostanie ustawiona wartość **0,000000**, obliczone kwoty zostaną zaokrąglone do sześciu miejsc dziesiętnych, a następnie wysłane do Microsoft Dynamics 365 Finance. Jeśli na przykład używana jest metoda zaokrąglania **Normalne**, kwota **987,1234567** jest zaokrąglana do **987,123457**.

> [!NOTE]
> W Finance kwoty są zaokrąglane zgodnie z regułami zaokrąglania waluty. Dlatego kwoty podatku wyświetlane i rejestrowane w transakcjach mają wpływ zarówno na reguły zaokrąglania obliczania podatku, jak i reguły zaokrąglania waluty.

## <a name="rounding-method"></a>Metoda zaokrąglania

Metodę zaokrąglania dla obliczania podatku można skonfigurować dla każdej firmy oddzielnie. W polu **Metoda zaokrąglania** można wybrać jedną z trzech opcji: **Normalne**, **W dół** i **Zaokrąglenie w górę**.

### <a name="rounding-example"></a>Przykład zaokrąglania

W poniższej tabeli pokazano przykład zaokrąglania kwoty **987,345** w przypadku różnych kombinacji precyzji zaokrąglania i metody zaokrąglania.

<table>
<thead>
<tr>
<th rowspan="2">Metoda zaokrąglania</th>
<th colspan="8">Dokładność zaokrąglania</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10,00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normalnie</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>W dół</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Zaokrąglenie w górę</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

Logikę obliczania i zaokrąglania kwot podatku można skonfigurować zgodnie z regułami opodatkowania.

## <a name="rounding-by"></a>Zaokrąglanie według 

W polu **Zaokrąglanie według** można wybrać zasadę zaokrąglania stosowaną do podatków. Dostępne są następujące opcje:

- **Kody podatku** — zaokrąglanie kwoty podatku wewnątrz każdego kodu podatku.
- **Kombinacje kodów podatku** — zaokrąglanie kwoty podatku wewnątrz kombinacji kodu podatku w wierszu.

## <a name="calculation-method"></a>Metoda obliczania

W polu **Metoda obliczania** można wybrać, czy podatek na fakturach powinien być obliczany dla każdego wiersza czy dla wszystkich wierszy razem. Dostępne są następujące opcje:

- **Wiersz** — umożliwia obliczanie kwoty podatku wiersz po wierszu. Kwota podatku w każdym wierszu nie ma wpływu na kwotę podatku w innych wierszach.
- **Suma** — umożliwia obliczanie kwoty podatku we wszystkich wierszach jednego dokumentu.

### <a name="rounding-calculation-example"></a>Przykładowe zaokrąglenie obliczania

W tym przykładzie pokazano różne obliczenia, które można wykonać na jednej fakturze z różnymi kombinacjami wartości **Zaokrąglanie według** i **Metoda obliczania**. W tym przykładzie obowiązuje następująca konfiguracja:

- Faktura ma cztery wiersze.
- Istnieją dwa kody podatku: **VAT1** (10%) i **VAT2** (10%).
- Precyzja zaokrąglania to **0,01**.
- Metodą zaokrąglania to **Zaokrąglanie w górę**.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Zaokrąglanie według = Kody podatku i Metoda obliczania = Wiersz

| Numer wiersza | Kwota netto wiersza | Ustalone kody podatku | Kwota podatku przed zaokrągleniem | Zaokrąglona kwota podatku |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2           | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,23         |
| 3           | 33.33           | VAT1                 | 3.333                      | 3.34               |
| 4           | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,45; 4,45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Zaokrąglanie według = Kombinacje kodu podatku i Metoda obliczania = Wiersz

| Numer wiersza | Kwota netto wiersza | Ustalone kody podatku | Kwota podatku przed zaokrągleniem | Zaokrąglona kwota podatku |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,22         |
| 3           | 33.33           | VAT1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,45; 4,44         |

\* Wiersz 2 = Zaokrąglenie\[22,22 × (10% + 10%)\] = 2,23 + 2,22

\*\* Wiersz 4 = Zaokrąglenie\[44,44 × (10% + 10%)\] = 4,45 + 4,44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Zaokrąglanie według = Kody podatku i Metoda obliczania = Suma

| Numer wiersza | Kwota netto wiersza | Ustalone kody podatku | Kwota podatku przed zaokrągleniem | Zaokrąglona kwota podatku |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | VAT1\*; VAT2\*\*     | 2,222; 2,222               | 2,22; 2,23         |
| 3           | 33.33           | VAT1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | VAT1\*; VAT2\*\*     | 4,444; 4,444               | 4,44; 4,44         |

\* VAT1(Wiersz 1, Wiersz 2, Wiersz 3, Wiersz 4) = Zaokrąglenie\[(11,11 + 22,22 + 33,33 + 44,44) × 10%\] = 1,12 + 2,22 + 3,33 + 4,44

\*\* VAT2(Wiersz 2, Wiersz 4) = Zaokrąglenie\[(22,22 + 44,44) × 10%\] = 2,23 + 4,44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Zaokrąglanie według = Kombinacje kodu podatku i Metoda obliczania = Suma

| Numer wiersza | Kwota netto wiersza | Ustalone kody podatku | Kwota podatku przed zaokrągleniem | Zaokrąglona kwota podatku |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,22         |
| 3\*         | 33.33           | VAT1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,44; 4,45         |

\* Wiersz 1, Wiersz 3 = Zaokrąglenie\[(11,11 + 33,33) × 10%\] = 1,12 + 3,33

\*\* Wiersz 2, Wiersz 4 = Zaokrąglenie\[(22,22 + 44,44) × (10% + 10%)\] = 2,23 + 2,22 + 4,44 + 4,45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
