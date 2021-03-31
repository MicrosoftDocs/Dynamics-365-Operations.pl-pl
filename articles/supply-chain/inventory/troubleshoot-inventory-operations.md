---
title: Rozwiązywanie problemów z operacjami magazynowymi
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z operacjami magazynowymi.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: ee1bfbf1b5aa736e1ee5bd38403b6c94c2bd036b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225009"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="d5050-103">Rozwiązywanie problemów z operacjami magazynowymi</span><span class="sxs-lookup"><span data-stu-id="d5050-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5050-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z operacjami magazynowymi.</span><span class="sxs-lookup"><span data-stu-id="d5050-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="d5050-105">Nie można znaleźć okna dialogowego „Przepływ pracy” dla arkuszy magazynowych.</span><span class="sxs-lookup"><span data-stu-id="d5050-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-106">Issue description</span></span>

<span data-ttu-id="d5050-107">Nie można znaleźć okna dialogowego **Przepływ pracy** na stronie arkusza lub powiązane operacje przepływu pracy są niedostępne.</span><span class="sxs-lookup"><span data-stu-id="d5050-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="d5050-108">Ten problem może mieć trzy przyczyny, co opisano w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="d5050-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="d5050-109">Rozwiązanie problemu 1</span><span class="sxs-lookup"><span data-stu-id="d5050-109">Issue resolution 1</span></span>

<span data-ttu-id="d5050-110">Jeśli problem dotyczy wszystkich użytkowników, może on wystąpić, ponieważ przepływ pracy zatwierdzania nie został przypisany do nazwy arkusza.</span><span class="sxs-lookup"><span data-stu-id="d5050-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="d5050-111">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="d5050-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="d5050-112">Przejdź do obszaru **Zarządzanie zapasami &gt; Ustawienia &gt; Nazwy arkuszy &gt; Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="d5050-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="d5050-113">W okienku listy wybierz nazwę arkusza, aby otworzyć jego ustawienia.</span><span class="sxs-lookup"><span data-stu-id="d5050-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="d5050-114">Na skróconej karcie **Ogólne** ustaw opcję **Przepływ pracy zatwierdzania** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="d5050-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="d5050-115">Wybierz **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie zmiany.</span><span class="sxs-lookup"><span data-stu-id="d5050-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="d5050-116">W polu **Przepływ pracy** wybierz przepływ pracy do użycia dla wybranej nazwy arkusza.</span><span class="sxs-lookup"><span data-stu-id="d5050-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="d5050-117">Rozwiązanie problemu 2</span><span class="sxs-lookup"><span data-stu-id="d5050-117">Issue resolution 2</span></span>

<span data-ttu-id="d5050-118">Jeśli w przepływie pracy jest używany dostosowany kod, problemy mogą wystąpić po uaktualnieniu systemu.</span><span class="sxs-lookup"><span data-stu-id="d5050-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="d5050-119">Na przykład w przepływie pracy arkusza przycisk **Prześlij** może być wyszarzony, więc nie można go wybrać w celu zatwierdzenia przesłania.</span><span class="sxs-lookup"><span data-stu-id="d5050-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="d5050-120">Jeśli przycisk **Prześlij** jest wyszarzony, być może przepływ pracy został dostosowany, co oznacza, że metoda przepływu pracy `canSubmitToWorkflow()` w `FormDataUtil` została rozszerzona.</span><span class="sxs-lookup"><span data-stu-id="d5050-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="d5050-121">Aby rozwiązać ten problem, zmień sposób rozszerzania metody `canSubmitToWorkflow()` w celu używania struktury w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d5050-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="d5050-122">Rozwiązanie problemu 3</span><span class="sxs-lookup"><span data-stu-id="d5050-122">Issue resolution 3</span></span>

<span data-ttu-id="d5050-123">Jeśli problem dotyczy tylko kilku określonych użytkowników, użytkownicy ci mogą nie mieć uprawnień zabezpieczeń wymaganych do uruchamiania operacji przepływu pracy w arkuszach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="d5050-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="d5050-124">Sprawdź, czy każdy z tych użytkowników ma uprawnienie zabezpieczeń *Obsługa przepływu pracy arkusza magazynowego*.</span><span class="sxs-lookup"><span data-stu-id="d5050-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="d5050-125">Domyślnie to uprawnienie jest przypisywane do obowiązków o takiej samej nazwie i jest stosowane do ról *Pracownik magazynu* i *Menedżer magazynu*.</span><span class="sxs-lookup"><span data-stu-id="d5050-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="d5050-126">Mój arkusz magazynowy ma nadal stan zablokowania przez system, a zadanie wsadowe przepływu pracy nie działa.</span><span class="sxs-lookup"><span data-stu-id="d5050-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-127">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-127">Issue description</span></span>

<span data-ttu-id="d5050-128">Jeden z arkuszy magazynowych jest zablokowany przez operację i nie jest zwalniany.</span><span class="sxs-lookup"><span data-stu-id="d5050-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="d5050-129">Jeśli na przykład podczas księgowania wystąpi nieznany błąd (czyli operacja blokowania systemu), arkusz może pozostać w stanie zablokowania systemu.</span><span class="sxs-lookup"><span data-stu-id="d5050-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="d5050-130">W takim przypadku program obsługi elementów roboczych przepływu pracy wystąpi błąd podczas blokowania weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="d5050-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d5050-131">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="d5050-131">Issue resolution</span></span>

<span data-ttu-id="d5050-132">Zaloguj się do wystąpienia programu SQL Server dla aplikacji Supply Chain Management i sprawdź, czy ustawienie **InventJournalTable.SystemBlocked** ma wartość *1*.</span><span class="sxs-lookup"><span data-stu-id="d5050-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="d5050-133">Jeśli tak, upewnij się, że arkusz nie powinien być w stanie zablokowania, a następnie zresetuj pozycję **InventJournalTable.SystemBlocked** na *0*.</span><span class="sxs-lookup"><span data-stu-id="d5050-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="d5050-134">Nigdy nie ukończono mojego przepływu pracy arkusza magazynowego i nie można go edytować ani zaksięgować.</span><span class="sxs-lookup"><span data-stu-id="d5050-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-135">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-135">Issue description</span></span>

<span data-ttu-id="d5050-136">Po przesłaniu przepływu pracy zatwierdzania arkusza proces przetwarzania przepływu pracy przestaje odpowiadać i nie można edytować ani przetwarzać arkuszy.</span><span class="sxs-lookup"><span data-stu-id="d5050-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d5050-137">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="d5050-137">Issue resolution</span></span>

<span data-ttu-id="d5050-138">Istnieje kilka przyczyn, dla których przetwarzanie przepływu może nie zostać ukończone.</span><span class="sxs-lookup"><span data-stu-id="d5050-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="d5050-139">Sprawdź następujące problemy:</span><span class="sxs-lookup"><span data-stu-id="d5050-139">Check for the following issues:</span></span>

- <span data-ttu-id="d5050-140">Przejdź do obszaru **Zarządzanie zapasami &gt; Ustawienia &gt; Przepływy pracy zarządzania zapasami** i przejrzyj konfigurację danego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d5050-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="d5050-141">Aby uzyskać więcej informacji, zobacz temat [Przepływy pracy zatwierdzania arkusza magazynowego](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d5050-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="d5050-142">Przepływ pracy może napotkać wyjątek lub błąd.</span><span class="sxs-lookup"><span data-stu-id="d5050-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="d5050-143">Przejrzyj historię elementów roboczych, których dotyczy ten przepływ pracy, aby sprawdzić, czy zawiera on błąd aplikacji, który kończy przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="d5050-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="d5050-144">Arkusz magazynowy można aktualizować lub edytować tylko wtedy, gdy jest zatwierdzony.</span><span class="sxs-lookup"><span data-stu-id="d5050-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="d5050-145">Jeśli odwołanie jest aktywne, można spróbować odwołać arkusz.</span><span class="sxs-lookup"><span data-stu-id="d5050-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="d5050-146">Wykonanie zadania wsadowego przepływu pracy może być zawieszone z wielu przyczyn.</span><span class="sxs-lookup"><span data-stu-id="d5050-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="d5050-147">Niektóre z tych przyczyn mogą być spowodowane przez problem ze strukturą przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d5050-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="d5050-148">Warunki przepływu pracy arkusza magazynowego mają zastosowanie tylko na poziomie arkusza, a nie na poziomie wiersza</span><span class="sxs-lookup"><span data-stu-id="d5050-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-149">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-149">Issue description</span></span>

<span data-ttu-id="d5050-150">Ten problem może wystąpić na przykład w przypadku próby skonfigurowania warunku przepływu pracy arkusza magazynowego dla kwoty kosztu.</span><span class="sxs-lookup"><span data-stu-id="d5050-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="d5050-151">Warunek jest ustawiany w taki sposób, aby krok 1 był uruchamiany tylko wtedy, gdy kwota kosztu jest mniejsza niż 100.</span><span class="sxs-lookup"><span data-stu-id="d5050-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="d5050-152">Następnie inny warunek jest ustawiany w taki sposób, aby krok 2 był uruchamiany tylko wtedy, gdy kwota kosztu jest większa lub równa 100.</span><span class="sxs-lookup"><span data-stu-id="d5050-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="d5050-153">Potem podczas uruchamiania przepływu pracy historia przepływu pracy pokazuje tylko jeden wiersz, a pierwszy warunek jest zawsze obliczany jako *prawdziwy*, niezależnie od przesłanej wartości.</span><span class="sxs-lookup"><span data-stu-id="d5050-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="d5050-154">Obejście problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-154">Issue workaround</span></span>

<span data-ttu-id="d5050-155">W aktualnym wydaniu warunki przepływu pracy arkusza magazynowego mają zastosowanie tylko na poziomie arkusza, a nie na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="d5050-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="d5050-156">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="d5050-156">This behavior is by design.</span></span> <span data-ttu-id="d5050-157">Zaleca się, aby kryteria warunku ustawić tylko dla atrybutów na poziomie arkusza.</span><span class="sxs-lookup"><span data-stu-id="d5050-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="d5050-158">Okienko filtru na stronie dostępnych zapasów nie filtruje wyników w oczekiwany sposób.</span><span class="sxs-lookup"><span data-stu-id="d5050-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-159">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-159">Issue description</span></span>

<span data-ttu-id="d5050-160">Filtry w okienku filtrów na stronie **dostępnych zapasów** nie filtruje wyników w oczekiwany sposób.</span><span class="sxs-lookup"><span data-stu-id="d5050-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d5050-161">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="d5050-161">Issue resolution</span></span>

<span data-ttu-id="d5050-162">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="d5050-162">This behavior is by design.</span></span>

<span data-ttu-id="d5050-163">Strona  **dostępnych zapasów** jest składana z tabeli szczegółowych dostępnych zapasów, która zawiera wszystkie dostępne wymiary.</span><span class="sxs-lookup"><span data-stu-id="d5050-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="d5050-164">Jednak lista na tej stronie jest podsumowaniem.</span><span class="sxs-lookup"><span data-stu-id="d5050-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="d5050-165">Dlatego można łączyć wiersze z tabeli źródłowej, sumując wartości zgodnie z podanymi wymiarami.</span><span class="sxs-lookup"><span data-stu-id="d5050-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="d5050-166">Filtry zdefiniowane w okienku filtrów mają zastosowanie do tabeli źródłowej, a nie do listy agregowanej.</span><span class="sxs-lookup"><span data-stu-id="d5050-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="d5050-167">Takie zachowanie może czasami mieć nieoczekiwane wyniki, tak jak pokazano w [tych przykładach](inventory-on-hand-list.md#examples).</span><span class="sxs-lookup"><span data-stu-id="d5050-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="d5050-168">Jednak  [filtry dostarczone w siatce](inventory-on-hand-list.md#grid-filters) *są* stosowane do zagregowanej listy.</span><span class="sxs-lookup"><span data-stu-id="d5050-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="d5050-169">Filtry te obejmują zarówno QuickFilter na górze siatki, jak i filtr dla każdego nagłówka kolumny.</span><span class="sxs-lookup"><span data-stu-id="d5050-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="d5050-170">Jednostki i ilość jednostek nie działają poprawnie w arkuszu magazynowym.</span><span class="sxs-lookup"><span data-stu-id="d5050-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-171">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-171">Issue description</span></span>

<span data-ttu-id="d5050-172">Podczas pracy z jednostkami i ilościami w arkuszu magazynowymi może wystąpić jeden lub oba następujące problemy:</span><span class="sxs-lookup"><span data-stu-id="d5050-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="d5050-173">Nie ma żadnych jednostek ani ilości jednostek w arkuszu magazynowym, gdy dla zwolnionego produktu jest ustawiona jednostka konwersji i nie można zmienić tej jednostki w arkuszu magazynowym.</span><span class="sxs-lookup"><span data-stu-id="d5050-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="d5050-174">W arkuszu magazynowym są widoczne pola **Ilość** i **Jednostka**, ale pole **Ilość jednostki** jest niewidoczne.</span><span class="sxs-lookup"><span data-stu-id="d5050-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="d5050-175">Po zmianie jednostki, wprowadzeniu ilości i zaksięgowaniu arkusza w arkuszu będzie nadal wyświetlana oryginalna jednostka miary dla tej ilości.</span><span class="sxs-lookup"><span data-stu-id="d5050-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d5050-176">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="d5050-176">Issue resolution</span></span>

<span data-ttu-id="d5050-177">Aby naprawić ten problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="d5050-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="d5050-178">Upewnij się, że w obszarze roboczym **Zarządzanie funkcjami** jest włączona funkcja *Używanie jednostki miary i ilości jednostek w arkuszach magazynowych*.</span><span class="sxs-lookup"><span data-stu-id="d5050-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="d5050-179">Ta funkcja dodaje pola **Jednostka** i **Ilość jednostek** do arkusza.</span><span class="sxs-lookup"><span data-stu-id="d5050-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="d5050-180">Po włączeniu tej funkcji użyj pól **Ilość**, **Ilość jednostki** i **Jednostka** w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d5050-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="d5050-181">**Ilość** — określ ilość, używając domyślnej jednostki zdefiniowanej dla zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="d5050-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="d5050-182">W tym miejscu jednak nie jest wyświetlana jednostka domyślna.</span><span class="sxs-lookup"><span data-stu-id="d5050-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="d5050-183">Jeśli zostanie ustawiona konwersja między jednostką domyślną a jednostką wybraną w polu **Jednostka**, pole **Ilość** jest automatycznie aktualizowane na podstawie opcji wybranych w polach **Ilość jednostki** i **Jednostka**.</span><span class="sxs-lookup"><span data-stu-id="d5050-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="d5050-184">**Ilość jednostki** — określ ilość, używając jednostki wybranej w polu **Jednostka**.</span><span class="sxs-lookup"><span data-stu-id="d5050-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="d5050-185">**Jednostka** — wybierz jednostkę, która zostanie zastosowania do wartości w polu **Ilość jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d5050-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="d5050-186">Wyświetlany jest następujący komunikat o błędzie: „Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0”.</span><span class="sxs-lookup"><span data-stu-id="d5050-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d5050-187">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="d5050-187">Issue description</span></span>

<span data-ttu-id="d5050-188">Podczas próby zaksięgowania transakcji magazynowej lub rezerwacji zapasów zostanie wyświetlony następujący komunikat o błędzie: „Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0”.</span><span class="sxs-lookup"><span data-stu-id="d5050-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="d5050-189">Ten problem występuje, gdy ilość transakcji magazynowej jest określona jako wartość dziesiętna poniżej poziomu dokładności, który obsługuje to pole.</span><span class="sxs-lookup"><span data-stu-id="d5050-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="d5050-190">Na przykład dla transakcji magazynowej określono ilość *0,5*, ale są obsługiwane tylko liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="d5050-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="d5050-191">Dlatego powinna to być wartość *1*, a nie *0,5*.</span><span class="sxs-lookup"><span data-stu-id="d5050-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d5050-192">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="d5050-192">Issue resolution</span></span>

1. <span data-ttu-id="d5050-193">Uruchom następujący skrypt w wystąpieniu programu SQL Server, aby zaokrąglić ilości w transakcjach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="d5050-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="d5050-194">Ten skrypt spowoduje poprawienie wartości w tabeli **inventTrans**.</span><span class="sxs-lookup"><span data-stu-id="d5050-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="d5050-195">Uruchom sprawdzanie spójności dostępnych zapasów, dla których włączono opcję **poprawiania błędu**.</span><span class="sxs-lookup"><span data-stu-id="d5050-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="d5050-196">Ten test spowoduje poprawienie wartości w tabeli **inventSum**.</span><span class="sxs-lookup"><span data-stu-id="d5050-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5050-197">Zdecydowanie zalecamy uważne edytowanie skryptu zgodnie z wymaganiami środowiska, testowanie go w środowisku testowym, a następnie sprawdzanie wynikowych danych przed uruchomieniem skryptu w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="d5050-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]