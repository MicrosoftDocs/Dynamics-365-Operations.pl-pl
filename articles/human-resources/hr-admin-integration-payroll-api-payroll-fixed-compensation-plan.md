---
title: Plan stałych wynagrodzeń listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Płace stałe plany wynagrodzeń w Dynamics 365 Human Resources.
author: jcart
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
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021303"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="fd30b-103">Plan stałych wynagrodzeń listy płac</span><span class="sxs-lookup"><span data-stu-id="fd30b-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fd30b-104">Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Płace stałe plany wynagrodzeń w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fd30b-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="fd30b-105">Właściwości</span><span class="sxs-lookup"><span data-stu-id="fd30b-105">Properties</span></span>

| <span data-ttu-id="fd30b-106">Właściwość</span><span class="sxs-lookup"><span data-stu-id="fd30b-106">Property</span></span><br><span data-ttu-id="fd30b-107">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="fd30b-107">**Physical name**</span></span><br><span data-ttu-id="fd30b-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="fd30b-108">**_Type_**</span></span> | <span data-ttu-id="fd30b-109">Użycie</span><span class="sxs-lookup"><span data-stu-id="fd30b-109">Use</span></span> | <span data-ttu-id="fd30b-110">opis</span><span class="sxs-lookup"><span data-stu-id="fd30b-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fd30b-111">**Identyfikator pracownika**</span><span class="sxs-lookup"><span data-stu-id="fd30b-111">**Employee ID**</span></span><br><span data-ttu-id="fd30b-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="fd30b-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="fd30b-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="fd30b-113">*GUID*</span></span> | <span data-ttu-id="fd30b-114">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-114">Read-only</span></span><br><span data-ttu-id="fd30b-115">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-115">Required</span></span><br><span data-ttu-id="fd30b-116">Klucz obcy: mshr_Employee_id jednostki mshr_payrollemployeeentity</span><span class="sxs-lookup"><span data-stu-id="fd30b-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="fd30b-117">Identyfikator pracownika</span><span class="sxs-lookup"><span data-stu-id="fd30b-117">Employee ID</span></span> |
| <span data-ttu-id="fd30b-118">**Stawka płacy**</span><span class="sxs-lookup"><span data-stu-id="fd30b-118">**Pay rate**</span></span><br><span data-ttu-id="fd30b-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="fd30b-119">mshr_payrate</span></span><br><span data-ttu-id="fd30b-120">*Dziesiętny*</span><span class="sxs-lookup"><span data-stu-id="fd30b-120">*Decimal*</span></span> | <span data-ttu-id="fd30b-121">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-121">Read-only</span></span><br><span data-ttu-id="fd30b-122">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-122">Required</span></span> | <span data-ttu-id="fd30b-123">Stawka płacy zdefiniowana w planie stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="fd30b-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="fd30b-124">**Identyfikator planu**</span><span class="sxs-lookup"><span data-stu-id="fd30b-124">**Plan ID**</span></span><br><span data-ttu-id="fd30b-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="fd30b-125">mshr_planid</span></span><br><span data-ttu-id="fd30b-126">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fd30b-126">*String*</span></span> | <span data-ttu-id="fd30b-127">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-127">Read-only</span></span><br><span data-ttu-id="fd30b-128">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-128">Required</span></span> |<span data-ttu-id="fd30b-129">Określa plan wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="fd30b-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="fd30b-130">**Data wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="fd30b-130">**Valid from**</span></span><br><span data-ttu-id="fd30b-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="fd30b-131">mshr_validfrom</span></span><br><span data-ttu-id="fd30b-132">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="fd30b-132">*Date Time Offset*</span></span> |  <span data-ttu-id="fd30b-133">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-133">Read-only</span></span><br><span data-ttu-id="fd30b-134">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-134">Required</span></span> |<span data-ttu-id="fd30b-135">Data, od której obowiązuje stałe wynagrodzenie pracownika.</span><span class="sxs-lookup"><span data-stu-id="fd30b-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="fd30b-136">**Jednostka Plan stałych wynagrodzeń listy płac**</span><span class="sxs-lookup"><span data-stu-id="fd30b-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="fd30b-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="fd30b-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="fd30b-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="fd30b-138">*GUID*</span></span> | <span data-ttu-id="fd30b-139">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-139">Required</span></span><br><span data-ttu-id="fd30b-140">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="fd30b-140">Sytem generated</span></span> | <span data-ttu-id="fd30b-141">Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania planu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="fd30b-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="fd30b-142">**Częstotliwość wypłat**</span><span class="sxs-lookup"><span data-stu-id="fd30b-142">**Pay frequency**</span></span><br><span data-ttu-id="fd30b-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="fd30b-143">mshr_payfrequency</span></span><br><span data-ttu-id="fd30b-144">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fd30b-144">*String*</span></span> | <span data-ttu-id="fd30b-145">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-145">Read-only</span></span><br><span data-ttu-id="fd30b-146">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-146">Required</span></span> |<span data-ttu-id="fd30b-147">Częstotliwość wypłat dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="fd30b-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="fd30b-148">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="fd30b-148">**Valid to**</span></span><br><span data-ttu-id="fd30b-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="fd30b-149">mshr_validto</span></span><br><span data-ttu-id="fd30b-150">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="fd30b-150">*Date Time Offset*</span></span> | <span data-ttu-id="fd30b-151">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-151">Read-only</span></span> <br><span data-ttu-id="fd30b-152">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-152">Required</span></span> | <span data-ttu-id="fd30b-153">Data, do której obowiązuje stałe wynagrodzenie pracownika.</span><span class="sxs-lookup"><span data-stu-id="fd30b-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="fd30b-154">**Identyfikator stanowiska**</span><span class="sxs-lookup"><span data-stu-id="fd30b-154">**Position ID**</span></span><br><span data-ttu-id="fd30b-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="fd30b-155">mshr_positionid</span></span><br><span data-ttu-id="fd30b-156">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fd30b-156">*String*</span></span> | <span data-ttu-id="fd30b-157">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-157">Read-only</span></span> <br><span data-ttu-id="fd30b-158">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-158">Required</span></span> | <span data-ttu-id="fd30b-159">Identyfikator stanowiska powiązany z rejestracją pracownika i planu stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="fd30b-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="fd30b-160">**Waluta**</span><span class="sxs-lookup"><span data-stu-id="fd30b-160">**Currency**</span></span><br><span data-ttu-id="fd30b-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="fd30b-161">mshr_currency</span></span><br><span data-ttu-id="fd30b-162">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fd30b-162">*String*</span></span> | <span data-ttu-id="fd30b-163">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-163">Read-only</span></span> <br><span data-ttu-id="fd30b-164">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-164">Required</span></span> |<span data-ttu-id="fd30b-165">Waluta zdefiniowana dla stałego planu wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="fd30b-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="fd30b-166">**Numer pracownika**</span><span class="sxs-lookup"><span data-stu-id="fd30b-166">**Personnel number**</span></span><br><span data-ttu-id="fd30b-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="fd30b-167">mshr_personnelnumber</span></span><br><span data-ttu-id="fd30b-168">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fd30b-168">*String*</span></span> | <span data-ttu-id="fd30b-169">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="fd30b-169">Read-only</span></span><br><span data-ttu-id="fd30b-170">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="fd30b-170">Required</span></span> |<span data-ttu-id="fd30b-171">Unikalny numer personelu pracownika.</span><span class="sxs-lookup"><span data-stu-id="fd30b-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="fd30b-172">**Kwerenda**</span><span class="sxs-lookup"><span data-stu-id="fd30b-172">**Query**</span></span>

<span data-ttu-id="fd30b-173">**Wniosek**</span><span class="sxs-lookup"><span data-stu-id="fd30b-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="fd30b-174">**Odpowiedź**</span><span class="sxs-lookup"><span data-stu-id="fd30b-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
