---
title: ER Tworzenie konfiguracji formatu (listopad 2016)
description: W tym temacie wyjaśniono sposób tworzenia konfiguracji formatu raportowania elektronicznego (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9404d1e242c83d2103d1f24c42589c33b9f57f02
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092257"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="57477-103">ER Tworzenie konfiguracji formatu (listopad 2016)</span><span class="sxs-lookup"><span data-stu-id="57477-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57477-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfigurację formatu dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="57477-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="57477-105">Ta konfiguracja formatu określi format dokumentów elektronicznych, które będą używane do przetwarzania płatności.</span><span class="sxs-lookup"><span data-stu-id="57477-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="57477-106">W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy Litware, Inc. W celu wykonania tych kroków należy najpierw wykonać procedurę „Mapowanie modelu na wybrane źródła danych”.</span><span class="sxs-lookup"><span data-stu-id="57477-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="57477-107">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="57477-107">Create a new format configuration</span></span>
1. <span data-ttu-id="57477-108">Wybierz kolejno opcje **Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="57477-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="57477-109">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="57477-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="57477-110">W drzewie zaznacz element **Płatności (model uproszczony)**.</span><span class="sxs-lookup"><span data-stu-id="57477-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="57477-111">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57477-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="57477-112">Jeśli nie widać przycisku **Utwórz konfigurację**, należy włączyć tryb projektowania na stronie **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="57477-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="57477-113">W polu **Nowy** wpisz **Format oparty na modelu danych PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="57477-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="57477-114">W polu **Nazwa** wpisz **BACS (fikcyjny brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="57477-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="57477-115">W polu **Opis** wpisz **Format płatności dla dostawcy BACS (fikcyjny brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="57477-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="57477-116">Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="57477-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="57477-117">Ten dostawca będzie mógł obsługiwać tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="57477-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="57477-118">Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.</span><span class="sxs-lookup"><span data-stu-id="57477-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="57477-119">Można zdefiniować określony format dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="57477-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="57477-120">Pozostaw to pole puste, aby wybrać format w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="57477-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="57477-121">W polu **Definicja modelu danych** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="57477-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="57477-122">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="57477-122">Click **Create configuration**.</span></span> <span data-ttu-id="57477-123">Utworzono nową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="57477-123">A new configuration has been created.</span></span> <span data-ttu-id="57477-124">Wersja robocza może służyć do przechowywania formatu projektu w celu zarządzania dokumentami elektronicznymi.</span><span class="sxs-lookup"><span data-stu-id="57477-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="57477-125">Zaprojektuj format dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="57477-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="57477-126">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="57477-126">Click **Designer**.</span></span>
2. <span data-ttu-id="57477-127">Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57477-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="57477-128">W drzewie zaznacz element **Wspólne\Plik**.</span><span class="sxs-lookup"><span data-stu-id="57477-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="57477-129">W polu **Nazwa** wpisz **Xml**.</span><span class="sxs-lookup"><span data-stu-id="57477-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="57477-130">W polu **Kodowanie** wpisz **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="57477-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="57477-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-131">Click **OK**.</span></span>
7. <span data-ttu-id="57477-132">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="57477-132">Click **Add**.</span></span>
8. <span data-ttu-id="57477-133">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="57477-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="57477-134">W polu **Nazwa** wpisz **Komunikat**.</span><span class="sxs-lookup"><span data-stu-id="57477-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="57477-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-135">Click **OK**.</span></span>
11. <span data-ttu-id="57477-136">W drzewie zaznacz element **Xml\Komunikat**.</span><span class="sxs-lookup"><span data-stu-id="57477-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="57477-137">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="57477-138">W polu **Nazwa** wpisz **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="57477-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="57477-139">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-139">Click **OK**.</span></span>
15. <span data-ttu-id="57477-140">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="57477-141">W polu Nazwa wpisz **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="57477-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="57477-142">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-142">Click **OK**.</span></span>
18. <span data-ttu-id="57477-143">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="57477-144">W polu **Nazwa** wpisz **Płatności**.</span><span class="sxs-lookup"><span data-stu-id="57477-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="57477-145">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-145">Click **OK**.</span></span>
21. <span data-ttu-id="57477-146">W drzewie zaznacz element **Xml\Komunikat\Płatności**.</span><span class="sxs-lookup"><span data-stu-id="57477-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="57477-147">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="57477-148">W polu **Nazwa** wpisz **Towar**.</span><span class="sxs-lookup"><span data-stu-id="57477-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="57477-149">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-149">Click **OK**.</span></span>
25. <span data-ttu-id="57477-150">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.</span><span class="sxs-lookup"><span data-stu-id="57477-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="57477-151">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="57477-151">Click **Add**.</span></span>
27. <span data-ttu-id="57477-152">W drzewie zaznacz element **XML\Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="57477-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="57477-153">W polu Nazwa wpisz **Identyfikator**</span><span class="sxs-lookup"><span data-stu-id="57477-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="57477-154">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-154">Click **OK**.</span></span>
30. <span data-ttu-id="57477-155">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="57477-155">Click **Add**.</span></span>
31. <span data-ttu-id="57477-156">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="57477-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="57477-157">W polu Nazwa wpisz **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="57477-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="57477-158">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-158">Click **OK**.</span></span>
34. <span data-ttu-id="57477-159">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="57477-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="57477-160">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="57477-161">W polu Nazwa wpisz **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="57477-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="57477-162">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-162">Click **OK**.</span></span>
38. <span data-ttu-id="57477-163">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="57477-164">W polu **Nazwa** wpisz **Bank**.</span><span class="sxs-lookup"><span data-stu-id="57477-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="57477-165">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-165">Click **OK**.</span></span>
41. <span data-ttu-id="57477-166">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank**.</span><span class="sxs-lookup"><span data-stu-id="57477-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="57477-167">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="57477-168">W polu **Nazwa** wpisz **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="57477-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="57477-169">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-169">Click **OK**.</span></span>
45. <span data-ttu-id="57477-170">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="57477-171">W polu **Nazwa** wpisz **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="57477-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="57477-172">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-172">Click **OK**.</span></span>
48. <span data-ttu-id="57477-173">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="57477-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="57477-174">Kliknij opcję **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="57477-174">Click **Copy**.</span></span>
50. <span data-ttu-id="57477-175">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.</span><span class="sxs-lookup"><span data-stu-id="57477-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="57477-176">Kliknij opcję **Wklej**.</span><span class="sxs-lookup"><span data-stu-id="57477-176">Click **Paste**.</span></span>
52. <span data-ttu-id="57477-177">W polu **Nazwa** wpisz **Płatnik**.</span><span class="sxs-lookup"><span data-stu-id="57477-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="57477-178">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.</span><span class="sxs-lookup"><span data-stu-id="57477-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="57477-179">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="57477-180">W polu **Nazwa** wpisz **Waluta**.</span><span class="sxs-lookup"><span data-stu-id="57477-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="57477-181">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-181">Click **OK**.</span></span>
57. <span data-ttu-id="57477-182">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="57477-183">W polu **Nazwa** wpisz **Opis**.</span><span class="sxs-lookup"><span data-stu-id="57477-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="57477-184">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-184">Click **OK**.</span></span>
60. <span data-ttu-id="57477-185">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="57477-186">W polu Nazwa wpisz **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="57477-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="57477-187">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-187">Click **OK**.</span></span>
63. <span data-ttu-id="57477-188">Kliknij opcję **Dodaj element**.</span><span class="sxs-lookup"><span data-stu-id="57477-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="57477-189">W polu Nazwa wpisz **Kwota**.</span><span class="sxs-lookup"><span data-stu-id="57477-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="57477-190">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="57477-191">Przygotuj składniki formatu w celu zmapowania na elementy modelu danych.</span><span class="sxs-lookup"><span data-stu-id="57477-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="57477-192">W drzewie zaznacz element **Xml\Komunikat\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="57477-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="57477-193">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57477-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="57477-194">W drzewie zaznacz element **Tekst\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="57477-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="57477-195">W polu **Format** wpisz **rrrr-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="57477-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="57477-196">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-196">Click **OK**.</span></span>
6. <span data-ttu-id="57477-197">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="57477-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="57477-198">Kliknij opcję **Dodaj datę/godzinę**.</span><span class="sxs-lookup"><span data-stu-id="57477-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="57477-199">W polu **Format** wpisz **rrrr-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="57477-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="57477-200">W polu **Typ daty/godziny** wybierz opcję **Data**.</span><span class="sxs-lookup"><span data-stu-id="57477-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="57477-201">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-201">Click **OK**.</span></span>
11. <span data-ttu-id="57477-202">W drzewie zaznacz element **Xml\Komunikat\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="57477-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="57477-203">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57477-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="57477-204">W drzewie zaznacz element **Tekst\Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="57477-205">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-205">Click **OK**.</span></span>
15. <span data-ttu-id="57477-206">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="57477-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="57477-207">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-207">Click **Add String**.</span></span>
17. <span data-ttu-id="57477-208">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-208">Click **OK**.</span></span>
18. <span data-ttu-id="57477-209">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="57477-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="57477-210">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-210">Click **Add String**.</span></span>
20. <span data-ttu-id="57477-211">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-211">Click **OK**.</span></span>
21. <span data-ttu-id="57477-212">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="57477-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="57477-213">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-213">Click **Add String**.</span></span>
23. <span data-ttu-id="57477-214">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-214">Click **OK**.</span></span>
24. <span data-ttu-id="57477-215">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="57477-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="57477-216">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-216">Click **Add String**.</span></span>
26. <span data-ttu-id="57477-217">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-217">Click **OK**.</span></span>
27. <span data-ttu-id="57477-218">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="57477-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="57477-219">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-219">Click **Add String**.</span></span>
29. <span data-ttu-id="57477-220">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-220">Click **OK**.</span></span>
30. <span data-ttu-id="57477-221">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="57477-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="57477-222">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-222">Click **Add String**.</span></span>
32. <span data-ttu-id="57477-223">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-223">Click **OK**.</span></span>
33. <span data-ttu-id="57477-224">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Waluta**.</span><span class="sxs-lookup"><span data-stu-id="57477-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="57477-225">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-225">Click **Add String**.</span></span>
35. <span data-ttu-id="57477-226">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-226">Click **OK**.</span></span>
36. <span data-ttu-id="57477-227">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Opis**.</span><span class="sxs-lookup"><span data-stu-id="57477-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="57477-228">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-228">Click **Add String**.</span></span>
38. <span data-ttu-id="57477-229">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-229">Click **OK**.</span></span>
39. <span data-ttu-id="57477-230">W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Kwota**.</span><span class="sxs-lookup"><span data-stu-id="57477-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="57477-231">Kliknij opcję **Dodaj ciąg**.</span><span class="sxs-lookup"><span data-stu-id="57477-231">Click **Add String**.</span></span>
41. <span data-ttu-id="57477-232">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57477-232">Click **OK**.</span></span>
42. <span data-ttu-id="57477-233">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="57477-233">Click **Save**.</span></span>
43. <span data-ttu-id="57477-234">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57477-234">Close the page.</span></span>

