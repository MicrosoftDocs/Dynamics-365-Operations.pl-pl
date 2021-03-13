---
title: Typ certyfikatu
description: W tym temacie opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1d2d53a628ef43d50bd83fd6b62807f44eddd653
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125720"
---
# <a name="certificate-type"></a><span data-ttu-id="1fe71-103">Typ certyfikatu</span><span class="sxs-lookup"><span data-stu-id="1fe71-103">Certificate type</span></span>

<span data-ttu-id="1fe71-104">W tym temacie opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1fe71-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1fe71-105">Nazwa fizyczna: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="1fe71-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="1fe71-106">opis</span><span class="sxs-lookup"><span data-stu-id="1fe71-106">Description</span></span>

<span data-ttu-id="1fe71-107">Ten podmiot definiuje listę typów certyfikatów zawodowych ustawionych w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1fe71-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="1fe71-108">Ta jednostka nie jest specyficzna dla osoby prawnej (firmy).</span><span class="sxs-lookup"><span data-stu-id="1fe71-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="1fe71-109">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="1fe71-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="1fe71-110">Właściwości</span><span class="sxs-lookup"><span data-stu-id="1fe71-110">Properties</span></span>

| <span data-ttu-id="1fe71-111">Właściwość</span><span class="sxs-lookup"><span data-stu-id="1fe71-111">Property</span></span><br><span data-ttu-id="1fe71-112">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="1fe71-112">**Physical name**</span></span><br><span data-ttu-id="1fe71-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="1fe71-113">**_Type_**</span></span> | <span data-ttu-id="1fe71-114">Użycie</span><span class="sxs-lookup"><span data-stu-id="1fe71-114">Use</span></span> | <span data-ttu-id="1fe71-115">opis</span><span class="sxs-lookup"><span data-stu-id="1fe71-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1fe71-116">**Identyfikator jednostki typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="1fe71-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="1fe71-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="1fe71-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="1fe71-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1fe71-118">*GUID*</span></span> | <span data-ttu-id="1fe71-119">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="1fe71-119">Read-only</span></span><br><span data-ttu-id="1fe71-120">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="1fe71-120">Required</span></span> 
<span data-ttu-id="1fe71-121">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="1fe71-121">System-generated</span></span> | <span data-ttu-id="1fe71-122">Unikalny identyfikator podstawowy dla typu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="1fe71-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="1fe71-123">**Typ certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="1fe71-123">**Certificate Type**</span></span><br><span data-ttu-id="1fe71-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="1fe71-124">mshr_certificatetype</span></span><br><span data-ttu-id="1fe71-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="1fe71-125">*String*</span></span> | <span data-ttu-id="1fe71-126">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="1fe71-126">Read/write</span></span><br><span data-ttu-id="1fe71-127">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="1fe71-127">Required</span></span> | <span data-ttu-id="1fe71-128">Unikalny czytelny dla użytkownika identyfikator typu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="1fe71-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="1fe71-129">**Opis**</span><span class="sxs-lookup"><span data-stu-id="1fe71-129">**Description**</span></span><br><span data-ttu-id="1fe71-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="1fe71-130">mshr_description</span></span><br><span data-ttu-id="1fe71-131">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="1fe71-131">*String*</span></span> | <span data-ttu-id="1fe71-132">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="1fe71-132">Read/write</span></span><br><span data-ttu-id="1fe71-133">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="1fe71-133">Required</span></span> | <span data-ttu-id="1fe71-134">Opis typu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="1fe71-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="1fe71-135">**Wymagaj odnowienia**</span><span class="sxs-lookup"><span data-stu-id="1fe71-135">**Require Renewal**</span></span><br><span data-ttu-id="1fe71-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="1fe71-136">mshr_requirerenewal</span></span><br><span data-ttu-id="1fe71-137">*zestaw opcji mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="1fe71-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="1fe71-138">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="1fe71-138">Read/write</span></span><br><span data-ttu-id="1fe71-139">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="1fe71-139">Optional</span></span> | <span data-ttu-id="1fe71-140">Wskazuje, czy dla certyfikatu jest wymagane odnowienie.</span><span class="sxs-lookup"><span data-stu-id="1fe71-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1fe71-141">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1fe71-141">See also</span></span>

[<span data-ttu-id="1fe71-142">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="1fe71-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1fe71-143">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="1fe71-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

