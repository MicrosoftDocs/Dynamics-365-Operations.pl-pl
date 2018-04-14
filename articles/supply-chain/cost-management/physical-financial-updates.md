---
title: Aktualizacje fizyczne i finansowe
description: "W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 08a04b3c80aaac25177f92b250e8dc287ae76c28
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="physical-and-financial-updates"></a><span data-ttu-id="908df-103">Aktualizacje fizyczne i finansowe</span><span class="sxs-lookup"><span data-stu-id="908df-103">Physical and financial updates</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="908df-104">W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów.</span><span class="sxs-lookup"><span data-stu-id="908df-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="908df-105">W programie Microsoft Dynamics 365 for Finance and Operations transakcje magazynowe można zaktualizowane fizycznie i finansowo.</span><span class="sxs-lookup"><span data-stu-id="908df-105">Inventory transactions can be physically updated and financially updated in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="908df-106">Niektóre typy transakcji fizycznych i finansowych zwiększają ilości zapasów, podczas gdy inne je zmniejszają.</span><span class="sxs-lookup"><span data-stu-id="908df-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="908df-107">Wzrost fizyczny</span><span class="sxs-lookup"><span data-stu-id="908df-107">Physical increases</span></span>
<span data-ttu-id="908df-108">Po zaksięgowaniu transakcji fizycznej stan tej transakcji przyjmuje wartość **Otrzymano**.</span><span class="sxs-lookup"><span data-stu-id="908df-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="908df-109">Oto transakcje, które stanowią wzrost fizyczny:</span><span class="sxs-lookup"><span data-stu-id="908df-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="908df-110">zamówienie zakupu — przychód,</span><span class="sxs-lookup"><span data-stu-id="908df-110">Purchase order receipt</span></span>
-   <span data-ttu-id="908df-111">zwrot dokumentu dostawy zamówienia sprzedaży,</span><span class="sxs-lookup"><span data-stu-id="908df-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="908df-112">Zgłaszanie zlecenia produkcyjnego jako zakończonego</span><span class="sxs-lookup"><span data-stu-id="908df-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="908df-113">według produktów na liście pobrania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="908df-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="908df-114">Wzrost finansowy</span><span class="sxs-lookup"><span data-stu-id="908df-114">Financial increases</span></span>
<span data-ttu-id="908df-115">Po zaksięgowaniu finansowej transakcji przychodu stan rekordu tej transakcji powodującej zwiększenie ilości przyjmuje wartość **Zakupiono**.</span><span class="sxs-lookup"><span data-stu-id="908df-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="908df-116">Oto transakcje, które stanowią wzrost finansowy:</span><span class="sxs-lookup"><span data-stu-id="908df-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="908df-117">Faktura dostawcy</span><span class="sxs-lookup"><span data-stu-id="908df-117">Vendor invoice</span></span>
-   <span data-ttu-id="908df-118">faktura zamówienia zakupu do zwrotu,</span><span class="sxs-lookup"><span data-stu-id="908df-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="908df-119">wycena zlecenia produkcyjnego,</span><span class="sxs-lookup"><span data-stu-id="908df-119">Production order costing</span></span>
-   <span data-ttu-id="908df-120">Arkusze magazynowe z ilością dodatnią, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="908df-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="908df-121">Transakcje, które zwiększają ilość</span><span class="sxs-lookup"><span data-stu-id="908df-121">Transactions that increase quantity</span></span>
<span data-ttu-id="908df-122">Transakcje zwiększające ilość są księgowane według dynamicznych średnich kosztów własnych.</span><span class="sxs-lookup"><span data-stu-id="908df-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="908df-123">Po zaksięgowaniu transakcji zwiększających ilość program Finance and Operations oblicza średnią kroczącą kosztu własnego na podstawie tych wszystkich transakcji dla każdego wymiaru zapasów podlegającego śledzeniu finansowemu.</span><span class="sxs-lookup"><span data-stu-id="908df-123">Finance and Operations calculates a running average cost price that is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="908df-124">Aby uzyskać informacje o uruchamianiu średnich kosztów własnych, zobacz [Dynamiczne średnie koszty własne](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="908df-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="908df-125">Transakcje, które zmniejszają ilość</span><span class="sxs-lookup"><span data-stu-id="908df-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="908df-126">Finance and Operations używa obliczonej średniej kroczącej kosztu własnego podczas księgowania transakcji, która zmniejsza ilość, niezależnie od tego, który model zapasów jest powiązany z danymi zapasami.</span><span class="sxs-lookup"><span data-stu-id="908df-126">Finance and Operations uses the calculated running average cost price when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="908df-127">Wymaga to, aby transakcja, która zmniejsza ilość nie została wcześniej oznaczona dla innej transakcji przed zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="908df-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="908df-128">Jeśli fizycznie dostępne zapasy osiągną ilość ujemną, w programie Finance and Operations jest używany koszt zapasów zdefiniowany dla towaru na stronie **Pozycja**.</span><span class="sxs-lookup"><span data-stu-id="908df-128">If the physical on-hand inventory becomes negative, Finance and Operations uses the inventory cost that is defined for the item on the **Item** page.</span></span> <span data-ttu-id="908df-129">**Uwaga:** Jeśli włączono funkcję wielooddziałowości, to koszt ten będzie zastępczo używany jako koszt magazynowy, zdefiniowany dla oddziału na stronie **Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="908df-129">**Note:** If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="908df-130">Rozchody fizyczne a finansowe</span><span class="sxs-lookup"><span data-stu-id="908df-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="908df-131">Po zaksięgowaniu transakcji fizycznego rozchodu stan rekordu transakcji przyjmuje wartość **Zmniejszono**.</span><span class="sxs-lookup"><span data-stu-id="908df-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="908df-132">Oto transakcje stanowiące fizyczne rozchody:</span><span class="sxs-lookup"><span data-stu-id="908df-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="908df-133">arkusz listy pobrań zlecenia produkcyjnego,</span><span class="sxs-lookup"><span data-stu-id="908df-133">Production order picking list journal</span></span>
-   <span data-ttu-id="908df-134">dokument dostawy zamówienia sprzedaży,</span><span class="sxs-lookup"><span data-stu-id="908df-134">Sales order packing slip</span></span>
-   <span data-ttu-id="908df-135">zwrot dokumentu dostawy zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="908df-135">Purchase order packing slip return</span></span>

<span data-ttu-id="908df-136">Po zaksięgowaniu transakcji finansowej stan rekordu tej transakcji przyjmuje wartość **Sprzedano**.</span><span class="sxs-lookup"><span data-stu-id="908df-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="908df-137">Oto transakcje stanowiące finansowe rozchody:</span><span class="sxs-lookup"><span data-stu-id="908df-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="908df-138">Kończenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="908df-138">Ending a production order</span></span>
-   <span data-ttu-id="908df-139">Faktura dla zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="908df-139">Sales order invoice</span></span>
-   <span data-ttu-id="908df-140">Zwrot z faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="908df-140">Vendor invoice return</span></span>
-   <span data-ttu-id="908df-141">Arkusze magazynowe z ilością ujemną, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="908df-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="908df-142">Transakcje zmniejszające ilość są księgowane według dynamicznych średnich kosztów własnych.</span><span class="sxs-lookup"><span data-stu-id="908df-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="908df-143">Z tego powodu proces zamknięcia magazynu jest wymagany w celu rozliczenia transakcji rozchodu z transakcjami przychodu, według modelu magazynu przypisanego dla danego towaru.</span><span class="sxs-lookup"><span data-stu-id="908df-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>




