---
title: Tworzenie podwykonawczej komórki roboczej w systemie lean manufacturing
description: Aby wymodelować pracę podwykonawczą dla produkcji oszczędnej, należy utworzyć komórkę roboczą skojarzoną z dostawcą, który dostarcza pracę.
author: cvocph
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e07dde702e3e247ac9312d05724ea307f431937
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210831"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="1becc-103">Tworzenie podwykonawczej komórki roboczej w systemie lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="1becc-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1becc-104">Aby wymodelować pracę podwykonawczą dla produkcji oszczędnej, należy utworzyć komórkę roboczą skojarzoną z dostawcą, który dostarcza pracę.</span><span class="sxs-lookup"><span data-stu-id="1becc-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="1becc-105">Komórka robocza pracy podwykonawczej jest połączona z dostawcą poprzez skojarzenie zasobu typu Dostawca.</span><span class="sxs-lookup"><span data-stu-id="1becc-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="1becc-106">Jeśli odtworzysz to nagranie w kontekście firmy demonstracyjnej USMF, możesz wybrać identyfikator konta dostawcy 1002 i oddział 1.</span><span class="sxs-lookup"><span data-stu-id="1becc-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="1becc-107">Tworzenie zasobu dostawcy</span><span class="sxs-lookup"><span data-stu-id="1becc-107">Create a vendor resource</span></span>
1. <span data-ttu-id="1becc-108">Przejdź do okna Zasoby.</span><span class="sxs-lookup"><span data-stu-id="1becc-108">Go to Resources.</span></span>
2. <span data-ttu-id="1becc-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1becc-109">Click New.</span></span>
3. <span data-ttu-id="1becc-110">W polu Zasób wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1becc-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="1becc-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1becc-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1becc-112">W polu Typ wybierz opcję „Dostawca”.</span><span class="sxs-lookup"><span data-stu-id="1becc-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="1becc-113">W polu Dostawca kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="1becc-114">Tworzenie grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="1becc-114">Create the resource group</span></span>
1. <span data-ttu-id="1becc-115">Przejdź do okna Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="1becc-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="1becc-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1becc-116">Click New.</span></span>
3. <span data-ttu-id="1becc-117">W polu Grupa zasobów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1becc-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="1becc-118">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1becc-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1becc-119">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1becc-120">Wybierz oddział, do którego powinna zostać przydzielona komórka robocza.</span><span class="sxs-lookup"><span data-stu-id="1becc-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="1becc-121">Teoretycznie oddział może reprezentować jeden oddział obsługiwany przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="1becc-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="1becc-122">Jednak w większości przypadków zasoby podwykonawcze są przydzielone do oddziału, który zlecenia pracę podwykonawczą.</span><span class="sxs-lookup"><span data-stu-id="1becc-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="1becc-123">Należy zauważyć, że magazyny wejściowy i wyjściowy komórek pracy podwykonawczej muszą się znajdować w tym samym oddziale.</span><span class="sxs-lookup"><span data-stu-id="1becc-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="1becc-124">W polu Oddział wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1becc-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="1becc-125">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="1becc-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="1becc-126">Zaznacz lub wyczyść pole wyboru Komórka robocza.</span><span class="sxs-lookup"><span data-stu-id="1becc-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="1becc-127">W polu Magazyn wejściowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1becc-128">Wybierz magazyn i lokalizację używane do przejściowego składowania materiału dla komórki roboczej zarządzanej przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="1becc-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="1becc-129">W wielu przypadkach magazyn i lokalizacja są modelowane przy użyciu oddzielnych magazynów dla poszczególnych dostawców i jednej lokalizacji na każdą komórkę roboczą.</span><span class="sxs-lookup"><span data-stu-id="1becc-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="1becc-130">W polu Lokalizacja wejściowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1becc-131">W polu Magazyn wyjściowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1becc-132">Zdefiniuj magazyn i lokalizację, w których będzie księgowany materiał podczas księgowania działań podwykonawczych komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="1becc-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="1becc-133">Magazyn i lokalizacja mogą być w oddziale dostawcy, jeśli dostawca raportuje zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="1becc-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="1becc-134">Alternatywnie magazyn i lokalizacja mogą być lokalizacją przyjęcia skojarzoną z następnym etapem przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="1becc-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="1becc-135">W polu Lokalizacja wyjściowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="1becc-136">Rozwiń lub zwiń sekcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="1becc-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="1becc-137">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1becc-137">Click Add.</span></span>
15. <span data-ttu-id="1becc-138">W polu Kalendarz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1becc-139">Skojarz kalendarz czasu pracy komórki roboczej z grupą zasobów.</span><span class="sxs-lookup"><span data-stu-id="1becc-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="1becc-140">Dla zasobów krytycznych zalecamy zdefiniowanie określonych kalendarzy, które reprezentują dokładne czasy pracy i powiązane zdolności produkcyjne komórki roboczej lub oddziału dostawcy.</span><span class="sxs-lookup"><span data-stu-id="1becc-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="1becc-141">Rozwiń lub zwiń sekcję Zasoby.</span><span class="sxs-lookup"><span data-stu-id="1becc-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="1becc-142">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1becc-142">Click Add.</span></span>
    * <span data-ttu-id="1becc-143">Grupa zasobów podwykonawczych musi mieć skojarzony zasób typu Dostawca, który łączy grupę zasobów z kontem dostawcy.</span><span class="sxs-lookup"><span data-stu-id="1becc-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="1becc-144">W polu Zasób kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1becc-145">Zaznacz lub wprowadź zasób dostawcy utworzony w poprzednim podzadaniu.</span><span class="sxs-lookup"><span data-stu-id="1becc-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="1becc-146">Rozwiń lub zwiń sekcję Zdolności produkcyjne komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="1becc-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="1becc-147">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1becc-147">Click Add.</span></span>
    * <span data-ttu-id="1becc-148">Komórka robocza musi mieć zdefiniowane zdolności produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="1becc-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="1becc-149">W tym przykładzie tworzymy produktywność 100 sztuk na standardowy dzień roboczy.</span><span class="sxs-lookup"><span data-stu-id="1becc-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="1becc-150">W polu Model przepływu produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="1becc-151">W polu Okres zdolności produkcyjnych wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="1becc-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="1becc-152">W polu Średnia produktywność (ilość) wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1becc-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="1becc-153">W polu Jednostka kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1becc-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="1becc-154">Rozstrzygnij zmiany w jednostce.</span><span class="sxs-lookup"><span data-stu-id="1becc-154">ResolveChanges the Unit.</span></span>

