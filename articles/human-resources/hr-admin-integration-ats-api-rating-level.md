---
title: Poziom oceniania
description: W tym temacie opisano jednostkę Poziom oceniania dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eac80599de07a045aa233f1cdfd16fe0db8733a2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800340"
---
# <a name="rating-level"></a><span data-ttu-id="31dce-103">Poziom oceniania</span><span class="sxs-lookup"><span data-stu-id="31dce-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="31dce-104">W tym temacie opisano jednostkę Poziom oceniania dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="31dce-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="31dce-105">Nazwa fizyczna: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="31dce-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="31dce-106">opis</span><span class="sxs-lookup"><span data-stu-id="31dce-106">Description</span></span>

<span data-ttu-id="31dce-107">Ta jednostka udostępnia dostępne poziomy oceniania kwalifikacji.</span><span class="sxs-lookup"><span data-stu-id="31dce-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="31dce-108">Poziomy oceniania obowiązują dla wszystkich firm.</span><span class="sxs-lookup"><span data-stu-id="31dce-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="31dce-109">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="31dce-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="31dce-110">Właściwości</span><span class="sxs-lookup"><span data-stu-id="31dce-110">Properties</span></span>

| <span data-ttu-id="31dce-111">Właściwość</span><span class="sxs-lookup"><span data-stu-id="31dce-111">Property</span></span><br><span data-ttu-id="31dce-112">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="31dce-112">**Physical name**</span></span><br><span data-ttu-id="31dce-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="31dce-113">**_Type_**</span></span> | <span data-ttu-id="31dce-114">Użycie</span><span class="sxs-lookup"><span data-stu-id="31dce-114">Use</span></span> | <span data-ttu-id="31dce-115">opis</span><span class="sxs-lookup"><span data-stu-id="31dce-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="31dce-116">**Identyfikator jednostki na poziomie oceny**</span><span class="sxs-lookup"><span data-stu-id="31dce-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="31dce-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="31dce-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="31dce-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="31dce-118">*GUID*</span></span> | <span data-ttu-id="31dce-119">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="31dce-119">Read-only</span></span><br><span data-ttu-id="31dce-120">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-120">Required</span></span><br><span data-ttu-id="31dce-121">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="31dce-121">System-generated</span></span> | <span data-ttu-id="31dce-122">Wygenerowany przez system unikatowy identyfikator poziomu.</span><span class="sxs-lookup"><span data-stu-id="31dce-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="31dce-123">**Identyfikator poziomu oceny**</span><span class="sxs-lookup"><span data-stu-id="31dce-123">**Rating Level ID**</span></span><br><span data-ttu-id="31dce-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="31dce-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="31dce-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="31dce-125">*String*</span></span> | <span data-ttu-id="31dce-126">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="31dce-126">Read/write</span></span><br><span data-ttu-id="31dce-127">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-127">Required</span></span> | <span data-ttu-id="31dce-128">Czytelny dla użytkownika unikalny identyfikator poziomu.</span><span class="sxs-lookup"><span data-stu-id="31dce-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="31dce-129">**Identyfikator modelu oceny**</span><span class="sxs-lookup"><span data-stu-id="31dce-129">**Rating Model ID**</span></span><br><span data-ttu-id="31dce-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="31dce-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="31dce-131">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="31dce-131">*String*</span></span> | <span data-ttu-id="31dce-132">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="31dce-132">Read/write</span></span><br><span data-ttu-id="31dce-133">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-133">Required</span></span> | <span data-ttu-id="31dce-134">Model oceniania, do którego należy poziom oceniania.</span><span class="sxs-lookup"><span data-stu-id="31dce-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="31dce-135">**Identyfikator jednostki oceny modelu**</span><span class="sxs-lookup"><span data-stu-id="31dce-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="31dce-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="31dce-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="31dce-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="31dce-137">*GUID*</span></span> | <span data-ttu-id="31dce-138">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="31dce-138">Read-only</span></span><br><span data-ttu-id="31dce-139">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-139">Required</span></span><br><span data-ttu-id="31dce-140">Klucz obcy: mshr_hcmratingmodelentityid należący do mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="31dce-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="31dce-141">Wygenerowany przez system identyfikator modelu oceniania, do którego należy poziom oceniania.</span><span class="sxs-lookup"><span data-stu-id="31dce-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="31dce-142">**Opis**</span><span class="sxs-lookup"><span data-stu-id="31dce-142">**Description**</span></span><br><span data-ttu-id="31dce-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="31dce-143">mshr_description</span></span><br><span data-ttu-id="31dce-144">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="31dce-144">*String*</span></span> | <span data-ttu-id="31dce-145">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="31dce-145">Read/write</span></span><br><span data-ttu-id="31dce-146">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-146">Required</span></span> | <span data-ttu-id="31dce-147">Opis poziomu oceny.</span><span class="sxs-lookup"><span data-stu-id="31dce-147">The description of the rating level.</span></span> |
| <span data-ttu-id="31dce-148">**Współczynnik**</span><span class="sxs-lookup"><span data-stu-id="31dce-148">**Factor**</span></span><br><span data-ttu-id="31dce-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="31dce-149">mshr_factor</span></span><br><span data-ttu-id="31dce-150">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="31dce-150">*Integer*</span></span> | <span data-ttu-id="31dce-151">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="31dce-151">Read/write</span></span><br><span data-ttu-id="31dce-152">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-152">Required</span></span> | <span data-ttu-id="31dce-153">Współczynnik poziomu oceny.</span><span class="sxs-lookup"><span data-stu-id="31dce-153">The factor for the rating level.</span></span> <span data-ttu-id="31dce-154">Służy on do normalizacji wyników podczas porównywania towarów z różnymi numerami poziomów oceny.</span><span class="sxs-lookup"><span data-stu-id="31dce-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="31dce-155">Wartość musi być liczbą całkowitą z liczby 0 do 9.</span><span class="sxs-lookup"><span data-stu-id="31dce-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="31dce-156">**Uwaga**</span><span class="sxs-lookup"><span data-stu-id="31dce-156">**Note**</span></span><br><span data-ttu-id="31dce-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="31dce-157">mshr_note</span></span><br><span data-ttu-id="31dce-158">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="31dce-158">*String*</span></span> | <span data-ttu-id="31dce-159">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="31dce-159">Read/write</span></span><br><span data-ttu-id="31dce-160">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="31dce-160">Optional</span></span> | <span data-ttu-id="31dce-161">Wszelkie notatki skojarzone z poziomem oceniania.</span><span class="sxs-lookup"><span data-stu-id="31dce-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="31dce-162">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="31dce-162">**Primary Field**</span></span><br><span data-ttu-id="31dce-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="31dce-163">mshr_primaryfield</span></span><br><span data-ttu-id="31dce-164">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="31dce-164">*String*</span></span> | <span data-ttu-id="31dce-165">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="31dce-165">Read-only</span></span><br><span data-ttu-id="31dce-166">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="31dce-166">Required</span></span> | <span data-ttu-id="31dce-167">Pole, które ma być używane jako identyfikator rekordu encji.</span><span class="sxs-lookup"><span data-stu-id="31dce-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="31dce-168">Kombinacja identyfikatora poziomu oceniania i identyfikatora modelu oceniania.</span><span class="sxs-lookup"><span data-stu-id="31dce-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="31dce-169">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="31dce-169">See also</span></span>

[<span data-ttu-id="31dce-170">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="31dce-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="31dce-171">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="31dce-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]