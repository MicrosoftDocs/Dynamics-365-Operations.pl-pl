---
title: Autoryzowanie skorygowanej prognozy
description: Nie wszystkie prognozy muszą być autoryzowane natychmiast. W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana. Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42137b9eb24e14518244d87e72e9ea1295be4485
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188965"
---
# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="29932-105">Autoryzowanie skorygowanej prognozy</span><span class="sxs-lookup"><span data-stu-id="29932-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29932-106">Nie wszystkie prognozy muszą być autoryzowane natychmiast.</span><span class="sxs-lookup"><span data-stu-id="29932-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="29932-107">W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana.</span><span class="sxs-lookup"><span data-stu-id="29932-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="29932-108">Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy.</span><span class="sxs-lookup"><span data-stu-id="29932-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="29932-109">Nie wszystkie prognozy muszą być autoryzowane natychmiast.</span><span class="sxs-lookup"><span data-stu-id="29932-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="29932-110">Można określić daty rozpoczęcia i zakończenia okresu, dla którego prognoza jest autoryzowana.</span><span class="sxs-lookup"><span data-stu-id="29932-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="29932-111">Ta funkcja umożliwia zamrożenie określonych przedziałów.</span><span class="sxs-lookup"><span data-stu-id="29932-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="29932-112">Określone daty rozpoczęcia i zakończenia muszą odpowiadać datom rozpoczęcia i zakończenia przedziału, w którym powstała prognoza.</span><span class="sxs-lookup"><span data-stu-id="29932-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="29932-113">System wymusza to ograniczenie i w razie potrzeby automatycznie koryguje daty.</span><span class="sxs-lookup"><span data-stu-id="29932-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="29932-114">Na karcie **Szczegóły** na stronie **Autoryzacja** można wyświetlić szczegółowe informacje o ostatnio wygenerowanej prognozie.</span><span class="sxs-lookup"><span data-stu-id="29932-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="29932-115">Można wybrać firmy i modele prognozy do autoryzacji prognozy w celu jej użycia.</span><span class="sxs-lookup"><span data-stu-id="29932-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="29932-116">Domyślnie siatka zawiera wszystkie firmy, dla których utworzono prognozę popytu.</span><span class="sxs-lookup"><span data-stu-id="29932-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="29932-117">Dla każdej firmy model prognozy odpowiadający aktualnemu planowi prognozy skonfigurowanemu w parametrach planowania głównego jest wstępnie wypełniany.</span><span class="sxs-lookup"><span data-stu-id="29932-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="29932-118">Można też zmienić ten model prognozy na dowolny inny model prognozy należący do danej firmy.</span><span class="sxs-lookup"><span data-stu-id="29932-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="29932-119">Jeśli dla danej firmy nie ma wygenerowanych danych prognozy, podczas importowania wyświetli się ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="29932-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="29932-120">Bardzo ważne jest, aby zrozumieć, jak działa pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="29932-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="29932-121">Wprowadzenie ręcznych zmian w bazowej prognozie popytu sprawia, że skorygowane wartości są autoryzowane do użycia, nawet wtedy, gdy to pole wyboru nie jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="29932-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="29932-122">Zmiany zostaną jednak odrzucone po autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="29932-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="29932-123">Dlatego przy następnym wygenerowaniu prognozy jest ona jedynie danymi statycznymi i nie zawiera żadnych zmian wprowadzonych ręcznie, nawet jeśli opcja **Przenieś ręczne korekty prognozy popytu** jest zaznaczona.</span><span class="sxs-lookup"><span data-stu-id="29932-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="29932-124">Dlatego pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu** należy traktować jako sposób odrzucania wszystkich zmian wprowadzonych ręcznie.</span><span class="sxs-lookup"><span data-stu-id="29932-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="29932-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="29932-125">Additional resources</span></span>

[<span data-ttu-id="29932-126">Wprowadzanie ręcznych korekt prognozy bazowej</span><span class="sxs-lookup"><span data-stu-id="29932-126">Make manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="29932-127">Monitorowanie dokładności prognozy</span><span class="sxs-lookup"><span data-stu-id="29932-127">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]