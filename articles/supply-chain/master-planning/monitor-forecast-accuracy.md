---
title: Monitorowanie dokładności prognozy
description: W tym artykule opisano typy dokładności prognozy dostępne w Dynamics 365 Supply Chain Management i wyjaśniono, jak można wyświetlać wartości dokładności.
author: roxanadiaconu
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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db8b9fdaf05f58d1386513348c11fcc54887d9c8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826474"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="63cf6-103">Monitorowanie dokładności prognozy</span><span class="sxs-lookup"><span data-stu-id="63cf6-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63cf6-104">W tym artykule opisano typy dokładności prognozy dostępne w Microsoft Dynamics 365 Supply Chain Management i wyjaśniono, jak można wyświetlać wartości dokładności.</span><span class="sxs-lookup"><span data-stu-id="63cf6-104">This topic describes the types of forecast accuracy that Microsoft Dynamics 365 Supply Chain Management calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="63cf6-105">Supply Chain Management oblicza następujące typy dokładności prognoz:</span><span class="sxs-lookup"><span data-stu-id="63cf6-105">Supply Chain Management calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="63cf6-106">Dokładność prognozy historycznej — przez porównanie prognozy historycznej używanej przez planowanie główne z historycznym popytem.</span><span class="sxs-lookup"><span data-stu-id="63cf6-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="63cf6-107">Aby wyświetlić wartości (bezwzględne i procentowe) dla dokładności prognozy historycznej, kliknij **Pokaż dokładność** na stronie **Szczegóły prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="63cf6-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="63cf6-108">Szacowana dokładność modelu prognozowania używanego do generowania prognoz.</span><span class="sxs-lookup"><span data-stu-id="63cf6-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="63cf6-109">Można wyświetlić dokładność procentową w **Szczegóły modelu — MAPE** na stronie **Szczegóły prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="63cf6-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="63cf6-110">W przypadku korzystania z usługi Microsoft Azure Machine Learning dla prognozowania popytu dokładność obliczeń modelu wewnętrznego opiera się na danych testowych.</span><span class="sxs-lookup"><span data-stu-id="63cf6-110">If you use the Demand forecasting Microsoft Azure Machine Learning, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="63cf6-111">Aby określić rozmiar zestawu danych testowych, należy ustawić parametr **TEST\_SET\_SIZE\_PERCENT** na stronie **Parametry prognozowania popytu**.</span><span class="sxs-lookup"><span data-stu-id="63cf6-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="63cf6-112">Na przykład w przypadku wartości **20** dokładność modelu wewnętrznego będzie obliczana na podstawie ostatnich 20 procent danych historycznych.</span><span class="sxs-lookup"><span data-stu-id="63cf6-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="63cf6-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="63cf6-113">Additional resources</span></span>
--------

[<span data-ttu-id="63cf6-114">Autoryzowanie skorygowanej prognozy</span><span class="sxs-lookup"><span data-stu-id="63cf6-114">Authorize an adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="63cf6-115">Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="63cf6-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]