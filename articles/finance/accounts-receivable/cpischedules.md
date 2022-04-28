---
title: Harmonogram indeksu ceny konsumenta
description: W tym temacie wyjaśniono, jak tworzyć listę harmonogramów indeksu cen klientów (CPI) uzyskiwanych przez Internet w celu ustalenia opłaty eskalacji w fakturowaniu subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 2a69e58095844286878e27a100fa49a44a4a71f4
ms.sourcegitcommit: 4d7bc52e6cdf6afce3793893ba2aa07176302314
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560486"
---
# <a name="consumer-price-index-schedule"></a>Harmonogram indeksu ceny konsumenta

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia, usuwania, przeglądania i przetwarzania harmonogramów indeksów cen klientów (CPI). Harmonogram CPI może być używany do określania cen towarów i usług konsumpcyjnych, które są dodawane jako linie harmonogramu rozliczeniowego. Harmonogram CPI można następnie wykorzystać z cenami eskalacyjnymi i rabatowymi w harmonogramie rozliczeniowym lub można go przetwarzać ręcznie w celu aktualizacji kwot rozliczeniowych w harmonogramach rozliczeniowych. Harmonogramy CPI można wprowadzać ręcznie lub importować je za pomocą elementu złożonego Harmonogram CPI.

Aby dodać harmonogram CPI, wykonaj poniższe czynności.

1. Na stronie **Harmonogram wskaźnika cen towarów i usług konsumpcyjnych** wybierz opcję **Nowe**.
2. W polu **Harmonogram indeksu cen dla odbiorców** wprowadź unikatową nazwę.
3. W polu **Opis wprowadź** opis.
4. Na stronie **Harmonogram wskaźnika cen towarów i usług konsumpcyjnych** wybierz opcję **Dodaj**.
5. W polu **Data indeksu cen klientów** określ datę, od kiedy będzie aktywny nowy harmonogram CPI.
6. W polu **Harmonogram indeksu cen dla odbiorców** wprowadź nazwę wprowadzona w kroku 2.
7. Wybierz opcję **Zapisz**.

Aby usunąć datę harmonogramu CPI, wykonaj poniższe czynności.

1. Na stronie **Harmonogram indeksu cen klientów** wybierz co najmniej jeden wiersze, które chcesz usunąć, a następnie wybierz pozycję **Usuń**.
2. Aby usunąć cały harmonogram CPI, w okienku akcji wybierz polecenie **Usuń**. Nie można usunąć wybranego harmonogramu CPI, jeśli jest skojarzony z harmonogramem fakturowania.
3. W okienku akcji wybierz opcję **Proces**, aby zaktualizować harmonogramy fakturowania, w których jest wybrany harmonogram CPI. Najnowsze daty CPI i kwoty harmonogramu będą używane do aktualizowania cen w harmonogramie fakturowania.
4. W skróconej karcie procesu **indeksu cen klientów** przejrzyj zaktualizowane pola **Numer harmonogramu fakturowania**, **Numer pozycji**, **Data rozpoczęcia fakturowania**, **Data zakończenia fakturowania**, **Data eskalacji** i **Częstotliwość eskalacji**.

Po skonfigurowaniu harmonogramów CPI można je wykorzystać do eskalacji i zmian cen rabatowych w harmonogramach rozliczeniowych.

## <a name="cpi-calculation"></a>Obliczanie CPI

W przypadku tych przykładów okres należy do okresu od 1 stycznia 2020 do 31 grudnia 2022. Podstawowa stawka CPI (wartość CPI w momencie rozpoczynania umowy) wynosi 105,65. W dniu 1 stycznia 2021 roku bieżący wskaźnik CPI wynosi 110,5. W dniu 1 stycznia 2022 roku bieżący wskaźnik CPI wynosi 114,25. Początkowa kwota wynosi 1 000 USD.

**Przykład 1**

Na stronie **Parametry fakturowania umowy cyklicznej** w polu **Obliczanie indeksu cen klientów** ustawiono wartość **Indeks cen konsumentów podstawowych**.

Dla okresu 1 stycznia 2021 pierwsza kwota eskalacji jest obliczana w następujący sposób, na podstawie kwoty początkowej:

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

Dla okresu 1 stycznia 2022 pierwsza kwota eskalacji jest obliczana w następujący sposób:

1 000 + (114,25 – 105,65) &divide; 105,65 &times; 1 000 = 1 081,40

**Przykład 2**

Na stronie **Parametry fakturowania umowy cyklicznej** w polu **Obliczanie indeksu cen klientów** ustawiono wartość **Wcześniejszy wskaźnik cen towarów i usług konsumpcyjnych**.

Dla okresu 1 stycznia 2021 pierwsza kwota eskalacji jest obliczana w następujący sposób, na podstawie kwoty początkowej:

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

W okresie od 1 stycznia 2022 r. kwotę eskalacji oblicza się w następujący sposób, na podstawie pierwszej kwoty eskalacji:

1 045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1 045,91 = 1 081,40

> [!NOTE]
> W procesie eskalacji zawsze jest używana ostatnia wartość CPI, niezależnie od daty indeksu. Jeśli na przykład eskalacja ma się od początku września, ale ostatnia wartość CPI to lipca, używany jest indeks lipca. Po wprowadzeniu indeksu września nie zostaną wprowadzone żadne korekty.

## <a name="prorated-escalation"></a>Proporcjonalna eskalacja

Jeśli eskalacja ma miejsce w trakcie okresu fakturowania, kwota jest proporcjonalna. Na przykład okres fakturowania to od 1 sierpnia 2020 do 31 lipca 2021. W dniu 1 września 2019 roku wartość CPI wynosi 244. W dniu 1 września 2020 roku wartość CPI wynosi 250. Jeśli poprzednia stawka wynosi 1000, do obliczenia kwoty fakturowania za okres służą następujące formuły:

* *Zmiany w CPI* = (250 – 244) &divide; 244 = 2,459%
* *Bieżąca data:* 1 000 &times; 2,459% = 1 024,59
* *Liczba dni przy bieżącym kursie* = 31 lipca 2021 – 1 września 2020 = 334
* *Poprzednia stawka* = 1000
* *Liczba dni przy poprzedniej stawce* = 31 sierpnia 2020 – 1 sierpnia 2020 = 31
* *Łączna liczba dni okresu fakturowania* = 31 lipca 2021 – 1 sierpnia 2020 + 1 = 365
* *Kwota za fakturę za ten okres* = (1 000 &times; 31 &divide; 365) + (1 024,59 &times; 334 &divide; 365) = 1022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Eskalacja z zastosowaniem CPI i procentu

Eskalacje mogą być wykonywane przy użyciu CPI. 3-procentowa eskalacja CPI rozpoczyna się 1 stycznia 2020 i ma roczną częstotliwość.

- Kwota fakturowana za 1 stycznia 2019 roku, do 31 grudnia 2020, wynosi 4000.
- Okres fakturowania, który będzie eskalowany, to 1 stycznia 2020 do 31 grudnia 2020.
- W dniu 1 grudnia 2018 r. wartość wskaźnika CPI wynosi 205,3. W dniu 1 grudnia 2019 r. wartość wskaźnika CPI wynosi 219,6.

Jeśli poprzednia stawka wynosi 4 000, kwota rozliczenia za ten okres jest obliczana w następujący sposób:

- *Zmiany w CPI* = (219.6 – 205.3) &divide; 205.3 = 6,965%
- *Bieżąca data* = (4 000 &times; 6,965%) – 4000 = 278,60
- *Zmiany procentowe* = (4000 &times; 1,03) – 4000 = 120
- *Kwota fakturowania* = 4000 + 278,6 + 120 = 4 398,6
