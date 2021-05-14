---
title: Zlecenia kwarantanny
description: W tym temacie opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956189"
---
# <a name="quarantine-orders"></a><span data-ttu-id="f4b54-103">Zlecenia kwarantanny</span><span class="sxs-lookup"><span data-stu-id="f4b54-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4b54-104">W tym temacie opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="f4b54-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="f4b54-105">Zlecenia kwarantanny pozwalają zablokować zapasy.</span><span class="sxs-lookup"><span data-stu-id="f4b54-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="f4b54-106">Na przykład można poddać kwarantannie towary ze względów kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="f4b54-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="f4b54-107">Zapasy poddane kwarantannie są przenoszone do magazynu kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="f4b54-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="f4b54-108">Jeśli używasz zaawansowanych procesów zarządzania magazynem (dostępnych w module Zarządzanie magazynem), przetwarzanie zleceń kwarantanny jest używane tylko do zamówień sprzedaży na zwrot.</span><span class="sxs-lookup"><span data-stu-id="f4b54-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="f4b54-109">Dostępne pozycje magazynowe w kwarantannie</span><span class="sxs-lookup"><span data-stu-id="f4b54-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="f4b54-110">W celu poddania towarów kwarantannie można ręcznie tworzyć zlecenia kwarantanny lub skonfigurować system, aby tworzył je automatycznie podczas przetwarzania dostaw przychodzących.</span><span class="sxs-lookup"><span data-stu-id="f4b54-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="f4b54-111">Aby skonfigurować system do automatycznego generowania zleceń kwarantanny, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f4b54-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="f4b54-112">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zapasy \> Grupy modeli pozycji**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="f4b54-113">Wybierz odpowiednią grupę modeli w okienku listy lub utwórz nową grupę modeli.</span><span class="sxs-lookup"><span data-stu-id="f4b54-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="f4b54-114">Na skróconej karcie **Zasady zapasów** zaznacz pole wyboru **Zarządzanie kwarantanną**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="f4b54-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f4b54-115">Close the page.</span></span>
1. <span data-ttu-id="f4b54-116">W polu **Magazyn kwarantanny** przyjmujących magazynów określ domyślny magazyn kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="f4b54-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="f4b54-117">Jeśli towar zarejestrowany jako przyjęty w magazynie należy do grupy modeli, w której jest zaznaczone pole wyboru **Zarządzanie kwarantanną**, system wygeneruje dla niego zlecenie kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="f4b54-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="f4b54-118">Zlecenie kwarantanny poleca pracownikom, aby przenieśli towar do magazynu kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="f4b54-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="f4b54-119">Podczas ręcznego tworzenia zleceń kwarantanny na stronie **Zlecenia kwarantanny** towar nie musi być skonfigurowany dla zarządzania kwarantanną w powiązanej grupie modeli pozycji.</span><span class="sxs-lookup"><span data-stu-id="f4b54-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="f4b54-120">W przypadku tego procesu należy określić dostępne zapasy wymagające kwarantanny oraz magazyn kwarantanny, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="f4b54-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="f4b54-121">Pomocą w planowaniu tego procesu mogą być stany zleceń kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="f4b54-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="f4b54-122">Stany zleceń kwarantanny</span><span class="sxs-lookup"><span data-stu-id="f4b54-122">Quarantine order statuses</span></span>

<span data-ttu-id="f4b54-123">Zlecenia kwarantanny mogą mieć następujące stany:</span><span class="sxs-lookup"><span data-stu-id="f4b54-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="f4b54-124">Utworzony</span><span class="sxs-lookup"><span data-stu-id="f4b54-124">Created</span></span>
- <span data-ttu-id="f4b54-125">Rozpoczęta</span><span class="sxs-lookup"><span data-stu-id="f4b54-125">Started</span></span>
- <span data-ttu-id="f4b54-126">Zgłoszone jako gotowe</span><span class="sxs-lookup"><span data-stu-id="f4b54-126">Reported as finished</span></span>
- <span data-ttu-id="f4b54-127">Zakończono</span><span class="sxs-lookup"><span data-stu-id="f4b54-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="f4b54-128">Utworzony</span><span class="sxs-lookup"><span data-stu-id="f4b54-128">Created</span></span>

<span data-ttu-id="f4b54-129">Gdy zlecenie kwarantanny zostało utworzone ręcznie, ale towar nie został jeszcze umieszczony w magazynie kwarantanny, zlecenie otrzymuje stan **Utworzone**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="f4b54-130">Generowane są dwie transakcje magazynowe.</span><span class="sxs-lookup"><span data-stu-id="f4b54-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="f4b54-131">Jedna to transakcja wydania, która może mieć stan **Zamówione**, **Fizycznie zarezerwowane** lub **Pobrane**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="f4b54-132">Druga to transakcja przyjęcia w magazynie kwarantanny, która może stan **Zamówione** lub **Zarejestrowane**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="f4b54-133">Aktualizacje zapasów można rezerwować, pobierać i rejestrować za pomocą zwykłych procesów.</span><span class="sxs-lookup"><span data-stu-id="f4b54-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="f4b54-134">Rozpoczęta</span><span class="sxs-lookup"><span data-stu-id="f4b54-134">Started</span></span>

<span data-ttu-id="f4b54-135">Gdy zlecenie kwarantanny ma stan **Rozpoczęte**, zapasy są przenoszone ze zwykłego magazynu do magazynu kwarantanny i następuje utworzenie dwóch transakcji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="f4b54-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="f4b54-136">Jedna transakcja ma stan **Wydane**, a druga ma stan **Otrzymane**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="f4b54-137">Jednocześnie tworzone są dwie transakcje magazynowe w celu realizacji przeniesienia zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="f4b54-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="f4b54-138">Te transakcje nie mają dat.</span><span class="sxs-lookup"><span data-stu-id="f4b54-138">These transactions aren't dated.</span></span> <span data-ttu-id="f4b54-139">Jedna transakcja ma stan **Fizycznie zarezerwowane**, a druga ma stan **Zamówione**.</span><span class="sxs-lookup"><span data-stu-id="f4b54-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="f4b54-140">Zgłoszone jako gotowe</span><span class="sxs-lookup"><span data-stu-id="f4b54-140">Reported as finished</span></span>

<span data-ttu-id="f4b54-141">Aby zgłosić rozpoczęte zlecenie kwarantanny jako zakończone, otwórz zamówienie i wybierz opcję **Gotowe** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="f4b54-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="f4b54-142">Towar jest zwalniany z kwarantanny, ale nie jest jeszcze przenoszony z powrotem do zwykłego magazynu.</span><span class="sxs-lookup"><span data-stu-id="f4b54-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="f4b54-143">Przesunięcie z powrotem do zwykłego magazynu można zrealizować za pomocą arkusza przyjęcia towaru, który można zainicjować w trakcie procesu zgłaszania gotowości.</span><span class="sxs-lookup"><span data-stu-id="f4b54-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="f4b54-144">Zakończone</span><span class="sxs-lookup"><span data-stu-id="f4b54-144">Ended</span></span>

<span data-ttu-id="f4b54-145">Po zakończeniu zlecenia kwarantanny towar jest przenoszony z magazynu kwarantanny z powrotem do zwykłego magazynu.</span><span class="sxs-lookup"><span data-stu-id="f4b54-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="f4b54-146">Transakcja towaru otrzymuje stan *Sprzedane* w magazynie kwarantanny i *Zakupione* w magazynie zwykłym.</span><span class="sxs-lookup"><span data-stu-id="f4b54-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="f4b54-147">Odpadki zamówienia kwarantanny</span><span class="sxs-lookup"><span data-stu-id="f4b54-147">Quarantine order scrap</span></span>

<span data-ttu-id="f4b54-148">W ramach procesu zlecenia kwarantanny można przekazać zapasy do likwidacji.</span><span class="sxs-lookup"><span data-stu-id="f4b54-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="f4b54-149">Podczas przetwarzania odpadków stan zapasów zostanie ustawiony na *Sprzedane* przez transakcję wydania z magazynu kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="f4b54-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4b54-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f4b54-150">Additional resources</span></span>

- [<span data-ttu-id="f4b54-151">Blokowanie zapasów</span><span class="sxs-lookup"><span data-stu-id="f4b54-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
