---
title: "Monitorowanie dokładności prognozy"
description: "W tym artykule opisano typy dokładności prognozy dostępne w programie Microsoft Dynamics 365 for Finance and Operations i wyjaśniono, jak można wyświetlać wartości dokładności."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1f54251b6f6937c59293bd44a0fc27272ffd3d55
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="monitor-forecast-accuracy"></a>Monitorowanie dokładności prognozy

[!include [banner](../includes/banner.md)]

W tym artykule opisano typy dokładności prognozy dostępne w programie Microsoft Dynamics 365 for Finance and Operations i wyjaśniono, jak można wyświetlać wartości dokładności.

Program Finance and Operations oblicza następujące typy dokładności prognoz:

-   Dokładność prognozy historycznej — przez porównanie prognozy historycznej używanej przez planowanie główne z historycznym popytem. Aby wyświetlić wartości (bezwzględne i procentowe) dla dokładności prognozy historycznej, kliknij **Pokaż dokładność** na stronie **Szczegóły prognozy popytu**.
-   Szacowana dokładność modelu prognozowania używanego do generowania prognoz. Można wyświetlić dokładność procentową w **Szczegóły modelu — MAPE** na stronie **Szczegóły prognozy popytu**. 

**Uwaga:** W przypadku korzystania z usługi uczenia maszynowego Microsoft Azure dla prognozowania popytu w programie Finance and Operations dokładność obliczeń modelu wewnętrznego opiera się na danych testowych. Aby określić rozmiar zestawu danych testowych, należy ustawić parametr **TEST\_SET\_SIZE\_PERCENT** na stronie **Parametry prognozowania popytu**. Na przykład w przypadku wartości **20** dokładność modelu wewnętrznego będzie obliczana na podstawie ostatnich 20 procent danych historycznych.


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md)

[Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu](remove-historical-outliers-calculating-demand-forecast.md)




