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
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115543"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="957f8-103">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="957f8-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="957f8-104">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="957f8-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="957f8-105">Klucz</span><span class="sxs-lookup"><span data-stu-id="957f8-105">Key</span></span>

  | <span data-ttu-id="957f8-106">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="957f8-106">Property Name</span></span> | <span data-ttu-id="957f8-107">Typ danych</span><span class="sxs-lookup"><span data-stu-id="957f8-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="957f8-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="957f8-108">dataAreaId</span></span>    | <span data-ttu-id="957f8-109">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-109">String</span></span>    |
  | <span data-ttu-id="957f8-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="957f8-110">RequestId</span></span>     | <span data-ttu-id="957f8-111">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-111">String</span></span>    |
  | <span data-ttu-id="957f8-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="957f8-112">LeaveType</span></span>     | <span data-ttu-id="957f8-113">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-113">String</span></span>    |
  | <span data-ttu-id="957f8-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="957f8-114">LeaveDate</span></span>     | <span data-ttu-id="957f8-115">Data</span><span class="sxs-lookup"><span data-stu-id="957f8-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="957f8-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="957f8-116">Properties</span></span>

  | <span data-ttu-id="957f8-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="957f8-117">Property Name</span></span>     | <span data-ttu-id="957f8-118">Typ danych</span><span class="sxs-lookup"><span data-stu-id="957f8-118">Data Type</span></span> | <span data-ttu-id="957f8-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="957f8-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="957f8-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="957f8-120">dataAreaId</span></span>        | <span data-ttu-id="957f8-121">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-121">String</span></span>    | <span data-ttu-id="957f8-122">X</span><span class="sxs-lookup"><span data-stu-id="957f8-122">X</span></span>        |
  | <span data-ttu-id="957f8-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="957f8-123">RequestId</span></span>         | <span data-ttu-id="957f8-124">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-124">String</span></span>    | <span data-ttu-id="957f8-125">X</span><span class="sxs-lookup"><span data-stu-id="957f8-125">X</span></span>        |
  | <span data-ttu-id="957f8-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="957f8-126">LeaveType</span></span>         | <span data-ttu-id="957f8-127">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-127">String</span></span>    | <span data-ttu-id="957f8-128">X</span><span class="sxs-lookup"><span data-stu-id="957f8-128">X</span></span>        |
  | <span data-ttu-id="957f8-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="957f8-129">LeaveDate</span></span>         | <span data-ttu-id="957f8-130">Data</span><span class="sxs-lookup"><span data-stu-id="957f8-130">Date</span></span>      | <span data-ttu-id="957f8-131">X</span><span class="sxs-lookup"><span data-stu-id="957f8-131">X</span></span>        |
  | <span data-ttu-id="957f8-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="957f8-132">ReasonCodeId</span></span>      | <span data-ttu-id="957f8-133">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-133">String</span></span>    |          |
  | <span data-ttu-id="957f8-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="957f8-134">PersonnelNumber</span></span>   | <span data-ttu-id="957f8-135">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-135">String</span></span>    | <span data-ttu-id="957f8-136">X</span><span class="sxs-lookup"><span data-stu-id="957f8-136">X</span></span>        |
  | <span data-ttu-id="957f8-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="957f8-137">RequestDate</span></span>       | <span data-ttu-id="957f8-138">Data</span><span class="sxs-lookup"><span data-stu-id="957f8-138">Date</span></span>      | <span data-ttu-id="957f8-139">X</span><span class="sxs-lookup"><span data-stu-id="957f8-139">X</span></span>        |
  | <span data-ttu-id="957f8-140">Komentarz</span><span class="sxs-lookup"><span data-stu-id="957f8-140">Comment</span></span>           | <span data-ttu-id="957f8-141">Ciąg</span><span class="sxs-lookup"><span data-stu-id="957f8-141">String</span></span>    |          |
  | <span data-ttu-id="957f8-142">Stan</span><span class="sxs-lookup"><span data-stu-id="957f8-142">Status</span></span>            | <span data-ttu-id="957f8-143">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="957f8-143">Enum</span></span>      | <span data-ttu-id="957f8-144">X</span><span class="sxs-lookup"><span data-stu-id="957f8-144">X</span></span>        |
  | <span data-ttu-id="957f8-145">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="957f8-145">Amount</span></span>            | <span data-ttu-id="957f8-146">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="957f8-146">Real</span></span>      |          |
  | <span data-ttu-id="957f8-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="957f8-147">HalfDayDefinition</span></span> | <span data-ttu-id="957f8-148">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="957f8-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="957f8-149">Akcje</span><span class="sxs-lookup"><span data-stu-id="957f8-149">Actions</span></span>

 | <span data-ttu-id="957f8-150">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="957f8-150">Action Name</span></span>                               | <span data-ttu-id="957f8-151">Opis</span><span class="sxs-lookup"><span data-stu-id="957f8-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="957f8-152">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="957f8-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="957f8-153">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="957f8-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="957f8-154">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="957f8-154">See also</span></span>

- [<span data-ttu-id="957f8-155">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="957f8-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="957f8-156">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="957f8-156">Authentication</span></span>](hr-developer-api-authentication.md)