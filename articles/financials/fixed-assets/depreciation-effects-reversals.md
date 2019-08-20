---
title: Przykłady wyników amortyzacji z cofnięciami
description: W tym artykule opisano potencjalne skutki stornowania transakcji na środkach trwałych.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd4c4a9e7e89b34b1311b38310877b45e4d95b22
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840608"
---
# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="1a522-103">Przykłady wyników amortyzacji z cofnięciami</span><span class="sxs-lookup"><span data-stu-id="1a522-103">Depreciation effects with reversals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a522-104">W tym artykule opisano potencjalne skutki stornowania transakcji na środkach trwałych.</span><span class="sxs-lookup"><span data-stu-id="1a522-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="1a522-105">Można cofać transakcje dotyczące środka trwałego oraz transakcje skojarzone ze środkiem trwałym.</span><span class="sxs-lookup"><span data-stu-id="1a522-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="1a522-106">Można też anulować wycofaną transakcję.</span><span class="sxs-lookup"><span data-stu-id="1a522-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="1a522-107">Można wycofać lub anulować transakcję, która nie jest ostatnią transakcją zaksięgowaną w księdze środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="1a522-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="1a522-108">Najpierw należy określić, czy po wycofywanej transakcji zostały zaksięgowane jakieś inne transakcje amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="1a522-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="1a522-109">Jest to spowodowane tym, że amortyzacja nie zostanie ponownie obliczona podczas wycofywania transakcji.</span><span class="sxs-lookup"><span data-stu-id="1a522-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="1a522-110">Z tego względu często jest zawyżona lub zaniżona po wycofaniu, jak to przedstawiono w przykładach.</span><span class="sxs-lookup"><span data-stu-id="1a522-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="1a522-111">Aby upewnić się, że po wycofaniu transakcji amortyzacja będzie poprawna, nie należy doprowadzać wycofania do końca, jeśli podczas tego procesu pojawi się komunikat informujący o tym, że amortyzacja nie zostanie ponownie wyliczona.</span><span class="sxs-lookup"><span data-stu-id="1a522-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="1a522-112">Najpierw wycofaj transakcję amortyzacji, którą zaksięgowano po transakcji, którą chcesz wycofać, a dopiero wtedy możesz przejść do wycofania tej transakcji.</span><span class="sxs-lookup"><span data-stu-id="1a522-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="1a522-113">Nie pojawi się wówczas ostrzeżenie dotyczące ponownego obliczania amortyzacji i można dokończyć wycofywanie.</span><span class="sxs-lookup"><span data-stu-id="1a522-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="1a522-114">W podanych dalej przykładach przedstawiono obliczenia mające miejsce w wypadku, gdy zignorujesz komunikat z ostrzeżeniem i nie wycofasz najpierw transakcji amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="1a522-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="1a522-115"> Przykład 1. Amortyzacja zawyżona</span><span class="sxs-lookup"><span data-stu-id="1a522-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="1a522-116">Dla środka trwałego skonfigurowano 5-letni okres użytkowania oraz amortyzację liniową (60 okresów amortyzacji).</span><span class="sxs-lookup"><span data-stu-id="1a522-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="1a522-117">W tym przykładzie amortyzacja jest zawyżona.</span><span class="sxs-lookup"><span data-stu-id="1a522-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="1a522-118">Historia transakcji dotyczących środka trwałego</span><span class="sxs-lookup"><span data-stu-id="1a522-118">Asset transaction history</span></span>

| <span data-ttu-id="1a522-119">Data</span><span class="sxs-lookup"><span data-stu-id="1a522-119">Date</span></span>       | <span data-ttu-id="1a522-120">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="1a522-120">Transaction type</span></span>                                                          | <span data-ttu-id="1a522-121">Kwota</span><span class="sxs-lookup"><span data-stu-id="1a522-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="1a522-122">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-122">January 1</span></span>  | <span data-ttu-id="1a522-123">Nabycie</span><span class="sxs-lookup"><span data-stu-id="1a522-123">Acquisition</span></span>                                                               | <span data-ttu-id="1a522-124">59 000,00</span><span class="sxs-lookup"><span data-stu-id="1a522-124">59,000.00</span></span>                                 |
| <span data-ttu-id="1a522-125">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-125">January 1</span></span>  | <span data-ttu-id="1a522-126">Korekta wartości początkowej</span><span class="sxs-lookup"><span data-stu-id="1a522-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="1a522-127">1000,00</span><span class="sxs-lookup"><span data-stu-id="1a522-127">1,000.00</span></span>                                  |
| <span data-ttu-id="1a522-128">31 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-128">January 31</span></span> | <span data-ttu-id="1a522-129">Amortyzacja (na podstawie proponowanej amortyzacji dla jednego okresu)</span><span class="sxs-lookup"><span data-stu-id="1a522-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="1a522-130">1,000.00 Obliczenie: wartość księgowa (59,000 + 1,000) / liczba pozostałych okresów amortyzacji (60)</span><span class="sxs-lookup"><span data-stu-id="1a522-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="1a522-131">Akcja wycofania</span><span class="sxs-lookup"><span data-stu-id="1a522-131">Reversal action</span></span>

| <span data-ttu-id="1a522-132">Data</span><span class="sxs-lookup"><span data-stu-id="1a522-132">Date</span></span>      | <span data-ttu-id="1a522-133">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="1a522-133">Transaction type</span></span>                | <span data-ttu-id="1a522-134">Kwota</span><span class="sxs-lookup"><span data-stu-id="1a522-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="1a522-135">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-135">January 1</span></span> | <span data-ttu-id="1a522-136">Wycofanie korekty amortyzacji</span><span class="sxs-lookup"><span data-stu-id="1a522-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="1a522-137">–1000,00</span><span class="sxs-lookup"><span data-stu-id="1a522-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="1a522-138">Końcowa wartość amortyzacji</span><span class="sxs-lookup"><span data-stu-id="1a522-138">Depreciation effect</span></span>

| <span data-ttu-id="1a522-139">Data</span><span class="sxs-lookup"><span data-stu-id="1a522-139">Date</span></span>        | <span data-ttu-id="1a522-140">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="1a522-140">Transaction type</span></span>        | <span data-ttu-id="1a522-141">Kwota</span><span class="sxs-lookup"><span data-stu-id="1a522-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="1a522-142">28 lutego</span><span class="sxs-lookup"><span data-stu-id="1a522-142">February 28</span></span> | <span data-ttu-id="1a522-143">Amortyzacja (propozycja)</span><span class="sxs-lookup"><span data-stu-id="1a522-143">Depreciation (proposal)</span></span> | <span data-ttu-id="1a522-144">983.05 Obliczenie: wartość księgowa (59 000 - amortyzacja 1000) / liczba pozostałych okresów amortyzacji (59)</span><span class="sxs-lookup"><span data-stu-id="1a522-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="1a522-145">Amortyzacja jest zawyżona o 16,95 (1000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="1a522-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="1a522-146"> Przykład 2. Amortyzacja zaniżona</span><span class="sxs-lookup"><span data-stu-id="1a522-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="1a522-147">Dla środka trwałego skonfigurowano 5-letni okres użytkowania oraz amortyzację liniową (60 okresów amortyzacji).</span><span class="sxs-lookup"><span data-stu-id="1a522-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="1a522-148">W tym przykładzie amortyzacja jest zaniżona.</span><span class="sxs-lookup"><span data-stu-id="1a522-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="1a522-149">Historia transakcji dotyczących środka trwałego</span><span class="sxs-lookup"><span data-stu-id="1a522-149">Asset transaction history</span></span>

| <span data-ttu-id="1a522-150">Data</span><span class="sxs-lookup"><span data-stu-id="1a522-150">Date</span></span>       | <span data-ttu-id="1a522-151">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="1a522-151">Transaction type</span></span>                                                          | <span data-ttu-id="1a522-152">Kwota</span><span class="sxs-lookup"><span data-stu-id="1a522-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="1a522-153">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-153">January 1</span></span>  | <span data-ttu-id="1a522-154">Nabycie</span><span class="sxs-lookup"><span data-stu-id="1a522-154">Acquisition</span></span>                                                               | <span data-ttu-id="1a522-155">59 000,00</span><span class="sxs-lookup"><span data-stu-id="1a522-155">59,000.00</span></span>                                   |
| <span data-ttu-id="1a522-156">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-156">January 1</span></span>  | <span data-ttu-id="1a522-157">Zmniejszenie wartości</span><span class="sxs-lookup"><span data-stu-id="1a522-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="1a522-158">1000,00</span><span class="sxs-lookup"><span data-stu-id="1a522-158">1,000.00</span></span>                                    |
| <span data-ttu-id="1a522-159">31 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-159">January 31</span></span> | <span data-ttu-id="1a522-160">Amortyzacja (na podstawie proponowanej amortyzacji dla jednego okresu)</span><span class="sxs-lookup"><span data-stu-id="1a522-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="1a522-161">966.67 Obliczenie: wartość księgowa (59,000 + 1,000) / liczba pozostałych okresów amortyzacji (60)</span><span class="sxs-lookup"><span data-stu-id="1a522-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="1a522-162">Akcja wycofania</span><span class="sxs-lookup"><span data-stu-id="1a522-162">Reversal action</span></span>

| <span data-ttu-id="1a522-163">Data</span><span class="sxs-lookup"><span data-stu-id="1a522-163">Date</span></span>      | <span data-ttu-id="1a522-164">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="1a522-164">Transaction type</span></span>               | <span data-ttu-id="1a522-165">Kwota</span><span class="sxs-lookup"><span data-stu-id="1a522-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="1a522-166">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="1a522-166">January 1</span></span> | <span data-ttu-id="1a522-167">Zapisanie korekty amortyzacji</span><span class="sxs-lookup"><span data-stu-id="1a522-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="1a522-168">–1000,00</span><span class="sxs-lookup"><span data-stu-id="1a522-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="1a522-169">Końcowa wartość amortyzacji</span><span class="sxs-lookup"><span data-stu-id="1a522-169">Depreciation effect</span></span>

| <span data-ttu-id="1a522-170">Data</span><span class="sxs-lookup"><span data-stu-id="1a522-170">Date</span></span>        | <span data-ttu-id="1a522-171">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="1a522-171">Transaction type</span></span>        | <span data-ttu-id="1a522-172">Kwota</span><span class="sxs-lookup"><span data-stu-id="1a522-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="1a522-173">28 lutego</span><span class="sxs-lookup"><span data-stu-id="1a522-173">February 28</span></span> | <span data-ttu-id="1a522-174">Amortyzacja (propozycja)</span><span class="sxs-lookup"><span data-stu-id="1a522-174">Depreciation (proposal)</span></span> | <span data-ttu-id="1a522-175">983.62 Obliczenie: wartość księgowa (59 000 - amortyzacja 966,67) / liczba pozostałych okresów amortyzacji (59)</span><span class="sxs-lookup"><span data-stu-id="1a522-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="1a522-176">Amortyzacja jest zaniżona o 16,95 (983,62 – 966,67).</span><span class="sxs-lookup"><span data-stu-id="1a522-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="additional-resources"></a><span data-ttu-id="1a522-177">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1a522-177">Additional resources</span></span>
--------

[<span data-ttu-id="1a522-178">Amortyzacja środka trwałego</span><span class="sxs-lookup"><span data-stu-id="1a522-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)



