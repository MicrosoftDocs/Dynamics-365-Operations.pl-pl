---
title: Certyfikat osoby
description: W tym temacie opisano jednostkę Certyfikatu osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa4582dc00341a647f1ea43ed16d9dce8bfcf688
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125360"
---
# <a name="person-certificate"></a><span data-ttu-id="d0072-103">Certyfikat osoby</span><span class="sxs-lookup"><span data-stu-id="d0072-103">Person certificate</span></span>

<span data-ttu-id="d0072-104">W tym temacie opisano jednostkę Certyfikatu osoby dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d0072-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="d0072-105">Nazwa fizyczna: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="d0072-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="d0072-106">opis</span><span class="sxs-lookup"><span data-stu-id="d0072-106">Description</span></span>

<span data-ttu-id="d0072-107">Ta jednostka opisuje certyfikaty zawodowe kandydata.</span><span class="sxs-lookup"><span data-stu-id="d0072-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="d0072-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="d0072-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="d0072-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="d0072-109">Properties</span></span>

| <span data-ttu-id="d0072-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="d0072-110">Property</span></span><br><span data-ttu-id="d0072-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="d0072-111">**Physical name**</span></span><br><span data-ttu-id="d0072-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="d0072-112">**_Type_**</span></span> | <span data-ttu-id="d0072-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="d0072-113">Use</span></span> | <span data-ttu-id="d0072-114">opis</span><span class="sxs-lookup"><span data-stu-id="d0072-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d0072-115">**Identyfikator jednostki certyfikatu osoby**</span><span class="sxs-lookup"><span data-stu-id="d0072-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="d0072-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="d0072-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="d0072-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d0072-117">*GUID*</span></span> | <span data-ttu-id="d0072-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d0072-118">Read-only</span></span><br><span data-ttu-id="d0072-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-119">Required</span></span> | <span data-ttu-id="d0072-120">Wygenerowany przez system unikalny identyfikator dla rekordu jednostki certyfikatu osoby.</span><span class="sxs-lookup"><span data-stu-id="d0072-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="d0072-121">**Numer strony**</span><span class="sxs-lookup"><span data-stu-id="d0072-121">**Party Number**</span></span><br><span data-ttu-id="d0072-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="d0072-122">mshr_partynumber</span></span><br><span data-ttu-id="d0072-123">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d0072-123">*String*</span></span> | <span data-ttu-id="d0072-124">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="d0072-124">Read/write</span></span><br><span data-ttu-id="d0072-125">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-125">Required</span></span> | <span data-ttu-id="d0072-126">Identyfikator strony (osoby) kandydata.</span><span class="sxs-lookup"><span data-stu-id="d0072-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="d0072-127">**Wartość identyfikatora osoby**</span><span class="sxs-lookup"><span data-stu-id="d0072-127">**Person ID Value**</span></span><br><span data-ttu-id="d0072-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="d0072-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="d0072-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d0072-129">*GUID*</span></span> | <span data-ttu-id="d0072-130">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d0072-130">Read-only</span></span><br><span data-ttu-id="d0072-131">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-131">Required</span></span><br><span data-ttu-id="d0072-132">Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="d0072-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="d0072-133">Wygenerowany przez system identyfikator rekordu jednostki strony (osoby).</span><span class="sxs-lookup"><span data-stu-id="d0072-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="d0072-134">**Identyfikator typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="d0072-134">**Certificate Type ID**</span></span><br><span data-ttu-id="d0072-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="d0072-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="d0072-136">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d0072-136">*String*</span></span> | <span data-ttu-id="d0072-137">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="d0072-137">Read/write</span></span><br><span data-ttu-id="d0072-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-138">Required</span></span> |  <span data-ttu-id="d0072-139">Identyfikator typu certyfikatu zdefiniowanego w części Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d0072-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="d0072-140">**Wartość identyfikatora typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="d0072-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="d0072-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="d0072-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="d0072-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d0072-142">*GUID*</span></span> | <span data-ttu-id="d0072-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d0072-143">Read-only</span></span><br><span data-ttu-id="d0072-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-144">Required</span></span><br><span data-ttu-id="d0072-145">Klucz obcy: mshr_hcmcertificatetypeentityid jednostki mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="d0072-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="d0072-146">Wygenerowany przez system unikalny identyfikator typu certyfikatu w powiązanej jednostce.</span><span class="sxs-lookup"><span data-stu-id="d0072-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="d0072-147">**Data rozpoczęcia**</span><span class="sxs-lookup"><span data-stu-id="d0072-147">**Start Date**</span></span><br><span data-ttu-id="d0072-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="d0072-148">mshr_startdate</span></span><br><span data-ttu-id="d0072-149">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="d0072-149">*Datetime*</span></span> | <span data-ttu-id="d0072-150">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="d0072-150">Read/write</span></span><br><span data-ttu-id="d0072-151">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-151">Required</span></span> | <span data-ttu-id="d0072-152">Data wydania certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="d0072-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="d0072-153">**Data końcowa**</span><span class="sxs-lookup"><span data-stu-id="d0072-153">**End Date**</span></span><br><span data-ttu-id="d0072-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="d0072-154">mshr_enddate</span></span><br><span data-ttu-id="d0072-155">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="d0072-155">*Datetime*</span></span> | <span data-ttu-id="d0072-156">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="d0072-156">Read/write</span></span><br><span data-ttu-id="d0072-157">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="d0072-157">Optional</span></span> | <span data-ttu-id="d0072-158">Data wygaśnięcia certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="d0072-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="d0072-159">**Notatki**</span><span class="sxs-lookup"><span data-stu-id="d0072-159">**Notes**</span></span><br><span data-ttu-id="d0072-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="d0072-160">mshr_notes</span></span><br><span data-ttu-id="d0072-161">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d0072-161">*String*</span></span> | <span data-ttu-id="d0072-162">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="d0072-162">Read/write</span></span><br><span data-ttu-id="d0072-163">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="d0072-163">Optional</span></span> | <span data-ttu-id="d0072-164">Notatki do użytku przez menedżerów zatrudniających i rekruterów.</span><span class="sxs-lookup"><span data-stu-id="d0072-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="d0072-165">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="d0072-165">**Primary Field**</span></span><br><span data-ttu-id="d0072-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="d0072-166">mshr_primaryfield</span></span><br><span data-ttu-id="d0072-167">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d0072-167">*String*</span></span> | <span data-ttu-id="d0072-168">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d0072-168">Read-only</span></span><br><span data-ttu-id="d0072-169">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d0072-169">Required</span></span> |  <span data-ttu-id="d0072-170">Pole, które ma być używane jako identyfikator rekordu encji.</span><span class="sxs-lookup"><span data-stu-id="d0072-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="d0072-171">Połączenie numeru strony, identyfikatora typu certyfikatu i daty rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="d0072-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d0072-172">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="d0072-172">See also</span></span>

[<span data-ttu-id="d0072-173">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="d0072-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="d0072-174">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="d0072-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

