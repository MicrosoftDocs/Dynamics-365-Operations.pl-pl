---
title: Zlecenia kwarantanny
description: "W tym temacie opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 523e51c705d76b6e8624887292395f8f239bcb65
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="quarantine-orders"></a><span data-ttu-id="eeb0d-103">Zlecenia kwarantanny</span><span class="sxs-lookup"><span data-stu-id="eeb0d-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eeb0d-104">W tym temacie opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-104">This topic describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="eeb0d-105">Zlecenia kwarantanny mogą służyć do blokowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="eeb0d-106">Na przykład można poddać kwarantannie towary ze względów kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="eeb0d-107">Zapasy poddane kwarantannie są przenoszone do magazynu kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="eeb0d-108">**Uwaga:** Jeśli używasz zaawansowanych procesów zarządzania magazynem (dostępnych w module Zarządzanie magazynem), przetwarzanie zleceń kwarantanny jest używane tylko do zamówień sprzedaży na zwrot.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="eeb0d-109">Dostępne pozycje magazynowe w kwarantannie</span><span class="sxs-lookup"><span data-stu-id="eeb0d-109">Quarantine on-hand inventory items</span></span>
<span data-ttu-id="eeb0d-110">W celu poddania towarów kwarantannie można ręcznie tworzyć zlecenia kwarantanny lub skonfigurować system, aby tworzył zlecenia kwarantanny automatycznie podczas przetwarzania dostaw przychodzących.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="eeb0d-111">Aby automatycznie tworzyć zlecenia kwarantanny, zaznacz opcję **Zarządzanie kwarantanną** na karcie **Zasady zapasów** na stronie **Grupy modeli pozycji**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="eeb0d-112">Należy także w magazynach przyjmujących określić domyślny magazyn kwarantanny w polu **Magazyn kwarantanny**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="eeb0d-113">Gdy zapasy fizycznie dostępne są rejestrowane w zamówieniu zakupu lub zleceniu produkcyjnym, towary poddane kwarantannie są automatycznie przenoszone do magazynu kwarantanny w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="eeb0d-114">To przesunięcie następuje, ponieważ stan zlecenia kwarantanny zmienił się na **Rozpoczęte**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="eeb0d-115">Podczas ręcznego tworzenia zleceń kwarantanny towar nie musi być skonfigurowany dla zarządzania kwarantanną w powiązanej grupie modeli towarów.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="eeb0d-116">W przypadku tego procesu należy określić dostępne zapasy wymagające kwarantanny oraz magazyn kwarantanny, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="eeb0d-117">Pomocą w planowaniu tego procesu mogą być stany zleceń kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="eeb0d-118">Stany zleceń kwarantanny</span><span class="sxs-lookup"><span data-stu-id="eeb0d-118">Quarantine order statuses</span></span>
<span data-ttu-id="eeb0d-119">Zlecenia kwarantanny mogą mieć następujące stany:</span><span class="sxs-lookup"><span data-stu-id="eeb0d-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="eeb0d-120">Utworzony</span><span class="sxs-lookup"><span data-stu-id="eeb0d-120">Created</span></span>
-   <span data-ttu-id="eeb0d-121">Rozpoczęta</span><span class="sxs-lookup"><span data-stu-id="eeb0d-121">Started</span></span>
-   <span data-ttu-id="eeb0d-122">Zgłoszone jako gotowe</span><span class="sxs-lookup"><span data-stu-id="eeb0d-122">Reported as finished</span></span>
-   <span data-ttu-id="eeb0d-123">Zakończono</span><span class="sxs-lookup"><span data-stu-id="eeb0d-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="eeb0d-124">Utworzony</span><span class="sxs-lookup"><span data-stu-id="eeb0d-124">Created</span></span>

<span data-ttu-id="eeb0d-125">Gdy zlecenie kwarantanny zostało utworzone ręcznie, ale towar nie został jeszcze umieszczony w magazynie kwarantanny, zlecenie otrzymuje stan **Utworzone**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="eeb0d-126">Generowane są dwie transakcje magazynowe.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="eeb0d-127">Jedna to transakcja wydania, która może mieć stan **Zamówione**, **Fizycznie zarezerwowane** lub **Pobrane**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="eeb0d-128">Druga to transakcja przyjęcia w magazynie kwarantanny, która może stan **Zamówione** lub **Zarejestrowane**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="eeb0d-129">Aktualizacje zapasów można rezerwować, pobierać i rejestrować za pomocą zwykłych procesów.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="eeb0d-130">Rozpoczęta</span><span class="sxs-lookup"><span data-stu-id="eeb0d-130">Started</span></span>

<span data-ttu-id="eeb0d-131">Gdy zlecenie kwarantanny ma stan **Rozpoczęte**, zapasy są przenoszone ze zwykłego magazynu do magazynu kwarantanny i następuje utworzenie dwóch transakcji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="eeb0d-132">Jedna transakcja ma stan **Wydane**, a druga ma stan **Otrzymane**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="eeb0d-133">Jednocześnie tworzone są dwie transakcje magazynowe w celu realizacji przeniesienia zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="eeb0d-134">Te transakcje nie mają dat.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-134">These transactions aren't dated.</span></span> <span data-ttu-id="eeb0d-135">Jedna transakcja ma stan **Fizycznie zarezerwowane**, a druga ma stan **Zamówione**.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="eeb0d-136">Zgłoszone jako gotowe</span><span class="sxs-lookup"><span data-stu-id="eeb0d-136">Reported as finished</span></span>

<span data-ttu-id="eeb0d-137">Kliknięcie opcji **Zgłoszenie wyrobów gotowych** umożliwia zgłoszenie rozpoczętego zlecenia kwarantanny jako gotowego.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="eeb0d-138">Towar jest zwalniany z kwarantanny, ale nie jest jeszcze przenoszony z powrotem do zwykłego magazynu.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="eeb0d-139">Przesunięcie z powrotem do zwykłego magazynu można zrealizować za pomocą arkusza przyjęcia towaru, który można zainicjować w trakcie procesu zgłaszania wyrobów gotowych.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-139">The movement back to the regular warehouse can be processed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="eeb0d-140">Zakończono</span><span class="sxs-lookup"><span data-stu-id="eeb0d-140">Ended</span></span>

<span data-ttu-id="eeb0d-141">Po zakończeniu zlecenia kwarantanny towar jest przenoszony z magazynu kwarantanny z powrotem do zwykłego magazynu.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="eeb0d-142">Transakcja towaru otrzymuje stan **Sprzedane** w magazynie kwarantanny i **Zakupione** w magazynie zwykłym.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="eeb0d-143">Odpadki zamówienia kwarantanny</span><span class="sxs-lookup"><span data-stu-id="eeb0d-143">Quarantine order scrap</span></span>
<span data-ttu-id="eeb0d-144">W ramach procesu zlecenia kwarantanny można przekazać zapasy do likwidacji.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="eeb0d-145">Podczas przetwarzania odpadków stan zapasów zostanie ustawiony na **Sprzedane** przez transakcję wydania z magazynu kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="eeb0d-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="additional-resources"></a><span data-ttu-id="eeb0d-146">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="eeb0d-146">Additional resources</span></span>
--------

[<span data-ttu-id="eeb0d-147">Blokowanie zapasów</span><span class="sxs-lookup"><span data-stu-id="eeb0d-147">Inventory blocking</span></span>](inventory-blocking.md)

