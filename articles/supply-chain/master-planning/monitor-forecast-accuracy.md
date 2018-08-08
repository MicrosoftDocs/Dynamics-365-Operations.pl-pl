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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d7070c15f9ee23cfdba871af68d1fc5954735651
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="19409-103">Monitorowanie dokładności prognozy</span><span class="sxs-lookup"><span data-stu-id="19409-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19409-104">W tym artykule opisano typy dokładności prognozy dostępne w programie Microsoft Dynamics 365 for Finance and Operations i wyjaśniono, jak można wyświetlać wartości dokładności.</span><span class="sxs-lookup"><span data-stu-id="19409-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="19409-105">Program Finance and Operations oblicza następujące typy dokładności prognoz:</span><span class="sxs-lookup"><span data-stu-id="19409-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="19409-106">Dokładność prognozy historycznej — przez porównanie prognozy historycznej używanej przez planowanie główne z historycznym popytem.</span><span class="sxs-lookup"><span data-stu-id="19409-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="19409-107">Aby wyświetlić wartości (bezwzględne i procentowe) dla dokładności prognozy historycznej, kliknij **Pokaż dokładność** na stronie **Szczegóły prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="19409-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="19409-108">Szacowana dokładność modelu prognozowania używanego do generowania prognoz.</span><span class="sxs-lookup"><span data-stu-id="19409-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="19409-109">Można wyświetlić dokładność procentową w **Szczegóły modelu — MAPE** na stronie **Szczegóły prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="19409-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="19409-110">**Uwaga:** W przypadku korzystania z usługi uczenia maszynowego Microsoft Azure dla prognozowania popytu w programie Finance and Operations dokładność obliczeń modelu wewnętrznego opiera się na danych testowych.</span><span class="sxs-lookup"><span data-stu-id="19409-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="19409-111">Aby określić rozmiar zestawu danych testowych, należy ustawić parametr **TEST\_SET\_SIZE\_PERCENT** na stronie **Parametry prognozowania popytu**.</span><span class="sxs-lookup"><span data-stu-id="19409-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="19409-112">Na przykład w przypadku wartości **20** dokładność modelu wewnętrznego będzie obliczana na podstawie ostatnich 20 procent danych historycznych.</span><span class="sxs-lookup"><span data-stu-id="19409-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="19409-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="19409-113">Additional resources</span></span>
--------

[<span data-ttu-id="19409-114">Autoryzowanie skorygowanej prognozy</span><span class="sxs-lookup"><span data-stu-id="19409-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="19409-115">Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="19409-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)




