---
title: Certyfikat osoby
description: W tym temacie opisano jednostkę Certyfikatu osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5cdd742d6d36ccd7136f95e416507ed6e5e5a75a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055203"
---
# <a name="person-certificate"></a><span data-ttu-id="f2fd4-103">Certyfikat osoby</span><span class="sxs-lookup"><span data-stu-id="f2fd4-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f2fd4-104">W tym temacie opisano jednostkę Certyfikatu osoby dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f2fd4-105">Nazwa fizyczna: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="f2fd4-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="f2fd4-106">opis</span><span class="sxs-lookup"><span data-stu-id="f2fd4-106">Description</span></span>

<span data-ttu-id="f2fd4-107">Ta jednostka opisuje certyfikaty zawodowe kandydata.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f2fd4-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="f2fd4-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="f2fd4-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f2fd4-109">Properties</span></span>

| <span data-ttu-id="f2fd4-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="f2fd4-110">Property</span></span><br><span data-ttu-id="f2fd4-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-111">**Physical name**</span></span><br><span data-ttu-id="f2fd4-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-112">**_Type_**</span></span> | <span data-ttu-id="f2fd4-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="f2fd4-113">Use</span></span> | <span data-ttu-id="f2fd4-114">opis</span><span class="sxs-lookup"><span data-stu-id="f2fd4-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f2fd4-115">**Identyfikator jednostki certyfikatu osoby**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="f2fd4-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="f2fd4-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="f2fd4-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-117">*GUID*</span></span> | <span data-ttu-id="f2fd4-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2fd4-118">Read-only</span></span><br><span data-ttu-id="f2fd4-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-119">Required</span></span> | <span data-ttu-id="f2fd4-120">Wygenerowany przez system unikalny identyfikator dla rekordu jednostki certyfikatu osoby.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="f2fd4-121">**Numer strony**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-121">**Party Number**</span></span><br><span data-ttu-id="f2fd4-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="f2fd4-122">mshr_partynumber</span></span><br><span data-ttu-id="f2fd4-123">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-123">*String*</span></span> | <span data-ttu-id="f2fd4-124">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2fd4-124">Read/write</span></span><br><span data-ttu-id="f2fd4-125">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-125">Required</span></span> | <span data-ttu-id="f2fd4-126">Identyfikator strony (osoby) kandydata.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="f2fd4-127">**Wartość identyfikatora osoby**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-127">**Person ID Value**</span></span><br><span data-ttu-id="f2fd4-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="f2fd4-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="f2fd4-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-129">*GUID*</span></span> | <span data-ttu-id="f2fd4-130">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2fd4-130">Read-only</span></span><br><span data-ttu-id="f2fd4-131">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-131">Required</span></span><br><span data-ttu-id="f2fd4-132">Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="f2fd4-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="f2fd4-133">Wygenerowany przez system identyfikator rekordu jednostki strony (osoby).</span><span class="sxs-lookup"><span data-stu-id="f2fd4-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="f2fd4-134">**Identyfikator typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-134">**Certificate Type ID**</span></span><br><span data-ttu-id="f2fd4-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="f2fd4-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="f2fd4-136">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-136">*String*</span></span> | <span data-ttu-id="f2fd4-137">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2fd4-137">Read/write</span></span><br><span data-ttu-id="f2fd4-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-138">Required</span></span> |  <span data-ttu-id="f2fd4-139">Identyfikator typu certyfikatu zdefiniowanego w części Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="f2fd4-140">**Wartość identyfikatora typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="f2fd4-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="f2fd4-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="f2fd4-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-142">*GUID*</span></span> | <span data-ttu-id="f2fd4-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2fd4-143">Read-only</span></span><br><span data-ttu-id="f2fd4-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-144">Required</span></span><br><span data-ttu-id="f2fd4-145">Klucz obcy: mshr_hcmcertificatetypeentityid jednostki mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="f2fd4-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="f2fd4-146">Wygenerowany przez system unikalny identyfikator typu certyfikatu w powiązanej jednostce.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="f2fd4-147">**Data rozpoczęcia**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-147">**Start Date**</span></span><br><span data-ttu-id="f2fd4-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="f2fd4-148">mshr_startdate</span></span><br><span data-ttu-id="f2fd4-149">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-149">*Datetime*</span></span> | <span data-ttu-id="f2fd4-150">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2fd4-150">Read/write</span></span><br><span data-ttu-id="f2fd4-151">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-151">Required</span></span> | <span data-ttu-id="f2fd4-152">Data wydania certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="f2fd4-153">**Data końcowa**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-153">**End Date**</span></span><br><span data-ttu-id="f2fd4-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="f2fd4-154">mshr_enddate</span></span><br><span data-ttu-id="f2fd4-155">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-155">*Datetime*</span></span> | <span data-ttu-id="f2fd4-156">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2fd4-156">Read/write</span></span><br><span data-ttu-id="f2fd4-157">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="f2fd4-157">Optional</span></span> | <span data-ttu-id="f2fd4-158">Data wygaśnięcia certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="f2fd4-159">**Notatki**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-159">**Notes**</span></span><br><span data-ttu-id="f2fd4-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="f2fd4-160">mshr_notes</span></span><br><span data-ttu-id="f2fd4-161">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-161">*String*</span></span> | <span data-ttu-id="f2fd4-162">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2fd4-162">Read/write</span></span><br><span data-ttu-id="f2fd4-163">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="f2fd4-163">Optional</span></span> | <span data-ttu-id="f2fd4-164">Notatki do użytku przez menedżerów zatrudniających i rekruterów.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="f2fd4-165">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="f2fd4-165">**Primary Field**</span></span><br><span data-ttu-id="f2fd4-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="f2fd4-166">mshr_primaryfield</span></span><br><span data-ttu-id="f2fd4-167">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2fd4-167">*String*</span></span> | <span data-ttu-id="f2fd4-168">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2fd4-168">Read-only</span></span><br><span data-ttu-id="f2fd4-169">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2fd4-169">Required</span></span> |  <span data-ttu-id="f2fd4-170">Pole, które ma być używane jako identyfikator rekordu encji.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="f2fd4-171">Połączenie numeru strony, identyfikatora typu certyfikatu i daty rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="f2fd4-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f2fd4-172">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f2fd4-172">See also</span></span>

[<span data-ttu-id="f2fd4-173">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="f2fd4-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f2fd4-174">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="f2fd4-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]