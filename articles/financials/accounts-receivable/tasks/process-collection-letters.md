--- 
title: "Przetwarzanie ponagleń"
description: "W tej procedurze pokazano sposób tworzenia, drukowania i księgowania ponagleń."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="process-collection-letters"></a><span data-ttu-id="61db2-103">Przetwarzanie ponagleń</span><span class="sxs-lookup"><span data-stu-id="61db2-103">Process collection letters</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="61db2-104">W tej procedurze pokazano sposób tworzenia, drukowania i księgowania ponagleń.</span><span class="sxs-lookup"><span data-stu-id="61db2-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="61db2-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="61db2-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="61db2-106">Konfigurowanie kolejności ponagleń w profilu księgowania</span><span class="sxs-lookup"><span data-stu-id="61db2-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="61db2-107">Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców.</span><span class="sxs-lookup"><span data-stu-id="61db2-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="61db2-108">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="61db2-108">Click Edit.</span></span>
    * <span data-ttu-id="61db2-109">Z listy rozwijanej wybierz numer kolejny ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="61db2-110">Jeśli nie chcesz generować ponagleń dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="61db2-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="61db2-111">Karta Restrykcje tabeli pozwala na zmianę sposobu przetwarzania ponagleń.</span><span class="sxs-lookup"><span data-stu-id="61db2-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="61db2-112">Jeśli to pole ma ustawioną wartość Tak, ponaglenia będą tworzone dla tego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="61db2-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="61db2-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61db2-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="61db2-114">Tworzenie ponagleń</span><span class="sxs-lookup"><span data-stu-id="61db2-114">Create collection letters</span></span>
1. <span data-ttu-id="61db2-115">Wybierz kolejno opcje Kredyty i windykacja > Ponaglenie > Utwórz ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="61db2-116">Należy wybrać typy transakcji, dla których będą generowane ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="61db2-117">Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="61db2-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="61db2-118">W polu Ponaglenie wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="61db2-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="61db2-119">Wprowadź datę ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="61db2-120">Istnieją dwie opcje profili księgowania:   Konto — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="61db2-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="61db2-121">Wybierz — Zostanie użyty profil księgowania wybrany w polu Profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="61db2-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="61db2-122">Jeśli w polu „Użyj profilu księgowania z” zmieniono wartość na „Wybierz”, wybierz profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="61db2-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="61db2-123">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="61db2-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="61db2-124">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="61db2-124">Click Filter.</span></span>
6. <span data-ttu-id="61db2-125">W polu Kryteria wprowadź identyfikator odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="61db2-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="61db2-126">Na przykład wpisz „US-001”.</span><span class="sxs-lookup"><span data-stu-id="61db2-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="61db2-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="61db2-127">Click OK.</span></span>
8. <span data-ttu-id="61db2-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="61db2-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="61db2-129">Drukowanie ponagleń</span><span class="sxs-lookup"><span data-stu-id="61db2-129">Print collection letters</span></span>
1. <span data-ttu-id="61db2-130">Wybierz kolejno opcje Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="61db2-131">W polu Stan wybierz opcję „Utworzono”.</span><span class="sxs-lookup"><span data-stu-id="61db2-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="61db2-132">W polu Wydrukowane wybierz opcję „Nie wydrukowano”.</span><span class="sxs-lookup"><span data-stu-id="61db2-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="61db2-133">Kliknij przycisk Drukuj.</span><span class="sxs-lookup"><span data-stu-id="61db2-133">Click Print.</span></span>
5. <span data-ttu-id="61db2-134">Kliknij opcję Tekst ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="61db2-135">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="61db2-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="61db2-136">Wprowadź graniczną datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="61db2-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="61db2-137">Kliknij przycisk OK, aby wydrukować ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="61db2-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="61db2-138">Księgowanie ponaglenia</span><span class="sxs-lookup"><span data-stu-id="61db2-138">Post the collection letter</span></span>
1. <span data-ttu-id="61db2-139">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="61db2-139">Click Post.</span></span>
2. <span data-ttu-id="61db2-140">Wprowadź datę księgowania ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="61db2-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="61db2-141">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="61db2-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="61db2-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="61db2-142">Click OK.</span></span>
5. <span data-ttu-id="61db2-143">W polu Stan wybierz opcję „Zaksięgowano”.</span><span class="sxs-lookup"><span data-stu-id="61db2-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="61db2-144">W polu Wydrukowane wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="61db2-144">In the Printed field, select an option.</span></span>


