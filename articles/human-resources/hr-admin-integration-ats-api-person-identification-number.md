---
title: Numer dokumentu identyfikacyjnego osoby
description: W tym temacie opisano jednostkę Numer dokumentu identyfikacyjnego osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 054547c4f33e50d2dc0fa275559ba6ed44c27971
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125408"
---
# <a name="person-identification-number"></a><span data-ttu-id="e4f9b-103">Numer dokumentu identyfikacyjnego osoby</span><span class="sxs-lookup"><span data-stu-id="e4f9b-103">Person identification number</span></span>

<span data-ttu-id="e4f9b-104">W tym temacie opisano jednostkę Numer dokumentu identyfikacyjnego osoby dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-104">This topic describes the Person identification number entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e4f9b-105">Nazwa fizyczna: mshr_hcmpersonidentificationnumberentity</span><span class="sxs-lookup"><span data-stu-id="e4f9b-105">Physical name: mshr_hcmpersonidentificationnumberentity</span></span>

## <a name="description"></a><span data-ttu-id="e4f9b-106">opis</span><span class="sxs-lookup"><span data-stu-id="e4f9b-106">Description</span></span>

<span data-ttu-id="e4f9b-107">Podmiot ten opisuje numery identyfikacyjne kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-107">This entity describes the identification numbers for the candidate.</span></span> <span data-ttu-id="e4f9b-108">Umożliwia konsumentowi API zapisywanie numerów identyfikacyjnych, takich jak numery PESEL lub numery paszportów, w aktach kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-108">It enables the API consumer to write identification numbers, like Social Security numbers or passport numbers, to the candidate record.</span></span> <span data-ttu-id="e4f9b-109">Numery identyfikacyjne znajdują się w aktach pracownika, ale nie w aktach kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-109">Identification numbers are surfaced on the worker record, but not on the candidate record.</span></span> <span data-ttu-id="e4f9b-110">Aplikacja integrująca może zapisywać wartości w bazie danych Human Resources, ale liczby nie będą widoczne w dziale kadr, dopóki nie zostanie utworzony rekord pracownika kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-110">An integrating application can write the values to the Human Resources database, but the numbers won’t be visible in Human Resources until the candidate's worker record is created.</span></span>

## <a name="json-representation"></a><span data-ttu-id="e4f9b-111">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="e4f9b-111">JSON representation</span></span>

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a><span data-ttu-id="e4f9b-112">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e4f9b-112">Properties</span></span>

| <span data-ttu-id="e4f9b-113">Właściwość</span><span class="sxs-lookup"><span data-stu-id="e4f9b-113">Property</span></span><br><span data-ttu-id="e4f9b-114">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-114">**Physical name**</span></span><br><span data-ttu-id="e4f9b-115">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-115">**_Type_**</span></span> | <span data-ttu-id="e4f9b-116">Użycie</span><span class="sxs-lookup"><span data-stu-id="e4f9b-116">Use</span></span> | <span data-ttu-id="e4f9b-117">opis</span><span class="sxs-lookup"><span data-stu-id="e4f9b-117">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e4f9b-118">**Numer identyfikacyjny osoby Identyfikator jednostki**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-118">**Person Identification Number Entity ID**</span></span><br><span data-ttu-id="e4f9b-119">mshr_hcmpersonidentificationnumberentityid</span><span class="sxs-lookup"><span data-stu-id="e4f9b-119">mshr_hcmpersonidentificationnumberentityid</span></span><br><span data-ttu-id="e4f9b-120">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-120">*GUID*</span></span> | <span data-ttu-id="e4f9b-121">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e4f9b-121">Read-only</span></span><br><span data-ttu-id="e4f9b-122">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-122">Required</span></span><br><span data-ttu-id="e4f9b-123">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="e4f9b-123">System-generated</span></span> | <span data-ttu-id="e4f9b-124">Niepowtarzalny identyfikator podstawowy dla rekordu numeru identyfikacyjnego osoby.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-124">Unique primary identifier for the person identification number record.</span></span> |
| <span data-ttu-id="e4f9b-125">**Typ wpisu**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-125">**Entry Type**</span></span><br><span data-ttu-id="e4f9b-126">mshr_entrytype</span><span class="sxs-lookup"><span data-stu-id="e4f9b-126">mshr_entrytype</span></span><br><span data-ttu-id="e4f9b-127">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-127">*String*</span></span> | <span data-ttu-id="e4f9b-128">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-128">Read-write</span></span><br><span data-ttu-id="e4f9b-129">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-129">Optional</span></span> | <span data-ttu-id="e4f9b-130">Dowolna wartość wskazująca rodzaj wpisu numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-130">Free value to reference the type of entry for the identification number.</span></span> |
| <span data-ttu-id="e4f9b-131">**Opis**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-131">**Description**</span></span><br><span data-ttu-id="e4f9b-132">mshr_description</span><span class="sxs-lookup"><span data-stu-id="e4f9b-132">mshr_description</span></span><br><span data-ttu-id="e4f9b-133">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-133">*String*</span></span> | <span data-ttu-id="e4f9b-134">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-134">Read-write</span></span><br><span data-ttu-id="e4f9b-135">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-135">Optional</span></span> | <span data-ttu-id="e4f9b-136">Opis numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-136">The description of the identification number.</span></span> |
| <span data-ttu-id="e4f9b-137">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-137">**Expiration Date**</span></span><br><span data-ttu-id="e4f9b-138">mshr_expirationdate</span><span class="sxs-lookup"><span data-stu-id="e4f9b-138">mshr_expirationdate</span></span><br><span data-ttu-id="e4f9b-139">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-139">*Datetime*</span></span> | <span data-ttu-id="e4f9b-140">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-140">Read-write</span></span><br><span data-ttu-id="e4f9b-141">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-141">Optional</span></span> | <span data-ttu-id="e4f9b-142">Data wygaśnięcia numeru identyfikacyjnego lub skojarzonego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-142">The date on which the identification number or associated document expires.</span></span> |
| <span data-ttu-id="e4f9b-143">**Główne**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-143">**Is Primary**</span></span><br><span data-ttu-id="e4f9b-144">mshr_isprimary</span><span class="sxs-lookup"><span data-stu-id="e4f9b-144">mshr_isprimary</span></span><br><span data-ttu-id="e4f9b-145">*zestaw opcji mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-145">*mshr_noyes option set*</span></span> | <span data-ttu-id="e4f9b-146">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-146">Read-write</span></span><br><span data-ttu-id="e4f9b-147">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-147">Optional</span></span> | <span data-ttu-id="e4f9b-148">Określa, czy numer identyfikacyjny jest podstawowym rekordem osoby dla tego typu identyfikacji.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-148">Defines whether the identification number is the primary record for the person for this identification type.</span></span> |
| <span data-ttu-id="e4f9b-149">**Numer identyfikacyjny**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-149">**Identification Number**</span></span><br><span data-ttu-id="e4f9b-150">mshr_identificationnumber</span><span class="sxs-lookup"><span data-stu-id="e4f9b-150">mshr_identificationnumber</span></span><br><span data-ttu-id="e4f9b-151">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-151">*String*</span></span> | <span data-ttu-id="e4f9b-152">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-152">Read-write</span></span><br><span data-ttu-id="e4f9b-153">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-153">Required</span></span> | <span data-ttu-id="e4f9b-154">Numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-154">The identification number.</span></span> |
| <span data-ttu-id="e4f9b-155">**Numer strony**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-155">**Party Number**</span></span><br><span data-ttu-id="e4f9b-156">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="e4f9b-156">mshr_partynumber</span></span><br><span data-ttu-id="e4f9b-157">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-157">*String*</span></span> | <span data-ttu-id="e4f9b-158">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-158">Read-write</span></span><br><span data-ttu-id="e4f9b-159">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-159">Required</span></span> | <span data-ttu-id="e4f9b-160">Identyfikator strony (osoby) posiadającej numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-160">The identifier of the party (person) owning the identification number.</span></span> |
| <span data-ttu-id="e4f9b-161">**Wartość identyfikatora osoby**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-161">**Person ID Value**</span></span><br><span data-ttu-id="e4f9b-162">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="e4f9b-162">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="e4f9b-163">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-163">*GUID*</span></span> | <span data-ttu-id="e4f9b-164">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e4f9b-164">Read-only</span></span><br><span data-ttu-id="e4f9b-165">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-165">Required</span></span><br><span data-ttu-id="e4f9b-166">Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="e4f9b-166">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity entity</span></span> | <span data-ttu-id="e4f9b-167">Unikalny identyfikator strony (osoby).</span><span class="sxs-lookup"><span data-stu-id="e4f9b-167">The unique identifier of the party (person).</span></span> |
| <span data-ttu-id="e4f9b-168">**Identyfikator typu identyfikacji**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-168">**Identification Type ID**</span></span><br><span data-ttu-id="e4f9b-169">mshr_identificationtypeid</span><span class="sxs-lookup"><span data-stu-id="e4f9b-169">mshr_identificationtypeid</span></span><br><span data-ttu-id="e4f9b-170">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-170">*String*</span></span> | <span data-ttu-id="e4f9b-171">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-171">Read-write</span></span><br><span data-ttu-id="e4f9b-172">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-172">Required</span></span> | <span data-ttu-id="e4f9b-173">Rodzaj numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-173">The type of identification number.</span></span> |
| <span data-ttu-id="e4f9b-174">**Wartość identyfikacyjna typu identyfikatora**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-174">**Identification Type ID Value**</span></span><br><span data-ttu-id="e4f9b-175">_mshr_fk_identificationtype_id_value</span><span class="sxs-lookup"><span data-stu-id="e4f9b-175">_mshr_fk_identificationtype_id_value</span></span><br><span data-ttu-id="e4f9b-176">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-176">*GUID*</span></span> | <span data-ttu-id="e4f9b-177">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e4f9b-177">Read-only</span></span><br><span data-ttu-id="e4f9b-178">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-178">Required</span></span><br><span data-ttu-id="e4f9b-179">Klucz obcy: mshr_hcmidentificationtypeentityid jednostki mshr_hcmidentificationtypeentity</span><span class="sxs-lookup"><span data-stu-id="e4f9b-179">Foreign key: mshr_hcmidentificationtypeentityid of mshr_hcmidentificationtypeentity entity</span></span> | <span data-ttu-id="e4f9b-180">Wygenerowany przez system unikalny identyfikator dla typu identyfikacji.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-180">System-generated unique identifier of the identification type.</span></span> |
| <span data-ttu-id="e4f9b-181">**Numer identyfikacyjny Agencji wystawiającej**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-181">**Issuing Agency ID**</span></span><br><span data-ttu-id="e4f9b-182">mshr_issuingagencyid</span><span class="sxs-lookup"><span data-stu-id="e4f9b-182">mshr_issuingagencyid</span></span><br><span data-ttu-id="e4f9b-183">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-183">*String*</span></span> | <span data-ttu-id="e4f9b-184">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-184">Read-write</span></span><br><span data-ttu-id="e4f9b-185">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-185">Optional</span></span> | <span data-ttu-id="e4f9b-186">Agencja lub organizacja wystawiające numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-186">The agency or organization issuing the identification number.</span></span> |
| <span data-ttu-id="e4f9b-187">**Wartość numeru identyfikacyjnego Agencji wystawiającej**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-187">**Issuing Agency ID Value**</span></span><br><span data-ttu-id="e4f9b-188">_mshr_fk_issuingagency_id_value</span><span class="sxs-lookup"><span data-stu-id="e4f9b-188">_mshr_fk_issuingagency_id_value</span></span><br><span data-ttu-id="e4f9b-189">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-189">*GUID*</span></span> | <span data-ttu-id="e4f9b-190">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e4f9b-190">Read-only</span></span><br><span data-ttu-id="e4f9b-191">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-191">Optional</span></span><br><span data-ttu-id="e4f9b-192">Klucz obcy: mshr_hcmissuingagencyentityid jednostki mshr_hcmissuingagencyentity</span><span class="sxs-lookup"><span data-stu-id="e4f9b-192">Foreign key: mshr_hcmissuingagencyentityid of mshr_hcmissuingagencyentity entity</span></span> | <span data-ttu-id="e4f9b-193">Wygenerowany przez system niepowtarzalny identyfikator agencji wydającej numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-193">System-generated unique identifier of the agency issuing the identification number.</span></span> |
| <span data-ttu-id="e4f9b-194">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-194">**Primary Field**</span></span><br><span data-ttu-id="e4f9b-195">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="e4f9b-195">mshr_primaryfield</span></span><br><span data-ttu-id="e4f9b-196">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-196">*String*</span></span> | <span data-ttu-id="e4f9b-197">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e4f9b-197">Read-only</span></span><br><span data-ttu-id="e4f9b-198">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e4f9b-198">Required</span></span> | <span data-ttu-id="e4f9b-199">Pole, które ma być używane jako identyfikator rekordu encji.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-199">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="e4f9b-200">Połączenie numeru strony, identyfikatora typu identyfikatora i numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-200">Combination of party number, identification type ID, and identification number.</span></span> |
| <span data-ttu-id="e4f9b-201">**Data wystawienia**</span><span class="sxs-lookup"><span data-stu-id="e4f9b-201">**Issue Date**</span></span><br><span data-ttu-id="e4f9b-202">mshr_issuedate</span><span class="sxs-lookup"><span data-stu-id="e4f9b-202">mshr_issuedate</span></span><br><span data-ttu-id="e4f9b-203">*Data*</span><span class="sxs-lookup"><span data-stu-id="e4f9b-203">*Date*</span></span> | <span data-ttu-id="e4f9b-204">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="e4f9b-204">Read-write</span></span><br><span data-ttu-id="e4f9b-205">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="e4f9b-205">Optional</span></span> | <span data-ttu-id="e4f9b-206">Data nadania numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-206">The date the identification number was issued.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e4f9b-207">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e4f9b-207">See also</span></span>

[<span data-ttu-id="e4f9b-208">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="e4f9b-208">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e4f9b-209">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="e4f9b-209">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
