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
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092044"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="f9e82-103">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="f9e82-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="f9e82-104">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="f9e82-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="f9e82-105">Klucz</span><span class="sxs-lookup"><span data-stu-id="f9e82-105">Key</span></span>

  | <span data-ttu-id="f9e82-106">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="f9e82-106">Property Name</span></span> | <span data-ttu-id="f9e82-107">Typ danych</span><span class="sxs-lookup"><span data-stu-id="f9e82-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="f9e82-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="f9e82-108">dataAreaId</span></span>    | <span data-ttu-id="f9e82-109">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-109">String</span></span>    |
  | <span data-ttu-id="f9e82-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="f9e82-110">RequestId</span></span>     | <span data-ttu-id="f9e82-111">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-111">String</span></span>    |
  | <span data-ttu-id="f9e82-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="f9e82-112">LeaveType</span></span>     | <span data-ttu-id="f9e82-113">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-113">String</span></span>    |
  | <span data-ttu-id="f9e82-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="f9e82-114">LeaveDate</span></span>     | <span data-ttu-id="f9e82-115">Data</span><span class="sxs-lookup"><span data-stu-id="f9e82-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="f9e82-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f9e82-116">Properties</span></span>

  | <span data-ttu-id="f9e82-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="f9e82-117">Property Name</span></span>     | <span data-ttu-id="f9e82-118">Typ danych</span><span class="sxs-lookup"><span data-stu-id="f9e82-118">Data Type</span></span> | <span data-ttu-id="f9e82-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="f9e82-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="f9e82-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="f9e82-120">dataAreaId</span></span>        | <span data-ttu-id="f9e82-121">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-121">String</span></span>    | <span data-ttu-id="f9e82-122">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-122">X</span></span>        |
  | <span data-ttu-id="f9e82-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="f9e82-123">RequestId</span></span>         | <span data-ttu-id="f9e82-124">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-124">String</span></span>    | <span data-ttu-id="f9e82-125">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-125">X</span></span>        |
  | <span data-ttu-id="f9e82-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="f9e82-126">LeaveType</span></span>         | <span data-ttu-id="f9e82-127">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-127">String</span></span>    | <span data-ttu-id="f9e82-128">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-128">X</span></span>        |
  | <span data-ttu-id="f9e82-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="f9e82-129">LeaveDate</span></span>         | <span data-ttu-id="f9e82-130">Data</span><span class="sxs-lookup"><span data-stu-id="f9e82-130">Date</span></span>      | <span data-ttu-id="f9e82-131">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-131">X</span></span>        |
  | <span data-ttu-id="f9e82-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="f9e82-132">ReasonCodeId</span></span>      | <span data-ttu-id="f9e82-133">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-133">String</span></span>    |          |
  | <span data-ttu-id="f9e82-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="f9e82-134">PersonnelNumber</span></span>   | <span data-ttu-id="f9e82-135">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-135">String</span></span>    | <span data-ttu-id="f9e82-136">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-136">X</span></span>        |
  | <span data-ttu-id="f9e82-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="f9e82-137">RequestDate</span></span>       | <span data-ttu-id="f9e82-138">Data</span><span class="sxs-lookup"><span data-stu-id="f9e82-138">Date</span></span>      | <span data-ttu-id="f9e82-139">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-139">X</span></span>        |
  | <span data-ttu-id="f9e82-140">Komentarz</span><span class="sxs-lookup"><span data-stu-id="f9e82-140">Comment</span></span>           | <span data-ttu-id="f9e82-141">Ciąg</span><span class="sxs-lookup"><span data-stu-id="f9e82-141">String</span></span>    |          |
  | <span data-ttu-id="f9e82-142">Stan</span><span class="sxs-lookup"><span data-stu-id="f9e82-142">Status</span></span>            | <span data-ttu-id="f9e82-143">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="f9e82-143">Enum</span></span>      | <span data-ttu-id="f9e82-144">X</span><span class="sxs-lookup"><span data-stu-id="f9e82-144">X</span></span>        |
  | <span data-ttu-id="f9e82-145">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="f9e82-145">Amount</span></span>            | <span data-ttu-id="f9e82-146">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="f9e82-146">Real</span></span>      |          |
  | <span data-ttu-id="f9e82-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="f9e82-147">HalfDayDefinition</span></span> | <span data-ttu-id="f9e82-148">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="f9e82-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="f9e82-149">Akcje</span><span class="sxs-lookup"><span data-stu-id="f9e82-149">Actions</span></span>

 | <span data-ttu-id="f9e82-150">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="f9e82-150">Action Name</span></span>                               | <span data-ttu-id="f9e82-151">Opis</span><span class="sxs-lookup"><span data-stu-id="f9e82-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="f9e82-152">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="f9e82-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="f9e82-153">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="f9e82-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f9e82-154">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f9e82-154">See also</span></span>

- [<span data-ttu-id="f9e82-155">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f9e82-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="f9e82-156">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="f9e82-156">Authentication</span></span>](hr-developer-api-authentication.md)