---
title: Amortyzacja czynnikowa
description: Ten artykuł zawiera omówienie metody amortyzacji współczynnikowej.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4920f7f90b859006ecdcd486eaa9f4449442e51a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976148"
---
# <a name="factor-depreciation"></a><span data-ttu-id="dc2c4-103">Amortyzacja czynnikowa</span><span class="sxs-lookup"><span data-stu-id="dc2c4-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc2c4-104">Ten artykuł zawiera omówienie metody amortyzacji współczynnikowej.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="dc2c4-105">Czynniki to wartości procentowe używane do amortyzacji środków.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="dc2c4-106">Po konfiguracji profilu amortyzacji środka trwałego i wybraniu wartości **Współczynnik** w polu **Metoda** na stronie **Profile amortyzacji** można skonfigurować amortyzację progresywną, degresywną lub liniową:</span><span class="sxs-lookup"><span data-stu-id="dc2c4-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="dc2c4-107">W przypadku wybrania amortyzacji progresywnej kwota wzrasta z każdym okresem amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="dc2c4-108">W przypadku wybrania amortyzacji degresywnej kwota amortyzacji na okres systematycznie spada.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="dc2c4-109">W przypadku wybrania amortyzacji liniowej amortyzacja jest taka sama w każdym okresie.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="dc2c4-110">Poniższe reguły i przykłady wskazują, jak można skonfigurować czynniki dla każdego typu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="dc2c4-111">Po wybraniu opcji **Współczynnik** w polu **Metoda** zostaną wyświetlone pola **Współczynnik** i **Interwał**.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="dc2c4-112">Amortyzacja progresywna</span><span class="sxs-lookup"><span data-stu-id="dc2c4-112">Progressive depreciation</span></span>
<span data-ttu-id="dc2c4-113">Wartość w polu **Współczynnik** jest większa niż **50**.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="dc2c4-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="dc2c4-114">Example</span></span>

<span data-ttu-id="dc2c4-115">Cena nabycia wynosi 100,000, współczynnik wynosi 70, okres użytkowania to 10 lat, a data początkowa amortyzacji to 1 stycznia.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="dc2c4-116">Kwoty amortyzacji i kwoty wartości księgowej netto będą wyświetlane tylko przez pierwsze sześć lat okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="dc2c4-117">Rok</span><span class="sxs-lookup"><span data-stu-id="dc2c4-117">Year</span></span> | <span data-ttu-id="dc2c4-118">Okres</span><span class="sxs-lookup"><span data-stu-id="dc2c4-118">Period</span></span>      | <span data-ttu-id="dc2c4-119">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dc2c4-119">Depreciation amount</span></span> | <span data-ttu-id="dc2c4-120">Kwota wartości księgowej netto</span><span class="sxs-lookup"><span data-stu-id="dc2c4-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="dc2c4-121">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="dc2c4-121">1</span></span>    | <span data-ttu-id="dc2c4-122">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-122">December 31</span></span> | <span data-ttu-id="dc2c4-123">307,69</span><span class="sxs-lookup"><span data-stu-id="dc2c4-123">307.69</span></span>              | <span data-ttu-id="dc2c4-124">99692,31</span><span class="sxs-lookup"><span data-stu-id="dc2c4-124">99,692.31</span></span>             |
| <span data-ttu-id="dc2c4-125">2</span><span class="sxs-lookup"><span data-stu-id="dc2c4-125">2</span></span>    | <span data-ttu-id="dc2c4-126">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-126">December 31</span></span> | <span data-ttu-id="dc2c4-127">1447,21</span><span class="sxs-lookup"><span data-stu-id="dc2c4-127">1,447.21</span></span>            | <span data-ttu-id="dc2c4-128">98,245.10</span><span class="sxs-lookup"><span data-stu-id="dc2c4-128">98,245.10</span></span>             |
| <span data-ttu-id="dc2c4-129">3</span><span class="sxs-lookup"><span data-stu-id="dc2c4-129">3</span></span>    | <span data-ttu-id="dc2c4-130">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-130">December 31</span></span> | <span data-ttu-id="dc2c4-131">3104,50</span><span class="sxs-lookup"><span data-stu-id="dc2c4-131">3,104.50</span></span>            | <span data-ttu-id="dc2c4-132">95,140.60</span><span class="sxs-lookup"><span data-stu-id="dc2c4-132">95,140.60</span></span>             |
| <span data-ttu-id="dc2c4-133">4</span><span class="sxs-lookup"><span data-stu-id="dc2c4-133">4</span></span>    | <span data-ttu-id="dc2c4-134">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-134">December 31</span></span> | <span data-ttu-id="dc2c4-135">5150,21</span><span class="sxs-lookup"><span data-stu-id="dc2c4-135">5,150.21</span></span>            | <span data-ttu-id="dc2c4-136">89,990.39</span><span class="sxs-lookup"><span data-stu-id="dc2c4-136">89,990.39</span></span>             |
| <span data-ttu-id="dc2c4-137">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="dc2c4-137">5</span></span>    | <span data-ttu-id="dc2c4-138">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-138">December 31</span></span> | <span data-ttu-id="dc2c4-139">7522,95</span><span class="sxs-lookup"><span data-stu-id="dc2c4-139">7,522.95</span></span>            | <span data-ttu-id="dc2c4-140">82,467.44</span><span class="sxs-lookup"><span data-stu-id="dc2c4-140">82,467.44</span></span>             |
| <span data-ttu-id="dc2c4-141">6</span><span class="sxs-lookup"><span data-stu-id="dc2c4-141">6</span></span>    | <span data-ttu-id="dc2c4-142">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-142">December 31</span></span> | <span data-ttu-id="dc2c4-143">10184,06</span><span class="sxs-lookup"><span data-stu-id="dc2c4-143">10,184.06</span></span>           | <span data-ttu-id="dc2c4-144">72,283.38</span><span class="sxs-lookup"><span data-stu-id="dc2c4-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="dc2c4-145">Amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="dc2c4-145">Digressive depreciation</span></span>
<span data-ttu-id="dc2c4-146">Wartość w polu **Współczynnik** jest mniejsza niż **50**.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="dc2c4-147">Przykład</span><span class="sxs-lookup"><span data-stu-id="dc2c4-147">Example</span></span>

<span data-ttu-id="dc2c4-148">Cena nabycia wynosi 100,000, współczynnik wynosi 20, okres użytkowania to 10 lat, a data początkowa amortyzacji to 1 stycznia.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="dc2c4-149">Kwoty amortyzacji i kwoty wartości księgowej netto będą wyświetlane tylko przez pierwsze sześć lat okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="dc2c4-150">Rok</span><span class="sxs-lookup"><span data-stu-id="dc2c4-150">Year</span></span> | <span data-ttu-id="dc2c4-151">Okres</span><span class="sxs-lookup"><span data-stu-id="dc2c4-151">Period</span></span>      | <span data-ttu-id="dc2c4-152">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dc2c4-152">Depreciation amount</span></span> | <span data-ttu-id="dc2c4-153">Kwota wartości księgowej netto</span><span class="sxs-lookup"><span data-stu-id="dc2c4-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="dc2c4-154">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="dc2c4-154">1</span></span>    | <span data-ttu-id="dc2c4-155">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-155">December 31</span></span> | <span data-ttu-id="dc2c4-156">56080,43</span><span class="sxs-lookup"><span data-stu-id="dc2c4-156">56,080.43</span></span>           | <span data-ttu-id="dc2c4-157">43,919.57</span><span class="sxs-lookup"><span data-stu-id="dc2c4-157">43,919.57</span></span>             |
| <span data-ttu-id="dc2c4-158">2</span><span class="sxs-lookup"><span data-stu-id="dc2c4-158">2</span></span>    | <span data-ttu-id="dc2c4-159">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-159">December 31</span></span> | <span data-ttu-id="dc2c4-160">10665,70</span><span class="sxs-lookup"><span data-stu-id="dc2c4-160">10,665.70</span></span>           | <span data-ttu-id="dc2c4-161">33,253.87</span><span class="sxs-lookup"><span data-stu-id="dc2c4-161">33,253.87</span></span>             |
| <span data-ttu-id="dc2c4-162">3</span><span class="sxs-lookup"><span data-stu-id="dc2c4-162">3</span></span>    | <span data-ttu-id="dc2c4-163">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-163">December 31</span></span> | <span data-ttu-id="dc2c4-164">7156,22</span><span class="sxs-lookup"><span data-stu-id="dc2c4-164">7,156.22</span></span>            | <span data-ttu-id="dc2c4-165">26,097.65</span><span class="sxs-lookup"><span data-stu-id="dc2c4-165">26,097.65</span></span>             |
| <span data-ttu-id="dc2c4-166">4</span><span class="sxs-lookup"><span data-stu-id="dc2c4-166">4</span></span>    | <span data-ttu-id="dc2c4-167">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-167">December 31</span></span> | <span data-ttu-id="dc2c4-168">5538,06</span><span class="sxs-lookup"><span data-stu-id="dc2c4-168">5,538.06</span></span>            | <span data-ttu-id="dc2c4-169">20,559.59</span><span class="sxs-lookup"><span data-stu-id="dc2c4-169">20,559.59</span></span>             |
| <span data-ttu-id="dc2c4-170">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="dc2c4-170">5</span></span>    | <span data-ttu-id="dc2c4-171">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-171">December 31</span></span> | <span data-ttu-id="dc2c4-172">4579,89</span><span class="sxs-lookup"><span data-stu-id="dc2c4-172">4,579.89</span></span>            | <span data-ttu-id="dc2c4-173">15,979.70</span><span class="sxs-lookup"><span data-stu-id="dc2c4-173">15,979.70</span></span>             |
| <span data-ttu-id="dc2c4-174">6</span><span class="sxs-lookup"><span data-stu-id="dc2c4-174">6</span></span>    | <span data-ttu-id="dc2c4-175">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="dc2c4-175">December 31</span></span> | <span data-ttu-id="dc2c4-176">3937,36</span><span class="sxs-lookup"><span data-stu-id="dc2c4-176">3,937.36</span></span>            | <span data-ttu-id="dc2c4-177">12,042.34</span><span class="sxs-lookup"><span data-stu-id="dc2c4-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="dc2c4-178">Amortyzacja liniowa</span><span class="sxs-lookup"><span data-stu-id="dc2c4-178">Straight line depreciation</span></span>
<span data-ttu-id="dc2c4-179">Wartość w polu **Współczynnik** jest równa **50**.</span><span class="sxs-lookup"><span data-stu-id="dc2c4-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="dc2c4-180">W tym przypadku amortyzacja jest taka sama w każdym okresie i powinno się uwzględnić w innych polach wybrane wartości, zgodnie z informacjami zawartymi w temacie [Amortyzację za liniowy okres użytkowania](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="dc2c4-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>



