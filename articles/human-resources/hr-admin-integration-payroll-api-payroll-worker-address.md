---
title: Adres pracownika listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882054"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="206f6-103">Adres pracownika listy płac</span><span class="sxs-lookup"><span data-stu-id="206f6-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="206f6-104">Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="206f6-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="206f6-105">Właściwości</span><span class="sxs-lookup"><span data-stu-id="206f6-105">Properties</span></span>

| <span data-ttu-id="206f6-106">Właściwość</span><span class="sxs-lookup"><span data-stu-id="206f6-106">Property</span></span><br><span data-ttu-id="206f6-107">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="206f6-107">**Physical name**</span></span><br><span data-ttu-id="206f6-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="206f6-108">**_Type_**</span></span> | <span data-ttu-id="206f6-109">Użycie</span><span class="sxs-lookup"><span data-stu-id="206f6-109">Use</span></span> | <span data-ttu-id="206f6-110">opis</span><span class="sxs-lookup"><span data-stu-id="206f6-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="206f6-111">**Miasto**</span><span class="sxs-lookup"><span data-stu-id="206f6-111">**City**</span></span><br><span data-ttu-id="206f6-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="206f6-112">mshr_city</span></span><br><span data-ttu-id="206f6-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-113">*String*</span></span> | <span data-ttu-id="206f6-114">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-114">Read-only</span></span><br><span data-ttu-id="206f6-115">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-115">Required</span></span> | <span data-ttu-id="206f6-116">Miasto zdefiniowane dla adresu.</span><span class="sxs-lookup"><span data-stu-id="206f6-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="206f6-117">**Numer pracownika**</span><span class="sxs-lookup"><span data-stu-id="206f6-117">**Personnel number**</span></span><br><span data-ttu-id="206f6-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="206f6-118">mshr_personnelnumber</span></span><br><span data-ttu-id="206f6-119">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-119">*String*</span></span> | <span data-ttu-id="206f6-120">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-120">Read-only</span></span><br><span data-ttu-id="206f6-121">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-121">Required</span></span> | <span data-ttu-id="206f6-122">Unikalny numer personelu pracownika.</span><span class="sxs-lookup"><span data-stu-id="206f6-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="206f6-123">**Kraj region**</span><span class="sxs-lookup"><span data-stu-id="206f6-123">**Country region**</span></span><br><span data-ttu-id="206f6-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="206f6-124">mshr_countryregionid</span></span><br><span data-ttu-id="206f6-125">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-125">*String*</span></span> | <span data-ttu-id="206f6-126">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-126">Read-only</span></span><br><span data-ttu-id="206f6-127">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-127">Required</span></span> | <span data-ttu-id="206f6-128">Region kraju zdefiniowany dla adresu</span><span class="sxs-lookup"><span data-stu-id="206f6-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="206f6-129">**Data wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="206f6-129">**Valid from**</span></span><br><span data-ttu-id="206f6-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="206f6-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="206f6-131">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="206f6-131">*Date Time Offset*</span></span> | <span data-ttu-id="206f6-132">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-132">Read-only</span></span> <br><span data-ttu-id="206f6-133">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-133">Required</span></span> | <span data-ttu-id="206f6-134">Data, od której adres jest ważny.</span><span class="sxs-lookup"><span data-stu-id="206f6-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="206f6-135">**Pracował w adresie**</span><span class="sxs-lookup"><span data-stu-id="206f6-135">**Worked in address**</span></span><br><span data-ttu-id="206f6-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="206f6-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="206f6-137">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-137">Read-only</span></span><br><span data-ttu-id="206f6-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-138">Required</span></span> | <span data-ttu-id="206f6-139">Wskazuje, czy adres jest miejscem pracy pracownika.</span><span class="sxs-lookup"><span data-stu-id="206f6-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="206f6-140">**Powiat**</span><span class="sxs-lookup"><span data-stu-id="206f6-140">**County**</span></span><br><span data-ttu-id="206f6-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="206f6-141">mshr_county</span></span><br><span data-ttu-id="206f6-142">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-142">*String*</span></span> | <span data-ttu-id="206f6-143">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-143">Read-only</span></span><br><span data-ttu-id="206f6-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-144">Required</span></span> | <span data-ttu-id="206f6-145">Hrabstwo zdefiniowane dla adresu.</span><span class="sxs-lookup"><span data-stu-id="206f6-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="206f6-146">**Identyfikator adresu pracownika listy płac**</span><span class="sxs-lookup"><span data-stu-id="206f6-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="206f6-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="206f6-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="206f6-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="206f6-148">*GUID*</span></span> | <span data-ttu-id="206f6-149">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-149">Required</span></span><br><span data-ttu-id="206f6-150">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="206f6-150">System generated</span></span> | <span data-ttu-id="206f6-151">Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania adresu.</span><span class="sxs-lookup"><span data-stu-id="206f6-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="206f6-152">**Pole główne**</span><span class="sxs-lookup"><span data-stu-id="206f6-152">**Primary field**</span></span><br><span data-ttu-id="206f6-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="206f6-153">mshr_primaryfield</span></span><br><span data-ttu-id="206f6-154">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-154">*String*</span></span> | <span data-ttu-id="206f6-155">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-155">Read-only</span></span><br><span data-ttu-id="206f6-156">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-156">Required</span></span> |  |
| <span data-ttu-id="206f6-157">**Ulica**</span><span class="sxs-lookup"><span data-stu-id="206f6-157">**Street**</span></span><br><span data-ttu-id="206f6-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="206f6-158">mshr_street</span></span><br><span data-ttu-id="206f6-159">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-159">*String*</span></span> | <span data-ttu-id="206f6-160">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-160">Read-only</span></span><br><span data-ttu-id="206f6-161">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-161">Required</span></span> | <span data-ttu-id="206f6-162">Ulica określona dla adresu.</span><span class="sxs-lookup"><span data-stu-id="206f6-162">The street defined for the address.</span></span> |
| <span data-ttu-id="206f6-163">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="206f6-163">**Valid to**</span></span><br><span data-ttu-id="206f6-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="206f6-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="206f6-165">*Przesunięcie daty i godziny*</span><span class="sxs-lookup"><span data-stu-id="206f6-165">*Date Time Offset*</span></span> | <span data-ttu-id="206f6-166">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-166">Read-only</span></span> <br><span data-ttu-id="206f6-167">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-167">Required</span></span> | <span data-ttu-id="206f6-168">Data, do której adres jest ważny.</span><span class="sxs-lookup"><span data-stu-id="206f6-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="206f6-169">**Identyfikator lokalizacji**</span><span class="sxs-lookup"><span data-stu-id="206f6-169">**Location ID**</span></span><br><span data-ttu-id="206f6-170">mshr_locationidbr>*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="206f6-171">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-171">Read-only</span></span> <br><span data-ttu-id="206f6-172">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-172">Required</span></span> | <span data-ttu-id="206f6-173">Identyfikator dla adresu.</span><span class="sxs-lookup"><span data-stu-id="206f6-173">The ID for the address.</span></span>  |
| <span data-ttu-id="206f6-174">**Kod pocztowy**</span><span class="sxs-lookup"><span data-stu-id="206f6-174">**Postal code**</span></span><br><span data-ttu-id="206f6-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="206f6-175">mshr_zipcode</span></span><br><span data-ttu-id="206f6-176">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-176">*String*</span></span> | <span data-ttu-id="206f6-177">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-177">Read-only</span></span> <br><span data-ttu-id="206f6-178">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-178">Required</span></span> |<span data-ttu-id="206f6-179">Numer identyfikacji zdefiniowany dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="206f6-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="206f6-180">**Mieszkał pod adresem**</span><span class="sxs-lookup"><span data-stu-id="206f6-180">**Lived in address**</span></span><br><span data-ttu-id="206f6-181">mshr_islivedinaddressbr>*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="206f6-182">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-182">Read-only</span></span><br><span data-ttu-id="206f6-183">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-183">Required</span></span> | <span data-ttu-id="206f6-184">Wskazuje, czy adres jest miejscem zamieszkania pracownika.</span><span class="sxs-lookup"><span data-stu-id="206f6-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="206f6-185">**Stanowy**</span><span class="sxs-lookup"><span data-stu-id="206f6-185">**State**</span></span><br><span data-ttu-id="206f6-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="206f6-186">mshr_state</span></span><br><span data-ttu-id="206f6-187">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="206f6-187">*String*</span></span> | <span data-ttu-id="206f6-188">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="206f6-188">Read-only</span></span><br><span data-ttu-id="206f6-189">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="206f6-189">Required</span></span> | <span data-ttu-id="206f6-190">Stan określony dla adresu.</span><span class="sxs-lookup"><span data-stu-id="206f6-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="206f6-191">Przykład kwerendy</span><span class="sxs-lookup"><span data-stu-id="206f6-191">Example query</span></span>

<span data-ttu-id="206f6-192">**Wniosek**</span><span class="sxs-lookup"><span data-stu-id="206f6-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="206f6-193">**Odpowiedź**</span><span class="sxs-lookup"><span data-stu-id="206f6-193">**Response**</span></span>

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
