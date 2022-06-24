---
title: Reguły zaokrąglania i obliczania podatku
description: Ten artykuł zawiera omówienie obliczeń i zaokrąglania podatku oraz objaśnienie parametrów konfiguracji obliczania i zaokrąglania podatku.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939241"
---
# <a name="sales-tax-calculation-and-rounding"></a>Reguły zaokrąglania i obliczania podatku

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie obliczania i zaokrąglania podatku w aplikacji Microsoft Dynamics 365 Finance. Opisano w nim także parametry stosowane w konfiguracji obliczania i zaokrąglania podatku oraz sposób ich działania.

## <a name="parameters"></a>Parametry

Kilka parametrów steruje obliczaniem podatku i jego zaokrąglaniem:

- **Metoda obliczania** — ten parametr jest ustawiany stronie na **Parametry księgi głównej** i definiuje, czy kwota podstawy podatku jest obliczana dla dokumentu, czy dla wiersza. Jeśli parametr **Podstawa limitu** dla kodu podatku jest ustawiona na **Kwota netto faktury**, kwota podstawy podatku jest zawsze obliczana dla każdego dokumentu, niezależnie od ustawienia tego parametru.
- **Zaokrąglanie według** — ten parametr jest ustawiany dla grupy podatków i określa, czy kwota podatku jest zaokrąglana według kodu podatku czy dla kombinacji kodów podatków.
- **Źródło** — ten parametr jest ustawiany dla kodu podatku i definiuje sposób obliczania kwoty podatku. Aby uzyskać więcej informacji, zobacz [Wybieranie metody obliczania podatku w polu Źródło](sales-tax-calculation-methods-origin-field.md).
- **Podstawa limitu** — ten parametr jest ustawiany dla kodu podatku i określa, która kwota służy do wybierania odpowiednich stawek podatkowych na stronie **Wartości kodu podatku**. Aby uzyskać więcej informacji, zobacz [Stawki podatku na podstawie pól Podstawa limitu i Metody obliczania](marginal-base-field.md).
- **Reguła zaokrąglania podatku** — ten parametr jest ustawiany dla kodu podatku i definiuje sposób zaokrąglania ustalonej kwoty podatku, z uwzględnieniem dokładności zaokrąglania i metody zaokrąglania.

W pozostałej części tego artykułu przedstawiono kilka typowych przykładów obliczania podatku i zaokrąglania, w których jest używana kombinacja opisanych wcześniej parametrów.

## <a name="scenario-for-the-examples"></a>Scenariusz dla przykładów

- W dokumencie podlegającym opodatkowaniu znajdują się dwa wiersze, a kwota podstawy podatku dla każdego wiersza to 42,42.
- Dla każdego wiersza są zdefiniowane dwa kody podatków: kod podatku 1 i kod podatku 2.
- Stawka podatku dla kodu podatku 1 i kodu podatku 2 wynosi 10 procent.
- Cena nie uwzględnia podatku.
- Dokładność zaokrąglania to 0,01.
- Metoda zaokrąglania to **Zaokrąglanie w górę**.

## <a name="example-1"></a>Przykład 1

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według    | Pochodzenie                   | Podstawa limitu       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Wiersz               | Kod podatku | Procent od kwoty netto | Kwota netto na wiersz |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ------------| ---------------| --------------| -----------------|
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.25             |
| 2           | Kod 1         | 42.42         | 4.25             |
| 2           | Kod 2         | 42.42         | 4.25             |

Kwota podstawy podatku jest obliczana dla poszczególnych wierszy:

- **Wiersz 1:** 42,42
- **Wiersz 2:** 42,42

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- **Wiersz 1:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent = 4,242
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent = 4,242

- **Wiersz 2:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent = 4,242
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent = 4,242

Kwota podatku jest zaokrąglana dla poszczególnych kodów podatku:

- **Wiersz 1:**

    - Zaokrąglona kwota podatku dla kodu podatku 1 = 4,25
    - Zaokrąglona kwota podatku dla kodu podatku 2 = 4,25

- **Wiersz 2:**

    - Zaokrąglona kwota podatku dla kodu podatku 1 = 4,25
    - Zaokrąglona kwota podatku dla kodu podatku 2 = 4,25

## <a name="example-2"></a>Przykład 2

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według    | Pochodzenie                   | Podstawa limitu                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Wiersz/suma         | Kod podatku | Procent od kwoty netto | Kwota netto faktury |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.25             |
| 2           | Kod 1         | 42.42         | 4.24             |
| 2           | Kod 2         | 42.42         | 4.24             |

Kwota podstawy podatku jest obliczana dla poszczególnych dokumentów:

- Kwota podstawy podatku = 42,42 + 42,42 = 84,84

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- Kwota podatku dla kodu podatku 1 = 84,84 &times; 10 procent = 8,484
- Kwota podatku dla kodu podatku 2 = 84,84 &times; 10 procent = 8,484

Kwota podatku jest zaokrąglana dla poszczególnych kodów podatku:

- Zaokrąglona kwota podatku dla kodu podatku 1 = 8,49
- Zaokrąglona kwota podatku dla kodu podatku 2 = 8,49

Zaokrąglona kwota podatku jest przydzielana do każdego wiersza dla poszczególnych kodów podatku:

- Przydziel zaokrągloną kwotę podatku dla kodu podatku 1 (8,49) do wiersza 1 (4,25) i wiersza 2 (4,24).
- Przydziel zaokrągloną kwotę podatku dla kodu podatku 2 (8,49) do wiersza 1 (4,25) i wiersza 2 (4,24).

## <a name="example-3"></a>Przykład 3

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według    | Pochodzenie                              | Podstawa limitu       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Wiersz               | Kod podatku | Obliczony procent kwoty netto | Kwota netto na wiersz |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.72             |
| 2           | Kod 1         | 42.42         | 4.72             |
| 2           | Kod 2         | 42.42         | 4.72             |

Kwota podstawy podatku jest obliczana dla poszczególnych wierszy:

- **Wiersz 1:** 42,42
- **Wiersz 2:** 42,42

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- **Wiersz 1:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

- **Wiersz 2:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

Kwota podatku jest zaokrąglana dla poszczególnych kodów podatku:

- **Wiersz 1:**

    - Zaokrąglona kwota podatku dla kodu podatku 1 = 4,72
    - Zaokrąglona kwota podatku dla kodu podatku 2 = 4,72

- **Wiersz 2:**

    - Zaokrąglona kwota podatku dla kodu podatku 1 = 4,72
    - Zaokrąglona kwota podatku dla kodu podatku 2 = 4,72

## <a name="example-4"></a>Przykład 4

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według    | Pochodzenie                              | Podstawa limitu                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Wiersz/suma         | Kod podatku | Obliczony procent kwoty netto | Kwota netto faktury |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.72             |
| 2           | Kod 1         | 42.42         | 4.71             |
| 2           | Kod 2         | 42.42         | 4.71             |

Kwota podstawy podatku jest obliczana dla poszczególnych dokumentów:

- Kwota podstawy podatku = 42,42 + 42,42 = 84,84

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- Kwota podatku dla kodu podatku 1 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267
- Kwota podatku dla kodu podatku 2 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267

Kwota podatku jest zaokrąglana dla poszczególnych kodów podatku:

- Zaokrąglona kwota podatku dla kodu podatku 1 = 9,43
- Zaokrąglona kwota podatku dla kodu podatku 2 = 9,43

Zaokrąglona kwota podatku jest przydzielana do każdego wiersza dla poszczególnych kodów podatku:

- Przydziel kwotę podatku dla kodu podatku 1 (9,43) do wiersza 1 (4,72) i wiersza 2 (4,71).
- Przydziel kwotę podatku dla kodu podatku 2 (9,43) do wiersza 1 (4,72) i wiersza 2 (4,71).

## <a name="example-5"></a>Przykład 5

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według                | Pochodzenie                   | Podstawa limitu       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Wiersz               | Kombinacje kodów podatku | Procent od kwoty netto | Kwota netto na wiersz |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.24             |
| 2           | Kod 1         | 42.42         | 4.24             |
| 2           | Kod 2         | 42.42         | 4.24             |

Kwota podstawy podatku jest obliczana dla poszczególnych wierszy:

- **Wiersz 1:** 42,42
- **Wiersz 2:** 42,42

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- **Wiersz 1:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent = 4,242
    - kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent = 4,242

- **Wiersz 2:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent = 4,242
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent = 4,242

Kwota podatku jest zaokrąglana dla poszczególnych kombinacji kodów podatku:

- Łączna kwota podatku = 4,242 + 4,242 + 4,242 + 4,242 = 16,968; ta wartość jest zaokrąglana w górę do 16,97

Zaokrąglona kwota podatku jest przydzielana do każdego wiersza dla poszczególnych kodów podatku:

- Przydziel kwotę podatku (16,97) do wiersza 1 i wiersza 2:

    - **Wiersz 1:**

        - Kwota podatku dla kodu podatku 1 = 4,25
        - Kwota podatku dla kodu podatku 2 = 4,24

    - **Wiersz 2:**

        - Kwota podatku dla kodu podatku 1 = 4,24
        - Kwota podatku dla kodu podatku 2 = 4,24

## <a name="example-6"></a>Przykład 6

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według                | Pochodzenie                   | Podstawa limitu                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Wiersz/suma         | Kombinacje kodów podatku | Procent od kwoty netto | Kwota netto faktury |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.24             |
| 2           | Kod 1         | 42.42         | 4.24             |
| 2           | Kod 2         | 42.42         | 4.24             |

Kwota podstawy podatku jest obliczana dla poszczególnych dokumentów:

- Kwota podstawy podatku = 42,42 + 42,42 = 84,84

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- Kwota podatku dla kodu podatku 1 = 84,84 &times; 10 procent = 8,484
- Kwota podatku dla kodu podatku 2 = 84,84 &times; 10 procent = 8,484

Kwota podatku jest zaokrąglana dla poszczególnych kombinacji kodów podatku:

- Łączna kwota podatku = 8,484 + 8,484 = 16,968; ta wartość jest zaokrąglana w górę do 16,97

Zaokrąglona kwota podatku jest przydzielana do każdego wiersza dla poszczególnych kodów podatku:

- Przydziel kwotę podatku (16,97) do wiersza 1 i wiersza 2:

    - **Wiersz 1:**

        - Kwota podatku dla kodu podatku 1 = 4,25
        - Kwota podatku dla kodu podatku 2 = 4,24

    - **Wiersz 2:**

        - Kwota podatku dla kodu podatku 1 = 4,24
        - Kwota podatku dla kodu podatku 2 = 4,24

## <a name="example-7"></a>Przykład 7

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według                | Pochodzenie                              | Podstawa limitu       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Wiersz               | Kombinacje kodów podatku | Obliczony procent kwoty netto | Kwota netto na wiersz |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.71             |
| 2           | Kod 1         | 42.42         | 4.71             |
| 2           | Kod 2         | 42.42         | 4.72             |

Kwota podstawy podatku jest obliczana dla poszczególnych wierszy:

- **Wiersz 1:** 42,42
- **Wiersz 2:** 42,42

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- **Wiersz 1:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

- **Wiersz 2:**

    - Kwota podatku dla kodu podatku 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Kwota podatku dla kodu podatku 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

Kwota podatku jest zaokrąglana dla poszczególnych kombinacji kodów podatku:

- Łączna kwota podatku = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532; ta wartość jest zaokrąglana w górę do 18,86

Zaokrąglona kwota podatku jest przydzielana do każdego wiersza dla poszczególnych kodów podatku:

- Przydziel kwotę podatku (18,86) do wiersza 1 i wiersza 2:

    - **Wiersz 1:**

        - Kwota podatku dla kodu podatku 1 = 4,72
        - Kwota podatku dla kodu podatku 2 = 4,71

    - **Wiersz 2:**

        - Kwota podatku dla kodu podatku 1 = 4,71
        - Kwota podatku dla kodu podatku 2 = 4,72

## <a name="example-8"></a>Przykład 8

### <a name="parameter-values"></a>Wartości parametrów

| Metoda obliczeń | Zaokrąglanie według                | Pochodzenie                              | Podstawa limitu                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Wiersz/suma         | Kombinacje kodów podatku | Obliczony procent kwoty netto | Kwota netto faktury |

### <a name="calculation-and-rounding-behavior"></a>Zachowanie funkcji obliczania i zaokrąglania

| Numer wiersza | Kod podatku | Źródło kwoty | Kwota podatku |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.71             |
| 2           | Kod 1         | 42.42         | 4.71             |
| 2           | Kod 2         | 42.42         | 4.72             |

Kwota podstawy podatku jest obliczana dla poszczególnych dokumentów:

- Kwota podstawy podatku = 42,42 + 42,42 = 84,84

Kwota podatku jest obliczana dla poszczególnych kodów podatku:

- Kwota podatku dla kodu podatku 1 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267
- Kwota podatku dla kodu podatku 2 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267

Kwota podatku jest zaokrąglana dla poszczególnych kombinacji kodów podatku:

- Łączna kwota podatku = 9,4267 + 9,4267 = 18,8534; ta wartość jest zaokrąglana w górę do 18,86

Zaokrąglona kwota podatku jest przydzielana do każdego wiersza dla poszczególnych kodów podatku:

- Przydziel kwotę podatku (18,86) do wiersza 1 i wiersza 2:

    - **Wiersz 1:**

        - Kwota podatku dla kodu podatku 1 = 4,72
        - Kwota podatku dla kodu podatku 2 = 4,71

    - **Wiersz 2:**

        - Kwota podatku dla kodu podatku 1 = 4,71
        - Kwota podatku dla kodu podatku 2 = 4,72

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Wybieranie metody obliczania podatku w polu Źródło](sales-tax-calculation-methods-origin-field.md)
- [Stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania](marginal-base-field.md)
- [Opcje Cała kwota i Obliczanie interwału dla kodów podatku](whole-amount-interval-options-sales-tax-codes.md)
