---
title: "Przykłady wyników amortyzacji z cofnięciami"
description: "W tym artykule opisano potencjalne skutki stornowania transakcji na środkach trwałych."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6672047cb3234e4432190d3afb20f46827ad5ef4
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="577ac-103">Przykłady wyników amortyzacji z cofnięciami</span><span class="sxs-lookup"><span data-stu-id="577ac-103">Depreciation effects with reversals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="577ac-104">W tym artykule opisano potencjalne skutki stornowania transakcji na środkach trwałych.</span><span class="sxs-lookup"><span data-stu-id="577ac-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="577ac-105">Można cofać transakcje dotyczące środka trwałego oraz transakcje skojarzone ze środkiem trwałym.</span><span class="sxs-lookup"><span data-stu-id="577ac-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="577ac-106">Można też anulować wycofaną transakcję.</span><span class="sxs-lookup"><span data-stu-id="577ac-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="577ac-107">Można wycofać lub anulować transakcję, która nie jest ostatnią transakcją zaksięgowaną w księdze środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="577ac-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="577ac-108">Najpierw należy określić, czy po wycofywanej transakcji zostały zaksięgowane jakieś inne transakcje amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="577ac-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="577ac-109">Jest to spowodowane tym, że amortyzacja nie zostanie ponownie obliczona podczas wycofywania transakcji.</span><span class="sxs-lookup"><span data-stu-id="577ac-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="577ac-110">Z tego względu często jest zawyżona lub zaniżona po wycofaniu, jak to przedstawiono w przykładach.</span><span class="sxs-lookup"><span data-stu-id="577ac-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="577ac-111">Aby upewnić się, że po wycofaniu transakcji amortyzacja będzie poprawna, nie należy doprowadzać wycofania do końca, jeśli podczas tego procesu pojawi się komunikat informujący o tym, że amortyzacja nie zostanie ponownie wyliczona.</span><span class="sxs-lookup"><span data-stu-id="577ac-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="577ac-112">Najpierw wycofaj transakcję amortyzacji, którą zaksięgowano po transakcji, którą chcesz wycofać, a dopiero wtedy możesz przejść do wycofania tej transakcji.</span><span class="sxs-lookup"><span data-stu-id="577ac-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="577ac-113">Nie pojawi się wówczas ostrzeżenie dotyczące ponownego obliczania amortyzacji i można dokończyć wycofywanie.</span><span class="sxs-lookup"><span data-stu-id="577ac-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="577ac-114">W podanych dalej przykładach przedstawiono obliczenia mające miejsce w wypadku, gdy zignorujesz komunikat z ostrzeżeniem i nie wycofasz najpierw transakcji amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="577ac-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="577ac-115"> Przykład 1. Amortyzacja zawyżona</span><span class="sxs-lookup"><span data-stu-id="577ac-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="577ac-116">Dla środka trwałego skonfigurowano 5-letni okres użytkowania oraz amortyzację liniową (60 okresów amortyzacji).</span><span class="sxs-lookup"><span data-stu-id="577ac-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="577ac-117">W tym przykładzie amortyzacja jest zawyżona.</span><span class="sxs-lookup"><span data-stu-id="577ac-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="577ac-118">Historia transakcji dotyczących środka trwałego</span><span class="sxs-lookup"><span data-stu-id="577ac-118">Asset transaction history</span></span>

| <span data-ttu-id="577ac-119">Data</span><span class="sxs-lookup"><span data-stu-id="577ac-119">Date</span></span>       | <span data-ttu-id="577ac-120">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="577ac-120">Transaction type</span></span>                                                          | <span data-ttu-id="577ac-121">Kwota</span><span class="sxs-lookup"><span data-stu-id="577ac-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="577ac-122">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-122">January 1</span></span>  | <span data-ttu-id="577ac-123">Nabycie</span><span class="sxs-lookup"><span data-stu-id="577ac-123">Acquisition</span></span>                                                               | <span data-ttu-id="577ac-124">59 000,00</span><span class="sxs-lookup"><span data-stu-id="577ac-124">59,000.00</span></span>                                 |
| <span data-ttu-id="577ac-125">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-125">January 1</span></span>  | <span data-ttu-id="577ac-126">Korekta wartości początkowej</span><span class="sxs-lookup"><span data-stu-id="577ac-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="577ac-127">1000,00</span><span class="sxs-lookup"><span data-stu-id="577ac-127">1,000.00</span></span>                                  |
| <span data-ttu-id="577ac-128">31 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-128">January 31</span></span> | <span data-ttu-id="577ac-129">Amortyzacja (na podstawie proponowanej amortyzacji dla jednego okresu)</span><span class="sxs-lookup"><span data-stu-id="577ac-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="577ac-130">1,000.00 Obliczenie: wartość księgowa (59,000 + 1,000) / liczba pozostałych okresów amortyzacji (60)</span><span class="sxs-lookup"><span data-stu-id="577ac-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="577ac-131">Akcja wycofania</span><span class="sxs-lookup"><span data-stu-id="577ac-131">Reversal action</span></span>

| <span data-ttu-id="577ac-132">Data</span><span class="sxs-lookup"><span data-stu-id="577ac-132">Date</span></span>      | <span data-ttu-id="577ac-133">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="577ac-133">Transaction type</span></span>                | <span data-ttu-id="577ac-134">Kwota</span><span class="sxs-lookup"><span data-stu-id="577ac-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="577ac-135">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-135">January 1</span></span> | <span data-ttu-id="577ac-136">Wycofanie korekty amortyzacji</span><span class="sxs-lookup"><span data-stu-id="577ac-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="577ac-137">–1000,00</span><span class="sxs-lookup"><span data-stu-id="577ac-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="577ac-138">Końcowa wartość amortyzacji</span><span class="sxs-lookup"><span data-stu-id="577ac-138">Depreciation effect</span></span>

| <span data-ttu-id="577ac-139">Data</span><span class="sxs-lookup"><span data-stu-id="577ac-139">Date</span></span>        | <span data-ttu-id="577ac-140">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="577ac-140">Transaction type</span></span>        | <span data-ttu-id="577ac-141">Kwota</span><span class="sxs-lookup"><span data-stu-id="577ac-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="577ac-142">28 lutego</span><span class="sxs-lookup"><span data-stu-id="577ac-142">February 28</span></span> | <span data-ttu-id="577ac-143">Amortyzacja (propozycja)</span><span class="sxs-lookup"><span data-stu-id="577ac-143">Depreciation (proposal)</span></span> | <span data-ttu-id="577ac-144">983.05 Obliczenie: wartość księgowa (59 000 - amortyzacja 1000) / liczba pozostałych okresów amortyzacji (59)</span><span class="sxs-lookup"><span data-stu-id="577ac-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="577ac-145">Amortyzacja jest zawyżona o 16,95 (1000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="577ac-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="577ac-146"> Przykład 2. Amortyzacja zaniżona</span><span class="sxs-lookup"><span data-stu-id="577ac-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="577ac-147">Dla środka trwałego skonfigurowano 5-letni okres użytkowania oraz amortyzację liniową (60 okresów amortyzacji).</span><span class="sxs-lookup"><span data-stu-id="577ac-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="577ac-148">W tym przykładzie amortyzacja jest zaniżona.</span><span class="sxs-lookup"><span data-stu-id="577ac-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="577ac-149">Historia transakcji dotyczących środka trwałego</span><span class="sxs-lookup"><span data-stu-id="577ac-149">Asset transaction history</span></span>

| <span data-ttu-id="577ac-150">Data</span><span class="sxs-lookup"><span data-stu-id="577ac-150">Date</span></span>       | <span data-ttu-id="577ac-151">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="577ac-151">Transaction type</span></span>                                                          | <span data-ttu-id="577ac-152">Kwota</span><span class="sxs-lookup"><span data-stu-id="577ac-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="577ac-153">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-153">January 1</span></span>  | <span data-ttu-id="577ac-154">Nabycie</span><span class="sxs-lookup"><span data-stu-id="577ac-154">Acquisition</span></span>                                                               | <span data-ttu-id="577ac-155">59 000,00</span><span class="sxs-lookup"><span data-stu-id="577ac-155">59,000.00</span></span>                                   |
| <span data-ttu-id="577ac-156">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-156">January 1</span></span>  | <span data-ttu-id="577ac-157">Zmniejszenie wartości</span><span class="sxs-lookup"><span data-stu-id="577ac-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="577ac-158">1000,00</span><span class="sxs-lookup"><span data-stu-id="577ac-158">1,000.00</span></span>                                    |
| <span data-ttu-id="577ac-159">31 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-159">January 31</span></span> | <span data-ttu-id="577ac-160">Amortyzacja (na podstawie proponowanej amortyzacji dla jednego okresu)</span><span class="sxs-lookup"><span data-stu-id="577ac-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="577ac-161">966.67 Obliczenie: wartość księgowa (59,000 + 1,000) / liczba pozostałych okresów amortyzacji (60)</span><span class="sxs-lookup"><span data-stu-id="577ac-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="577ac-162">Akcja wycofania</span><span class="sxs-lookup"><span data-stu-id="577ac-162">Reversal action</span></span>

| <span data-ttu-id="577ac-163">Data</span><span class="sxs-lookup"><span data-stu-id="577ac-163">Date</span></span>      | <span data-ttu-id="577ac-164">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="577ac-164">Transaction type</span></span>               | <span data-ttu-id="577ac-165">Kwota</span><span class="sxs-lookup"><span data-stu-id="577ac-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="577ac-166">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="577ac-166">January 1</span></span> | <span data-ttu-id="577ac-167">Zapisanie korekty amortyzacji</span><span class="sxs-lookup"><span data-stu-id="577ac-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="577ac-168">–1000,00</span><span class="sxs-lookup"><span data-stu-id="577ac-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="577ac-169">Końcowa wartość amortyzacji</span><span class="sxs-lookup"><span data-stu-id="577ac-169">Depreciation effect</span></span>

| <span data-ttu-id="577ac-170">Data</span><span class="sxs-lookup"><span data-stu-id="577ac-170">Date</span></span>        | <span data-ttu-id="577ac-171">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="577ac-171">Transaction type</span></span>        | <span data-ttu-id="577ac-172">Kwota</span><span class="sxs-lookup"><span data-stu-id="577ac-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="577ac-173">28 lutego</span><span class="sxs-lookup"><span data-stu-id="577ac-173">February 28</span></span> | <span data-ttu-id="577ac-174">Amortyzacja (propozycja)</span><span class="sxs-lookup"><span data-stu-id="577ac-174">Depreciation (proposal)</span></span> | <span data-ttu-id="577ac-175">983.62 Obliczenie: wartość księgowa (59 000 - amortyzacja 966,67) / liczba pozostałych okresów amortyzacji (59)</span><span class="sxs-lookup"><span data-stu-id="577ac-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="577ac-176">Amortyzacja jest zaniżona o 16,95 (983,62 – 966,67).</span><span class="sxs-lookup"><span data-stu-id="577ac-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="see-also"></a><span data-ttu-id="577ac-177">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="577ac-177">See also</span></span>
--------

[<span data-ttu-id="577ac-178">Amortyzacja środka trwałego</span><span class="sxs-lookup"><span data-stu-id="577ac-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)




