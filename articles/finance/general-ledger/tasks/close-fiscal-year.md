---
title: Zamykanie roku obrachunkowego
description: Ta procedura prowadzi przez proces zamknięcia roku, który przenosi salda do nowego roku obrachunkowego.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6299325bb8d77cad3977ae3c20790122574b47f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235820"
---
# <a name="close-the-fiscal-year"></a><span data-ttu-id="b1b29-103">Zamykanie roku obrachunkowego</span><span class="sxs-lookup"><span data-stu-id="b1b29-103">Close the fiscal year</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b1b29-104">Ta procedura prowadzi przez proces zamknięcia roku, który przenosi salda do nowego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="b1b29-104">This procedure steps through the year end close process that transfers balances to a new fiscal year.</span></span>


## <a name="validate-year-end-close-parameters"></a><span data-ttu-id="b1b29-105">Sprawdzanie poprawności parametrów zamknięcia na koniec roku</span><span class="sxs-lookup"><span data-stu-id="b1b29-105">Validate year-end close parameters</span></span>
1. <span data-ttu-id="b1b29-106">Przejdź do **Okienko nawigacji > Moduły > Księga główna > Ustawienia księgi > Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-106">Go to **Navigation pane > Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="b1b29-107">Rozwiń sekcję **Zamknięcie roku obrachunkowego**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-107">Expand the **Fiscal year close** section.</span></span>
3. <span data-ttu-id="b1b29-108">Zaznacz wartość Tak lub Nie dla opcji **Usuwanie transakcji zamknięcia roku podczas przenoszenia**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-108">Select 'Yes' or 'No' for the **Delete close-of-year transactions during transfer** option.</span></span>
    
    <span data-ttu-id="b1b29-109">To ustawienie jest ważne, jeśli rok obrachunkowy został już zamknięty, a jest ponownie wykonywane zamknięcie na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-109">If the fiscal year has already been closed and the year-end close is being run again, this setting is important.</span></span> <span data-ttu-id="b1b29-110">Jeśli zostanie ustawione na Tak, załącznik poprzedniego zamknięcia na koniec roku zostanie usunięty, a zostanie utworzony nowy załącznik dla sald początkowych wszystkich kont.</span><span class="sxs-lookup"><span data-stu-id="b1b29-110">If set to Yes, the voucher for the previous year-end close will be deleted, and a new voucher will be created for all accounts beginning balances.</span></span> <span data-ttu-id="b1b29-111">Jeśli ustawisz wartość Nie, poprzedni załącznik pozostanie, a nowy załącznik zostanie utworzony tylko dla zapisów korygujących, które zostały zaksięgowane po ostatnim zamknięciu na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-111">If set to No, the previous voucher will remain and a new voucher will only be created for adjusting entries that were posted after the last year-end close.</span></span>

4. <span data-ttu-id="b1b29-112">Zaznacz wartość Tak lub Nie dla opcji **Tworzenie transakcji zamknięcia w trakcie przeniesienia**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-112">Select 'Yes' or 'No' for the **Create closing transactions during transfer** option.</span></span>

    <span data-ttu-id="b1b29-113">Jeśli ustawisz wartość Tak, tworzone są dwie transakcje.</span><span class="sxs-lookup"><span data-stu-id="b1b29-113">If set to Yes, two transactions are created.</span></span> <span data-ttu-id="b1b29-114">Jeden załącznik jest tworzony w zamykanym roku obrachunkowym w celu wyzerowania sald kont księgowych rachunku zysków i strat, a drugi załącznik jest tworzony w następnym roku obrachunkowym dla sald początkowych.</span><span class="sxs-lookup"><span data-stu-id="b1b29-114">One voucher is created in the fiscal year being closed to bring the balances of the P&L ledger accounts down to zero and a second voucher is created in the next fiscal year for the beginning balances.</span></span> <span data-ttu-id="b1b29-115">Jeśli ustawisz wartość Nie, jest tworzony jeden załącznik w następnym roku obrachunkowym dla sald początkowych.</span><span class="sxs-lookup"><span data-stu-id="b1b29-115">If set to No, a single voucher is created in the next fiscal year for the beginning balances.</span></span>  

5. <span data-ttu-id="b1b29-116">Zaznacz wartość Tak lub Nie dla opcji **Ustaw stan roku obrachunkowego na trwale zamknięty**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-116">Select 'Yes' or 'No' for the **Set fiscal year status to permanently closed** option.</span></span>

    <span data-ttu-id="b1b29-117">Jeśli ustawisz wartość Tak, stan roku obrachunkowego zostanie ustawiony na Trwale zamknięty.</span><span class="sxs-lookup"><span data-stu-id="b1b29-117">If set to Yes, the fiscal year status will be set to Permanently closed.</span></span>  <span data-ttu-id="b1b29-118">Ponieważ trwale zamkniętego roku nie można otworzyć ponownie, byłoby najlepszym rozwiązaniem, aby ustawić tę opcję na wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="b1b29-118">Because a permanently closed year cannot be reopened, it would be a best practice to set this option to No.</span></span>  

6. <span data-ttu-id="b1b29-119">Zaznacz wartość Tak lub Nie dla opcji mówiącej o tym, czy **numer załącznika musi być wypełniony podczas zamknięcia na koniec roku**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-119">Select 'Yes' or 'No' for the **Voucher number must be filled in during the year end close** option.</span></span>

    <span data-ttu-id="b1b29-120">Jeśli ustawisz wartość Tak, numer załącznika należy wprowadzić ręcznie podczas procesu zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-120">If set to Yes, a voucher number must be manually entered during the year end close process.</span></span> <span data-ttu-id="b1b29-121">Funkcja numeracji nie jest używana do generowania tego numeru załącznika.</span><span class="sxs-lookup"><span data-stu-id="b1b29-121">A number sequence is not used to generate this voucher number.</span></span> <span data-ttu-id="b1b29-122">Najlepszym rozwiązaniem jest ustawić wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="b1b29-122">It's a best practice to set this to Yes.</span></span>  

7. <span data-ttu-id="b1b29-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b1b29-123">Close the page.</span></span>
8. <span data-ttu-id="b1b29-124">Wybierz kolejno opcje **Księga główna > Zamykanie okresu > Zamknięcie na koniec roku**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-124">Go to **General ledger > Period close > Year end close**.</span></span>
9. <span data-ttu-id="b1b29-125">Kliknij przycisk **Nowy**, aby utworzyć szablon zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-125">Click **New** to create a year-end close template.</span></span>

    <span data-ttu-id="b1b29-126">Szablon można utworzyć dla grupy firm, dla których ma zostać wykonane zamknięcie na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-126">A template can be created for a group of legal entities for which to run the year-end close.</span></span> <span data-ttu-id="b1b29-127">Tego szablonu można używać co rok.</span><span class="sxs-lookup"><span data-stu-id="b1b29-127">This template can be reused year after year.</span></span>  

10. <span data-ttu-id="b1b29-128">W polu **Nazwa grupy** wprowadź nazwę szablonu zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-128">In the **Group name** field, enter a year-end close template name..</span></span>
11. <span data-ttu-id="b1b29-129">W polu **Kalendarz obrachunkowy** wybierz rok obrachunkowy, dla którego zostanie utworzony szablon.</span><span class="sxs-lookup"><span data-stu-id="b1b29-129">In the **Fiscal calendar** field, select the fiscal year for which the template will be created.</span></span>

    <span data-ttu-id="b1b29-130">W szablonie zamknięcia na koniec roku można grupować tylko firmy, które używają tego samego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="b1b29-130">Only legal entities which use the same fiscal year can be grouped together in the year-end close template.</span></span> <span data-ttu-id="b1b29-131">To dlatego, że zamknięcie na koniec roku wykonuje się przez zaznaczenie roku obrachunkowego, a nie daty.</span><span class="sxs-lookup"><span data-stu-id="b1b29-131">This is because the year end close is done by selecting a fiscal year, not a date.</span></span>  

12. <span data-ttu-id="b1b29-132">W **okienku akcji** kliknij pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-132">On the **Action pane**, click **Save**.</span></span>
13. <span data-ttu-id="b1b29-133">W sekcji **osoby prawne** kliknij przycisk **Dodaj**, aby wybrać firmy dla tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="b1b29-133">In the **Legal entities** section, click **Add** to select the legal entities for this template.</span></span>
    
    <span data-ttu-id="b1b29-134">Firmy mogą być dodawane poprzez wybieranie firm lub wybieranie hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="b1b29-134">Legal entities can be added by either selecting the legal entities or by selecting an organizational hierarchy.</span></span>  <span data-ttu-id="b1b29-135">Zostaną dodane tylko firmy mające hierarchię organizacyjną z wybranym takim samym kalendarzem obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="b1b29-135">Only legal entities with the organizational hierarchy with the same fiscal calendar selected will be added.</span></span>  

14. <span data-ttu-id="b1b29-136">Wybierz firmy lub hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="b1b29-136">Select either the legal entities or the organizational hierarchy.</span></span>
15. <span data-ttu-id="b1b29-137">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-137">Click **OK**.</span></span>
16. <span data-ttu-id="b1b29-138">Wybierz opcję „tak” lub „nie” w **Przenieś wymiary bilansu**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-138">Select 'Yes' or 'No' in the **Transfer balance sheet dimension**.</span></span>

    <span data-ttu-id="b1b29-139">Jest najlepszym rozwiązaniem, aby ustawić tę opcję na Tak dla kont bilansowych.</span><span class="sxs-lookup"><span data-stu-id="b1b29-139">It's best practice to set this option to Yes for Balance sheet accounts.</span></span> <span data-ttu-id="b1b29-140">Spowoduje to zachowanie wymiarów finansowych w księgowanych transakcjach podczas tworzenia sald początkowych dla kont bilansowych.</span><span class="sxs-lookup"><span data-stu-id="b1b29-140">This will maintain the financial dimensions on posted transactions when creating the beginning balances for the balance sheet accounts.</span></span> <span data-ttu-id="b1b29-141">Dla kont wynikowych można wybrać opcję zachowania wymiarów finansowych (Zamknij wszystko), kiedy salda są przenoszone do dochodów zatrzymanych, lub opcję zastąpienia wymiarów finansowych inną wartością wymiaru (Zamknij jeden).</span><span class="sxs-lookup"><span data-stu-id="b1b29-141">For profit and loss accounts, you can select to maintain the financial dimensions (Close all) when the balances are moved to Retained earnings or you can select to have the financial dimensions replaced with a different dimension value (Close single).</span></span> <span data-ttu-id="b1b29-142">Jeśli zostanie wybrana opcja Zamknij jeden, można zdefiniować określoną dla każdego wymiaru lub nawet zdecydować się na niewypełnianie tego pola.</span><span class="sxs-lookup"><span data-stu-id="b1b29-142">If you choose Close single, you can define a specific dimension value for each dimension or even choose to leave it blank.</span></span>  

17. <span data-ttu-id="b1b29-143">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-143">Click **Save**.</span></span>
18. <span data-ttu-id="b1b29-144">Uruchom zamknięcia na koniec roku, wybierając operację **Uruchom zamknięcie obrachunkowe** w **Okienku akcji**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-144">Start the year-end close by choosing **Run fiscal close** on the **Action Pane**.</span></span> <span data-ttu-id="b1b29-145">Zamknięcia na koniec roku zostanie wykonane dla wybranego szablonu.</span><span class="sxs-lookup"><span data-stu-id="b1b29-145">The year-end close will be run for the selected template.</span></span>  
19. <span data-ttu-id="b1b29-146">W szablonie zaznacz wszystkie lub tylko niektóre firmy, dla których ma zostać wykonane zamknięcie na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-146">Select all or a subset of legal entities from the template for which to run the year-end close.</span></span>

    <span data-ttu-id="b1b29-147">Aby podczas pierwszego wykonywania zamknięcia na koniec roku uzyskać salda początkowe, większość organizacji wykonuje zamknięcie na koniec roku dla wszystkich firm zdefiniowanych w szablonie.</span><span class="sxs-lookup"><span data-stu-id="b1b29-147">When first running the year-end close, to get beginning balance,s most organizations may choose to run the year-end close for all legal entities within the template.</span></span> <span data-ttu-id="b1b29-148">Jeśli zapisy korygujące zostaną wprowadzone potem, można wykonać zamknięcie na koniec roku tylko dla firm mających korekty.</span><span class="sxs-lookup"><span data-stu-id="b1b29-148">If adjusting entries are made after that, you may choose to run the year-end close for only the legal entities that have adjustments.</span></span>  

20. <span data-ttu-id="b1b29-149">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-149">Click **OK**.</span></span>
21. <span data-ttu-id="b1b29-150">Wybierz rok obrachunkowy, dla którego chcesz wykonać zamknięcie na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-150">Select the fiscal year for which to run the year-end close.</span></span>
22. <span data-ttu-id="b1b29-151">W **polu Załącznik** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b1b29-151">In the **Voucher field**, type a value.</span></span> <span data-ttu-id="b1b29-152">Jest najlepszym rozwiązaniem, aby uwzględnić rok obrachunkowy w numer załącznika, ponieważ ułatwi do znalezienie utworzonego załącznika zamknięcia na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="b1b29-152">It's best practice to include the fiscal year in the voucher number, to make it easier to find the year-end close voucher that is created.</span></span>  
23. <span data-ttu-id="b1b29-153">Zamknięcie na koniec roku domyślnie jest uruchamiane w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="b1b29-153">The year-end close defaults to run in batch.</span></span> <span data-ttu-id="b1b29-154">Dla długotrwałych procesów najlepszym rozwiązaniem jest uruchamianie ich w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="b1b29-154">It's best practice for long-running processes to run in batch mode.</span></span> <span data-ttu-id="b1b29-155">Zazwyczaj procesy trwają długo, dlatego domyślnie jest używany tryb wsadowy.</span><span class="sxs-lookup"><span data-stu-id="b1b29-155">This is typically one of those processes, which is why the default is to use batch mode.</span></span>  
24. <span data-ttu-id="b1b29-156">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1b29-156">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]