---
title: Certyfikat osoby
description: W tym temacie opisano jednostkę Certyfikatu osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 796a57a5f97de08ff8c8440bc00d4dc5ced18f58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798136"
---
# <a name="person-certificate"></a><span data-ttu-id="f2cb5-103">Certyfikat osoby</span><span class="sxs-lookup"><span data-stu-id="f2cb5-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f2cb5-104">W tym temacie opisano jednostkę Certyfikatu osoby dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f2cb5-105">Nazwa fizyczna: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="f2cb5-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="f2cb5-106">opis</span><span class="sxs-lookup"><span data-stu-id="f2cb5-106">Description</span></span>

<span data-ttu-id="f2cb5-107">Ta jednostka opisuje certyfikaty zawodowe kandydata.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f2cb5-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="f2cb5-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="f2cb5-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f2cb5-109">Properties</span></span>

| <span data-ttu-id="f2cb5-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="f2cb5-110">Property</span></span><br><span data-ttu-id="f2cb5-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-111">**Physical name**</span></span><br><span data-ttu-id="f2cb5-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-112">**_Type_**</span></span> | <span data-ttu-id="f2cb5-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="f2cb5-113">Use</span></span> | <span data-ttu-id="f2cb5-114">opis</span><span class="sxs-lookup"><span data-stu-id="f2cb5-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f2cb5-115">**Identyfikator jednostki certyfikatu osoby**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="f2cb5-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="f2cb5-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="f2cb5-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-117">*GUID*</span></span> | <span data-ttu-id="f2cb5-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2cb5-118">Read-only</span></span><br><span data-ttu-id="f2cb5-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-119">Required</span></span> | <span data-ttu-id="f2cb5-120">Wygenerowany przez system unikalny identyfikator dla rekordu jednostki certyfikatu osoby.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="f2cb5-121">**Numer strony**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-121">**Party Number**</span></span><br><span data-ttu-id="f2cb5-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="f2cb5-122">mshr_partynumber</span></span><br><span data-ttu-id="f2cb5-123">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-123">*String*</span></span> | <span data-ttu-id="f2cb5-124">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2cb5-124">Read/write</span></span><br><span data-ttu-id="f2cb5-125">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-125">Required</span></span> | <span data-ttu-id="f2cb5-126">Identyfikator strony (osoby) kandydata.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="f2cb5-127">**Wartość identyfikatora osoby**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-127">**Person ID Value**</span></span><br><span data-ttu-id="f2cb5-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="f2cb5-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="f2cb5-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-129">*GUID*</span></span> | <span data-ttu-id="f2cb5-130">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2cb5-130">Read-only</span></span><br><span data-ttu-id="f2cb5-131">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-131">Required</span></span><br><span data-ttu-id="f2cb5-132">Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="f2cb5-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="f2cb5-133">Wygenerowany przez system identyfikator rekordu jednostki strony (osoby).</span><span class="sxs-lookup"><span data-stu-id="f2cb5-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="f2cb5-134">**Identyfikator typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-134">**Certificate Type ID**</span></span><br><span data-ttu-id="f2cb5-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="f2cb5-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="f2cb5-136">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-136">*String*</span></span> | <span data-ttu-id="f2cb5-137">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2cb5-137">Read/write</span></span><br><span data-ttu-id="f2cb5-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-138">Required</span></span> |  <span data-ttu-id="f2cb5-139">Identyfikator typu certyfikatu zdefiniowanego w części Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="f2cb5-140">**Wartość identyfikatora typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="f2cb5-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="f2cb5-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="f2cb5-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-142">*GUID*</span></span> | <span data-ttu-id="f2cb5-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2cb5-143">Read-only</span></span><br><span data-ttu-id="f2cb5-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-144">Required</span></span><br><span data-ttu-id="f2cb5-145">Klucz obcy: mshr_hcmcertificatetypeentityid jednostki mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="f2cb5-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="f2cb5-146">Wygenerowany przez system unikalny identyfikator typu certyfikatu w powiązanej jednostce.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="f2cb5-147">**Data rozpoczęcia**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-147">**Start Date**</span></span><br><span data-ttu-id="f2cb5-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="f2cb5-148">mshr_startdate</span></span><br><span data-ttu-id="f2cb5-149">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-149">*Datetime*</span></span> | <span data-ttu-id="f2cb5-150">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2cb5-150">Read/write</span></span><br><span data-ttu-id="f2cb5-151">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-151">Required</span></span> | <span data-ttu-id="f2cb5-152">Data wydania certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="f2cb5-153">**Data końcowa**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-153">**End Date**</span></span><br><span data-ttu-id="f2cb5-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="f2cb5-154">mshr_enddate</span></span><br><span data-ttu-id="f2cb5-155">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-155">*Datetime*</span></span> | <span data-ttu-id="f2cb5-156">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2cb5-156">Read/write</span></span><br><span data-ttu-id="f2cb5-157">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="f2cb5-157">Optional</span></span> | <span data-ttu-id="f2cb5-158">Data wygaśnięcia certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="f2cb5-159">**Notatki**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-159">**Notes**</span></span><br><span data-ttu-id="f2cb5-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="f2cb5-160">mshr_notes</span></span><br><span data-ttu-id="f2cb5-161">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-161">*String*</span></span> | <span data-ttu-id="f2cb5-162">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f2cb5-162">Read/write</span></span><br><span data-ttu-id="f2cb5-163">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="f2cb5-163">Optional</span></span> | <span data-ttu-id="f2cb5-164">Notatki do użytku przez menedżerów zatrudniających i rekruterów.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="f2cb5-165">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="f2cb5-165">**Primary Field**</span></span><br><span data-ttu-id="f2cb5-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="f2cb5-166">mshr_primaryfield</span></span><br><span data-ttu-id="f2cb5-167">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2cb5-167">*String*</span></span> | <span data-ttu-id="f2cb5-168">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f2cb5-168">Read-only</span></span><br><span data-ttu-id="f2cb5-169">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f2cb5-169">Required</span></span> |  <span data-ttu-id="f2cb5-170">Pole, które ma być używane jako identyfikator rekordu encji.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="f2cb5-171">Połączenie numeru strony, identyfikatora typu certyfikatu i daty rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f2cb5-172">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f2cb5-172">See also</span></span>

[<span data-ttu-id="f2cb5-173">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="f2cb5-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f2cb5-174">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="f2cb5-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]