---
title: Tworzenie planu materiałów dla produktów towarzyszących
description: Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920736"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="5baa5-103">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="5baa5-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5baa5-104">Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.</span><span class="sxs-lookup"><span data-stu-id="5baa5-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="5baa5-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="5baa5-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="5baa5-106">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="5baa5-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="5baa5-107">Przejdź do lokalizacji **Sprzedaż i marketing \> Obszary robocze \> Przetwarzanie zamówienia sprzedaży i zapytania o nie**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="5baa5-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-108">Select **New**.</span></span>
1. <span data-ttu-id="5baa5-109">Wybierz opcję **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="5baa5-110">W polu **Konto odbiorcy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5baa5-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="5baa5-111">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="5baa5-111">Example: US-001</span></span>  
1. <span data-ttu-id="5baa5-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-112">Select **OK**.</span></span>
1. <span data-ttu-id="5baa5-113">W polu **Numer towaru** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5baa5-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="5baa5-114">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="5baa5-114">Example: P6003</span></span>  
1. <span data-ttu-id="5baa5-115">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="5baa5-116">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="5baa5-116">Example: 50000</span></span>  
1. <span data-ttu-id="5baa5-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="5baa5-118">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="5baa5-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="5baa5-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-119">Close the page.</span></span>
1. <span data-ttu-id="5baa5-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-120">Close the page.</span></span>
1. <span data-ttu-id="5baa5-121">Wybierz opcję **Planowanie główne**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="5baa5-122">W polu **Plan** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5baa5-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="5baa5-123">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5baa5-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="5baa5-124">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="5baa5-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="5baa5-125">Wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-125">Select **Run**.</span></span>
1. <span data-ttu-id="5baa5-126">Rozwiń lub zwiń sekcję **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="5baa5-127">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-127">Select **Filter**.</span></span>
1. <span data-ttu-id="5baa5-128">Na liście zaznacz wiersz, gdzie **Pole** = *Numer towaru*.</span><span class="sxs-lookup"><span data-stu-id="5baa5-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="5baa5-129">W polu **Kryteria** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5baa5-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="5baa5-130">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="5baa5-130">Example: P6003</span></span>  
1. <span data-ttu-id="5baa5-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-131">Select **OK**.</span></span>
1. <span data-ttu-id="5baa5-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-132">Select **OK**.</span></span>
1. <span data-ttu-id="5baa5-133">Wybierz **Zamówienia planowane**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="5baa5-134">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="5baa5-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5baa5-135">Na przykład ustaw filtr na pole **Numer towaru** z wartością 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="5baa5-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="5baa5-136">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5baa5-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="5baa5-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="5baa5-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5baa5-138">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="5baa5-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="5baa5-139">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5baa5-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="5baa5-140">Rozwiń sekcję **Oznaczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="5baa5-141">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5baa5-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="5baa5-142">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="5baa5-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="5baa5-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="5baa5-144">Tworzenie drugiego zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="5baa5-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="5baa5-145">Przejdź do lokalizacji **Sprzedaż i marketing \> Obszary robocze \> Przetwarzanie zamówienia sprzedaży i zapytania o nie**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="5baa5-146">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-146">Select **New**.</span></span>
1. <span data-ttu-id="5baa5-147">Wybierz opcję **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="5baa5-148">W polu **Konto odbiorcy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5baa5-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="5baa5-149">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="5baa5-149">Example: US-001</span></span>  
1. <span data-ttu-id="5baa5-150">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-150">Select **OK**.</span></span>
1. <span data-ttu-id="5baa5-151">W polu **Numer towaru** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5baa5-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="5baa5-152">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="5baa5-152">Example: P6003</span></span>  
1. <span data-ttu-id="5baa5-153">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="5baa5-154">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="5baa5-154">Example: 50000</span></span>  
1. <span data-ttu-id="5baa5-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="5baa5-156">Tworzenie drugiego planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="5baa5-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="5baa5-157">W polu **Plan** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5baa5-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="5baa5-158">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5baa5-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="5baa5-159">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="5baa5-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="5baa5-160">Wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-160">Select **Run**.</span></span>
4. <span data-ttu-id="5baa5-161">Rozwiń lub zwiń sekcję **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="5baa5-162">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-162">Select **Filter**.</span></span>
6. <span data-ttu-id="5baa5-163">Na liście zaznacz wiersz, gdzie **Pole** = *Numer towaru*.</span><span class="sxs-lookup"><span data-stu-id="5baa5-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="5baa5-164">W polu *Kryteria* wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5baa5-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="5baa5-165">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="5baa5-165">Example: P6003</span></span>  
8. <span data-ttu-id="5baa5-166">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-166">Select **OK**.</span></span>
9. <span data-ttu-id="5baa5-167">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-167">Select **OK**.</span></span>
10. <span data-ttu-id="5baa5-168">Wybierz **Zamówienia planowane**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="5baa5-169">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="5baa5-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5baa5-170">Na przykład ustaw filtr na pole **Numer towaru** z wartością 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="5baa5-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="5baa5-171">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5baa5-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="5baa5-172">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="5baa5-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5baa5-173">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="5baa5-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="5baa5-174">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5baa5-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="5baa5-175">Rozwiń lub zwiń sekcję **Oznaczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="5baa5-176">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5baa5-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="5baa5-177">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="5baa5-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="5baa5-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-178">Close the page.</span></span>
17. <span data-ttu-id="5baa5-179">Wybierz opcję **Planowanie główne**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="5baa5-180">Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Parametry planowania głównego**.</span><span class="sxs-lookup"><span data-stu-id="5baa5-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="5baa5-181">W polu **Wyłącz wszystkie procesy planowania** wybierz opcję *Nie*.</span><span class="sxs-lookup"><span data-stu-id="5baa5-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="5baa5-182">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5baa5-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]