---
title: Przetwarzanie odsetek
description: W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad30984f55017ee275af15ddb4f1a46c6a50db69
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992946"
---
# <a name="process-interest"></a><span data-ttu-id="e2aff-103">Przetwarzanie odsetek</span><span class="sxs-lookup"><span data-stu-id="e2aff-103">Process interest</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2aff-104">W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="e2aff-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="e2aff-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="e2aff-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="e2aff-106">Konfigurowanie odsetek w profilu księgowania</span><span class="sxs-lookup"><span data-stu-id="e2aff-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="e2aff-107">W **Okienku nawigacji** przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="e2aff-108">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-108">Click **Edit**.</span></span>
3. <span data-ttu-id="e2aff-109">W **skróconej karcie Ustawień** w polu **Kod odsetek** wybierz kod odsetek z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="e2aff-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="e2aff-110">Jeśli nie chcesz naliczać odsetek dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="e2aff-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="e2aff-111">Karta skrócona **Restrykcje tabeli** pozwala na zmianę sposobu przetwarzania odsetek.</span><span class="sxs-lookup"><span data-stu-id="e2aff-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="e2aff-112">Jeśli to pole ma ustawioną wartość Tak, odsetki będą obliczane dla tego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="e2aff-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="e2aff-113">Nalicz odsetki</span><span class="sxs-lookup"><span data-stu-id="e2aff-113">Calculate interest</span></span>
1. <span data-ttu-id="e2aff-114">W **Okienku nawigacji** przejdź do **Moduły > Kredyty i windykacja > Odsetki > Utwórz noty odsetkowe**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="e2aff-115">Należy wybrać typy transakcji, dla których będą obliczane odsetki.</span><span class="sxs-lookup"><span data-stu-id="e2aff-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="e2aff-116">Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="e2aff-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="e2aff-117">Jeśli opcję **Odsetki** ustawiono na „Tak”, obliczysz odsetki od odsetek.</span><span class="sxs-lookup"><span data-stu-id="e2aff-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="e2aff-118">Przed uwzględnieniem tych transakcji warto sprawdzić przepisy dotyczące obliczania odsetek od odsetek.</span><span class="sxs-lookup"><span data-stu-id="e2aff-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="e2aff-119">W polu **Od dnia** wprowadź datę, od kiedy będą naliczane odsetki.</span><span class="sxs-lookup"><span data-stu-id="e2aff-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="e2aff-120">Jeśli nie określisz wartości **Od dnia**, wszystkie niezaksięgowane noty odsetkowe zostaną anulowane, a odsetki zostaną obliczone ponownie od daty transakcji.</span><span class="sxs-lookup"><span data-stu-id="e2aff-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="e2aff-121">W polu **Do dnia** wprowadź datę, do kiedy będą naliczane odsetki.</span><span class="sxs-lookup"><span data-stu-id="e2aff-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="e2aff-122">W polu **Użyj profilu księgowania z** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="e2aff-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="e2aff-123">Dostępne są trzy opcje profili księgowania:</span><span class="sxs-lookup"><span data-stu-id="e2aff-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="e2aff-124">Konto — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e2aff-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="e2aff-125">Wybierz — Zostanie użyty profil księgowania wybrany w polu Profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="e2aff-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="e2aff-126">Transakcja — Użycie dla każdej noty odsetkowej indywidualnego profilu księgowania z transakcji, w której obliczano odsetki.</span><span class="sxs-lookup"><span data-stu-id="e2aff-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="e2aff-127">Transakcje, które nie mają przypisanego profilu księgowania, będą używać profilu księgowania określonego w formularzu Parametry modułu rozrachunków z odbiorcami w obszarze Księga i podatek.</span><span class="sxs-lookup"><span data-stu-id="e2aff-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="e2aff-128">Rozwiń kartę skróconą **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="e2aff-129">Kliknij przycisk **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-129">Click **Filter**.</span></span>
9. <span data-ttu-id="e2aff-130">W polu **Kryteria** wpisz identyfikator odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e2aff-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="e2aff-131">Na przykład wpisz „US-001”.</span><span class="sxs-lookup"><span data-stu-id="e2aff-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="e2aff-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-132">Click **OK**.</span></span>
7. <span data-ttu-id="e2aff-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="e2aff-134">Drukuj noty odsetkowe</span><span class="sxs-lookup"><span data-stu-id="e2aff-134">Print interest notes</span></span>
1. <span data-ttu-id="e2aff-135">W **Okienku nawigacji** przejdź do **Moduły > Kredyty i windykacja > Odsetki > Przejrzyj i przetwórz noty odsetkowe**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="e2aff-136">W polu **Stan** wybierz opcję „Utworzono”.</span><span class="sxs-lookup"><span data-stu-id="e2aff-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="e2aff-137">W polu **Wydrukowane** wybierz opcję „Nie wydrukowano”.</span><span class="sxs-lookup"><span data-stu-id="e2aff-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="e2aff-138">Kliknij przycisk **Drukuj**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-138">Click **Print**.</span></span>
5. <span data-ttu-id="e2aff-139">Rozwiń kartę skróconą **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="e2aff-140">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-140">Click **OK**.</span></span>
7. <span data-ttu-id="e2aff-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e2aff-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="e2aff-142">Księgowanie noty odsetkowej</span><span class="sxs-lookup"><span data-stu-id="e2aff-142">Post the interest note</span></span>
1. <span data-ttu-id="e2aff-143">Wybierz notę odsetkową, która jest gotowa do zaksięgowania (ma stan Utworzono).</span><span class="sxs-lookup"><span data-stu-id="e2aff-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="e2aff-144">Kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-144">Click **Post**.</span></span>
3. <span data-ttu-id="e2aff-145">Wprowadź datę księgowania noty odsetkowej.</span><span class="sxs-lookup"><span data-stu-id="e2aff-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="e2aff-146">Zaznacz opcję Tak, aby tworzyć transakcje księgi głównej dla każdej noty odsetkowej.</span><span class="sxs-lookup"><span data-stu-id="e2aff-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="e2aff-147">Jeśli nie zaznaczysz opcji Tak, odsetki ze wszystkich not odsetkowych dotyczących danego klienta zostaną skumulowane i zaksięgowane w księdze głównej jako jedna transakcja.</span><span class="sxs-lookup"><span data-stu-id="e2aff-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="e2aff-148">Rozwiń kartę skróconą **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="e2aff-149">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2aff-149">Click **OK**.</span></span>
6. <span data-ttu-id="e2aff-150">W polu **Stan** wybierz opcję „Zaksięgowano”.</span><span class="sxs-lookup"><span data-stu-id="e2aff-150">In the **Status** field, select 'Posted'.</span></span>

