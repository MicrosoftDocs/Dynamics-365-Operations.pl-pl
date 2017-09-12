---
title: "Wprowadzanie ręcznych korekt prognozy bazowej"
description: "W tym artykule wyjaśniono, jak wprowadzać ręczne korekty prognozy bazowej i jak wyświetlać szczegóły prognozy."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 218374cdb6b5588648422d97c04fb60f26e47ac7
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="78b5c-103">Wprowadzanie ręcznych korekt prognozy bazowej</span><span class="sxs-lookup"><span data-stu-id="78b5c-103">Make manual adjustments to the baseline forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="78b5c-104">W tym artykule wyjaśniono, jak wprowadzać ręczne korekty prognozy bazowej i jak wyświetlać szczegóły prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-104">This article explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="78b5c-105">Przed dokonaniem ręcznych korekt bardzo ważne jest, aby zapoznać się z kilkoma koncepcjami na różnych stronach.</span><span class="sxs-lookup"><span data-stu-id="78b5c-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="78b5c-106">Siatka na stronie Skorygowana prognoza popytu</span><span class="sxs-lookup"><span data-stu-id="78b5c-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="78b5c-107">Strona **Skorygowana prognoza popytu** zawiera siatkę, która oferuje następującą strukturę:</span><span class="sxs-lookup"><span data-stu-id="78b5c-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="78b5c-108">Pierwsza kolumna pokazuje towary, klucze alokacji produktów, firmy itd., dla których wygenerowano prognozę.</span><span class="sxs-lookup"><span data-stu-id="78b5c-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="78b5c-109">Podtytuł strony zawiera opis bieżących wymiarów prognozy, które są widoczne na siatce.</span><span class="sxs-lookup"><span data-stu-id="78b5c-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="78b5c-110">Jeśli na przykład strona ma podtytuł **Firma / Oddział / Klucz alokacji produktów**, a jeden z nagłówków wierszy w siatce to **USMF / 1 / D\_Alloc**, ten wiersz pokazuje prognozę dla oddziału 1 firmy USMF i klucza alokacji produktów **D\_Alloc**.</span><span class="sxs-lookup"><span data-stu-id="78b5c-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="78b5c-111">Kolejne kolumny zawierają przedziały prognozy, dla których prognoza została wygenerowana.</span><span class="sxs-lookup"><span data-stu-id="78b5c-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="78b5c-112">Każdy nagłówek kolumny jest pierwszą datą przedziału prognozy, jaka jest widoczna w kolumnie.</span><span class="sxs-lookup"><span data-stu-id="78b5c-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="78b5c-113">Wartości w komórkach pokazują prognozę dla jednego towaru, klucza alokacji produktów itd, dla określonego przedziału prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-deaggregation"></a><span data-ttu-id="78b5c-114">Agregacja i deagregacja prognozy</span><span class="sxs-lookup"><span data-stu-id="78b5c-114">Forecast aggregation and deaggregation</span></span>
<span data-ttu-id="78b5c-115">Podtytuł strony pokazuje poziom agregacji prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="78b5c-116">Na przykład, jeśli strona ma podtytuł **Firma / Oddział / Klucza alokacji / Kod towaru / Kolor / Rozmiar / Konfiguracja / Style**, nie ma żadnej agregacji prognozy i prognoza jest wyświetlana na poziomie towaru i jego wymiarów.</span><span class="sxs-lookup"><span data-stu-id="78b5c-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="78b5c-117">Aby zmienić agregację, użyj strony **Zmień wymiary prognozy**, który można otworzyć z menu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="78b5c-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="78b5c-118">Aby zmodyfikować prognozę, kliknij dowolną z dostępnych komórek i wpisz skorygowaną wartość prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="78b5c-119">Zmieniona komórka natychmiast staje się pogrubiona, wskazując, że widoczna w niej prognoza nie została utworzona przez usługę prognozowania popytu, ale została ręcznie skorygowana.</span><span class="sxs-lookup"><span data-stu-id="78b5c-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="78b5c-120">Jeśli zmienisz agregację w celu zwiększenia ilości danych wyświetlanych na stronie, możesz użyć strony **Wiersze prognozy popytu**, aby wyświetlić poszczególne wiersze prognozy tworzące sumaryczną prognozę.</span><span class="sxs-lookup"><span data-stu-id="78b5c-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="78b5c-121">Na przykład została wygenerowana prognoza na poziomie towaru, ale wiadomo, że popyt na ten towar wzrośnie we wszystkich oddziałach ze względu na promocję lub innego rodzaju podobne zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="78b5c-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="78b5c-122">W takim przypadku można ustawić agregację na **Firma / Klucz alokacji produktów / Towar** na stronie **Zmień wymiary prognozy**.</span><span class="sxs-lookup"><span data-stu-id="78b5c-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="78b5c-123">Globalne skorygować globalną prognozę dla towaru we wszystkich oddziałach na siatce **Skorygowana prognoza popytu**.</span><span class="sxs-lookup"><span data-stu-id="78b5c-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="78b5c-124">Aby zobaczyć efekt zmian we wszystkich oddziałach, otwórz stronę **Wiersze prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="78b5c-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="78b5c-125">Na tej stronie będzie widoczny jeden wiersz dla towaru w każdym oddziale, skorygowaną prognozowaną ilość i pierwotną prognozowaną ilość.</span><span class="sxs-lookup"><span data-stu-id="78b5c-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="78b5c-126">Po skorygowaniu prognozowanej ilości na poziomie sumarycznym system używa alokacji ważonej do dystrybucji zmiany w wierszach tworzących agregację.</span><span class="sxs-lookup"><span data-stu-id="78b5c-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="78b5c-127">Można też wprowadzać ręczne korekty na stronie **Wiersze prognozy popytu**, zmieniając wartość **Ilość całkowita** lub komórki **Ilość** na siatce deagregacji.</span><span class="sxs-lookup"><span data-stu-id="78b5c-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="78b5c-128">Wyświetlanie szczegółów prognozy</span><span class="sxs-lookup"><span data-stu-id="78b5c-128">Viewing details of the forecast</span></span>
<span data-ttu-id="78b5c-129">Można otworzyć stronę **Szczegóły prognozy popytu**, aby wyświetlić więcej informacji na temat prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="78b5c-130">Strona **Szczegóły prognozy popytu** pokazuje następujące informacje na grafice i w tabeli:</span><span class="sxs-lookup"><span data-stu-id="78b5c-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="78b5c-131">Popyt historyczny, na którym opierają się przewidywania prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="78b5c-132">Bieżąca prognoza używana przez Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="78b5c-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="78b5c-133">Nowe wartości prognozy popytu i kwoty, o które zostały one ręcznie skorygowane.</span><span class="sxs-lookup"><span data-stu-id="78b5c-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="78b5c-134">Przedział wiarygodności dla prognozowanych wartości.</span><span class="sxs-lookup"><span data-stu-id="78b5c-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="78b5c-135">Model prognozy używany do generowania prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="78b5c-136">Przy przeglądaniu danych sumarycznych pojawi się lista wszystkich metod używanych dla wszystkich serii czasu łącznego.</span><span class="sxs-lookup"><span data-stu-id="78b5c-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="78b5c-137">Wewnętrzny model dokładności (MAPE).</span><span class="sxs-lookup"><span data-stu-id="78b5c-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="78b5c-138">Aby uzyskać więcej informacji o dokładności prognozy, zobacz [Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md).</span><span class="sxs-lookup"><span data-stu-id="78b5c-138">For more information about forecast accuracy, see [Monitoring forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="78b5c-139">**Uwagi:**</span><span class="sxs-lookup"><span data-stu-id="78b5c-139">**Notes:**</span></span>

-   <span data-ttu-id="78b5c-140">Przedział wiarygodności widoczny w sekcji **Prognoza** na stronie przedstawia różnicę między górnym i dolnym limitem przedziału wiarygodności.</span><span class="sxs-lookup"><span data-stu-id="78b5c-140">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="78b5c-141">Aby wyświetlić wartości limitów górnych i dolnych, umieść wskaźnik myszy na wykresie w sekcji **Graficzna prezentacja popytu historycznego i prognozy**.</span><span class="sxs-lookup"><span data-stu-id="78b5c-141">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="78b5c-142">W przypadku korzystania z usługi uczenia maszynowego Microsoft Azure dla prognozowania popytu w programie Finance and Operations można określić wymagany procent poziomu zaufania dla generowanej prognozy.</span><span class="sxs-lookup"><span data-stu-id="78b5c-142">If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="78b5c-143">Przedział wiarygodności zawiera zakres wartości będących dobrymi danymi szacunkowymi dla prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="78b5c-143">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="78b5c-144">Wiarygodność na poziomie 95% oznacza, że występuje 5-procentowe ryzyko, że prognoza popytu wykroczy poza zakres wiarygodności.</span><span class="sxs-lookup"><span data-stu-id="78b5c-144">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="78b5c-145">Istnieje również możliwość ręcznego korygowania prognozy na stronie **Szczegóły prognozy popytu** poprzez modyfikację wartości w wierszu **Prognoza** w sekcji **Prognoza**.</span><span class="sxs-lookup"><span data-stu-id="78b5c-145">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="see-also"></a><span data-ttu-id="78b5c-146">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="78b5c-146">See also</span></span>
--------

[<span data-ttu-id="78b5c-147">Monitorowanie dokładności prognozy</span><span class="sxs-lookup"><span data-stu-id="78b5c-147">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="78b5c-148">Generowanie bazowej prognozy statystycznej</span><span class="sxs-lookup"><span data-stu-id="78b5c-148">Generating a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)




