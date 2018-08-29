--- 
title: "Używanie konfiguracji mapowań modeli do obliczeń agregujących na poziomie bazy danych"
description: Ta procedura zawiera informacje na temat projektowania nowego mapowania modelu raportowania elektronicznego (ER) i stosowania wbudowanych funkcji ER w celu efektywnego obliczania agregacji.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: a462a3997644a494b5cea89c9530ddba67c32450
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a><span data-ttu-id="ac2c1-103">Używanie konfiguracji mapowań modeli do obliczeń agregujących na poziomie bazy danych</span><span class="sxs-lookup"><span data-stu-id="ac2c1-103">Use model mapping configurations for aggregate calculations at the database level</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac2c1-104">Ta procedura zawiera informacje na temat projektowania nowego mapowania modelu raportowania elektronicznego (ER) i stosowania wbudowanych funkcji ER w celu efektywnego obliczania agregacji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="ac2c1-105">Ta procedura dotyczy tworzenia konfiguracji dla przykładowej firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="ac2c1-106">Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="ac2c1-107">Kroki te można wykonać przy użyciu dowolnego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="ac2c1-108">Aby wykonać tę procedurę, należy najpierw wykonać kroki opisane w procedurze „Poprawa wydajności obliczeń agregacji przy użyciu ER poprzez wykonywanie ich na poziomie bazy danych (część 1: Przygotowywanie konfiguracji)”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-108">To complete these steps, you must first complete the steps in the procedure, “ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations).”</span></span>

1. <span data-ttu-id="ac2c1-109">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ac2c1-110">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="ac2c1-111">W drzewie wybierz kolejno elementy „Model Intrastat\Przykładowe mapowanie Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="ac2c1-112">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-112">Click Designer.</span></span>
5. <span data-ttu-id="ac2c1-113">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-113">Click Designer.</span></span>
6. <span data-ttu-id="ac2c1-114">W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="ac2c1-115">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-115">Click Add root.</span></span>
    * <span data-ttu-id="ac2c1-116">Dodaj nowe źródło danych reprezentujące rekordy, które chcesz zgrupować.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="ac2c1-117">W polu Nazwa wpisz „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="ac2c1-118">Transakcje</span><span class="sxs-lookup"><span data-stu-id="ac2c1-118">Transactions</span></span>  
9. <span data-ttu-id="ac2c1-119">W polu Tabela wpisz „Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="ac2c1-120">Intrastat</span><span class="sxs-lookup"><span data-stu-id="ac2c1-120">Intrastat</span></span>  
10. <span data-ttu-id="ac2c1-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-121">Click OK.</span></span>
11. <span data-ttu-id="ac2c1-122">W drzewie zaznacz element „Funkcje\Grupuj wg”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="ac2c1-123">Ten typ źródła danych jest używany do wprowadzania nowego źródła danych w czasie procesu w celu grupowania rekordów i obliczania wymaganych agregacji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="ac2c1-124">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-124">Click Add root.</span></span>
13. <span data-ttu-id="ac2c1-125">W polu Nazwa wpisz „TransactionsGroups”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="ac2c1-126">Grupy transakcji</span><span class="sxs-lookup"><span data-stu-id="ac2c1-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="ac2c1-127">Kliknij opcję Edytuj grupę według.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-127">Click Edit group by.</span></span>
15. <span data-ttu-id="ac2c1-128">W drzewie zaznacz element „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="ac2c1-129">Wybierz dodane źródło danych typu „Lista rekordów” reprezentujące rekordy, które chcesz grupować.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-129">Select the added data source of the ‘Record list’ type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="ac2c1-130">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-130">Click Add field to.</span></span>
17. <span data-ttu-id="ac2c1-131">Kliknij opcję Jakie elementy do grupowania.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-131">Click What to group.</span></span>
18. <span data-ttu-id="ac2c1-132">W drzewie rozwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="ac2c1-133">W drzewie wybierz kolejno elementy „Transakcje\Kierunek”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="ac2c1-134">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-134">Click Add field to.</span></span>
21. <span data-ttu-id="ac2c1-135">Kliknij opcję Zgrupowane pola.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="ac2c1-136">Zaznacz to pole, aby określić poziom grupowania.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="ac2c1-137">W zależności od tego zaznaczenia źródło danych będzie zwracać w czasie procesu tyle grup transakcji, ile jest kodów kierunku, które zostaną uwzględnione w tabeli Intrastat.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="ac2c1-138">W drzewie wybierz kolejno elementy „Transakcje\Kwota faktury(AmountMST)”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="ac2c1-139">Zaznacz to pole, aby określić źródło do obliczania agregacji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="ac2c1-140">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-140">Click Add field to.</span></span>
24. <span data-ttu-id="ac2c1-141">Kliknij opcje Pola agregacji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="ac2c1-142">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="ac2c1-143">W polu Metoda wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="ac2c1-144">Wybierz typ agregacji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="ac2c1-145">W polu nazwa wpisz „SumOfAmountMST”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="ac2c1-146">Określ nazwę tej agregacji w skonfigurowanym źródle danych.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="ac2c1-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-147">Click Save.</span></span>
    * <span data-ttu-id="ac2c1-148">Należy zwrócić uwagę, że pole „Wykonanie w” wskazuje, że grupowanie będzie wykonywane w czasie procesu w bazie danych SQL.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-148">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="ac2c1-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-149">Close the page.</span></span>
30. <span data-ttu-id="ac2c1-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-150">Click OK.</span></span>
31. <span data-ttu-id="ac2c1-151">W drzewie rozwiń węzeł „Sumy”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="ac2c1-152">W drzewie rozwiń węzeł „Grupy transakcji”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="ac2c1-153">W drzewie rozwiń węzeł „Grupy transakcji\Zagregowane”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="ac2c1-154">W drzewie wybierz kolejno elementy „Grupy transakcji\Zagregowane\SumOfAmountMST”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="ac2c1-155">W drzewie wybierz kolejno elementy „Sumy\Łączna wartość faktury(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="ac2c1-156">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-156">Click Bind.</span></span>
    * <span data-ttu-id="ac2c1-157">Na podstawie tego ustawienia to źródło danych będzie obliczać sumę wartości w polu „AmountMST” dla poszczególnych grup transakcji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-157">Based on this setting, this data source will calculate the sum of values of the ‘AmountMST’ field for each groups of transactions.</span></span> <span data-ttu-id="ac2c1-158">To obliczenie agregacji będzie dostępne jako pozycja TransactionsGroups.aggregated.TotalAmount.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="ac2c1-159">W drzewie rozwiń węzeł „Grupy transakcji”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="ac2c1-160">W drzewie wybierz element „Grupy transakcji”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="ac2c1-161">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-161">Click Edit.</span></span>
40. <span data-ttu-id="ac2c1-162">Kliknij opcję Edytuj grupę według.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-162">Click Edit group by.</span></span>
41. <span data-ttu-id="ac2c1-163">W drzewie rozwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="ac2c1-164">W drzewie wybierz kolejno elementy „Transakcje\Kwota faktury(AmountMST)”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="ac2c1-165">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-165">Click Add field to.</span></span>
44. <span data-ttu-id="ac2c1-166">Kliknij opcje Pola agregacji.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="ac2c1-167">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="ac2c1-168">W polu Metoda wybierz wartość „Maks.”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="ac2c1-169">W polu Nazwa wpisz „MaxOfAmountMST”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="ac2c1-170">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-170">Click Save.</span></span>
    * <span data-ttu-id="ac2c1-171">Obecnie wykonywanie źródeł danych GROUPBY można z pewnymi ograniczeniami przekładać na poziom bazy danych SQL.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="ac2c1-172">Translację można wykonać dla źródeł danych typu „Lista rekordów” lub źródeł danych reprezentowanych jako wyrażenie przy użyciu funkcji FILTR.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-172">Translation can be done for either data sources of the ‘Record list’ type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="ac2c1-173">Można ją również wykonać, gdy dla pojedynczego pola rekordów grupowania skonfigurowano tylko jedną agregację.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="ac2c1-174">Należy zauważyć, że nawet jeśli dla pola AmountMST skonfigurowano więcej niż jedną agregację, pole „Wykonanie w” nadal wskazuje, że dane grupowanie zostanie wykonane w czasie procesu w bazie danych SQL.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-174">Note that even though more than one aggregation was configured for the AmountMST field, the ‘Execution at’ field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="ac2c1-175">Wynika to z faktu, że z daną pozycją modelu danych powiązana jest tylko jedna agregacja, która zostanie użyta w czasie procesu do pobrania danych z takiego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="ac2c1-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-176">Close the page.</span></span>
50. <span data-ttu-id="ac2c1-177">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-177">Click OK.</span></span>
51. <span data-ttu-id="ac2c1-178">W drzewie rozwiń węzeł „Grupy transakcji”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="ac2c1-179">W drzewie rozwiń węzeł „Grupy transakcji\Zagregowane”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="ac2c1-180">W drzewie wybierz kolejno elementy „Grupy transakcji\Zagregowane\MaxOfAmountMST”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="ac2c1-181">W drzewie wybierz kolejno elementy „Sumy\Łączna wartość statystyczna(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="ac2c1-182">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-182">Click Bind.</span></span>
56. <span data-ttu-id="ac2c1-183">W drzewie rozwiń węzeł „Grupy transakcji”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="ac2c1-184">W drzewie wybierz element „Grupy transakcji”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="ac2c1-185">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-185">Click Edit.</span></span>
59. <span data-ttu-id="ac2c1-186">Kliknij opcję Edytuj grupę według.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-186">Click Edit group by.</span></span>
    * <span data-ttu-id="ac2c1-187">Należy zwrócić uwagę, że pole „Wykonanie w” wskazuje, że to grupowanie zostanie wykonane w czasie procesu w pamięci, ponieważ obydwie agregacje tego samego pola są powiązane z pozycjami modelu danych.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-187">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="ac2c1-188">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="ac2c1-189">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-189">Click Delete.</span></span>
62. <span data-ttu-id="ac2c1-190">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-190">Click Yes.</span></span>
63. <span data-ttu-id="ac2c1-191">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-191">Click Delete.</span></span>
64. <span data-ttu-id="ac2c1-192">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-192">Click Yes.</span></span>
65. <span data-ttu-id="ac2c1-193">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-193">Click Add field to.</span></span>
66. <span data-ttu-id="ac2c1-194">Kliknij opcję Jakie elementy do grupowania.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-194">Click What to group.</span></span>
67. <span data-ttu-id="ac2c1-195">W drzewie rozwiń węzeł „Rekord asortymentu (Intrastat)”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="ac2c1-196">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-196">Click Save.</span></span>
    * <span data-ttu-id="ac2c1-197">Należy zwrócić uwagę, że pole „Wykonanie w” wskazuje, że to grupowanie będzie wykonane w czasie procesu w pamięci, nawet jeśli nie zdefiniowano żadnych agregacji, a wybrane źródło danych typu „Rekordy w tabeli” odnosi się do tej samej tabeli „Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-197">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of ‘Table records’ type refers to the same ‘Intrastat’ table.</span></span> <span data-ttu-id="ac2c1-198">Dzieje się tak, ponieważ źródło danych zawiera kilka pól obliczeniowych, których jeszcze nie można przełożyć na poziom bazy danych SQL.</span><span class="sxs-lookup"><span data-stu-id="ac2c1-198">This is because the data source contains some calculated fields which can’t yet be translated to the SQL database level.</span></span>  


