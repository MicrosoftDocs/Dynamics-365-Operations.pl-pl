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

[Fixed asset depreciation](fixed-asset-depreciation.md)

[Straight line service life depreciation](Straight-line-service-life-depreciation.md)

[Reducing balance depreciation](reduce-balance-depreciation.md)

[Manual depreciation](manual-depreciation.md)

[Factor depreciation](factor-depreciation.md)

[Consumption depreciation](consumption-depreciation.md)

[Straight line life remaining depreciation](straight-line-life-remaining-depreciation.md)

[Amortyzacja degresywna 125%](125-percent-reducing-balance-depreciation.md)

[Amortyzacja degresywna 150%](150-percent-reducing-balance-depreciation.md)

[amortyzacja Degresywna 175%](175-percent-reducing-balance-depreciation.md)

[Amortyzacja degresywna 200%](200-percent-reducing-balance-depreciation.md)


