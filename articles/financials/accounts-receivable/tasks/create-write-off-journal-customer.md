--- 
title: "Tworzenie arkusza odpisów dla odbiorcy"
description: "W tym przewodniku po zadaniach zostanie pokazany sposób konfigurowania parametrów odpisów i następnie transakcji odpisu ze stron Windykacja, Otwarte faktury odbiorcy i Odbiorca."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c90ff4abd343936612866b07577062fe1814085b
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="2dfb3-103">Tworzenie arkusza odpisów dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="2dfb3-103">Create a write-off journal for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2dfb3-104">W tym przewodniku po zadaniach zostanie pokazany sposób konfigurowania parametrów odpisów i następnie transakcji odpisu ze stron Windykacja, Otwarte faktury odbiorcy i Odbiorca.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="2dfb3-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="2dfb3-106">Konfigurowanie parametrów odpisów</span><span class="sxs-lookup"><span data-stu-id="2dfb3-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="2dfb3-107">Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-107">Go to Credit and collections > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="2dfb3-108">Kliknij kartę Windykacja.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-108">Click the Collections tab.</span></span>
3. <span data-ttu-id="2dfb3-109">Rozwiń lub zwiń sekcję Odpisz.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-109">Expand or collapse the Write-off section.</span></span>
    * <span data-ttu-id="2dfb3-110">Arkusz odpisów jest arkuszem finansowym, który będzie zawierał transakcje odpisu utworzone przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-110">The Write-off journal is the general journal that will hold the write-off transactions that you create.</span></span>  
    * <span data-ttu-id="2dfb3-111">Do każdego odpisu można dołączyć kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="2dfb3-112">To domyślne ustawienie można zastąpić podczas dokonywania odpisu.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-112">You can override this default at the time of the write-off.</span></span>  
    * <span data-ttu-id="2dfb3-113">Ustaw wartość Tak, aby w odpisie oddzielić podatek od oryginalnej transakcji.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-113">Set this to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="2dfb3-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-114">Close the page.</span></span>
5. <span data-ttu-id="2dfb3-115">Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-115">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
    * <span data-ttu-id="2dfb3-116">Konto odpisu będzie używane jako konto wydatków lub rezerwacji korekt w arkuszu finansowym</span><span class="sxs-lookup"><span data-stu-id="2dfb3-116">The write-off account will be used as the expense account or reserve adjustment in the general journal</span></span>   
6. <span data-ttu-id="2dfb3-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="2dfb3-118">Odpisywanie salda odbiorcy ze strony wiekowanych sald</span><span class="sxs-lookup"><span data-stu-id="2dfb3-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="2dfb3-119">Wybierz kolejno opcje Kredyty i windykacja > Windykacja > Wiekowane salda.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-119">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="2dfb3-120">Zaznacz wiersz odbiorcy, dla którego ma zostać dokonany odpis.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="2dfb3-121">Na przykład zaznacz wiersz z firmą Birch Company.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="2dfb3-122">W okienku akcji kliknij pozycję Windykacja.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-122">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="2dfb3-123">Kliknij opcję Odpisz.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-123">Click Write off.</span></span>
5. <span data-ttu-id="2dfb3-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-124">Click OK.</span></span>
6. <span data-ttu-id="2dfb3-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-125">Close the page.</span></span>
7. <span data-ttu-id="2dfb3-126">Wybierz kolejno opcje Księga główna > Wpisy w arkuszu > Arkusze finansowe.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-126">Go to General ledger > Journal entries > General journals.</span></span>
8. <span data-ttu-id="2dfb3-127">Wybierz numer partii arkuszy z arkuszem, który zawiera odpis.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-127">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="2dfb3-128">Jest tworzony jeden wiersz w celu wystornowania salda odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="2dfb3-129">Jeden lub więcej wierszy jest tworzonych w celu zaksięgowania odpisu na koncie odpisów.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="2dfb3-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-130">Close the page.</span></span>
10. <span data-ttu-id="2dfb3-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="2dfb3-132">Odpisywanie transakcji z formularza windykacji</span><span class="sxs-lookup"><span data-stu-id="2dfb3-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="2dfb3-133">Wybierz kolejno opcje Kredyty i windykacja > Windykacja > Wiekowane salda.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-133">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="2dfb3-134">Zaznacz nazwę odbiorcy mającego transakcje, które chcesz odpisać.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="2dfb3-135">Na przykład wybierz Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="2dfb3-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="2dfb3-136">Zaznacz wiersz pierwszej transakcji.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="2dfb3-137">Zaznacz wiersz drugiej transakcji.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="2dfb3-138">Kliknij opcję Odpisz.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-138">Click Write off.</span></span>
6. <span data-ttu-id="2dfb3-139">W polu Komentarz dotyczący przyczyny wpisz „Prawdopodobnie nieściągalne długi”.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-139">In the Reason comment field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="2dfb3-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-140">Click OK.</span></span>
8. <span data-ttu-id="2dfb3-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-141">Close the page.</span></span>
9. <span data-ttu-id="2dfb3-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-142">Close the page.</span></span>
10. <span data-ttu-id="2dfb3-143">Wybierz kolejno opcje Księga główna > Wpisy w arkuszu > Arkusze finansowe.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-143">Go to General ledger > Journal entries > General journals.</span></span>
11. <span data-ttu-id="2dfb3-144">Wybierz numer partii arkuszy z arkuszem, który zawiera odpis.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-144">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="2dfb3-145">Jest tworzony jeden wiersz w celu wystornowania salda odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="2dfb3-146">Jeden lub więcej wierszy jest tworzonych w celu zaksięgowania odpisu na koncie odpisów.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="2dfb3-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-147">Close the page.</span></span>
13. <span data-ttu-id="2dfb3-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="2dfb3-149">Odpisywanie faktury ze strony Otwarte faktury odbiorców</span><span class="sxs-lookup"><span data-stu-id="2dfb3-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="2dfb3-150">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Otwarte faktury odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-150">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="2dfb3-151">Zaznacz wiersz faktury.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-151">Mark the line for an invoice.</span></span> <span data-ttu-id="2dfb3-152">Na przykład zaznacz wiersz faktury CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="2dfb3-153">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-153">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="2dfb3-154">Kliknij opcję Odpisz.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-154">Click Write off.</span></span>
5. <span data-ttu-id="2dfb3-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-155">Click OK.</span></span>
6. <span data-ttu-id="2dfb3-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="2dfb3-157">Odpisywanie salda odbiorcy ze strony odbiorcy</span><span class="sxs-lookup"><span data-stu-id="2dfb3-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="2dfb3-158">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-158">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="2dfb3-159">Umożliwia wybór konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-159">Select a customer account.</span></span> <span data-ttu-id="2dfb3-160">Wybierz na przykład US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="2dfb3-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="2dfb3-161">W okienku akcji kliknij pozycję Windykacja.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-161">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="2dfb3-162">Kliknij opcję Odpisz.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-162">Click Write off.</span></span>
5. <span data-ttu-id="2dfb3-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-163">Click OK.</span></span>
6. <span data-ttu-id="2dfb3-164">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-164">Close the page.</span></span>


