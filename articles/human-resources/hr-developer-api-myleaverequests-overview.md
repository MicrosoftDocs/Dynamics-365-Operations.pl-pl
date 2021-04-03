---
title: MyLeaveRequests — omówienie
description: Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465517"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="76ced-103">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="76ced-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="76ced-104">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="76ced-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="76ced-105">Klucz</span><span class="sxs-lookup"><span data-stu-id="76ced-105">Key</span></span>

  | <span data-ttu-id="76ced-106">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="76ced-106">Property Name</span></span> | <span data-ttu-id="76ced-107">Typ danych</span><span class="sxs-lookup"><span data-stu-id="76ced-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="76ced-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="76ced-108">dataAreaId</span></span>    | <span data-ttu-id="76ced-109">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-109">String</span></span>    |
  | <span data-ttu-id="76ced-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="76ced-110">RequestId</span></span>     | <span data-ttu-id="76ced-111">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-111">String</span></span>    |
  | <span data-ttu-id="76ced-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="76ced-112">LeaveType</span></span>     | <span data-ttu-id="76ced-113">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-113">String</span></span>    |
  | <span data-ttu-id="76ced-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="76ced-114">LeaveDate</span></span>     | <span data-ttu-id="76ced-115">Data</span><span class="sxs-lookup"><span data-stu-id="76ced-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="76ced-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="76ced-116">Properties</span></span>

  | <span data-ttu-id="76ced-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="76ced-117">Property Name</span></span>     | <span data-ttu-id="76ced-118">Typ danych</span><span class="sxs-lookup"><span data-stu-id="76ced-118">Data Type</span></span> | <span data-ttu-id="76ced-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="76ced-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="76ced-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="76ced-120">dataAreaId</span></span>        | <span data-ttu-id="76ced-121">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-121">String</span></span>    | <span data-ttu-id="76ced-122">X</span><span class="sxs-lookup"><span data-stu-id="76ced-122">X</span></span>        |
  | <span data-ttu-id="76ced-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="76ced-123">RequestId</span></span>         | <span data-ttu-id="76ced-124">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-124">String</span></span>    | <span data-ttu-id="76ced-125">X</span><span class="sxs-lookup"><span data-stu-id="76ced-125">X</span></span>        |
  | <span data-ttu-id="76ced-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="76ced-126">LeaveType</span></span>         | <span data-ttu-id="76ced-127">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-127">String</span></span>    | <span data-ttu-id="76ced-128">X</span><span class="sxs-lookup"><span data-stu-id="76ced-128">X</span></span>        |
  | <span data-ttu-id="76ced-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="76ced-129">LeaveDate</span></span>         | <span data-ttu-id="76ced-130">Data</span><span class="sxs-lookup"><span data-stu-id="76ced-130">Date</span></span>      | <span data-ttu-id="76ced-131">X</span><span class="sxs-lookup"><span data-stu-id="76ced-131">X</span></span>        |
  | <span data-ttu-id="76ced-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="76ced-132">ReasonCodeId</span></span>      | <span data-ttu-id="76ced-133">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-133">String</span></span>    |          |
  | <span data-ttu-id="76ced-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="76ced-134">PersonnelNumber</span></span>   | <span data-ttu-id="76ced-135">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-135">String</span></span>    | <span data-ttu-id="76ced-136">X</span><span class="sxs-lookup"><span data-stu-id="76ced-136">X</span></span>        |
  | <span data-ttu-id="76ced-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="76ced-137">RequestDate</span></span>       | <span data-ttu-id="76ced-138">Data</span><span class="sxs-lookup"><span data-stu-id="76ced-138">Date</span></span>      | <span data-ttu-id="76ced-139">X</span><span class="sxs-lookup"><span data-stu-id="76ced-139">X</span></span>        |
  | <span data-ttu-id="76ced-140">Komentarz</span><span class="sxs-lookup"><span data-stu-id="76ced-140">Comment</span></span>           | <span data-ttu-id="76ced-141">Ciąg</span><span class="sxs-lookup"><span data-stu-id="76ced-141">String</span></span>    |          |
  | <span data-ttu-id="76ced-142">Stan</span><span class="sxs-lookup"><span data-stu-id="76ced-142">Status</span></span>            | <span data-ttu-id="76ced-143">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="76ced-143">Enum</span></span>      | <span data-ttu-id="76ced-144">X</span><span class="sxs-lookup"><span data-stu-id="76ced-144">X</span></span>        |
  | <span data-ttu-id="76ced-145">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="76ced-145">Amount</span></span>            | <span data-ttu-id="76ced-146">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="76ced-146">Real</span></span>      |          |
  | <span data-ttu-id="76ced-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="76ced-147">HalfDayDefinition</span></span> | <span data-ttu-id="76ced-148">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="76ced-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="76ced-149">Akcje</span><span class="sxs-lookup"><span data-stu-id="76ced-149">Actions</span></span>

 | <span data-ttu-id="76ced-150">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="76ced-150">Action Name</span></span>                               | <span data-ttu-id="76ced-151">Opis</span><span class="sxs-lookup"><span data-stu-id="76ced-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="76ced-152">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="76ced-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="76ced-153">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="76ced-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="76ced-154">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="76ced-154">See also</span></span>

- [<span data-ttu-id="76ced-155">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="76ced-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="76ced-156">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="76ced-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]