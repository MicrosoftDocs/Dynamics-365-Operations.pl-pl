---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2 — Rozszerzanie modelu danych)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5923a14f4ba544154bf40391896d29826d3ce1b1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681818"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="57d14-103">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2 — Rozszerzanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="57d14-103">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57d14-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="57d14-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="57d14-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="57d14-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="57d14-106">W celu wykonania tych kroków należy najpierw wykonać kroki opisane w przewodniku po zadaniu „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1: Przygotowanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="57d14-106">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="57d14-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="57d14-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="57d14-108">Rozszerzanie modelu danych w celu przedstawienia w nim plików zarządzania dokumentami</span><span class="sxs-lookup"><span data-stu-id="57d14-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="57d14-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="57d14-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="57d14-110">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="57d14-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="57d14-111">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="57d14-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="57d14-112">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="57d14-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="57d14-113">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="57d14-113">Click Designer.</span></span>
6. <span data-ttu-id="57d14-114">W drzewie zaznacz element „Faktura dla odbiorcy(InvoiceCustomer)”.</span><span class="sxs-lookup"><span data-stu-id="57d14-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="57d14-115">Rozszerzymy ten model danych w celu udostępnienia w nim wszystkich plików, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.</span><span class="sxs-lookup"><span data-stu-id="57d14-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="57d14-116">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57d14-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="57d14-117">W polu Nazwa wpisz „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="57d14-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="57d14-118">Załączniki faktur</span><span class="sxs-lookup"><span data-stu-id="57d14-118">Invoice attachments</span></span>  
9. <span data-ttu-id="57d14-119">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="57d14-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="57d14-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="57d14-120">Click Add.</span></span>
11. <span data-ttu-id="57d14-121">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57d14-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="57d14-122">W polu Nazwa wpisz „Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="57d14-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="57d14-123">Zawartość pliku</span><span class="sxs-lookup"><span data-stu-id="57d14-123">File content</span></span>  
13. <span data-ttu-id="57d14-124">W polu Typ elementu wybierz opcję „Kontener”.</span><span class="sxs-lookup"><span data-stu-id="57d14-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="57d14-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="57d14-125">Click Add.</span></span>
15. <span data-ttu-id="57d14-126">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="57d14-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="57d14-127">W polu Nazwa wpisz „Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="57d14-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="57d14-128">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="57d14-128">File name</span></span>  
17. <span data-ttu-id="57d14-129">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="57d14-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="57d14-130">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="57d14-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="57d14-131">Mapowanie elementów nowego modelu danych na źródła danych</span><span class="sxs-lookup"><span data-stu-id="57d14-131">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="57d14-132">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="57d14-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="57d14-133">Użyj szybkiego filtru, aby wyfiltrować pole Definicja według wartości „InvoiceCustomer”.</span><span class="sxs-lookup"><span data-stu-id="57d14-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="57d14-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="57d14-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="57d14-135">Zmapujemy elementy nowego modelu na odpowiednie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="57d14-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="57d14-136">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="57d14-136">Click Designer.</span></span>
4. <span data-ttu-id="57d14-137">W drzewie zaznacz element „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="57d14-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="57d14-138">W drzewie rozwiń węzeł „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="57d14-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="57d14-139">W drzewie zaznacz element „Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="57d14-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="57d14-140">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="57d14-140">Click Edit.</span></span>
8. <span data-ttu-id="57d14-141">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'”.</span><span class="sxs-lookup"><span data-stu-id="57d14-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="57d14-142">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="57d14-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="57d14-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="57d14-143">Click Save.</span></span>
10. <span data-ttu-id="57d14-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57d14-144">Close the page.</span></span>
11. <span data-ttu-id="57d14-145">W drzewie zaznacz element „Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="57d14-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="57d14-146">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="57d14-146">Click Edit.</span></span>
13. <span data-ttu-id="57d14-147">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'”.</span><span class="sxs-lookup"><span data-stu-id="57d14-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="57d14-148">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="57d14-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="57d14-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="57d14-149">Click Save.</span></span>
15. <span data-ttu-id="57d14-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57d14-150">Close the page.</span></span>
16. <span data-ttu-id="57d14-151">W drzewie zaznacz element „Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="57d14-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="57d14-152">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="57d14-152">Click Edit.</span></span>
18. <span data-ttu-id="57d14-153">W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'”.</span><span class="sxs-lookup"><span data-stu-id="57d14-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="57d14-154">CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'</span><span class="sxs-lookup"><span data-stu-id="57d14-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="57d14-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="57d14-155">Click Save.</span></span>
20. <span data-ttu-id="57d14-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57d14-156">Close the page.</span></span>
21. <span data-ttu-id="57d14-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="57d14-157">Click Save.</span></span>
22. <span data-ttu-id="57d14-158">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57d14-158">Close the page.</span></span>
23. <span data-ttu-id="57d14-159">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57d14-159">Close the page.</span></span>
24. <span data-ttu-id="57d14-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57d14-160">Close the page.</span></span>
25. <span data-ttu-id="57d14-161">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="57d14-161">Click Change status.</span></span>
26. <span data-ttu-id="57d14-162">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="57d14-162">Click Complete.</span></span>
27. <span data-ttu-id="57d14-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="57d14-163">Click OK.</span></span>

