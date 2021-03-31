---
title: Tworzenie planu materiałów dla produktów towarzyszących
description: Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a87935f8f30d909f1a6a62ed7be00c83476a36a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214377"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ff668-103">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="ff668-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ff668-104">Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.</span><span class="sxs-lookup"><span data-stu-id="ff668-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="ff668-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="ff668-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="ff668-106">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="ff668-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="ff668-107">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="ff668-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="ff668-108">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="ff668-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="ff668-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ff668-109">Click New.</span></span>
4. <span data-ttu-id="ff668-110">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff668-110">Click Sales order.</span></span>
5. <span data-ttu-id="ff668-111">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff668-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="ff668-112">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="ff668-112">Example: US-001</span></span>  
6. <span data-ttu-id="ff668-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff668-113">Click OK.</span></span>
7. <span data-ttu-id="ff668-114">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff668-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ff668-115">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="ff668-115">Example: P6003</span></span>  
8. <span data-ttu-id="ff668-116">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ff668-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ff668-117">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="ff668-117">Example: 50000</span></span>  
9. <span data-ttu-id="ff668-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ff668-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ff668-119">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="ff668-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="ff668-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff668-120">Close the page.</span></span>
2. <span data-ttu-id="ff668-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff668-121">Close the page.</span></span>
3. <span data-ttu-id="ff668-122">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="ff668-122">Click Master planning.</span></span>
4. <span data-ttu-id="ff668-123">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ff668-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ff668-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ff668-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ff668-125">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="ff668-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="ff668-126">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="ff668-126">Click Run.</span></span>
7. <span data-ttu-id="ff668-127">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="ff668-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="ff668-128">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="ff668-128">Click Filter.</span></span>
9. <span data-ttu-id="ff668-129">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="ff668-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="ff668-130">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff668-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="ff668-131">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="ff668-131">Example: P6003</span></span>  
11. <span data-ttu-id="ff668-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff668-132">Click OK.</span></span>
12. <span data-ttu-id="ff668-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff668-133">Click OK.</span></span>
13. <span data-ttu-id="ff668-134">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="ff668-134">Click Planned orders.</span></span>
14. <span data-ttu-id="ff668-135">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="ff668-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ff668-136">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="ff668-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="ff668-137">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff668-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="ff668-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ff668-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ff668-139">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="ff668-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="ff668-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ff668-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="ff668-141">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="ff668-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="ff668-142">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ff668-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ff668-143">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="ff668-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="ff668-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff668-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="ff668-145">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="ff668-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="ff668-146">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="ff668-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="ff668-147">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="ff668-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="ff668-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ff668-148">Click New.</span></span>
4. <span data-ttu-id="ff668-149">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff668-149">Click Sales order.</span></span>
5. <span data-ttu-id="ff668-150">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff668-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="ff668-151">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="ff668-151">Example: US-001</span></span>  
6. <span data-ttu-id="ff668-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff668-152">Click OK.</span></span>
7. <span data-ttu-id="ff668-153">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff668-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ff668-154">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="ff668-154">Example: P6003</span></span>  
8. <span data-ttu-id="ff668-155">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ff668-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ff668-156">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="ff668-156">Example: 50000</span></span>  
9. <span data-ttu-id="ff668-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ff668-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ff668-158">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="ff668-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="ff668-159">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ff668-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ff668-160">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ff668-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ff668-161">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="ff668-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="ff668-162">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="ff668-162">Click Run.</span></span>
4. <span data-ttu-id="ff668-163">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="ff668-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="ff668-164">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="ff668-164">Click Filter.</span></span>
6. <span data-ttu-id="ff668-165">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="ff668-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="ff668-166">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff668-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="ff668-167">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="ff668-167">Example: P6003</span></span>  
8. <span data-ttu-id="ff668-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff668-168">Click OK.</span></span>
9. <span data-ttu-id="ff668-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff668-169">Click OK.</span></span>
10. <span data-ttu-id="ff668-170">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="ff668-170">Click Planned orders.</span></span>
11. <span data-ttu-id="ff668-171">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="ff668-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ff668-172">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="ff668-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="ff668-173">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff668-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="ff668-174">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ff668-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ff668-175">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="ff668-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="ff668-176">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ff668-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="ff668-177">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="ff668-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="ff668-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ff668-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ff668-179">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="ff668-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="ff668-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff668-180">Close the page.</span></span>
17. <span data-ttu-id="ff668-181">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="ff668-181">Click Master planning.</span></span>
18. <span data-ttu-id="ff668-182">Wybierz kolejno opcje Planowanie główne > Ustawienia > Parametry planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="ff668-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="ff668-183">W polu Wyłącz wszystkie procesy planowania wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="ff668-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="ff668-184">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff668-184">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]