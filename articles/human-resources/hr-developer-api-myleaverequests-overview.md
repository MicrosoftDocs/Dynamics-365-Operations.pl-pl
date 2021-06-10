---
title: MyLeaveRequests — omówienie
description: Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054963"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="58790-103">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="58790-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="58790-104">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="58790-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="58790-105">Klucz</span><span class="sxs-lookup"><span data-stu-id="58790-105">Key</span></span>

  | <span data-ttu-id="58790-106">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="58790-106">Property Name</span></span> | <span data-ttu-id="58790-107">Typ danych</span><span class="sxs-lookup"><span data-stu-id="58790-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="58790-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="58790-108">dataAreaId</span></span>    | <span data-ttu-id="58790-109">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-109">String</span></span>    |
  | <span data-ttu-id="58790-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="58790-110">RequestId</span></span>     | <span data-ttu-id="58790-111">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-111">String</span></span>    |
  | <span data-ttu-id="58790-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="58790-112">LeaveType</span></span>     | <span data-ttu-id="58790-113">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-113">String</span></span>    |
  | <span data-ttu-id="58790-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="58790-114">LeaveDate</span></span>     | <span data-ttu-id="58790-115">Data</span><span class="sxs-lookup"><span data-stu-id="58790-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="58790-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="58790-116">Properties</span></span>

  | <span data-ttu-id="58790-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="58790-117">Property Name</span></span>     | <span data-ttu-id="58790-118">Typ danych</span><span class="sxs-lookup"><span data-stu-id="58790-118">Data Type</span></span> | <span data-ttu-id="58790-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="58790-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="58790-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="58790-120">dataAreaId</span></span>        | <span data-ttu-id="58790-121">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-121">String</span></span>    | <span data-ttu-id="58790-122">X</span><span class="sxs-lookup"><span data-stu-id="58790-122">X</span></span>        |
  | <span data-ttu-id="58790-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="58790-123">RequestId</span></span>         | <span data-ttu-id="58790-124">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-124">String</span></span>    | <span data-ttu-id="58790-125">X</span><span class="sxs-lookup"><span data-stu-id="58790-125">X</span></span>        |
  | <span data-ttu-id="58790-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="58790-126">LeaveType</span></span>         | <span data-ttu-id="58790-127">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-127">String</span></span>    | <span data-ttu-id="58790-128">X</span><span class="sxs-lookup"><span data-stu-id="58790-128">X</span></span>        |
  | <span data-ttu-id="58790-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="58790-129">LeaveDate</span></span>         | <span data-ttu-id="58790-130">Data</span><span class="sxs-lookup"><span data-stu-id="58790-130">Date</span></span>      | <span data-ttu-id="58790-131">X</span><span class="sxs-lookup"><span data-stu-id="58790-131">X</span></span>        |
  | <span data-ttu-id="58790-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="58790-132">ReasonCodeId</span></span>      | <span data-ttu-id="58790-133">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-133">String</span></span>    |          |
  | <span data-ttu-id="58790-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="58790-134">PersonnelNumber</span></span>   | <span data-ttu-id="58790-135">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-135">String</span></span>    | <span data-ttu-id="58790-136">X</span><span class="sxs-lookup"><span data-stu-id="58790-136">X</span></span>        |
  | <span data-ttu-id="58790-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="58790-137">RequestDate</span></span>       | <span data-ttu-id="58790-138">Data</span><span class="sxs-lookup"><span data-stu-id="58790-138">Date</span></span>      | <span data-ttu-id="58790-139">X</span><span class="sxs-lookup"><span data-stu-id="58790-139">X</span></span>        |
  | <span data-ttu-id="58790-140">Komentarz</span><span class="sxs-lookup"><span data-stu-id="58790-140">Comment</span></span>           | <span data-ttu-id="58790-141">Ciąg</span><span class="sxs-lookup"><span data-stu-id="58790-141">String</span></span>    |          |
  | <span data-ttu-id="58790-142">Stan</span><span class="sxs-lookup"><span data-stu-id="58790-142">Status</span></span>            | <span data-ttu-id="58790-143">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="58790-143">Enum</span></span>      | <span data-ttu-id="58790-144">X</span><span class="sxs-lookup"><span data-stu-id="58790-144">X</span></span>        |
  | <span data-ttu-id="58790-145">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="58790-145">Amount</span></span>            | <span data-ttu-id="58790-146">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="58790-146">Real</span></span>      |          |
  | <span data-ttu-id="58790-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="58790-147">HalfDayDefinition</span></span> | <span data-ttu-id="58790-148">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="58790-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="58790-149">Akcje</span><span class="sxs-lookup"><span data-stu-id="58790-149">Actions</span></span>

 | <span data-ttu-id="58790-150">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="58790-150">Action Name</span></span>                               | <span data-ttu-id="58790-151">Opis</span><span class="sxs-lookup"><span data-stu-id="58790-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="58790-152">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="58790-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="58790-153">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="58790-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="58790-154">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="58790-154">See also</span></span>

- [<span data-ttu-id="58790-155">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="58790-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="58790-156">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="58790-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]