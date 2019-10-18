---
title: Obliczanie rabatu wiersza od ceny jednostkowej dla Polski
description: Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza. Ten temat zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 263424
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 334fc2fcc2e6adbfce6c299302774e0edfe262dd
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175171"
---
# <a name="line-discount-calculation-from-the-unit-price-for-poland"></a>Obliczanie rabatu wiersza od ceny jednostkowej dla Polski

[!include [banner](../includes/banner.md)]

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




