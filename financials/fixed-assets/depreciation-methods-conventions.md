---
title: Metody amortyzacji i konwencje
description: "Ten artykuł zawiera omówienie konwencji amortyzacji i metod amortyzacji obsługiwanych w systemie Microsoft Dynamics AX."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 51c053e6c130d20258e02284d097431a18bb38cb
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-methods-and-conventions"></a>Metody amortyzacji i konwencje

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie konwencji amortyzacji i metod amortyzacji obsługiwanych w systemie Microsoft Dynamics AX.

Można wybrać różne metody i konwencje amortyzacji. Celem metod jest alokowanie wartości amortyzacji środka trwałego w okresach obrachunkowych. Wartość środka trwałego podlegająca amortyzacji jest ceną nabycia pomniejszoną o ewentualną wartość likwidacji. 

W przypadku używania konwencji amortyzacji i modyfikowania daty ostatniego rozpoczęcia amortyzacji środka trwałego, co sprawia, że kilka amortyzacji jest pomijanych, amortyzacja za ostatni rok może być większa lub mniejsza niż oczekiwana. Amortyzacja jest korygowana przez liczbę okresów amortyzacji których dotyczy modyfikacja daty ostatniego rozpoczęcia amortyzacji.

Przykładowo, gdy przez trzy lata używana jest półroczna konwencja amortyzacji, amortyzacja zazwyczaj występuje przez 3,5 roku. Jeśli w ciągu 3,5 roku zostanie zmieniona data ostatniego rozpoczęcia amortyzacji, ostatni rok amortyzacji przesunie w górę liczbę okresów, których to dotyczy. Jeśli data zostanie przesunięta o trzy miesiące, ostatni rok będzie miał dziewięć miesięcy wartych amortyzacji, podczas gdy normalnie byłoby ich sześć.

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

 



<a name="see-also"></a>Informacje dodatkowe
--------

[Amortyzacja środka trwałego](fixed-asset-depreciation.md)

[Amortyzacja liniowa za okres użytkowania](Straight-line-service-life-depreciation.md)

[Amortyzacja degresywna](reduce-balance-depreciation.md)

[Amortyzacja ręczna](manual-depreciation.md)

[Amortyzacja czynnikowa](factor-depreciation.md)

[Amortyzacja według zużycia](consumption-depreciation.md)

[Amortyzacja liniowa za pozostały okres użytkowania](straight-line-life-remaining-depreciation.md)

[125% amortyzacja degresywna](125-percent-reducing-balance-depreciation.md)

[150% amortyzacja degresywna](150-percent-reducing-balance-depreciation.md)

[175% amortyzacja degresywna](175-percent-reducing-balance-depreciation.md)

[200% amortyzacja degresywna](200-percent-reducing-balance-depreciation.md)



