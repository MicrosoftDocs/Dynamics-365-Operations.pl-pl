---
title: Przy anulowaniu zamówienia sprzedaży nie można zmniejszyć ilości
description: Przy anulowaniu zamówienia sprzedaży nie można zmniejszyć ilości.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230843"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="71077-103">Przy anulowaniu zamówienia sprzedaży nie można zmniejszyć ilości</span><span class="sxs-lookup"><span data-stu-id="71077-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="71077-104">Kod błędu: SYS138831</span><span class="sxs-lookup"><span data-stu-id="71077-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="71077-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="71077-105">Symptoms</span></span>

<span data-ttu-id="71077-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="71077-106">The system shows the following error message:</span></span>

> <span data-ttu-id="71077-107">Nie można zmniejszyć ilości.</span><span class="sxs-lookup"><span data-stu-id="71077-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="71077-108">Liczba transakcji inwentaryzacyjnych w zamówieniu jest zbyt mała, ponieważ ilość lub jej część jest odniesiona do zlecenia wyjściowego lub produkcyjnego lub jest oznaczona w stosunku do innych transakcji.</span><span class="sxs-lookup"><span data-stu-id="71077-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="71077-109">Powód</span><span class="sxs-lookup"><span data-stu-id="71077-109">Cause</span></span>

<span data-ttu-id="71077-110">Jeśli praca jest skojarzona z zamówieniem sprzedaży, nie można anulować zamówienia sprzedaży, dopóki praca nie zostanie anulowana i wycofana.</span><span class="sxs-lookup"><span data-stu-id="71077-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="71077-111">To wymaganie ma zastosowanie nawet wtedy, gdy praca skojarzona z zamówieniem sprzedaży jest zamknięta.</span><span class="sxs-lookup"><span data-stu-id="71077-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="71077-112">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="71077-112">Resolution</span></span>

<span data-ttu-id="71077-113">Aby naprawić ten problem, wykonaj jedno z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="71077-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="71077-114">Anuluj otwartą pracę.</span><span class="sxs-lookup"><span data-stu-id="71077-114">Cancel open work.</span></span>
1. <span data-ttu-id="71077-115">Usuń ładunek.</span><span class="sxs-lookup"><span data-stu-id="71077-115">Delete the load.</span></span>
1. <span data-ttu-id="71077-116">Zmniejsz ilość pobraną.</span><span class="sxs-lookup"><span data-stu-id="71077-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="71077-117">Anuluj otwartą pracę</span><span class="sxs-lookup"><span data-stu-id="71077-117">Cancel open work</span></span>

<span data-ttu-id="71077-118">Aby anulować otwartą pracę, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="71077-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="71077-119">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="71077-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="71077-120">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować, a obecnie ma wartość pola **Stan pracy** *Otwarta*, *W toku*, *Anulowana*, *Połączona* lub *Zamknięta*.</span><span class="sxs-lookup"><span data-stu-id="71077-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="71077-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="71077-121">Select **OK**.</span></span>
1. <span data-ttu-id="71077-122">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="71077-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="71077-123">Usuń ładunek</span><span class="sxs-lookup"><span data-stu-id="71077-123">Delete the load</span></span>

<span data-ttu-id="71077-124">Aby usunąć ładunek, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="71077-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="71077-125">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="71077-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71077-126">Otwórz odnośne zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="71077-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="71077-127">W skróconej karcie **Wiesze zamówień sprzedaży**, wybierz opcję **Magazyn \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="71077-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="71077-128">Na stronie **Praca**, w okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Anulowanie pracy**.</span><span class="sxs-lookup"><span data-stu-id="71077-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="71077-129">Potwierdź, że pole **Stan pracy** ma wartość *Anulowana*.</span><span class="sxs-lookup"><span data-stu-id="71077-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="71077-130">Zamknij stronę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="71077-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="71077-131">Na stronie szczegółów zamówienia sprzedaży, na skróconej karcie **wiersze zamówienia sprzedaży** zaznacz szczegóły dotyczące **Magazynu \> szegółów ładunku**.</span><span class="sxs-lookup"><span data-stu-id="71077-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="71077-132">W okienku akcji wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="71077-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="71077-133">Zaznacz **Tak**, aby potwierdzić, że chcesz usunąć ładunek.</span><span class="sxs-lookup"><span data-stu-id="71077-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="71077-134">Zamknij stronę **ładunek**.</span><span class="sxs-lookup"><span data-stu-id="71077-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="71077-135">Zmniejsz ilość pobraną</span><span class="sxs-lookup"><span data-stu-id="71077-135">Reduce the picked quantity</span></span>

<span data-ttu-id="71077-136">Po anulowaniu całej pracy należy wykonać następujące kroki, aby zmniejszyć ilość pobrań.</span><span class="sxs-lookup"><span data-stu-id="71077-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="71077-137">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="71077-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71077-138">Otwórz odnośne zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="71077-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="71077-139">Na skróconej karcie **Wiersze zamówienia sprzedaży** zaznacz pozycję **Aktualizuj wiersz \> Pobieranie** na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="71077-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="71077-140">Na stronie **Pobrania** w sekcji **Transakcje** wybierz wiersz, w którym w polu **Stan wydania** ustawiono wartość *Pobrano*.</span><span class="sxs-lookup"><span data-stu-id="71077-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="71077-141">W sekcji **Transakcje** wybierz pozycję **Dodaj wiersz pobrania** z paska narzędzi.</span><span class="sxs-lookup"><span data-stu-id="71077-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="71077-142">W sekcji **Wiersze pobrania** wybierz pozycję **Potwierdź pobranie wszystkiego** z paska narzędzi.</span><span class="sxs-lookup"><span data-stu-id="71077-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="71077-143">Zamknij stronę **Pobieranie**.</span><span class="sxs-lookup"><span data-stu-id="71077-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="71077-144">Na stronie szczegółów zamówienia sprzedaży w okienku akcji na karcie **Zamówienie sprzedaży** w grupie **Utrzymanie** wybierz **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="71077-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="71077-145">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować zmówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="71077-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>
