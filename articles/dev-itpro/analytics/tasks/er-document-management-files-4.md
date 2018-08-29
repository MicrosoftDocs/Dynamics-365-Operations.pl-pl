--- 
title: "Uruchamianie formatów w celu używania plików zarządzania dokumentami w danych wyjściowych raportowania elektronicznego"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników)."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.openlocfilehash: e0c01a44bde47860b3ad587da73dc2760e9ef4fc
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="run-formats-to-use-document-management-files-in-er-output"></a><span data-ttu-id="e025c-103">Uruchamianie formatów w celu używania plików zarządzania dokumentami w danych wyjściowych raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="e025c-103">Run formats to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e025c-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="e025c-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="e025c-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="e025c-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="e025c-106">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3: Tworzenie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="e025c-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="e025c-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="e025c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="e025c-108">Dodawanie niezbędnych załączników dla zamówienia sprzedaży z jedną fakturą</span><span class="sxs-lookup"><span data-stu-id="e025c-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="e025c-109">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Otwarte faktury odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e025c-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="e025c-110">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="e025c-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e025c-111">Na przykład wyfiltruj według pola Faktura z wartością „CIV-000148”.</span><span class="sxs-lookup"><span data-stu-id="e025c-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="e025c-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="e025c-112">CIV-000148</span></span>  
3. <span data-ttu-id="e025c-113">Kliknij, aby otworzyć łącze do wybranej faktury.</span><span class="sxs-lookup"><span data-stu-id="e025c-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="e025c-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="e025c-114">CIV-000148</span></span>  
4. <span data-ttu-id="e025c-115">Kliknij, aby otworzyć łącze istniejące w polu Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e025c-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="e025c-116">000148</span><span class="sxs-lookup"><span data-stu-id="e025c-116">000148</span></span>  
5. <span data-ttu-id="e025c-117">W polu Wiersze lub nagłówek wybierz opcję Nagłówek.</span><span class="sxs-lookup"><span data-stu-id="e025c-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="e025c-118">Wybierz opcję Nagłówek, aby wskazać, że będzie to docelowe miejsce dodawania załączników.</span><span class="sxs-lookup"><span data-stu-id="e025c-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="e025c-119">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="e025c-119">Click Attach.</span></span>
    * <span data-ttu-id="e025c-120">Dodaj kilka plików jako załączniki do tego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e025c-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="e025c-121">Użyj plików dokumentów o typach obsługiwanych w zarządzaniu dokumentami (z rozszerzeniem DOCX, DPF, XML, JPG itp.).</span><span class="sxs-lookup"><span data-stu-id="e025c-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="e025c-122">Znajdź i zaznacz pliki, które mają zostać dołączone i być dalej przetwarzane z powiązaną fakturą w komunikacie elektronicznym raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="e025c-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="e025c-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e025c-123">Click New.</span></span>
8. <span data-ttu-id="e025c-124">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="e025c-124">Click File.</span></span>
9. <span data-ttu-id="e025c-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e025c-125">Click New.</span></span>
10. <span data-ttu-id="e025c-126">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="e025c-126">Click File.</span></span>
11. <span data-ttu-id="e025c-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e025c-127">Close the page.</span></span>
12. <span data-ttu-id="e025c-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e025c-128">Close the page.</span></span>
13. <span data-ttu-id="e025c-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e025c-129">Close the page.</span></span>
14. <span data-ttu-id="e025c-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e025c-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="e025c-131">Generowanie zaprojektowanego raportu dla wybranej faktury</span><span class="sxs-lookup"><span data-stu-id="e025c-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="e025c-132">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="e025c-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="e025c-133">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="e025c-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="e025c-134">W drzewie rozwiń węzeł „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="e025c-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="e025c-135">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)\Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="e025c-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="e025c-136">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="e025c-136">Click Run.</span></span>
6. <span data-ttu-id="e025c-137">Rozwiń sekcję Rekordy do uwzględnienia ().</span><span class="sxs-lookup"><span data-stu-id="e025c-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="e025c-138">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="e025c-138">Click Filter.</span></span>
8. <span data-ttu-id="e025c-139">Zaznacz wiersz z arkuszem faktur dla odbiorcy i polem Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e025c-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="e025c-140">W polu Kryteria wpisz wartość „000148”.</span><span class="sxs-lookup"><span data-stu-id="e025c-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="e025c-141">W polu kryteriów „Zamówienie sprzedaży” wpisz numer zamówienia 000148.</span><span class="sxs-lookup"><span data-stu-id="e025c-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="e025c-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e025c-142">Click OK.</span></span>
11. <span data-ttu-id="e025c-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e025c-143">Click OK.</span></span>
    * <span data-ttu-id="e025c-144">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e025c-144">Review the generated output.</span></span> <span data-ttu-id="e025c-145">Należy zauważyć, że dla każdego załącznika został utworzony jeden węzeł XML.</span><span class="sxs-lookup"><span data-stu-id="e025c-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="e025c-146">Treść załączników zostanie zapisana w danych wyjściowych XML w formacie tekstowym MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="e025c-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  


