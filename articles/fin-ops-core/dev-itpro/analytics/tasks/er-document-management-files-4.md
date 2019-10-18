---
title: Uruchamianie formatów w celu używania plików zarządzania dokumentami w danych wyjściowych raportowania elektronicznego
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego, aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8dc541af4d26b61ff9b90e08a8ca2c6a6bb8e70
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185021"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4-run-format"></a><span data-ttu-id="d180d-103">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 4: Inicjowanie formatu)</span><span class="sxs-lookup"><span data-stu-id="d180d-103">ER Use Document Management files in format outputs (Part 4: Run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d180d-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="d180d-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="d180d-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="d180d-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="d180d-106">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3: Tworzenie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="d180d-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="d180d-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="d180d-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="d180d-108">Dodawanie niezbędnych załączników dla zamówienia sprzedaży z jedną fakturą</span><span class="sxs-lookup"><span data-stu-id="d180d-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="d180d-109">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Otwarte faktury odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d180d-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="d180d-110">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="d180d-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d180d-111">Na przykład wyfiltruj według pola Faktura z wartością „CIV-000148”.</span><span class="sxs-lookup"><span data-stu-id="d180d-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="d180d-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="d180d-112">CIV-000148</span></span>  
3. <span data-ttu-id="d180d-113">Kliknij, aby otworzyć łącze do wybranej faktury.</span><span class="sxs-lookup"><span data-stu-id="d180d-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="d180d-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="d180d-114">CIV-000148</span></span>  
4. <span data-ttu-id="d180d-115">Kliknij, aby otworzyć łącze istniejące w polu Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d180d-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="d180d-116">000148</span><span class="sxs-lookup"><span data-stu-id="d180d-116">000148</span></span>  
5. <span data-ttu-id="d180d-117">W polu Wiersze lub nagłówek wybierz opcję Nagłówek.</span><span class="sxs-lookup"><span data-stu-id="d180d-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="d180d-118">Wybierz opcję Nagłówek, aby wskazać, że będzie to docelowe miejsce dodawania załączników.</span><span class="sxs-lookup"><span data-stu-id="d180d-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="d180d-119">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="d180d-119">Click Attach.</span></span>
    * <span data-ttu-id="d180d-120">Dodaj kilka plików jako załączniki do tego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d180d-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="d180d-121">Użyj plików dokumentów o typach obsługiwanych w zarządzaniu dokumentami (z rozszerzeniem DOCX, DPF, XML, JPG itp.).</span><span class="sxs-lookup"><span data-stu-id="d180d-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="d180d-122">Znajdź i zaznacz pliki, które mają zostać dołączone i być dalej przetwarzane z powiązaną fakturą w komunikacie elektronicznym raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="d180d-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="d180d-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d180d-123">Click New.</span></span>
8. <span data-ttu-id="d180d-124">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="d180d-124">Click File.</span></span>
9. <span data-ttu-id="d180d-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d180d-125">Click New.</span></span>
10. <span data-ttu-id="d180d-126">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="d180d-126">Click File.</span></span>
11. <span data-ttu-id="d180d-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d180d-127">Close the page.</span></span>
12. <span data-ttu-id="d180d-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d180d-128">Close the page.</span></span>
13. <span data-ttu-id="d180d-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d180d-129">Close the page.</span></span>
14. <span data-ttu-id="d180d-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d180d-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="d180d-131">Generowanie zaprojektowanego raportu dla wybranej faktury</span><span class="sxs-lookup"><span data-stu-id="d180d-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="d180d-132">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="d180d-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d180d-133">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="d180d-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="d180d-134">W drzewie rozwiń węzeł „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="d180d-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="d180d-135">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)\Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="d180d-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="d180d-136">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="d180d-136">Click Run.</span></span>
6. <span data-ttu-id="d180d-137">Rozwiń sekcję Rekordy do uwzględnienia ().</span><span class="sxs-lookup"><span data-stu-id="d180d-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="d180d-138">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="d180d-138">Click Filter.</span></span>
8. <span data-ttu-id="d180d-139">Zaznacz wiersz z arkuszem faktur dla odbiorcy i polem Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d180d-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="d180d-140">W polu Kryteria wpisz wartość „000148”.</span><span class="sxs-lookup"><span data-stu-id="d180d-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="d180d-141">W polu kryteriów „Zamówienie sprzedaży” wpisz numer zamówienia 000148.</span><span class="sxs-lookup"><span data-stu-id="d180d-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="d180d-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d180d-142">Click OK.</span></span>
11. <span data-ttu-id="d180d-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d180d-143">Click OK.</span></span>
    * <span data-ttu-id="d180d-144">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="d180d-144">Review the generated output.</span></span> <span data-ttu-id="d180d-145">Należy zauważyć, że dla każdego załącznika został utworzony jeden węzeł XML.</span><span class="sxs-lookup"><span data-stu-id="d180d-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="d180d-146">Treść załączników zostanie zapisana w danych wyjściowych XML w formacie tekstowym MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="d180d-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  

