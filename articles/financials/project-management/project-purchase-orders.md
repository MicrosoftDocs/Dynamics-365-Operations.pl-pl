---
title: Zamówienia zakupu dla projektu
description: W tym artykule opisano różne metody, których można używać do tworzenia zamówień zakupu dla projektu. Wybrana metoda zależy od przeznaczenia zamówienia zakupu oraz od czasu zużywania kupionych towarów i zapisywania ich w ciężar projektu.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 971a4ea0abac43c160d8a6f46f385cbfc5134ffd
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838878"
---
# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="47e83-104">Zamówienia zakupu dla projektu</span><span class="sxs-lookup"><span data-stu-id="47e83-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47e83-105">W tym artykule opisano różne metody, których można używać do tworzenia zamówień zakupu dla projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="47e83-106">Wybrana metoda zależy od przeznaczenia zamówienia zakupu oraz od czasu zużywania kupionych towarów i zapisywania ich w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="47e83-107">W Microsoft Dynamics 365 for Finance and Operations można używać wielu metod tworzenia zamówień zakupu dla projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-107">In Microsoft Dynamics 365 for Finance and Operations, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="47e83-108">Wybrana metoda zależy od przeznaczenia zamówienia zakupu, czasu zużywania kupionych towarów i oraz momentu zapisania kupionych towarów w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="47e83-109">Metody tworzenia zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="47e83-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="47e83-110">Można użyć jednej z następujących metod w celu utworzenia zamówienia zakupu w module Zarządzanie projektami i ich księgowanie.</span><span class="sxs-lookup"><span data-stu-id="47e83-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="47e83-111">Przeznaczenie zamówienia zakupu decyduje o tym, kiedy jest ono zużywane i w efekcie kiedy towary są zapisywane w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47e83-112">Metoda</span><span class="sxs-lookup"><span data-stu-id="47e83-112">Method</span></span></th>
<th><span data-ttu-id="47e83-113">Cel</span><span class="sxs-lookup"><span data-stu-id="47e83-113">Purpose</span></span></th>
<th><span data-ttu-id="47e83-114">Zużycie towarów</span><span class="sxs-lookup"><span data-stu-id="47e83-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="47e83-115">Tworzenie zamówienia zakupu bezpośrednio z projektu</span><span class="sxs-lookup"><span data-stu-id="47e83-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="47e83-116">Użyj tej metody do zakupu towaru u zewnętrznego dostawcy w celu zużycia w projekcie.</span><span class="sxs-lookup"><span data-stu-id="47e83-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="47e83-117">Zamówienie zakupu można utworzyć na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="47e83-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="47e83-118">Z samego projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-118">From the project itself.</span></span> <span data-ttu-id="47e83-119">W tym przypadku projekt jest już zdefiniowany dla zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="47e83-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="47e83-120">Przechodząc do zamówienia zakupu projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="47e83-121">Należy wybrać zarówno dostawcę, jak i projekt, dla których zostanie utworzone zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="47e83-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="47e83-122">Towary są zużywane przy aktualizacji faktury dostawcy.</span><span class="sxs-lookup"><span data-stu-id="47e83-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="47e83-123">Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="47e83-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="47e83-124">Ten metody należy używać do kupowania towarów w przypadku tworzenia zamówienia sprzedaży z projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="47e83-125">Towary są zużywane, gdy zamówienie sprzedaży jest fakturowane do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="47e83-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="47e83-126">Tworzenie zamówienia zakupu z zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="47e83-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="47e83-127">Tej metody należy używać do kupowania towarów w przypadku tworzenia zapotrzebowania na towar z projektu.</span><span class="sxs-lookup"><span data-stu-id="47e83-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="47e83-128">Towary są zużywane przy aktualizacji dokumentu dostawy dla zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="47e83-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="47e83-129">W przypadku aktualizacji faktury od dostawcy lub dokumentu dostawy wyświetlany jest monit o aktualizację dokumentu dostawy w zapotrzebowaniu na towar.</span><span class="sxs-lookup"><span data-stu-id="47e83-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="47e83-130">Aby uzyskać więcej informacji, zobacz [Przyjmowanie towarów względem zamówienia zakupu z zapotrzebowania na towary](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="47e83-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

