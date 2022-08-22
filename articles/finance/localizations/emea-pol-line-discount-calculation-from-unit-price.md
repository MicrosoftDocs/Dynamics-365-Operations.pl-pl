---
title: Obliczanie rabatu wiersza od ceny jednostkowej dla Polski
description: Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza. Ten artykuł zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263424
ms.openlocfilehash: 089f058e2b1c3771f16775b8a28b6c0b7f0e15f6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281627"
---
# <a name="line-discount-calculation-from-the-unit-price-for-poland"></a>Obliczanie rabatu wiersza od ceny jednostkowej dla Polski

[!include [banner](../includes/banner.md)]

Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza. Ten artykuł zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję.

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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
