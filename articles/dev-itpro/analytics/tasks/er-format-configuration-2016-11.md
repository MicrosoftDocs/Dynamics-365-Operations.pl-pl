--- 
title: ER Tworzenie konfiguracji formatu (listopad 2016)
description: "W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfiguracji formatu dla raportowania elektronicznego (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f004451a260b5be6c15c3975cd9e63ba9c1a7a2e
ms.openlocfilehash: 6fa5023a29c95ab9f10d8aacd51edc1a06c3c152
ms.contentlocale: pl-pl
ms.lasthandoff: 02/06/2019

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="f29ca-103">ER Tworzenie konfiguracji formatu (listopad 2016)</span><span class="sxs-lookup"><span data-stu-id="f29ca-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f29ca-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfiguracji formatu dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="f29ca-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="f29ca-105">Ta konfiguracja formatu określi format dokumentów elektronicznych, które będą używane do przetwarzania płatności.</span><span class="sxs-lookup"><span data-stu-id="f29ca-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="f29ca-106">W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy Litware, Inc. W celu wykonania tych kroków należy najpierw wykonać procedurę „Mapowanie modelu na wybrane źródła danych”.</span><span class="sxs-lookup"><span data-stu-id="f29ca-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="f29ca-107">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="f29ca-107">Create a new format configuration</span></span>
1. <span data-ttu-id="f29ca-108">Wybierz kolejno opcje **Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="f29ca-109">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="f29ca-110">W drzewie zaznacz element **Płatności (model uproszczony)**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="f29ca-111">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f29ca-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="f29ca-112">Jeśli nie widać przycisku **Utwórz konfigurację**, należy włączyć tryb projektowania na stronie **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="f29ca-113">W polu **Nowy** wpisz **Format oparty na modelu danych PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="f29ca-114">W polu **Nazwa** wpisz **BACS (fikcyjny brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="f29ca-115">W polu **Opis** wpisz **Format płatności dla dostawcy BACS (fikcyjny brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="f29ca-116">Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="f29ca-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f29ca-117">Ten dostawca będzie mógł obsługiwać tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="f29ca-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f29ca-118">Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.</span><span class="sxs-lookup"><span data-stu-id="f29ca-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="f29ca-119">Można zdefiniować określony format dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="f29ca-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="f29ca-120">Pozostaw to pole puste, aby wybrać format w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f29ca-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="f29ca-121">W polu **Definicja modelu danych** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f29ca-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="f29ca-122">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-122">Click **Create configuration**.</span></span> <span data-ttu-id="f29ca-123">Utworzono nową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="f29ca-123">A new configuration has been created.</span></span> <span data-ttu-id="f29ca-124">Wersja robocza może służyć do przechowywania formatu projektu w celu zarządzania dokumentami elektronicznymi.</span><span class="sxs-lookup"><span data-stu-id="f29ca-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="f29ca-125">Jeśli nie widać przycisku **Utwórz konfigurację**, należy włączyć tryb projektowania na stronie **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="f29ca-126">Zaprojektuj format dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="f29ca-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="f29ca-127">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-127">Click **Designer**.</span></span>
2. <span data-ttu-id="f29ca-128">Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f29ca-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="f29ca-129">W drzewie zaznacz element **Wspólne\Plik**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="f29ca-130">W polu **Nazwa** wpisz **Xml**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="f29ca-131">W polu **Kodowanie** wpisz **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="f29ca-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-132">Click **OK**.</span></span>
7. <span data-ttu-id="f29ca-133">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-133">Click **Add**.</span></span>
8. <span data-ttu-id="f29ca-134">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="f29ca-135">W polu **Nazwa** wpisz **Komunikat**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="f29ca-136">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-136">Click **OK**.</span></span>
11. <span data-ttu-id="f29ca-137">W drzewie zaznacz element **Xml\Komunikat**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="f29ca-138">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="f29ca-139">W polu **Nazwa** wpisz **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="f29ca-140">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-140">Click **OK**.</span></span>
15. <span data-ttu-id="f29ca-141">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="f29ca-142">W polu Nazwa wpisz **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="f29ca-143">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-143">Click **OK**.</span></span>
18. <span data-ttu-id="f29ca-144">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="f29ca-145">W polu **Nazwa** wpisz **Płatności**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="f29ca-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-146">Click **OK**.</span></span>
21. <span data-ttu-id="f29ca-147">W drzewie zaznacz element **Xml\Komunikat\Płatności**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="f29ca-148">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="f29ca-149">W polu **Nazwa** wpisz **Towar**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="f29ca-150">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-150">Click **OK**.</span></span>
25. <span data-ttu-id="f29ca-151">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="f29ca-152">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-152">Click **Add**.</span></span>
27. <span data-ttu-id="f29ca-153">W drzewie zaznacz element **XML\Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="f29ca-154">W polu Nazwa wpisz **Identyfikator**</span><span class="sxs-lookup"><span data-stu-id="f29ca-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="f29ca-155">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-155">Click **OK**.</span></span>
30. <span data-ttu-id="f29ca-156">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-156">Click **Add**.</span></span>
31. <span data-ttu-id="f29ca-157">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="f29ca-158">W polu Nazwa wpisz **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="f29ca-159">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-159">Click **OK**.</span></span>
34. <span data-ttu-id="f29ca-160">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="f29ca-161">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="f29ca-162">W polu Nazwa wpisz **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="f29ca-163">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-163">Click **OK**.</span></span>
38. <span data-ttu-id="f29ca-164">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="f29ca-165">W polu **Nazwa** wpisz **Bank**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="f29ca-166">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-166">Click **OK**.</span></span>
41. <span data-ttu-id="f29ca-167">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="f29ca-168">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="f29ca-169">W polu **Nazwa** wpisz **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="f29ca-170">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-170">Click **OK**.</span></span>
45. <span data-ttu-id="f29ca-171">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="f29ca-172">W polu **Nazwa** wpisz **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="f29ca-173">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-173">Click **OK**.</span></span>
48. <span data-ttu-id="f29ca-174">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="f29ca-175">Kliknij opcję **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-175">Click **Copy**.</span></span>
50. <span data-ttu-id="f29ca-176">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="f29ca-177">Kliknij opcję **Wklej**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-177">Click **Paste**.</span></span>
52. <span data-ttu-id="f29ca-178">W polu **Nazwa** wpisz **Płatnik**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="f29ca-179">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="f29ca-180">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="f29ca-181">W polu **Nazwa** wpisz **Waluta**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="f29ca-182">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-182">Click **OK**.</span></span>
57. <span data-ttu-id="f29ca-183">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="f29ca-184">W polu **Nazwa** wpisz **Opis**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="f29ca-185">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-185">Click **OK**.</span></span>
60. <span data-ttu-id="f29ca-186">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="f29ca-187">W polu Nazwa wpisz **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="f29ca-188">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-188">Click **OK**.</span></span>
63. <span data-ttu-id="f29ca-189">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="f29ca-190">W polu Nazwa wpisz **Kwota**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="f29ca-191">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="f29ca-192">Przygotuj składniki formatu w celu zmapowania na elementy modelu danych.</span><span class="sxs-lookup"><span data-stu-id="f29ca-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="f29ca-193">W drzewie zaznacz element **Xml\Komunikat\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="f29ca-194">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f29ca-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="f29ca-195">W drzewie zaznacz element **Tekst\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="f29ca-196">W polu **Format** wpisz **rrrr-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="f29ca-197">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-197">Click **OK**.</span></span>
6. <span data-ttu-id="f29ca-198">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="f29ca-199">Kliknij opcję **Dodaj datę/godzinę**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="f29ca-200">W polu **Format** wpisz **rrrr-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="f29ca-201">W polu **Typ daty/godziny** wybierz opcję **Data**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="f29ca-202">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-202">Click **OK**.</span></span>
11. <span data-ttu-id="f29ca-203">W drzewie zaznacz element **Xml\Komunikat\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="f29ca-204">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f29ca-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="f29ca-205">W drzewie zaznacz element **Tekst\Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="f29ca-206">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-206">Click **OK**.</span></span>
15. <span data-ttu-id="f29ca-207">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="f29ca-208">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-208">Click **Add String**.</span></span>
17. <span data-ttu-id="f29ca-209">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-209">Click **OK**.</span></span>
18. <span data-ttu-id="f29ca-210">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="f29ca-211">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-211">Click **Add String**.</span></span>
20. <span data-ttu-id="f29ca-212">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-212">Click **OK**.</span></span>
21. <span data-ttu-id="f29ca-213">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="f29ca-214">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-214">Click **Add String**.</span></span>
23. <span data-ttu-id="f29ca-215">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-215">Click **OK**.</span></span>
24. <span data-ttu-id="f29ca-216">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="f29ca-217">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-217">Click **Add String**.</span></span>
26. <span data-ttu-id="f29ca-218">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-218">Click **OK**.</span></span>
27. <span data-ttu-id="f29ca-219">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="f29ca-220">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-220">Click **Add String**.</span></span>
29. <span data-ttu-id="f29ca-221">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-221">Click **OK**.</span></span>
30. <span data-ttu-id="f29ca-222">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="f29ca-223">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-223">Click **Add String**.</span></span>
32. <span data-ttu-id="f29ca-224">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-224">Click **OK**.</span></span>
33. <span data-ttu-id="f29ca-225">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Waluta**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="f29ca-226">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-226">Click **Add String**.</span></span>
35. <span data-ttu-id="f29ca-227">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-227">Click **OK**.</span></span>
36. <span data-ttu-id="f29ca-228">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Opis**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="f29ca-229">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-229">Click **Add String**.</span></span>
38. <span data-ttu-id="f29ca-230">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-230">Click **OK**.</span></span>
39. <span data-ttu-id="f29ca-231">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Kwota**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="f29ca-232">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-232">Click **Add String**.</span></span>
41. <span data-ttu-id="f29ca-233">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-233">Click **OK**.</span></span>
42. <span data-ttu-id="f29ca-234">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f29ca-234">Click **Save**.</span></span>
43. <span data-ttu-id="f29ca-235">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f29ca-235">Close the page.</span></span>


