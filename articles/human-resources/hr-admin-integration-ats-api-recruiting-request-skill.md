---
title: Umiejętność we wniosku o rekrutację
description: W tym temacie opisano jednostkę Umiejętność we wniosku o rekrutację dla Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 83a9956b9aa820e8aca9bf6b2ab920a45c1061f6
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126009"
---
# <a name="recruiting-request-skill"></a><span data-ttu-id="124c0-103">Umiejętność we wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="124c0-103">Recruiting request skill</span></span>

<span data-ttu-id="124c0-104">W tym temacie opisano jednostkę Umiejętność we wniosku o rekrutację dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="124c0-104">This topic describes the Recruiting request skill entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="124c0-105">Nazwa fizyczna: mshr_hcmrecruitingrequestskillentity</span><span class="sxs-lookup"><span data-stu-id="124c0-105">Physical name: mshr_hcmrecruitingrequestskillentity</span></span>

### <a name="description"></a><span data-ttu-id="124c0-106">opis</span><span class="sxs-lookup"><span data-stu-id="124c0-106">Description</span></span>

<span data-ttu-id="124c0-107">Opisuje wymagania dotyczące kwalifikacji dla questu RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="124c0-107">Describes skill requirements for a RecruitingRequest.</span></span>

### <a name="json-representation"></a><span data-ttu-id="124c0-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="124c0-108">JSON representation</span></span>

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a><span data-ttu-id="124c0-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="124c0-109">Properties</span></span>

| <span data-ttu-id="124c0-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="124c0-110">Property</span></span><br><span data-ttu-id="124c0-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="124c0-111">**Physical name**</span></span><br><span data-ttu-id="124c0-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="124c0-112">**_Type_**</span></span> | <span data-ttu-id="124c0-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="124c0-113">Use</span></span> | <span data-ttu-id="124c0-114">opis</span><span class="sxs-lookup"><span data-stu-id="124c0-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="124c0-115">**Identyfikator jednostki Umiejętności we wniosku o rekrutację**</span><span class="sxs-lookup"><span data-stu-id="124c0-115">**Recruiting Request Skill Entity ID**</span></span><br><span data-ttu-id="124c0-116">mshr_hcmrecruitingrequestskillentityid</span><span class="sxs-lookup"><span data-stu-id="124c0-116">mshr_hcmrecruitingrequestskillentityid</span></span><br><span data-ttu-id="124c0-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="124c0-117">*GUID*</span></span> | <span data-ttu-id="124c0-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-118">Read-only</span></span><br><span data-ttu-id="124c0-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-119">Required</span></span> | <span data-ttu-id="124c0-120">Wygenerowany przez system unikalny identyfikator rekordu **Umiejętności we wniosku rekrutacji**.</span><span class="sxs-lookup"><span data-stu-id="124c0-120">System-generated unique identifier for the **Recruiting Request Skill** record.</span></span> |
| <span data-ttu-id="124c0-121">**Identyfikator wniosku o rekrutację**</span><span class="sxs-lookup"><span data-stu-id="124c0-121">**Recruiting Request ID**</span></span><br><span data-ttu-id="124c0-122">mshr_recruitingrequestid</span><span class="sxs-lookup"><span data-stu-id="124c0-122">mshr_recruitingrequestid</span></span><br><span data-ttu-id="124c0-123">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-123">*String*</span></span> | <span data-ttu-id="124c0-124">Odpisz raz</span><span class="sxs-lookup"><span data-stu-id="124c0-124">Write-once</span></span><br><span data-ttu-id="124c0-125">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-125">Required</span></span> | <span data-ttu-id="124c0-126">Odczytywalny przez użytkownika unikatowy identyfikator powiązanego wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="124c0-126">The user-readable unique identifier of the associated recruiting request.</span></span> |
| <span data-ttu-id="124c0-127">**Wartość identyfikatora wniosku o rekrutację**</span><span class="sxs-lookup"><span data-stu-id="124c0-127">**Recruiting Request ID Value**</span></span><br><span data-ttu-id="124c0-128">_mshr_fk_recruitingrequest_id_value</span><span class="sxs-lookup"><span data-stu-id="124c0-128">_mshr_fk_recruitingrequest_id_value</span></span><br><span data-ttu-id="124c0-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="124c0-129">*GUID*</span></span> | <span data-ttu-id="124c0-130">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-130">Read-only</span></span><br><span data-ttu-id="124c0-131">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-131">Required</span></span><br> <span data-ttu-id="124c0-132">Klucz obcy: mshr_hcmrecruitingrequestentityid należący do jednostki mshr_hcmrecruitingrequestentity</span><span class="sxs-lookup"><span data-stu-id="124c0-132">Foreign key: mshr_hcmrecruitingrequestentityid of mshr_hcmrecruitingrequestentity entity</span></span> | <span data-ttu-id="124c0-133">Wygenerowany przez system unikalny identyfikator powiązanego wniosku rekrutacyjnego.</span><span class="sxs-lookup"><span data-stu-id="124c0-133">System-generated unique identifier of the associated recruiting request.</span></span> |
| <span data-ttu-id="124c0-134">**Identyfikator kwalifikacji**</span><span class="sxs-lookup"><span data-stu-id="124c0-134">**Skill ID**</span></span><br><span data-ttu-id="124c0-135">mshr_skillid</span><span class="sxs-lookup"><span data-stu-id="124c0-135">mshr_skillid</span></span><br><span data-ttu-id="124c0-136">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-136">*String*</span></span><br> | <span data-ttu-id="124c0-137">Odpisz raz</span><span class="sxs-lookup"><span data-stu-id="124c0-137">Write-once</span></span><br><span data-ttu-id="124c0-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-138">Required</span></span> | <span data-ttu-id="124c0-139">Odczytywalny przez użytkownika unikatowy identyfikator wymaganej umiejętności.</span><span class="sxs-lookup"><span data-stu-id="124c0-139">The user-readable unique identifier of the required skill.</span></span> |
| <span data-ttu-id="124c0-140">**Wartość identyfikatora kwalifikacji**</span><span class="sxs-lookup"><span data-stu-id="124c0-140">**Skill ID Value**</span></span><br><span data-ttu-id="124c0-141">_mshr_fk_skill_id_value</span><span class="sxs-lookup"><span data-stu-id="124c0-141">_mshr_fk_skill_id_value</span></span><br><span data-ttu-id="124c0-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="124c0-142">*GUID*</span></span> | <span data-ttu-id="124c0-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-143">Read-only</span></span><br><span data-ttu-id="124c0-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-144">Required</span></span><br><span data-ttu-id="124c0-145">Klucz obcy: mshr_hcmskillentityid jednostki mshr_hcmskillentity</span><span class="sxs-lookup"><span data-stu-id="124c0-145">Foreign key: mshr_hcmskillentityid of mshr_hcmskillentity entity</span></span> | <span data-ttu-id="124c0-146">Wygenerowany przez system unikalny identyfikator wymaganej umiejętności.</span><span class="sxs-lookup"><span data-stu-id="124c0-146">System-generated unique identifier of the required skill.</span></span> |
| <span data-ttu-id="124c0-147">**Identyfikator poziomu oceny**</span><span class="sxs-lookup"><span data-stu-id="124c0-147">**Rating Level ID**</span></span><br><span data-ttu-id="124c0-148">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="124c0-148">mshr_ratinglevelid</span></span><br><span data-ttu-id="124c0-149">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-149">*String*</span></span> | <span data-ttu-id="124c0-150">Odpisz raz</span><span class="sxs-lookup"><span data-stu-id="124c0-150">Write-once</span></span><br><span data-ttu-id="124c0-151">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="124c0-151">Optional</span></span> | <span data-ttu-id="124c0-152">Wymagana wartość poziomu umiejętności wybrana dla stanowiska na podstawie modelu oceniania przypisanego do umiejętności.</span><span class="sxs-lookup"><span data-stu-id="124c0-152">The required skill level value selected for the job, based on the rating model assigned to the skill.</span></span> |
| <span data-ttu-id="124c0-153">**Wartość identyfikatora poziomu oceny**</span><span class="sxs-lookup"><span data-stu-id="124c0-153">**Rating Level ID Value**</span></span><br><span data-ttu-id="124c0-154">_mshr_fk_ratinglevel_id_value</span><span class="sxs-lookup"><span data-stu-id="124c0-154">_mshr_fk_ratinglevel_id_value</span></span><br><span data-ttu-id="124c0-155">*GUID*</span><span class="sxs-lookup"><span data-stu-id="124c0-155">*GUID*</span></span> | <span data-ttu-id="124c0-156">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-156">Read-only</span></span><br><span data-ttu-id="124c0-157">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="124c0-157">Optional</span></span><br><span data-ttu-id="124c0-158">Klucz obcy: mshr_hcmratinglevelentityid jednostki mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="124c0-158">Foreign key: mshr_hcmratinglevelentityid of mshr_hcmratinglevelentity entity</span></span> | <span data-ttu-id="124c0-159">Wygenerowany przez system unikatowy identyfikator poziomu.</span><span class="sxs-lookup"><span data-stu-id="124c0-159">System-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="124c0-160">**Opis kwalifikacji**</span><span class="sxs-lookup"><span data-stu-id="124c0-160">**Skill Description**</span></span><br><span data-ttu-id="124c0-161">mshr_skilldescription</span><span class="sxs-lookup"><span data-stu-id="124c0-161">mshr_skilldescription</span></span><br><span data-ttu-id="124c0-162">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-162">*String*</span></span> | <span data-ttu-id="124c0-163">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-163">Read-only</span></span><br><span data-ttu-id="124c0-164">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-164">Required</span></span> | <span data-ttu-id="124c0-165">Opis kwalifikacji.</span><span class="sxs-lookup"><span data-stu-id="124c0-165">The skill description.</span></span> |
| <span data-ttu-id="124c0-166">**Opis poziomu oceniania**</span><span class="sxs-lookup"><span data-stu-id="124c0-166">**Rating Level Description**</span></span><br><span data-ttu-id="124c0-167">mshr_ratingleveldescription</span><span class="sxs-lookup"><span data-stu-id="124c0-167">mshr_ratingleveldescription</span></span><br><span data-ttu-id="124c0-168">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-168">*String*</span></span> | <span data-ttu-id="124c0-169">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-169">Read-only</span></span><br><span data-ttu-id="124c0-170">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="124c0-170">Optional</span></span> | <span data-ttu-id="124c0-171">Opis wybranego poziomu umiejętności.</span><span class="sxs-lookup"><span data-stu-id="124c0-171">The description of the selected skill level.</span></span> |
| <span data-ttu-id="124c0-172">**Identyfikator obszaru danych**</span><span class="sxs-lookup"><span data-stu-id="124c0-172">**Data Area ID**</span></span><br><span data-ttu-id="124c0-173">mshr_dataareaid</span><span class="sxs-lookup"><span data-stu-id="124c0-173">mshr_dataareaid</span></span><br><span data-ttu-id="124c0-174">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-174">*String*</span></span> | <span data-ttu-id="124c0-175">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="124c0-175">Read/write</span></span><br><span data-ttu-id="124c0-176">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="124c0-176">Optional</span></span> | <span data-ttu-id="124c0-177">Określa osobę prawną (firmę).</span><span class="sxs-lookup"><span data-stu-id="124c0-177">Specifies the legal entity (company).</span></span> |
| <span data-ttu-id="124c0-178">**Wartość identyfikatora obszaru danych**</span><span class="sxs-lookup"><span data-stu-id="124c0-178">**Data Area ID Value**</span></span><br><span data-ttu-id="124c0-179">_mshr_dataareaid_id_value</span><span class="sxs-lookup"><span data-stu-id="124c0-179">_mshr_dataareaid_id_value</span></span><br><span data-ttu-id="124c0-180">*GUID*</span><span class="sxs-lookup"><span data-stu-id="124c0-180">*GUID*</span></span> | <span data-ttu-id="124c0-181">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-181">Read-only</span></span><br><span data-ttu-id="124c0-182">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="124c0-182">Optional</span></span><br><span data-ttu-id="124c0-183">Klucz obcy: cdm_companyid jednostki cdm_company obcej</span><span class="sxs-lookup"><span data-stu-id="124c0-183">Foreign key: cdm_companyid of cdm_company entity</span></span> | <span data-ttu-id="124c0-184">Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę).</span><span class="sxs-lookup"><span data-stu-id="124c0-184">System-generated GUID value identifying the legal entity (company).</span></span> |
| <span data-ttu-id="124c0-185">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="124c0-185">**Primary Field**</span></span><br><span data-ttu-id="124c0-186">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="124c0-186">mshr_primaryfield</span></span><br><span data-ttu-id="124c0-187">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-187">*String*</span></span> | <span data-ttu-id="124c0-188">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-188">Read-only</span></span><br><span data-ttu-id="124c0-189">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-189">Required</span></span> | <span data-ttu-id="124c0-190">Łączenie wartości żądania rekrutacji i identyfikatora umiejętności jako kolejna metoda unikalnej identyfikacji rekordu.</span><span class="sxs-lookup"><span data-stu-id="124c0-190">Concatenation of Recruiting Request value and Skill ID as another method to uniquely identify the record.</span></span> |
| <span data-ttu-id="124c0-191">**Identyfikator modelu oceny**</span><span class="sxs-lookup"><span data-stu-id="124c0-191">**Rating Model ID**</span></span><br><span data-ttu-id="124c0-192">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="124c0-192">mshr_ratingmodelid</span></span><br><span data-ttu-id="124c0-193">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="124c0-193">*String*</span></span> | <span data-ttu-id="124c0-194">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="124c0-194">Read-write</span></span><br><span data-ttu-id="124c0-195">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-195">Required</span></span> | <span data-ttu-id="124c0-196">Model oceniania używany do oceniania umiejętności.</span><span class="sxs-lookup"><span data-stu-id="124c0-196">The rating model used to rate the skill.</span></span> |
| <span data-ttu-id="124c0-197">**Wartość identyfikatora modelu oceny**</span><span class="sxs-lookup"><span data-stu-id="124c0-197">**Rating Model ID Value**</span></span><br><span data-ttu-id="124c0-198">_mshr_fk_hcmratingmodel_id_value</span><span class="sxs-lookup"><span data-stu-id="124c0-198">_mshr_fk_hcmratingmodel_id_value</span></span><br><span data-ttu-id="124c0-199">*GUID*</span><span class="sxs-lookup"><span data-stu-id="124c0-199">*GUID*</span></span> | <span data-ttu-id="124c0-200">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="124c0-200">Read-only</span></span><br><span data-ttu-id="124c0-201">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="124c0-201">Required</span></span><br><span data-ttu-id="124c0-202">Klucz obcy: mshr_hcmratingmodelentityid jednostki mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="124c0-202">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity entity</span></span> | <span data-ttu-id="124c0-203">Wygenerowany przez system niepowtarzalny identyfikator modelu oceny używanego do oceny umiejętności.</span><span class="sxs-lookup"><span data-stu-id="124c0-203">System-generated unique identifier of the rating model used to rate the skill.</span></span> |

## <a name="see-also"></a><span data-ttu-id="124c0-204">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="124c0-204">See also</span></span>

[<span data-ttu-id="124c0-205">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="124c0-205">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="124c0-206">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="124c0-206">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)