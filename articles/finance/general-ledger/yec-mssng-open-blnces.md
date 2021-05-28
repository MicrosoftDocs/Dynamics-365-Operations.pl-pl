---
title: Brakujące salda otwarcia dla zamknięcia na koniec roku
description: W tym temacie wyjaśniono, dlaczego podczas zamykania roku może brakować sald otwarcia, a także opisano sposób ich odtworzenia w przypadku ich braku.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028581"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="f3015-103">Brakujące salda otwarcia dla zamknięcia na koniec roku</span><span class="sxs-lookup"><span data-stu-id="f3015-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3015-104">W tym temacie wyjaśniono, dlaczego podczas zamykania roku może brakować sald otwarcia, a także opisano sposób ich odtworzenia w przypadku ich braku.</span><span class="sxs-lookup"><span data-stu-id="f3015-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="f3015-105">Objaw</span><span class="sxs-lookup"><span data-stu-id="f3015-105">Symptom</span></span>

<span data-ttu-id="f3015-106">Dlaczego po uruchomieniu zamknięcia na koniec roku księgi głównej nie są dostępne salda początkowe?</span><span class="sxs-lookup"><span data-stu-id="f3015-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="f3015-107">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="f3015-107">Resolution</span></span>

<span data-ttu-id="f3015-108">Oto kilka czynności do sprawdzenia w przypadku, gdy zamknięto rok w księdze głównej, a następnie wygenerowano bilans próbny, który nie wyświetlił sald otwarcia dla następnego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="f3015-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="f3015-109">Jeśli dla pola **Cofnij poprzednie zamknięcie** wybrano opcję **Tak**, poprzednie zamknięcie na koniec roku dla tego samego roku obrachunkowego zostanie cofnięte.</span><span class="sxs-lookup"><span data-stu-id="f3015-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="f3015-110">W przypadku uruchomienia procesu cofnięcia zamknięcia roku wszystkie wpisy zarówno salda zamknięcia, jak i salda otwarcia zostaną usunięte, tak jakby zamknięcie na koniec roku nigdy nie zostało przeprowadzone.</span><span class="sxs-lookup"><span data-stu-id="f3015-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="f3015-111">Załączniki także zostaną usunięte.</span><span class="sxs-lookup"><span data-stu-id="f3015-111">The vouchers are also deleted.</span></span> <span data-ttu-id="f3015-112">Proces zamknięcia na koniec roku nie zostanie ponownie uruchomiony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f3015-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="f3015-113">Konieczne będzie ponowne rozpoczęcie procesu, przy czym tym razem należy dla opcji **Cofnij poprzednie zamknięcie** zmienić ustawienie na **Nie**.</span><span class="sxs-lookup"><span data-stu-id="f3015-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="f3015-114">Ten scenariusz został opisany w zawierającym często zadawane pytania temacie poświęconym kwestii zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="f3015-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="f3015-115">Aby uzyskać więcej informacji, zobacz [Działania na koniec roku — często zadawane pytania](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="f3015-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="f3015-116">Objaw</span><span class="sxs-lookup"><span data-stu-id="f3015-116">Symptom</span></span>

<span data-ttu-id="f3015-117">Uruchomiono zamknięcie na koniec roku z opcją **Cofnij poprzednie zamknięcie** ustawioną na **Nie**, a mimo to nie są dostępne salda otwarcia dla danego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="f3015-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="f3015-118">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="f3015-118">Resolution</span></span>

<span data-ttu-id="f3015-119">Najpierw sprawdź stan zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="f3015-119">First check the status of the batch job.</span></span> <span data-ttu-id="f3015-120">Zamknięcie roku obejmuje wiele oddzielnych zadań, ale najważniejszym krokiem jest zadanie wsadowe z opisem **Krok 5.0.0**.</span><span class="sxs-lookup"><span data-stu-id="f3015-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="f3015-121">W tym kroku ma miejsce zaksięgowanie w księdze głównej transakcji otwarcia oraz, opcjonalnie, transakcji zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="f3015-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="f3015-122">[![Lista historii zadań przetwarzania wsadowego](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="f3015-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="f3015-123">Jeśli ten krok zakończył się pomyślnie, ale salda otwarcia nie są widoczne na stronie **Zapytanie o bilans próbny** (**Księga główna > Zapytania i raporty > Bilans próbny**), przejrzyj wyniki zadania wsadowego zamknięcia na koniec roku, aby sprawdzić, czy krok Odbuduj salda został pomyślnie ukończony.</span><span class="sxs-lookup"><span data-stu-id="f3015-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="f3015-124">[![Wyniki zadania wsadowego zamknięcia na koniec roku](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="f3015-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="f3015-125">Jeśli ten krok nie powiódł się z dowolnej przyczyny, transakcje otwarcia (i opcjonalnie zamknięcia) prawdopodobnie zostały pomyślnie zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="f3015-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="f3015-126">Za pomocą strony **Zapytanie o transakcje na załączniku** można sprawdzić, czy transakcje księgi głównej zostały pomyślnie zaksięgowane. W tym celu należy określić numer załącznika i datę z okna dialogowego zamknięcia na koniec roku przeprowadzonego przez użytkownika (**Księga główna > Zapytania i raporty > Transakcje na załączniku**).</span><span class="sxs-lookup"><span data-stu-id="f3015-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="f3015-127">[![Zapytanie o transakcje na załączniku](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="f3015-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="f3015-128">Jeśli załączniki otwarcia (i opcjonalne zamknięcia) są obecne, nie musisz ponownie uruchamiać zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="f3015-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="f3015-129">Zamiast tego zapoznaj się z następną sekcją, aby uzyskać informacje o właściwym sposobie dalszego postępowania.</span><span class="sxs-lookup"><span data-stu-id="f3015-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="f3015-130">Objaw</span><span class="sxs-lookup"><span data-stu-id="f3015-130">Symptom</span></span>

<span data-ttu-id="f3015-131">Krok „Odbuduj salda” w trakcie zamknięcia na koniec roku nie powiódł się. Czy należy ponownie uruchomić cały proces zamknięcia na koniec roku?</span><span class="sxs-lookup"><span data-stu-id="f3015-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="f3015-132">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="f3015-132">Resolution</span></span>

<span data-ttu-id="f3015-133">W ramach kroku Odbuduj salda następuje aktualizacja sald księgi głównej, które są używane podczas generowania zapytania o bilans próbny.</span><span class="sxs-lookup"><span data-stu-id="f3015-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="f3015-134">Jest to ostatni etap procesu zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="f3015-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="f3015-135">Jeśli tylko ten krok zakończy się niepowodzeniem, transakcje księgi głównej zostały pomyślnie zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="f3015-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="f3015-136">Ponowne uruchomienie zamknięcia na koniec roku nie jest konieczne.</span><span class="sxs-lookup"><span data-stu-id="f3015-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="f3015-137">Proces odbudowy sald można uruchomić ręcznie za pomocą strony **Zestawy wymiarów finansowych** (**Księga główna > Plan kont > Wymiary > Zestawy wymiarów finansowych**).</span><span class="sxs-lookup"><span data-stu-id="f3015-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="f3015-138">[![Przycisk Odbuduj salda na stronie Zestawy wymiarów finansowych](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="f3015-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="f3015-139">Jeśli przetworzenie tego kroku zajmuje dużo czasu, zalecane jest przejrzenie najlepszych rozwiązań w odniesieniu do zestawów wymiarów finansowych zgodnie z opisem w temacie [Najlepsze rozwiązania dotyczące aktualizowania zestawów wymiarów finansowych](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span><span class="sxs-lookup"><span data-stu-id="f3015-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 

