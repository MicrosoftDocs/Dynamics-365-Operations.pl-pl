---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 4 — inicjowanie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do używania plików zarządzania dokumentami w wynikach ER. (część 4)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d437b31b8a55f345ebc3567bc8c6a2c5ecfd2eec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092523"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="3820e-104">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 4 — inicjowanie formatu)</span><span class="sxs-lookup"><span data-stu-id="3820e-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3820e-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="3820e-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="3820e-106">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="3820e-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="3820e-107">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3: Tworzenie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="3820e-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="3820e-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="3820e-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="3820e-109">Dodawanie niezbędnych załączników dla zamówienia sprzedaży z jedną fakturą</span><span class="sxs-lookup"><span data-stu-id="3820e-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="3820e-110">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Otwarte faktury odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3820e-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="3820e-111">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="3820e-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3820e-112">Na przykład wyfiltruj według pola Faktura z wartością „CIV-000148”.</span><span class="sxs-lookup"><span data-stu-id="3820e-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="3820e-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="3820e-113">CIV-000148</span></span>  
3. <span data-ttu-id="3820e-114">Kliknij, aby otworzyć łącze do wybranej faktury.</span><span class="sxs-lookup"><span data-stu-id="3820e-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="3820e-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="3820e-115">CIV-000148</span></span>  
4. <span data-ttu-id="3820e-116">Kliknij, aby otworzyć łącze istniejące w polu Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3820e-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="3820e-117">000148</span><span class="sxs-lookup"><span data-stu-id="3820e-117">000148</span></span>  
5. <span data-ttu-id="3820e-118">W polu Wiersze lub nagłówek wybierz opcję Nagłówek.</span><span class="sxs-lookup"><span data-stu-id="3820e-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="3820e-119">Wybierz opcję Nagłówek, aby wskazać, że będzie to docelowe miejsce dodawania załączników.</span><span class="sxs-lookup"><span data-stu-id="3820e-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="3820e-120">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="3820e-120">Click Attach.</span></span>
    * <span data-ttu-id="3820e-121">Dodaj kilka plików jako załączniki do tego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3820e-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="3820e-122">Użyj plików dokumentów o typach obsługiwanych w zarządzaniu dokumentami (z rozszerzeniem DOCX, DPF, XML, JPG itp.).</span><span class="sxs-lookup"><span data-stu-id="3820e-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="3820e-123">Znajdź i zaznacz pliki, które mają zostać dołączone i być dalej przetwarzane z powiązaną fakturą w komunikacie elektronicznym raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="3820e-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="3820e-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3820e-124">Click New.</span></span>
8. <span data-ttu-id="3820e-125">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="3820e-125">Click File.</span></span>
9. <span data-ttu-id="3820e-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3820e-126">Click New.</span></span>
10. <span data-ttu-id="3820e-127">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="3820e-127">Click File.</span></span>
11. <span data-ttu-id="3820e-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3820e-128">Close the page.</span></span>
12. <span data-ttu-id="3820e-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3820e-129">Close the page.</span></span>
13. <span data-ttu-id="3820e-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3820e-130">Close the page.</span></span>
14. <span data-ttu-id="3820e-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3820e-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="3820e-132">Generowanie zaprojektowanego raportu dla wybranej faktury</span><span class="sxs-lookup"><span data-stu-id="3820e-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="3820e-133">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="3820e-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3820e-134">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="3820e-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="3820e-135">W drzewie rozwiń węzeł „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="3820e-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="3820e-136">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)\Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="3820e-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="3820e-137">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="3820e-137">Click Run.</span></span>
6. <span data-ttu-id="3820e-138">Rozwiń sekcję Rekordy do uwzględnienia ().</span><span class="sxs-lookup"><span data-stu-id="3820e-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="3820e-139">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="3820e-139">Click Filter.</span></span>
8. <span data-ttu-id="3820e-140">Zaznacz wiersz z arkuszem faktur dla odbiorcy i polem Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3820e-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="3820e-141">W polu Kryteria wpisz wartość „000148”.</span><span class="sxs-lookup"><span data-stu-id="3820e-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="3820e-142">W polu kryteriów „Zamówienie sprzedaży” wpisz numer zamówienia 000148.</span><span class="sxs-lookup"><span data-stu-id="3820e-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="3820e-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3820e-143">Click OK.</span></span>
11. <span data-ttu-id="3820e-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3820e-144">Click OK.</span></span>
    * <span data-ttu-id="3820e-145">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="3820e-145">Review the generated output.</span></span> <span data-ttu-id="3820e-146">Należy zauważyć, że dla każdego załącznika został utworzony jeden węzeł XML.</span><span class="sxs-lookup"><span data-stu-id="3820e-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="3820e-147">Treść załączników zostanie zapisana w danych wyjściowych XML w formacie tekstowym MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="3820e-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  

