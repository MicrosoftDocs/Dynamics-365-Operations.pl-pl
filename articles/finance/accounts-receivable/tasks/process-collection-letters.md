---
title: Przetwarzanie ponagleń
description: W tym temacie pokazano sposób tworzenia, drukowania i księgowania ponagleń.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179445"
---
# <a name="process-collection-letters"></a><span data-ttu-id="80d67-103">Przetwarzanie ponagleń</span><span class="sxs-lookup"><span data-stu-id="80d67-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="80d67-104">W tym temacie pokazano sposób tworzenia, drukowania i księgowania ponagleń.</span><span class="sxs-lookup"><span data-stu-id="80d67-104">This topic shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="80d67-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="80d67-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="80d67-106">Konfigurowanie kolejności ponagleń w profilu księgowania</span><span class="sxs-lookup"><span data-stu-id="80d67-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="80d67-107">Otwórz **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców**.</span><span class="sxs-lookup"><span data-stu-id="80d67-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="80d67-108">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="80d67-108">Click **Edit**.</span></span>
3. <span data-ttu-id="80d67-109">Z listy rozwijanej wybierz numer kolejny ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="80d67-110">Jeśli nie chcesz generować ponagleń dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="80d67-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="80d67-111">Rozwiń kartę **Restrykcje tabeli** pozwala na zmianę sposobu przetwarzania ponagleń.</span><span class="sxs-lookup"><span data-stu-id="80d67-111">Expand the **Table restrictions** tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="80d67-112">Jeśli to pole ma ustawioną wartość **Tak**, ponaglenia będą tworzone dla tego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="80d67-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="80d67-113">Tworzenie ponagleń</span><span class="sxs-lookup"><span data-stu-id="80d67-113">Create collection letters</span></span>
1. <span data-ttu-id="80d67-114">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kredyty i windykacja > Ponaglenie > Utwórz ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-114">Go to **Navigation pane > Modules > Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="80d67-115">Wybierz typy transakcji, dla których będą generowane ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="80d67-116">Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="80d67-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="80d67-117">W polu **Ponaglenie** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="80d67-117">In the **Collection letter** field, select an option.</span></span>
4. <span data-ttu-id="80d67-118">W polu **Data ponaglenia** wprowadź datę ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-118">In the **Collection letter date** field, enter the date of the collection letter.</span></span>
5. <span data-ttu-id="80d67-119">Jeśli w polu **Użyj profilu księgowania z** zmieniono wartość na **Wybierz**, wybierz profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="80d67-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="80d67-120">Dostępne są dwa profile księgowania:</span><span class="sxs-lookup"><span data-stu-id="80d67-120">There are two posting profile options:</span></span>   

   - <span data-ttu-id="80d67-121">**Konto** — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="80d67-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="80d67-122">**Wybierz** — Zostanie użyty profil księgowania wybrany w polu **Profil księgowania**.</span><span class="sxs-lookup"><span data-stu-id="80d67-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  

6. <span data-ttu-id="80d67-123">Rozwiń sekcję **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-123">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="80d67-124">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="80d67-124">Select **Filter**.</span></span>
8. <span data-ttu-id="80d67-125">W polu **Kryteria** wpisz identyfikator odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="80d67-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="80d67-126">Na przykład wpisz „US-001”.</span><span class="sxs-lookup"><span data-stu-id="80d67-126">For example, enter 'US-001'.</span></span>
9. <span data-ttu-id="80d67-127">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="80d67-127">Select **OK**.</span></span>
10. <span data-ttu-id="80d67-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="80d67-128">Select **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="80d67-129">Drukowanie ponagleń</span><span class="sxs-lookup"><span data-stu-id="80d67-129">Print collection letters</span></span>
1. <span data-ttu-id="80d67-130">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-130">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="80d67-131">W polu **Stan** wybierz opcję **Utworzono**.</span><span class="sxs-lookup"><span data-stu-id="80d67-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="80d67-132">W polu **Wydrukowane** wybierz opcję **Nie wydrukowano**.</span><span class="sxs-lookup"><span data-stu-id="80d67-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="80d67-133">Wybierz **Drukuj**.</span><span class="sxs-lookup"><span data-stu-id="80d67-133">Select **Print**.</span></span>
5. <span data-ttu-id="80d67-134">Wybierz **Tekst ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-134">Select **Collection letter note**.</span></span>
6. <span data-ttu-id="80d67-135">W sekcji **Parametry** wprowadź datę graniczną księgowania.</span><span class="sxs-lookup"><span data-stu-id="80d67-135">In the **Parameters** section, enter the cutoff date for postings.</span></span>
7. <span data-ttu-id="80d67-136">Rozwiń sekcję **Rekordy do uwzględnienia** uwzględnić, a następnie wprowadź szczegóły noty ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-136">Expand the **Records to include** section and enter the details of the Collection letter note.</span></span>
8. <span data-ttu-id="80d67-137">Wybier **OK**, aby wydrukować ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="80d67-137">Select **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="80d67-138">Księgowanie ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-138">Post the collection letter.</span></span>

    1. <span data-ttu-id="80d67-139">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="80d67-139">Select **Post**.</span></span>
    1. <span data-ttu-id="80d67-140">Wprowadź datę księgowania ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-140">Enter the posting date for the collection letter.</span></span>
    1. <span data-ttu-id="80d67-141">Rozwiń sekcję **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-141">Expand the **Records to include** section.</span></span>
    1. <span data-ttu-id="80d67-142">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="80d67-142">Select **OK**.</span></span>
    1. <span data-ttu-id="80d67-143">W polu **Stan** wybierz opcję **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="80d67-143">In the **Status** field, select **Posted**.</span></span>
    1. <span data-ttu-id="80d67-144">W polu **Wydrukowane** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="80d67-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="80d67-145">Kontrolowanie arkuszy ponagleń na poziomie odbiorcy</span><span class="sxs-lookup"><span data-stu-id="80d67-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="80d67-146">Można też skonfigurować ponaglenia na poziomie odbiorcy, aby kod ponaglenia dla każdej transakcji był śledzony, ale przetwarzanie ponaglenia opierało się na jednym poziomie ponaglenia zapisanego dla danego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="80d67-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="80d67-147">Pojedyncze ponaglenie będzie zawierało wszystkie transakcje, które są zaległe dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="80d67-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="80d67-148">Ponieważ liczba dni prolongaty jest teraz śledzona na poziomie odbiorcy, następne ponaglenie nie zostanie wysłane aż do upłynięcia dni prolongaty dla następnego ponaglenia w sekwencji, nawet jeśli transakcje staną się zaległe od momentu wysłania ostatniego ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="80d67-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="80d67-149">Ta opcja zmniejsza liczbę ponagleń wysyłanych do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="80d67-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="80d67-150">Konfigurowanie odbiorcy do kontrolowania arkuszy ponagleń na poziomie odbiorcy</span><span class="sxs-lookup"><span data-stu-id="80d67-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="80d67-151">Przejdź do **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami** i wybierz kartę **Windykacje**.</span><span class="sxs-lookup"><span data-stu-id="80d67-151">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and select the **Collections** tab.</span></span> 
2.  <span data-ttu-id="80d67-152">Zmień wartość **Utwórz ponaglenie dla** na **Obiorcy**.</span><span class="sxs-lookup"><span data-stu-id="80d67-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="80d67-153">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-153">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="80d67-154">Tylko jedno ponaglenie zostanie wygenerowane dla odbiorcy ze wszystkimi zaległymi transakcjami.</span><span class="sxs-lookup"><span data-stu-id="80d67-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="80d67-155">Ignorowanie płatności i not kredytowych przy obliczaniu kodu ponaglenia</span><span class="sxs-lookup"><span data-stu-id="80d67-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="80d67-156">Jeśli uwzględnisz płatności i noty kredytowe w transakcjach umieszczanych w ponagleniach, możesz mieć płatności lub noty kredytowe, które będą wywoływały ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="80d67-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="80d67-157">Możesz kontrolować sposób kontrolowania kodu ponaglenia przez płatności i noty kredytowe, zmieniając wartość parametru **Ignoruj płatności i noty kredytowe przy obliczaniu kodu ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="80d67-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="80d67-158">Aby zignorować płatności i noty kredytowe przy obliczaniu kodu ponaglenia, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="80d67-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>

1. <span data-ttu-id="80d67-159">Przejdź do **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami** i kliknij kartę **Windykacje**.</span><span class="sxs-lookup"><span data-stu-id="80d67-159">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="80d67-160">Zmień wartość opcji **Ignoruj płatności i noty kredytowe przy obliczaniu kodu ponaglenia** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="80d67-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
