---
title: Monitorowanie dokładności prognozy
description: W tym artykule opisano typy dokładności prognozy dostępne w Dynamics 365 Supply Chain Management i wyjaśniono, jak można wyświetlać wartości dokładności.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a21e9d6199229438b73bfdf8307030eed60c21bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977945"
---
# <a name="monitor-forecast-accuracy"></a>Monitorowanie dokładności prognozy

[!include [banner](../includes/banner.md)]

W tym artykule opisano typy dokładności prognozy dostępne w Microsoft Dynamics 365 Supply Chain Management i wyjaśniono, jak można wyświetlać wartości dokładności.

Supply Chain Management oblicza następujące typy dokładności prognoz:

-   Dokładność prognozy historycznej — przez porównanie prognozy historycznej używanej przez planowanie główne z historycznym popytem. Aby wyświetlić wartości (bezwzględne i procentowe) dla dokładności prognozy historycznej, kliknij **Pokaż dokładność** na stronie **Szczegóły prognozy popytu**.
-   Szacowana dokładność modelu prognozowania używanego do generowania prognoz. Można wyświetlić dokładność procentową w **Szczegóły modelu — MAPE** na stronie **Szczegóły prognozy popytu**. 

> [!NOTE]
> W przypadku korzystania z usługi Microsoft Azure Machine Learning dla prognozowania popytu dokładność obliczeń modelu wewnętrznego opiera się na danych testowych. Aby określić rozmiar zestawu danych testowych, należy ustawić parametr **TEST\_SET\_SIZE\_PERCENT** na stronie **Parametry prognozowania popytu**. Na przykład w przypadku wartości **20** dokładność modelu wewnętrznego będzie obliczana na podstawie ostatnich 20 procent danych historycznych.


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md)

[Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]