---
title: Typ certyfikatu
description: W tym temacie opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798400"
---
# <a name="certificate-type"></a><span data-ttu-id="b8695-103">Typ certyfikatu</span><span class="sxs-lookup"><span data-stu-id="b8695-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b8695-104">W tym temacie opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8695-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="b8695-105">Nazwa fizyczna: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="b8695-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="b8695-106">opis</span><span class="sxs-lookup"><span data-stu-id="b8695-106">Description</span></span>

<span data-ttu-id="b8695-107">Ten podmiot definiuje listę typów certyfikatów zawodowych ustawionych w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8695-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="b8695-108">Ta jednostka nie jest specyficzna dla osoby prawnej (firmy).</span><span class="sxs-lookup"><span data-stu-id="b8695-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="b8695-109">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="b8695-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="b8695-110">Właściwości</span><span class="sxs-lookup"><span data-stu-id="b8695-110">Properties</span></span>

| <span data-ttu-id="b8695-111">Właściwość</span><span class="sxs-lookup"><span data-stu-id="b8695-111">Property</span></span><br><span data-ttu-id="b8695-112">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="b8695-112">**Physical name**</span></span><br><span data-ttu-id="b8695-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="b8695-113">**_Type_**</span></span> | <span data-ttu-id="b8695-114">Użycie</span><span class="sxs-lookup"><span data-stu-id="b8695-114">Use</span></span> | <span data-ttu-id="b8695-115">opis</span><span class="sxs-lookup"><span data-stu-id="b8695-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b8695-116">**Identyfikator jednostki typu certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="b8695-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="b8695-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="b8695-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="b8695-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b8695-118">*GUID*</span></span> | <span data-ttu-id="b8695-119">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="b8695-119">Read-only</span></span><br><span data-ttu-id="b8695-120">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="b8695-120">Required</span></span> 
<span data-ttu-id="b8695-121">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="b8695-121">System-generated</span></span> | <span data-ttu-id="b8695-122">Unikalny identyfikator podstawowy dla typu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="b8695-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="b8695-123">**Typ certyfikatu**</span><span class="sxs-lookup"><span data-stu-id="b8695-123">**Certificate Type**</span></span><br><span data-ttu-id="b8695-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="b8695-124">mshr_certificatetype</span></span><br><span data-ttu-id="b8695-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b8695-125">*String*</span></span> | <span data-ttu-id="b8695-126">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="b8695-126">Read/write</span></span><br><span data-ttu-id="b8695-127">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="b8695-127">Required</span></span> | <span data-ttu-id="b8695-128">Unikalny czytelny dla użytkownika identyfikator typu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="b8695-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="b8695-129">**Opis**</span><span class="sxs-lookup"><span data-stu-id="b8695-129">**Description**</span></span><br><span data-ttu-id="b8695-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="b8695-130">mshr_description</span></span><br><span data-ttu-id="b8695-131">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b8695-131">*String*</span></span> | <span data-ttu-id="b8695-132">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="b8695-132">Read/write</span></span><br><span data-ttu-id="b8695-133">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="b8695-133">Required</span></span> | <span data-ttu-id="b8695-134">Opis typu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="b8695-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="b8695-135">**Wymagaj odnowienia**</span><span class="sxs-lookup"><span data-stu-id="b8695-135">**Require Renewal**</span></span><br><span data-ttu-id="b8695-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="b8695-136">mshr_requirerenewal</span></span><br><span data-ttu-id="b8695-137">*zestaw opcji mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="b8695-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="b8695-138">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="b8695-138">Read/write</span></span><br><span data-ttu-id="b8695-139">Opcjonalny</span><span class="sxs-lookup"><span data-stu-id="b8695-139">Optional</span></span> | <span data-ttu-id="b8695-140">Wskazuje, czy dla certyfikatu jest wymagane odnowienie.</span><span class="sxs-lookup"><span data-stu-id="b8695-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b8695-141">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="b8695-141">See also</span></span>

[<span data-ttu-id="b8695-142">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="b8695-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="b8695-143">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="b8695-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]