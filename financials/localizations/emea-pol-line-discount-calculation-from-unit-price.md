---
title: Obliczanie rabatu od ceny jednostkowej dla Polski
description: "Dla osób prawnych w Polsce rabat wiersza może być obliczona z cena jednostkowa wiersza faktury, a nie od kwoty wiersza. Ten temat zawiera informacje o obliczaniu rabatu wiersza z metody cena jednostki i wyjaśniono, jak ją skonfigurować."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 263424
ms.assetid: d0645f8d-05a4-4212-b6de-975a625b1fe0
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 3a97f9b81173476ed200d649ca264bf61314672c
ms.lasthandoff: 03/31/2017


---

# <a name="line-discount-calculation-from-the-unit-price-for-poland"></a>Obliczanie rabatu od ceny jednostkowej dla Polski

Dla osób prawnych w Polsce rabat wiersza może być obliczona z cena jednostkowa wiersza faktury, a nie od kwoty wiersza. Ten temat zawiera informacje o obliczaniu rabatu wiersza z metody cena jednostki i wyjaśniono, jak ją skonfigurować.

Dla osób prawnych w Polsce rabat wiersza nie ma być obliczany na podstawie kwoty wiersza. Zamiast tego można obliczyć z ceną jednostkową wiersza faktury. Przy obliczaniu rabatu wiersza z metody cena jednostki jest używany, cena jednostkowa z rabatem jest zaokrąglana zanim kwota wiersza jest obliczana. W poniższej tabeli przedstawiono, jak rabat wiersza jest obliczany przez standardową metodą i obliczaniu rabatu wiersza z metody cenę jednostki.

|Ilość|Cena|Procent rabatu|Kwota netto (standardowa metoda)|Kwota netto (obliczenia rabatu wiersza z metody cena jednostki)|
|--------|-----|-------------------|---------------|------------------------------------------------|
|100     |6.75 |5                  |641.25 (6.75 × 100 = 675.00; 675 × 0.95 = 641.25)|641.00 (6.75 × 0.95 = 6.4125; 6.41 × 100 = 641.00)|

> [!NOTE]
> 0,95, używanym w equals obliczeń 1,00 – 0,05, gdzie 0,05 jest kwota rabatu, jeśli cena jednostkowa wynosi 1,00.

## <a name="set-up-the-calculation-of-line-discount-parameter"></a>Ustawianie obliczania parametru Rabat wiersza
Kalkulacja rabatu wiersza z metody cena jednostki dotyczy zarówno Rozrachunki z odbiorcami i Rozrachunki i jest ustawiony na **rozrachunków z odbiorcami Parametry** stronę i **zaopatrzenie i sourcing parametry** strony. **Obliczania rabatu wiersza** parametr ma następujące opcje:

-   **Od wartości wiersza** — umożliwia standardową metodę obliczania rabatu wiersza.
-   **Od ceny jednostkowej** — umożliwia obliczanie rabatu wiersza obliczeń rabatu wiersza z metody cenę jednostki.

**Obliczania rabatu wiersza** parametr ma wpływ na następujące dokumenty:

-   Zamówienia sprzedaży
-   Zamówienia zakupu
-   Faktury dostawcy



