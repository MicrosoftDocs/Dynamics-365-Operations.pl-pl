---
title: Subskrypcja — ceny sprzedaży
description: W przypadku tworzenia subskrypcji cena sprzedaży jest ustalana na podstawie konfiguracji ceny sprzedaży utworzonej w formularzu Cena sprzedaży — subskrypcja.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f03efbbca4fc9da76c6ead7566457beb79c8c249
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985872"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="90ac5-103">Subskrypcja — ceny sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="90ac5-104">W przypadku tworzenia subskrypcji cena sprzedaży jest ustalana na podstawie konfiguracji ceny sprzedaży utworzonej w formularzu **Cena sprzedaży — subskrypcja**.</span><span class="sxs-lookup"><span data-stu-id="90ac5-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="90ac5-105">W formularzu **Cena sprzedaży — subskrypcja** można utworzyć ceny sprzedaży dla określonej subskrypcji lub o szerszym zastosowaniu.</span><span class="sxs-lookup"><span data-stu-id="90ac5-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="90ac5-106">Aby cena sprzedaży była stosowana do subskrypcji, kod okresu i waluta subskrypcji muszą być takie same, jak kod okresu i waluta ceny sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="90ac5-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="90ac5-107">Jeśli kod okresu i waluta są takie same dla subskrypcji i ceny sprzedaży, ceny sprzedaży subskrypcji są wybierane na podstawie priorytetów przedstawionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="90ac5-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="90ac5-108">Pusta komórka w tabeli wskazuje puste pole, a znak X wskazuje wartość równą wartości określonej w subskrypcji, na podstawie której jest generowana transakcja.</span><span class="sxs-lookup"><span data-stu-id="90ac5-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="90ac5-109">Priorytet </span><span class="sxs-lookup"><span data-stu-id="90ac5-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="90ac5-110"><strong>Kategoria</strong></span><span class="sxs-lookup"><span data-stu-id="90ac5-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="90ac5-111"><strong>Identyfikator projektu</strong></span><span class="sxs-lookup"><span data-stu-id="90ac5-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="90ac5-112"><strong>Subskrypcja</strong></span><span class="sxs-lookup"><span data-stu-id="90ac5-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="90ac5-113"><strong>Waluta sprzedaży</strong></span><span class="sxs-lookup"><span data-stu-id="90ac5-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="90ac5-114"><strong>Kod okresu</strong></span><span class="sxs-lookup"><span data-stu-id="90ac5-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-115">1</span><span class="sxs-lookup"><span data-stu-id="90ac5-115">1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-116">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-116">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-117">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-117">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-118">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-118">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-119">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-119">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-120">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-121">2</span><span class="sxs-lookup"><span data-stu-id="90ac5-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-122">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-122">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-123">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-123">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-124">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-124">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-125">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-126">3</span><span class="sxs-lookup"><span data-stu-id="90ac5-126">3</span></span></p></td>
<td><p><span data-ttu-id="90ac5-127">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-128">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-128">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-129">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-129">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-130">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-131">4</span><span class="sxs-lookup"><span data-stu-id="90ac5-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-132">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-132">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-133">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-133">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-134">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-135">5</span><span class="sxs-lookup"><span data-stu-id="90ac5-135">5</span></span></p></td>
<td><p><span data-ttu-id="90ac5-136">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-136">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-137">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-138">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-138">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-139">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-140">6</span><span class="sxs-lookup"><span data-stu-id="90ac5-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-141">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-142">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-142">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-143">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-144">7</span><span class="sxs-lookup"><span data-stu-id="90ac5-144">7</span></span></p></td>
<td><p><span data-ttu-id="90ac5-145">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-146">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-146">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-147">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-148">8</span><span class="sxs-lookup"><span data-stu-id="90ac5-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="90ac5-149">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-149">X</span></span></p></td>
<td><p><span data-ttu-id="90ac5-150">X</span><span class="sxs-lookup"><span data-stu-id="90ac5-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90ac5-151">Podczas tworzenia opłaty subskrypcji jako cena sprzedaży subskrypcji jest wybierana cena sprzedaży o najwyższym poziomie szczegółowości, zgodnie z powyższą tabelą.</span><span class="sxs-lookup"><span data-stu-id="90ac5-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="90ac5-152">Aktualizacja i subskrypcje indeksu cen sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="90ac5-153">Cenę sprzedaży subskrypcji można zaktualizować przez aktualizację ceny podstawowej lub indeksu.</span><span class="sxs-lookup"><span data-stu-id="90ac5-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="90ac5-154">Aktualizacja polega na określeniu procentu lub nowej wartości.</span><span class="sxs-lookup"><span data-stu-id="90ac5-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="90ac5-155">Ceny sprzedaży dla opłaty subskrypcji</span><span class="sxs-lookup"><span data-stu-id="90ac5-155">Subscription fee sales prices</span></span>

<span data-ttu-id="90ac5-156">W przypadku tworzenia opłaty subskrypcji cena sprzedaży jest ustalana na podstawie konfiguracji cen sprzedaży subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="90ac5-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="90ac5-157">Można użyć ceny podstawowej z konfiguracji ceny sprzedaży subskrypcji lub utworzyć indeksowane ceny sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="90ac5-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="90ac5-158">Przykład</span><span class="sxs-lookup"><span data-stu-id="90ac5-158">Example</span></span>

<span data-ttu-id="90ac5-159">Chcesz skonfigurować cenę sprzedaży subskrypcji równą 500 euro dla nowego projektu 9030.</span><span class="sxs-lookup"><span data-stu-id="90ac5-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="90ac5-160">W formularzu **Cena sprzedaży — subskrypcja** tworzy się wiersz ceny sprzedaży subskrypcji w sposób przedstawiony w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="90ac5-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="90ac5-161">Obowiązuje od</span><span class="sxs-lookup"><span data-stu-id="90ac5-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="90ac5-162">Kategoria</span><span class="sxs-lookup"><span data-stu-id="90ac5-162">Category</span></span></p></th>
<th><p><span data-ttu-id="90ac5-163">Project</span><span class="sxs-lookup"><span data-stu-id="90ac5-163">Project</span></span></p></th>
<th><p><span data-ttu-id="90ac5-164">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="90ac5-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="90ac5-165">Kod okresu</span><span class="sxs-lookup"><span data-stu-id="90ac5-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="90ac5-166">Waluta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="90ac5-167">Cena sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-168">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="90ac5-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90ac5-169">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90ac5-170">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="90ac5-170">Month</span></span></p></td>
<td><p><span data-ttu-id="90ac5-171">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-172">500</span><span class="sxs-lookup"><span data-stu-id="90ac5-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90ac5-173">Należy zauważyć, że pola **Kategoria** i **Subskrypcja** są puste.</span><span class="sxs-lookup"><span data-stu-id="90ac5-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="90ac5-174">Następnie tworzysz poniższe subskrypcje:</span><span class="sxs-lookup"><span data-stu-id="90ac5-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="90ac5-175">Subskrypcja serwisu</span><span class="sxs-lookup"><span data-stu-id="90ac5-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="90ac5-176">Project</span><span class="sxs-lookup"><span data-stu-id="90ac5-176">Project</span></span></p></th>
<th><p><span data-ttu-id="90ac5-177">Grupa subskrypcji</span><span class="sxs-lookup"><span data-stu-id="90ac5-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="90ac5-178">Kategoria</span><span class="sxs-lookup"><span data-stu-id="90ac5-178">Category</span></span></p></th>
<th><p><span data-ttu-id="90ac5-179">Waluta</span><span class="sxs-lookup"><span data-stu-id="90ac5-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="90ac5-180">Kod okresu</span><span class="sxs-lookup"><span data-stu-id="90ac5-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="90ac5-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="90ac5-182">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-182">9030</span></span></p></td>
<td><p><span data-ttu-id="90ac5-183">Sub1</span><span class="sxs-lookup"><span data-stu-id="90ac5-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-184">KatSub1</span><span class="sxs-lookup"><span data-stu-id="90ac5-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-185">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-186">Miesięczna</span><span class="sxs-lookup"><span data-stu-id="90ac5-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="90ac5-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="90ac5-188">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-188">9030</span></span></p></td>
<td><p><span data-ttu-id="90ac5-189">Sub1</span><span class="sxs-lookup"><span data-stu-id="90ac5-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-190">KatSub2</span><span class="sxs-lookup"><span data-stu-id="90ac5-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="90ac5-191">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-192">Miesięczna</span><span class="sxs-lookup"><span data-stu-id="90ac5-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90ac5-193">Teraz tworzysz opłaty subskrypcji dla obu subskrypcji w grupie subskrypcji Sub1:</span><span class="sxs-lookup"><span data-stu-id="90ac5-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="90ac5-194">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Subskrypcje serwisowe** \> **Grupy subskrypcji**.</span><span class="sxs-lookup"><span data-stu-id="90ac5-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="90ac5-195">W formularzu **Grupy subskrypcji** kliknij kolejno opcje **Funkcja** \> **Utwórz opłatę subskrypcji**.</span><span class="sxs-lookup"><span data-stu-id="90ac5-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="90ac5-196">W formularzu **Utwórz opłatę subskrypcji** wprowadź odpowiednie informacje.</span><span class="sxs-lookup"><span data-stu-id="90ac5-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="90ac5-197">Aby uzyskać więcej informacji, zobacz [Tworzenie transakcji opłat subskrypcji](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="90ac5-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="90ac5-198">Opłaty subskrypcyjne, których cena sprzedaży wynosi 500 euro, są tworzone dla obu subskrypcji, jak pokazano w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="90ac5-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="90ac5-199">Data projektu</span><span class="sxs-lookup"><span data-stu-id="90ac5-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="90ac5-200">Subskrypcja serwisu</span><span class="sxs-lookup"><span data-stu-id="90ac5-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="90ac5-201">Project</span><span class="sxs-lookup"><span data-stu-id="90ac5-201">Project</span></span></p></th>
<th><p><span data-ttu-id="90ac5-202">Kategoria</span><span class="sxs-lookup"><span data-stu-id="90ac5-202">Category</span></span></p></th>
<th><p><span data-ttu-id="90ac5-203">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="90ac5-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="90ac5-204">Data końcowa</span><span class="sxs-lookup"><span data-stu-id="90ac5-204">End date</span></span></p></th>
<th><p><span data-ttu-id="90ac5-205">Waluta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="90ac5-206">Cena sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-207">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="90ac5-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="90ac5-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="90ac5-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="90ac5-209">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-209">9030</span></span></p></td>
<td><p><span data-ttu-id="90ac5-210">KatSub1</span><span class="sxs-lookup"><span data-stu-id="90ac5-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-211">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="90ac5-212">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="90ac5-213">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-214">500</span><span class="sxs-lookup"><span data-stu-id="90ac5-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-215">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="90ac5-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="90ac5-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="90ac5-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="90ac5-217">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-217">9030</span></span></p></td>
<td><p><span data-ttu-id="90ac5-218">KatSub2</span><span class="sxs-lookup"><span data-stu-id="90ac5-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="90ac5-219">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="90ac5-220">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="90ac5-221">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-222">500</span><span class="sxs-lookup"><span data-stu-id="90ac5-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90ac5-223">Następnie decydujesz się określić ceny sprzedaży dla kategorii KatSub1 i projektu 9030.</span><span class="sxs-lookup"><span data-stu-id="90ac5-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="90ac5-224">Dlatego tworzysz nowy wiersz ceny sprzedaży z ceną sprzedaży 550 euro dla kombinacji projektu 9030 i kategorii opłaty KatSub1.</span><span class="sxs-lookup"><span data-stu-id="90ac5-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="90ac5-225">Dla projektu 9030 są teraz dwa wiersze ceny sprzedaży subskrypcji, jak widać w tabeli poniżej:</span><span class="sxs-lookup"><span data-stu-id="90ac5-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="90ac5-226">Obowiązuje od</span><span class="sxs-lookup"><span data-stu-id="90ac5-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="90ac5-227">Kategoria</span><span class="sxs-lookup"><span data-stu-id="90ac5-227">Category</span></span></p></th>
<th><p><span data-ttu-id="90ac5-228">Project</span><span class="sxs-lookup"><span data-stu-id="90ac5-228">Project</span></span></p></th>
<th><p><span data-ttu-id="90ac5-229">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="90ac5-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="90ac5-230">Kod okresu</span><span class="sxs-lookup"><span data-stu-id="90ac5-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="90ac5-231">Waluta</span><span class="sxs-lookup"><span data-stu-id="90ac5-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="90ac5-232">Cena sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-233">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90ac5-234">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90ac5-235">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="90ac5-235">Month</span></span></p></td>
<td><p><span data-ttu-id="90ac5-236">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-237">500</span><span class="sxs-lookup"><span data-stu-id="90ac5-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-238">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="90ac5-239">KatSub1</span><span class="sxs-lookup"><span data-stu-id="90ac5-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-240">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90ac5-241">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="90ac5-241">Month</span></span></p></td>
<td><p><span data-ttu-id="90ac5-242">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-243">550</span><span class="sxs-lookup"><span data-stu-id="90ac5-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90ac5-244">Powtarzasz procedurę opisaną powyżej w celu utworzenia opłat subskrypcji dla obu subskrypcji w grupie subskrypcji Sub1.</span><span class="sxs-lookup"><span data-stu-id="90ac5-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="90ac5-245">Tabela poniżej pokazuje transakcje, które są tworzone dla każdej subskrypcji dołączonej do grupy subskrypcji:</span><span class="sxs-lookup"><span data-stu-id="90ac5-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="90ac5-246">Data projektu</span><span class="sxs-lookup"><span data-stu-id="90ac5-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="90ac5-247">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="90ac5-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="90ac5-248">Project</span><span class="sxs-lookup"><span data-stu-id="90ac5-248">Project</span></span></p></th>
<th><p><span data-ttu-id="90ac5-249">Kategoria</span><span class="sxs-lookup"><span data-stu-id="90ac5-249">Category</span></span></p></th>
<th><p><span data-ttu-id="90ac5-250">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="90ac5-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="90ac5-251">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="90ac5-251">End date</span></span></p></th>
<th><p><span data-ttu-id="90ac5-252">Waluta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="90ac5-253">Cena sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac5-254">28-07-2007</span><span class="sxs-lookup"><span data-stu-id="90ac5-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="90ac5-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="90ac5-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="90ac5-256">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-256">9030</span></span></p></td>
<td><p><span data-ttu-id="90ac5-257">KatSub1</span><span class="sxs-lookup"><span data-stu-id="90ac5-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="90ac5-258">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="90ac5-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="90ac5-259">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="90ac5-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="90ac5-260">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-261">550</span><span class="sxs-lookup"><span data-stu-id="90ac5-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac5-262">28-07-2008</span><span class="sxs-lookup"><span data-stu-id="90ac5-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="90ac5-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="90ac5-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="90ac5-264">9030</span><span class="sxs-lookup"><span data-stu-id="90ac5-264">9030</span></span></p></td>
<td><p><span data-ttu-id="90ac5-265">KatSub2</span><span class="sxs-lookup"><span data-stu-id="90ac5-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="90ac5-266">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="90ac5-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="90ac5-267">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="90ac5-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="90ac5-268">EUR</span><span class="sxs-lookup"><span data-stu-id="90ac5-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="90ac5-269">500</span><span class="sxs-lookup"><span data-stu-id="90ac5-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90ac5-270">W pierwszej transakcji — dla subskrypcji 00020\_135 — cena sprzedaży 550 euro została ustalona na podstawie cen sprzedaży subskrypcji skonfigurowanej dla kombinacji określonego projektu i kategorii.</span><span class="sxs-lookup"><span data-stu-id="90ac5-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="90ac5-271">W drugiej transakcji — dla subskrypcji 00021\_135 — cena sprzedaży 500 euro została ustalona jako cena sprzedaży subskrypcji projektu, ponieważ nie ma skonfigurowanej ceny dla kombinacji projektu 9030 i kategorii KatSub2.</span><span class="sxs-lookup"><span data-stu-id="90ac5-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="90ac5-272">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="90ac5-272">See also</span></span>

[<span data-ttu-id="90ac5-273">Aktualizacja i subskrypcje indeksu cen sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90ac5-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


