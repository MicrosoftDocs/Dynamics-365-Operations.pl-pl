---
title: Typy kontroli
description: W tym temacie opisano jednostkę Typy kontroli dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb99c2fb57df883ab376c7f6aab547073bd0ff
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058303"
---
# <a name="screening-types"></a><span data-ttu-id="f5bd3-103">Typy kontroli</span><span class="sxs-lookup"><span data-stu-id="f5bd3-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f5bd3-104">W tym temacie opisano jednostkę Typy kontroli dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f5bd3-105">Nazwa fizyczna: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="f5bd3-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="f5bd3-106">opis</span><span class="sxs-lookup"><span data-stu-id="f5bd3-106">Description</span></span>

<span data-ttu-id="f5bd3-107">Podmiot ten opisuje typy kontroli ustanowione przez firmę dla procesów poprzedzających zatrudnienie i trwających kontroli pracowników.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f5bd3-108">Reprezentacja JSON</span><span class="sxs-lookup"><span data-stu-id="f5bd3-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="f5bd3-109">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f5bd3-109">Properties</span></span>

| <span data-ttu-id="f5bd3-110">Właściwość</span><span class="sxs-lookup"><span data-stu-id="f5bd3-110">Property</span></span><br><span data-ttu-id="f5bd3-111">**Nazwa fizyczna**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-111">**Physical name**</span></span><br><span data-ttu-id="f5bd3-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-112">**_Type_**</span></span> | <span data-ttu-id="f5bd3-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="f5bd3-113">Use</span></span> | <span data-ttu-id="f5bd3-114">opis</span><span class="sxs-lookup"><span data-stu-id="f5bd3-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f5bd3-115">**Identyfikator jednostki typu kontroli**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="f5bd3-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="f5bd3-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="f5bd3-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f5bd3-117">*GUID*</span></span> | <span data-ttu-id="f5bd3-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f5bd3-118">Read-only</span></span><br><span data-ttu-id="f5bd3-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f5bd3-119">Required</span></span><br><span data-ttu-id="f5bd3-120">Wygenerowany przez system</span><span class="sxs-lookup"><span data-stu-id="f5bd3-120">System-generated</span></span> | <span data-ttu-id="f5bd3-121">Unikalny identyfikator podstawowy dla typu kontroli rekordu.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="f5bd3-122">**Identyfikator typu kontroli**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-122">**Screening Type ID**</span></span><br><span data-ttu-id="f5bd3-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="f5bd3-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="f5bd3-124">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f5bd3-124">*String*</span></span> | <span data-ttu-id="f5bd3-125">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f5bd3-125">Read/write</span></span><br><span data-ttu-id="f5bd3-126">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f5bd3-126">Required</span></span> | <span data-ttu-id="f5bd3-127">Unikalny identyfikator zdefiniowany przez użytkownika dla typu kontroli.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="f5bd3-128">**Opis**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-128">**Description**</span></span><br><span data-ttu-id="f5bd3-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="f5bd3-129">mshr_description</span></span><br><span data-ttu-id="f5bd3-130">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f5bd3-130">*String*</span></span> | <span data-ttu-id="f5bd3-131">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f5bd3-131">Read/write</span></span><br><span data-ttu-id="f5bd3-132">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f5bd3-132">Required</span></span> | <span data-ttu-id="f5bd3-133">Opis typu kontroli.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-133">The description of the screening type.</span></span> |
| <span data-ttu-id="f5bd3-134">**Jednostka częstotliwości**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-134">**Frequency Unit**</span></span><br><span data-ttu-id="f5bd3-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="f5bd3-135">mshr_frequencyunit</span></span><br><span data-ttu-id="f5bd3-136">*zestaw opcji mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="f5bd3-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="f5bd3-137">Czytaj/zapisz</span><span class="sxs-lookup"><span data-stu-id="f5bd3-137">Read/write</span></span><br><span data-ttu-id="f5bd3-138">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f5bd3-138">Required</span></span> | <span data-ttu-id="f5bd3-139">Opisuje częstotliwość, z jaką kontrola musi zostać zakończona dla przypisanej osoby.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="f5bd3-140">**Generuj formularz**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-140">**Generate From**</span></span><br><span data-ttu-id="f5bd3-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="f5bd3-141">mshr_generatefrom</span></span><br><span data-ttu-id="f5bd3-142">*zestaw opcji mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="f5bd3-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="f5bd3-143">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="f5bd3-143">Read-write</span></span><br><span data-ttu-id="f5bd3-144">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f5bd3-144">Required</span></span> | <span data-ttu-id="f5bd3-145">Jeśli wartość Częstotliwość jest dowolną wartością inną niż „Tylko raz”, wartość GenerateFrom określa datę, od której ma zostać obliczone następne zdarzenie przesiewowe.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="f5bd3-146">**Zakres częstotliwości**</span><span class="sxs-lookup"><span data-stu-id="f5bd3-146">**Frequency Interval**</span></span><br><span data-ttu-id="f5bd3-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="f5bd3-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="f5bd3-148">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="f5bd3-148">*Integer*</span></span> | <span data-ttu-id="f5bd3-149">Czytaj-zapisz</span><span class="sxs-lookup"><span data-stu-id="f5bd3-149">Read-write</span></span><br><span data-ttu-id="f5bd3-150">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f5bd3-150">Required</span></span> | <span data-ttu-id="f5bd3-151">Jeśli wartość Częstotliwość ma wartość inną niż „Tylko raz”, należy zdefiniować interwał jednostek czasu między poszczególnymi zdarzeniami kontroli.</span><span class="sxs-lookup"><span data-stu-id="f5bd3-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f5bd3-152">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f5bd3-152">See also</span></span>

[<span data-ttu-id="f5bd3-153">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="f5bd3-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f5bd3-154">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="f5bd3-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]