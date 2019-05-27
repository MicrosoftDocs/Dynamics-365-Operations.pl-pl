---
title: Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów
description: Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7b39b7649aaef0d354b61e3d70b6cac887282ed
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543894"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="e5cf3-103">Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="e5cf3-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e5cf3-104">Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="e5cf3-105">Aby zasada weszła w życie, sama zasada i odpowiednie reguły muszą być przypisane do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="e5cf3-106">Ta procedura służy do tworzenia zasady, a następnie jej przypisywania do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="e5cf3-107">Tworzenie hierarchii zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e5cf3-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="e5cf3-108">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="e5cf3-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-109">Click New.</span></span>
3. <span data-ttu-id="e5cf3-110">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-110">Click Create.</span></span>
4. <span data-ttu-id="e5cf3-111">W polu Nazwa hierarchii wymiarów wpisz „Hierarchia zachowania kosztów”.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="e5cf3-112">W polu Wymiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-113">Wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="e5cf3-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-114">Click Save.</span></span>
7. <span data-ttu-id="e5cf3-115">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="e5cf3-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-116">Click New.</span></span>
9. <span data-ttu-id="e5cf3-117">W polu Nazwa węzła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="e5cf3-118">Wypełnij pole Koszt stały.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="e5cf3-119">W drzewie zaznacz pozycję „Hierarchia zachowania kosztów”.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="e5cf3-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-120">Click New.</span></span>
12. <span data-ttu-id="e5cf3-121">W polu Nazwa węzła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="e5cf3-122">Wypełnij pole Koszt zmienny.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="e5cf3-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-123">Click Save.</span></span>
14. <span data-ttu-id="e5cf3-124">W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt stały”.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="e5cf3-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-125">Click New.</span></span>
16. <span data-ttu-id="e5cf3-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="e5cf3-127">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-128">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="e5cf3-129">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-130">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="e5cf3-131">W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt zmienny”.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="e5cf3-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-132">Click New.</span></span>
21. <span data-ttu-id="e5cf3-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="e5cf3-134">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-135">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="e5cf3-136">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-137">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="e5cf3-138">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="e5cf3-139">Tworzenie zasady i reguł</span><span class="sxs-lookup"><span data-stu-id="e5cf3-139">Create the policy and rules</span></span>
1. <span data-ttu-id="e5cf3-140">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady zachowania kosztów.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="e5cf3-141">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-141">Click New.</span></span>
3. <span data-ttu-id="e5cf3-142">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="e5cf3-143">W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-144">Zaznacz utworzoną właśnie hierarchię zasad.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="e5cf3-145">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-146">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-146">Select Organization.</span></span>  
6. <span data-ttu-id="e5cf3-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-147">Click Save.</span></span>
7. <span data-ttu-id="e5cf3-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-148">Click New.</span></span>
8. <span data-ttu-id="e5cf3-149">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="e5cf3-150">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-151">Rozwiń hierarchię i wybierz pozycję Koszt zmienny.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="e5cf3-152">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="e5cf3-153">Domyślnie zmienny procent wynosi 100 procent.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="e5cf3-154">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="e5cf3-155">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-155">Click New.</span></span>
13. <span data-ttu-id="e5cf3-156">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="e5cf3-157">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="e5cf3-158">Reguły mają daty obowiązywania, tzn. użytkownik lub system mogą wygasić regułę, jeśli zostanie utworzona nowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="e5cf3-159">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="e5cf3-160">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e5cf3-160">Click Save.</span></span>

