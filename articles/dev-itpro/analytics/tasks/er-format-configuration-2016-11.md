--- 
title: "Tworzenie konfiguracji formatów raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfiguracji formatu dla raportowania elektronicznego (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 8c11f64fd899b8be4e6c3179913787eb2c32c6c6
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-electronic-reporting-er-format-configurations"></a><span data-ttu-id="86456-103">Tworzenie konfiguracji formatów raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="86456-103">Create Electronic reporting (ER) format configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86456-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfiguracji formatu dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="86456-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="86456-105">Ta konfiguracja formatu określi format dokumentów elektronicznych, które będą używane do przetwarzania płatności.</span><span class="sxs-lookup"><span data-stu-id="86456-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="86456-106">W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy Litware, Inc. W celu wykonania tych kroków należy najpierw wykonać procedurę „Mapowanie modelu na wybrane źródła danych”.</span><span class="sxs-lookup"><span data-stu-id="86456-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="86456-107">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="86456-107">Create a new format configuration</span></span>
1. <span data-ttu-id="86456-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="86456-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="86456-109">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="86456-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="86456-110">W drzewie zaznacz element „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="86456-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="86456-111">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="86456-112">W polu Nowy wpisz „Format oparty na modelu danych PaymentModel”.</span><span class="sxs-lookup"><span data-stu-id="86456-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="86456-113">W polu Nazwa wpisz „BACS (fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="86456-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="86456-114">BACS (fikcyjny brytyjski)</span><span class="sxs-lookup"><span data-stu-id="86456-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="86456-115">W polu Opis wpisz „Format płatności dla dostawcy BACS (fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="86456-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="86456-116">Format płatności dla dostawcy BACS (fikcyjny brytyjski)</span><span class="sxs-lookup"><span data-stu-id="86456-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="86456-117">Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="86456-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="86456-118">Ten dostawca będzie mógł obsługiwać tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="86456-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="86456-119">Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.</span><span class="sxs-lookup"><span data-stu-id="86456-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="86456-120">Można zdefiniować określony format dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="86456-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="86456-121">Pozostaw to pole puste, aby wybrać format w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="86456-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="86456-122">W polu Definicja modelu danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="86456-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="86456-123">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="86456-123">Click Create configuration.</span></span>
    * <span data-ttu-id="86456-124">Utworzono nową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="86456-124">A new configuration has been created.</span></span> <span data-ttu-id="86456-125">Wersja robocza może służyć do przechowywania formatu projektu w celu zarządzania dokumentami elektronicznymi.</span><span class="sxs-lookup"><span data-stu-id="86456-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="86456-126">Zaprojektuj format dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="86456-126">Design format of electronic document</span></span>
1. <span data-ttu-id="86456-127">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="86456-127">Click Designer.</span></span>
2. <span data-ttu-id="86456-128">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="86456-129">W drzewie zaznacz element „Wspólne\Plik”.</span><span class="sxs-lookup"><span data-stu-id="86456-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="86456-130">W polu Nazwa wpisz „Xml”.</span><span class="sxs-lookup"><span data-stu-id="86456-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="86456-131">XML</span><span class="sxs-lookup"><span data-stu-id="86456-131">Xml</span></span>  
5. <span data-ttu-id="86456-132">W polu Kodowanie wpisz „UTF-8”.</span><span class="sxs-lookup"><span data-stu-id="86456-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="86456-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="86456-133">UTF-8</span></span>  
6. <span data-ttu-id="86456-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-134">Click OK.</span></span>
7. <span data-ttu-id="86456-135">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="86456-136">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="86456-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="86456-137">W polu Nazwa wpisz „Komunikat”.</span><span class="sxs-lookup"><span data-stu-id="86456-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="86456-138">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="86456-138">Message</span></span>  
10. <span data-ttu-id="86456-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-139">Click OK.</span></span>
11. <span data-ttu-id="86456-140">W drzewie zaznacz element „Xml\Komunikat”.</span><span class="sxs-lookup"><span data-stu-id="86456-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="86456-141">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-141">Click Add Element.</span></span>
13. <span data-ttu-id="86456-142">W polu Nazwa wpisz „ProcessingDate”.</span><span class="sxs-lookup"><span data-stu-id="86456-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="86456-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="86456-143">ProcessingDate</span></span>  
14. <span data-ttu-id="86456-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-144">Click OK.</span></span>
15. <span data-ttu-id="86456-145">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-145">Click Add Element.</span></span>
16. <span data-ttu-id="86456-146">W polu Nazwa wpisz „MessageId”.</span><span class="sxs-lookup"><span data-stu-id="86456-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="86456-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="86456-147">MessageId</span></span>  
17. <span data-ttu-id="86456-148">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-148">Click OK.</span></span>
18. <span data-ttu-id="86456-149">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-149">Click Add Element.</span></span>
19. <span data-ttu-id="86456-150">W polu Nazwa wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="86456-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="86456-151">Płatności</span><span class="sxs-lookup"><span data-stu-id="86456-151">Payments</span></span>  
20. <span data-ttu-id="86456-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-152">Click OK.</span></span>
21. <span data-ttu-id="86456-153">W drzewie zaznacz element „Xml\Komunikat\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="86456-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="86456-154">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-154">Click Add Element.</span></span>
23. <span data-ttu-id="86456-155">W polu Nazwa wpisz „Towar”.</span><span class="sxs-lookup"><span data-stu-id="86456-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="86456-156">Element</span><span class="sxs-lookup"><span data-stu-id="86456-156">Item</span></span>  
24. <span data-ttu-id="86456-157">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-157">Click OK.</span></span>
25. <span data-ttu-id="86456-158">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.</span><span class="sxs-lookup"><span data-stu-id="86456-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="86456-159">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="86456-160">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="86456-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="86456-161">W polu Nazwa wpisz „Identyfikator”.</span><span class="sxs-lookup"><span data-stu-id="86456-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="86456-162">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="86456-162">Id</span></span>  
29. <span data-ttu-id="86456-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-163">Click OK.</span></span>
30. <span data-ttu-id="86456-164">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="86456-165">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="86456-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="86456-166">W polu Nazwa wpisz „Dostawca”.</span><span class="sxs-lookup"><span data-stu-id="86456-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="86456-167">Dostawca</span><span class="sxs-lookup"><span data-stu-id="86456-167">Vendor</span></span>  
33. <span data-ttu-id="86456-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-168">Click OK.</span></span>
34. <span data-ttu-id="86456-169">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca”.</span><span class="sxs-lookup"><span data-stu-id="86456-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="86456-170">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-170">Click Add Element.</span></span>
36. <span data-ttu-id="86456-171">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="86456-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="86456-172">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="86456-172">Name</span></span>  
37. <span data-ttu-id="86456-173">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-173">Click OK.</span></span>
38. <span data-ttu-id="86456-174">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-174">Click Add Element.</span></span>
39. <span data-ttu-id="86456-175">W polu Nazwa wpisz „Bank”.</span><span class="sxs-lookup"><span data-stu-id="86456-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="86456-176">Bank</span><span class="sxs-lookup"><span data-stu-id="86456-176">Bank</span></span>  
40. <span data-ttu-id="86456-177">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-177">Click OK.</span></span>
41. <span data-ttu-id="86456-178">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank”.</span><span class="sxs-lookup"><span data-stu-id="86456-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="86456-179">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-179">Click Add Element.</span></span>
43. <span data-ttu-id="86456-180">W polu Nazwa wpisz „RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="86456-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="86456-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="86456-181">RoutingNumber</span></span>  
44. <span data-ttu-id="86456-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-182">Click OK.</span></span>
45. <span data-ttu-id="86456-183">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-183">Click Add Element.</span></span>
46. <span data-ttu-id="86456-184">W polu Nazwa wpisz „AccountNumber”.</span><span class="sxs-lookup"><span data-stu-id="86456-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="86456-185">AccountNumber</span><span class="sxs-lookup"><span data-stu-id="86456-185">AccountNumber</span></span>  
47. <span data-ttu-id="86456-186">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-186">Click OK.</span></span>
48. <span data-ttu-id="86456-187">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca”.</span><span class="sxs-lookup"><span data-stu-id="86456-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="86456-188">Kliknij opcję Kopiuj.</span><span class="sxs-lookup"><span data-stu-id="86456-188">Click Copy.</span></span>
50. <span data-ttu-id="86456-189">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.</span><span class="sxs-lookup"><span data-stu-id="86456-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="86456-190">Kliknij opcję Wklej.</span><span class="sxs-lookup"><span data-stu-id="86456-190">Click Paste.</span></span>
52. <span data-ttu-id="86456-191">W polu Nazwa wpisz „Płatnik”.</span><span class="sxs-lookup"><span data-stu-id="86456-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="86456-192">Płatnik</span><span class="sxs-lookup"><span data-stu-id="86456-192">Payer</span></span>  
53. <span data-ttu-id="86456-193">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.</span><span class="sxs-lookup"><span data-stu-id="86456-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="86456-194">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-194">Click Add Element.</span></span>
55. <span data-ttu-id="86456-195">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="86456-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="86456-196">Waluta</span><span class="sxs-lookup"><span data-stu-id="86456-196">Currency</span></span>  
56. <span data-ttu-id="86456-197">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-197">Click OK.</span></span>
57. <span data-ttu-id="86456-198">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-198">Click Add Element.</span></span>
58. <span data-ttu-id="86456-199">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="86456-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="86456-200">opis</span><span class="sxs-lookup"><span data-stu-id="86456-200">Description</span></span>  
59. <span data-ttu-id="86456-201">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-201">Click OK.</span></span>
60. <span data-ttu-id="86456-202">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-202">Click Add Element.</span></span>
61. <span data-ttu-id="86456-203">W polu Nazwa wpisz „TransDate”.</span><span class="sxs-lookup"><span data-stu-id="86456-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="86456-204">TransDate</span><span class="sxs-lookup"><span data-stu-id="86456-204">TransDate</span></span>  
62. <span data-ttu-id="86456-205">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-205">Click OK.</span></span>
63. <span data-ttu-id="86456-206">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="86456-206">Click Add Element.</span></span>
64. <span data-ttu-id="86456-207">W polu Nazwa wpisz „Kwota”.</span><span class="sxs-lookup"><span data-stu-id="86456-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="86456-208">Ilość</span><span class="sxs-lookup"><span data-stu-id="86456-208">Amount</span></span>  
65. <span data-ttu-id="86456-209">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="86456-210">Przygotuj składniki formatu w celu zmapowania na elementy modelu danych.</span><span class="sxs-lookup"><span data-stu-id="86456-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="86456-211">W drzewie zaznacz element „Xml\Komunikat\ProcessingDate”.</span><span class="sxs-lookup"><span data-stu-id="86456-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="86456-212">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="86456-213">W drzewie zaznacz element „Tekst\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="86456-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="86456-214">W polu Format wpisz „rrrr-MM-dd”.</span><span class="sxs-lookup"><span data-stu-id="86456-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="86456-215">rrrr-MM-dd</span><span class="sxs-lookup"><span data-stu-id="86456-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="86456-216">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-216">Click OK.</span></span>
6. <span data-ttu-id="86456-217">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\TransDate”.</span><span class="sxs-lookup"><span data-stu-id="86456-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="86456-218">Kliknij opcję Dodaj datę/godzinę.</span><span class="sxs-lookup"><span data-stu-id="86456-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="86456-219">W polu Format wpisz „rrrr-MM-dd”.</span><span class="sxs-lookup"><span data-stu-id="86456-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="86456-220">rrrr-MM-dd</span><span class="sxs-lookup"><span data-stu-id="86456-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="86456-221">W polu Typ daty/godziny wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="86456-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="86456-222">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-222">Click OK.</span></span>
11. <span data-ttu-id="86456-223">W drzewie zaznacz element „Xml\Komunikat\MessageId”.</span><span class="sxs-lookup"><span data-stu-id="86456-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="86456-224">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="86456-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="86456-225">W drzewie zaznacz element „Tekst\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="86456-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="86456-226">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-226">Click OK.</span></span>
15. <span data-ttu-id="86456-227">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="86456-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="86456-228">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-228">Click Add String.</span></span>
17. <span data-ttu-id="86456-229">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-229">Click OK.</span></span>
18. <span data-ttu-id="86456-230">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="86456-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="86456-231">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-231">Click Add String.</span></span>
20. <span data-ttu-id="86456-232">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-232">Click OK.</span></span>
21. <span data-ttu-id="86456-233">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber”.</span><span class="sxs-lookup"><span data-stu-id="86456-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="86456-234">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-234">Click Add String.</span></span>
23. <span data-ttu-id="86456-235">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-235">Click OK.</span></span>
24. <span data-ttu-id="86456-236">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="86456-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="86456-237">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-237">Click Add String.</span></span>
26. <span data-ttu-id="86456-238">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-238">Click OK.</span></span>
27. <span data-ttu-id="86456-239">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="86456-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="86456-240">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-240">Click Add String.</span></span>
29. <span data-ttu-id="86456-241">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-241">Click OK.</span></span>
30. <span data-ttu-id="86456-242">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber”.</span><span class="sxs-lookup"><span data-stu-id="86456-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="86456-243">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-243">Click Add String.</span></span>
32. <span data-ttu-id="86456-244">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-244">Click OK.</span></span>
33. <span data-ttu-id="86456-245">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="86456-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="86456-246">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-246">Click Add String.</span></span>
35. <span data-ttu-id="86456-247">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-247">Click OK.</span></span>
36. <span data-ttu-id="86456-248">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Opis”.</span><span class="sxs-lookup"><span data-stu-id="86456-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="86456-249">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-249">Click Add String.</span></span>
38. <span data-ttu-id="86456-250">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-250">Click OK.</span></span>
39. <span data-ttu-id="86456-251">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Kwota”.</span><span class="sxs-lookup"><span data-stu-id="86456-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="86456-252">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="86456-252">Click Add String.</span></span>
41. <span data-ttu-id="86456-253">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="86456-253">Click OK.</span></span>
42. <span data-ttu-id="86456-254">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="86456-254">Click Save.</span></span>
43. <span data-ttu-id="86456-255">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86456-255">Close the page.</span></span>


