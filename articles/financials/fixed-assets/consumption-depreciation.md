---
title: Amortyzacja według zużycia
description: Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja według zużycia.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0f64fee275f63a3e6b31a196df872e41c84dde6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "319691"
---
# <a name="consumption-depreciation"></a><span data-ttu-id="678cc-103">Amortyzacja według zużycia</span><span class="sxs-lookup"><span data-stu-id="678cc-103">Consumption depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="678cc-104">Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja według zużycia.</span><span class="sxs-lookup"><span data-stu-id="678cc-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="678cc-105">Jeśli podczas ustawiania profilu amortyzacji środków trwałych zaznaczono opcję **Zużycie** w polu **Metoda** na stronie **Profile amortyzacji**, środki trwałe będą przypisane do profilu amortyzacji na podstawie ich zużycia.</span><span class="sxs-lookup"><span data-stu-id="678cc-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="678cc-106">Nie trzeba ustawiać wartość procentowych i interwałów na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="678cc-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="678cc-107">Po utworzeniu profilu amortyzacji używającego metody Zużycie można ustawić metodę na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="678cc-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="678cc-108">Konfigurowanie i używanie amortyzacji według zużycia</span><span class="sxs-lookup"><span data-stu-id="678cc-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="678cc-109">Utwórz profil amortyzacji na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="678cc-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="678cc-110">Do obliczeń zużycia profil amortyzacji musi zawierać identyfikator i nazwę, a w polu **Metoda** trzeba zaznaczyć **Zużycie**.</span><span class="sxs-lookup"><span data-stu-id="678cc-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="678cc-111">Na stronie **Współczynniki zużycia** ustaw współczynniki zużycia.</span><span class="sxs-lookup"><span data-stu-id="678cc-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="678cc-112">Każdy współczynnik zużycia musi mieć identyfikator i nazwę, i musi być wyrażony jako ilość lub wartość procentowa.</span><span class="sxs-lookup"><span data-stu-id="678cc-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="678cc-113">Na stronie **Jednostki zużycia** ustaw jednostki zużycia.</span><span class="sxs-lookup"><span data-stu-id="678cc-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="678cc-114">Każda jednostka zużycia musi mieć identyfikator i nazwę.</span><span class="sxs-lookup"><span data-stu-id="678cc-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="678cc-115">Jednostki amortyzacji są używane do obliczania amortyzacji wg zużycia na stronie **amortyzacji według zużycia**.</span><span class="sxs-lookup"><span data-stu-id="678cc-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="678cc-116">Przykładowymi jednostkami są km, kg i godzina.</span><span class="sxs-lookup"><span data-stu-id="678cc-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="678cc-117">Na stronie **środki trwałe** ustaw poszczególne środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="678cc-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="678cc-118">Dla każdego środka trwałego wybierz modele ewidencji i księgi amortyzacji z profilami amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="678cc-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="678cc-119">Należy ustawić modele ewidencji lub księgi amortyzacji dla amortyzacji według zużycia, jeśli jakikolwiek ze środków trwałych używa profili amortyzacji opartych na metodzie Zużycia.</span><span class="sxs-lookup"><span data-stu-id="678cc-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="678cc-120">Ta konfiguracja jest przeprowadzana albo na karcie **amortyzacji** na stronie **Modele ewidencji**, albo na skróconej karcie **Ogólne** na stronie **profilu amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="678cc-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="678cc-121">Jeden model ewidencji można stosować dla wielu środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="678cc-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="678cc-122">Profile amortyzacji są częścią modelu ewidencji lub księgi amortyzacji wybranych dla każdego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="678cc-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="678cc-123">Nie można dodawać lub modyfikować profili amortyzacji bezpośrednio na stronie **Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="678cc-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="678cc-124">Profile amortyzacji można zmodyfikować tylko na stronie **ksiąg amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="678cc-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="678cc-125">Na stronie **Modele ewidencji** lub **Księgi amortyzacji** w grupie pól **amortyzacji według zużycia** wprowadź informacje w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="678cc-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="678cc-126">Współczynnik zużycia</span><span class="sxs-lookup"><span data-stu-id="678cc-126">Consumption factor</span></span>
    -   <span data-ttu-id="678cc-127">Jednostka</span><span class="sxs-lookup"><span data-stu-id="678cc-127">Unit</span></span>
    -   <span data-ttu-id="678cc-128">Jednostka amortyzacji</span><span class="sxs-lookup"><span data-stu-id="678cc-128">Unit depreciation</span></span>
    -   <span data-ttu-id="678cc-129">Szacunkowe zużycie</span><span class="sxs-lookup"><span data-stu-id="678cc-129">Estimated consumption</span></span>

    <span data-ttu-id="678cc-130">W polu **Zaksięgowane zużycie** jest wyświetlona wartość amortyzacji według zużycia (w jednostkach), która została już zaksięgowana w modelu ewidencji środków trwałych lub w księdze amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="678cc-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="678cc-131">Wartość w tym polu nie można ręcznie zmienić wartości.</span><span class="sxs-lookup"><span data-stu-id="678cc-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="678cc-132">Przykłady</span><span class="sxs-lookup"><span data-stu-id="678cc-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="678cc-133">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="678cc-133">Example 1</span></span>

<span data-ttu-id="678cc-134">31 stycznia ustawiono następujący współczynnik zużycia:</span><span class="sxs-lookup"><span data-stu-id="678cc-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="678cc-135">Ilość wynosi 1000.</span><span class="sxs-lookup"><span data-stu-id="678cc-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="678cc-136">Jednostka amortyzacji, która jest określona dla środka trwałego, wynosi 1,5.</span><span class="sxs-lookup"><span data-stu-id="678cc-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="678cc-137">Propozycja amortyzacji na 31 stycznia jest następująca: ilość x jednostka amortyzacji 1000 x 1,5 = 1500, jeśli współczynnik określony dla środka trwałego ustawiono jako procentowy, ilość, którą oblicza się w polu **szacowane zużycie** dla modelu ewidencji środka trwałego jest mnożona przez wartość procentową ustawioną dla wybranej daty końcowej.</span><span class="sxs-lookup"><span data-stu-id="678cc-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="678cc-138">Tak obliczona ilość jest sugerowana jako wielkość amortyzacji dla okresu.</span><span class="sxs-lookup"><span data-stu-id="678cc-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="678cc-139">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="678cc-139">Example 2</span></span>

<span data-ttu-id="678cc-140">Dla 31 stycznia ustawiono następujący współczynnik amortyzacji według zużycia:</span><span class="sxs-lookup"><span data-stu-id="678cc-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="678cc-141">Wartość procentowa wynosi 10 procent.</span><span class="sxs-lookup"><span data-stu-id="678cc-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="678cc-142">Jednostka amortyzacji, która jest określona dla środka trwałego, wynosi 1,5.</span><span class="sxs-lookup"><span data-stu-id="678cc-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="678cc-143">Szacowana ilość środka trwałego wynosi 2000.</span><span class="sxs-lookup"><span data-stu-id="678cc-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="678cc-144">Propozycja amortyzacji na 31 stycznia jest w następująca: szacowana ilość x procent x Jednostka amortyzacji 2000 x 0,10 x 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="678cc-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>



