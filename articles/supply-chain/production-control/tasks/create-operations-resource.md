---
title: Tworzenie zasobu operacyjnego
description: Zasób operacyjny wykonuje działania projektu lub procesu produkcji.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9d8f13e29ea813eb9721ddca795b67837e2aa5e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "350074"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="a3253-103">Tworzenie zasobu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="a3253-103">Create an operations resource</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a3253-104">Zasób operacyjny wykonuje działania projektu lub procesu produkcji.</span><span class="sxs-lookup"><span data-stu-id="a3253-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="a3253-105">Ta procedura przedstawia sposób definiowania zasobu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a3253-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="a3253-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="a3253-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="a3253-107">Przejdź do okna Zasoby.</span><span class="sxs-lookup"><span data-stu-id="a3253-107">Go to Resources.</span></span>
2. <span data-ttu-id="a3253-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a3253-108">Click New.</span></span>
3. <span data-ttu-id="a3253-109">W polu Zasób wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="a3253-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="a3253-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="a3253-111">Definiowanie parametrów zdolności produkcyjnych i zużycia</span><span class="sxs-lookup"><span data-stu-id="a3253-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="a3253-112">Rozwiń sekcję Operacja.</span><span class="sxs-lookup"><span data-stu-id="a3253-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="a3253-113">W polu Procent odpadków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a3253-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="a3253-114">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="a3253-115">Umożliwia określenie kategorii kosztów, która definiuje sposób rozliczania kosztów przezbrajania.</span><span class="sxs-lookup"><span data-stu-id="a3253-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="a3253-116">W polu Kategoria czasu procesu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="a3253-117">Umożliwia określenie kategorii kosztów, która definiuje sposób rozliczania kosztów wykonywania procesu.</span><span class="sxs-lookup"><span data-stu-id="a3253-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="a3253-118">W polu Kategoria ilości wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="a3253-119">Umożliwia określenie kategorii kosztów, która definiuje sposób rozliczania kosztu zasobu na podstawie ilości wyprodukowanych towarów.</span><span class="sxs-lookup"><span data-stu-id="a3253-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="a3253-120">W polu Jednostka zdolności produkcyjnych wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="a3253-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="a3253-121">Umożliwia określenie jednostki, w której będą wyrażane zdolności produkcyjne zasobu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a3253-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="a3253-122">W polu Zdolności produkcyjne wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a3253-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="a3253-123">W polu Procent wydajności wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a3253-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="a3253-124">Umożliwia określenie wydajności oczekiwanej od zasobu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a3253-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="a3253-125">Procent wydajności dostosowuje produktywność zasobu operacyjnego i wpływa na czas zarezerwowany dla zasobu.</span><span class="sxs-lookup"><span data-stu-id="a3253-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="a3253-126">W polu Planowanie operacji — procent wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a3253-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="a3253-127">Określ maksymalny procent zdolności produkcyjnych zasobu operacyjnego, jaki ma być wykorzystywany w planowaniu operacji.</span><span class="sxs-lookup"><span data-stu-id="a3253-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="a3253-128">W polu Ograniczone zdolności produkcyjne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a3253-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="a3253-129">Ustaw w tej opcji wartość Tak, jeśli zasób operacyjny ma być planowany na podstawie rzeczywistych dostępnych zdolności produkcyjnych, a istniejące rezerwacje zdolności produkcyjnych mają zostać uwzględnione.</span><span class="sxs-lookup"><span data-stu-id="a3253-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="a3253-130">Jeśli w opcji zostanie ustawiona wartość Nie, zakłada się, że zasób operacyjny ma nieograniczone zdolności produkcyjne i może być rezerwowany ponad możliwości.</span><span class="sxs-lookup"><span data-stu-id="a3253-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="a3253-131">W polu Zasób w wąskim gardle zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a3253-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="a3253-132">Definiowanie czasów pracy</span><span class="sxs-lookup"><span data-stu-id="a3253-132">Define working times</span></span>
1. <span data-ttu-id="a3253-133">Rozwiń sekcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="a3253-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="a3253-134">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a3253-134">Click Add.</span></span>
3. <span data-ttu-id="a3253-135">W polu Kalendarz wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="a3253-136">Umożliwia określenie kalendarza czasu pracy definiującego zdolności produkcyjne zasobu (w godzinach).</span><span class="sxs-lookup"><span data-stu-id="a3253-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="a3253-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a3253-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a3253-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a3253-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="a3253-139">Definiowanie możliwości zasobu</span><span class="sxs-lookup"><span data-stu-id="a3253-139">Define resource capabilities</span></span>
1. <span data-ttu-id="a3253-140">Rozwiń sekcję Możliwości.</span><span class="sxs-lookup"><span data-stu-id="a3253-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="a3253-141">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a3253-141">Click Add.</span></span>
    * <span data-ttu-id="a3253-142">Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania.</span><span class="sxs-lookup"><span data-stu-id="a3253-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="a3253-143">Aparat planowania przydziela zasoby przez dopasowanie zapotrzebowań na zasoby w każdym działaniu do możliwości dostępnych zasobów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="a3253-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="a3253-144">W polu Możliwość wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="a3253-145">W polu Poziom wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a3253-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="a3253-146">Umożliwia określenie poziomu biegłości, z jaką zasób używa swoich możliwości.</span><span class="sxs-lookup"><span data-stu-id="a3253-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="a3253-147">W polu Priorytet wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a3253-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="a3253-148">Służy do określania priorytetu zasobu operacyjnego w odniesieniu do możliwości.</span><span class="sxs-lookup"><span data-stu-id="a3253-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="a3253-149">Podczas planowania według priorytetu najpierw jest wybierany zasób operacyjny o najwyższym priorytecie (najmniejszej wartości liczbowej).</span><span class="sxs-lookup"><span data-stu-id="a3253-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="a3253-150">Przypisywanie zasobu do grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="a3253-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="a3253-151">Rozwiń sekcję Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="a3253-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="a3253-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a3253-152">Click Add.</span></span>
    * <span data-ttu-id="a3253-153">Grupa zasobów definiuje oddział, jednostkę produkcyjną i kontekst magazynu dla zasobów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="a3253-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="a3253-154">Zasób operacyjny można zaplanować tylko wtedy, gdy jest przypisany do grupy zasobów i tylko w oddziale, w którym znajduje się grupa zasobów.</span><span class="sxs-lookup"><span data-stu-id="a3253-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="a3253-155">W polu Grupa zasobów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="a3253-156">W polu Lokalizacja wejściowa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a3253-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="a3253-157">Umożliwia określenie lokalizacji w magazynie, z której zasób operacyjny zużywa materiały.</span><span class="sxs-lookup"><span data-stu-id="a3253-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  

