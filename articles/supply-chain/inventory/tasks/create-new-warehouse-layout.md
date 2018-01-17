---
title: "Tworzenie nowego układu magazynu"
description: "W tej procedurze pokazano sposób konfigurowania informacji o lokalizacjach w magazynie."
author: perlynne
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
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 7374aec8e3033370453752b9f488d0838008d709
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="a9b7a-103">Tworzenie nowego układu magazynu</span><span class="sxs-lookup"><span data-stu-id="a9b7a-103">Create a new warehouse layout</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a9b7a-104">W tej procedurze pokazano sposób konfigurowania informacji o lokalizacjach w magazynie.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="a9b7a-105">Dotyczy to tylko magazynów utworzonych przy użyciu funkcji „podstawowego magazynowania” dostępnych w module Zarządzanie zapasami, a nie magazynów utworzonych w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="a9b7a-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="a9b7a-107">Ustawianie domyślnej pojemności lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a9b7a-107">Set the default location capacity</span></span>
1. <span data-ttu-id="a9b7a-108">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="a9b7a-109">Kliknij kartę Lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="a9b7a-110">W polu Standardowa szerokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="a9b7a-111">W polu Standardowa długość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="a9b7a-112">W polu Standardowa wysokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="a9b7a-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-113">Click Save.</span></span>
7. <span data-ttu-id="a9b7a-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="a9b7a-115">Określanie formatu nazwy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a9b7a-115">Define the location name format</span></span>
1. <span data-ttu-id="a9b7a-116">Przejdź do Zarządzanie zapasami > Konfiguracja > Podział magazynu > Magazyny.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="a9b7a-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-117">Click New.</span></span>
3. <span data-ttu-id="a9b7a-118">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="a9b7a-119">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a9b7a-120">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a9b7a-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a9b7a-122">Przełącz rozwinięcie sekcji Nazwy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="a9b7a-123">Opcje w tej sekcji definiują domyślny format nazw lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="a9b7a-124">W naszym przykładzie uwzględnimy numery alei, regału i półki.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="a9b7a-125">W opcji Uwzględnij korytarz zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="a9b7a-126">W opcji Uwzględnij regał zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-126">Set the Include rack option to Yes.</span></span>
10. <span data-ttu-id="a9b7a-127">W polu Format dla regału wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="a9b7a-128">Na przykład: -##</span><span class="sxs-lookup"><span data-stu-id="a9b7a-128">For example: -##</span></span>  
11. <span data-ttu-id="a9b7a-129">W opcji Uwzględnij półkę zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="a9b7a-130">W polu Format dla półki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="a9b7a-131">Na przykład: -##</span><span class="sxs-lookup"><span data-stu-id="a9b7a-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="a9b7a-132">Określanie lokalizacji w magazynach</span><span class="sxs-lookup"><span data-stu-id="a9b7a-132">Define warehouse locations</span></span>
1. <span data-ttu-id="a9b7a-133">W okienku akcji kliknij pozycję Magazyn.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="a9b7a-134">Kliknij przycisk Kreator lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="a9b7a-135">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-135">Click Next.</span></span>
4. <span data-ttu-id="a9b7a-136">Usuń zaznaczenie opcji Doki załadunkowe</span><span class="sxs-lookup"><span data-stu-id="a9b7a-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="a9b7a-137">Usuń zaznaczenie opcji Lokalizacje zbiorcze</span><span class="sxs-lookup"><span data-stu-id="a9b7a-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="a9b7a-138">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-138">Click Next.</span></span>
7. <span data-ttu-id="a9b7a-139">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-139">Click Next.</span></span>
8. <span data-ttu-id="a9b7a-140">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-140">Click Next.</span></span>
9. <span data-ttu-id="a9b7a-141">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-141">Click Next.</span></span>
10. <span data-ttu-id="a9b7a-142">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-142">Click Next.</span></span>
11. <span data-ttu-id="a9b7a-143">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-143">Click Next.</span></span>
12. <span data-ttu-id="a9b7a-144">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-144">Click Next.</span></span>
    * <span data-ttu-id="a9b7a-145">Należy zwrócić uwagę, że wymiary fizyczne wyświetlane na tej stronie ustawiono na początku tej procedury.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="a9b7a-146">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-146">Click Next.</span></span>
14. <span data-ttu-id="a9b7a-147">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-147">Click Finish.</span></span>
15. <span data-ttu-id="a9b7a-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-148">Close the page.</span></span>
16. <span data-ttu-id="a9b7a-149">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a9b7a-149">Refresh the page.</span></span>

