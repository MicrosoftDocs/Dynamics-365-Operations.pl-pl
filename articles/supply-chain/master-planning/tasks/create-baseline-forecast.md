--- 
title: Tworzenie prognozy bazowej
description: "Planista produkcji można utworzyć bazową prognozę przy użyciu modeli prognozowania serii czasowych lub przez skopiowanie historycznego popytu."
author: YuyuScheller
manager: AnnBe
ms.date: 111/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: 6a712077fed4a94ae6ae6ce7ea2cfba8848e5fa5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="create-a-baseline-forecast"></a><span data-ttu-id="52f25-103">Tworzenie prognozy bazowej</span><span class="sxs-lookup"><span data-stu-id="52f25-103">Create a baseline forecast</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52f25-104">Planista produkcji można utworzyć bazową prognozę przy użyciu modeli prognozowania serii czasowych lub przez skopiowanie historycznego popytu.</span><span class="sxs-lookup"><span data-stu-id="52f25-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="52f25-105">W tej procedurze pokazano sposób kopiowania historycznego popytu w celu utworzenia prognozy bazowej dla wszystkich produktów za pomocą jednego klucza alokacji produktów.</span><span class="sxs-lookup"><span data-stu-id="52f25-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span> 


## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="52f25-106">Ustawianie klucza alokacji towaru</span><span class="sxs-lookup"><span data-stu-id="52f25-106">Set up an item allocation key</span></span>
1. <span data-ttu-id="52f25-107">Wybierz kolejno opcje Planowanie główne > Ustawienia > Grupy planowania międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="52f25-107">Go to Master planning > Setup > Intercompany planning groups.</span></span>
2. <span data-ttu-id="52f25-108">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="52f25-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="52f25-109">Na przykład wyfiltruj według pola Nazwa z wartością „10”.</span><span class="sxs-lookup"><span data-stu-id="52f25-109">For example, filter on the Name field with a value of '10'.</span></span>
    * <span data-ttu-id="52f25-110">Prognozowanie popytu odbywa się wśród podmiotów prawnych.</span><span class="sxs-lookup"><span data-stu-id="52f25-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="52f25-111">Dlatego wszystkie firmy, dla których chcesz wygenerować prognozy, należy umieścić w jednej międzyfirmowej grupie planowania.</span><span class="sxs-lookup"><span data-stu-id="52f25-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="52f25-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="52f25-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="52f25-113">Kliknij opcję kluczy alokacji produktów.</span><span class="sxs-lookup"><span data-stu-id="52f25-113">Click Item allocation keys.</span></span>
    * <span data-ttu-id="52f25-114">Wybierz wszystkie klucze alokacji produktów, dla których chcesz utworzyć prognozy.</span><span class="sxs-lookup"><span data-stu-id="52f25-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="52f25-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="52f25-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="52f25-116">Wybierz klucz alokacji produktów D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="52f25-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="52f25-117">Kliknij >.</span><span class="sxs-lookup"><span data-stu-id="52f25-117">Click >.</span></span>
7. <span data-ttu-id="52f25-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="52f25-118">Close the page.</span></span>
8. <span data-ttu-id="52f25-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="52f25-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-parameters"></a><span data-ttu-id="52f25-120">Konfigurowanie parametrów prognozowania popytu</span><span class="sxs-lookup"><span data-stu-id="52f25-120">Set up the demand forecasting parameters</span></span>
1. <span data-ttu-id="52f25-121">Wybierz kolejno opcje Planowanie główne > Ustawienia > Prognozowanie popytu > Parametry prognozowania popytu.</span><span class="sxs-lookup"><span data-stu-id="52f25-121">Go to Master planning > Setup > Demand forecasting > Demand forecasting parameters.</span></span>
2. <span data-ttu-id="52f25-122">Rozwiń sekcję Parametry algorytmu prognozy.</span><span class="sxs-lookup"><span data-stu-id="52f25-122">Expand the Forecast algorithm parameters section.</span></span>
3. <span data-ttu-id="52f25-123">W polu Strategia generowania prognozy wybierz opcję „Kopiuj na popycie historycznym”.</span><span class="sxs-lookup"><span data-stu-id="52f25-123">In the Forecast generation strategy field, select 'Copy over historical demand'.</span></span>
4. <span data-ttu-id="52f25-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="52f25-124">Click Save.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="52f25-125">Tworzenie prognozy bazowej</span><span class="sxs-lookup"><span data-stu-id="52f25-125">Create a baseline forecast</span></span>
1. <span data-ttu-id="52f25-126">Wybierz kolejno opcje Planowanie główne > Prognozowanie > Prognozowanie popytu > Generuj bazową prognozę statystyczną.</span><span class="sxs-lookup"><span data-stu-id="52f25-126">Go to Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast.</span></span>
2. <span data-ttu-id="52f25-127">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="52f25-127">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="52f25-128">Jeśli masz zamówienia sprzedaży rozpoczynające się od 1 stycznia 2015 r., należy wprowadzić tę datę.</span><span class="sxs-lookup"><span data-stu-id="52f25-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="52f25-129">W przeciwnym wypadku wprowadź najwcześniejszą datę zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="52f25-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="52f25-130">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="52f25-130">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="52f25-131">Wprowadź ostatnią datę swoich zamówień sprzedaży, np. „2015-03-31”.</span><span class="sxs-lookup"><span data-stu-id="52f25-131">Enter the last date of your sales orders, for example '2015-03-31'.</span></span>  
4. <span data-ttu-id="52f25-132">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="52f25-132">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="52f25-133">Wprowadź „2015-04-01”.</span><span class="sxs-lookup"><span data-stu-id="52f25-133">Enter '2015-04-01'.</span></span> <span data-ttu-id="52f25-134">Data ta będzie obliczana automatycznie jako data rozpoczęcia następnego przedziału prognozowania.</span><span class="sxs-lookup"><span data-stu-id="52f25-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="52f25-135">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="52f25-135">Expand the Records to include section.</span></span>
6. <span data-ttu-id="52f25-136">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="52f25-136">Click Filter.</span></span>
7. <span data-ttu-id="52f25-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="52f25-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="52f25-138">Zaznacz wiersz, gdzie Pole = Grupa planowania międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="52f25-138">Mark the row where Field = Intercompany planning group.</span></span>  
8. <span data-ttu-id="52f25-139">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="52f25-139">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="52f25-140">Wpisz grupę planowania międzyfirmowego, na przykład 10, której użyto w pierwszym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="52f25-140">Type the intercompany planning group, for example, 10, that you used in the first task.</span></span>  
9. <span data-ttu-id="52f25-141">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="52f25-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="52f25-142">Zaznacz wiersz, gdzie Pole = Klucz alokacji produktów.</span><span class="sxs-lookup"><span data-stu-id="52f25-142">Select the row where Field = Item allocation key.</span></span>  
10. <span data-ttu-id="52f25-143">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="52f25-143">In the Criteria field, type a value.</span></span>
11. <span data-ttu-id="52f25-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="52f25-144">Click OK.</span></span>
12. <span data-ttu-id="52f25-145">Rozwiń sekcję Parametry zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="52f25-145">Expand the Advanced parameters section.</span></span>
13. <span data-ttu-id="52f25-146">W polu Przedział prognozy zaznacz wartość „Miesiąc”.</span><span class="sxs-lookup"><span data-stu-id="52f25-146">In the Forecast bucket field, select 'Month'.</span></span>
14. <span data-ttu-id="52f25-147">W polu Horyzont prognozy wpisz wartość „3”.</span><span class="sxs-lookup"><span data-stu-id="52f25-147">In the Forecast horizon field, enter '3'.</span></span>
15. <span data-ttu-id="52f25-148">W polu Horyzont czasowy zamrożenia wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="52f25-148">In the Freeze time fence field, enter '1'.</span></span>
16. <span data-ttu-id="52f25-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="52f25-149">Click OK.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="52f25-150">Wizualizacja prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="52f25-150">Visualize the demand forecast</span></span>
1. <span data-ttu-id="52f25-151">Wybierz kolejno opcje Planowanie główne > Prognozowanie > Prognozowanie popytu > Skorygowana prognoza popytu.</span><span class="sxs-lookup"><span data-stu-id="52f25-151">Go to Master planning > Forecasting > Demand forecasting > Adjusted demand forecast.</span></span>
2. <span data-ttu-id="52f25-152">W tabeli zagregowanego widoku zaznacz komórkę w wierszu 1 w kolumnie 2.</span><span class="sxs-lookup"><span data-stu-id="52f25-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="52f25-153">Jest to drugi miesiąc, dla którego utworzono prognozę.</span><span class="sxs-lookup"><span data-stu-id="52f25-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="52f25-154">W atrybucie QtyCell ustaw wartość „400”.</span><span class="sxs-lookup"><span data-stu-id="52f25-154">Set QtyCell to '400'.</span></span>
    * <span data-ttu-id="52f25-155">W komórce wprowadź liczbę inną niż prognozowana, na przykład 400.</span><span class="sxs-lookup"><span data-stu-id="52f25-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="52f25-156">Dokonano ręcznego dopasowania do prognozy.</span><span class="sxs-lookup"><span data-stu-id="52f25-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="52f25-157">Zwróć uwagę na wskazanie graficzne w kolejnym kroku.</span><span class="sxs-lookup"><span data-stu-id="52f25-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="52f25-158">Kliknij opcję Szczegóły wiersza prognozy.</span><span class="sxs-lookup"><span data-stu-id="52f25-158">Click Forecast line details.</span></span>
    * <span data-ttu-id="52f25-159">Na tej stronie można wyświetlić wartości dokładności, popyt historyczny i prognozę.</span><span class="sxs-lookup"><span data-stu-id="52f25-159">On this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="52f25-160">Można także modyfikować prognozę.</span><span class="sxs-lookup"><span data-stu-id="52f25-160">You can make changes to the forecast as well.</span></span>  


