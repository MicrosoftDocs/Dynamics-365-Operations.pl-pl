---
title: Obliczanie rabatu wiersza od ceny jednostkowej dla Polski
description: "Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza. Ten temat zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 263424
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: fcb337c09846efad07f31c7b37d2f7efca544200
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="line-discount-calculation-from-the-unit-price-for-poland"></a>Obliczanie rabatu wiersza od ceny jednostkowej dla Polski

[!include[banner](../includes/banner.md)]


Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza. Ten temat zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję.

W firmach w Polsce rabat wiersza nie ma być obliczany na podstawie kwoty wiersza. Zamiast tego można go obliczać na podstawie ceny jednostkowej wiersza faktury. Gdy jest używana metoda obliczania rabatu wiersza na podstawie ceny jednostkowej, przed obliczeniem kwoty wiersza następuje zaokrąglenie ceny jednostkowej z rabatem. W poniższej tabeli przedstawiono, jak rabat wiersza jest obliczany metodą standardową i metodą od ceny jednostkowej.

|Ilość|Cena|Procent rabatu|Kwota netto (metoda standardowa)|Kwota netto (metoda obliczania rabatu wiersza od ceny jednostkowej)|
|--------|-----|-------------------|---------------|------------------------------------------------|
|100     |6.75 |5                  |641,25 (6,75 × 100 = 675.00; 675 × 0,95 = 641,25)|641,00 (6,75 × 0,95 = 6,4125; 6,41 × 100 = 641,00)|

> [!NOTE]
> Wartość 0,95 użyta w obliczeniach to wynik działania 1,00 – 0,05, gdzie 0,05 jest kwotą rabatu, jeśli cena jednostkowa wynosi 1,00.

## <a name="set-up-the-calculation-of-line-discount-parameter"></a>Konfigurowanie parametru obliczania rabatu wiersza
Metoda obliczania rabatu wiersza względem ceny jednostkowej może być stosowana do rozrachunków z odbiorcami i rozrachunków z dostawcami, a konfiguruje się ją na stronach **Parametry modułu rozrachunków z odbiorcami** i **Parametry modułu Zaopatrzenie i sourcing**. Parametr **Obliczanie rabatu liniowego** ma następujące opcje:

-   **Od wartości wiersza** — rabat wiersza jest obliczany metodą standardową.
-   **Od ceny jednostkowej** — rabat wiersza jest obliczany względem ceny jednostkowej.

Parametr **Obliczanie rabatu liniowego** wpływa na następujące dokumenty:

-   Zamówienia sprzedaży
-   Zamówienia zakupu
-   Faktury dostawcy





