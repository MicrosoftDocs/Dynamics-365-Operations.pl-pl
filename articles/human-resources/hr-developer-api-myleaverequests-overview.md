---
title: MyLeaveRequests — omówienie
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010199"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="e6a43-102">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="e6a43-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="e6a43-103">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="e6a43-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="e6a43-104">Klucz</span><span class="sxs-lookup"><span data-stu-id="e6a43-104">Key</span></span>

  | <span data-ttu-id="e6a43-105">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="e6a43-105">Property Name</span></span> | <span data-ttu-id="e6a43-106">Typ danych</span><span class="sxs-lookup"><span data-stu-id="e6a43-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="e6a43-107">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="e6a43-107">dataAreaId</span></span>    | <span data-ttu-id="e6a43-108">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-108">String</span></span>    |
  | <span data-ttu-id="e6a43-109">RequestId</span><span class="sxs-lookup"><span data-stu-id="e6a43-109">RequestId</span></span>     | <span data-ttu-id="e6a43-110">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-110">String</span></span>    |
  | <span data-ttu-id="e6a43-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="e6a43-111">LeaveType</span></span>     | <span data-ttu-id="e6a43-112">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-112">String</span></span>    |
  | <span data-ttu-id="e6a43-113">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="e6a43-113">LeaveDate</span></span>     | <span data-ttu-id="e6a43-114">Data</span><span class="sxs-lookup"><span data-stu-id="e6a43-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="e6a43-115">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e6a43-115">Properties</span></span>

  | <span data-ttu-id="e6a43-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="e6a43-116">Property Name</span></span>     | <span data-ttu-id="e6a43-117">Typ danych</span><span class="sxs-lookup"><span data-stu-id="e6a43-117">Data Type</span></span> | <span data-ttu-id="e6a43-118">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="e6a43-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="e6a43-119">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="e6a43-119">dataAreaId</span></span>        | <span data-ttu-id="e6a43-120">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-120">String</span></span>    | <span data-ttu-id="e6a43-121">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-121">X</span></span>        |
  | <span data-ttu-id="e6a43-122">RequestId</span><span class="sxs-lookup"><span data-stu-id="e6a43-122">RequestId</span></span>         | <span data-ttu-id="e6a43-123">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-123">String</span></span>    | <span data-ttu-id="e6a43-124">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-124">X</span></span>        |
  | <span data-ttu-id="e6a43-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="e6a43-125">LeaveType</span></span>         | <span data-ttu-id="e6a43-126">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-126">String</span></span>    | <span data-ttu-id="e6a43-127">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-127">X</span></span>        |
  | <span data-ttu-id="e6a43-128">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="e6a43-128">LeaveDate</span></span>         | <span data-ttu-id="e6a43-129">Data</span><span class="sxs-lookup"><span data-stu-id="e6a43-129">Date</span></span>      | <span data-ttu-id="e6a43-130">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-130">X</span></span>        |
  | <span data-ttu-id="e6a43-131">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="e6a43-131">ReasonCodeId</span></span>      | <span data-ttu-id="e6a43-132">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-132">String</span></span>    |          |
  | <span data-ttu-id="e6a43-133">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="e6a43-133">PersonnelNumber</span></span>   | <span data-ttu-id="e6a43-134">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-134">String</span></span>    | <span data-ttu-id="e6a43-135">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-135">X</span></span>        |
  | <span data-ttu-id="e6a43-136">RequestDate</span><span class="sxs-lookup"><span data-stu-id="e6a43-136">RequestDate</span></span>       | <span data-ttu-id="e6a43-137">Data</span><span class="sxs-lookup"><span data-stu-id="e6a43-137">Date</span></span>      | <span data-ttu-id="e6a43-138">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-138">X</span></span>        |
  | <span data-ttu-id="e6a43-139">Komentarz</span><span class="sxs-lookup"><span data-stu-id="e6a43-139">Comment</span></span>           | <span data-ttu-id="e6a43-140">Ciąg</span><span class="sxs-lookup"><span data-stu-id="e6a43-140">String</span></span>    |          |
  | <span data-ttu-id="e6a43-141">Stan</span><span class="sxs-lookup"><span data-stu-id="e6a43-141">Status</span></span>            | <span data-ttu-id="e6a43-142">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="e6a43-142">Enum</span></span>      | <span data-ttu-id="e6a43-143">X</span><span class="sxs-lookup"><span data-stu-id="e6a43-143">X</span></span>        |
  | <span data-ttu-id="e6a43-144">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="e6a43-144">Amount</span></span>            | <span data-ttu-id="e6a43-145">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="e6a43-145">Real</span></span>      |          |
  | <span data-ttu-id="e6a43-146">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="e6a43-146">HalfDayDefinition</span></span> | <span data-ttu-id="e6a43-147">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="e6a43-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="e6a43-148">Akcje</span><span class="sxs-lookup"><span data-stu-id="e6a43-148">Actions</span></span>

 | <span data-ttu-id="e6a43-149">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="e6a43-149">Action Name</span></span>                               | <span data-ttu-id="e6a43-150">Opis</span><span class="sxs-lookup"><span data-stu-id="e6a43-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="e6a43-151">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="e6a43-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="e6a43-152">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="e6a43-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e6a43-153">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e6a43-153">See also</span></span>

- [<span data-ttu-id="e6a43-154">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="e6a43-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="e6a43-155">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="e6a43-155">Authentication</span></span>](hr-developer-api-authentication.md)