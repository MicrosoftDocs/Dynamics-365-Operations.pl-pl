---
title: Monitorowanie dokładności prognozy
description: W tym artykule opisano typy dokładności prognozy dostępne w Dynamics 365 Supply Chain Management i wyjaśniono, jak można wyświetlać wartości dokładności.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76248d87533fd233b255060aa278c76e13719700
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740747"
---
# <a name="monitor-forecast-accuracy"></a>Monitorowanie dokładności prognozy

[!include [banner](../includes/banner.md)]

W tym artykule opisano typy dokładności prognozy dostępne w Microsoft Dynamics 365 Supply Chain Management i wyjaśniono, jak można wyświetlać wartości dokładności.

Supply Chain Management oblicza następujące typy dokładności prognoz:

-   Dokładność prognozy historycznej — przez porównanie prognozy historycznej używanej przez planowanie główne z historycznym popytem. Aby wyświetlić wartości (bezwzględne i procentowe) dla dokładności prognozy historycznej, kliknij **Pokaż dokładność** na stronie **Szczegóły prognozy popytu**.
-   Szacowana dokładność modelu prognozowania używanego do generowania prognoz. Można wyświetlić dokładność procentową w **Szczegóły modelu — MAPE** na stronie **Szczegóły prognozy popytu**. 

> [!NOTE]
> W przypadku korzystania z usługi Microsoft Azure Machine Learning dla prognozowania popytu dokładność obliczeń modelu wewnętrznego opiera się na danych testowych. Aby określić rozmiar zestawu danych testowych, należy ustawić parametr **TEST\_SET\_SIZE\_PERCENT** na stronie **Parametry prognozowania popytu**. Na przykład w przypadku wartości **20** dokładność modelu wewnętrznego będzie obliczana na podstawie ostatnich 20 procent danych historycznych.


## <a name="additional-resources"></a>Dodatkowe zasoby

- [Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md)
- [Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]