---
title: Utwórz grupowo oferty sprzedaży
description: Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77f7a2df813eb0bf211b72646c1e99306fdf3f88
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148614"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="dcb43-103">Utwórz grupowo oferty sprzedaży</span><span class="sxs-lookup"><span data-stu-id="dcb43-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dcb43-104">Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="dcb43-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="dcb43-105">Ta operacja grupowego tworzenia ofert bazuje na szablonach ofert.</span><span class="sxs-lookup"><span data-stu-id="dcb43-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="dcb43-106">Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="dcb43-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="dcb43-107">Tworzenie szablonu oferty</span><span class="sxs-lookup"><span data-stu-id="dcb43-107">Create a quotation template</span></span>
1. <span data-ttu-id="dcb43-108">Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Oferty > Grupy szablonów.</span><span class="sxs-lookup"><span data-stu-id="dcb43-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="dcb43-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dcb43-109">Click New.</span></span>
3. <span data-ttu-id="dcb43-110">W polu Identyfikator grupy wpisz dowolny identyfikator.</span><span class="sxs-lookup"><span data-stu-id="dcb43-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="dcb43-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dcb43-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dcb43-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dcb43-112">Click Save.</span></span>
6. <span data-ttu-id="dcb43-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-113">Close the page.</span></span>
7. <span data-ttu-id="dcb43-114">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="dcb43-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="dcb43-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dcb43-115">Click New.</span></span>
9. <span data-ttu-id="dcb43-116">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="dcb43-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="dcb43-117">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="dcb43-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dcb43-118">Click OK.</span></span>
    * <span data-ttu-id="dcb43-119">Aby oferta stała się szablonem, trzeba wykonać czynności konfiguracyjne w nagłówku oferty.</span><span class="sxs-lookup"><span data-stu-id="dcb43-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="dcb43-120">Należy to zrobić przed dodaniem wierszy do oferty.</span><span class="sxs-lookup"><span data-stu-id="dcb43-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="dcb43-121">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="dcb43-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="dcb43-122">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="dcb43-122">Click Change view.</span></span>
14. <span data-ttu-id="dcb43-123">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="dcb43-123">Click Header view.</span></span>
15. <span data-ttu-id="dcb43-124">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="dcb43-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="dcb43-125">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="dcb43-126">W polu Nazwa szablonu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="dcb43-127">W polu Aktywny wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="dcb43-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="dcb43-128">Podczas stosowania szablonu do nowej oferty sprzedaży można używać tylko aktywnych szablonów.</span><span class="sxs-lookup"><span data-stu-id="dcb43-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="dcb43-129">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="dcb43-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="dcb43-130">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="dcb43-130">Click Change view.</span></span>
21. <span data-ttu-id="dcb43-131">Kliknij opcję Widok wiersza.</span><span class="sxs-lookup"><span data-stu-id="dcb43-131">Click Line view.</span></span>
22. <span data-ttu-id="dcb43-132">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="dcb43-133">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="dcb43-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-134">Close the page.</span></span>
25. <span data-ttu-id="dcb43-135">W polu Procent rabatu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="dcb43-136">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="dcb43-136">Click Add line.</span></span>
27. <span data-ttu-id="dcb43-137">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="dcb43-138">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="dcb43-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-139">Close the page.</span></span>
30. <span data-ttu-id="dcb43-140">W polu Cena jednostkowa wprowadź nową cenę lub zmień bieżącą.</span><span class="sxs-lookup"><span data-stu-id="dcb43-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="dcb43-141">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="dcb43-141">Click Add line.</span></span>
32. <span data-ttu-id="dcb43-142">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="dcb43-143">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="dcb43-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-144">Close the page.</span></span>
35. <span data-ttu-id="dcb43-145">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="dcb43-146">W polu Rabat wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="dcb43-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dcb43-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="dcb43-148">Używanie szablonu do utworzenia pojedynczej oferty</span><span class="sxs-lookup"><span data-stu-id="dcb43-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="dcb43-149">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="dcb43-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="dcb43-150">Należy zwrócić uwagę, że utworzona właśnie oferta jest oznaczona jako szablon.</span><span class="sxs-lookup"><span data-stu-id="dcb43-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="dcb43-151">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dcb43-151">Click New.</span></span>
3. <span data-ttu-id="dcb43-152">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="dcb43-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="dcb43-153">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="dcb43-154">Rozwiń sekcję Szablon.</span><span class="sxs-lookup"><span data-stu-id="dcb43-154">Expand the Template section.</span></span>
6. <span data-ttu-id="dcb43-155">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="dcb43-156">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="dcb43-157">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="dcb43-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="dcb43-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dcb43-158">Click OK.</span></span>
    * <span data-ttu-id="dcb43-159">Nowa oferta została utworzona na podstawie danych i warunków szablonu.</span><span class="sxs-lookup"><span data-stu-id="dcb43-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="dcb43-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-160">Close the page.</span></span>
11. <span data-ttu-id="dcb43-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dcb43-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="dcb43-162">Używanie szablonu do grupowego tworzenia ofert</span><span class="sxs-lookup"><span data-stu-id="dcb43-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="dcb43-163">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Aktualizacja oferty > Utwórz grupowo oferty.</span><span class="sxs-lookup"><span data-stu-id="dcb43-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="dcb43-164">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="dcb43-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="dcb43-165">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="dcb43-166">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dcb43-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="dcb43-167">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="dcb43-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="dcb43-168">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="dcb43-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="dcb43-169">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="dcb43-169">Click Filter.</span></span>
8. <span data-ttu-id="dcb43-170">W polu Kryteria ustaw filtr, aby uwzględnić zakres odbiorców, którzy mają zostać uwzględnieni w tej operacji grupowego tworzenia ofert.</span><span class="sxs-lookup"><span data-stu-id="dcb43-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="dcb43-171">Użyj następującego formatu: „Odbiorca1..OdbiorcaN.</span><span class="sxs-lookup"><span data-stu-id="dcb43-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="dcb43-172">Na przykład można ustawić filtr na US-001..US-004.</span><span class="sxs-lookup"><span data-stu-id="dcb43-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="dcb43-173">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dcb43-173">Click OK.</span></span>
10. <span data-ttu-id="dcb43-174">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dcb43-174">Click OK.</span></span>
11. <span data-ttu-id="dcb43-175">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="dcb43-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="dcb43-176">Sprawdź, czy oferty zostały utworzone dla wszystkich odbiorców określonych w procedury aktualizacji grupowej zgodnie z wybranym szablonem.</span><span class="sxs-lookup"><span data-stu-id="dcb43-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  

