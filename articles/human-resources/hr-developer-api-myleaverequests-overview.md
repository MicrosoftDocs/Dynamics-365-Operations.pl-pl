---
title: MyLeaveRequests — omówienie
description: Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419999"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="2e6b0-103">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="2e6b0-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="2e6b0-104">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="2e6b0-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="2e6b0-105">Klucz</span><span class="sxs-lookup"><span data-stu-id="2e6b0-105">Key</span></span>

  | <span data-ttu-id="2e6b0-106">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="2e6b0-106">Property Name</span></span> | <span data-ttu-id="2e6b0-107">Typ danych</span><span class="sxs-lookup"><span data-stu-id="2e6b0-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="2e6b0-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="2e6b0-108">dataAreaId</span></span>    | <span data-ttu-id="2e6b0-109">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-109">String</span></span>    |
  | <span data-ttu-id="2e6b0-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="2e6b0-110">RequestId</span></span>     | <span data-ttu-id="2e6b0-111">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-111">String</span></span>    |
  | <span data-ttu-id="2e6b0-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="2e6b0-112">LeaveType</span></span>     | <span data-ttu-id="2e6b0-113">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-113">String</span></span>    |
  | <span data-ttu-id="2e6b0-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="2e6b0-114">LeaveDate</span></span>     | <span data-ttu-id="2e6b0-115">Data</span><span class="sxs-lookup"><span data-stu-id="2e6b0-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="2e6b0-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="2e6b0-116">Properties</span></span>

  | <span data-ttu-id="2e6b0-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="2e6b0-117">Property Name</span></span>     | <span data-ttu-id="2e6b0-118">Typ danych</span><span class="sxs-lookup"><span data-stu-id="2e6b0-118">Data Type</span></span> | <span data-ttu-id="2e6b0-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="2e6b0-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="2e6b0-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="2e6b0-120">dataAreaId</span></span>        | <span data-ttu-id="2e6b0-121">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-121">String</span></span>    | <span data-ttu-id="2e6b0-122">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-122">X</span></span>        |
  | <span data-ttu-id="2e6b0-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="2e6b0-123">RequestId</span></span>         | <span data-ttu-id="2e6b0-124">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-124">String</span></span>    | <span data-ttu-id="2e6b0-125">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-125">X</span></span>        |
  | <span data-ttu-id="2e6b0-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="2e6b0-126">LeaveType</span></span>         | <span data-ttu-id="2e6b0-127">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-127">String</span></span>    | <span data-ttu-id="2e6b0-128">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-128">X</span></span>        |
  | <span data-ttu-id="2e6b0-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="2e6b0-129">LeaveDate</span></span>         | <span data-ttu-id="2e6b0-130">Data</span><span class="sxs-lookup"><span data-stu-id="2e6b0-130">Date</span></span>      | <span data-ttu-id="2e6b0-131">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-131">X</span></span>        |
  | <span data-ttu-id="2e6b0-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="2e6b0-132">ReasonCodeId</span></span>      | <span data-ttu-id="2e6b0-133">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-133">String</span></span>    |          |
  | <span data-ttu-id="2e6b0-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="2e6b0-134">PersonnelNumber</span></span>   | <span data-ttu-id="2e6b0-135">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-135">String</span></span>    | <span data-ttu-id="2e6b0-136">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-136">X</span></span>        |
  | <span data-ttu-id="2e6b0-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="2e6b0-137">RequestDate</span></span>       | <span data-ttu-id="2e6b0-138">Data</span><span class="sxs-lookup"><span data-stu-id="2e6b0-138">Date</span></span>      | <span data-ttu-id="2e6b0-139">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-139">X</span></span>        |
  | <span data-ttu-id="2e6b0-140">Komentarz</span><span class="sxs-lookup"><span data-stu-id="2e6b0-140">Comment</span></span>           | <span data-ttu-id="2e6b0-141">Ciąg</span><span class="sxs-lookup"><span data-stu-id="2e6b0-141">String</span></span>    |          |
  | <span data-ttu-id="2e6b0-142">Stan</span><span class="sxs-lookup"><span data-stu-id="2e6b0-142">Status</span></span>            | <span data-ttu-id="2e6b0-143">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="2e6b0-143">Enum</span></span>      | <span data-ttu-id="2e6b0-144">X</span><span class="sxs-lookup"><span data-stu-id="2e6b0-144">X</span></span>        |
  | <span data-ttu-id="2e6b0-145">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="2e6b0-145">Amount</span></span>            | <span data-ttu-id="2e6b0-146">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="2e6b0-146">Real</span></span>      |          |
  | <span data-ttu-id="2e6b0-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="2e6b0-147">HalfDayDefinition</span></span> | <span data-ttu-id="2e6b0-148">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="2e6b0-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="2e6b0-149">Akcje</span><span class="sxs-lookup"><span data-stu-id="2e6b0-149">Actions</span></span>

 | <span data-ttu-id="2e6b0-150">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="2e6b0-150">Action Name</span></span>                               | <span data-ttu-id="2e6b0-151">Opis</span><span class="sxs-lookup"><span data-stu-id="2e6b0-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="2e6b0-152">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="2e6b0-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="2e6b0-153">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="2e6b0-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2e6b0-154">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2e6b0-154">See also</span></span>

- [<span data-ttu-id="2e6b0-155">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2e6b0-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="2e6b0-156">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="2e6b0-156">Authentication</span></span>](hr-developer-api-authentication.md)