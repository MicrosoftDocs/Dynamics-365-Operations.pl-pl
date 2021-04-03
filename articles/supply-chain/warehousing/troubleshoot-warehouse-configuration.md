---
title: Rozwiązywanie problemów z konfiguracją magazynu
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas konfiguracji Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1fe285f05e5f1ddcb7bd206290b9954cbdaffc75
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487104"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="ab896-103">Rozwiązywanie problemów z konfiguracją magazynu</span><span class="sxs-lookup"><span data-stu-id="ab896-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab896-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas konfiguracji Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ab896-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="ab896-105">Pojawia się następujący komunikat o błędzie: „Numer identyfikacyjny lub lokalizacja jest nieprawidłowa”.</span><span class="sxs-lookup"><span data-stu-id="ab896-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-106">Issue description</span></span>

<span data-ttu-id="ab896-107">Ten komunikat o błędzie pojawia się podczas skanowania identyfikatora numeru identyfikacyjnego lub lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ab896-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-108">Issue resolution</span></span>

<span data-ttu-id="ab896-109">Upewnij się, że identyfikator numeru identyfikacyjnego nie jest zarezerwowany na coś innego.</span><span class="sxs-lookup"><span data-stu-id="ab896-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="ab896-110">Ten problem występuje, jeśli wartość, którą użytkownik przeskanował w aplikacji magazynu, była zarówno prawidłową lokalizacją, jak i prawidłowym identyfikatorem numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="ab896-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="ab896-111">Jednak ten problem został rozwiązany w wersji 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="ab896-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="ab896-112">Pojawia się następujący komunikat o błędzie: „Numer identyfikacyjny musi być określony dla tej lokalizacji”.</span><span class="sxs-lookup"><span data-stu-id="ab896-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-113">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-113">Issue description</span></span>

<span data-ttu-id="ab896-114">Ten komunikat o błędzie pojawia się, jeśli utworzysz zlecenie przeniesienia przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="ab896-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-115">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-115">Issue resolution</span></span>

<span data-ttu-id="ab896-116">Pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”.</span><span class="sxs-lookup"><span data-stu-id="ab896-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="ab896-117">Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym.</span><span class="sxs-lookup"><span data-stu-id="ab896-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="ab896-118">Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="ab896-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="ab896-119">Otrzymuję następujący komunikat o błędzie: „Nie można utworzyć wiersza szablonu pracy dla zmiany stanu zapasów, ponieważ typ pracy jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="ab896-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="ab896-120">Wybierz inny typ pracy".</span><span class="sxs-lookup"><span data-stu-id="ab896-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-121">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-121">Issue description</span></span>

<span data-ttu-id="ab896-122">W przypadku szablonu pracy nie można wybrać *Zmianę stanu zapasów* w kolumnie **Typ pracy** w sekcji **Szczegóły szablonu pracy**.</span><span class="sxs-lookup"><span data-stu-id="ab896-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-123">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-123">Issue resolution</span></span>

<span data-ttu-id="ab896-124">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="ab896-124">This behavior is by design.</span></span> <span data-ttu-id="ab896-125">Typ pracy *Zmiana stanu zapasów* jest używany tylko przez procesy systemowe.</span><span class="sxs-lookup"><span data-stu-id="ab896-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="ab896-126">Nie można go skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="ab896-126">It can't be configured.</span></span> <span data-ttu-id="ab896-127">Ponieważ lista typów prac jest ustalona jako wyliczenie, dodatkowe wpisy nie mogą być filtrowane z menu rozwijanego **Typ pracy**.</span><span class="sxs-lookup"><span data-stu-id="ab896-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="ab896-128">Otrzymuję następujący komunikat o błędzie: „Ilość jest nieprawidłowa dla jednostki 1%”.</span><span class="sxs-lookup"><span data-stu-id="ab896-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-129">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-129">Issue description</span></span>

<span data-ttu-id="ab896-130">Ilość jest nieprawidłowa dla jednostki *każdy*, jeśli w jednej lokalizacji istnieje praca pobrania zawierająca wiele numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ab896-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-131">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-131">Issue resolution</span></span>

<span data-ttu-id="ab896-132">Sprawdź, czy pola **Identyfikator grupy sekwencji jednostek** i **Konwersje jednostek** dla zwolnionego produktu lub wariantu produktu są poprawnie ustawione.</span><span class="sxs-lookup"><span data-stu-id="ab896-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="ab896-133">Należy zauważyć, że komunikat o błędzie został ulepszony w wersji 10.0.15 (zobacz [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="ab896-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="ab896-134">Nowy komunikat o błędzie to „Ilość jest nieprawidłowa.</span><span class="sxs-lookup"><span data-stu-id="ab896-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="ab896-135">Oczekiwane %1 %2."</span><span class="sxs-lookup"><span data-stu-id="ab896-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="ab896-136">W dyrektywach lokalizacji dotyczących pracy nad zamówieniem sprzedaży, opcja wielu jednostek SKU nie ocenia wielu akcji dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ab896-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-137">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-137">Issue description</span></span>

<span data-ttu-id="ab896-138">Dyrektywy lokalizacji typu zlecenia pracy *Zamówienia sprzedaży* i typu pracy *Odłożenie* nie oceniają wielu działań dyrektywy lokalizacji, gdy wybrana jest opcja **Wiele jednostek SKU**.</span><span class="sxs-lookup"><span data-stu-id="ab896-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="ab896-139">Sprawdzana jest tylko akcja dyrektywy pierwszej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ab896-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-140">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-140">Issue resolution</span></span>

<span data-ttu-id="ab896-141">Nowa funkcja *Oceń wszystkie akcje dla dyrektyw lokalizacji dla wielu jednostek SKU* została dodana w wersji 10.0.15 (zobacz [4579866 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="ab896-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="ab896-142">Ta funkcja ocenia wszystkie akcje dyrektyw lokalizacji w wielu jednostkach SKU.</span><span class="sxs-lookup"><span data-stu-id="ab896-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="ab896-143">Jeśli ta funkcja jest wymagana, należy skorzystać [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby ją włączyć.</span><span class="sxs-lookup"><span data-stu-id="ab896-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="ab896-144">Nie mogę skorzystać z aplikacji magazynowej, aby przeprowadzić pobieranie częściowe.</span><span class="sxs-lookup"><span data-stu-id="ab896-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-145">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-145">Issue description</span></span>

<span data-ttu-id="ab896-146">W przypadku zamówień sprzedaży i przeniesienia nie można pomijać towarów ani wykonać pobrania częściowego.</span><span class="sxs-lookup"><span data-stu-id="ab896-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-147">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-147">Issue resolution</span></span>

<span data-ttu-id="ab896-148">Na stronie **Elementy menu urządzenia przenośnego** dla każdego elementu menu skonfigurowanego do przetwarzania zamówień sprzedaży lub zamówień przeniesienia ustaw opcję **Zezwalaj na dzielenie pracy** na skróconej karcie **Ogólne** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="ab896-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="ab896-149">Jak mogę wykonać zmianę stanu zapasów dla części pracy dotyczącej ilości częściowej?</span><span class="sxs-lookup"><span data-stu-id="ab896-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-150">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-150">Issue description</span></span>

<span data-ttu-id="ab896-151">Konieczna jest zmiana stanu zapasów dla częściowej ilości partii.</span><span class="sxs-lookup"><span data-stu-id="ab896-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-152">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-152">Issue resolution</span></span>

<span data-ttu-id="ab896-153">Aby umożliwić pracownikom wprowadzenie tej zmiany, można utworzyć element menu dla aplikacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="ab896-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="ab896-154">Na stronie **Elementy menu urządzenia przenośnego** utwórz (lub edytuj) element menu, który ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="ab896-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="ab896-155">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="ab896-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="ab896-156">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="ab896-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="ab896-157">**Proces tworzenia pracy:** *Przesunięcie*</span><span class="sxs-lookup"><span data-stu-id="ab896-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="ab896-158">**Wyświetl kolumnę Stan zapasów:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="ab896-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="ab896-159">W razie konieczności można skonfigurować inne pola na stronie.</span><span class="sxs-lookup"><span data-stu-id="ab896-159">You can set other fields on the page as you require.</span></span>

## <a name="the-dock-management-profile-of-a-location-profile-is-not-preventing-inventory-types-from-being-mixed"></a><span data-ttu-id="ab896-160">Profil zarządzania na rampie profilu lokalizacji nie zapobiega mieszaniu typów zapasów.</span><span class="sxs-lookup"><span data-stu-id="ab896-160">The dock management profile of a location profile is not preventing inventory types from being mixed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab896-161">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ab896-161">Issue description</span></span>

<span data-ttu-id="ab896-162">Korzystasz z *zasad konsolidacji przesyłek*.</span><span class="sxs-lookup"><span data-stu-id="ab896-162">You are using *shipment consolidation policies*.</span></span> <span data-ttu-id="ab896-163">Skonfigurowano *profil zarządzania na rampie* dla *profilu lokalizacji*, ale po utworzeniu pracy typy zapasów są mieszane w ostatecznej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ab896-163">You have set up a *dock management profile* for a *location profile*, but when work is created, the inventory types are mixed at the final location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab896-164">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab896-164">Issue resolution</span></span>

<span data-ttu-id="ab896-165">Profile zarządzania na rampie wymagają wcześniejszego podziału pracy.</span><span class="sxs-lookup"><span data-stu-id="ab896-165">Dock management profiles require work to be split up front.</span></span> <span data-ttu-id="ab896-166">Profil zarządzania na rampie oczekuje, że nagłówek pracy nie będzie zawierał wielu lokalizacji odłożyń.</span><span class="sxs-lookup"><span data-stu-id="ab896-166">In other words, the dock management profile expects that a work header won't have multiple put locations.</span></span>

<span data-ttu-id="ab896-167">Aby profil zarządzania dokiem mógł efektywnie zarządzać mieszaniem zapasów, należy ustawić przerwę w nagłówku pracy.</span><span class="sxs-lookup"><span data-stu-id="ab896-167">For the dock management profile to effectively manage the mixing of inventory, a work header break must be set up.</span></span>

<span data-ttu-id="ab896-168">W tym przykładzie nasz profil zarządzania dokiem jest skonfigurowany tak, że **Typy zapasów, które nie powinny być mieszane**, są ustawione na *Identyfikator przesyłki*, a my ustawimy przerwę w nagłówku pracy:</span><span class="sxs-lookup"><span data-stu-id="ab896-168">In this example our dock management profile is configured such that **Inventory types that should not be mixed** is set to *Shipment ID*, and we'll set up a work header break for it:</span></span>

1. <span data-ttu-id="ab896-169">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="ab896-169">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="ab896-170">Wybierz **Typ zlecenia pracy** do edycji (na przykład *Zamówienia zakupu*).</span><span class="sxs-lookup"><span data-stu-id="ab896-170">Select the **Work order type** to edit (for example, *Purchase orders*).</span></span>
1. <span data-ttu-id="ab896-171">Wybierz szablon pracy do edycji.</span><span class="sxs-lookup"><span data-stu-id="ab896-171">Select the work template to edit.</span></span>
1. <span data-ttu-id="ab896-172">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="ab896-172">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="ab896-173">Otwórz kartę **Sortowanie** i dodaj wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="ab896-173">Open the **Sorting** tab and add a row with the following settings:</span></span>
    - <span data-ttu-id="ab896-174">**Tabela** - *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="ab896-174">**Table** - *Temporary work transactions*</span></span>
    - <span data-ttu-id="ab896-175">**Tabela pochodna** - *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="ab896-175">**Derived table** - *Temporary work transactions*</span></span>
    - <span data-ttu-id="ab896-176">**Pole** - *Identyfikator wysyłki*</span><span class="sxs-lookup"><span data-stu-id="ab896-176">**Field** - *Shipment ID*</span></span>
1. <span data-ttu-id="ab896-177">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab896-177">Select **OK**.</span></span>
1. <span data-ttu-id="ab896-178">Wróć do strony **Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="ab896-178">You return to the **Work templates** page.</span></span> <span data-ttu-id="ab896-179">W okienku akcji wybierz **Podziały nagłówka pracy**.</span><span class="sxs-lookup"><span data-stu-id="ab896-179">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="ab896-180">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="ab896-180">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ab896-181">Zaznacz pole wyboru skojarzone z **Polem o nazwie** *Identyfikator wysyłki*.</span><span class="sxs-lookup"><span data-stu-id="ab896-181">Select the check box associated with the **Field name** *Shipment ID*.</span></span>
1. <span data-ttu-id="ab896-182">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ab896-182">On the Action Pane, select **Save**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
