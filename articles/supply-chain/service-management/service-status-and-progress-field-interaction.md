---
title: Stan usługi i interakcja pola postępu
description: W formularzu Zlecenia serwisowe pole Postęp znajdujące się w nagłówku odzwierciedla stan całego zlecenia serwisowego, a pole Stan prezentuje stany poszczególnych wierszy zlecenia serwisowego.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c66871d07bdfd949e29a704f53b3e5698d996c2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254222"
---
# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="635e8-103">Stan usługi i interakcja pola postępu</span><span class="sxs-lookup"><span data-stu-id="635e8-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="635e8-104">W formularzu **Zlecenia serwisowe** pole **Postęp** znajdujące się w nagłówku zlecenia serwisowego odzwierciedla stan całego zlecenia serwisowego, a pole **Stan** prezentuje stany poszczególnych wierszy zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="635e8-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="635e8-105">Postęp</span><span class="sxs-lookup"><span data-stu-id="635e8-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="635e8-106">Stan wiersza 1</span><span class="sxs-lookup"><span data-stu-id="635e8-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="635e8-107">Stan wiersza 2</span><span class="sxs-lookup"><span data-stu-id="635e8-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="635e8-108">Stan wiersza 3</span><span class="sxs-lookup"><span data-stu-id="635e8-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="635e8-109"><strong>W toku</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-110"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-111"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-112"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635e8-113"><strong>W toku</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-114"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-115"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-116"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635e8-117"><strong>W toku</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-118"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-119"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-120"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635e8-121"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-122"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-123"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-124"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635e8-125"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-126"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-127"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-128"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635e8-129"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-130"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-131"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="635e8-132"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="635e8-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="635e8-133">Zlecenie serwisowe jest przetwarzane, jeśli wszystkie wiersze mają stan **Utworzono**. Nadal jest przetwarzane, jeśli niektóre wiersze mają stan **Anulowano** lub **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="635e8-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="635e8-134">Jeśli wszystkie wiersze zlecenia serwisowego są oznaczone jako **Zaksięgowano**, postęp przetwarzania zlecenia serwisowego jest oznaczony jako **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="635e8-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="635e8-135">Jeśli niektóre wiersze są oznaczone jako **Zaksięgowano**, a inne jako **Anulowano**, postęp przetwarzania jest wciąż oznaczony jako **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="635e8-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]