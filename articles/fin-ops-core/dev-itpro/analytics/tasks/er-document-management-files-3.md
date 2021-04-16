---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3 — tworzenie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do używania plików zarządzania dokumentami w wynikach ER. (część 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99a286b4e40ddeb7f4ff37c1ece3c678b26c838b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755017"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="1c50e-104">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3 — tworzenie formatu)</span><span class="sxs-lookup"><span data-stu-id="1c50e-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1c50e-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="1c50e-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="1c50e-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="1c50e-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="1c50e-107">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2: Rozszerzanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="1c50e-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="1c50e-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="1c50e-109">Tworzenie formatu przetwarzania faktur</span><span class="sxs-lookup"><span data-stu-id="1c50e-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="1c50e-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="1c50e-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1c50e-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="1c50e-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1c50e-112">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="1c50e-113">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="1c50e-114">Utworzysz format do generowania komunikatów elektronicznych z informacjami o wszystkich plikach, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.</span><span class="sxs-lookup"><span data-stu-id="1c50e-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="1c50e-115">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="1c50e-116">W polu Nowy wpisz „Format oparty na modelu danych Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="1c50e-117">W polu Nazwa wpisz „Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="1c50e-118">Przykładowy komunikat faktury elektronicznej</span><span class="sxs-lookup"><span data-stu-id="1c50e-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="1c50e-119">W polu Definicja modelu danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1c50e-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="1c50e-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="1c50e-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="1c50e-121">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="1c50e-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="1c50e-122">Projektowanie formatu w celu dodania do generowanego komunikatu treści załączników w formacie MIME</span><span class="sxs-lookup"><span data-stu-id="1c50e-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="1c50e-123">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="1c50e-123">Click Designer.</span></span>
2. <span data-ttu-id="1c50e-124">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="1c50e-125">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="1c50e-126">W polu Nazwa wpisz „Faktura”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="1c50e-127">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="1c50e-127">Invoice</span></span>  
5. <span data-ttu-id="1c50e-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-128">Click OK.</span></span>
6. <span data-ttu-id="1c50e-129">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="1c50e-130">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="1c50e-131">W polu Nazwa wpisz „SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="1c50e-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="1c50e-132">SalesOrder</span></span>  
9. <span data-ttu-id="1c50e-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-133">Click OK.</span></span>
10. <span data-ttu-id="1c50e-134">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="1c50e-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="1c50e-135">W polu Nazwa wpisz „InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="1c50e-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="1c50e-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="1c50e-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-137">Click OK.</span></span>
13. <span data-ttu-id="1c50e-138">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="1c50e-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="1c50e-139">W polu Nazwa wpisz „InvoiceAmount”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="1c50e-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="1c50e-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="1c50e-141">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-141">Click OK.</span></span>
16. <span data-ttu-id="1c50e-142">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="1c50e-143">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="1c50e-144">W polu Nazwa wpisz „EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="1c50e-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="1c50e-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="1c50e-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-146">Click OK.</span></span>
20. <span data-ttu-id="1c50e-147">W drzewie zaznacz element „Faktura\EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="1c50e-148">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="1c50e-148">Click Add Element.</span></span>
22. <span data-ttu-id="1c50e-149">W polu Nazwa wpisz „Dokument”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="1c50e-150">Wydruk pokwitowania</span><span class="sxs-lookup"><span data-stu-id="1c50e-150">Document</span></span>  
23. <span data-ttu-id="1c50e-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-151">Click OK.</span></span>
24. <span data-ttu-id="1c50e-152">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="1c50e-153">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="1c50e-154">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="1c50e-155">W polu Nazwa wpisz „FileName”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="1c50e-156">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="1c50e-156">FileName</span></span>  
28. <span data-ttu-id="1c50e-157">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-157">Click OK.</span></span>
29. <span data-ttu-id="1c50e-158">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="1c50e-159">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="1c50e-160">W polu Nazwa wpisz „FileContent”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="1c50e-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="1c50e-161">FileContent</span></span>  
32. <span data-ttu-id="1c50e-162">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-162">Click OK.</span></span>
33. <span data-ttu-id="1c50e-163">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileContent”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="1c50e-164">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1c50e-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="1c50e-165">W drzewie zaznacz element „Tekst\Base64”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="1c50e-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1c50e-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="1c50e-167">Mapowanie elementów formatu na model danych jako źródło danych</span><span class="sxs-lookup"><span data-stu-id="1c50e-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="1c50e-168">W drzewie zaznacz element „Faktura\SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="1c50e-169">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="1c50e-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="1c50e-170">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="1c50e-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="1c50e-171">W drzewie zaznacz element „model\Numer zamówienia sprzedaży(SalesId)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="1c50e-172">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="1c50e-172">Click Bind.</span></span>
6. <span data-ttu-id="1c50e-173">W drzewie zaznacz element „Faktura\InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="1c50e-174">W drzewie rozwiń węzeł „model\Faktura podstawowa(InvoiceBase)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="1c50e-175">W drzewie zaznacz element „model\Faktura podstawowa(InvoiceBase)\Numer faktury(Identyfikator)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="1c50e-176">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="1c50e-176">Click Bind.</span></span>
10. <span data-ttu-id="1c50e-177">W drzewie zaznacz element „Faktura\InvoiceAmount”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="1c50e-178">W drzewie zaznacz element „model\Faktura podstawowa(InvoiceBase)\Kwota faktury(Kwota)”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="1c50e-179">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="1c50e-179">Click Bind.</span></span>
13. <span data-ttu-id="1c50e-180">W drzewie rozwiń węzeł „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="1c50e-181">W drzewie zaznacz element „model\Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="1c50e-182">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileContent\Base64”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="1c50e-183">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="1c50e-183">Click Bind.</span></span>
17. <span data-ttu-id="1c50e-184">W drzewie zaznacz element „model\Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="1c50e-185">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileName”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="1c50e-186">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="1c50e-186">Click Bind.</span></span>
20. <span data-ttu-id="1c50e-187">W drzewie zaznacz element „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="1c50e-188">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument”.</span><span class="sxs-lookup"><span data-stu-id="1c50e-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="1c50e-189">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="1c50e-189">Click Bind.</span></span>
23. <span data-ttu-id="1c50e-190">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1c50e-190">Click Save.</span></span>
24. <span data-ttu-id="1c50e-191">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1c50e-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]