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
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58f888a373af33832c24518fbb5483c3de2d1a58
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208710"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="cd2ae-103">Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="cd2ae-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd2ae-104">Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="cd2ae-105">Aby zasada weszła w życie, sama zasada i odpowiednie reguły muszą być przypisane do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="cd2ae-106">Ta procedura służy do tworzenia zasady, a następnie jej przypisywania do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="cd2ae-107">Tworzenie hierarchii zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="cd2ae-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="cd2ae-108">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="cd2ae-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-109">Click New.</span></span>
3. <span data-ttu-id="cd2ae-110">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-110">Click Create.</span></span>
4. <span data-ttu-id="cd2ae-111">W polu Nazwa hierarchii wymiarów wpisz „Hierarchia zachowania kosztów”.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="cd2ae-112">W polu Wymiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-113">Wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="cd2ae-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-114">Click Save.</span></span>
7. <span data-ttu-id="cd2ae-115">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="cd2ae-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-116">Click New.</span></span>
9. <span data-ttu-id="cd2ae-117">W polu Nazwa węzła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="cd2ae-118">Wypełnij pole Koszt stały.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="cd2ae-119">W drzewie zaznacz pozycję „Hierarchia zachowania kosztów”.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="cd2ae-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-120">Click New.</span></span>
12. <span data-ttu-id="cd2ae-121">W polu Nazwa węzła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="cd2ae-122">Wypełnij pole Koszt zmienny.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="cd2ae-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-123">Click Save.</span></span>
14. <span data-ttu-id="cd2ae-124">W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt stały”.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="cd2ae-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-125">Click New.</span></span>
16. <span data-ttu-id="cd2ae-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="cd2ae-127">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-128">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="cd2ae-129">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-130">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="cd2ae-131">W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt zmienny”.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="cd2ae-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-132">Click New.</span></span>
21. <span data-ttu-id="cd2ae-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="cd2ae-134">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-135">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="cd2ae-136">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-137">Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="cd2ae-138">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="cd2ae-139">Tworzenie zasady i reguł</span><span class="sxs-lookup"><span data-stu-id="cd2ae-139">Create the policy and rules</span></span>
1. <span data-ttu-id="cd2ae-140">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady zachowania kosztów.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="cd2ae-141">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-141">Click New.</span></span>
3. <span data-ttu-id="cd2ae-142">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="cd2ae-143">W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-144">Zaznacz utworzoną właśnie hierarchię zasad.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="cd2ae-145">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-146">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-146">Select Organization.</span></span>  
6. <span data-ttu-id="cd2ae-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-147">Click Save.</span></span>
7. <span data-ttu-id="cd2ae-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-148">Click New.</span></span>
8. <span data-ttu-id="cd2ae-149">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="cd2ae-150">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-151">Rozwiń hierarchię i wybierz pozycję Koszt zmienny.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="cd2ae-152">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="cd2ae-153">Domyślnie zmienny procent wynosi 100 procent.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="cd2ae-154">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="cd2ae-155">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-155">Click New.</span></span>
13. <span data-ttu-id="cd2ae-156">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="cd2ae-157">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="cd2ae-158">Reguły mają daty obowiązywania, tzn. użytkownik lub system mogą wygasić regułę, jeśli zostanie utworzona nowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="cd2ae-159">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="cd2ae-160">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cd2ae-160">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]