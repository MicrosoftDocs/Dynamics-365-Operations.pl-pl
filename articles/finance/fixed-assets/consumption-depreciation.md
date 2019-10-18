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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c9d95a7a45ed99c63516749285126c786685c87
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187321"
---
# <a name="consumption-depreciation"></a><span data-ttu-id="d22a1-103">Amortyzacja według zużycia</span><span class="sxs-lookup"><span data-stu-id="d22a1-103">Consumption depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d22a1-104">Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja według zużycia.</span><span class="sxs-lookup"><span data-stu-id="d22a1-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="d22a1-105">Jeśli podczas ustawiania profilu amortyzacji środków trwałych zaznaczono opcję **Zużycie** w polu **Metoda** na stronie **Profile amortyzacji**, środki trwałe będą przypisane do profilu amortyzacji na podstawie ich zużycia.</span><span class="sxs-lookup"><span data-stu-id="d22a1-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="d22a1-106">Nie trzeba ustawiać wartość procentowych i interwałów na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="d22a1-107">Po utworzeniu profilu amortyzacji używającego metody Zużycie można ustawić metodę na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="d22a1-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="d22a1-108">Konfigurowanie i używanie amortyzacji według zużycia</span><span class="sxs-lookup"><span data-stu-id="d22a1-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="d22a1-109">Utwórz profil amortyzacji na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="d22a1-110">Do obliczeń zużycia profil amortyzacji musi zawierać identyfikator i nazwę, a w polu **Metoda** trzeba zaznaczyć **Zużycie**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="d22a1-111">Na stronie **Współczynniki zużycia** ustaw współczynniki zużycia.</span><span class="sxs-lookup"><span data-stu-id="d22a1-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="d22a1-112">Każdy współczynnik zużycia musi mieć identyfikator i nazwę, i musi być wyrażony jako ilość lub wartość procentowa.</span><span class="sxs-lookup"><span data-stu-id="d22a1-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="d22a1-113">Na stronie **Jednostki zużycia** ustaw jednostki zużycia.</span><span class="sxs-lookup"><span data-stu-id="d22a1-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="d22a1-114">Każda jednostka zużycia musi mieć identyfikator i nazwę.</span><span class="sxs-lookup"><span data-stu-id="d22a1-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="d22a1-115">Jednostki amortyzacji są używane do obliczania amortyzacji wg zużycia na stronie **amortyzacji według zużycia**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="d22a1-116">Przykładowymi jednostkami są km, kg i godzina.</span><span class="sxs-lookup"><span data-stu-id="d22a1-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="d22a1-117">Na stronie **środki trwałe** ustaw poszczególne środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="d22a1-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="d22a1-118">Dla każdego środka trwałego wybierz modele ewidencji i księgi amortyzacji z profilami amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="d22a1-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="d22a1-119">Należy ustawić modele ewidencji lub księgi amortyzacji dla amortyzacji według zużycia, jeśli jakikolwiek ze środków trwałych używa profili amortyzacji opartych na metodzie Zużycia.</span><span class="sxs-lookup"><span data-stu-id="d22a1-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="d22a1-120">Ta konfiguracja jest przeprowadzana albo na karcie **amortyzacji** na stronie **Modele ewidencji**, albo na skróconej karcie **Ogólne** na stronie **profilu amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="d22a1-121">Jeden model ewidencji można stosować dla wielu środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="d22a1-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="d22a1-122">Profile amortyzacji są częścią modelu ewidencji lub księgi amortyzacji wybranych dla każdego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="d22a1-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="d22a1-123">Nie można dodawać lub modyfikować profili amortyzacji bezpośrednio na stronie **Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="d22a1-124">Profile amortyzacji można zmodyfikować tylko na stronie **ksiąg amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="d22a1-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="d22a1-125">Na stronie **Modele ewidencji** lub **Księgi amortyzacji** w grupie pól **amortyzacji według zużycia** wprowadź informacje w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="d22a1-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="d22a1-126">Współczynnik zużycia</span><span class="sxs-lookup"><span data-stu-id="d22a1-126">Consumption factor</span></span>
    -   <span data-ttu-id="d22a1-127">Jednostka</span><span class="sxs-lookup"><span data-stu-id="d22a1-127">Unit</span></span>
    -   <span data-ttu-id="d22a1-128">Jednostka amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d22a1-128">Unit depreciation</span></span>
    -   <span data-ttu-id="d22a1-129">Szacunkowe zużycie</span><span class="sxs-lookup"><span data-stu-id="d22a1-129">Estimated consumption</span></span>

    <span data-ttu-id="d22a1-130">W polu **Zaksięgowane zużycie** jest wyświetlona wartość amortyzacji według zużycia (w jednostkach), która została już zaksięgowana w modelu ewidencji środków trwałych lub w księdze amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="d22a1-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="d22a1-131">Wartość w tym polu nie można ręcznie zmienić wartości.</span><span class="sxs-lookup"><span data-stu-id="d22a1-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="d22a1-132">Przykłady</span><span class="sxs-lookup"><span data-stu-id="d22a1-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="d22a1-133">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="d22a1-133">Example 1</span></span>

<span data-ttu-id="d22a1-134">31 stycznia ustawiono następujący współczynnik zużycia:</span><span class="sxs-lookup"><span data-stu-id="d22a1-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="d22a1-135">Ilość wynosi 1000.</span><span class="sxs-lookup"><span data-stu-id="d22a1-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="d22a1-136">Jednostka amortyzacji, która jest określona dla środka trwałego, wynosi 1,5.</span><span class="sxs-lookup"><span data-stu-id="d22a1-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="d22a1-137">Propozycja amortyzacji na 31 stycznia jest następująca: ilość x jednostka amortyzacji 1000 x 1,5 = 1500, jeśli współczynnik określony dla środka trwałego ustawiono jako procentowy, ilość, którą oblicza się w polu **szacowane zużycie** dla modelu ewidencji środka trwałego jest mnożona przez wartość procentową ustawioną dla wybranej daty końcowej.</span><span class="sxs-lookup"><span data-stu-id="d22a1-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="d22a1-138">Tak obliczona ilość jest sugerowana jako wielkość amortyzacji dla okresu.</span><span class="sxs-lookup"><span data-stu-id="d22a1-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="d22a1-139">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="d22a1-139">Example 2</span></span>

<span data-ttu-id="d22a1-140">Dla 31 stycznia ustawiono następujący współczynnik amortyzacji według zużycia:</span><span class="sxs-lookup"><span data-stu-id="d22a1-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="d22a1-141">Wartość procentowa wynosi 10 procent.</span><span class="sxs-lookup"><span data-stu-id="d22a1-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="d22a1-142">Jednostka amortyzacji, która jest określona dla środka trwałego, wynosi 1,5.</span><span class="sxs-lookup"><span data-stu-id="d22a1-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="d22a1-143">Szacowana ilość środka trwałego wynosi 2000.</span><span class="sxs-lookup"><span data-stu-id="d22a1-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="d22a1-144">Propozycja amortyzacji na 31 stycznia jest w następująca: szacowana ilość x procent x Jednostka amortyzacji 2000 x 0,10 x 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="d22a1-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>



