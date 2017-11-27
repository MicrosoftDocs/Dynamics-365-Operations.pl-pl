--- 
title: "Projektowanie konfiguracji do generowania raportów w formacie OpenXML na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą szablon generowania dokumentów elektronicznych w formacie OPENXML."
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
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 09789957839097ba2898544102af908c198090c7
ms.contentlocale: pl-pl
ms.lasthandoff: 11/14/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="8bdff-103">Projektowanie konfiguracji do generowania raportów w formacie OpenXML na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="8bdff-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8bdff-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą szablon generowania dokumentów elektronicznych w formacie OPENXML.</span><span class="sxs-lookup"><span data-stu-id="8bdff-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="8bdff-105">Ta konfiguracja będzie używana do przetwarzania płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="8bdff-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="8bdff-106">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Kroki można wykonać na danych firmy GBSI.</span><span class="sxs-lookup"><span data-stu-id="8bdff-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="8bdff-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="8bdff-108">Należy także pobrać i zapisać plik programu Microsoft Excel, [Szablon raportu o płatnościach](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="8bdff-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="8bdff-109">Przekazywanie konfiguracji modelu danych płatności</span><span class="sxs-lookup"><span data-stu-id="8bdff-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="8bdff-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="8bdff-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8bdff-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8bdff-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8bdff-112">Wybierz dostawcę konfiguracji przykładowej firmy Litware, Inc. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="8bdff-113">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="8bdff-113">Click Set active.</span></span>
4. <span data-ttu-id="8bdff-114">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="8bdff-114">Click Repositories.</span></span>
    * <span data-ttu-id="8bdff-115">Wybierz repozytorium typu zasobów operacyjnych, jeśli jest dostępne.</span><span class="sxs-lookup"><span data-stu-id="8bdff-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="8bdff-116">Jeśli jej dostępne, pomiń poniższe kroki tworzenia nowego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="8bdff-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="8bdff-117">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="8bdff-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="8bdff-118">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="8bdff-119">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="8bdff-119">Click Create repository.</span></span>
8. <span data-ttu-id="8bdff-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8bdff-120">Click OK.</span></span>
9. <span data-ttu-id="8bdff-121">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="8bdff-121">Click Open.</span></span>
10. <span data-ttu-id="8bdff-122">W drzewie zaznacz element „Model płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="8bdff-123">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="8bdff-123">Click Import.</span></span>
    * <span data-ttu-id="8bdff-124">Zaimportuj ten model danych.</span><span class="sxs-lookup"><span data-stu-id="8bdff-124">Import this data model.</span></span> <span data-ttu-id="8bdff-125">Będzie on służył jako źródło danych w nowej konfiguracji formatu.</span><span class="sxs-lookup"><span data-stu-id="8bdff-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="8bdff-126">Jeśli ta konfiguracja została już zaimportowana, pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="8bdff-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="8bdff-127">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="8bdff-127">Click Yes.</span></span>
13. <span data-ttu-id="8bdff-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-128">Close the page.</span></span>
14. <span data-ttu-id="8bdff-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="8bdff-130">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="8bdff-130">Create a new format configuration</span></span>
1. <span data-ttu-id="8bdff-131">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="8bdff-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="8bdff-132">W drzewie zaznacz element „Model płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="8bdff-133">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="8bdff-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="8bdff-134">W polu Nowy wpisz „Format oparty na modelu danych PaymentModel”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="8bdff-135">Tworzenie formatu opartego na modelu danych PaymentModel</span><span class="sxs-lookup"><span data-stu-id="8bdff-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="8bdff-136">W polu Nazwa wpisz „Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="8bdff-137">Przykładowy raport arkusza</span><span class="sxs-lookup"><span data-stu-id="8bdff-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="8bdff-138">W polu Opis wpisz „Przykładowy raport arkusza o płatnościach dla dostawców”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="8bdff-139">Przykładowy raport arkusza o płatnościach dla dostawców.</span><span class="sxs-lookup"><span data-stu-id="8bdff-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="8bdff-140">W polu Definicja modelu danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8bdff-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="8bdff-141">Zaznacz definicję „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="8bdff-142">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="8bdff-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="8bdff-143">Projektowanie nowego dokumentu w formacie arkusza OPENXML</span><span class="sxs-lookup"><span data-stu-id="8bdff-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="8bdff-144">W drzewie zaznacz węzeł „Model płatności\Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="8bdff-145">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="8bdff-145">Click Designer.</span></span>
3. <span data-ttu-id="8bdff-146">W okienku akcji kliknij pozycję Importuj.</span><span class="sxs-lookup"><span data-stu-id="8bdff-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="8bdff-147">Kliknij opcję Importuj z programu Excel.</span><span class="sxs-lookup"><span data-stu-id="8bdff-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="8bdff-148">Kliknij opcję Załączniki.</span><span class="sxs-lookup"><span data-stu-id="8bdff-148">Click Attachments.</span></span>
    * <span data-ttu-id="8bdff-149">Dołącz istniejący dokument programu Excel jako szablon.</span><span class="sxs-lookup"><span data-stu-id="8bdff-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="8bdff-150">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8bdff-150">Click New.</span></span>
7. <span data-ttu-id="8bdff-151">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="8bdff-151">Click File.</span></span>
    * <span data-ttu-id="8bdff-152">Wskaż istniejący plik programu Excel.</span><span class="sxs-lookup"><span data-stu-id="8bdff-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="8bdff-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-153">Close the page.</span></span>
9. <span data-ttu-id="8bdff-154">W polu Szablon wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8bdff-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="8bdff-155">Zaznacz załączony plik programu Excel, który ma być używany jako szablon.</span><span class="sxs-lookup"><span data-stu-id="8bdff-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="8bdff-156">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8bdff-156">Click OK.</span></span>
    * <span data-ttu-id="8bdff-157">Należy zwrócić uwagę, że składniki formatu raportowania elektronicznego zostały utworzone w formacie projektowania opartym na strukturze źródłowego dokument programu MS Excel (nazwanych zakresów).</span><span class="sxs-lookup"><span data-stu-id="8bdff-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="8bdff-158">Tworzenie nowego źródła danych do obliczania sum według kodów walut</span><span class="sxs-lookup"><span data-stu-id="8bdff-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="8bdff-159">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="8bdff-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="8bdff-160">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="8bdff-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="8bdff-161">W drzewie zaznacz element „Funkcje\Grupuj wg”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="8bdff-162">W polu Nazwa wpisz „PaymentByCurrency”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="8bdff-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="8bdff-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="8bdff-164">Kliknij opcję Edytuj grupę według.</span><span class="sxs-lookup"><span data-stu-id="8bdff-164">Click Edit group by.</span></span>
6. <span data-ttu-id="8bdff-165">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="8bdff-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="8bdff-166">W drzewie zaznacz element „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="8bdff-167">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="8bdff-167">Click Add field to.</span></span>
9. <span data-ttu-id="8bdff-168">Kliknij opcję Jakie elementy do grupowania.</span><span class="sxs-lookup"><span data-stu-id="8bdff-168">Click What to group.</span></span>
10. <span data-ttu-id="8bdff-169">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="8bdff-170">W drzewie zaznacz element „model\Płatności\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="8bdff-171">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="8bdff-171">Click Add field to.</span></span>
13. <span data-ttu-id="8bdff-172">Kliknij opcję Zgrupowane pola.</span><span class="sxs-lookup"><span data-stu-id="8bdff-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="8bdff-173">W drzewie zaznacz element „model\Płatności\Wskazana kwota(InstructedAmount)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="8bdff-174">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="8bdff-174">Click Add field to.</span></span>
16. <span data-ttu-id="8bdff-175">Kliknij opcje Pola agregacji.</span><span class="sxs-lookup"><span data-stu-id="8bdff-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="8bdff-176">W polu Metoda wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="8bdff-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="8bdff-177">Wybierz funkcję agregacji SUMA.</span><span class="sxs-lookup"><span data-stu-id="8bdff-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="8bdff-178">W polu Nazwa wpisz „TotalInstructuredAmount”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="8bdff-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="8bdff-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="8bdff-180">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8bdff-180">Click Save.</span></span>
20. <span data-ttu-id="8bdff-181">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-181">Close the page.</span></span>
21. <span data-ttu-id="8bdff-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8bdff-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="8bdff-183">Mapowanie składników formatu do źródeł danych</span><span class="sxs-lookup"><span data-stu-id="8bdff-183">Map format components to data sources</span></span>
1. <span data-ttu-id="8bdff-184">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="8bdff-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="8bdff-185">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="8bdff-186">W drzewie rozwiń węzeł „model\Płatności\Strona inicjująca(InitiatingParty)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="8bdff-187">W drzewie zaznacz węzeł „model\Płatności\Strona inicjująca(InitiatingParty)\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="8bdff-188">W drzewie rozwiń węzeł „Excel\ReportHeader”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="8bdff-189">W drzewie zaznacz element „Excel\ReportHeader\CompanyName”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="8bdff-190">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-190">Click Bind.</span></span>
8. <span data-ttu-id="8bdff-191">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="8bdff-192">W drzewie rozwiń węzeł „model\Płatności\Konto wierzyciela\Identyfikacja”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="8bdff-193">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel\Identyfikacja\Identyfikator źródła(SourceID)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="8bdff-194">W drzewie rozwiń węzeł „Excel\PaymLines”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="8bdff-195">W drzewie zaznacz element „Excel\PaymLines\VendAccountName”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="8bdff-196">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-196">Click Bind.</span></span>
14. <span data-ttu-id="8bdff-197">W drzewie zaznacz element „model\Płatności\Wierzyciel\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="8bdff-198">W drzewie zaznacz element „Excel\PaymLines\VendName”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="8bdff-199">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-199">Click Bind.</span></span>
17. <span data-ttu-id="8bdff-200">W drzewie rozwiń węzeł „model\Płatności\Agent wierzyciela(CreditorAgent)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="8bdff-201">W drzewie zaznacz element „model\Płatności\Agent wierzyciela(CreditorAgent)\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="8bdff-202">W drzewie zaznacz element „Excel\PaymLines\Bank”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="8bdff-203">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-203">Click Bind.</span></span>
21. <span data-ttu-id="8bdff-204">W drzewie zaznacz element „model\Płatności\Agent wierzyciela(CreditorAgent)\Kod banku(RoutingNumber)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="8bdff-205">W drzewie zaznacz element „Excel\PaymLines\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="8bdff-206">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-206">Click Bind.</span></span>
24. <span data-ttu-id="8bdff-207">W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".</span><span class="sxs-lookup"><span data-stu-id="8bdff-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="8bdff-208">W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".</span><span class="sxs-lookup"><span data-stu-id="8bdff-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="8bdff-209">W drzewie wybierz „model\Płatności\Konto wierzyciela(CreditorAccount\Identyfikacja\Numer”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="8bdff-210">W drzewie zaznacz element „Excel\PaymLines\AccountNumber”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="8bdff-211">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-211">Click Bind.</span></span>
29. <span data-ttu-id="8bdff-212">W drzewie zaznacz element „model\Płatności\Wskazana kwota(InstructedAmount)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="8bdff-213">W drzewie zaznacz element „Excel\PaymLines\Debet”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="8bdff-214">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-214">Click Bind.</span></span>
32. <span data-ttu-id="8bdff-215">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="8bdff-216">W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".</span><span class="sxs-lookup"><span data-stu-id="8bdff-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="8bdff-217">W drzewie rozwiń węzeł „model\Płatności\Agent wierzyciela(CreditorAgent)”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="8bdff-218">W drzewie zaznacz element „model\Płatności\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="8bdff-219">W drzewie zaznacz element „Excel\PaymLines\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="8bdff-220">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-220">Click Bind.</span></span>
38. <span data-ttu-id="8bdff-221">W drzewie rozwiń węzeł „PaymentByCurrency”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="8bdff-222">W drzewie rozwiń węzeł „PaymentByCurrency\zgrupowane”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="8bdff-223">W drzewie zaznacz element „PaymentByCurrency\zgrupowane\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="8bdff-224">W drzewie rozwiń węzeł „Excel\SummaryLines”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="8bdff-225">W drzewie zaznacz element „Excel\SummaryLines\SummaryCurrency”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="8bdff-226">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-226">Click Bind.</span></span>
44. <span data-ttu-id="8bdff-227">W drzewie rozwiń węzeł „PaymentByCurrency\zagregowane”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="8bdff-228">W drzewie zaznacz element „PaymentByCurrency\zagregowane\TotalInstructuredAmount”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="8bdff-229">W drzewie zaznacz element „Excel\SummaryLines\SummaryAmount”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="8bdff-230">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-230">Click Bind.</span></span>
48. <span data-ttu-id="8bdff-231">W drzewie zaznacz element „PaymentByCurrency”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="8bdff-232">W drzewie zaznacz element „Excel\SummaryLines”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="8bdff-233">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-233">Click Bind.</span></span>
51. <span data-ttu-id="8bdff-234">W drzewie zaznacz element „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="8bdff-235">W drzewie zaznacz element „Excel\PaymLines”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="8bdff-236">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="8bdff-236">Click Bind.</span></span>
54. <span data-ttu-id="8bdff-237">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8bdff-237">Click Save.</span></span>
55. <span data-ttu-id="8bdff-238">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="8bdff-239">Używanie utworzonej konfiguracji do przetwarzania płatności</span><span class="sxs-lookup"><span data-stu-id="8bdff-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="8bdff-240">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="8bdff-240">Click Change status.</span></span>
2. <span data-ttu-id="8bdff-241">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="8bdff-241">Click Complete.</span></span>
3. <span data-ttu-id="8bdff-242">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8bdff-242">Click OK.</span></span>
4. <span data-ttu-id="8bdff-243">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-243">Close the page.</span></span>
5. <span data-ttu-id="8bdff-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-244">Close the page.</span></span>
6. <span data-ttu-id="8bdff-245">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="8bdff-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="8bdff-246">Użyj szybkiego filtru, aby wyfiltrować pole Metoda płatności według wartości „Elektroniczne”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="8bdff-247">Elektroniczne</span><span class="sxs-lookup"><span data-stu-id="8bdff-247">Electronic</span></span>  
8. <span data-ttu-id="8bdff-248">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="8bdff-248">Click Edit.</span></span>
9. <span data-ttu-id="8bdff-249">Rozwiń sekcję Formaty plików.</span><span class="sxs-lookup"><span data-stu-id="8bdff-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="8bdff-250">W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8bdff-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="8bdff-251">W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8bdff-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="8bdff-252">Zaznacz konfigurację „Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="8bdff-253">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8bdff-253">Click Save.</span></span>
13. <span data-ttu-id="8bdff-254">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8bdff-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="8bdff-255">Używanie utworzonej konfiguracji w celu testowania przetwarzania arkuszy płatności</span><span class="sxs-lookup"><span data-stu-id="8bdff-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="8bdff-256">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="8bdff-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="8bdff-257">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8bdff-257">Click New.</span></span>
    * <span data-ttu-id="8bdff-258">Utwórz nowy arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="8bdff-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="8bdff-259">W polu Nazwa wpisz „VendPay”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="8bdff-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="8bdff-260">VendPay</span></span>  
4. <span data-ttu-id="8bdff-261">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="8bdff-261">Click Lines.</span></span>
5. <span data-ttu-id="8bdff-262">W polu Konto wpisz wartość „GB_SI_000001”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="8bdff-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="8bdff-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="8bdff-264">W polu Debet wpisz wartość „1000”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="8bdff-265">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8bdff-265">Click New.</span></span>
8. <span data-ttu-id="8bdff-266">W polu Konto wpisz wartość „GB_SI_000005”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="8bdff-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="8bdff-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="8bdff-268">W polu Debet wpisz wartość „2000”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="8bdff-269">W polu Waluta wpisz wartość „EUR”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="8bdff-270">EUR</span><span class="sxs-lookup"><span data-stu-id="8bdff-270">EUR</span></span>  
11. <span data-ttu-id="8bdff-271">W polu Konto przeciwstawne wpisz wartość „GBSI OPER”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="8bdff-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="8bdff-272">GBSI OPER</span></span>  
12. <span data-ttu-id="8bdff-273">W polu Metoda płatności wpisz wartość „Elektroniczne”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="8bdff-274">Elektroniczne</span><span class="sxs-lookup"><span data-stu-id="8bdff-274">Electronic</span></span>  
13. <span data-ttu-id="8bdff-275">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8bdff-275">Click Save.</span></span>
14. <span data-ttu-id="8bdff-276">Kliknij opcję Generuj płatności.</span><span class="sxs-lookup"><span data-stu-id="8bdff-276">Click Generate payments.</span></span>
15. <span data-ttu-id="8bdff-277">W polu Metoda płatności wpisz wartość „Elektroniczne”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="8bdff-278">Elektroniczne</span><span class="sxs-lookup"><span data-stu-id="8bdff-278">Electronic</span></span>  
16. <span data-ttu-id="8bdff-279">W polu Nazwa pliku wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="8bdff-280">Na przykład wpisz Płatności.</span><span class="sxs-lookup"><span data-stu-id="8bdff-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="8bdff-281">W polu Konto bankowe wpisz „GBSI OPER”.</span><span class="sxs-lookup"><span data-stu-id="8bdff-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="8bdff-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="8bdff-282">GBSI OPER</span></span>  
18. <span data-ttu-id="8bdff-283">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8bdff-283">Click OK.</span></span>
19. <span data-ttu-id="8bdff-284">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8bdff-284">Click OK.</span></span>
    * <span data-ttu-id="8bdff-285">Przejrzyj utworzony arkusz, łącznie ze szczegółami wierszy płatności oraz sumami dla każdego kodu waluty użytego w tym komunikacie płatności.</span><span class="sxs-lookup"><span data-stu-id="8bdff-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


