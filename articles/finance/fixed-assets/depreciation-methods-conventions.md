---
title: Metody amortyzacji i konwencje
description: Ten artykuł zawiera omówienie konwencji amortyzacji i metod amortyzacji obsługiwanych w Microsoft Dynamics 365 Finance.
author: moaamer
ms.date: 12/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 066e571485602907d167b2ed1f7530b2285a02b6
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714181"
---
# <a name="depreciation-methods-and-conventions"></a>Metody amortyzacji i konwencje

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie obsługiwanych konwencji amortyzacji i metod amortyzacji.

Można wybrać różne metody i konwencje amortyzacji. Celem metod jest alokowanie wartości amortyzacji środka trwałego w okresach obrachunkowych. Wartość środka trwałego podlegająca amortyzacji jest ceną nabycia pomniejszoną o ewentualną wartość likwidacji. 

W przypadku używania konwencji amortyzacji i modyfikowania daty ostatniego rozpoczęcia amortyzacji środka trwałego, co sprawia, że kilka amortyzacji jest pomijanych, amortyzacja za ostatni rok może być większa lub mniejsza niż oczekiwana. Amortyzacja jest korygowana przez liczbę okresów amortyzacji których dotyczy modyfikacja daty ostatniego rozpoczęcia amortyzacji.

Przykładowo, gdy przez trzy lata używana jest półroczna konwencja amortyzacji, amortyzacja zazwyczaj występuje przez trzy i pół roku. Jeśli w ciągu trzech i pół roku zostanie zmieniona data ostatniego rozpoczęcia amortyzacji, ostatni rok amortyzacji przesunie w górę liczbę okresów, których to dotyczy. Jeśli data zostanie przesunięta o trzy miesiące, ostatni rok będzie miał dziewięć miesięcy wartych amortyzacji, podczas gdy normalnie byłoby ich sześć.

Można wybierać spośród następujących konwencji amortyzacji.


-   Pół roku
-   Pełny miesiąc
-   Kwartał środkowy
-   Miesiąc środkowy (1. dzień miesiąca)
-   Miesiąc środkowy (15. dzień miesiąca)
-   Pół roku (początek roku)
-   Pół roku (następny rok)

Można wybrać jedną z następujących metod amortyzacji.
-   Liniowy okres użytkowania
-   Degresywna
-   Ręczne
-   Współczynnik
-   Zużycie
-   Liniowy pozostały okres użytkowania
-   Degresywna 200%
-   Degresywna 175%
-   Degresywna 150%
-   Degresywna 125%





## <a name="additional-resources"></a>Dodatkowe zasoby

[Amortyzacja środka trwałego](fixed-asset-depreciation.md)

[Amortyzacja liniowa za okres użytkowania](Straight-line-service-life-depreciation.md)

[Amortyzacja degresywna](reduce-balance-depreciation.md)

[Amortyzacja ręczna](manual-depreciation.md)

[Amortyzacja czynnikowa](factor-depreciation.md)

[Amortyzacja według zużycia](consumption-depreciation.md)

[Amortyzacja liniowa za pozostały okres użytkowania](straight-line-life-remaining-depreciation.md)

[Amortyzacja degresywna 125 procent](125-percent-reducing-balance-depreciation.md)

[150% amortyzacja degresywna](150-percent-reducing-balance-depreciation.md)

[175% amortyzacja degresywna](175-percent-reducing-balance-depreciation.md)

[200% amortyzacja degresywna](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
