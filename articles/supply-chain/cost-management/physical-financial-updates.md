---
title: Aktualizacje fizyczne i finansowe
description: W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b29c1c0727487992a478552d94b5bbe8684d0550
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967465"
---
# <a name="physical-and-financial-updates"></a><span data-ttu-id="c92a9-103">Aktualizacje fizyczne i finansowe</span><span class="sxs-lookup"><span data-stu-id="c92a9-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c92a9-104">W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów.</span><span class="sxs-lookup"><span data-stu-id="c92a9-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="c92a9-105">W Dynamics 365 Supply Chain Management transakcje magazynowe można zaktualizowane fizycznie i finansowo.</span><span class="sxs-lookup"><span data-stu-id="c92a9-105">Inventory transactions can be physically updated and financially updated in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c92a9-106">Niektóre typy transakcji fizycznych i finansowych zwiększają ilości zapasów, podczas gdy inne je zmniejszają.</span><span class="sxs-lookup"><span data-stu-id="c92a9-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="c92a9-107">Wzrost fizyczny</span><span class="sxs-lookup"><span data-stu-id="c92a9-107">Physical increases</span></span>
<span data-ttu-id="c92a9-108">Po zaksięgowaniu transakcji fizycznej stan tej transakcji przyjmuje wartość **Otrzymano**.</span><span class="sxs-lookup"><span data-stu-id="c92a9-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="c92a9-109">Oto transakcje, które stanowią wzrost fizyczny:</span><span class="sxs-lookup"><span data-stu-id="c92a9-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="c92a9-110">zamówienie zakupu — przychód,</span><span class="sxs-lookup"><span data-stu-id="c92a9-110">Purchase order receipt</span></span>
-   <span data-ttu-id="c92a9-111">zwrot dokumentu dostawy zamówienia sprzedaży,</span><span class="sxs-lookup"><span data-stu-id="c92a9-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="c92a9-112">Zgłaszanie zlecenia produkcyjnego jako zakończonego</span><span class="sxs-lookup"><span data-stu-id="c92a9-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="c92a9-113">według produktów na liście pobrania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="c92a9-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="c92a9-114">Wzrost finansowy</span><span class="sxs-lookup"><span data-stu-id="c92a9-114">Financial increases</span></span>
<span data-ttu-id="c92a9-115">Po zaksięgowaniu finansowej transakcji przychodu stan rekordu tej transakcji powodującej zwiększenie ilości przyjmuje wartość **Zakupiono**.</span><span class="sxs-lookup"><span data-stu-id="c92a9-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="c92a9-116">Oto transakcje, które stanowią wzrost finansowy:</span><span class="sxs-lookup"><span data-stu-id="c92a9-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="c92a9-117">Faktura dostawcy</span><span class="sxs-lookup"><span data-stu-id="c92a9-117">Vendor invoice</span></span>
-   <span data-ttu-id="c92a9-118">faktura zamówienia zakupu do zwrotu,</span><span class="sxs-lookup"><span data-stu-id="c92a9-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="c92a9-119">wycena zlecenia produkcyjnego,</span><span class="sxs-lookup"><span data-stu-id="c92a9-119">Production order costing</span></span>
-   <span data-ttu-id="c92a9-120">Arkusze magazynowe z ilością dodatnią, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="c92a9-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="c92a9-121">Transakcje, które zwiększają ilość</span><span class="sxs-lookup"><span data-stu-id="c92a9-121">Transactions that increase quantity</span></span>
<span data-ttu-id="c92a9-122">Transakcje zwiększające ilość są księgowane według dynamicznych średnich kosztów własnych.</span><span class="sxs-lookup"><span data-stu-id="c92a9-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="c92a9-123">Po zaksięgowaniu transakcji zwiększających ilość obliczone dynamiczne średnie koszty własne na podstawie tych wszystkich transakcji dla każdego wymiaru magazynowego podlegającego śledzeniu finansowemu.</span><span class="sxs-lookup"><span data-stu-id="c92a9-123">The calculated running average cost price is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="c92a9-124">Aby uzyskać informacje o uruchamianiu średnich kosztów własnych, zobacz [Dynamiczne średnie koszty własne](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="c92a9-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="c92a9-125">Transakcje, które zmniejszają ilość</span><span class="sxs-lookup"><span data-stu-id="c92a9-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="c92a9-126">Obliczone dynamiczne średne koszty są używane podczas księgowania transakcji, która zmniejsza ilość, niezależnie od tego, który model magazynu jest powiązany z danym magazynem.</span><span class="sxs-lookup"><span data-stu-id="c92a9-126">The calculated running average cost price is used  when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="c92a9-127">Wymaga to, aby transakcja, która zmniejsza ilość nie została wcześniej oznaczona dla innej transakcji przed zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="c92a9-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="c92a9-128">Jeśli fizyczny stan dostępnych zapasów uzyskuje wartość ujemną, jest używany koszt magazynowy zdefiniowany dla towaru na stronie **Pozycja**.</span><span class="sxs-lookup"><span data-stu-id="c92a9-128">If the physical on-hand inventory becomes negative, the inventory cost that is defined for the item on the **Item** page is used.</span></span> 

> [!NOTE]
> <span data-ttu-id="c92a9-129">Jeśli włączono funkcję wielooddziałowości, to koszt ten będzie zastępczo używany jako koszt magazynowy, zdefiniowany dla oddziału na stronie **Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="c92a9-129">If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="c92a9-130">Rozchody fizyczne a finansowe</span><span class="sxs-lookup"><span data-stu-id="c92a9-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="c92a9-131">Po zaksięgowaniu transakcji fizycznego rozchodu stan rekordu transakcji przyjmuje wartość **Zmniejszono**.</span><span class="sxs-lookup"><span data-stu-id="c92a9-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="c92a9-132">Oto transakcje stanowiące fizyczne rozchody:</span><span class="sxs-lookup"><span data-stu-id="c92a9-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="c92a9-133">arkusz listy pobrań zlecenia produkcyjnego,</span><span class="sxs-lookup"><span data-stu-id="c92a9-133">Production order picking list journal</span></span>
-   <span data-ttu-id="c92a9-134">dokument dostawy zamówienia sprzedaży,</span><span class="sxs-lookup"><span data-stu-id="c92a9-134">Sales order packing slip</span></span>
-   <span data-ttu-id="c92a9-135">zwrot dokumentu dostawy zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="c92a9-135">Purchase order packing slip return</span></span>

<span data-ttu-id="c92a9-136">Po zaksięgowaniu transakcji finansowej stan rekordu tej transakcji przyjmuje wartość **Sprzedano**.</span><span class="sxs-lookup"><span data-stu-id="c92a9-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="c92a9-137">Oto transakcje stanowiące finansowe rozchody:</span><span class="sxs-lookup"><span data-stu-id="c92a9-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="c92a9-138">Kończenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="c92a9-138">Ending a production order</span></span>
-   <span data-ttu-id="c92a9-139">Faktura dla zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c92a9-139">Sales order invoice</span></span>
-   <span data-ttu-id="c92a9-140">Zwrot z faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="c92a9-140">Vendor invoice return</span></span>
-   <span data-ttu-id="c92a9-141">Arkusze magazynowe z ilością ujemną, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="c92a9-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="c92a9-142">Transakcje zmniejszające ilość są księgowane według dynamicznych średnich kosztów własnych.</span><span class="sxs-lookup"><span data-stu-id="c92a9-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="c92a9-143">Z tego powodu proces zamknięcia magazynu jest wymagany w celu rozliczenia transakcji rozchodu z transakcjami przychodu, według modelu magazynu przypisanego dla danego towaru.</span><span class="sxs-lookup"><span data-stu-id="c92a9-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>
