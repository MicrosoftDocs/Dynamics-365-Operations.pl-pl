---
title: Adres pracownika listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 964f04261ea95ee6fa2880b0905a669855f6c58a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020712"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="ce0dd-103">Adres pracownika listy płac</span><span class="sxs-lookup"><span data-stu-id="ce0dd-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ce0dd-104">Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="ce0dd-105">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ce0dd-105">Properties</span></span>

| <span data-ttu-id="ce0dd-106">Właściwość</span><span class="sxs-lookup"><span data-stu-id="ce0dd-106">Property</span></span><br><span data-ttu-id="ce0dd-107">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-107">**Physical name**</span></span><br><span data-ttu-id="ce0dd-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-108">**_Type_**</span></span> | <span data-ttu-id="ce0dd-109">Użycie</span><span class="sxs-lookup"><span data-stu-id="ce0dd-109">Use</span></span> | <span data-ttu-id="ce0dd-110">opis</span><span class="sxs-lookup"><span data-stu-id="ce0dd-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ce0dd-111">**Miasto**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-111">**City**</span></span><br><span data-ttu-id="ce0dd-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="ce0dd-112">mshr_city</span></span><br><span data-ttu-id="ce0dd-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-113">*String*</span></span> | <span data-ttu-id="ce0dd-114">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-114">Read-only</span></span><br><span data-ttu-id="ce0dd-115">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-115">Required</span></span> | <span data-ttu-id="ce0dd-116">Miasto zdefiniowane dla adresu.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="ce0dd-117">**Numer pracownika**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-117">**Personnel number**</span></span><br><span data-ttu-id="ce0dd-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="ce0dd-118">mshr_personnelnumber</span></span><br><span data-ttu-id="ce0dd-119">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-119">*String*</span></span> | <span data-ttu-id="ce0dd-120">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-120">Read-only</span></span><br><span data-ttu-id="ce0dd-121">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-121">Required</span></span> | <span data-ttu-id="ce0dd-122">Unikalny numer personelu pracownika.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="ce0dd-123">**Kraj region**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-123">**Country region**</span></span><br><span data-ttu-id="ce0dd-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="ce0dd-124">mshr_countryregionid</span></span><br><span data-ttu-id="ce0dd-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-125">*String*</span></span> | <span data-ttu-id="ce0dd-126">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-126">Read-only</span></span><br><span data-ttu-id="ce0dd-127">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-127">Required</span></span> | <span data-ttu-id="ce0dd-128">Region kraju zdefiniowany dla adresu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="ce0dd-129">**Data wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-129">**Valid from**</span></span><br><span data-ttu-id="ce0dd-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="ce0dd-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="ce0dd-131">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-131">*Date Time Offset*</span></span> | <span data-ttu-id="ce0dd-132">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-132">Read-only</span></span> <br><span data-ttu-id="ce0dd-133">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-133">Required</span></span> | <span data-ttu-id="ce0dd-134">Data, od której adres jest ważny.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="ce0dd-135">**Pracował w adresie**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-135">**Worked in address**</span></span><br><span data-ttu-id="ce0dd-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="ce0dd-137">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-137">Read-only</span></span><br><span data-ttu-id="ce0dd-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-138">Required</span></span> | <span data-ttu-id="ce0dd-139">Wskazuje, czy adres jest miejscem pracy pracownika.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="ce0dd-140">**Powiat**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-140">**County**</span></span><br><span data-ttu-id="ce0dd-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="ce0dd-141">mshr_county</span></span><br><span data-ttu-id="ce0dd-142">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-142">*String*</span></span> | <span data-ttu-id="ce0dd-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-143">Read-only</span></span><br><span data-ttu-id="ce0dd-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-144">Required</span></span> | <span data-ttu-id="ce0dd-145">Hrabstwo zdefiniowane dla adresu.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="ce0dd-146">**Identyfikator adresu pracownika listy płac**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="ce0dd-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="ce0dd-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="ce0dd-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-148">*GUID*</span></span> | <span data-ttu-id="ce0dd-149">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-149">Required</span></span><br><span data-ttu-id="ce0dd-150">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="ce0dd-150">System generated</span></span> | <span data-ttu-id="ce0dd-151">Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania adresu.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="ce0dd-152">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-152">**Primary field**</span></span><br><span data-ttu-id="ce0dd-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="ce0dd-153">mshr_primaryfield</span></span><br><span data-ttu-id="ce0dd-154">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-154">*String*</span></span> | <span data-ttu-id="ce0dd-155">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-155">Read-only</span></span><br><span data-ttu-id="ce0dd-156">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-156">Required</span></span> |  |
| <span data-ttu-id="ce0dd-157">**Ulica**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-157">**Street**</span></span><br><span data-ttu-id="ce0dd-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="ce0dd-158">mshr_street</span></span><br><span data-ttu-id="ce0dd-159">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-159">*String*</span></span> | <span data-ttu-id="ce0dd-160">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-160">Read-only</span></span><br><span data-ttu-id="ce0dd-161">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-161">Required</span></span> | <span data-ttu-id="ce0dd-162">Ulica określona dla adresu.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-162">The street defined for the address.</span></span> |
| <span data-ttu-id="ce0dd-163">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-163">**Valid to**</span></span><br><span data-ttu-id="ce0dd-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="ce0dd-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="ce0dd-165">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-165">*Date Time Offset*</span></span> | <span data-ttu-id="ce0dd-166">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-166">Read-only</span></span> <br><span data-ttu-id="ce0dd-167">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-167">Required</span></span> | <span data-ttu-id="ce0dd-168">Data, do której adres jest ważny.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="ce0dd-169">**Identyfikator lokalizacji**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-169">**Location ID**</span></span><br><span data-ttu-id="ce0dd-170">mshr_locationidbr>*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="ce0dd-171">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-171">Read-only</span></span> <br><span data-ttu-id="ce0dd-172">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-172">Required</span></span> | <span data-ttu-id="ce0dd-173">Identyfikator dla adresu.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-173">The ID for the address.</span></span>  |
| <span data-ttu-id="ce0dd-174">**Kod pocztowy**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-174">**Postal code**</span></span><br><span data-ttu-id="ce0dd-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="ce0dd-175">mshr_zipcode</span></span><br><span data-ttu-id="ce0dd-176">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-176">*String*</span></span> | <span data-ttu-id="ce0dd-177">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-177">Read-only</span></span> <br><span data-ttu-id="ce0dd-178">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-178">Required</span></span> |<span data-ttu-id="ce0dd-179">Numer identyfikacji zdefiniowany dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="ce0dd-180">**Mieszkał pod adresem**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-180">**Lived in address**</span></span><br><span data-ttu-id="ce0dd-181">mshr_islivedinaddressbr>*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="ce0dd-182">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-182">Read-only</span></span><br><span data-ttu-id="ce0dd-183">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-183">Required</span></span> | <span data-ttu-id="ce0dd-184">Wskazuje, czy adres jest miejscem zamieszkania pracownika.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="ce0dd-185">**Stanowy**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-185">**State**</span></span><br><span data-ttu-id="ce0dd-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="ce0dd-186">mshr_state</span></span><br><span data-ttu-id="ce0dd-187">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ce0dd-187">*String*</span></span> | <span data-ttu-id="ce0dd-188">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ce0dd-188">Read-only</span></span><br><span data-ttu-id="ce0dd-189">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="ce0dd-189">Required</span></span> | <span data-ttu-id="ce0dd-190">Stan określony dla adresu.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="ce0dd-191">Przykład kwerendy</span><span class="sxs-lookup"><span data-stu-id="ce0dd-191">Example query</span></span>

<span data-ttu-id="ce0dd-192">**Wniosek**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="ce0dd-193">**Odpowiedź**</span><span class="sxs-lookup"><span data-stu-id="ce0dd-193">**Response**</span></span>

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
