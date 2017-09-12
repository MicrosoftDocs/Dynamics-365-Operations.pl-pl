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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 51208cbc5118e95fd402cca3cbc228ef1b87a47f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="51bf0-103">Projektowanie konfiguracji do generowania raportów w formacie OpenXML na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="51bf0-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51bf0-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą szablon generowania dokumentów elektronicznych w formacie OPENXML.</span><span class="sxs-lookup"><span data-stu-id="51bf0-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="51bf0-105">Ta konfiguracja będzie używana do przetwarzania płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="51bf0-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="51bf0-106">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Kroki można wykonać na danych firmy GBSI.</span><span class="sxs-lookup"><span data-stu-id="51bf0-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="51bf0-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="51bf0-108">Musi także istnieć plik programu Excel, który zostanie zaimportowany podczas tworzenia szablonu.</span><span class="sxs-lookup"><span data-stu-id="51bf0-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="51bf0-109">Plik można pobrać z adresu https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx.</span><span class="sxs-lookup"><span data-stu-id="51bf0-109">This file can be accessed from:  https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="51bf0-110">Przekazywanie konfiguracji modelu danych płatności</span><span class="sxs-lookup"><span data-stu-id="51bf0-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="51bf0-111">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="51bf0-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="51bf0-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="51bf0-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="51bf0-113">Wybierz dostawcę konfiguracji przykładowej firmy Litware, Inc. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="51bf0-114">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="51bf0-114">Click Set active.</span></span>
4. <span data-ttu-id="51bf0-115">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="51bf0-115">Click Repositories.</span></span>
    * <span data-ttu-id="51bf0-116">Wybierz repozytorium typu zasobów operacyjnych, jeśli jest dostępne.</span><span class="sxs-lookup"><span data-stu-id="51bf0-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="51bf0-117">Jeśli jej dostępne, pomiń poniższe kroki tworzenia nowego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="51bf0-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="51bf0-118">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="51bf0-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="51bf0-119">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="51bf0-120">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="51bf0-120">Click Create repository.</span></span>
8. <span data-ttu-id="51bf0-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51bf0-121">Click OK.</span></span>
9. <span data-ttu-id="51bf0-122">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="51bf0-122">Click Open.</span></span>
10. <span data-ttu-id="51bf0-123">W drzewie zaznacz element „Model płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="51bf0-124">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="51bf0-124">Click Import.</span></span>
    * <span data-ttu-id="51bf0-125">Zaimportuj ten model danych.</span><span class="sxs-lookup"><span data-stu-id="51bf0-125">Import this data model.</span></span> <span data-ttu-id="51bf0-126">Będzie on służył jako źródło danych w nowej konfiguracji formatu.</span><span class="sxs-lookup"><span data-stu-id="51bf0-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="51bf0-127">Jeśli ta konfiguracja została już zaimportowana, pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="51bf0-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="51bf0-128">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="51bf0-128">Click Yes.</span></span>
13. <span data-ttu-id="51bf0-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-129">Close the page.</span></span>
14. <span data-ttu-id="51bf0-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="51bf0-131">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="51bf0-131">Create a new format configuration</span></span>
1. <span data-ttu-id="51bf0-132">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="51bf0-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="51bf0-133">W drzewie zaznacz element „Model płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="51bf0-134">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="51bf0-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="51bf0-135">W polu Nowy wpisz „Format oparty na modelu danych PaymentModel”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="51bf0-136">Tworzenie formatu opartego na modelu danych PaymentModel</span><span class="sxs-lookup"><span data-stu-id="51bf0-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="51bf0-137">W polu Nazwa wpisz „Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="51bf0-138">Przykładowy raport arkusza</span><span class="sxs-lookup"><span data-stu-id="51bf0-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="51bf0-139">W polu Opis wpisz „Przykładowy raport arkusza o płatnościach dla dostawców”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="51bf0-140">Przykładowy raport arkusza o płatnościach dla dostawców.</span><span class="sxs-lookup"><span data-stu-id="51bf0-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="51bf0-141">W polu Definicja modelu danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51bf0-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="51bf0-142">Zaznacz definicję „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="51bf0-143">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="51bf0-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="51bf0-144">Projektowanie nowego dokumentu w formacie arkusza OPENXML</span><span class="sxs-lookup"><span data-stu-id="51bf0-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="51bf0-145">W drzewie zaznacz węzeł „Model płatności\Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="51bf0-146">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="51bf0-146">Click Designer.</span></span>
3. <span data-ttu-id="51bf0-147">W okienku akcji kliknij pozycję Importuj.</span><span class="sxs-lookup"><span data-stu-id="51bf0-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="51bf0-148">Kliknij opcję Importuj z programu Excel.</span><span class="sxs-lookup"><span data-stu-id="51bf0-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="51bf0-149">Kliknij opcję Załączniki.</span><span class="sxs-lookup"><span data-stu-id="51bf0-149">Click Attachments.</span></span>
    * <span data-ttu-id="51bf0-150">Dołącz istniejący dokument programu Excel jako szablon.</span><span class="sxs-lookup"><span data-stu-id="51bf0-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="51bf0-151">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="51bf0-151">Click New.</span></span>
7. <span data-ttu-id="51bf0-152">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="51bf0-152">Click File.</span></span>
    * <span data-ttu-id="51bf0-153">Wskaż istniejący plik programu Excel.</span><span class="sxs-lookup"><span data-stu-id="51bf0-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="51bf0-154">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-154">Close the page.</span></span>
9. <span data-ttu-id="51bf0-155">W polu Szablon wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51bf0-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="51bf0-156">Zaznacz załączony plik programu Excel, który ma być używany jako szablon.</span><span class="sxs-lookup"><span data-stu-id="51bf0-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="51bf0-157">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51bf0-157">Click OK.</span></span>
    * <span data-ttu-id="51bf0-158">Należy zwrócić uwagę, że składniki formatu raportowania elektronicznego zostały utworzone w formacie projektowania opartym na strukturze źródłowego dokument programu MS Excel (nazwanych zakresów).</span><span class="sxs-lookup"><span data-stu-id="51bf0-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="51bf0-159">Tworzenie nowego źródła danych do obliczania sum według kodów walut</span><span class="sxs-lookup"><span data-stu-id="51bf0-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="51bf0-160">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="51bf0-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="51bf0-161">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="51bf0-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="51bf0-162">W drzewie zaznacz element „Funkcje\Grupuj wg”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="51bf0-163">W polu Nazwa wpisz „PaymentByCurrency”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="51bf0-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="51bf0-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="51bf0-165">Kliknij opcję Edytuj grupę według.</span><span class="sxs-lookup"><span data-stu-id="51bf0-165">Click Edit group by.</span></span>
6. <span data-ttu-id="51bf0-166">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="51bf0-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="51bf0-167">W drzewie zaznacz element „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="51bf0-168">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="51bf0-168">Click Add field to.</span></span>
9. <span data-ttu-id="51bf0-169">Kliknij opcję Jakie elementy do grupowania.</span><span class="sxs-lookup"><span data-stu-id="51bf0-169">Click What to group.</span></span>
10. <span data-ttu-id="51bf0-170">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="51bf0-171">W drzewie zaznacz element „model\Płatności\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="51bf0-172">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="51bf0-172">Click Add field to.</span></span>
13. <span data-ttu-id="51bf0-173">Kliknij opcję Zgrupowane pola.</span><span class="sxs-lookup"><span data-stu-id="51bf0-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="51bf0-174">W drzewie zaznacz element „model\Płatności\Wskazana kwota(InstructedAmount)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="51bf0-175">Kliknij opcję Dodaj pole do.</span><span class="sxs-lookup"><span data-stu-id="51bf0-175">Click Add field to.</span></span>
16. <span data-ttu-id="51bf0-176">Kliknij opcje Pola agregacji.</span><span class="sxs-lookup"><span data-stu-id="51bf0-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="51bf0-177">W polu Metoda wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="51bf0-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="51bf0-178">Wybierz funkcję agregacji SUMA.</span><span class="sxs-lookup"><span data-stu-id="51bf0-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="51bf0-179">W polu Nazwa wpisz „TotalInstructuredAmount”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="51bf0-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="51bf0-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="51bf0-181">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51bf0-181">Click Save.</span></span>
20. <span data-ttu-id="51bf0-182">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-182">Close the page.</span></span>
21. <span data-ttu-id="51bf0-183">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51bf0-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="51bf0-184">Mapowanie składników formatu do źródeł danych</span><span class="sxs-lookup"><span data-stu-id="51bf0-184">Map format components to data sources</span></span>
1. <span data-ttu-id="51bf0-185">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="51bf0-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="51bf0-186">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="51bf0-187">W drzewie rozwiń węzeł „model\Płatności\Strona inicjująca(InitiatingParty)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="51bf0-188">W drzewie zaznacz węzeł „model\Płatności\Strona inicjująca(InitiatingParty)\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="51bf0-189">W drzewie rozwiń węzeł „Excel\ReportHeader”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="51bf0-190">W drzewie zaznacz element „Excel\ReportHeader\CompanyName”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="51bf0-191">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-191">Click Bind.</span></span>
8. <span data-ttu-id="51bf0-192">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="51bf0-193">W drzewie rozwiń węzeł „model\Płatności\Konto wierzyciela\Identyfikacja”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="51bf0-194">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel\Identyfikacja\Identyfikator źródła(SourceID)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="51bf0-195">W drzewie rozwiń węzeł „Excel\PaymLines”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="51bf0-196">W drzewie zaznacz element „Excel\PaymLines\VendAccountName”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="51bf0-197">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-197">Click Bind.</span></span>
14. <span data-ttu-id="51bf0-198">W drzewie zaznacz element „model\Płatności\Wierzyciel\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="51bf0-199">W drzewie zaznacz element „Excel\PaymLines\VendName”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="51bf0-200">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-200">Click Bind.</span></span>
17. <span data-ttu-id="51bf0-201">W drzewie rozwiń węzeł „model\Płatności\Agent wierzyciela(CreditorAgent)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="51bf0-202">W drzewie zaznacz element „model\Płatności\Agent wierzyciela(CreditorAgent)\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="51bf0-203">W drzewie zaznacz element „Excel\PaymLines\Bank”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="51bf0-204">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-204">Click Bind.</span></span>
21. <span data-ttu-id="51bf0-205">W drzewie zaznacz element „model\Płatności\Agent wierzyciela(CreditorAgent)\Kod banku(RoutingNumber)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="51bf0-206">W drzewie zaznacz element „Excel\PaymLines\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="51bf0-207">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-207">Click Bind.</span></span>
24. <span data-ttu-id="51bf0-208">W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".</span><span class="sxs-lookup"><span data-stu-id="51bf0-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="51bf0-209">W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".</span><span class="sxs-lookup"><span data-stu-id="51bf0-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="51bf0-210">W drzewie wybierz „model\Płatności\Konto wierzyciela(CreditorAccount\Identyfikacja\Numer”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="51bf0-211">W drzewie zaznacz element „Excel\PaymLines\AccountNumber”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="51bf0-212">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-212">Click Bind.</span></span>
29. <span data-ttu-id="51bf0-213">W drzewie zaznacz element „model\Płatności\Wskazana kwota(InstructedAmount)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="51bf0-214">W drzewie zaznacz element „Excel\PaymLines\Debet”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="51bf0-215">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-215">Click Bind.</span></span>
32. <span data-ttu-id="51bf0-216">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="51bf0-217">W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".</span><span class="sxs-lookup"><span data-stu-id="51bf0-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="51bf0-218">W drzewie rozwiń węzeł „model\Płatności\Agent wierzyciela(CreditorAgent)”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="51bf0-219">W drzewie zaznacz element „model\Płatności\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="51bf0-220">W drzewie zaznacz element „Excel\PaymLines\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="51bf0-221">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-221">Click Bind.</span></span>
38. <span data-ttu-id="51bf0-222">W drzewie rozwiń węzeł „PaymentByCurrency”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="51bf0-223">W drzewie rozwiń węzeł „PaymentByCurrency\zgrupowane”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="51bf0-224">W drzewie zaznacz element „PaymentByCurrency\zgrupowane\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="51bf0-225">W drzewie rozwiń węzeł „Excel\SummaryLines”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="51bf0-226">W drzewie zaznacz element „Excel\SummaryLines\SummaryCurrency”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="51bf0-227">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-227">Click Bind.</span></span>
44. <span data-ttu-id="51bf0-228">W drzewie rozwiń węzeł „PaymentByCurrency\zagregowane”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="51bf0-229">W drzewie zaznacz element „PaymentByCurrency\zagregowane\TotalInstructuredAmount”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="51bf0-230">W drzewie zaznacz element „Excel\SummaryLines\SummaryAmount”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="51bf0-231">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-231">Click Bind.</span></span>
48. <span data-ttu-id="51bf0-232">W drzewie zaznacz element „PaymentByCurrency”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="51bf0-233">W drzewie zaznacz element „Excel\SummaryLines”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="51bf0-234">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-234">Click Bind.</span></span>
51. <span data-ttu-id="51bf0-235">W drzewie zaznacz element „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="51bf0-236">W drzewie zaznacz element „Excel\PaymLines”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="51bf0-237">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="51bf0-237">Click Bind.</span></span>
54. <span data-ttu-id="51bf0-238">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51bf0-238">Click Save.</span></span>
55. <span data-ttu-id="51bf0-239">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="51bf0-240">Używanie utworzonej konfiguracji do przetwarzania płatności</span><span class="sxs-lookup"><span data-stu-id="51bf0-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="51bf0-241">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="51bf0-241">Click Change status.</span></span>
2. <span data-ttu-id="51bf0-242">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="51bf0-242">Click Complete.</span></span>
3. <span data-ttu-id="51bf0-243">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51bf0-243">Click OK.</span></span>
4. <span data-ttu-id="51bf0-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-244">Close the page.</span></span>
5. <span data-ttu-id="51bf0-245">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-245">Close the page.</span></span>
6. <span data-ttu-id="51bf0-246">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="51bf0-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="51bf0-247">Użyj szybkiego filtru, aby wyfiltrować pole Metoda płatności według wartości „Elektroniczne”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="51bf0-248">Elektroniczne</span><span class="sxs-lookup"><span data-stu-id="51bf0-248">Electronic</span></span>  
8. <span data-ttu-id="51bf0-249">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="51bf0-249">Click Edit.</span></span>
9. <span data-ttu-id="51bf0-250">Rozwiń sekcję Formaty plików.</span><span class="sxs-lookup"><span data-stu-id="51bf0-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="51bf0-251">W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="51bf0-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="51bf0-252">W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51bf0-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="51bf0-253">Zaznacz konfigurację „Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="51bf0-254">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51bf0-254">Click Save.</span></span>
13. <span data-ttu-id="51bf0-255">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51bf0-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="51bf0-256">Używanie utworzonej konfiguracji w celu testowania przetwarzania arkuszy płatności</span><span class="sxs-lookup"><span data-stu-id="51bf0-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="51bf0-257">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="51bf0-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="51bf0-258">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="51bf0-258">Click New.</span></span>
    * <span data-ttu-id="51bf0-259">Utwórz nowy arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="51bf0-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="51bf0-260">W polu Nazwa wpisz „VendPay”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="51bf0-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="51bf0-261">VendPay</span></span>  
4. <span data-ttu-id="51bf0-262">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="51bf0-262">Click Lines.</span></span>
5. <span data-ttu-id="51bf0-263">W polu Konto wpisz wartość „GB_SI_000001”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="51bf0-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="51bf0-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="51bf0-265">W polu Debet wpisz wartość „1000”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="51bf0-266">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="51bf0-266">Click New.</span></span>
8. <span data-ttu-id="51bf0-267">W polu Konto wpisz wartość „GB_SI_000005”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="51bf0-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="51bf0-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="51bf0-269">W polu Debet wpisz wartość „2000”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="51bf0-270">W polu Waluta wpisz wartość „EUR”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="51bf0-271">EUR</span><span class="sxs-lookup"><span data-stu-id="51bf0-271">EUR</span></span>  
11. <span data-ttu-id="51bf0-272">W polu Konto przeciwstawne wpisz wartość „GBSI OPER”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="51bf0-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="51bf0-273">GBSI OPER</span></span>  
12. <span data-ttu-id="51bf0-274">W polu Metoda płatności wpisz wartość „Elektroniczne”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="51bf0-275">Elektroniczne</span><span class="sxs-lookup"><span data-stu-id="51bf0-275">Electronic</span></span>  
13. <span data-ttu-id="51bf0-276">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51bf0-276">Click Save.</span></span>
14. <span data-ttu-id="51bf0-277">Kliknij opcję Generuj płatności.</span><span class="sxs-lookup"><span data-stu-id="51bf0-277">Click Generate payments.</span></span>
15. <span data-ttu-id="51bf0-278">W polu Metoda płatności wpisz wartość „Elektroniczne”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="51bf0-279">Elektroniczne</span><span class="sxs-lookup"><span data-stu-id="51bf0-279">Electronic</span></span>  
16. <span data-ttu-id="51bf0-280">W polu Nazwa pliku wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="51bf0-281">Na przykład wpisz Płatności.</span><span class="sxs-lookup"><span data-stu-id="51bf0-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="51bf0-282">W polu Konto bankowe wpisz „GBSI OPER”.</span><span class="sxs-lookup"><span data-stu-id="51bf0-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="51bf0-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="51bf0-283">GBSI OPER</span></span>  
18. <span data-ttu-id="51bf0-284">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51bf0-284">Click OK.</span></span>
19. <span data-ttu-id="51bf0-285">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51bf0-285">Click OK.</span></span>
    * <span data-ttu-id="51bf0-286">Przejrzyj utworzony arkusz, łącznie ze szczegółami wierszy płatności oraz sumami dla każdego kodu waluty użytego w tym komunikacie płatności.</span><span class="sxs-lookup"><span data-stu-id="51bf0-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


