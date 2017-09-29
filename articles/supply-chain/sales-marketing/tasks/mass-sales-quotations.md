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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1fcb2c4d47f0c8e701be025e0554ed476693d732
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="f67eb-103">Utwórz grupowo oferty sprzedaży</span><span class="sxs-lookup"><span data-stu-id="f67eb-103">Mass create sales quotations</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f67eb-104">Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="f67eb-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="f67eb-105">Ta operacja grupowego tworzenia ofert bazuje na szablonach ofert.</span><span class="sxs-lookup"><span data-stu-id="f67eb-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="f67eb-106">Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f67eb-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="f67eb-107">Tworzenie szablonu oferty</span><span class="sxs-lookup"><span data-stu-id="f67eb-107">Create a quotation template</span></span>
1. <span data-ttu-id="f67eb-108">Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Oferty > Grupy szablonów.</span><span class="sxs-lookup"><span data-stu-id="f67eb-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="f67eb-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f67eb-109">Click New.</span></span>
3. <span data-ttu-id="f67eb-110">W polu Identyfikator grupy wpisz dowolny identyfikator.</span><span class="sxs-lookup"><span data-stu-id="f67eb-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="f67eb-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="f67eb-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f67eb-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f67eb-112">Click Save.</span></span>
6. <span data-ttu-id="f67eb-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-113">Close the page.</span></span>
7. <span data-ttu-id="f67eb-114">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="f67eb-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="f67eb-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f67eb-115">Click New.</span></span>
9. <span data-ttu-id="f67eb-116">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="f67eb-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="f67eb-117">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="f67eb-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f67eb-118">Click OK.</span></span>
    * <span data-ttu-id="f67eb-119">Aby oferta stała się szablonem, trzeba wykonać czynności konfiguracyjne w nagłówku oferty.</span><span class="sxs-lookup"><span data-stu-id="f67eb-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="f67eb-120">Należy to zrobić przed dodaniem wierszy do oferty.</span><span class="sxs-lookup"><span data-stu-id="f67eb-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="f67eb-121">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="f67eb-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="f67eb-122">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="f67eb-122">Click Change view.</span></span>
14. <span data-ttu-id="f67eb-123">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="f67eb-123">Click Header view.</span></span>
15. <span data-ttu-id="f67eb-124">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="f67eb-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="f67eb-125">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="f67eb-126">W polu Nazwa szablonu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="f67eb-127">W polu Aktywny wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="f67eb-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="f67eb-128">Podczas stosowania szablonu do nowej oferty sprzedaży można używać tylko aktywnych szablonów.</span><span class="sxs-lookup"><span data-stu-id="f67eb-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="f67eb-129">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="f67eb-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="f67eb-130">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="f67eb-130">Click Change view.</span></span>
21. <span data-ttu-id="f67eb-131">Kliknij opcję Widok wiersza.</span><span class="sxs-lookup"><span data-stu-id="f67eb-131">Click Line view.</span></span>
22. <span data-ttu-id="f67eb-132">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="f67eb-133">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="f67eb-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-134">Close the page.</span></span>
25. <span data-ttu-id="f67eb-135">W polu Procent rabatu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="f67eb-136">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="f67eb-136">Click Add line.</span></span>
27. <span data-ttu-id="f67eb-137">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="f67eb-138">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="f67eb-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-139">Close the page.</span></span>
30. <span data-ttu-id="f67eb-140">W polu Cena jednostkowa wprowadź nową cenę lub zmień bieżącą.</span><span class="sxs-lookup"><span data-stu-id="f67eb-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="f67eb-141">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="f67eb-141">Click Add line.</span></span>
32. <span data-ttu-id="f67eb-142">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="f67eb-143">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="f67eb-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-144">Close the page.</span></span>
35. <span data-ttu-id="f67eb-145">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="f67eb-146">W polu Rabat wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="f67eb-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f67eb-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="f67eb-148">Używanie szablonu do utworzenia pojedynczej oferty</span><span class="sxs-lookup"><span data-stu-id="f67eb-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="f67eb-149">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="f67eb-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="f67eb-150">Należy zwrócić uwagę, że utworzona właśnie oferta jest oznaczona jako szablon.</span><span class="sxs-lookup"><span data-stu-id="f67eb-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="f67eb-151">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f67eb-151">Click New.</span></span>
3. <span data-ttu-id="f67eb-152">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="f67eb-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="f67eb-153">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="f67eb-154">Rozwiń sekcję Szablon.</span><span class="sxs-lookup"><span data-stu-id="f67eb-154">Expand the Template section.</span></span>
6. <span data-ttu-id="f67eb-155">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="f67eb-156">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="f67eb-157">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="f67eb-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="f67eb-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f67eb-158">Click OK.</span></span>
    * <span data-ttu-id="f67eb-159">Nowa oferta została utworzona na podstawie danych i warunków szablonu.</span><span class="sxs-lookup"><span data-stu-id="f67eb-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="f67eb-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-160">Close the page.</span></span>
11. <span data-ttu-id="f67eb-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f67eb-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="f67eb-162">Używanie szablonu do grupowego tworzenia ofert</span><span class="sxs-lookup"><span data-stu-id="f67eb-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="f67eb-163">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Aktualizacja oferty > Utwórz grupowo oferty.</span><span class="sxs-lookup"><span data-stu-id="f67eb-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="f67eb-164">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="f67eb-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="f67eb-165">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="f67eb-166">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f67eb-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="f67eb-167">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="f67eb-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="f67eb-168">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="f67eb-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="f67eb-169">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="f67eb-169">Click Filter.</span></span>
8. <span data-ttu-id="f67eb-170">W polu Kryteria ustaw filtr, aby uwzględnić zakres odbiorców, którzy mają zostać uwzględnieni w tej operacji grupowego tworzenia ofert.</span><span class="sxs-lookup"><span data-stu-id="f67eb-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="f67eb-171">Użyj następującego formatu: „Odbiorca1..OdbiorcaN.</span><span class="sxs-lookup"><span data-stu-id="f67eb-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="f67eb-172">Na przykład można ustawić filtr na US-001..US-004.</span><span class="sxs-lookup"><span data-stu-id="f67eb-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="f67eb-173">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f67eb-173">Click OK.</span></span>
10. <span data-ttu-id="f67eb-174">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f67eb-174">Click OK.</span></span>
11. <span data-ttu-id="f67eb-175">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="f67eb-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="f67eb-176">Sprawdź, czy oferty zostały utworzone dla wszystkich odbiorców określonych w procedury aktualizacji grupowej zgodnie z wybranym szablonem.</span><span class="sxs-lookup"><span data-stu-id="f67eb-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  


