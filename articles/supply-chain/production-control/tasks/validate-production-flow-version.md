---
title: Sprawdzanie przepływu i wersji produkcji
description: W tej procedurze pokazano sposób tworzenia nowego przepływu produkcji oraz pierwszej wersji dla produkcji oszczędnej.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ae4c5f55d317a99e23ba6e76fc50ddece1e55a1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571411"
---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="882d9-103">Sprawdzanie przepływu i wersji produkcji</span><span class="sxs-lookup"><span data-stu-id="882d9-103">Validate a production flow and version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="882d9-104">W tej procedurze pokazano sposób tworzenia nowego przepływu produkcji oraz pierwszej wersji dla produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="882d9-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="882d9-105">Warunki wstępne: Należy wcześniej zdefiniować parametry produkcji dla produkcji oszczędnej oraz jednostki miary dla czasu klasy.</span><span class="sxs-lookup"><span data-stu-id="882d9-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="882d9-106">Trzeba zdefiniować strumień wartości i grupę produkcji.</span><span class="sxs-lookup"><span data-stu-id="882d9-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="882d9-107">Przeczytaj oficjalne dokumenty o produkcji oszczędnej, aby zaznajomić się z pojęciami przepływów produkcji i działań.</span><span class="sxs-lookup"><span data-stu-id="882d9-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="882d9-108">Ta procedura odnosi się do firmy USMF umieszczonej w danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="882d9-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="882d9-109">Jednak można też używać innych firm, o ile tylko są skonfigurowane dla produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="882d9-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="882d9-110">Tworzenie przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="882d9-110">Create a production flow</span></span>
1. <span data-ttu-id="882d9-111">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="882d9-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="882d9-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="882d9-112">Click New.</span></span>
3. <span data-ttu-id="882d9-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="882d9-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="882d9-114">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="882d9-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="882d9-115">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="882d9-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="882d9-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="882d9-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="882d9-117">Strumień wartości jest jednostką operacyjną, która obejmuje wszystkie działania i przepływy w strumieniu wartości.</span><span class="sxs-lookup"><span data-stu-id="882d9-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="882d9-118">Na tym etapie jednostkami operacyjnymi są tylko firmy i nie mają one żadnych dodatkowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="882d9-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="882d9-119">W polu Grupa produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="882d9-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="882d9-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="882d9-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="882d9-121">Grupy produkcji umożliwiają definiowanie materiałów, robocizny i kont PWT dla procesu produkcji.</span><span class="sxs-lookup"><span data-stu-id="882d9-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="882d9-122">Aby skojarzyć kontekst księgowania z przepływem produkcji, należy wybrać grupę produkcji.</span><span class="sxs-lookup"><span data-stu-id="882d9-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="882d9-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="882d9-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="882d9-124">Tworzenie nowej wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="882d9-124">Create a production flow version</span></span>
1. <span data-ttu-id="882d9-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="882d9-125">Click Add.</span></span>
2. <span data-ttu-id="882d9-126">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="882d9-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="882d9-127">Można zmienić datę ważności wersji w każdym momencie, nawet w przypadku wersji aktywnych.</span><span class="sxs-lookup"><span data-stu-id="882d9-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="882d9-128">Data ważności może służyć do zaplanowania wycofania wersji.</span><span class="sxs-lookup"><span data-stu-id="882d9-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="882d9-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="882d9-129">Click OK.</span></span>
4. <span data-ttu-id="882d9-130">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="882d9-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="882d9-131">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="882d9-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="882d9-132">Wybierz jednostkę taktu.</span><span class="sxs-lookup"><span data-stu-id="882d9-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="882d9-133">W polu Średni czas taktu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="882d9-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="882d9-134">Do celów kontroli taktu wersji przepływu produkcji określ docelowy średni czas taktu.</span><span class="sxs-lookup"><span data-stu-id="882d9-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="882d9-135">Takt jest definiowany jako ilość w okresie.</span><span class="sxs-lookup"><span data-stu-id="882d9-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="882d9-136">W podanym przykładzie czas taktu wynosi 0,2 godziny na 10 sztuk.</span><span class="sxs-lookup"><span data-stu-id="882d9-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="882d9-137">Dla czasu pracy 8 godzin odpowiada to dziennej produktywności 400 sztuk.</span><span class="sxs-lookup"><span data-stu-id="882d9-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="882d9-138">W polu Ilość na cykl wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="882d9-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="882d9-139">Rozwiń lub zwiń sekcję Szczegóły wersji.</span><span class="sxs-lookup"><span data-stu-id="882d9-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="882d9-140">W polu Minimalny czas taktu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="882d9-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="882d9-141">Minimalny czas taktu musi być mniejszy lub równy średniemu czasowi taktu.</span><span class="sxs-lookup"><span data-stu-id="882d9-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="882d9-142">W polu Maksymalny czas taktu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="882d9-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="882d9-143">Maksymalny czas taktu musi być większy lub równy średniemu czasowi taktu.</span><span class="sxs-lookup"><span data-stu-id="882d9-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="882d9-144">Wprowadź liczbę dni w polu Okres rzeczywistego czasu cyklu.</span><span class="sxs-lookup"><span data-stu-id="882d9-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="882d9-145">Okres rzeczywistego czasu cyklu jest liczbą dni agregowania zadań od faktycznej minuty wstecz, aby obliczyć rzeczywisty czas cyklu.</span><span class="sxs-lookup"><span data-stu-id="882d9-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="882d9-146">Wartość można zmienić w dowolnym momencie i jest ona używana tylko do obliczania rzeczywistych czasów cykli.</span><span class="sxs-lookup"><span data-stu-id="882d9-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="882d9-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="882d9-147">Click Save.</span></span>

