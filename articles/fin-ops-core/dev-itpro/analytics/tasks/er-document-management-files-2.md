---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2 — Rozszerzanie modelu danych)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego (ER) do używania plików zarządzania dokumentami (załączników) w danych wyjściowych ER. (część 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b47c35790ce04a494b6c58f6e04fa9b829d2ab93
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559780"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="79409-104">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2 — Rozszerzanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="79409-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79409-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="79409-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="79409-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="79409-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="79409-107">W celu wykonania tych kroków należy najpierw wykonać kroki opisane w przewodniku po zadaniu „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1: Przygotowanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="79409-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="79409-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="79409-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="79409-109">Rozszerzanie modelu danych w celu przedstawienia w nim plików zarządzania dokumentami</span><span class="sxs-lookup"><span data-stu-id="79409-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="79409-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="79409-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="79409-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="79409-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="79409-112">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="79409-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="79409-113">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="79409-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="79409-114">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="79409-114">Click Designer.</span></span>
6. <span data-ttu-id="79409-115">W drzewie zaznacz element „Faktura dla odbiorcy(InvoiceCustomer)”.</span><span class="sxs-lookup"><span data-stu-id="79409-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="79409-116">Rozszerzymy ten model danych w celu udostępnienia w nim wszystkich plików, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.</span><span class="sxs-lookup"><span data-stu-id="79409-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="79409-117">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="79409-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="79409-118">W polu Nazwa wpisz „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="79409-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="79409-119">Załączniki faktur</span><span class="sxs-lookup"><span data-stu-id="79409-119">Invoice attachments</span></span>  
9. <span data-ttu-id="79409-120">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="79409-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="79409-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="79409-121">Click Add.</span></span>
11. <span data-ttu-id="79409-122">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="79409-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="79409-123">W polu Nazwa wpisz „Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="79409-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="79409-124">Zawartość pliku</span><span class="sxs-lookup"><span data-stu-id="79409-124">File content</span></span>  
13. <span data-ttu-id="79409-125">W polu Typ elementu wybierz opcję „Kontener”.</span><span class="sxs-lookup"><span data-stu-id="79409-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="79409-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="79409-126">Click Add.</span></span>
15. <span data-ttu-id="79409-127">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="79409-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="79409-128">W polu Nazwa wpisz „Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="79409-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="79409-129">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="79409-129">File name</span></span>  
17. <span data-ttu-id="79409-130">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="79409-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="79409-131">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="79409-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="79409-132">Mapowanie elementów nowego modelu danych na źródła danych</span><span class="sxs-lookup"><span data-stu-id="79409-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="79409-133">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="79409-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="79409-134">Użyj szybkiego filtru, aby wyfiltrować pole Definicja według wartości „InvoiceCustomer”.</span><span class="sxs-lookup"><span data-stu-id="79409-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="79409-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="79409-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="79409-136">Zmapujemy elementy nowego modelu na odpowiednie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="79409-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="79409-137">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="79409-137">Click Designer.</span></span>
4. <span data-ttu-id="79409-138">W drzewie zaznacz element „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="79409-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="79409-139">W drzewie rozwiń węzeł „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="79409-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="79409-140">W drzewie zaznacz element „Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="79409-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="79409-141">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="79409-141">Click Edit.</span></span>
8. <span data-ttu-id="79409-142">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'”.</span><span class="sxs-lookup"><span data-stu-id="79409-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="79409-143">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="79409-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="79409-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="79409-144">Click Save.</span></span>
10. <span data-ttu-id="79409-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="79409-145">Close the page.</span></span>
11. <span data-ttu-id="79409-146">W drzewie zaznacz element „Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="79409-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="79409-147">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="79409-147">Click Edit.</span></span>
13. <span data-ttu-id="79409-148">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'”.</span><span class="sxs-lookup"><span data-stu-id="79409-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="79409-149">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="79409-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="79409-150">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="79409-150">Click Save.</span></span>
15. <span data-ttu-id="79409-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="79409-151">Close the page.</span></span>
16. <span data-ttu-id="79409-152">W drzewie zaznacz element „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="79409-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="79409-153">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="79409-153">Click Edit.</span></span>
18. <span data-ttu-id="79409-154">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'”.</span><span class="sxs-lookup"><span data-stu-id="79409-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="79409-155">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'</span><span class="sxs-lookup"><span data-stu-id="79409-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="79409-156">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="79409-156">Click Save.</span></span>
20. <span data-ttu-id="79409-157">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="79409-157">Close the page.</span></span>
21. <span data-ttu-id="79409-158">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="79409-158">Click Save.</span></span>
22. <span data-ttu-id="79409-159">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="79409-159">Close the page.</span></span>
23. <span data-ttu-id="79409-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="79409-160">Close the page.</span></span>
24. <span data-ttu-id="79409-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="79409-161">Close the page.</span></span>
25. <span data-ttu-id="79409-162">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="79409-162">Click Change status.</span></span>
26. <span data-ttu-id="79409-163">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="79409-163">Click Complete.</span></span>
27. <span data-ttu-id="79409-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="79409-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]