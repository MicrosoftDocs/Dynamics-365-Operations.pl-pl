--- 
title: "Utwórz grupowo oferty sprzedaży"
description: "Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e3bc39912d19880258ff7dd56c74b77b52deda3a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="e82a4-103">Utwórz grupowo oferty sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e82a4-103">Mass create sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e82a4-104">Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="e82a4-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="e82a4-105">Ta operacja grupowego tworzenia ofert bazuje na szablonach ofert.</span><span class="sxs-lookup"><span data-stu-id="e82a4-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="e82a4-106">Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e82a4-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="e82a4-107">Tworzenie szablonu oferty</span><span class="sxs-lookup"><span data-stu-id="e82a4-107">Create a quotation template</span></span>
1. <span data-ttu-id="e82a4-108">Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Oferty > Grupy szablonów.</span><span class="sxs-lookup"><span data-stu-id="e82a4-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="e82a4-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e82a4-109">Click New.</span></span>
3. <span data-ttu-id="e82a4-110">W polu Identyfikator grupy wpisz dowolny identyfikator.</span><span class="sxs-lookup"><span data-stu-id="e82a4-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="e82a4-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="e82a4-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e82a4-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e82a4-112">Click Save.</span></span>
6. <span data-ttu-id="e82a4-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-113">Close the page.</span></span>
7. <span data-ttu-id="e82a4-114">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="e82a4-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="e82a4-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e82a4-115">Click New.</span></span>
9. <span data-ttu-id="e82a4-116">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="e82a4-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="e82a4-117">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="e82a4-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e82a4-118">Click OK.</span></span>
    * <span data-ttu-id="e82a4-119">Aby oferta stała się szablonem, trzeba wykonać czynności konfiguracyjne w nagłówku oferty.</span><span class="sxs-lookup"><span data-stu-id="e82a4-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="e82a4-120">Należy to zrobić przed dodaniem wierszy do oferty.</span><span class="sxs-lookup"><span data-stu-id="e82a4-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="e82a4-121">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="e82a4-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="e82a4-122">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="e82a4-122">Click Change view.</span></span>
14. <span data-ttu-id="e82a4-123">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="e82a4-123">Click Header view.</span></span>
15. <span data-ttu-id="e82a4-124">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="e82a4-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="e82a4-125">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="e82a4-126">W polu Nazwa szablonu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="e82a4-127">W polu Aktywny wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e82a4-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="e82a4-128">Podczas stosowania szablonu do nowej oferty sprzedaży można używać tylko aktywnych szablonów.</span><span class="sxs-lookup"><span data-stu-id="e82a4-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="e82a4-129">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="e82a4-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="e82a4-130">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="e82a4-130">Click Change view.</span></span>
21. <span data-ttu-id="e82a4-131">Kliknij opcję Widok wiersza.</span><span class="sxs-lookup"><span data-stu-id="e82a4-131">Click Line view.</span></span>
22. <span data-ttu-id="e82a4-132">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="e82a4-133">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="e82a4-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-134">Close the page.</span></span>
25. <span data-ttu-id="e82a4-135">W polu Procent rabatu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="e82a4-136">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="e82a4-136">Click Add line.</span></span>
27. <span data-ttu-id="e82a4-137">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="e82a4-138">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="e82a4-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-139">Close the page.</span></span>
30. <span data-ttu-id="e82a4-140">W polu Cena jednostkowa wprowadź nową cenę lub zmień bieżącą.</span><span class="sxs-lookup"><span data-stu-id="e82a4-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="e82a4-141">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="e82a4-141">Click Add line.</span></span>
32. <span data-ttu-id="e82a4-142">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="e82a4-143">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="e82a4-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-144">Close the page.</span></span>
35. <span data-ttu-id="e82a4-145">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="e82a4-146">W polu Rabat wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="e82a4-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e82a4-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="e82a4-148">Używanie szablonu do utworzenia pojedynczej oferty</span><span class="sxs-lookup"><span data-stu-id="e82a4-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="e82a4-149">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="e82a4-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="e82a4-150">Należy zwrócić uwagę, że utworzona właśnie oferta jest oznaczona jako szablon.</span><span class="sxs-lookup"><span data-stu-id="e82a4-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="e82a4-151">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e82a4-151">Click New.</span></span>
3. <span data-ttu-id="e82a4-152">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="e82a4-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="e82a4-153">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="e82a4-154">Rozwiń sekcję Szablon.</span><span class="sxs-lookup"><span data-stu-id="e82a4-154">Expand the Template section.</span></span>
6. <span data-ttu-id="e82a4-155">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="e82a4-156">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="e82a4-157">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="e82a4-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="e82a4-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e82a4-158">Click OK.</span></span>
    * <span data-ttu-id="e82a4-159">Nowa oferta została utworzona na podstawie danych i warunków szablonu.</span><span class="sxs-lookup"><span data-stu-id="e82a4-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="e82a4-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-160">Close the page.</span></span>
11. <span data-ttu-id="e82a4-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e82a4-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="e82a4-162">Używanie szablonu do grupowego tworzenia ofert</span><span class="sxs-lookup"><span data-stu-id="e82a4-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="e82a4-163">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Aktualizacja oferty > Utwórz grupowo oferty.</span><span class="sxs-lookup"><span data-stu-id="e82a4-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="e82a4-164">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="e82a4-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="e82a4-165">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="e82a4-166">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e82a4-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="e82a4-167">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="e82a4-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="e82a4-168">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="e82a4-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="e82a4-169">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="e82a4-169">Click Filter.</span></span>
8. <span data-ttu-id="e82a4-170">W polu Kryteria ustaw filtr, aby uwzględnić zakres odbiorców, którzy mają zostać uwzględnieni w tej operacji grupowego tworzenia ofert.</span><span class="sxs-lookup"><span data-stu-id="e82a4-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="e82a4-171">Użyj następującego formatu: „Odbiorca1..OdbiorcaN.</span><span class="sxs-lookup"><span data-stu-id="e82a4-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="e82a4-172">Na przykład można ustawić filtr na US-001..US-004.</span><span class="sxs-lookup"><span data-stu-id="e82a4-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="e82a4-173">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e82a4-173">Click OK.</span></span>
10. <span data-ttu-id="e82a4-174">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e82a4-174">Click OK.</span></span>
11. <span data-ttu-id="e82a4-175">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="e82a4-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="e82a4-176">Sprawdź, czy oferty zostały utworzone dla wszystkich odbiorców określonych w procedury aktualizacji grupowej zgodnie z wybranym szablonem.</span><span class="sxs-lookup"><span data-stu-id="e82a4-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  


