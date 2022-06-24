---
title: Scenariusze daty wyrównania
description: Ten artykuł zawiera przykłady, które pokazują, jak daty wyrównania działają w rozliczeniach subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 102e3a104be5be287f914172160e95aff65d0b18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872623"
---
# <a name="alignment-date-scenarios"></a>Scenariusze daty wyrównania

Ten artykuł zawiera przykłady, które pokazują, jak daty wyrównania działają w rozliczeniach subskrypcji.

W tym przykładzie szczegół rozliczenia dla harmonogramu rozliczeń ma datę wyrównania 31 października 2019 roku. Pierwszy szczegół rozliczenia dla tej linii kończy się 31 października 2019 roku i jest odpowiednio proporcjonalny. Linia jest automatycznie odnawiana przy użyciu daty rozpoczęcia odnowienia 11 listopada.

> [!NOTE]
> Rok jest istotny, ponieważ może spowodować, że data wyrównania będzie większa lub mniejsza niż rok. W tych przykładach metoda odliczania jest ustawiona na **Miesięcznie** na stronie **Parametry rozliczania umów cyklicznych**. Jeśli jest ustawiona na **Codziennie**, niektóre kwoty częściowe będą się różnić.

## <a name="scenario-1-no-alignment"></a>Scenariusz 1: Bez wyrównania

Harmonogram rozliczeń jest skonfigurowany z następującymi danymi:

- **Data rozpoczęcia:** 1 maja 2019 r.
- **Data końcowa:** 31 grudnia 2024 r.
- **Kwota:** 1000 $

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 4/30/2020 | | | 1,00 | | 1,00 | 1,000.00 |
| 5/1/2020 | 4/30/2021 | | | 1,00 | | 1,00 | 1,000.00 |
| 5/1/2021 | 4/30/2022 | | | 1,00 | | 1,00 | 1,000.00 |
| 5/1/2022 | 4/30/2023 | | | 1,00 | | 1,00 | 1,000.00 |
| 5/1/2023 | 4/30/2024 | | | 1,00 | | 1,00 | 1,000.00 |
| 5/1/2024 | 12/31/2024 | | | 1,00 | | 1,00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>Scenariusz 2: Skrócone wyrównanie

Harmonogram rozliczeń jest skonfigurowany z następującymi danymi:

- **Data rozpoczęcia:** 1 maja 2019 r.
- **Data końcowa:** 31 grudnia 2024 r.
- **Kwota:** 1000 $
- **Data dopasowania:** 31 grudnia 2019 r.

Pierwsza kwota odnowienia jest przeznaczona na okres krótszy niż jeden rok.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1,00 | | 1,00 | 666.67 |
| 1/1/2020 | 12/31/2020 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2021 | 12/31/2021 | | | 1,00 | | 1,00 | 1,000.00 |
| 1.1.2022 | 12/31/2022 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2023 | 12/31/2023 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2024 | 12/31/2024 | | | 1,00 | | 1,00 | 1,000.00 |

## <a name="scenario-3-extended-alignment"></a>Scenariusz 3: Wydłużone wyrównanie

Harmonogram rozliczeń jest skonfigurowany z następującymi danymi:

- **Data rozpoczęcia:** 1 maja 2019 r.
- **Data końcowa:** 31 grudnia 2024 r.
- **Kwota:** 1000 $
- **Data dopasowania:** 31 grudnia 2020 r.

Pierwsza kwota odnowienia jest przeznaczona na okres dłuższy niż jeden rok.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2020 | | | 1,00 | | 1,00 | 1,666.67 |
| 1/1/2021 | 12/31/2021 | | | 1,00 | | 1,00 | 1,000.00 |
| 1.1.2022 | 12/31/2022 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2023 | 12/31/2023 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2024 | 12/31/2024 | | | 1,00 | | 1,00 | 1,000.00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>Scenariusz 4: Wyrównanie z innym miesiącem końcowym

Harmonogram rozliczeń jest skonfigurowany z następującymi danymi:

- **Data rozpoczęcia:** 1 maja 2019 r.
- **Data końcowa:** 31 października 2024 r.
- **Kwota:** 1000 $
- **Data dopasowania:** 31 grudnia 2019 r.

> [!NOTE]
> Ten scenariusz nie jest powszechny.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1,00 | | 1,00 | 666.67 |
| 1/1/2020 | 12/31/2020 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2021 | 12/31/2021 | | | 1,00 | | 1,00 | 1,000.00 |
| 1.1.2022 | 12/31/2022 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2023 | 12/31/2023 | | | 1,00 | | 1,00 | 1,000.00 |
| 1/1/2024 | 10/31/2024 | | | 1,00 | | 1,00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>Scenariusz 5: Jeden rok częściowy

Harmonogram rozliczeń jest skonfigurowany z następującymi danymi:

- **Data rozpoczęcia:** 1 maja 2019 r.
- **Data końcowa:** 31 grudnia 2019 r.
- **Kwota:** 1000 $
- **Data dopasowania:** 31 grudnia 2019 r.

W tym scenariuszu data wyrównania nie jest potrzebna. Taki scenariusz jest częsty w przypadku automatycznych odnowień.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1,00 | | 1,00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>Scenariusz 6: Wyliczone daty

Wsparcie i odnowienie jest ustawione z następującymi danymi:

- **Zastępowanie daty rozpoczęcia:** Nie
- **Daty rozpoczęcia wsparcia i odnowienia:** Początek następnego miesiąca
- **Data księgowania faktury:** 22 czerwca 2019 r.
- **Data dopasowania:** 31 grudnia 2020 r.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 7/1/2019 | 7/31/2019 | | | 1,00 | | 1,00 | 297.60 |
| 8/1/2019 | 12/31/2020 | | | 1,00 | | 1,00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>Scenariusz 7: Obliczone daty i przyszłe księgowanie

Wsparcie i odnowienie jest ustawione z następującymi danymi:

- **Zastępowanie daty rozpoczęcia:** Nie
- **Daty rozpoczęcia wsparcia i odnowienia:** Początek następnego miesiąca
- **Data księgowania faktury:** 22 czerwca 2019 r.
- **Data dopasowania:** 31 grudnia 2020 r.

W tym scenariuszu data wyrównania jest zmieniana na 31 grudnia 2021.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1,00 | | 1,00 | 0,00 |
| 8/1/2019 | 12/31/2020 | | | 1,00 | | 1,00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>Scenariusz 8: Daty ręczne i wiele lat

Wsparcie i odnowienie jest ustawione z następującymi danymi:

- **Zastąp datę rozpoczęcia:** Tak
- **Data rozpoczęcia odnowienia:** 1 czerwca 2020 r.
- **Data końcowa odnowienia:** 31 grudnia 2024 r.
- **Data dopasowania:** 31 grudnia 2021 r.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1,00 | | 1,00 | 0,00 |
| 7/1/2020 | 12/31/2021 | | | 1,00 | | 1,00 | 375.00 |
| 1.1.2022 | 12/31/2022 | | | 1,00 | | 1,00 | 250.00 |
| 1/1/2023 | 12/31/2023 | | | 1,00 | | 1,00 | 250.00 |
| 1/1/2024 | 12/31/2024 | | | 1,00 | | 1,00 | 250.00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>Scenariusz 9: Daty ręczne, wiele lat i inny miesiąc końcowy

Wsparcie i odnowienie jest ustawione z następującymi danymi:

- **Zastąp datę rozpoczęcia:** Tak
- **Data rozpoczęcia odnowienia:** 1 czerwca 2020 r.
- **Data końcowa odnowienia:** 31 października 2024 r.
- **Data dopasowania:** 31 grudnia 2021 r.

| Data rozpoczęcia rozliczania | Data zakończenia rozliczenia | Poprzednie odczytywanie | Bieżący odczyt | Wprowadzona ilość | Ilość bezpłatna | Ilość do rozliczenia | Cena jednostkowa |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1,00 | | 1,00 | 0,00 |
| 7/1/2020 | 12/31/2021 | | | 1,00 | | 1,00 | 375.00 |
| 1.1.2022 | 12/31/2022 | | | 1,00 | | 1,00 | 250.00 |
| 1/1/2023 | 12/31/2023 | | | 1,00 | | 1,00 | 250.00 |
| 1/1/2024 | 10/31/2024 | | | 1,00 | | 1,00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>Scenariusz 10: Wyrównanie bez proraty

Wsparcie i odnowienie jest ustawione z następującymi danymi:

- **Zastępowanie daty rozpoczęcia:** Nie
- **Data księgowania faktury:** 22 czerwca 2019 r.
- **Data dopasowania:** 31 grudnia 2019 r.

Data rozpoczęcia odnowienia i daty wyrównania są dostosowane tak, aby obie daty rozpoczęcia były po dacie delegowania.

- **Data rozpoczęcia odnowienia:** 1 stycznia 2020 r.
- **Data końcowa odnowienia:** 31 grudnia 2020 r.
