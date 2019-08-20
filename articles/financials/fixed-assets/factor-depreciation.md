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
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840536"
---
# <a name="factor-depreciation"></a><span data-ttu-id="d534d-103">Amortyzacja czynnikowa</span><span class="sxs-lookup"><span data-stu-id="d534d-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d534d-104">Ten artykuł zawiera omówienie metody amortyzacji współczynnikowej.</span><span class="sxs-lookup"><span data-stu-id="d534d-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="d534d-105">Czynniki to wartości procentowe używane do amortyzacji środków.</span><span class="sxs-lookup"><span data-stu-id="d534d-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="d534d-106">Po konfiguracji profilu amortyzacji środka trwałego i wybraniu wartości **Współczynnik** w polu **Metoda** na stronie **Profile amortyzacji** można skonfigurować amortyzację progresywną, degresywną lub liniową:</span><span class="sxs-lookup"><span data-stu-id="d534d-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="d534d-107">W przypadku wybrania amortyzacji progresywnej kwota wzrasta z każdym okresem amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="d534d-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="d534d-108">W przypadku wybrania amortyzacji degresywnej kwota amortyzacji na okres systematycznie spada.</span><span class="sxs-lookup"><span data-stu-id="d534d-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="d534d-109">W przypadku wybrania amortyzacji liniowej amortyzacja jest taka sama w każdym okresie.</span><span class="sxs-lookup"><span data-stu-id="d534d-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="d534d-110">Poniższe reguły i przykłady wskazują, jak można skonfigurować czynniki dla każdego typu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="d534d-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d534d-111">Po wybraniu opcji **Współczynnik** w polu **Metoda** zostaną wyświetlone pola **Współczynnik** i **Interwał**.</span><span class="sxs-lookup"><span data-stu-id="d534d-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="d534d-112">Amortyzacja progresywna</span><span class="sxs-lookup"><span data-stu-id="d534d-112">Progressive depreciation</span></span>
<span data-ttu-id="d534d-113">Wartość w polu **Współczynnik** jest większa niż **50**.</span><span class="sxs-lookup"><span data-stu-id="d534d-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="d534d-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="d534d-114">Example</span></span>

<span data-ttu-id="d534d-115">Cena nabycia wynosi 100,000, współczynnik wynosi 70, okres użytkowania to 10 lat, a data początkowa amortyzacji to 1 stycznia.</span><span class="sxs-lookup"><span data-stu-id="d534d-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="d534d-116">Kwoty amortyzacji i kwoty wartości księgowej netto będą wyświetlane tylko przez pierwsze sześć lat okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="d534d-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="d534d-117">Rok</span><span class="sxs-lookup"><span data-stu-id="d534d-117">Year</span></span> | <span data-ttu-id="d534d-118">Okres</span><span class="sxs-lookup"><span data-stu-id="d534d-118">Period</span></span>      | <span data-ttu-id="d534d-119">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d534d-119">Depreciation amount</span></span> | <span data-ttu-id="d534d-120">Kwota wartości księgowej netto</span><span class="sxs-lookup"><span data-stu-id="d534d-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="d534d-121">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="d534d-121">1</span></span>    | <span data-ttu-id="d534d-122">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-122">December 31</span></span> | <span data-ttu-id="d534d-123">307,69</span><span class="sxs-lookup"><span data-stu-id="d534d-123">307.69</span></span>              | <span data-ttu-id="d534d-124">99692,31</span><span class="sxs-lookup"><span data-stu-id="d534d-124">99,692.31</span></span>             |
| <span data-ttu-id="d534d-125">2</span><span class="sxs-lookup"><span data-stu-id="d534d-125">2</span></span>    | <span data-ttu-id="d534d-126">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-126">December 31</span></span> | <span data-ttu-id="d534d-127">1447,21</span><span class="sxs-lookup"><span data-stu-id="d534d-127">1,447.21</span></span>            | <span data-ttu-id="d534d-128">98,245.10</span><span class="sxs-lookup"><span data-stu-id="d534d-128">98,245.10</span></span>             |
| <span data-ttu-id="d534d-129">3</span><span class="sxs-lookup"><span data-stu-id="d534d-129">3</span></span>    | <span data-ttu-id="d534d-130">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-130">December 31</span></span> | <span data-ttu-id="d534d-131">3104,50</span><span class="sxs-lookup"><span data-stu-id="d534d-131">3,104.50</span></span>            | <span data-ttu-id="d534d-132">95,140.60</span><span class="sxs-lookup"><span data-stu-id="d534d-132">95,140.60</span></span>             |
| <span data-ttu-id="d534d-133">4</span><span class="sxs-lookup"><span data-stu-id="d534d-133">4</span></span>    | <span data-ttu-id="d534d-134">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-134">December 31</span></span> | <span data-ttu-id="d534d-135">5150,21</span><span class="sxs-lookup"><span data-stu-id="d534d-135">5,150.21</span></span>            | <span data-ttu-id="d534d-136">89,990.39</span><span class="sxs-lookup"><span data-stu-id="d534d-136">89,990.39</span></span>             |
| <span data-ttu-id="d534d-137">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="d534d-137">5</span></span>    | <span data-ttu-id="d534d-138">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-138">December 31</span></span> | <span data-ttu-id="d534d-139">7522,95</span><span class="sxs-lookup"><span data-stu-id="d534d-139">7,522.95</span></span>            | <span data-ttu-id="d534d-140">82,467.44</span><span class="sxs-lookup"><span data-stu-id="d534d-140">82,467.44</span></span>             |
| <span data-ttu-id="d534d-141">6</span><span class="sxs-lookup"><span data-stu-id="d534d-141">6</span></span>    | <span data-ttu-id="d534d-142">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-142">December 31</span></span> | <span data-ttu-id="d534d-143">10184,06</span><span class="sxs-lookup"><span data-stu-id="d534d-143">10,184.06</span></span>           | <span data-ttu-id="d534d-144">72,283.38</span><span class="sxs-lookup"><span data-stu-id="d534d-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="d534d-145">Amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="d534d-145">Digressive depreciation</span></span>
<span data-ttu-id="d534d-146">Wartość w polu **Współczynnik** jest mniejsza niż **50**.</span><span class="sxs-lookup"><span data-stu-id="d534d-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="d534d-147">Przykład</span><span class="sxs-lookup"><span data-stu-id="d534d-147">Example</span></span>

<span data-ttu-id="d534d-148">Cena nabycia wynosi 100,000, współczynnik wynosi 20, okres użytkowania to 10 lat, a data początkowa amortyzacji to 1 stycznia.</span><span class="sxs-lookup"><span data-stu-id="d534d-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="d534d-149">Kwoty amortyzacji i kwoty wartości księgowej netto będą wyświetlane tylko przez pierwsze sześć lat okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="d534d-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="d534d-150">Rok</span><span class="sxs-lookup"><span data-stu-id="d534d-150">Year</span></span> | <span data-ttu-id="d534d-151">Okres</span><span class="sxs-lookup"><span data-stu-id="d534d-151">Period</span></span>      | <span data-ttu-id="d534d-152">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d534d-152">Depreciation amount</span></span> | <span data-ttu-id="d534d-153">Kwota wartości księgowej netto</span><span class="sxs-lookup"><span data-stu-id="d534d-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="d534d-154">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="d534d-154">1</span></span>    | <span data-ttu-id="d534d-155">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-155">December 31</span></span> | <span data-ttu-id="d534d-156">56080,43</span><span class="sxs-lookup"><span data-stu-id="d534d-156">56,080.43</span></span>           | <span data-ttu-id="d534d-157">43,919.57</span><span class="sxs-lookup"><span data-stu-id="d534d-157">43,919.57</span></span>             |
| <span data-ttu-id="d534d-158">2</span><span class="sxs-lookup"><span data-stu-id="d534d-158">2</span></span>    | <span data-ttu-id="d534d-159">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-159">December 31</span></span> | <span data-ttu-id="d534d-160">10665,70</span><span class="sxs-lookup"><span data-stu-id="d534d-160">10,665.70</span></span>           | <span data-ttu-id="d534d-161">33,253.87</span><span class="sxs-lookup"><span data-stu-id="d534d-161">33,253.87</span></span>             |
| <span data-ttu-id="d534d-162">3</span><span class="sxs-lookup"><span data-stu-id="d534d-162">3</span></span>    | <span data-ttu-id="d534d-163">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-163">December 31</span></span> | <span data-ttu-id="d534d-164">7156,22</span><span class="sxs-lookup"><span data-stu-id="d534d-164">7,156.22</span></span>            | <span data-ttu-id="d534d-165">26,097.65</span><span class="sxs-lookup"><span data-stu-id="d534d-165">26,097.65</span></span>             |
| <span data-ttu-id="d534d-166">4</span><span class="sxs-lookup"><span data-stu-id="d534d-166">4</span></span>    | <span data-ttu-id="d534d-167">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-167">December 31</span></span> | <span data-ttu-id="d534d-168">5538,06</span><span class="sxs-lookup"><span data-stu-id="d534d-168">5,538.06</span></span>            | <span data-ttu-id="d534d-169">20,559.59</span><span class="sxs-lookup"><span data-stu-id="d534d-169">20,559.59</span></span>             |
| <span data-ttu-id="d534d-170">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="d534d-170">5</span></span>    | <span data-ttu-id="d534d-171">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-171">December 31</span></span> | <span data-ttu-id="d534d-172">4579,89</span><span class="sxs-lookup"><span data-stu-id="d534d-172">4,579.89</span></span>            | <span data-ttu-id="d534d-173">15,979.70</span><span class="sxs-lookup"><span data-stu-id="d534d-173">15,979.70</span></span>             |
| <span data-ttu-id="d534d-174">6</span><span class="sxs-lookup"><span data-stu-id="d534d-174">6</span></span>    | <span data-ttu-id="d534d-175">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="d534d-175">December 31</span></span> | <span data-ttu-id="d534d-176">3937,36</span><span class="sxs-lookup"><span data-stu-id="d534d-176">3,937.36</span></span>            | <span data-ttu-id="d534d-177">12,042.34</span><span class="sxs-lookup"><span data-stu-id="d534d-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="d534d-178">Amortyzacja liniowa</span><span class="sxs-lookup"><span data-stu-id="d534d-178">Straight line depreciation</span></span>
<span data-ttu-id="d534d-179">Wartość w polu **Współczynnik** jest równa **50**.</span><span class="sxs-lookup"><span data-stu-id="d534d-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="d534d-180">W tym przypadku amortyzacja jest taka sama w każdym okresie i powinno się uwzględnić w innych polach wybrane wartości, zgodnie z informacjami zawartymi w temacie [Amortyzację za liniowy okres użytkowania](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="d534d-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>



