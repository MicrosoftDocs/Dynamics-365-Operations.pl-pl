---
title: "Monitor dokładności prognozy"
description: "W tym artykule opisano rodzaje dokładności prognozy Microsoft Dynamics 365 dla operacji oblicza i wyjaśnia, w jaki sposób wyświetlania wartości dokładności."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Monitor dokładności prognozy

W tym artykule opisano rodzaje dokładności prognozy Microsoft Dynamics 365 dla operacji oblicza i wyjaśnia, w jaki sposób wyświetlania wartości dokładności.

Dynamics 365 dla operacji oblicza następujące rodzaje dokładności prognozy:

-   Dokładność prognozy historycznej — przez porównanie prognozy historycznej używanej przez planowanie główne z historycznym popytem. Aby wyświetlić wartości (bezwzględne i procentowe) dla dokładności prognozy historycznej, kliknij **Pokaż dokładność** na stronie **Szczegóły prognozy popytu**.
-   Szacowana dokładność modelu prognozowania używanego do generowania prognoz. Można wyświetlić dokładność procentową w **Szczegóły modelu — MAPE** na stronie **Szczegóły prognozy popytu**. 

**Uwaga:** Jeśli używasz Dynamics 365 dla operacji żądanie prognozowania usługą sieci Web usługi obliczenie dokładności modelu wewnętrznego jest oparte na zestawie danych badań. Aby określić rozmiar zestawu danych test, należy ustawić **TEST\_zestaw\_rozmiar\_procent** parametru na **prognozowania parametrów popytu** strony. Na przykład w przypadku wartości **20** dokładność modelu wewnętrznego będzie obliczana na podstawie ostatnich 20 procent danych historycznych.


<a name="see-also"></a>Informacje dodatkowe
--------

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


