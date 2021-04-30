---
title: Szczegóły listy płac dla stanowisk
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Szczegóły listy płac dla stanowisk w Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f6c4bb0e2f4521e8c870f6c4fb645e2ce506138c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882052"
---
# <a name="payroll-position"></a><span data-ttu-id="6d910-103">Stanowisko listy płac</span><span class="sxs-lookup"><span data-stu-id="6d910-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6d910-104">Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Szczegóły listy płac dla stanowisk w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6d910-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="6d910-105">Właściwości</span><span class="sxs-lookup"><span data-stu-id="6d910-105">Properties</span></span>

| <span data-ttu-id="6d910-106">Właściwość</span><span class="sxs-lookup"><span data-stu-id="6d910-106">Property</span></span><br><span data-ttu-id="6d910-107">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="6d910-107">**Physical name**</span></span><br><span data-ttu-id="6d910-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="6d910-108">**_Type_**</span></span> | <span data-ttu-id="6d910-109">Użycie</span><span class="sxs-lookup"><span data-stu-id="6d910-109">Use</span></span> | <span data-ttu-id="6d910-110">opis</span><span class="sxs-lookup"><span data-stu-id="6d910-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d910-111">**Zwykłe godziny (rocznie)**</span><span class="sxs-lookup"><span data-stu-id="6d910-111">**Annual regular hours**</span></span><br><span data-ttu-id="6d910-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="6d910-112">annualregularhours</span></span><br><span data-ttu-id="6d910-113">*Dziesiętny*</span><span class="sxs-lookup"><span data-stu-id="6d910-113">*Decimal*</span></span> | <span data-ttu-id="6d910-114">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-114">Read-only</span></span><br><span data-ttu-id="6d910-115">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-115">Required</span></span> | <span data-ttu-id="6d910-116">Zwykłe godziny (rocznie) zdefiniowane dla stanowiska.</span><span class="sxs-lookup"><span data-stu-id="6d910-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="6d910-117">**Identyfikator podmiotu zawierający szczegóły dotyczące stanowiska płacowego**</span><span class="sxs-lookup"><span data-stu-id="6d910-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="6d910-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="6d910-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="6d910-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="6d910-119">*Guid*</span></span> | <span data-ttu-id="6d910-120">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-120">Required</span></span><br><span data-ttu-id="6d910-121">Wygenerowany przez system.</span><span class="sxs-lookup"><span data-stu-id="6d910-121">System generated.</span></span> | <span data-ttu-id="6d910-122">Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania stanowiska.</span><span class="sxs-lookup"><span data-stu-id="6d910-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="6d910-123">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="6d910-123">**Primary field**</span></span><br><span data-ttu-id="6d910-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="6d910-124">mshr_primaryfield</span></span><br><span data-ttu-id="6d910-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6d910-125">*String*</span></span> | <span data-ttu-id="6d910-126">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-126">Required</span></span><br><span data-ttu-id="6d910-127">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="6d910-127">System generated</span></span> |  |
| <span data-ttu-id="6d910-128">**Wartość identyfikatora zadania stanowiska**</span><span class="sxs-lookup"><span data-stu-id="6d910-128">**Position job ID value**</span></span><br><span data-ttu-id="6d910-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="6d910-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="6d910-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="6d910-130">*GUID*</span></span> | <span data-ttu-id="6d910-131">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-131">Read-only</span></span><br><span data-ttu-id="6d910-132">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-132">Required</span></span><br><span data-ttu-id="6d910-133">Klucz obcy: mshr_PayrollPositionJobEntity klucza mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="6d910-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="6d910-134">identyfikator stanowiska związany ze stanowiskiem.</span><span class="sxs-lookup"><span data-stu-id="6d910-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="6d910-135">**Wartość identyfikatora stałego planu wynagrodzeń**</span><span class="sxs-lookup"><span data-stu-id="6d910-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="6d910-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="6d910-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="6d910-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="6d910-137">*GUID*</span></span> | <span data-ttu-id="6d910-138">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-138">Read-only</span></span><br><span data-ttu-id="6d910-139">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-139">Required</span></span><br><span data-ttu-id="6d910-140">Klucz obcy: mshr_FixedCompPlan_id dla mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="6d910-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="6d910-141">Identyfikator planu stałych wynagrodzeń powiązany ze stanowiskiem.</span><span class="sxs-lookup"><span data-stu-id="6d910-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="6d910-142">**Identyfikator cyklu płac**</span><span class="sxs-lookup"><span data-stu-id="6d910-142">**Pay cycle ID**</span></span><br><span data-ttu-id="6d910-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="6d910-143">mshr_primaryfield</span></span><br><span data-ttu-id="6d910-144">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6d910-144">*String*</span></span> | <span data-ttu-id="6d910-145">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-145">Read-only</span></span><br><span data-ttu-id="6d910-146">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-146">Required</span></span> | <span data-ttu-id="6d910-147">Zdefiniowano cykl płac dla stanowiska.</span><span class="sxs-lookup"><span data-stu-id="6d910-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="6d910-148">**Zapłacone przez firmę**</span><span class="sxs-lookup"><span data-stu-id="6d910-148">**Paid by legal entity**</span></span><br><span data-ttu-id="6d910-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="6d910-149">paidbylegalentity</span></span><br><span data-ttu-id="6d910-150">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6d910-150">*String*</span></span> | <span data-ttu-id="6d910-151">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-151">Read-only</span></span><br><span data-ttu-id="6d910-152">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-152">Required</span></span> | <span data-ttu-id="6d910-153">Firma zdefiniowana dla stanowiska odpowiedzialnego za wydawanie płatności.</span><span class="sxs-lookup"><span data-stu-id="6d910-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="6d910-154">**Identyfikator stanowiska**</span><span class="sxs-lookup"><span data-stu-id="6d910-154">**Position ID**</span></span><br><span data-ttu-id="6d910-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="6d910-155">mshr_positionid</span></span><br><span data-ttu-id="6d910-156">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6d910-156">*String*</span></span> | <span data-ttu-id="6d910-157">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-157">Read-only</span></span><br><span data-ttu-id="6d910-158">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-158">Required</span></span> | <span data-ttu-id="6d910-159">Identyfikator stanowiska.</span><span class="sxs-lookup"><span data-stu-id="6d910-159">The ID of the position.</span></span> |
| <span data-ttu-id="6d910-160">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="6d910-160">**Valid to**</span></span><br><span data-ttu-id="6d910-161">validto</span><span class="sxs-lookup"><span data-stu-id="6d910-161">validto</span></span><br><span data-ttu-id="6d910-162">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="6d910-162">*Date Time Offset*</span></span> | <span data-ttu-id="6d910-163">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-163">Read-only</span></span><br><span data-ttu-id="6d910-164">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-164">Required</span></span> |<span data-ttu-id="6d910-165">Data, od której obowiązują szczegóły dotyczące stanowiska.</span><span class="sxs-lookup"><span data-stu-id="6d910-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="6d910-166">**Data wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="6d910-166">**Valid from**</span></span><br><span data-ttu-id="6d910-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="6d910-167">validfrom</span></span><br><span data-ttu-id="6d910-168">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="6d910-168">*Date Time Offset*</span></span> | <span data-ttu-id="6d910-169">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6d910-169">Read-only</span></span><br><span data-ttu-id="6d910-170">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="6d910-170">Required</span></span> |<span data-ttu-id="6d910-171">Data, do której obowiązują szczegóły dotyczące stanowiska.</span><span class="sxs-lookup"><span data-stu-id="6d910-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="6d910-172">**Kwerenda**</span><span class="sxs-lookup"><span data-stu-id="6d910-172">**Query**</span></span>

<span data-ttu-id="6d910-173">**Wniosek**</span><span class="sxs-lookup"><span data-stu-id="6d910-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="6d910-174">**Odpowiedź**</span><span class="sxs-lookup"><span data-stu-id="6d910-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
