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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd70d00f7ce531b225362065dfd9f1f5c1adc754
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207331"
---
# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="ca9f1-103">Stan usługi i interakcja pola postępu</span><span class="sxs-lookup"><span data-stu-id="ca9f1-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ca9f1-104">W formularzu **Zlecenia serwisowe** pole **Postęp** znajdujące się w nagłówku zlecenia serwisowego odzwierciedla stan całego zlecenia serwisowego, a pole **Stan** prezentuje stany poszczególnych wierszy zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="ca9f1-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ca9f1-105">Postęp</span><span class="sxs-lookup"><span data-stu-id="ca9f1-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="ca9f1-106">Stan wiersza 1</span><span class="sxs-lookup"><span data-stu-id="ca9f1-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="ca9f1-107">Stan wiersza 2</span><span class="sxs-lookup"><span data-stu-id="ca9f1-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="ca9f1-108">Stan wiersza 3</span><span class="sxs-lookup"><span data-stu-id="ca9f1-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca9f1-109"><strong>W toku</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-110"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-111"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-112"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9f1-113"><strong>W toku</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-114"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-115"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-116"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca9f1-117"><strong>W toku</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-118"><strong>Utworzone</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-119"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-120"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9f1-121"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-122"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-123"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-124"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca9f1-125"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-126"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-127"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-128"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9f1-129"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-130"><strong>Zaksięgowano</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-131"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9f1-132"><strong>Anulowane</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ca9f1-133">Zlecenie serwisowe jest przetwarzane, jeśli wszystkie wiersze mają stan **Utworzono**. Nadal jest przetwarzane, jeśli niektóre wiersze mają stan **Anulowano** lub **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="ca9f1-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="ca9f1-134">Jeśli wszystkie wiersze zlecenia serwisowego są oznaczone jako **Zaksięgowano**, postęp przetwarzania zlecenia serwisowego jest oznaczony jako **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="ca9f1-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="ca9f1-135">Jeśli niektóre wiersze są oznaczone jako **Zaksięgowano**, a inne jako **Anulowano**, postęp przetwarzania jest wciąż oznaczony jako **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="ca9f1-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  


