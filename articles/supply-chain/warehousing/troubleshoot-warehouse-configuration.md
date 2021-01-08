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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646114"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="c1596-103">Rozwiązywanie problemów z konfiguracją magazynu</span><span class="sxs-lookup"><span data-stu-id="c1596-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1596-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas konfiguracji Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c1596-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="c1596-105">Pojawia się następujący komunikat o błędzie: „Numer identyfikacyjny lub lokalizacja jest nieprawidłowa”.</span><span class="sxs-lookup"><span data-stu-id="c1596-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-106">Issue description</span></span>

<span data-ttu-id="c1596-107">Ten komunikat o błędzie pojawia się podczas skanowania identyfikatora numeru identyfikacyjnego lub lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c1596-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-108">Issue resolution</span></span>

<span data-ttu-id="c1596-109">Upewnij się, że identyfikator numeru identyfikacyjnego nie jest zarezerwowany na coś innego.</span><span class="sxs-lookup"><span data-stu-id="c1596-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="c1596-110">Ten problem występuje, jeśli wartość, którą użytkownik przeskanował w aplikacji magazynu, była zarówno prawidłową lokalizacją, jak i prawidłowym identyfikatorem numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c1596-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="c1596-111">Jednak ten problem został rozwiązany w wersji 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="c1596-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="c1596-112">Pojawia się następujący komunikat o błędzie: „Numer identyfikacyjny musi być określony dla tej lokalizacji”.</span><span class="sxs-lookup"><span data-stu-id="c1596-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-113">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-113">Issue description</span></span>

<span data-ttu-id="c1596-114">Ten komunikat o błędzie pojawia się, jeśli utworzysz zlecenie przeniesienia przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="c1596-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-115">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-115">Issue resolution</span></span>

<span data-ttu-id="c1596-116">Pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”.</span><span class="sxs-lookup"><span data-stu-id="c1596-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="c1596-117">Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym.</span><span class="sxs-lookup"><span data-stu-id="c1596-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="c1596-118">Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c1596-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="c1596-119">Otrzymuję następujący komunikat o błędzie: „Nie można utworzyć wiersza szablonu pracy dla zmiany stanu zapasów, ponieważ typ pracy jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="c1596-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="c1596-120">Wybierz inny typ pracy".</span><span class="sxs-lookup"><span data-stu-id="c1596-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-121">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-121">Issue description</span></span>

<span data-ttu-id="c1596-122">W przypadku szablonu pracy nie można wybrać *Zmianę stanu zapasów* w kolumnie **Typ pracy** w sekcji **Szczegóły szablonu pracy**.</span><span class="sxs-lookup"><span data-stu-id="c1596-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-123">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-123">Issue resolution</span></span>

<span data-ttu-id="c1596-124">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="c1596-124">This behavior is by design.</span></span> <span data-ttu-id="c1596-125">Typ pracy *Zmiana stanu zapasów* jest używany tylko przez procesy systemowe.</span><span class="sxs-lookup"><span data-stu-id="c1596-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="c1596-126">Nie można go skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="c1596-126">It can't be configured.</span></span> <span data-ttu-id="c1596-127">Ponieważ lista typów prac jest ustalona jako wyliczenie, dodatkowe wpisy nie mogą być filtrowane z menu rozwijanego **Typ pracy**.</span><span class="sxs-lookup"><span data-stu-id="c1596-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="c1596-128">Otrzymuję następujący komunikat o błędzie: „Ilość jest nieprawidłowa dla jednostki 1%”.</span><span class="sxs-lookup"><span data-stu-id="c1596-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-129">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-129">Issue description</span></span>

<span data-ttu-id="c1596-130">Ilość jest nieprawidłowa dla jednostki *każdy*, jeśli w jednej lokalizacji istnieje praca pobrania zawierająca wiele numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="c1596-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-131">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-131">Issue resolution</span></span>

<span data-ttu-id="c1596-132">Sprawdź, czy pola **Identyfikator grupy sekwencji jednostek** i **Konwersje jednostek** dla zwolnionego produktu lub wariantu produktu są poprawnie ustawione.</span><span class="sxs-lookup"><span data-stu-id="c1596-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="c1596-133">Należy zauważyć, że komunikat o błędzie został ulepszony w wersji 10.0.15 (zobacz [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="c1596-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="c1596-134">Nowy komunikat o błędzie to „Ilość jest nieprawidłowa.</span><span class="sxs-lookup"><span data-stu-id="c1596-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="c1596-135">Oczekiwane %1 %2."</span><span class="sxs-lookup"><span data-stu-id="c1596-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="c1596-136">W dyrektywach lokalizacji dotyczących pracy nad zamówieniem sprzedaży, opcja wielu jednostek SKU nie ocenia wielu akcji dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c1596-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-137">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-137">Issue description</span></span>

<span data-ttu-id="c1596-138">Dyrektywy lokalizacji typu zlecenia pracy *Zamówienia sprzedaży* i typu pracy *Odłożenie* nie oceniają wielu działań dyrektywy lokalizacji, gdy wybrana jest opcja **Wiele jednostek SKU**.</span><span class="sxs-lookup"><span data-stu-id="c1596-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="c1596-139">Sprawdzana jest tylko akcja dyrektywy pierwszej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c1596-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-140">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-140">Issue resolution</span></span>

<span data-ttu-id="c1596-141">Nowa funkcja *Oceń wszystkie akcje dla dyrektyw lokalizacji dla wielu jednostek SKU* została dodana w wersji 10.0.15 (zobacz [4579866 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="c1596-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="c1596-142">Ta funkcja ocenia wszystkie akcje dyrektyw lokalizacji w wielu jednostkach SKU.</span><span class="sxs-lookup"><span data-stu-id="c1596-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="c1596-143">Jeśli ta funkcja jest wymagana, należy skorzystać [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby ją włączyć.</span><span class="sxs-lookup"><span data-stu-id="c1596-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="c1596-144">Nie mogę skorzystać z aplikacji magazynowej, aby przeprowadzić pobieranie częściowe.</span><span class="sxs-lookup"><span data-stu-id="c1596-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-145">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-145">Issue description</span></span>

<span data-ttu-id="c1596-146">W przypadku zamówień sprzedaży i przeniesienia nie można pomijać towarów ani wykonać pobrania częściowego.</span><span class="sxs-lookup"><span data-stu-id="c1596-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-147">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-147">Issue resolution</span></span>

<span data-ttu-id="c1596-148">Na stronie **Elementy menu urządzenia przenośnego** dla każdego elementu menu skonfigurowanego do przetwarzania zamówień sprzedaży lub zamówień przeniesienia ustaw opcję **Zezwalaj na dzielenie pracy** na skróconej karcie **Ogólne** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="c1596-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="c1596-149">Jak mogę wykonać zmianę stanu zapasów dla części pracy dotyczącej ilości częściowej?</span><span class="sxs-lookup"><span data-stu-id="c1596-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="c1596-150">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c1596-150">Issue description</span></span>

<span data-ttu-id="c1596-151">Konieczna jest zmiana stanu zapasów dla częściowej ilości partii.</span><span class="sxs-lookup"><span data-stu-id="c1596-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c1596-152">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c1596-152">Issue resolution</span></span>

<span data-ttu-id="c1596-153">Aby umożliwić pracownikom wprowadzenie tej zmiany, można utworzyć element menu dla aplikacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="c1596-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="c1596-154">Na stronie **Elementy menu urządzenia przenośnego** utwórz (lub edytuj) element menu, który ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="c1596-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="c1596-155">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="c1596-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="c1596-156">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="c1596-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="c1596-157">**Proces tworzenia pracy:** *Przesunięcie*</span><span class="sxs-lookup"><span data-stu-id="c1596-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="c1596-158">**Wyświetl kolumnę Stan zapasów:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="c1596-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="c1596-159">W razie konieczności można skonfigurować inne pola na stronie.</span><span class="sxs-lookup"><span data-stu-id="c1596-159">You can set other fields on the page as you require.</span></span>
