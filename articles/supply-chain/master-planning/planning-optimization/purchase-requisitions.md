---
title: Zapotrzebowania na zakup
description: W tym temacie opisano sposób, w jaki zapotrzebowania na zakup są obsługiwane w optymalizacji planowania.
author: ChristianRytt
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 564f87fe78e79107feb103f953ed4769e4734aa1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808047"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="d64c5-103">Zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="d64c5-103">Purchase requisitions</span></span>

<span data-ttu-id="d64c5-104">Planowanie główne może uzupełniać zapasy dla zatwierdzonych zapotrzebowań na zakup.</span><span class="sxs-lookup"><span data-stu-id="d64c5-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="d64c5-105">Dlatego aby pokryć zapotrzebowania na zakup, użytkownicy nie muszą używać przepływu pracy do tworzenia zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="d64c5-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="d64c5-106">Zapotrzebowania na zakup mogą być natomiast pokrywane przez planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="d64c5-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="d64c5-107">Dzięki tej funkcji zapotrzebowania na zakup mogą tworzyć zamówienia zakupu, zamówienia przeniesienia lub zlecenia produkcyjne, w zależności od wartości **typu planowanego zamówienia** ustawionej dla powiązanego produktu.</span><span class="sxs-lookup"><span data-stu-id="d64c5-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="d64c5-108">Włączanie planów głównych z uwzględnieniem zapotrzebowań</span><span class="sxs-lookup"><span data-stu-id="d64c5-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="d64c5-109">Aby uwzględnić zapotrzebowania podczas obliczania zapotrzebowania dla planu głównego, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d64c5-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="d64c5-110">Przejdź do obszaru **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne**.</span><span class="sxs-lookup"><span data-stu-id="d64c5-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="d64c5-111">Utwórz lub wybierz plan główny.</span><span class="sxs-lookup"><span data-stu-id="d64c5-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="d64c5-112">Na skróconej karcie **Ogólne** ustaw opcję **Uwzględnij zapotrzebowania** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="d64c5-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="d64c5-113">Powtórz kroki 2 i 3 dla każdego dodatkowego planu głównego, w którym chcesz uwzględnić zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d64c5-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="d64c5-114">Zatwierdzony horyzont czasowy zapotrzebowań</span><span class="sxs-lookup"><span data-stu-id="d64c5-114">Approved requisitions time fence</span></span>

<span data-ttu-id="d64c5-115">*Zatwierdzony horyzont czasowy zapotrzebowań* określa, jak daleko wstecz (w dniach) plan główny będzie uwzględniał popyt z zatwierdzonych zapotrzebowań uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="d64c5-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="d64c5-116">Można ustawić zatwierdzony horyzont czasowy zapotrzebowania zarówno na poziomie grupy zapotrzebowania, jak i na poziomie planu głównego.</span><span class="sxs-lookup"><span data-stu-id="d64c5-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="d64c5-117">Ustawianie horyzontu czasowego zatwierdzonych zapotrzebowań dla grupy zapotrzebowań</span><span class="sxs-lookup"><span data-stu-id="d64c5-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="d64c5-118">Przejdź do menu **Planowanie główne** \> **Konfiguracja** \> **Zapotrzebowanie** \> **Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="d64c5-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**.</span></span>
1. <span data-ttu-id="d64c5-119">Utwórz lub wybierz grupę zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d64c5-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="d64c5-120">Na skróconej karcie **Inne** ustaw w polu **Horyzont czasowy zatwierdzonych zapotrzebowań (dni)** liczbę dni, która ma zostać w nim uwzględniona.</span><span class="sxs-lookup"><span data-stu-id="d64c5-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="d64c5-121">Powtórz kroki 2 i 3 dla każdej dodatkowej grupy zapotrzebowania, w której chcesz ustawić horyzont czasowy zatwierdzonych zapotrzebowań.</span><span class="sxs-lookup"><span data-stu-id="d64c5-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="d64c5-122">Ustawianie horyzontu czasowego zatwierdzonych zapotrzebowań dla indywidualnych planów głównych</span><span class="sxs-lookup"><span data-stu-id="d64c5-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="d64c5-123">Po ustawieniu horyzontu czasowego zatwierdzonych zapotrzebowań dla pojedynczego planu głównego to ustawienie zastępuje ustawienie horyzontu czasowego dla dowolnej właściwej grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d64c5-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="d64c5-124">Przejdź do obszaru **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne**.</span><span class="sxs-lookup"><span data-stu-id="d64c5-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="d64c5-125">Utwórz lub wybierz plan główny.</span><span class="sxs-lookup"><span data-stu-id="d64c5-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="d64c5-126">Na skróconej karcie **Horyzonty czasowe w dniach** ustaw w polu **Horyzont czasowy zatwierdzonych zapotrzebowań (dni)** liczbę dni, która ma zostać w nim uwzględniona.</span><span class="sxs-lookup"><span data-stu-id="d64c5-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="d64c5-127">Powtórz kroki 2 i 3 dla każdego dodatkowego planu głównego, w której chcesz ustawić horyzont czasowy zatwierdzonych zapotrzebowań.</span><span class="sxs-lookup"><span data-stu-id="d64c5-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d64c5-128">**Dostępne wkrótce:** horyzonty czasowe zatwierdzonych zapotrzebowań nie są jeszcze obsługiwane podczas optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="d64c5-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="d64c5-129">Dopóki nie będą one obsługiwane, wszystkie wartości podane w polu **Horyzonty czasowe zatwierdzonych zapotrzebowań (dni)** będą ignorowane.</span><span class="sxs-lookup"><span data-stu-id="d64c5-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="d64c5-130">Niezależne zaopatrzenie, niezależnie od kodu zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="d64c5-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="d64c5-131">Zapotrzebowania na zakup są zawsze pokrywane przez niezależne zamówienia planowane, niezależnie od kodu zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d64c5-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="d64c5-132">Takie działanie zapewnia czytelną możliwość śledzenia i przepływów pracy między zapotrzebowaniami na zakupu i zamówieniami uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="d64c5-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="d64c5-133">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="d64c5-133">Example 1</span></span>

<span data-ttu-id="d64c5-134">Produkt jest tak ustawiony, że ma wartość **kodu zapotrzebowania** *Minimum/maksimum*. Ma one następujące stany zapasów i zapotrzebowania:</span><span class="sxs-lookup"><span data-stu-id="d64c5-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="d64c5-135">Ilość dostępnych zapasów = 10.</span><span class="sxs-lookup"><span data-stu-id="d64c5-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="d64c5-136">Minimalna ilość zapasów = 15.</span><span class="sxs-lookup"><span data-stu-id="d64c5-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="d64c5-137">Maksymalna ilość zapasów = 20.</span><span class="sxs-lookup"><span data-stu-id="d64c5-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="d64c5-138">Istnieje zapotrzebowanie na zakup jednej sztuki.</span><span class="sxs-lookup"><span data-stu-id="d64c5-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="d64c5-139">Żądana data to data dzisiejsza.</span><span class="sxs-lookup"><span data-stu-id="d64c5-139">It has a requested date of today.</span></span>

<span data-ttu-id="d64c5-140">Podczas planowania głównego tworzone są dwa planowane zamówienia: jedno na 10 sztuk w celu uzupełnienia zapasów do maksymalnej ilości, a drugie na jedną sztukę w celu uzupełnienia zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="d64c5-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="d64c5-141">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="d64c5-141">Example 2</span></span>

<span data-ttu-id="d64c5-142">Produkt jest tak ustawiony, że ma wartość **kodu zapotrzebowania** *Minimum/maksimum*. Ma one następujące stany zapasów i zapotrzebowania:</span><span class="sxs-lookup"><span data-stu-id="d64c5-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="d64c5-143">Ilość dostępnych zapasów = 17.</span><span class="sxs-lookup"><span data-stu-id="d64c5-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="d64c5-144">Minimalna ilość zapasów = 15.</span><span class="sxs-lookup"><span data-stu-id="d64c5-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="d64c5-145">Maksymalna ilość zapasów = 20.</span><span class="sxs-lookup"><span data-stu-id="d64c5-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="d64c5-146">Istnieje zapotrzebowanie na zakup jednej sztuki.</span><span class="sxs-lookup"><span data-stu-id="d64c5-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="d64c5-147">Żądana data to data dzisiejsza.</span><span class="sxs-lookup"><span data-stu-id="d64c5-147">It has a requested date of today.</span></span>

<span data-ttu-id="d64c5-148">Podczas planowania głównego tworzone jest jedno planowane zamówienie na jedną sztukę w celu uzupełnienia zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="d64c5-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="d64c5-149">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="d64c5-149">Example 3</span></span>

<span data-ttu-id="d64c5-150">Produkt jest tak ustawiony, że ma wartość **kodu zapotrzebowania** *Okres*, a długość okresu wynosi siedem dni.</span><span class="sxs-lookup"><span data-stu-id="d64c5-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="d64c5-151">Ma on następujące stany zapasów, zamówienia sprzedaży i zapotrzebowania:</span><span class="sxs-lookup"><span data-stu-id="d64c5-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="d64c5-152">Ilość dostępnych zapasów = 0.</span><span class="sxs-lookup"><span data-stu-id="d64c5-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="d64c5-153">Istnieje zamówienie sprzedaży na pięć sztuk.</span><span class="sxs-lookup"><span data-stu-id="d64c5-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="d64c5-154">Oczekiwana data wysyłki to dzisiaj plus jeden dzień.</span><span class="sxs-lookup"><span data-stu-id="d64c5-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="d64c5-155">Istnieje zapotrzebowanie na zakup trzech sztuk.</span><span class="sxs-lookup"><span data-stu-id="d64c5-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="d64c5-156">Żądana data to data dzisiejsza plus trzy dni.</span><span class="sxs-lookup"><span data-stu-id="d64c5-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="d64c5-157">Podczas planowania głównego tworzone są dwa planowane zamówienia: jedno na trzy sztuk w celu uzupełnienia zapotrzebowania na zakup, a drugie na pięć sztuk w celu uzupełnienia popytu w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d64c5-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="d64c5-158">Po zaakceptowaniu zamówienia planowanego z oznaczoną transakcją zapotrzebowania na zakup aparat planowania przechowuje oznaczanie transakcji dla zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="d64c5-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="d64c5-159">Jeśli później dowiemy się, że w zaakceptowanym zamówieniu brakuje określonej ilości wymaganej do zrealizowania zapotrzebowania na zakup, system utworzy nowe planowane zamówienie dla tej różnicy.</span><span class="sxs-lookup"><span data-stu-id="d64c5-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="d64c5-160">Aby uzyskać dalsze informacje o zapotrzebowaniach na zakupu, zobacz [Omówienie zapotrzebowań na zakup](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d64c5-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]