---
title: Przetwarzanie odsetek
description: W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fba25c900461fbbf4db0cd3b93847d258704ab4e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842888"
---
# <a name="process-interest"></a><span data-ttu-id="dc4de-103">Przetwarzanie odsetek</span><span class="sxs-lookup"><span data-stu-id="dc4de-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc4de-104">W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="dc4de-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="dc4de-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="dc4de-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="dc4de-106">Konfigurowanie odsetek w profilu księgowania</span><span class="sxs-lookup"><span data-stu-id="dc4de-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="dc4de-107">Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców.</span><span class="sxs-lookup"><span data-stu-id="dc4de-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="dc4de-108">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="dc4de-108">Click Edit.</span></span>
    * <span data-ttu-id="dc4de-109">Z listy rozwijanej wybierz kod odsetek.</span><span class="sxs-lookup"><span data-stu-id="dc4de-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="dc4de-110">Jeśli nie chcesz naliczać odsetek dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="dc4de-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="dc4de-111">Karta Restrykcje tabeli pozwala na zmianę sposobu przetwarzania odsetek.</span><span class="sxs-lookup"><span data-stu-id="dc4de-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="dc4de-112">Jeśli to pole ma ustawioną wartość Tak, odsetki będą obliczane dla tego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="dc4de-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="dc4de-113">Nalicz odsetki</span><span class="sxs-lookup"><span data-stu-id="dc4de-113">Calculate interest</span></span>
1. <span data-ttu-id="dc4de-114">Wybierz kolejno opcje Kredyty i windykacja > Odsetki > Utwórz noty odsetkowe.</span><span class="sxs-lookup"><span data-stu-id="dc4de-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="dc4de-115">Należy wybrać typy transakcji, dla których będą obliczane odsetki.</span><span class="sxs-lookup"><span data-stu-id="dc4de-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="dc4de-116">Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="dc4de-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="dc4de-117">Jeśli wybrano opcję Odsetki, będziesz naliczać odsetki od odsetek.</span><span class="sxs-lookup"><span data-stu-id="dc4de-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="dc4de-118">Przed uwzględnieniem tych transakcji warto sprawdzić przepisy dotyczące obliczania odsetek od odsetek.</span><span class="sxs-lookup"><span data-stu-id="dc4de-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="dc4de-119">Odsetki będą obliczane od tego dnia do daty „Do dnia”.</span><span class="sxs-lookup"><span data-stu-id="dc4de-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="dc4de-120">Jeśli nie określisz wartości „Od dnia”, wszystkie niezaksięgowane noty odsetkowe zostaną anulowane, a odsetki zostaną obliczone ponownie od daty transakcji.</span><span class="sxs-lookup"><span data-stu-id="dc4de-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="dc4de-121">Wprowadź datę noty odsetkowej.</span><span class="sxs-lookup"><span data-stu-id="dc4de-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="dc4de-122">Istnieją trzy opcje profili księgowania:   Konto — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="dc4de-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="dc4de-123">Wybierz — Zostanie użyty profil księgowania wybrany w polu Profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="dc4de-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="dc4de-124">Transakcja — Użycie dla każdej noty odsetkowej indywidualnego profilu księgowania z transakcji, w której obliczano odsetki.</span><span class="sxs-lookup"><span data-stu-id="dc4de-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="dc4de-125">Transakcje, które nie mają przypisanego profilu księgowania, będą używać profilu księgowania określonego w formularzu Parametry modułu rozrachunków z odbiorcami w obszarze Księga i podatek.</span><span class="sxs-lookup"><span data-stu-id="dc4de-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="dc4de-126">Jeśli w polu „Użyj profilu księgowania z” zmieniono wartość na „Wybierz”, w tym miejscu wybierz profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="dc4de-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="dc4de-127">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="dc4de-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="dc4de-128">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="dc4de-128">Click Filter.</span></span>
5. <span data-ttu-id="dc4de-129">W polu Kryteria wpisz identyfikator odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="dc4de-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="dc4de-130">Na przykład wpisz „US-001”.</span><span class="sxs-lookup"><span data-stu-id="dc4de-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="dc4de-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dc4de-131">Click OK.</span></span>
7. <span data-ttu-id="dc4de-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dc4de-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="dc4de-133">Drukuj noty odsetkowe</span><span class="sxs-lookup"><span data-stu-id="dc4de-133">Print interest notes</span></span>
1. <span data-ttu-id="dc4de-134">Wybierz kolejno opcje Kredyty i windykacja > Odsetki > Przejrzyj i przetwórz noty odsetkowe.</span><span class="sxs-lookup"><span data-stu-id="dc4de-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="dc4de-135">W polu Stan wybierz opcję „Utworzono”.</span><span class="sxs-lookup"><span data-stu-id="dc4de-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="dc4de-136">W polu Wydrukowane wybierz opcję „Nie wydrukowano”.</span><span class="sxs-lookup"><span data-stu-id="dc4de-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="dc4de-137">Kliknij przycisk Drukuj.</span><span class="sxs-lookup"><span data-stu-id="dc4de-137">Click Print.</span></span>
5. <span data-ttu-id="dc4de-138">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="dc4de-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="dc4de-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dc4de-139">Click OK.</span></span>
7. <span data-ttu-id="dc4de-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dc4de-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="dc4de-141">Księgowanie noty odsetkowej</span><span class="sxs-lookup"><span data-stu-id="dc4de-141">Post the interest note</span></span>
1. <span data-ttu-id="dc4de-142">Wybierz notę odsetkową, która jest gotowa do zaksięgowania (ma stan Utworzono).</span><span class="sxs-lookup"><span data-stu-id="dc4de-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="dc4de-143">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="dc4de-143">Click Post.</span></span>
3. <span data-ttu-id="dc4de-144">Wprowadź datę księgowania noty odsetkowej.</span><span class="sxs-lookup"><span data-stu-id="dc4de-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="dc4de-145">Zaznacz opcję Tak, aby tworzyć transakcje księgi głównej dla każdej noty odsetkowej.</span><span class="sxs-lookup"><span data-stu-id="dc4de-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="dc4de-146">Jeśli nie zaznaczysz opcji Tak, odsetki ze wszystkich not odsetkowych dotyczących danego klienta zostaną skumulowane i zaksięgowane w księdze głównej jako jedna transakcja.</span><span class="sxs-lookup"><span data-stu-id="dc4de-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="dc4de-147">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="dc4de-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="dc4de-148">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dc4de-148">Click OK.</span></span>
6. <span data-ttu-id="dc4de-149">W polu Stan wybierz opcję „Zaksięgowano”.</span><span class="sxs-lookup"><span data-stu-id="dc4de-149">In the Status field, select 'Posted'.</span></span>

