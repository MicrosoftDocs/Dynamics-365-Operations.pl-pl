---
title: Funkcja interwału łączenia
description: Ten temat zawiera informacje pomocne w wyborze spośród miesięcznych, kwartalnych, półrocznych i rocznych interwałów łączenia.
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
ms.openlocfilehash: 5978abfd4341bbca76ff0211f029097c3d2d785c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971460"
---
# <a name="compounding-interval-functionality"></a>Funkcja interwału łączenia

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ten temat zawiera informacje pomocne w wyborze spośród miesięcznych, kwartalnych, półrocznych i rocznych interwałów łączenia. Funkcja interwału łączenia służy do ustalania liczby okresów łączenia na rok w harmonogramie płatności wynajmu. Każdy z czterech przykładów w tym temacie przedstawia sposób, w jaki harmonogram płatności wynajmu będzie wyglądał z innym interwałem.

Nie można wybrać interwału łączenia, który jest rzadszy niż częstotliwość opłat z tytułu wynajmu. Na przykład kwartalny interwał łączenia nie może być używany z miesięczną częstotliwością opłat, a roczny okres łączenia nie może być używany z półroczną częstotliwością opłat. Wybranie interwału łączenia, który jest rzadszy niż częstotliwość opłat z tytułu wynajmu, skutkuje wyświetleniem komunikatu o błędzie.

> [!NOTE]
> We wszystkich czterech przykładach w tym temacie interwał łączenia jest zgodny z częstotliwością opłat.

## <a name="examples"></a>Przykłady

### <a name="setup-for-all-four-leases"></a>Ustawienia dla wszystkich czterech wynajmów

W poniższych tabelach przedstawiono wartości ustawione na kartach **Ogólne** i **Wiersze harmonogramu płatności** dla czterech wynajmów używanych w przykładach.

**Karta Ogólne**

| Pole                      | Wartość                        |
|----------------------------|------------------------------|
| Krańcowa stopa procentowa | **5%**                       |
| Typ annuity               | **Zwykła annuita**         |
| Interwał łączenia       | Zajrzyj do poszczególnych przykładów. |
| Częstość płatności          | **Miesięczne**                  |
| Data rozpoczęcia          | **1/1/2020**                 |

**Karta Wiersze harmonogramu płatności**

| Pole             | Wartość                        |
|-------------------|------------------------------|
| Rozpoczęcie        | **1/1/2020**                 |
| Okresy           | **120**                      |
| Zakres czasowy   | **Miesiące**                   |
| Data końcowa          | **12/31/2029**               |
| Częstość płatności | Zajrzyj do poszczególnych przykładów. |
| Kwota płatności    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>Wynajem 1: miesięczny interwał łączenia i miesięczna częstotliwość płatności

W poniższej tabeli wyszczególniono pierwsze 12 miesięcy harmonogramu płatności. Warto pamiętać o następujących szczegółach:

- Wartość w kolumnie „Okres” wzrasta o 1 co miesiąc, ponieważ każdy miesiąc jest nowym interwałem łączenia.
- W formule w kolumnie „Wartość bieżąca” stawka jest dzielona przez 12, ponieważ liczba okresów łączenia na rok wynosi 12. Wykładnik (czyli zapis w indeksie górnym) jest równy wartości w kolumnie „Okres”.

| Okres | Miesiąc | Data       | Kwota płatności | Obecna wartość                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 1/31/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>1</sup> = 49 792,53  |
| 2      | 2     | 2/29/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>2</sup> = 49 585,92  |
| 3      | 3     | 3/31/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>3</sup> = 49 380,17  |
| 4      | 4     | 4/30/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>4</sup> = 49 175,28  |
| 5      | 5     | 5/31/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>5</sup> = 48 971,23  |
| 6      | 6     | 6/30/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>6</sup> = 48 768,03  |
| 7      | 7     | 7/31/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>7</sup> = 48 565,67  |
| 8      | 8     | 8/31/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>8</sup> = 48 364,15  |
| 9      | 9     | 9/30/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>9</sup> = 48 163,47  |
| 10     | 10    | 10/31/2020 | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>10</sup> = 47 963,62 |
| 11     | 11    | 11/30/2020 | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>11</sup> = 47 764,61 |
| 12     | 12    | 12/31/2020 | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 12\])<sup>12</sup> = 47 566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>Wynajem 2: kwartalny interwał łączenia i kwartalna częstotliwość płatności

W poniższej tabeli wyszczególniono pierwsze 12 miesięcy harmonogramu płatności. Warto pamiętać o następujących szczegółach:

- Wartość w kolumnie „Okres” wzrasta o 1 co trzy miesiące (czyli co kwartał), ponieważ każdy kwartał jest nowym interwałem łączenia.
- W formule w kolumnie „Wartość bieżąca” stawka jest dzielona przez 4, ponieważ są cztery okresy łączenia na rok. Wykładnik jest równy wartości w kolumnie „Okres”.

| Okres | Miesiąc | Data       | Kwota płatności | Obecna wartość                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 1/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 2/29/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 3/31/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 49 382,72 |
| 2      | 4     | 4/30/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 5/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 6/30/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 48 773,05 |
| 3      | 7     | 7/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 8/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 9/30/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 48 170,92 |
| 4      | 10    | 10/31/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 11/30/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 12/31/2020 | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 47 576,21 |

> [!NOTE]
> Jeśli typ annuity zostanie zmieniony na **Annuita należna**, płatność będzie na początku kwartału, a nie na końcu kwartału.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>Wynajem 3: półroczny interwał łączenia i półroczna częstotliwość płatności

W poniższej tabeli wyszczególniono pierwsze 12 miesięcy harmonogramu płatności. Warto pamiętać o następujących szczegółach:

- Wartość w kolumnie „Okres” wzrasta o 1 co sześć miesięcy (czyli co pół roku), ponieważ każde półrocze jest nowym interwałem łączenia.
- W formule w kolumnie „Wartość bieżąca” stawka jest dzielona przez 2, ponieważ są dwa okresy łączenia na rok. Wykładnik jest równy wartości w kolumnie „Okres”.

| Okres | Miesiąc | Data       | Kwota płatności | Obecna wartość                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 1/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 2/29/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 3/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 4/30/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 5/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 6/30/2020  | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 48 780,49 |
| 2      | 7     | 7/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 8/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 9/30/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 10/31/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 11/30/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 12/31/2020 | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 47 590,72 |

> [!NOTE]
> Jeśli typ annuity zostanie zmieniony na **Annuita należna**, płatność będzie w styczniu i lipcu, a nie czerwcu i grudniu.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>Wynajem 4: roczny interwał łączenia i roczna częstotliwość płatności

W poniższej tabeli wyszczególniono pierwsze 12 miesięcy harmonogramu płatności. Warto pamiętać o następujących szczegółach:

- Wartość w kolumnie „Okres” wzrasta o 1 co 12 miesięcy (czyli co rok), ponieważ każdy rok jest nowym interwałem łączenia.
- W formule w kolumnie „Wartość bieżąca” stawka jest dzielona przez 1, ponieważ jest jeden okres łączenia na rok. Wykładnik jest równy wartości w kolumnie „Okres”.

| Okres | Miesiąc | Data       | Kwota płatności | Obecna wartość                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 1/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 2/29/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 3/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 4/30/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 5/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 6/30/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 7/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 8/31/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 9/30/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 10/31/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 11/30/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 12/31/2020 | 50,000.00      | 50 000 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 47 619,05 |

> [!NOTE]
> Jeśli typ annuity zostanie zmieniony na **Annuita należna**, płatność będzie w styczniu, a nie grudniu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]