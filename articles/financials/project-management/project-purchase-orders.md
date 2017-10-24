---
title: "Zamówienia zakupu dla projektu"
description: "W tym artykule opisano różne metody, których można używać do tworzenia zamówień zakupu dla projektu. Wybrana metoda zależy od przeznaczenia zamówienia zakupu oraz od czasu zużywania kupionych towarów i zapisywania ich w ciężar projektu."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 985a57ae9fb116b1c4514b836b35c5da0f8838fd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="aed69-104">Zamówienia zakupu dla projektu</span><span class="sxs-lookup"><span data-stu-id="aed69-104">Purchase orders for a project</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="aed69-105">W tym artykule opisano różne metody, których można używać do tworzenia zamówień zakupu dla projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="aed69-106">Wybrana metoda zależy od przeznaczenia zamówienia zakupu oraz od czasu zużywania kupionych towarów i zapisywania ich w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="aed69-107">W programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition można używać wielu metod tworzenia zamówień zakupu dla projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="aed69-108">Wybrana metoda zależy od przeznaczenia zamówienia zakupu, czasu zużywania kupionych towarów i oraz momentu zapisania kupionych towarów w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="aed69-109">Metody tworzenia zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="aed69-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="aed69-110">Można użyć jednej z następujących metod w celu utworzenia zamówienia zakupu w module Zarządzanie projektami i ich księgowanie.</span><span class="sxs-lookup"><span data-stu-id="aed69-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="aed69-111">Przeznaczenie zamówienia zakupu decyduje o tym, kiedy jest ono zużywane i w efekcie kiedy towary są zapisywane w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aed69-112">Metoda</span><span class="sxs-lookup"><span data-stu-id="aed69-112">Method</span></span></th>
<th><span data-ttu-id="aed69-113">Cel</span><span class="sxs-lookup"><span data-stu-id="aed69-113">Purpose</span></span></th>
<th><span data-ttu-id="aed69-114">Zużycie towarów</span><span class="sxs-lookup"><span data-stu-id="aed69-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aed69-115">Tworzenie zamówienia zakupu bezpośrednio z projektu</span><span class="sxs-lookup"><span data-stu-id="aed69-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="aed69-116">Użyj tej metody do zakupu towaru u zewnętrznego dostawcy w celu zużycia w projekcie.</span><span class="sxs-lookup"><span data-stu-id="aed69-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="aed69-117">Zamówienie zakupu można utworzyć na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="aed69-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="aed69-118">Z samego projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-118">From the project itself.</span></span> <span data-ttu-id="aed69-119">W tym przypadku projekt jest już zdefiniowany dla zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="aed69-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="aed69-120">Przechodząc do zamówienia zakupu projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="aed69-121">Należy wybrać zarówno dostawcę, jak i projekt, dla których zostanie utworzone zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="aed69-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="aed69-122">Towary są zużywane przy aktualizacji faktury dostawcy.</span><span class="sxs-lookup"><span data-stu-id="aed69-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed69-123">Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="aed69-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="aed69-124">Ten metody należy używać do kupowania towarów w przypadku tworzenia zamówienia sprzedaży z projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="aed69-125">Towary są zużywane, gdy zamówienie sprzedaży jest fakturowane do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="aed69-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed69-126">Tworzenie zamówienia zakupu z zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="aed69-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="aed69-127">Tej metody należy używać do kupowania towarów w przypadku tworzenia zapotrzebowania na towar z projektu.</span><span class="sxs-lookup"><span data-stu-id="aed69-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="aed69-128">Towary są zużywane przy aktualizacji dokumentu dostawy dla zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="aed69-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="aed69-129">W przypadku aktualizacji faktury od dostawcy lub dokumentu dostawy wyświetlany jest monit o aktualizację dokumentu dostawy w zapotrzebowaniu na towar.</span><span class="sxs-lookup"><span data-stu-id="aed69-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="aed69-130">Aby uzyskać więcej informacji, zobacz [Przyjmowanie towarów względem zamówienia zakupu z zapotrzebowania na towary](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="aed69-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


