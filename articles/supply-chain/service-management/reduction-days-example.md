---
title: "Przykład dni redukcji"
description: "Przykład dni redukcji."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 46b38579e8a6246476d0893e1a047ad434f6d399
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---


# <a name="reduction-days-example"></a><span data-ttu-id="ee7b7-103">Przykład dni redukcji</span><span class="sxs-lookup"><span data-stu-id="ee7b7-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ee7b7-104">Utworzono transakcję dla subskrypcji utrzymania wykupionej przez klienta, jak to pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="ee7b7-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ee7b7-105">Data Od</span><span class="sxs-lookup"><span data-stu-id="ee7b7-105">From date</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-106">Data Do</span><span class="sxs-lookup"><span data-stu-id="ee7b7-106">To date</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-107">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="ee7b7-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-108">Typ subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ee7b7-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-109">Project</span><span class="sxs-lookup"><span data-stu-id="ee7b7-109">Project</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-110">Kategoria</span><span class="sxs-lookup"><span data-stu-id="ee7b7-110">Category</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-111">Waluta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ee7b7-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-112">Cena sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ee7b7-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee7b7-113">01 marca 2011</span><span class="sxs-lookup"><span data-stu-id="ee7b7-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-114">31 marca 2011</span><span class="sxs-lookup"><span data-stu-id="ee7b7-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="ee7b7-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-116"><strong>Normalna</strong></span><span class="sxs-lookup"><span data-stu-id="ee7b7-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="ee7b7-117">9013</span><span class="sxs-lookup"><span data-stu-id="ee7b7-117">9013</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-118">KatSub2</span><span class="sxs-lookup"><span data-stu-id="ee7b7-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-119">EUR</span><span class="sxs-lookup"><span data-stu-id="ee7b7-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-120">200,00</span><span class="sxs-lookup"><span data-stu-id="ee7b7-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ee7b7-121">Klient zgłasza, że nie potrzebuje serwisu przez dwa dni (10 i 11 marca).</span><span class="sxs-lookup"><span data-stu-id="ee7b7-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="ee7b7-122">Zgadzasz się na ograniczenie subskrypcji w tych dniach.</span><span class="sxs-lookup"><span data-stu-id="ee7b7-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="ee7b7-123">Tworzysz nową transakcję typu **Dni redukcji**, jak to opisano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="ee7b7-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ee7b7-124">Data Od</span><span class="sxs-lookup"><span data-stu-id="ee7b7-124">From date</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-125">Data Do</span><span class="sxs-lookup"><span data-stu-id="ee7b7-125">To date</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-126">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="ee7b7-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-127">Typ subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ee7b7-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-128">Project</span><span class="sxs-lookup"><span data-stu-id="ee7b7-128">Project</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-129">Kategoria</span><span class="sxs-lookup"><span data-stu-id="ee7b7-129">Category</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-130">Waluta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ee7b7-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="ee7b7-131">Cena sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ee7b7-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee7b7-132">10 marca 2011</span><span class="sxs-lookup"><span data-stu-id="ee7b7-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-133">11 marca 2011</span><span class="sxs-lookup"><span data-stu-id="ee7b7-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="ee7b7-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-135"><strong>Dni redukcji</strong></span><span class="sxs-lookup"><span data-stu-id="ee7b7-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="ee7b7-136">9013</span><span class="sxs-lookup"><span data-stu-id="ee7b7-136">9013</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-137">KatSub2</span><span class="sxs-lookup"><span data-stu-id="ee7b7-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-138">EUR</span><span class="sxs-lookup"><span data-stu-id="ee7b7-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="ee7b7-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="ee7b7-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ee7b7-140">W czasie fakturowania transakcji za miesiąc marzec 2011 roku cena sprzedaży 200 EUR zostaje obniżona o 12,90 EUR.</span><span class="sxs-lookup"><span data-stu-id="ee7b7-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="ee7b7-141">Należność z tytułu transakcji subskrypcji wynosi zatem 187,10 EUR, a łączna wartość faktury dla dwóch transakcji wynosi 187,10 EUR.</span><span class="sxs-lookup"><span data-stu-id="ee7b7-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee7b7-142">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ee7b7-142">See also</span></span>

[<span data-ttu-id="ee7b7-143">Zmniejszanie dni na opłaty subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ee7b7-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  



