---
title: Utwórz grupowo oferty sprzedaży
description: Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0422817576d9d93d0ec6bbfb5f3777013ee09ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817708"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="8207f-103">Utwórz grupowo oferty sprzedaży</span><span class="sxs-lookup"><span data-stu-id="8207f-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8207f-104">Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="8207f-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="8207f-105">Ta operacja grupowego tworzenia ofert bazuje na szablonach ofert.</span><span class="sxs-lookup"><span data-stu-id="8207f-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="8207f-106">Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8207f-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="8207f-107">Tworzenie szablonu oferty</span><span class="sxs-lookup"><span data-stu-id="8207f-107">Create a quotation template</span></span>
1. <span data-ttu-id="8207f-108">Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Oferty > Grupy szablonów.</span><span class="sxs-lookup"><span data-stu-id="8207f-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="8207f-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8207f-109">Click New.</span></span>
3. <span data-ttu-id="8207f-110">W polu Identyfikator grupy wpisz dowolny identyfikator.</span><span class="sxs-lookup"><span data-stu-id="8207f-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="8207f-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="8207f-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8207f-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8207f-112">Click Save.</span></span>
6. <span data-ttu-id="8207f-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8207f-113">Close the page.</span></span>
7. <span data-ttu-id="8207f-114">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="8207f-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="8207f-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8207f-115">Click New.</span></span>
9. <span data-ttu-id="8207f-116">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="8207f-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="8207f-117">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="8207f-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8207f-118">Click OK.</span></span>
    * <span data-ttu-id="8207f-119">Aby oferta stała się szablonem, trzeba wykonać czynności konfiguracyjne w nagłówku oferty.</span><span class="sxs-lookup"><span data-stu-id="8207f-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="8207f-120">Należy to zrobić przed dodaniem wierszy do oferty.</span><span class="sxs-lookup"><span data-stu-id="8207f-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="8207f-121">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="8207f-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="8207f-122">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="8207f-122">Click Change view.</span></span>
14. <span data-ttu-id="8207f-123">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="8207f-123">Click Header view.</span></span>
15. <span data-ttu-id="8207f-124">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="8207f-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="8207f-125">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="8207f-126">W polu Nazwa szablonu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="8207f-127">W polu Aktywny wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8207f-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="8207f-128">Podczas stosowania szablonu do nowej oferty sprzedaży można używać tylko aktywnych szablonów.</span><span class="sxs-lookup"><span data-stu-id="8207f-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="8207f-129">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="8207f-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="8207f-130">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="8207f-130">Click Change view.</span></span>
21. <span data-ttu-id="8207f-131">Kliknij opcję Widok wiersza.</span><span class="sxs-lookup"><span data-stu-id="8207f-131">Click Line view.</span></span>
22. <span data-ttu-id="8207f-132">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="8207f-133">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="8207f-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8207f-134">Close the page.</span></span>
25. <span data-ttu-id="8207f-135">W polu Procent rabatu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8207f-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="8207f-136">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="8207f-136">Click Add line.</span></span>
27. <span data-ttu-id="8207f-137">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="8207f-138">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="8207f-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8207f-139">Close the page.</span></span>
30. <span data-ttu-id="8207f-140">W polu Cena jednostkowa wprowadź nową cenę lub zmień bieżącą.</span><span class="sxs-lookup"><span data-stu-id="8207f-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="8207f-141">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="8207f-141">Click Add line.</span></span>
32. <span data-ttu-id="8207f-142">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="8207f-143">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="8207f-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8207f-144">Close the page.</span></span>
35. <span data-ttu-id="8207f-145">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="8207f-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="8207f-146">W polu Rabat wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8207f-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="8207f-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8207f-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="8207f-148">Używanie szablonu do utworzenia pojedynczej oferty</span><span class="sxs-lookup"><span data-stu-id="8207f-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="8207f-149">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="8207f-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="8207f-150">Należy zwrócić uwagę, że utworzona właśnie oferta jest oznaczona jako szablon.</span><span class="sxs-lookup"><span data-stu-id="8207f-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="8207f-151">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8207f-151">Click New.</span></span>
3. <span data-ttu-id="8207f-152">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="8207f-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="8207f-153">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="8207f-154">Rozwiń sekcję Szablon.</span><span class="sxs-lookup"><span data-stu-id="8207f-154">Expand the Template section.</span></span>
6. <span data-ttu-id="8207f-155">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="8207f-156">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="8207f-157">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="8207f-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="8207f-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8207f-158">Click OK.</span></span>
    * <span data-ttu-id="8207f-159">Nowa oferta została utworzona na podstawie danych i warunków szablonu.</span><span class="sxs-lookup"><span data-stu-id="8207f-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="8207f-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8207f-160">Close the page.</span></span>
11. <span data-ttu-id="8207f-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8207f-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="8207f-162">Używanie szablonu do grupowego tworzenia ofert</span><span class="sxs-lookup"><span data-stu-id="8207f-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="8207f-163">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Aktualizacja oferty > Utwórz grupowo oferty.</span><span class="sxs-lookup"><span data-stu-id="8207f-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="8207f-164">W polu Typ konta wybierz wartość „Odbiorca”.</span><span class="sxs-lookup"><span data-stu-id="8207f-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="8207f-165">W polu Identyfikator grupy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="8207f-166">W polu Nazwa szablonu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8207f-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="8207f-167">W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.</span><span class="sxs-lookup"><span data-stu-id="8207f-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="8207f-168">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="8207f-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="8207f-169">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="8207f-169">Click Filter.</span></span>
8. <span data-ttu-id="8207f-170">W polu Kryteria ustaw filtr, aby uwzględnić zakres odbiorców, którzy mają zostać uwzględnieni w tej operacji grupowego tworzenia ofert.</span><span class="sxs-lookup"><span data-stu-id="8207f-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="8207f-171">Użyj następującego formatu: „Odbiorca1..OdbiorcaN.</span><span class="sxs-lookup"><span data-stu-id="8207f-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="8207f-172">Na przykład można ustawić filtr na US-001..US-004.</span><span class="sxs-lookup"><span data-stu-id="8207f-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="8207f-173">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8207f-173">Click OK.</span></span>
10. <span data-ttu-id="8207f-174">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8207f-174">Click OK.</span></span>
11. <span data-ttu-id="8207f-175">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="8207f-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="8207f-176">Sprawdź, czy oferty zostały utworzone dla wszystkich odbiorców określonych w procedury aktualizacji grupowej zgodnie z wybranym szablonem.</span><span class="sxs-lookup"><span data-stu-id="8207f-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]