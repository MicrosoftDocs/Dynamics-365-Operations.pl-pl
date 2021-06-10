---
title: Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management
description: W tym temacie opisano sposób przypisywania ikon kroków i tytułów dla nowych lub dostosowanych przepływów zadań w aplikacji mobilnej Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049371"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="76d03-103">Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="76d03-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76d03-104">W tym temacie opisano sposób przypisywania ikon kroków i tytułów kroków dla nowych lub dostosowanych przepływów zadań w aplikacji mobilnej Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="76d03-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="76d03-105">Na ilustracjach pokazano, jak ikony kroku i tytuły kroku pojawiają się w aplikacji mobilnej Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="76d03-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="76d03-106">![Przykład ikony kroku i tytułu kroku w aplikacji mobilnej Warehouse Management](media/step-icon-example.png "Przykład ikony kroku i tytułu kroku w aplikacji mobilnej Warehouse Management")</span><span class="sxs-lookup"><span data-stu-id="76d03-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="76d03-107">Włączanie funkcji w systemie</span><span class="sxs-lookup"><span data-stu-id="76d03-107">Turn on this feature in your system</span></span>

<span data-ttu-id="76d03-108">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="76d03-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="76d03-109">Administratorzy mogą skorzystać z ustawień [Zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="76d03-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="76d03-110">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="76d03-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="76d03-111">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="76d03-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="76d03-112">**Nazwa funkcji:** *ustawienia użytkownika, ikony i tytuły kroków dla nowej aplikacji magazynowej*</span><span class="sxs-lookup"><span data-stu-id="76d03-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="76d03-113">Standardowe identyfikatory kroków, klasy i ikony</span><span class="sxs-lookup"><span data-stu-id="76d03-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="76d03-114">Każdy krok w przepływie zadań jest identyfikowany za pomocą identyfikatora kroku, a każdy identyfikator kroku ma odpowiednią klasę kroku.</span><span class="sxs-lookup"><span data-stu-id="76d03-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="76d03-115">Ikona kroku i tytuł są określone w każdej klasie kroku.</span><span class="sxs-lookup"><span data-stu-id="76d03-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="76d03-116">Identyfikatory kroków i klasy kroków</span><span class="sxs-lookup"><span data-stu-id="76d03-116">Step IDs and step classes</span></span>

<span data-ttu-id="76d03-117">W poniższej tabeli wymieniono wszystkie dostępne identyfikatory kroków oraz odpowiadającą im klasę kroku.</span><span class="sxs-lookup"><span data-stu-id="76d03-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="76d03-118">Jako identyfikator kroku jest używana nazwa formantu podstawowego pola wejściowego.</span><span class="sxs-lookup"><span data-stu-id="76d03-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="76d03-119">Przykład pokazujący, jak są używane identyfikatory i klasy kroków, można znaleźć w implementacji metody `WHSMobileAppStepInfoBuilder.stepId()` w sekcji [Przykład: Przydzielanie ikon i tytułów kroków dla przepływu niestandardowego](#example) w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="76d03-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="76d03-120">Identyfikator kroku</span><span class="sxs-lookup"><span data-stu-id="76d03-120">Step ID</span></span> | <span data-ttu-id="76d03-121">Klasa kroku</span><span class="sxs-lookup"><span data-stu-id="76d03-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="76d03-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-122">BatchDisposition</span></span> | <span data-ttu-id="76d03-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="76d03-124">Przewoźnik</span><span class="sxs-lookup"><span data-stu-id="76d03-124">Carrier</span></span> | <span data-ttu-id="76d03-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="76d03-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="76d03-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-126">CatchWeight</span></span> | <span data-ttu-id="76d03-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="76d03-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="76d03-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="76d03-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="76d03-130">CatchWeightTag</span></span> | <span data-ttu-id="76d03-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="76d03-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="76d03-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="76d03-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="76d03-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="76d03-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="76d03-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="76d03-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="76d03-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="76d03-136">CheckDigit</span></span> | <span data-ttu-id="76d03-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="76d03-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="76d03-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="76d03-138">ClusterId</span></span> | <span data-ttu-id="76d03-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="76d03-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="76d03-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="76d03-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="76d03-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="76d03-142">ClusterPosition</span></span> | <span data-ttu-id="76d03-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="76d03-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="76d03-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="76d03-144">ConfigId</span></span> | <span data-ttu-id="76d03-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="76d03-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="76d03-146">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="76d03-146">Confirmation</span></span> | <span data-ttu-id="76d03-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="76d03-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="76d03-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="76d03-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="76d03-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="76d03-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="76d03-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="76d03-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="76d03-154">ContainerType</span></span> | <span data-ttu-id="76d03-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="76d03-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="76d03-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="76d03-156">CountingReasonCode</span></span> | <span data-ttu-id="76d03-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="76d03-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="76d03-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="76d03-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="76d03-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="76d03-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="76d03-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="76d03-160">CycleCountQty1</span></span> | <span data-ttu-id="76d03-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="76d03-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="76d03-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="76d03-162">CycleCountQty2</span></span> | <span data-ttu-id="76d03-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="76d03-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="76d03-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="76d03-164">CycleCountQty3</span></span> | <span data-ttu-id="76d03-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="76d03-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="76d03-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="76d03-166">CycleCountQty4</span></span> | <span data-ttu-id="76d03-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="76d03-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="76d03-168">Disposition</span><span class="sxs-lookup"><span data-stu-id="76d03-168">Disposition</span></span> | <span data-ttu-id="76d03-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="76d03-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="76d03-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="76d03-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="76d03-172">DriverCheckInId</span></span> | <span data-ttu-id="76d03-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="76d03-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="76d03-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="76d03-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="76d03-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="76d03-176">DriverCheckOutId</span></span> | <span data-ttu-id="76d03-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="76d03-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="76d03-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="76d03-178">ExpDate</span></span> | <span data-ttu-id="76d03-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="76d03-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="76d03-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-180">FromBatchDisposition</span></span> | <span data-ttu-id="76d03-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="76d03-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="76d03-182">FromInventoryStatus</span></span> | <span data-ttu-id="76d03-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="76d03-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="76d03-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="76d03-184">FullQty</span></span> | <span data-ttu-id="76d03-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="76d03-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="76d03-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="76d03-186">InboundPut</span></span> | <span data-ttu-id="76d03-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="76d03-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="76d03-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="76d03-188">InventBatchId</span></span> | <span data-ttu-id="76d03-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="76d03-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="76d03-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="76d03-190">InventColorId</span></span> | <span data-ttu-id="76d03-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="76d03-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="76d03-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-192">InventLocation</span></span> | <span data-ttu-id="76d03-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="76d03-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="76d03-194">InventLocationId</span></span> | <span data-ttu-id="76d03-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="76d03-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="76d03-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="76d03-196">InventSerialId</span></span> | <span data-ttu-id="76d03-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="76d03-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="76d03-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="76d03-198">InventSizeId</span></span> | <span data-ttu-id="76d03-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="76d03-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="76d03-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="76d03-200">InventStatusId</span></span> | <span data-ttu-id="76d03-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="76d03-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="76d03-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="76d03-202">InventStyleId</span></span> | <span data-ttu-id="76d03-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="76d03-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="76d03-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="76d03-204">InventVersionId</span></span> | <span data-ttu-id="76d03-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="76d03-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="76d03-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="76d03-206">ItemId</span></span> | <span data-ttu-id="76d03-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="76d03-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="76d03-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="76d03-208">ITMContainerID</span></span> | <span data-ttu-id="76d03-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="76d03-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="76d03-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="76d03-210">ITMShipmentID</span></span> | <span data-ttu-id="76d03-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="76d03-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="76d03-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="76d03-212">KanbanCardId</span></span> | <span data-ttu-id="76d03-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="76d03-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="76d03-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="76d03-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="76d03-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="76d03-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="76d03-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="76d03-216">KanbanOrCardId</span></span> | <span data-ttu-id="76d03-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="76d03-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="76d03-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-218">LicensePlateId</span></span> | <span data-ttu-id="76d03-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="76d03-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="76d03-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="76d03-220">LoadId</span></span> | <span data-ttu-id="76d03-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="76d03-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="76d03-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="76d03-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="76d03-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="76d03-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="76d03-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="76d03-224">LocOrLP</span></span> | <span data-ttu-id="76d03-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="76d03-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="76d03-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="76d03-226">LocOrLP_From</span></span> | <span data-ttu-id="76d03-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="76d03-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="76d03-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="76d03-228">LocOrLP_To</span></span> | <span data-ttu-id="76d03-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="76d03-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="76d03-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="76d03-230">LocOrLPCheck</span></span> | <span data-ttu-id="76d03-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="76d03-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="76d03-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-232">LocVerification</span></span> | <span data-ttu-id="76d03-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="76d03-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="76d03-234">LPAdjustIn</span></span> | <span data-ttu-id="76d03-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="76d03-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="76d03-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="76d03-236">LPBreakChildLP</span></span> | <span data-ttu-id="76d03-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="76d03-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="76d03-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="76d03-238">LPBreakParentLP</span></span> | <span data-ttu-id="76d03-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="76d03-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="76d03-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="76d03-240">LPBuildChildLP</span></span> | <span data-ttu-id="76d03-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="76d03-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="76d03-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="76d03-242">LPBuildParentLP</span></span> | <span data-ttu-id="76d03-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="76d03-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="76d03-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-244">LPVerification</span></span> | <span data-ttu-id="76d03-245">WHSMobileAppStepLPVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="76d03-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="76d03-246">MergeContainerId</span></span> | <span data-ttu-id="76d03-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="76d03-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="76d03-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-248">MixedLPLineNum</span></span> | <span data-ttu-id="76d03-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="76d03-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="76d03-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="76d03-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="76d03-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="76d03-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="76d03-252">MovementConfirmCancel</span></span> | <span data-ttu-id="76d03-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="76d03-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="76d03-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-254">NewCaptureWeight</span></span> | <span data-ttu-id="76d03-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="76d03-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="76d03-256">NewQty</span></span> | <span data-ttu-id="76d03-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="76d03-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="76d03-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="76d03-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="76d03-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="76d03-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="76d03-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="76d03-260">OutboundPut</span></span> | <span data-ttu-id="76d03-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="76d03-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="76d03-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-262">OutboundWeight</span></span> | <span data-ttu-id="76d03-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="76d03-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-264">OverridePutNewLocation</span></span> | <span data-ttu-id="76d03-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="76d03-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="76d03-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="76d03-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-268">POLineNum</span></span> | <span data-ttu-id="76d03-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="76d03-270">PONum</span><span class="sxs-lookup"><span data-stu-id="76d03-270">PONum</span></span> | <span data-ttu-id="76d03-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="76d03-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="76d03-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="76d03-272">PositionFull</span></span> | <span data-ttu-id="76d03-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="76d03-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="76d03-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="76d03-274">PositionFullQty</span></span> | <span data-ttu-id="76d03-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="76d03-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="76d03-276">Zawartość</span><span class="sxs-lookup"><span data-stu-id="76d03-276">Potency</span></span> | <span data-ttu-id="76d03-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="76d03-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="76d03-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="76d03-278">PrinterName</span></span> | <span data-ttu-id="76d03-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="76d03-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="76d03-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="76d03-280">ProdId</span></span> | <span data-ttu-id="76d03-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="76d03-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="76d03-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="76d03-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="76d03-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-284">ProductConfirmation</span></span> | <span data-ttu-id="76d03-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="76d03-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="76d03-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="76d03-288">Odłożenie</span><span class="sxs-lookup"><span data-stu-id="76d03-288">Put</span></span> | <span data-ttu-id="76d03-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="76d03-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="76d03-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="76d03-290">PutawayClusterId</span></span> | <span data-ttu-id="76d03-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="76d03-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="76d03-292">Ilość</span><span class="sxs-lookup"><span data-stu-id="76d03-292">Qty</span></span> | <span data-ttu-id="76d03-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="76d03-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="76d03-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="76d03-294">QtyAdjust</span></span> | <span data-ttu-id="76d03-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="76d03-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="76d03-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="76d03-296">QtyShort</span></span> | <span data-ttu-id="76d03-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="76d03-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="76d03-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="76d03-298">QtyToConsume</span></span> | <span data-ttu-id="76d03-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="76d03-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="76d03-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="76d03-300">QtyToPick</span></span> | <span data-ttu-id="76d03-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="76d03-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="76d03-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="76d03-302">QtyToPut</span></span> | <span data-ttu-id="76d03-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="76d03-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="76d03-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="76d03-304">QtyToScrap</span></span> | <span data-ttu-id="76d03-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="76d03-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="76d03-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-306">QtyVerification</span></span> | <span data-ttu-id="76d03-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="76d03-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="76d03-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="76d03-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="76d03-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="76d03-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="76d03-310">ReasonString</span></span> | <span data-ttu-id="76d03-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="76d03-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="76d03-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="76d03-312">RecvLocationId</span></span> | <span data-ttu-id="76d03-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="76d03-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="76d03-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="76d03-314">RemoveContainerId</span></span> | <span data-ttu-id="76d03-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="76d03-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="76d03-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="76d03-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="76d03-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="76d03-318">RMANum</span></span> | <span data-ttu-id="76d03-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="76d03-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="76d03-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="76d03-320">ShortPickReason</span></span> | <span data-ttu-id="76d03-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="76d03-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="76d03-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="76d03-322">SortConOrLP</span></span> | <span data-ttu-id="76d03-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="76d03-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="76d03-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-324">SortLicensePlateId</span></span> | <span data-ttu-id="76d03-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="76d03-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="76d03-326">SortPositionId</span></span> | <span data-ttu-id="76d03-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="76d03-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="76d03-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-328">SortVerification</span></span> | <span data-ttu-id="76d03-329">WHSMobileAppStepSortVerification</span><span class="sxs-lookup"><span data-stu-id="76d03-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="76d03-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="76d03-330">StartLocationId</span></span> | <span data-ttu-id="76d03-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="76d03-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="76d03-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="76d03-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="76d03-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-334">TargetLicensePlateId</span></span> | <span data-ttu-id="76d03-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="76d03-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-336">TOLineNum</span></span> | <span data-ttu-id="76d03-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="76d03-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-338">ToLocation</span></span> | <span data-ttu-id="76d03-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="76d03-340">TONum</span><span class="sxs-lookup"><span data-stu-id="76d03-340">TONum</span></span> | <span data-ttu-id="76d03-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="76d03-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="76d03-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="76d03-342">ToWarehouse</span></span> | <span data-ttu-id="76d03-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="76d03-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="76d03-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="76d03-344">TransportLoadId</span></span> | <span data-ttu-id="76d03-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="76d03-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="76d03-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="76d03-346">WaveLabelId</span></span> | <span data-ttu-id="76d03-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="76d03-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="76d03-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="76d03-348">WaveLblQty</span></span> | <span data-ttu-id="76d03-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="76d03-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="76d03-350">Masa</span><span class="sxs-lookup"><span data-stu-id="76d03-350">Weight</span></span> | <span data-ttu-id="76d03-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="76d03-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="76d03-352">WeightToConsume</span></span> | <span data-ttu-id="76d03-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="76d03-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="76d03-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="76d03-354">WHSAdjustmentType</span></span> | <span data-ttu-id="76d03-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="76d03-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="76d03-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="76d03-356">WHSReceivingException</span></span> | <span data-ttu-id="76d03-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="76d03-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="76d03-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="76d03-358">WHSWorkException</span></span> | <span data-ttu-id="76d03-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="76d03-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="76d03-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="76d03-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="76d03-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="76d03-362">WMSLocationId</span></span> | <span data-ttu-id="76d03-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="76d03-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="76d03-364">WorkId</span></span> | <span data-ttu-id="76d03-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="76d03-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="76d03-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="76d03-366">WorkIdToCancel</span></span> | <span data-ttu-id="76d03-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="76d03-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="76d03-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="76d03-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="76d03-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="76d03-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="76d03-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="76d03-370">WorkPoolId</span></span> | <span data-ttu-id="76d03-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="76d03-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="76d03-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="76d03-372">ZoneId</span></span> | <span data-ttu-id="76d03-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="76d03-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="76d03-374">Dostępne ikony kroków</span><span class="sxs-lookup"><span data-stu-id="76d03-374">Available step icons</span></span>

<span data-ttu-id="76d03-375">System zawiera kolekcję standardowych ikon kroków, których można także używać w niestandardowych krokach.</span><span class="sxs-lookup"><span data-stu-id="76d03-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="76d03-376">Nie można obecnie przekazywać niestandardowych ikon kroku.</span><span class="sxs-lookup"><span data-stu-id="76d03-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="76d03-377">W związku z tym należy zawsze wybrać jedną ze standardowych ikon kroków.</span><span class="sxs-lookup"><span data-stu-id="76d03-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="76d03-378">W poniższej tabeli pokazano każdą aktualnie dostępną ikonę kroku oraz jej nazwę.</span><span class="sxs-lookup"><span data-stu-id="76d03-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Informacje o ikonie kroku"><br><span data-ttu-id="76d03-380">Informacje o</span><span class="sxs-lookup"><span data-stu-id="76d03-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Dodaj numer identyfikacyjny lub ikonę kroku pozycji"><br><span data-ttu-id="76d03-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="76d03-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Ikona kroku dyspozycji partii"><br><span data-ttu-id="76d03-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Ikona kroku przewoźnika"><br><span data-ttu-id="76d03-386">Przewoźnik</span><span class="sxs-lookup"><span data-stu-id="76d03-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Ikona kroku znacznika ilości efektywnej"><br><span data-ttu-id="76d03-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="76d03-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Ikona kroku znacznika ilości efektywnej"><br><span data-ttu-id="76d03-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Ikona kroku cyfry kontrolnej"><br><span data-ttu-id="76d03-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="76d03-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Ikona kroku ID zameldowania lub wymeldowania"><br><span data-ttu-id="76d03-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="76d03-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Ikona kroku podrzędnego — numer identyfikacyjny"><br><span data-ttu-id="76d03-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="76d03-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Ikona kroku identyfikatora grupy"><br><span data-ttu-id="76d03-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="76d03-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Ikona pozycji kroku grupy"><br><span data-ttu-id="76d03-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="76d03-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Ikona identyfikatora konfiguracji kroku"><br><span data-ttu-id="76d03-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="76d03-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Ikona skonfigurowanego pola korku"><br><span data-ttu-id="76d03-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="76d03-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Ikona kroku Con lub LP"><br><span data-ttu-id="76d03-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="76d03-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Konsolidacja z ikony kroku dla identyfikatora identyfikacyjnego"><br><span data-ttu-id="76d03-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="76d03-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Konsolidacja do ikony kroku dla identyfikatora identyfikacyjnego"><br><span data-ttu-id="76d03-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="76d03-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Ikona kroku typu kontenera"><br><span data-ttu-id="76d03-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="76d03-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Ikona kroku inwentaryzacji"><br><span data-ttu-id="76d03-414">Inwentaryzacja</span><span class="sxs-lookup"><span data-stu-id="76d03-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Ikona kroku kodu przyczyny inwentaryzacji"><br><span data-ttu-id="76d03-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="76d03-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Ikona kroku kodu kraju pochodzenia"><br><span data-ttu-id="76d03-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="76d03-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Ikona kroku dyspozycji"><br><span data-ttu-id="76d03-420">Disposition</span><span class="sxs-lookup"><span data-stu-id="76d03-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Ikona Krok gotowe"><br><span data-ttu-id="76d03-422">Zakończono</span><span class="sxs-lookup"><span data-stu-id="76d03-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Ikona kroku potwierdzenia odprawy kierowcy"><br><span data-ttu-id="76d03-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Ikona kroku identyfikacji kierowcy"><br><span data-ttu-id="76d03-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="76d03-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Ikona kroku zakończenia identyfikacji kierowcy"><br><span data-ttu-id="76d03-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="76d03-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Ikona kroku daty ważności"><br><span data-ttu-id="76d03-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="76d03-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Ikona skonfigurowanego pola"><br><span data-ttu-id="76d03-432">Pole</span><span class="sxs-lookup"><span data-stu-id="76d03-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Ikona kroku dyspozycji partii od"><br><span data-ttu-id="76d03-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="76d03-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Ikona Krok stanu magazynu z"><br><span data-ttu-id="76d03-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="76d03-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Ikona kroku identyfikatora atrybutu"><br><span data-ttu-id="76d03-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="76d03-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Ikona kroku identyfikatora partii zapasów"><br><span data-ttu-id="76d03-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="76d03-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Ikona kroku identyfikatora koloru"><br><span data-ttu-id="76d03-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="76d03-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Ikona kroku identyfikatora lokalizacji"><br><span data-ttu-id="76d03-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Ikona kroku identyfikatora serializowania"><br><span data-ttu-id="76d03-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="76d03-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Ikona kroku identyfikatora rozmiaru"><br><span data-ttu-id="76d03-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="76d03-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Ikona kroku identyfikatora stanu zapasów"><br><span data-ttu-id="76d03-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="76d03-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Ikona kroku identyfikatora stylu"><br><span data-ttu-id="76d03-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="76d03-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Ikona kroku identyfikatora wersji zapasów"><br><span data-ttu-id="76d03-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="76d03-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Ikona identyfikatora elementu kroku"><br><span data-ttu-id="76d03-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="76d03-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Ikona kroku identyfikatora kontenera ITM"><br><span data-ttu-id="76d03-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="76d03-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Ikona kroku identyfikatora wysyłki ITM"><br><span data-ttu-id="76d03-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="76d03-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Ikona kroku identyfikatora karty Kanban"><br><span data-ttu-id="76d03-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="76d03-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Ikona kroku identyfikatora karty lub Kanban"><br><span data-ttu-id="76d03-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="76d03-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Ikona kroku — numer identyfikacyjny"><br><span data-ttu-id="76d03-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="76d03-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Ikona identyfikatora ładowania kroku"><br><span data-ttu-id="76d03-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="76d03-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Ikona stopnia położenia numeru identyfikacyjnego"><br><span data-ttu-id="76d03-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="76d03-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Ikona kroku lokalizacji lub numeru identyfikacyjnego"><br><span data-ttu-id="76d03-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="76d03-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Ikona kroku lokalizacji lub sprawdzania numeru identyfikacyjnego"><br><span data-ttu-id="76d03-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="76d03-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Ikona kroku od lokalizacji lub numeru identyfikacyjnego"><br><span data-ttu-id="76d03-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="76d03-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Ikona kroku lokalizacji lub numeru identyfikacyjnego do"><br><span data-ttu-id="76d03-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="76d03-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Ikona kroku zakończonego długiego procesu"><br><span data-ttu-id="76d03-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="76d03-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Ikona kroku nadrzędnego LP podziału LP"><br><span data-ttu-id="76d03-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="76d03-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Ikona kroku identyfikatora kontenera scalania"><br><span data-ttu-id="76d03-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="76d03-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Ikona kroku numeru mieszanego numeru identyfikacyjnych"><br><span data-ttu-id="76d03-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Ikona kroku wagi wychodzącej"><br><span data-ttu-id="76d03-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="76d03-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Ikona kroku właściciela"><br><span data-ttu-id="76d03-490">Właściciel</span><span class="sxs-lookup"><span data-stu-id="76d03-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Ikona kroku nadrzędnego — numer identyfikacyjny"><br><span data-ttu-id="76d03-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="76d03-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Potwierdź ikonę kroku"><br><span data-ttu-id="76d03-494">PleaseConfirm</span><span class="sxs-lookup"><span data-stu-id="76d03-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Ikona kroku numeru linii zamówienia"><br><span data-ttu-id="76d03-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Ikona kroku numeru zamówienia"><br><span data-ttu-id="76d03-498">PONum</span><span class="sxs-lookup"><span data-stu-id="76d03-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Ikona pełnego kroku pozycji"><br><span data-ttu-id="76d03-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="76d03-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Ikona kroku zawartości"><br><span data-ttu-id="76d03-502">Zawartość</span><span class="sxs-lookup"><span data-stu-id="76d03-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Ikona kroku nazwy drukarki"><br><span data-ttu-id="76d03-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="76d03-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Ikona identyfikatora produkcji kroku"><br><span data-ttu-id="76d03-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="76d03-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Ikona kroku potwierdzenia produktu"><br><span data-ttu-id="76d03-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Informacje o dodaniu kroku"><br><span data-ttu-id="76d03-510">Odłożenie</span><span class="sxs-lookup"><span data-stu-id="76d03-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Ikona kroku identyfikatora grupy odłożenia"><br><span data-ttu-id="76d03-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="76d03-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Ikona Kroku ilości"><br><span data-ttu-id="76d03-514">Ilość</span><span class="sxs-lookup"><span data-stu-id="76d03-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Korygowanie ilości w ikonie kroku"><br><span data-ttu-id="76d03-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="76d03-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Ikona krótkiego kroku ilości"><br><span data-ttu-id="76d03-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="76d03-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Ikona Ilości do zużywania w kroku"><br><span data-ttu-id="76d03-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="76d03-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Ikona Ilości do dołożenia w kroku"><br><span data-ttu-id="76d03-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="76d03-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Ikona Ilości do odrzucenia w kroku"><br><span data-ttu-id="76d03-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="76d03-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Ikona kroku potwierdzenia ilości"><br><span data-ttu-id="76d03-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="76d03-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Ikona kroku zadania zakończenia zgłoszenia jako gotowego"><br><span data-ttu-id="76d03-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="76d03-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Ikona kroku identyfikatora lokalizacji odbierania"><br><span data-ttu-id="76d03-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="76d03-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Ikona kroku identyfikatora kontenera usuwania"><br><span data-ttu-id="76d03-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="76d03-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Ikona stopnia numeru RMA"><br><span data-ttu-id="76d03-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="76d03-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Wybierz ikonę kolejność kroków"><br><span data-ttu-id="76d03-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="76d03-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Ikona krótkiego kroku uzasadnienia wyboru"><br><span data-ttu-id="76d03-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="76d03-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Ikona kroku identyfikatora stanowiska sortowania"><br><span data-ttu-id="76d03-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="76d03-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Ikona kroku — docelowy numer identyfikacyjny"><br><span data-ttu-id="76d03-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Ikona Krok numeru wiersza do"><br><span data-ttu-id="76d03-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="76d03-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Ikona kroku identyfikatora lokalizacji do"><br><span data-ttu-id="76d03-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="76d03-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Ikona kroku numeru do"><br><span data-ttu-id="76d03-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="76d03-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Ikona kroku magazynu do"><br><span data-ttu-id="76d03-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="76d03-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Ikona stopnia identyfikacji ładunku transportowego"><br><span data-ttu-id="76d03-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="76d03-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Ikona kroku ID partii dostawcy"><br><span data-ttu-id="76d03-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="76d03-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Ikona kroku identyfikatora etykiety grupy czynności"><br><span data-ttu-id="76d03-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="76d03-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Ikona kroku etykiety jakości grupy czynności"><br><span data-ttu-id="76d03-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="76d03-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Ikona kroku wagi"><br><span data-ttu-id="76d03-560">Masa</span><span class="sxs-lookup"><span data-stu-id="76d03-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Ikona wagi do zużywania w kroku"><br><span data-ttu-id="76d03-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="76d03-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Ikona kroku dostosowania magazynu"><br><span data-ttu-id="76d03-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="76d03-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Ikona kroku wyjątku odbioru WHS"><br><span data-ttu-id="76d03-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="76d03-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Ikona kroku ID lokalizacji WMS"><br><span data-ttu-id="76d03-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="76d03-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Ikona stopnia Work ID"><br><span data-ttu-id="76d03-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="76d03-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Identyfikator pracy do anulowania ikony kroku"><br><span data-ttu-id="76d03-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="76d03-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Ikona kroku — numer identyfikacyjny pracy"><br><span data-ttu-id="76d03-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="76d03-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Ikona kroku — numer identyfikacyjny grupy odłożenia"><br><span data-ttu-id="76d03-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="76d03-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Ikona puli identyfikatora pracy"><br><span data-ttu-id="76d03-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="76d03-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Ikona stopnia identyfikatora strefy"><br><span data-ttu-id="76d03-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="76d03-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="76d03-581">Przykład: Przypisywanie ikon i tytułów kroków dla przepływu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="76d03-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="76d03-582">Ten przykład wyjaśnia, jak ustawić ikony i tytuły kroków dla niestandardowego przepływu zadań.</span><span class="sxs-lookup"><span data-stu-id="76d03-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="76d03-583">Scenariusz jest zbudowany na przykładzie niestandardowego przepływu zadań, który jest przedstawiony i zbadany bardziej szczegółowo w poniższym wpisie na blogu: [Dostosowywanie w aplikacji mobilnej Warehousing](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="76d03-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="76d03-584">Przepływ zadań działa w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="76d03-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="76d03-585">Aplikacja wyświetla stronę, na której pracownik proszony jest o podanie identyfikatora pojemnika (np. poprzez zeskanowanie kodu kreskowego).</span><span class="sxs-lookup"><span data-stu-id="76d03-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="76d03-586">Jeśli identyfikator pojemnika jest prawidłowy, aplikacja otwiera nową stronę, na której pracownik proszony jest o podanie wagi.</span><span class="sxs-lookup"><span data-stu-id="76d03-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="76d03-587">(Jeśli identyfikator kontenera nie jest poprawny, pracownik wraca na pierwszą stronę).</span><span class="sxs-lookup"><span data-stu-id="76d03-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="76d03-588">Gdy pracownik wprowadzi prawidłową wagę, system zapisuje wagę i odsyła pracownika na pierwszą stronę.</span><span class="sxs-lookup"><span data-stu-id="76d03-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="76d03-589">Poniższa ilustracja przedstawia ten przepływ zadań.</span><span class="sxs-lookup"><span data-stu-id="76d03-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="76d03-590">![Diagram przepływu zadania](media/step-icons-example-task-flow.png "Diagram przepływu zadania")</span><span class="sxs-lookup"><span data-stu-id="76d03-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="76d03-591">Utwórz klasę kroku dla strony wejściowej kontenera</span><span class="sxs-lookup"><span data-stu-id="76d03-591">Create a step class for the container input page</span></span>

<span data-ttu-id="76d03-592">Strona wprowadzania danych o pojemniku umożliwia pracownikowi zeskanowanie lub wprowadzenie identyfikatora pojemnika.</span><span class="sxs-lookup"><span data-stu-id="76d03-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="76d03-593">![Strona danych wejściowych kontenera](media/step-icons-example-container-input.png "Strona danych wejściowych kontenera")</span><span class="sxs-lookup"><span data-stu-id="76d03-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="76d03-594">Na stronie wprowadzania danych w kontenerze, nazwa kontrolki dla pola wejściowego to `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="76d03-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="76d03-595">Ta nazwa formantu nie znajduje się na [liście identyfikatorów kroków](#step-ids-classes), więc nie będzie można odnaleźć istniejącego kroku opartego na tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="76d03-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="76d03-596">Dlatego musisz utworzyć klasę kroku, która będzie reprezentować krok.</span><span class="sxs-lookup"><span data-stu-id="76d03-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="76d03-597">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="76d03-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="76d03-598">Identyfikator ikony kroku jest przechowywany w klasie członka `defaultStepIcon`, a tytuł kroku jest przechowywany w klasie członka `defaultStepTitle`.</span><span class="sxs-lookup"><span data-stu-id="76d03-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="76d03-599">Aby przypisać ikonę kroku, ustaw jeden z identyfikatorów `defaultStepIcon` na ikonę wymienioną w sekcji [Dostępne ikony kroków](#step-icons) wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="76d03-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="76d03-600">Użyj standardowej lub niestandardowej ikony kroku i tytułu dla wprowadzanej wagi</span><span class="sxs-lookup"><span data-stu-id="76d03-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="76d03-601">Strona wprowadzania wagi pozwala pracownikowi na wprowadzenie wagi.</span><span class="sxs-lookup"><span data-stu-id="76d03-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="76d03-602">![Strona wprowadzania wagi](media/step-icons-example-weight-input.png "Strona wprowadzania wagi")</span><span class="sxs-lookup"><span data-stu-id="76d03-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="76d03-603">Na stronie wprowadzania wagi nazwa formantu pola wejściowego `Weight` znajduje się na [liście identyfikatorów kroków](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="76d03-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="76d03-604">Jeśli więc ikona kroku i tytuł zdefiniowane w klasie `WHSMobileAppStepWeight` są dla Ciebie akceptowane, nie musisz nic zmieniać w tym kroku.</span><span class="sxs-lookup"><span data-stu-id="76d03-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="76d03-605">Jeśli jednak w tym kroku preferujesz użycie innej ikony lub tytułu, możesz zastąpić metodę `stepId()` lub metodę `stepInfo()` w klasie konstruktora.</span><span class="sxs-lookup"><span data-stu-id="76d03-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="76d03-606">Każdy przepływ zadania ma własny konstruktor informacji krokowych.</span><span class="sxs-lookup"><span data-stu-id="76d03-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="76d03-607">Zastąp metodę stepId()</span><span class="sxs-lookup"><span data-stu-id="76d03-607">Override the stepId() method</span></span>

<span data-ttu-id="76d03-608">W tym przykładzie pokazano jeden sposób modyfikowania klasy konstruktora przez zastąpienie metody `stepId()`.</span><span class="sxs-lookup"><span data-stu-id="76d03-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="76d03-609">Następnie należy utworzyć klasę kroku `NewWeight` dla tego kroku.</span><span class="sxs-lookup"><span data-stu-id="76d03-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="76d03-610">Kod powinien przypominać kod dla przykładu `ContainerId` pokazanego wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="76d03-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="76d03-611">Zastąp metodę stepInfo()</span><span class="sxs-lookup"><span data-stu-id="76d03-611">Override the stepInfo() method</span></span>

<span data-ttu-id="76d03-612">W tym przykładzie pokazano jeden sposób modyfikowania klasy konstruktora przez zastąpienie metody `stepInfo()`.</span><span class="sxs-lookup"><span data-stu-id="76d03-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="76d03-613">Następnie można konstruować obiekt `WHSMobileAppStepInfo` i ustawiać bezpośrednio ikonę i/lub tytuł.</span><span class="sxs-lookup"><span data-stu-id="76d03-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76d03-614">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="76d03-614">Additional resources</span></span>

- [<span data-ttu-id="76d03-615">Instalowanie i łączenie aplikacji mobilnej Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="76d03-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="76d03-616">Ustawienia użytkownika urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="76d03-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
