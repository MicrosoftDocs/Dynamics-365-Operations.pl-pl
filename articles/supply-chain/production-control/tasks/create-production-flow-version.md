--- 
title: "Tworzenie nowej wersji przepływu produkcji"
description: "Ta procedura skupia się na tworzeniu nowej wersji przepływu produkcji."
author: cvocph
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 58b3c9cd265b97a814541315e4ba8378010eb2b2
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="ac412-103">Tworzenie nowej wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="ac412-103">Create a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac412-104">Ta procedura skupia się na tworzeniu nowej wersji przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="ac412-105">Aby można było wykonać tę procedurę, należy wcześniej zdefiniować parametry produkcji dla produkcji oszczędnej oraz jednostki miary dla czasu klasy.</span><span class="sxs-lookup"><span data-stu-id="ac412-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="ac412-106">Ponadto należy zdefiniować strumień wartości i grupę produkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="ac412-107">Aby uzyskać więcej informacji na temat przepływów produkcji i działań w produkcji oszczędnej, zobacz oficjalne dokumenty o produkcji oszczędnej w systemie Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="ac412-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="ac412-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ac412-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="ac412-109">Tworzenie przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="ac412-109">Create a production flow</span></span>
1. <span data-ttu-id="ac412-110">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="ac412-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ac412-111">Click New.</span></span>
3. <span data-ttu-id="ac412-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ac412-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ac412-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="ac412-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ac412-114">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ac412-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ac412-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ac412-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ac412-116">Wybierz jednostkę operacyjnej typu Strumień wartości.</span><span class="sxs-lookup"><span data-stu-id="ac412-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="ac412-117">Strumień wartości jest jednostką operacyjną, która obejmuje wszystkie działania i przepływy w strumieniu wartości.</span><span class="sxs-lookup"><span data-stu-id="ac412-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="ac412-118">Na tym etapie jednostkami operacyjnymi są tylko firmy i nie mają one żadnych dodatkowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="ac412-119">W polu Grupa produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ac412-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ac412-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ac412-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ac412-121">Wybierz grupę produkcji dla przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-121">Select a production group for the production flow.</span></span> <span data-ttu-id="ac412-122">Grupy produkcji umożliwiają definiowanie materiałów, robocizny i kont PWT dla procesu produkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-122">Production groups allow the definition of material, labour, and WIP accounts for a production process.</span></span> <span data-ttu-id="ac412-123">Aby skojarzyć kontekst księgowania z przepływem produkcji, należy wybrać grupę produkcji.</span><span class="sxs-lookup"><span data-stu-id="ac412-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="ac412-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac412-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="ac412-125">Tworzenie nowej wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="ac412-125">Create a production flow version</span></span>
1. <span data-ttu-id="ac412-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac412-126">Click Add.</span></span>
2. <span data-ttu-id="ac412-127">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="ac412-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="ac412-128">W razie potrzeby określ datę ważności wersji.</span><span class="sxs-lookup"><span data-stu-id="ac412-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="ac412-129">Można zaktualizować ją w dowolnym momencie, nawet w przypadku wersji aktywnych.</span><span class="sxs-lookup"><span data-stu-id="ac412-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="ac412-130">Można jej użyć do zaplanowania wycofania wersji.</span><span class="sxs-lookup"><span data-stu-id="ac412-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="ac412-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ac412-131">Click OK.</span></span>
4. <span data-ttu-id="ac412-132">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ac412-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="ac412-133">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ac412-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="ac412-134">Rozstrzygnij zmiany w jednostce taktu.</span><span class="sxs-lookup"><span data-stu-id="ac412-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="ac412-135">W polu Średni czas taktu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ac412-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="ac412-136">Określ średni czas taktu wersji.</span><span class="sxs-lookup"><span data-stu-id="ac412-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="ac412-137">Do celów kontroli taktu wersji przepływu produkcji określ docelowy średni czas taktu.</span><span class="sxs-lookup"><span data-stu-id="ac412-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="ac412-138">Takt jest definiowany jako ilość w okresie.</span><span class="sxs-lookup"><span data-stu-id="ac412-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="ac412-139">W opisywanym przykładzie czas taktu wynosi 0,2 godziny na 10 sztuk.</span><span class="sxs-lookup"><span data-stu-id="ac412-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="ac412-140">Dla czasu pracy 8 godzin odpowiada to dziennej produktywności 400 sztuk.</span><span class="sxs-lookup"><span data-stu-id="ac412-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="ac412-141">W polu Ilość na cykl wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="ac412-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="ac412-142">Zdefiniuj ilości na cykl związaną ze średnim czasem taktu.</span><span class="sxs-lookup"><span data-stu-id="ac412-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="ac412-143">Przełącz rozwinięcie sekcji Szczegóły wersji.</span><span class="sxs-lookup"><span data-stu-id="ac412-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="ac412-144">W polu Minimalny czas taktu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ac412-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="ac412-145">Określ minimalny czas taktu.</span><span class="sxs-lookup"><span data-stu-id="ac412-145">Define the minimum takt time.</span></span> <span data-ttu-id="ac412-146">Minimalny czas taktu musi być mniejszy lub równy średniemu czasowi taktu.</span><span class="sxs-lookup"><span data-stu-id="ac412-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="ac412-147">W polu Maksymalny czas taktu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ac412-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="ac412-148">Maksymalny czas taktu musi być większy lub równy średniemu czasowi taktu.</span><span class="sxs-lookup"><span data-stu-id="ac412-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="ac412-149">W polu Okres rzeczywistego czasu cyklu (dni) wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ac412-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="ac412-150">Wprowadź liczbę dni w polu Okres rzeczywistego czasu cyklu.</span><span class="sxs-lookup"><span data-stu-id="ac412-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="ac412-151">Okres rzeczywistego czasu cyklu jest liczbą dni agregowania zadań od faktycznej minuty wstecz, aby obliczyć rzeczywisty czas cyklu.</span><span class="sxs-lookup"><span data-stu-id="ac412-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="ac412-152">Wartość można zmienić w dowolnym momencie i jest ona używana tylko do obliczania rzeczywistych czasów cykli.</span><span class="sxs-lookup"><span data-stu-id="ac412-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="ac412-153">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac412-153">Click Save.</span></span>


