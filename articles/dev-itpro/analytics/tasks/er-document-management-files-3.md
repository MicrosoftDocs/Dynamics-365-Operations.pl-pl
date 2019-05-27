---
title: Tworzenie formatów w celu używania plików zarządzania dokumentami w danych wyjściowych raportowania elektronicznego
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego, aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1815a0004eee6734b3c7d2c2f9e75ce5fe16af1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544755"
---
# <a name="create-formats-to-use-document-management-files-in-er-output"></a><span data-ttu-id="c5ba1-103">Tworzenie formatów w celu używania plików zarządzania dokumentami w danych wyjściowych raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="c5ba1-103">Create formats to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c5ba1-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="c5ba1-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="c5ba1-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c5ba1-106">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2: Rozszerzanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="c5ba1-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="c5ba1-108">Tworzenie formatu przetwarzania faktur</span><span class="sxs-lookup"><span data-stu-id="c5ba1-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="c5ba1-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c5ba1-110">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="c5ba1-111">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="c5ba1-112">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="c5ba1-113">Utworzysz format do generowania komunikatów elektronicznych z informacjami o wszystkich plikach, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="c5ba1-114">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="c5ba1-115">W polu Nowy wpisz „Format oparty na modelu danych Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="c5ba1-116">W polu Nazwa wpisz „Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="c5ba1-117">Przykładowy komunikat faktury elektronicznej</span><span class="sxs-lookup"><span data-stu-id="c5ba1-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="c5ba1-118">W polu Definicja modelu danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ba1-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="c5ba1-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="c5ba1-120">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="c5ba1-121">Projektowanie formatu w celu dodania do generowanego komunikatu treści załączników w formacie MIME</span><span class="sxs-lookup"><span data-stu-id="c5ba1-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="c5ba1-122">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-122">Click Designer.</span></span>
2. <span data-ttu-id="c5ba1-123">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="c5ba1-124">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="c5ba1-125">W polu Nazwa wpisz „Faktura”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="c5ba1-126">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="c5ba1-126">Invoice</span></span>  
5. <span data-ttu-id="c5ba1-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-127">Click OK.</span></span>
6. <span data-ttu-id="c5ba1-128">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="c5ba1-129">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="c5ba1-130">W polu Nazwa wpisz „SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="c5ba1-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="c5ba1-131">SalesOrder</span></span>  
9. <span data-ttu-id="c5ba1-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-132">Click OK.</span></span>
10. <span data-ttu-id="c5ba1-133">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="c5ba1-134">W polu Nazwa wpisz „InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="c5ba1-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="c5ba1-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="c5ba1-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-136">Click OK.</span></span>
13. <span data-ttu-id="c5ba1-137">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="c5ba1-138">W polu Nazwa wpisz „InvoiceAmount”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="c5ba1-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="c5ba1-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="c5ba1-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-140">Click OK.</span></span>
16. <span data-ttu-id="c5ba1-141">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="c5ba1-142">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="c5ba1-143">W polu Nazwa wpisz „EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="c5ba1-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="c5ba1-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="c5ba1-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-145">Click OK.</span></span>
20. <span data-ttu-id="c5ba1-146">W drzewie zaznacz element „Faktura\EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="c5ba1-147">Kliknij opcję Dodaj element.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-147">Click Add Element.</span></span>
22. <span data-ttu-id="c5ba1-148">W polu Nazwa wpisz „Dokument”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="c5ba1-149">Wydruk pokwitowania</span><span class="sxs-lookup"><span data-stu-id="c5ba1-149">Document</span></span>  
23. <span data-ttu-id="c5ba1-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-150">Click OK.</span></span>
24. <span data-ttu-id="c5ba1-151">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="c5ba1-152">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="c5ba1-153">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="c5ba1-154">W polu Nazwa wpisz „FileName”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="c5ba1-155">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="c5ba1-155">FileName</span></span>  
28. <span data-ttu-id="c5ba1-156">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-156">Click OK.</span></span>
29. <span data-ttu-id="c5ba1-157">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="c5ba1-158">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="c5ba1-159">W polu Nazwa wpisz „FileContent”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="c5ba1-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="c5ba1-160">FileContent</span></span>  
32. <span data-ttu-id="c5ba1-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-161">Click OK.</span></span>
33. <span data-ttu-id="c5ba1-162">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileContent”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="c5ba1-163">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="c5ba1-164">W drzewie zaznacz element „Tekst\Base64”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="c5ba1-165">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="c5ba1-166">Mapowanie elementów formatu na model danych jako źródło danych</span><span class="sxs-lookup"><span data-stu-id="c5ba1-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="c5ba1-167">W drzewie zaznacz element „Faktura\SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="c5ba1-168">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="c5ba1-169">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="c5ba1-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="c5ba1-170">W drzewie zaznacz element „model\Numer zamówienia sprzedaży(SalesId)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="c5ba1-171">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-171">Click Bind.</span></span>
6. <span data-ttu-id="c5ba1-172">W drzewie zaznacz element „Faktura\InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="c5ba1-173">W drzewie rozwiń węzeł „model\Faktura podstawowa(InvoiceBase)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="c5ba1-174">W drzewie zaznacz element „model\Faktura podstawowa(InvoiceBase)\Numer faktury(Identyfikator)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="c5ba1-175">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-175">Click Bind.</span></span>
10. <span data-ttu-id="c5ba1-176">W drzewie zaznacz element „Faktura\InvoiceAmount”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="c5ba1-177">W drzewie zaznacz element „model\Faktura podstawowa(InvoiceBase)\Kwota faktury(Kwota)”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="c5ba1-178">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-178">Click Bind.</span></span>
13. <span data-ttu-id="c5ba1-179">W drzewie rozwiń węzeł „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="c5ba1-180">W drzewie zaznacz element „model\Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="c5ba1-181">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileContent\Base64”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="c5ba1-182">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-182">Click Bind.</span></span>
17. <span data-ttu-id="c5ba1-183">W drzewie zaznacz element „model\Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="c5ba1-184">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileName”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="c5ba1-185">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-185">Click Bind.</span></span>
20. <span data-ttu-id="c5ba1-186">W drzewie zaznacz element „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="c5ba1-187">W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument”.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="c5ba1-188">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-188">Click Bind.</span></span>
23. <span data-ttu-id="c5ba1-189">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-189">Click Save.</span></span>
24. <span data-ttu-id="c5ba1-190">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c5ba1-190">Close the page.</span></span>

