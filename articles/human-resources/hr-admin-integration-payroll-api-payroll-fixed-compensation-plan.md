---
title: Plan stałych wynagrodzeń listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Płace stałe plany wynagrodzeń w Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 227082358c59abddd63f4faa4536a8df270a4d80
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059095"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="a9cc8-103">Plan stałych wynagrodzeń listy płac</span><span class="sxs-lookup"><span data-stu-id="a9cc8-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a9cc8-104">Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Płace stałe plany wynagrodzeń w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="a9cc8-105">Właściwości</span><span class="sxs-lookup"><span data-stu-id="a9cc8-105">Properties</span></span>

| <span data-ttu-id="a9cc8-106">Właściwość</span><span class="sxs-lookup"><span data-stu-id="a9cc8-106">Property</span></span><br><span data-ttu-id="a9cc8-107">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-107">**Physical name**</span></span><br><span data-ttu-id="a9cc8-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-108">**_Type_**</span></span> | <span data-ttu-id="a9cc8-109">Użycie</span><span class="sxs-lookup"><span data-stu-id="a9cc8-109">Use</span></span> | <span data-ttu-id="a9cc8-110">opis</span><span class="sxs-lookup"><span data-stu-id="a9cc8-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a9cc8-111">**Identyfikator pracownika**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-111">**Employee ID**</span></span><br><span data-ttu-id="a9cc8-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="a9cc8-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="a9cc8-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-113">*GUID*</span></span> | <span data-ttu-id="a9cc8-114">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-114">Read-only</span></span><br><span data-ttu-id="a9cc8-115">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-115">Required</span></span><br><span data-ttu-id="a9cc8-116">Klucz obcy: mshr_Employee_id jednostki mshr_payrollemployeeentity</span><span class="sxs-lookup"><span data-stu-id="a9cc8-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="a9cc8-117">Identyfikator pracownika</span><span class="sxs-lookup"><span data-stu-id="a9cc8-117">Employee ID</span></span> |
| <span data-ttu-id="a9cc8-118">**Stawka płacy**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-118">**Pay rate**</span></span><br><span data-ttu-id="a9cc8-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="a9cc8-119">mshr_payrate</span></span><br><span data-ttu-id="a9cc8-120">*Dziesiętny*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-120">*Decimal*</span></span> | <span data-ttu-id="a9cc8-121">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-121">Read-only</span></span><br><span data-ttu-id="a9cc8-122">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-122">Required</span></span> | <span data-ttu-id="a9cc8-123">Stawka płacy zdefiniowana w planie stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="a9cc8-124">**Identyfikator planu**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-124">**Plan ID**</span></span><br><span data-ttu-id="a9cc8-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="a9cc8-125">mshr_planid</span></span><br><span data-ttu-id="a9cc8-126">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-126">*String*</span></span> | <span data-ttu-id="a9cc8-127">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-127">Read-only</span></span><br><span data-ttu-id="a9cc8-128">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-128">Required</span></span> |<span data-ttu-id="a9cc8-129">Określa plan wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="a9cc8-130">**Data wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-130">**Valid from**</span></span><br><span data-ttu-id="a9cc8-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="a9cc8-131">mshr_validfrom</span></span><br><span data-ttu-id="a9cc8-132">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-132">*Date Time Offset*</span></span> |  <span data-ttu-id="a9cc8-133">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-133">Read-only</span></span><br><span data-ttu-id="a9cc8-134">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-134">Required</span></span> |<span data-ttu-id="a9cc8-135">Data, od której obowiązuje stałe wynagrodzenie pracownika.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="a9cc8-136">**Jednostka Plan stałych wynagrodzeń listy płac**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="a9cc8-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="a9cc8-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="a9cc8-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-138">*GUID*</span></span> | <span data-ttu-id="a9cc8-139">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-139">Required</span></span><br><span data-ttu-id="a9cc8-140">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="a9cc8-140">Sytem generated</span></span> | <span data-ttu-id="a9cc8-141">Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania planu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="a9cc8-142">**Częstotliwość wypłat**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-142">**Pay frequency**</span></span><br><span data-ttu-id="a9cc8-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="a9cc8-143">mshr_payfrequency</span></span><br><span data-ttu-id="a9cc8-144">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-144">*String*</span></span> | <span data-ttu-id="a9cc8-145">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-145">Read-only</span></span><br><span data-ttu-id="a9cc8-146">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-146">Required</span></span> |<span data-ttu-id="a9cc8-147">Częstotliwość wypłat dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="a9cc8-148">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-148">**Valid to**</span></span><br><span data-ttu-id="a9cc8-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="a9cc8-149">mshr_validto</span></span><br><span data-ttu-id="a9cc8-150">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-150">*Date Time Offset*</span></span> | <span data-ttu-id="a9cc8-151">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-151">Read-only</span></span> <br><span data-ttu-id="a9cc8-152">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-152">Required</span></span> | <span data-ttu-id="a9cc8-153">Data, do której obowiązuje stałe wynagrodzenie pracownika.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="a9cc8-154">**Identyfikator stanowiska**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-154">**Position ID**</span></span><br><span data-ttu-id="a9cc8-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="a9cc8-155">mshr_positionid</span></span><br><span data-ttu-id="a9cc8-156">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-156">*String*</span></span> | <span data-ttu-id="a9cc8-157">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-157">Read-only</span></span> <br><span data-ttu-id="a9cc8-158">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-158">Required</span></span> | <span data-ttu-id="a9cc8-159">Identyfikator stanowiska powiązany z rejestracją pracownika i planu stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="a9cc8-160">**Waluta**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-160">**Currency**</span></span><br><span data-ttu-id="a9cc8-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="a9cc8-161">mshr_currency</span></span><br><span data-ttu-id="a9cc8-162">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-162">*String*</span></span> | <span data-ttu-id="a9cc8-163">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-163">Read-only</span></span> <br><span data-ttu-id="a9cc8-164">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-164">Required</span></span> |<span data-ttu-id="a9cc8-165">Waluta zdefiniowana dla stałego planu wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="a9cc8-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="a9cc8-166">**Numer pracownika**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-166">**Personnel number**</span></span><br><span data-ttu-id="a9cc8-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="a9cc8-167">mshr_personnelnumber</span></span><br><span data-ttu-id="a9cc8-168">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a9cc8-168">*String*</span></span> | <span data-ttu-id="a9cc8-169">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a9cc8-169">Read-only</span></span><br><span data-ttu-id="a9cc8-170">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="a9cc8-170">Required</span></span> |<span data-ttu-id="a9cc8-171">Unikalny numer personelu pracownika.</span><span class="sxs-lookup"><span data-stu-id="a9cc8-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="a9cc8-172">**Kwerenda**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-172">**Query**</span></span>

<span data-ttu-id="a9cc8-173">**Wniosek**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="a9cc8-174">**Odpowiedź**</span><span class="sxs-lookup"><span data-stu-id="a9cc8-174">**Response**</span></span>

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
