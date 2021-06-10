---
title: Kontrola osoby
description: W tym temacie opisano jednostkę Kontroli osoby dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d29b26094e307c3f68d57f297ab3614f3a5ccae
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059287"
---
# <a name="person-screening"></a><span data-ttu-id="7f8c9-103">Kontrola osoby</span><span class="sxs-lookup"><span data-stu-id="7f8c9-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7f8c9-104">W tym temacie opisano jednostkę Kontroli osoby dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7f8c9-105">Nazwa fizyczna: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="7f8c9-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="7f8c9-106">opis</span><span class="sxs-lookup"><span data-stu-id="7f8c9-106">Description</span></span>

<span data-ttu-id="7f8c9-107">Ta jednostka opisuje kontrole, które kandydat przeszedł lub musi przejść w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="7f8c9-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="7f8c9-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="7f8c9-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7f8c9-109">Properties</span></span>

| <span data-ttu-id="7f8c9-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="7f8c9-110">Property</span></span><br><span data-ttu-id="7f8c9-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-111">**Physical name**</span></span><br><span data-ttu-id="7f8c9-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-112">**_Type_**</span></span> | <span data-ttu-id="7f8c9-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="7f8c9-113">Use</span></span> | <span data-ttu-id="7f8c9-114">opis</span><span class="sxs-lookup"><span data-stu-id="7f8c9-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7f8c9-115">**Identyfikator jednostki kontroli osoby**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="7f8c9-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="7f8c9-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="7f8c9-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-117">*GUID*</span></span> | <span data-ttu-id="7f8c9-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7f8c9-118">Read-only</span></span><br><span data-ttu-id="7f8c9-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="7f8c9-119">Required</span></span><br><span data-ttu-id="7f8c9-120">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="7f8c9-120">System-generated</span></span> | <span data-ttu-id="7f8c9-121">Unikalny identyfikator podstawowy dla rekordu kontroli osoby.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="7f8c9-122">**Numer strony**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-122">**Party Number**</span></span><br><span data-ttu-id="7f8c9-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="7f8c9-123">mshr_partynumber</span></span><br><span data-ttu-id="7f8c9-124">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-124">*String*</span></span> | <span data-ttu-id="7f8c9-125">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="7f8c9-125">Read/write</span></span><br><span data-ttu-id="7f8c9-126">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="7f8c9-126">Required</span></span> | <span data-ttu-id="7f8c9-127">Numer strony (osoby) skojarzony z kandydatem.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="7f8c9-128">**Wartość identyfikatora osoby**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-128">**Person ID Value**</span></span><br><span data-ttu-id="7f8c9-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="7f8c9-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="7f8c9-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-130">*GUID*</span></span> | <span data-ttu-id="7f8c9-131">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7f8c9-131">Read-only</span></span><br><span data-ttu-id="7f8c9-132">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="7f8c9-132">Required</span></span><br><span data-ttu-id="7f8c9-133">Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="7f8c9-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="7f8c9-134">Wygenerowany przez system identyfikator rekordu jednostki strony (osoby).</span><span class="sxs-lookup"><span data-stu-id="7f8c9-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="7f8c9-135">**Identyfikator typu kontroli**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-135">**Screening Type ID**</span></span><br><span data-ttu-id="7f8c9-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="7f8c9-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="7f8c9-137">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-137">*String*</span></span> | <span data-ttu-id="7f8c9-138">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="7f8c9-138">Read/write</span></span><br><span data-ttu-id="7f8c9-139">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="7f8c9-139">Required</span></span><br><span data-ttu-id="7f8c9-140">Klucz obcy: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="7f8c9-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="7f8c9-141">Identyfikator typu kontroli zdefiniowanego w części Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="7f8c9-142">**Wartość identyfikatora jednostki typu kontroli**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="7f8c9-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="7f8c9-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="7f8c9-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-144">*GUID*</span></span> | <span data-ttu-id="7f8c9-145">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7f8c9-145">Read-only</span></span><br><span data-ttu-id="7f8c9-146">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="7f8c9-146">Required</span></span><br><span data-ttu-id="7f8c9-147">Klucz obcy: mshr_hcmscreeningtypeentityid jednostki mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="7f8c9-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="7f8c9-148">Wygenerowany przez system identyfikator rekordu typu kontroli w skojarzonej jednostce.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="7f8c9-149">**Wymagane przed datą**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-149">**Required By**</span></span><br><span data-ttu-id="7f8c9-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="7f8c9-150">mshr_requiredby</span></span><br><span data-ttu-id="7f8c9-151">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-151">*Datetime*</span></span> | <span data-ttu-id="7f8c9-152">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="7f8c9-152">Read/write</span></span><br><span data-ttu-id="7f8c9-153">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="7f8c9-153">Optional</span></span> | <span data-ttu-id="7f8c9-154">Data, do której kontrola musi zostać zakończona.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="7f8c9-155">**Stan**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-155">**Status**</span></span><br><span data-ttu-id="7f8c9-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="7f8c9-156">mshr_status</span></span><br><span data-ttu-id="7f8c9-157">*zestaw opcji mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="7f8c9-158">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="7f8c9-158">Read/write</span></span><br><span data-ttu-id="7f8c9-159">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="7f8c9-159">Required</span></span> | <span data-ttu-id="7f8c9-160">Dostarcza stan kandydata do kontroli.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="7f8c9-161">**Data zakończenia**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-161">**Completed Date**</span></span><br><span data-ttu-id="7f8c9-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="7f8c9-162">mshr_completeddate</span></span><br><span data-ttu-id="7f8c9-163">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-163">*Datetime*</span></span> | <span data-ttu-id="7f8c9-164">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="7f8c9-164">Read/write</span></span><br><span data-ttu-id="7f8c9-165">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="7f8c9-165">Optional</span></span> | <span data-ttu-id="7f8c9-166">Data zakończenia kontroli.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="7f8c9-167">**Notatki**</span><span class="sxs-lookup"><span data-stu-id="7f8c9-167">**Notes**</span></span><br><span data-ttu-id="7f8c9-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="7f8c9-168">mshr_note</span></span><br><span data-ttu-id="7f8c9-169">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="7f8c9-169">*String*</span></span> | <span data-ttu-id="7f8c9-170">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="7f8c9-170">Read/write</span></span><br><span data-ttu-id="7f8c9-171">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="7f8c9-171">Optional</span></span> | <span data-ttu-id="7f8c9-172">Notatki do użytku przez menedżerów zatrudniających i rekruterów.</span><span class="sxs-lookup"><span data-stu-id="7f8c9-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7f8c9-173">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="7f8c9-173">See also</span></span>

[<span data-ttu-id="7f8c9-174">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="7f8c9-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7f8c9-175">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="7f8c9-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]