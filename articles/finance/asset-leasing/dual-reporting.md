---
title: Podwójne raportowanie
description: W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6daa43178625316a40427728e7e4186691cc13c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229557"
---
# <a name="dual-reporting"></a>Podwójne raportowanie

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku. Wymagane jest zapoznanie się z warstwami księgowania w Microsoft Dynamics 365 Finance, dzięki czemu przykład będzie łatwiejszy do zrozumienia.

## <a name="example"></a>Przykład

W poniższym przykładzie przedstawiono wynajem podlegający ustawowej włoskiej sprawozdawczości przy użyciu metody kasowej i metody sprawozdawczości MSSF. Firma musi utworzyć trzy księgi, aby uwzględnić zarówno włoskie wymagania ustawowe, jak i wymagania MSSF 16. Jedna księga jest przeznaczona na MSSF 16, jedna na wymagania ustawowe i jedna do automatycznego wycofywania księgowań ustawowych. Księgi są skonfigurowane zgodnie z poniższymi tabelami.

**Księga MSSF 16**

Księga MSSF 16 jest skonfigurowana w taki sposób, aby była zgodna ze standardem księgowania MSSF 16. Wszystkie zapisy zaksięgowane w tej księdze będą księgowane w warstwie niestandardowej.

| Imię i nazwisko                                    | opis    |
|-----------------------------------------|----------------|
| Typ księgi                               | MSSF 16        |
| Opis księgi                        | MSSF 16        |
| Warstwa księgowania                           | Warstwa niestandardowa 1 |
| Typ wynajmu                              | Finance        |
| Struktura księgowania                    | MSSF 16        |
| Konfiguracja okresu / okresu użyteczności wynajmu         | 0,00           |
| Konfiguracja wartości obecnej / wartości godziwej składnika majątku | 0,00           |
| Próg krótkiego terminu                    | 12             |
| Próg niskiej wartości                     | 5,000.00       |
| Płatność dla dostawcy                           | Nr             |

**Księga ustawowa**

Księga ustawowa to księga metody kasowej, w której firma będzie księgować wydatki z tytułu wynajmu jako kwotę gotówki płaconej w każdym miesiącu za wynajem. Ta księga nie będzie generować składnika majątku z prawem do użytkowania ani zobowiązania z tytułu wynajmu.

| Imię i nazwisko                                    | opis |
|-----------------------------------------|-------------|
| Typ księgi                               | Ustawowa   |
| Opis księgi                        | Lokalna GAAP  |
| Warstwa księgowania                           | Bieżące     |
| Typ wynajmu                              | Automatyczna   |
| Struktura księgowania                    | Podstawa gotówki  |
| Konfiguracja okresu / okresu użyteczności wynajmu         | 0,00        |
| Konfiguracja wartości obecnej / wartości godziwej składnika majątku | 0,00        |
| Próg krótkiego terminu                    | 0           |
| Próg niskiej wartości                     | 0           |
| Płatność dla dostawcy                           | Nr          |

**Księga wycofania ustawowego**

Księga wycofania ustawowego jest konfigurowana w taki sam sposób, jak księga ustawowa.

| Imię i nazwisko                                    | opis                    |
|-----------------------------------------|--------------------------------|
| Typ księgi                               | Ustawowe — wycofanie           |
| Opis księgi                        | Księga do cofania księgi ustawowej |
| Warstwa księgowania                           | Warstwa niestandardowa 1                 |
| Typ wynajmu                              | Automatyczna                      |
| Struktura księgowania                    | Podstawa gotówki                     |
| Konfiguracja okresu / okresu użyteczności wynajmu         | 0,00                           |
| Konfiguracja wartości obecnej / wartości godziwej składnika majątku | 0,00                           |
| Próg krótkiego terminu                    | 0                              |
| Próg niskiej wartości                     | 0                              |
| Płatność dla dostawcy                           | Nr                             |

W tym przykładzie utworzono wynajem, który ma następujące ustawienia na kartach **Ogólne** i **Wiersze harmonogramu płatności**.

**Karta Ogólne**

| Pole                      | Wartość            |
|----------------------------|------------------|
| Krańcowa stopa procentowa | 5%               |
| Data rozpoczęcia          | 1/1/2020         |
| Grupa wynajmu                | Budynki        |
| Dostawca                     | 1001             |
| Wartość godziwa składnika majątku    | 245,000          |
| Okres użyteczności składnika majątku          | 120              |
| Typ annuity               | Zwykła annuita |
| Interwał łączenia       | Miesięczne          |

**Karta Wiersze harmonogramu płatności**

| Pole             | Wartość      |
|-------------------|------------|
| Rozpoczęcie        | 1/1/2020   |
| Zakres czasowy   | Miesiące     |
| Okresy           | 24         |
| Data końcowa          | 12/31/2020 |
| Częstość płatności | Miesięczne    |
| Kwota płatności    | 1 000      |

Aby ten wynajem był rozliczany w dwóch strukturach, należy skorzystać z bieżącej warstwy księgowania i niestandardowej warstwy księgowania. W poniższej tabeli przedstawiono przykład każdego wpisu w arkuszu wymaganego do rzetelnego reprezentowania finansów w poszczególnych standardach sprawozdawczości. Szczegółowy opis każdego wpisu w arkuszu za pierwszy miesiąc wynajmu znajduje się dalej.

<table>
<thead>
<tr>
<th rowspan='3'>Numer konta</th>
<th rowspan='3'>opis</th>
<th colspan='3'>Księga ustawowa (bieżąca warstwa)</th>
<th rowspan='3'>Suma bieżącej warstwy</th>
<th>Księga wycofania (niestandardowa warstwa)</th>
<th colspan='4'>Księga MSSF 16 (niestandardowa warstwa)</th>
<th rowspan='3'>Suma Bieżąca warstwa + Niestandardowa warstwa</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Wydatek z tytułu wynajmu</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Opłata bankowa</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Wydatek VAT</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Konto rozliczeniowe</td>
<td>-1000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Rozrachunki z dostawcami</td>
<td></td>
<td>-1008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Składnik majątku z PDU</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Zobowiązanie z tytułu leasingu finansowego</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22 794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21 888,87</td>
</tr>
<tr>
<td>8</td>
<td>Odsetki</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Kasa</td>
<td></td>
<td></td>
<td>-1008,00</td>
<td>-1008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-1008,00</td>
</tr>
<tr>
<td>10</td>
<td>Wydatek amortyzacji</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949.75</td>
<td>949.75</td>
</tr>
<tr>
<td>11</td>
<td>Umorzenie</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Jak widać w powyższych tabelach, wymagane są trzy księgi do raportowania według sprawozdawczości ustawowej i MSSF.

- W księdze ustawowej jest rejestrowana opłata z tytułu wynajmu zgodnie z regułami księgowania w metodzie kasowej w bieżącej warstwie.
- Księga wycofania ustawowego wycofuje ustawowe wpisy w arkuszu.
- Księga MSSF 16 tworzy wpisy w arkuszu wymagane na mocy MSSF 16.

Wynajem musi zostać wprowadzony tylko raz. Następnie można otworzyć stronę **Księgi** w celu wyświetlenia wszystkich ksiąg skojarzonych z wynajmem.

> [!NOTE]
> Po utworzeniu ksiąg wszystkie trzy z nich muszą być skojarzone z tym samym rekordem wynajmu.

Pierwszy wpis w arkuszu rejestruje wydatek z tytułu wynajmu w księdze ustawowej. Płatności można tworzyć w ramach partii lub wybierając harmonogram płatności w księdze ustawowej.

W tym przykładzie dla księgi ustawowej jest tworzony następujący wpis w arkuszu z harmonogramu płatności.

### <a name="lease-payment--1312020--je-100"></a>Opłata z tytułu wynajmu — 1/31/2020 — JE 100

| Typ konta | Numer konta | Warstwa   | Opis konta | Uznanie    | Strona kredytowa   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 1              | Bieżące | Wydatek z tytułu wynajmu       | 1,000.00 |          |
| Ledger       | 4              | Bieżące | Konto rozliczeniowe    |          | 1,000.00 |

Pracownik ds. rozrachunków z dostawcami korzysta ze standardowych funkcji systemu Dynamics 365, aby utworzyć fakturę do zapłacenia za wynajem poza wynajmem składnika majątku. Jednak zamiast wybierania **Wydatek z tytułu wynajmu** jako konta debetowego pracownik ds. rozrachunków z dostawcami wybiera konto rozliczeniowe w celu wygenerowania poniższego wpisu.

### <a name="ap-process--1312020--je-110"></a>Proces AP — 1/31/2020 — JE 110

| Typ konta | Numer konta | Warstwa   | Opis konta | Uznanie    | Strona kredytowa   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 4              | Bieżące | Konto rozliczeniowe    | 1,000.00 |          |
| Ledger       | 2              | Bieżące | Opłata bankowa            | 3.00     |          |
| Ledger       | 3              | Bieżące | Wydatek VAT         | 5.00     |          |
| Dostawca       | 5              | Bieżące | Rozrachunki z dostawcami    |          | 1,008.00 |

Gdy dostawcy jest udzielana instrukcja, należy postępować zgodnie z regularnym procesem płatności. Podczas tego procesu jest generowany następujący wpis w arkuszu.

### <a name="cash-payment--1312020--je-120"></a>Płatność gotówkowa — 1/31/2020 — JE 120

| Typ konta | Numer konta | Warstwa   | Opis konta | Uznanie    | Strona kredytowa   |
|--------------|----------------|---------|---------------------|----------|----------|
| Dostawca       | 5              | Bieżące | Rozrachunki z dostawcami    | 1,008.00 |          |
| Bank         | 9              | Bieżące | Kasa                |          | 1,008.00 |

Na tym etapie wynajem jest w pełni zaksięgowany zgodnie z ustawowymi wymogami sprawozdawczości i można wygenerować bilans próbny, korzystając z bieżącej warstwy. System zwraca bilans próbny o następujących wartościach:

<table>
<thead>
<tr>
<th rowspan='3'>Numer konta</th>
<th rowspan='3'>opis</th>
<th colspan='3'>Księga ustawowa (bieżąca warstwa)</th>
<th rowspan='3'>Suma bieżącej warstwy</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Wydatek z tytułu wynajmu</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Opłata bankowa</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Wydatek VAT</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Konto rozliczeniowe</td>
<td>-1000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Rozrachunki z dostawcami</td>
<td></td>
<td>-1008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Składnik majątku z PDU</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Zobowiązanie z tytułu leasingu finansowego</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Odsetki</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Kasa</td>
<td></td>
<td></td>
<td>-1008,00</td>
<td>-1008,00</td>
</tr>
<tr>
<td>10</td>
<td>Wydatek amortyzacji</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Umorzenie</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Jeśli ten sam bilans próbny ma zostać wykonany na wartościach MSSF 16, należy wycofać wpisy w arkuszu księgowania ustawowego i zaksięgować wpisy w arkuszu MSSF 16. Aby wycofać ustawowe wpisy w arkuszu, w tym przykładzie jest zawarta księga wycofania ustawowego, która ma taką samą konfigurację jak księga ustawowa, ale przeciwny profil księgowania. Na przykład księga ustawowa *obciąża* konto wydatku z tytułu wynajmu, a księga wycofania *uznaje* to konto. Relacje te są łatwe do zdefiniowania na kontach księgowania wynajmu składników majątku na stronie **Parametry wynajmu składników majątku** (**Wynajem składników majątku \> Ustawienia \> Parametry wynajmu składników majątku**).

Jeśli ten sam proces, który był używany dla księgi ustawowej, zostanie użyty w księdze wycofania, tworzony jest następujący wpis w arkuszu. Różnica polega na tym, że księga wycofania księguje zapisy wycofania z księgi ustawowej. Wpisy wycofania są również wprowadzane do niestandardowej warstwy. Jeśli bilans próbny zostanie wykonany na bieżącej warstwie, wycofujące wpisy w arkuszu nie będą uwzględniane.

### <a name="lease-payment--1312020--je-130"></a>Opłata z tytułu wynajmu — 1/31/2020 — JE 130

| Typ konta | Numer konta | Warstwa  | Opis konta | Uznanie    | Strona kredytowa   |
|--------------|----------------|--------|---------------------|----------|----------|
| Ledger       | 4              | Niestandardowe | Konto rozliczeniowe    | 1,000.00 |          |
| Ledger       | 1              | Niestandardowe | Wydatek z tytułu wynajmu       |          | 1,000.00 |

Po usunięciu ustawowych wpisów w arkuszu księgujesz w księdze MSSF 16 wszystkie wpisy w dzienniku, których wymaga MSSF 16. Do tych wpisów należą początkowe uznanie składnika majątku z PDU i zobowiązanie, a także rekord odsetek i amortyzacji.

### <a name="initial-recognition--112020--je-140"></a>Początkowe uznanie — 1/1/2020 — JE 140

| Typ konta | Numer konta | Warstwa  | Opis konta      | Uznanie     | Strona kredytowa    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Ledger       | 6              | Niestandardowe | Składnik majątku z PDU                | 22,793.90 |           |
| Ledger       | 7              | Niestandardowe | Zobowiązanie z tytułu leasingu finansowego |           | 22,793.90 |

Opłata z tytułu wynajmu jest księgowana jak inne opłaty z tytułu wynajmu. Przyczyną użycia konta rozliczeniowego jest zapewnienie, aby gotówka była uznawana tylko jeden raz.

### <a name="lease-payment--1312020--je-150"></a>Opłata z tytułu wynajmu — 1/31/2020 — JE 150

| Typ konta | Numer konta | Warstwa  | Opis konta      | Uznanie    | Strona kredytowa   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Ledger       | 7              | Niestandardowe | Zobowiązanie z tytułu leasingu finansowego | 1,000.00 |          |
| Ledger       | 4              | Niestandardowe | Konto rozliczeniowe         |          | 1,000.00 |

Wpis w arkuszu kosztu odsetek jest generowany na podstawie harmonogramu amortyzacji zobowiązań.

### <a name="interest-expense--1312020--je-160"></a>Koszt odsetek — 1/31/2020 — JE 160

| Typ konta | Numer konta | Warstwa  | Opis konta      | Uznanie | Strona kredytowa |
|--------------|----------------|--------|--------------------------|-------|--------|
| Ledger       | 8              | Niestandardowe | Odsetki         | 94.97 |        |
| Ledger       | 7              | Niestandardowe | Zobowiązanie z tytułu leasingu finansowego |       | 94.97  |

Wpis w arkuszu kosztu amortyzacji jest generowany na podstawie harmonogramu amortyzacji składnika majątku.

### <a name="depreciation-expense--1312020--je-170"></a>Wydatek amortyzacji — 1/31/2020 — JE 170

| Typ konta | Numer konta | Warstwa  | Opis konta      | Uznanie  | Strona kredytowa |
|--------------|----------------|--------|--------------------------|--------|--------|
| Ledger       | 10             | Niestandardowe | Wydatek amortyzacji     | 949.75 |        |
| Ledger       | 11             | Niestandardowe | Umorzenie |        | 949.75 |

Po utworzeniu i zaksięgowaniu wszystkich tych wpisów w arkuszu będą widoczne następujące wartości „niestandardowej warstwy 1”. Należy zauważyć, że ostatnia kolumna zawiera opłatę bankową, koszt VAT oraz zmniejszenie ilości gotówki z poprzedniej warstwy, ale nie zawiera wpisów w arkuszu sprawozdawczości ustawowej. Pozwala to na osiągnięcie prawdziwych możliwości podwójnego raportowania. W tym momencie firma ma możliwość uruchomienia bilansu próbnego i połączenia bieżącej warstwy z niestandardową warstwą w celu utworzenia bilansu próbnego według MSSF.

| Nr konta | opis              | Księga ustawowa\-bieżąca warstwa\-JE\-100\-Dr \(Cr\) | Księga ustawowa\-bieżąca warstwa\-JE\-110\-Dr \(Cr\) | Księga ustawowa\-bieżąca warstwa\-JE\-120\-Dr \(Cr\) | Bieżąca warstwa \- sumy | - | Księga wycofania\-niestandardowa warstwa\-JE\-130\-Dr \(Cr\) | Księga MSSF 16\-niestandardowa warstwa\-JE\-140\-Dr \(Cr\) | Księga MSSF 16\-niestandardowa warstwa\-JE\-150\-Dr \(Cr\) | Księga MSSF 16\-niestandardowa warstwa\-JE\-160\-Dr \(Cr\) | Księga MSSF 16\-niestandardowa warstwa\-JE\-170\-Dr \(Cr\) | Bieżąca warstwa \+ niestandardowa warstwa \- sumy |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Wydatek z tytułu wynajmu            | 1,000\.00                                         |                                                   |                                                   | 1,000\.00               |   | \-1000                                         |                                                |                                                |                                                |                                                | 0\.00                                   |
| 2          | Opłata bankowa                 |                                                   | 3\.00                                             |                                                   | 3\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\.00                                   |
| 3          | Wydatek VAT              |                                                   | 5\.00                                             |                                                   | 5\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\.00                                   |
| 4          | Konto rozliczeniowe         | \-1000\.00                                       | 1,000\.00                                         |                                                   | 0\.00                   |   | 1 000                                           |                                                | \-1000                                        |                                                |                                                | 0\.00                                   |
| 5          | Rozrachunki z dostawcami         |                                                   | \-1008\.00                                       | 1,008\.00                                         | 0\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\.00                                   |
| 6          | Składnik majątku z PDU                |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | 22,794                                         |                                                |                                                |                                                | 22,793\.90                              |
| 7          | Zobowiązanie z tytułu leasingu finansowego |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | \-22 794                                       | 1 000                                          | \-94\.97                                       |                                                | \-21 888\.87                            |
| 8          | Odsetki         |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                | 94\.97                                         |                                                | 94\.97                                  |
| 9          | Kasa                     |                                                   |                                                   | \-1008\.00                                       | \-1008\.00             |   |                                                 |                                                |                                                |                                                |                                                | \-1008\.00                             |
| 10         | Wydatek amortyzacji     |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | 949\.75                                        | 949\.75                                 |
| 11         | Umorzenie |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | \-949\.75                                      | \-949\.75                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]