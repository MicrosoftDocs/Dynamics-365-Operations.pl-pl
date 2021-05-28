---
title: Kumulacja rabatów dla odbiorcy nie powiedzie się, gdy używane są grupy rabatowe dla pozycji
description: W przypadku użycia umów rabatowych z klientem w połączeniu z grupami rabatowymi dla towarów rabaty są obliczane, ale kumulacja nie powiedzie się.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026803"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="285ad-103">Kumulacja rabatów dla odbiorcy nie powiedzie się, gdy używane są grupy rabatowe dla pozycji</span><span class="sxs-lookup"><span data-stu-id="285ad-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="285ad-104">Numer artykułu z bazy wiedzy: 4611372</span><span class="sxs-lookup"><span data-stu-id="285ad-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="285ad-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="285ad-105">Symptoms</span></span>

<span data-ttu-id="285ad-106">W przypadku użycia umów rabatowych z klientem (typów *kwota*)  w połączeniu z grupami rabatowymi dla towarów rabaty są obliczane, ale kumulacja nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="285ad-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="285ad-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="285ad-107">Resolution</span></span>

<span data-ttu-id="285ad-108">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="285ad-108">The system is behaving as designed.</span></span> <span data-ttu-id="285ad-109">Grupy pozycji grupuje tylko pozycje, które mają ten sam warunek progu.</span><span class="sxs-lookup"><span data-stu-id="285ad-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="285ad-110">Warunek rabatu (próg) jest ustawiany w stosunku do kwoty dla każdego towaru, a nie z skumulowanej kwoty dla jakiegokolwiek towaru w grupie towarów.</span><span class="sxs-lookup"><span data-stu-id="285ad-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
