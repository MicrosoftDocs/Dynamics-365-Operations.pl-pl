--- 
title: "Rozszerzanie modelu danych w celu używania plików zarządzania dokumentami w danych wyjściowych formatu na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników)."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f3d494cc83b273eef071b23d0948b283ba85c17e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="c2e2f-103">Rozszerzanie modelu danych w celu używania plików zarządzania dokumentami w danych wyjściowych formatu na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="c2e2f-103">Extend data model to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c2e2f-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="c2e2f-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="c2e2f-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c2e2f-106">W celu wykonania tych kroków należy najpierw wykonać kroki opisane w przewodniku po zadaniu „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1: Przygotowanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="c2e2f-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="c2e2f-108">Rozszerzanie modelu danych w celu przedstawienia w nim plików zarządzania dokumentami</span><span class="sxs-lookup"><span data-stu-id="c2e2f-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="c2e2f-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c2e2f-110">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="c2e2f-111">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="c2e2f-112">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="c2e2f-113">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-113">Click Designer.</span></span>
6. <span data-ttu-id="c2e2f-114">W drzewie zaznacz element „Faktura dla odbiorcy(InvoiceCustomer)”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="c2e2f-115">Rozszerzymy ten model danych w celu udostępnienia w nim wszystkich plików, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="c2e2f-116">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="c2e2f-117">W polu Nazwa wpisz „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="c2e2f-118">Załączniki faktur</span><span class="sxs-lookup"><span data-stu-id="c2e2f-118">Invoice attachments</span></span>  
9. <span data-ttu-id="c2e2f-119">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="c2e2f-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-120">Click Add.</span></span>
11. <span data-ttu-id="c2e2f-121">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="c2e2f-122">W polu Nazwa wpisz „Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="c2e2f-123">Zawartość pliku</span><span class="sxs-lookup"><span data-stu-id="c2e2f-123">File content</span></span>  
13. <span data-ttu-id="c2e2f-124">W polu Typ elementu wybierz opcję „Kontener”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="c2e2f-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-125">Click Add.</span></span>
15. <span data-ttu-id="c2e2f-126">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="c2e2f-127">W polu Nazwa wpisz „Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="c2e2f-128">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="c2e2f-128">File name</span></span>  
17. <span data-ttu-id="c2e2f-129">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="c2e2f-130">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="c2e2f-131">Mapowanie elementów nowego modelu danych na źródła danych programu Dynamics 365 for Finance and Operations Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c2e2f-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="c2e2f-132">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="c2e2f-133">Użyj szybkiego filtru, aby wyfiltrować pole Definicja według wartości „InvoiceCustomer”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="c2e2f-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="c2e2f-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="c2e2f-135">Zmapujemy elementy nowego modelu na odpowiednie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="c2e2f-136">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-136">Click Designer.</span></span>
4. <span data-ttu-id="c2e2f-137">W drzewie zaznacz element „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="c2e2f-138">W drzewie rozwiń węzeł „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="c2e2f-139">W drzewie zaznacz element „Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="c2e2f-140">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-140">Click Edit.</span></span>
8. <span data-ttu-id="c2e2f-141">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="c2e2f-142">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="c2e2f-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="c2e2f-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-143">Click Save.</span></span>
10. <span data-ttu-id="c2e2f-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-144">Close the page.</span></span>
11. <span data-ttu-id="c2e2f-145">W drzewie zaznacz element „Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="c2e2f-146">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-146">Click Edit.</span></span>
13. <span data-ttu-id="c2e2f-147">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="c2e2f-148">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="c2e2f-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="c2e2f-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-149">Click Save.</span></span>
15. <span data-ttu-id="c2e2f-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-150">Close the page.</span></span>
16. <span data-ttu-id="c2e2f-151">W drzewie zaznacz element „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="c2e2f-152">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-152">Click Edit.</span></span>
18. <span data-ttu-id="c2e2f-153">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'”.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="c2e2f-154">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'</span><span class="sxs-lookup"><span data-stu-id="c2e2f-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="c2e2f-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-155">Click Save.</span></span>
20. <span data-ttu-id="c2e2f-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-156">Close the page.</span></span>
21. <span data-ttu-id="c2e2f-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-157">Click Save.</span></span>
22. <span data-ttu-id="c2e2f-158">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-158">Close the page.</span></span>
23. <span data-ttu-id="c2e2f-159">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-159">Close the page.</span></span>
24. <span data-ttu-id="c2e2f-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-160">Close the page.</span></span>
25. <span data-ttu-id="c2e2f-161">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-161">Click Change status.</span></span>
26. <span data-ttu-id="c2e2f-162">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-162">Click Complete.</span></span>
27. <span data-ttu-id="c2e2f-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c2e2f-163">Click OK.</span></span>


