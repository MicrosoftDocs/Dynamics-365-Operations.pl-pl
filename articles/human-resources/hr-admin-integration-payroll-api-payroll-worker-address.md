---
title: Adres pracownika listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3407128b0172f0e253d51bcfa23a894f981e21e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052296"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="d470e-103">Adres pracownika listy płac</span><span class="sxs-lookup"><span data-stu-id="d470e-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d470e-104">Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d470e-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="d470e-105">Właściwości</span><span class="sxs-lookup"><span data-stu-id="d470e-105">Properties</span></span>

| <span data-ttu-id="d470e-106">Właściwość</span><span class="sxs-lookup"><span data-stu-id="d470e-106">Property</span></span><br><span data-ttu-id="d470e-107">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="d470e-107">**Physical name**</span></span><br><span data-ttu-id="d470e-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="d470e-108">**_Type_**</span></span> | <span data-ttu-id="d470e-109">Użycie</span><span class="sxs-lookup"><span data-stu-id="d470e-109">Use</span></span> | <span data-ttu-id="d470e-110">opis</span><span class="sxs-lookup"><span data-stu-id="d470e-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d470e-111">**Miasto**</span><span class="sxs-lookup"><span data-stu-id="d470e-111">**City**</span></span><br><span data-ttu-id="d470e-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="d470e-112">mshr_city</span></span><br><span data-ttu-id="d470e-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-113">*String*</span></span> | <span data-ttu-id="d470e-114">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-114">Read-only</span></span><br><span data-ttu-id="d470e-115">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-115">Required</span></span> | <span data-ttu-id="d470e-116">Miasto zdefiniowane dla adresu.</span><span class="sxs-lookup"><span data-stu-id="d470e-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="d470e-117">**Numer pracownika**</span><span class="sxs-lookup"><span data-stu-id="d470e-117">**Personnel number**</span></span><br><span data-ttu-id="d470e-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="d470e-118">mshr_personnelnumber</span></span><br><span data-ttu-id="d470e-119">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-119">*String*</span></span> | <span data-ttu-id="d470e-120">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-120">Read-only</span></span><br><span data-ttu-id="d470e-121">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-121">Required</span></span> | <span data-ttu-id="d470e-122">Unikalny numer personelu pracownika.</span><span class="sxs-lookup"><span data-stu-id="d470e-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="d470e-123">**Kraj region**</span><span class="sxs-lookup"><span data-stu-id="d470e-123">**Country region**</span></span><br><span data-ttu-id="d470e-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="d470e-124">mshr_countryregionid</span></span><br><span data-ttu-id="d470e-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-125">*String*</span></span> | <span data-ttu-id="d470e-126">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-126">Read-only</span></span><br><span data-ttu-id="d470e-127">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-127">Required</span></span> | <span data-ttu-id="d470e-128">Region kraju zdefiniowany dla adresu</span><span class="sxs-lookup"><span data-stu-id="d470e-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="d470e-129">**Data wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="d470e-129">**Valid from**</span></span><br><span data-ttu-id="d470e-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="d470e-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="d470e-131">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="d470e-131">*Date Time Offset*</span></span> | <span data-ttu-id="d470e-132">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-132">Read-only</span></span> <br><span data-ttu-id="d470e-133">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-133">Required</span></span> | <span data-ttu-id="d470e-134">Data, od której adres jest ważny.</span><span class="sxs-lookup"><span data-stu-id="d470e-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="d470e-135">**Pracował w adresie**</span><span class="sxs-lookup"><span data-stu-id="d470e-135">**Worked in address**</span></span><br><span data-ttu-id="d470e-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="d470e-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="d470e-137">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-137">Read-only</span></span><br><span data-ttu-id="d470e-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-138">Required</span></span> | <span data-ttu-id="d470e-139">Wskazuje, czy adres jest miejscem pracy pracownika.</span><span class="sxs-lookup"><span data-stu-id="d470e-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="d470e-140">**Powiat**</span><span class="sxs-lookup"><span data-stu-id="d470e-140">**County**</span></span><br><span data-ttu-id="d470e-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="d470e-141">mshr_county</span></span><br><span data-ttu-id="d470e-142">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-142">*String*</span></span> | <span data-ttu-id="d470e-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-143">Read-only</span></span><br><span data-ttu-id="d470e-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-144">Required</span></span> | <span data-ttu-id="d470e-145">Hrabstwo zdefiniowane dla adresu.</span><span class="sxs-lookup"><span data-stu-id="d470e-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="d470e-146">**Identyfikator adresu pracownika listy płac**</span><span class="sxs-lookup"><span data-stu-id="d470e-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="d470e-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="d470e-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="d470e-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d470e-148">*GUID*</span></span> | <span data-ttu-id="d470e-149">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-149">Required</span></span><br><span data-ttu-id="d470e-150">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="d470e-150">System generated</span></span> | <span data-ttu-id="d470e-151">Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania adresu.</span><span class="sxs-lookup"><span data-stu-id="d470e-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="d470e-152">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="d470e-152">**Primary field**</span></span><br><span data-ttu-id="d470e-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="d470e-153">mshr_primaryfield</span></span><br><span data-ttu-id="d470e-154">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-154">*String*</span></span> | <span data-ttu-id="d470e-155">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-155">Read-only</span></span><br><span data-ttu-id="d470e-156">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-156">Required</span></span> |  |
| <span data-ttu-id="d470e-157">**Ulica**</span><span class="sxs-lookup"><span data-stu-id="d470e-157">**Street**</span></span><br><span data-ttu-id="d470e-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="d470e-158">mshr_street</span></span><br><span data-ttu-id="d470e-159">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-159">*String*</span></span> | <span data-ttu-id="d470e-160">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-160">Read-only</span></span><br><span data-ttu-id="d470e-161">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-161">Required</span></span> | <span data-ttu-id="d470e-162">Ulica określona dla adresu.</span><span class="sxs-lookup"><span data-stu-id="d470e-162">The street defined for the address.</span></span> |
| <span data-ttu-id="d470e-163">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="d470e-163">**Valid to**</span></span><br><span data-ttu-id="d470e-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="d470e-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="d470e-165">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="d470e-165">*Date Time Offset*</span></span> | <span data-ttu-id="d470e-166">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-166">Read-only</span></span> <br><span data-ttu-id="d470e-167">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-167">Required</span></span> | <span data-ttu-id="d470e-168">Data, do której adres jest ważny.</span><span class="sxs-lookup"><span data-stu-id="d470e-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="d470e-169">**Identyfikator lokalizacji**</span><span class="sxs-lookup"><span data-stu-id="d470e-169">**Location ID**</span></span><br><span data-ttu-id="d470e-170">mshr_locationidbr>*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="d470e-171">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-171">Read-only</span></span> <br><span data-ttu-id="d470e-172">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-172">Required</span></span> | <span data-ttu-id="d470e-173">Identyfikator dla adresu.</span><span class="sxs-lookup"><span data-stu-id="d470e-173">The ID for the address.</span></span>  |
| <span data-ttu-id="d470e-174">**Kod pocztowy**</span><span class="sxs-lookup"><span data-stu-id="d470e-174">**Postal code**</span></span><br><span data-ttu-id="d470e-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="d470e-175">mshr_zipcode</span></span><br><span data-ttu-id="d470e-176">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-176">*String*</span></span> | <span data-ttu-id="d470e-177">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-177">Read-only</span></span> <br><span data-ttu-id="d470e-178">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-178">Required</span></span> |<span data-ttu-id="d470e-179">Numer identyfikacji zdefiniowany dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="d470e-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="d470e-180">**Mieszkał pod adresem**</span><span class="sxs-lookup"><span data-stu-id="d470e-180">**Lived in address**</span></span><br><span data-ttu-id="d470e-181">mshr_islivedinaddressbr>*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="d470e-182">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-182">Read-only</span></span><br><span data-ttu-id="d470e-183">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-183">Required</span></span> | <span data-ttu-id="d470e-184">Wskazuje, czy adres jest miejscem zamieszkania pracownika.</span><span class="sxs-lookup"><span data-stu-id="d470e-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="d470e-185">**Stanowy**</span><span class="sxs-lookup"><span data-stu-id="d470e-185">**State**</span></span><br><span data-ttu-id="d470e-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="d470e-186">mshr_state</span></span><br><span data-ttu-id="d470e-187">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d470e-187">*String*</span></span> | <span data-ttu-id="d470e-188">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d470e-188">Read-only</span></span><br><span data-ttu-id="d470e-189">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="d470e-189">Required</span></span> | <span data-ttu-id="d470e-190">Stan określony dla adresu.</span><span class="sxs-lookup"><span data-stu-id="d470e-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="d470e-191">Przykład kwerendy</span><span class="sxs-lookup"><span data-stu-id="d470e-191">Example query</span></span>

<span data-ttu-id="d470e-192">**Wniosek**</span><span class="sxs-lookup"><span data-stu-id="d470e-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="d470e-193">**Odpowiedź**</span><span class="sxs-lookup"><span data-stu-id="d470e-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
