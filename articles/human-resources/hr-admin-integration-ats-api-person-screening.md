---
title: Kontrola osoby
description: W tym temacie opisano jednostkę Kontroli osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: c6287f30aaa008ea77b91fd46a8dfb2b7c905036
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467248"
---
# <a name="person-screening"></a><span data-ttu-id="2cfd3-103">Kontrola osoby</span><span class="sxs-lookup"><span data-stu-id="2cfd3-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2cfd3-104">W tym temacie opisano jednostkę Kontroli osoby dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="2cfd3-105">Nazwa fizyczna: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="2cfd3-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="2cfd3-106">opis</span><span class="sxs-lookup"><span data-stu-id="2cfd3-106">Description</span></span>

<span data-ttu-id="2cfd3-107">Ta jednostka opisuje kontrole, które kandydat przeszedł lub musi przejść w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="2cfd3-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="2cfd3-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="2cfd3-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="2cfd3-109">Properties</span></span>

| <span data-ttu-id="2cfd3-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="2cfd3-110">Property</span></span><br><span data-ttu-id="2cfd3-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-111">**Physical name**</span></span><br><span data-ttu-id="2cfd3-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-112">**_Type_**</span></span> | <span data-ttu-id="2cfd3-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="2cfd3-113">Use</span></span> | <span data-ttu-id="2cfd3-114">opis</span><span class="sxs-lookup"><span data-stu-id="2cfd3-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2cfd3-115">**Identyfikator jednostki kontroli osoby**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="2cfd3-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="2cfd3-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="2cfd3-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-117">*GUID*</span></span> | <span data-ttu-id="2cfd3-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="2cfd3-118">Read-only</span></span><br><span data-ttu-id="2cfd3-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2cfd3-119">Required</span></span><br><span data-ttu-id="2cfd3-120">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="2cfd3-120">System-generated</span></span> | <span data-ttu-id="2cfd3-121">Unikalny identyfikator podstawowy dla rekordu kontroli osoby.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="2cfd3-122">**Numer strony**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-122">**Party Number**</span></span><br><span data-ttu-id="2cfd3-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="2cfd3-123">mshr_partynumber</span></span><br><span data-ttu-id="2cfd3-124">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-124">*String*</span></span> | <span data-ttu-id="2cfd3-125">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="2cfd3-125">Read/write</span></span><br><span data-ttu-id="2cfd3-126">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2cfd3-126">Required</span></span> | <span data-ttu-id="2cfd3-127">Numer strony (osoby) skojarzony z kandydatem.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="2cfd3-128">**Wartość identyfikatora osoby**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-128">**Person ID Value**</span></span><br><span data-ttu-id="2cfd3-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="2cfd3-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="2cfd3-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-130">*GUID*</span></span> | <span data-ttu-id="2cfd3-131">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="2cfd3-131">Read-only</span></span><br><span data-ttu-id="2cfd3-132">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2cfd3-132">Required</span></span><br><span data-ttu-id="2cfd3-133">Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="2cfd3-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="2cfd3-134">Wygenerowany przez system identyfikator rekordu jednostki strony (osoby).</span><span class="sxs-lookup"><span data-stu-id="2cfd3-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="2cfd3-135">**Identyfikator typu kontroli**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-135">**Screening Type ID**</span></span><br><span data-ttu-id="2cfd3-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="2cfd3-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="2cfd3-137">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-137">*String*</span></span> | <span data-ttu-id="2cfd3-138">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="2cfd3-138">Read/write</span></span><br><span data-ttu-id="2cfd3-139">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2cfd3-139">Required</span></span><br><span data-ttu-id="2cfd3-140">Klucz obcy: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="2cfd3-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="2cfd3-141">Identyfikator typu kontroli zdefiniowanego w części Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="2cfd3-142">**Wartość identyfikatora jednostki typu kontroli**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="2cfd3-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="2cfd3-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="2cfd3-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-144">*GUID*</span></span> | <span data-ttu-id="2cfd3-145">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="2cfd3-145">Read-only</span></span><br><span data-ttu-id="2cfd3-146">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2cfd3-146">Required</span></span><br><span data-ttu-id="2cfd3-147">Klucz obcy: mshr_hcmscreeningtypeentityid jednostki mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="2cfd3-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="2cfd3-148">Wygenerowany przez system identyfikator rekordu typu kontroli w skojarzonej jednostce.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="2cfd3-149">**Wymagane przed datą**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-149">**Required By**</span></span><br><span data-ttu-id="2cfd3-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="2cfd3-150">mshr_requiredby</span></span><br><span data-ttu-id="2cfd3-151">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-151">*Datetime*</span></span> | <span data-ttu-id="2cfd3-152">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="2cfd3-152">Read/write</span></span><br><span data-ttu-id="2cfd3-153">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="2cfd3-153">Optional</span></span> | <span data-ttu-id="2cfd3-154">Data, do której kontrola musi zostać zakończona.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="2cfd3-155">**Stan**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-155">**Status**</span></span><br><span data-ttu-id="2cfd3-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="2cfd3-156">mshr_status</span></span><br><span data-ttu-id="2cfd3-157">*zestaw opcji mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="2cfd3-158">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="2cfd3-158">Read/write</span></span><br><span data-ttu-id="2cfd3-159">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2cfd3-159">Required</span></span> | <span data-ttu-id="2cfd3-160">Dostarcza stan kandydata do kontroli.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="2cfd3-161">**Data zakończenia**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-161">**Completed Date**</span></span><br><span data-ttu-id="2cfd3-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="2cfd3-162">mshr_completeddate</span></span><br><span data-ttu-id="2cfd3-163">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-163">*Datetime*</span></span> | <span data-ttu-id="2cfd3-164">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="2cfd3-164">Read/write</span></span><br><span data-ttu-id="2cfd3-165">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="2cfd3-165">Optional</span></span> | <span data-ttu-id="2cfd3-166">Data zakończenia kontroli.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="2cfd3-167">**Notatki**</span><span class="sxs-lookup"><span data-stu-id="2cfd3-167">**Notes**</span></span><br><span data-ttu-id="2cfd3-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="2cfd3-168">mshr_note</span></span><br><span data-ttu-id="2cfd3-169">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2cfd3-169">*String*</span></span> | <span data-ttu-id="2cfd3-170">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="2cfd3-170">Read/write</span></span><br><span data-ttu-id="2cfd3-171">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="2cfd3-171">Optional</span></span> | <span data-ttu-id="2cfd3-172">Notatki do użytku przez menedżerów zatrudniających i rekruterów.</span><span class="sxs-lookup"><span data-stu-id="2cfd3-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2cfd3-173">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2cfd3-173">See also</span></span>

[<span data-ttu-id="2cfd3-174">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="2cfd3-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="2cfd3-175">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="2cfd3-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]