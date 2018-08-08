--- 
title: "Konfigurowanie ksiąg"
description: "W tej procedurze pokazano, jak utworzyć nową księgę środków trwałych i skojarzyć ją z grupą środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: b18f52254b9073cd95bf50539a4414598a8c19cc
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-books"></a><span data-ttu-id="8b5eb-103">Konfigurowanie ksiąg</span><span class="sxs-lookup"><span data-stu-id="8b5eb-103">Set up books</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b5eb-104">W tej procedurze pokazano, jak utworzyć nową księgę środków trwałych i skojarzyć ją z grupą środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="8b5eb-105">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="8b5eb-106">Tworzenie księgi</span><span class="sxs-lookup"><span data-stu-id="8b5eb-106">Create a book</span></span>
1. <span data-ttu-id="8b5eb-107">Wybierz kolejno opcje Środki trwałe > Ustawienia > Księgi.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="8b5eb-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-108">Click New.</span></span>
3. <span data-ttu-id="8b5eb-109">W polu Księga wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="8b5eb-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="8b5eb-111">Jeśli zaznaczysz opcję Oblicz amortyzację, skojarzona księga środków trwałych będzie uwzględniana w propozycjach amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="8b5eb-112">Jeśli opcja nie jest zaznaczona, pozycje księgi środków trwałych nie będą automatycznie amortyzowane.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="8b5eb-113">W polu Oblicz amortyzację wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="8b5eb-114">Wprowadź lub wybierz wartość w polu Profil amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="8b5eb-115">Profil amortyzacji alternatywnej jest również nazywany alternatywną metodą amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="8b5eb-116">Propozycja amortyzacji zostanie przełączona na ten profil, gdy profil alternatywny wyliczy kwotę amortyzacji równą lub większą kwocie z domyślnego profilu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="8b5eb-117">Profil Amortyzacja dodatkowa będzie używany na potrzeby dodatkowej amortyzacji składnika aktywów w nadzwyczajnych okolicznościach.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="8b5eb-118">Na przykład może to służy do zarejestrowania amortyzacji powstałej w wyniku klęski żywiołowej.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="8b5eb-119">Jeśli zaznaczysz opcję Tworzenie korekt amortyzacji przy korektach podstawy, korekty amortyzacji będą tworzone automatycznie po aktualizacji wartości środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="8b5eb-120">Jeśli opcja nie jest zaznaczona, zaktualizowana wartość składnika aktywów wpłynie tylko na przyszłe obliczenia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="8b5eb-121">Zaznacz opcję Tak w polu Tworzenie korekt amortyzacji przy korektach podstawy.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="8b5eb-122">Domyślnie transakcje księgi środków trwałych są księgowane w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="8b5eb-123">Księgowania pozycji księgi w księdze głównej można wyłączyć, ustawiając w polu Księguj w księdze głównej wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="8b5eb-124">Księgi, które nie są księgowane w księdze głównej, są zazwyczaj używane na potrzeby sprawozdawczości podatkowej.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="8b5eb-125">Zapewnia to dodatkową elastyczność umożliwiającą usuwanie historycznych transakcji z księgi środków trwałych, ponieważ nie zostały one potwierdzone w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="8b5eb-126">Ustawienie Warstwa księgowania domyślnie przyjmuje wartość Bieżąca warstwa, jeśli pozycje księgi są księgowane do księgi głównej, lub Brak, jeżeli pozycje nie są księgowane do księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="8b5eb-127">Zaktualizuj warstwę księgowania, jeśli chcesz, aby transakcje tej księgi były księgowanie na innej warstwie.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="8b5eb-128">W polu Kalendarz wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="8b5eb-129">W przypadku ksiąg pochodnych transakcje są księgowane do różnych ksiąg w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="8b5eb-130">Transakcje tworzy się w księdze podstawowej, a podczas księgowania dokładne kopie transakcji są księgowane w księdze pochodnej.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="8b5eb-131">Transakcje w księdze pochodnej nie są ponownie obliczane, więc nie można ich stosować jako transakcji amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="8b5eb-132">Kojarzenie księgi z grupą środków trwałych</span><span class="sxs-lookup"><span data-stu-id="8b5eb-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="8b5eb-133">Kliknij opcję Grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="8b5eb-134">W polu Grupa środków trwałych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="8b5eb-135">W polu Okres użytkowania wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="8b5eb-136">Należy zauważyć, że okresy amortyzacji są obliczane po ustawieniu okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="8b5eb-137">Można ustawić konwencję amortyzacji zgodnie z wymogami dla celów podatkowych.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  


