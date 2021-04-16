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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803640"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="4a950-103">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="4a950-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4a950-104">Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.</span><span class="sxs-lookup"><span data-stu-id="4a950-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="4a950-105">Klucz</span><span class="sxs-lookup"><span data-stu-id="4a950-105">Key</span></span>

  | <span data-ttu-id="4a950-106">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="4a950-106">Property Name</span></span> | <span data-ttu-id="4a950-107">Typ danych</span><span class="sxs-lookup"><span data-stu-id="4a950-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="4a950-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="4a950-108">dataAreaId</span></span>    | <span data-ttu-id="4a950-109">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-109">String</span></span>    |
  | <span data-ttu-id="4a950-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="4a950-110">RequestId</span></span>     | <span data-ttu-id="4a950-111">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-111">String</span></span>    |
  | <span data-ttu-id="4a950-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="4a950-112">LeaveType</span></span>     | <span data-ttu-id="4a950-113">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-113">String</span></span>    |
  | <span data-ttu-id="4a950-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="4a950-114">LeaveDate</span></span>     | <span data-ttu-id="4a950-115">Data</span><span class="sxs-lookup"><span data-stu-id="4a950-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="4a950-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="4a950-116">Properties</span></span>

  | <span data-ttu-id="4a950-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="4a950-117">Property Name</span></span>     | <span data-ttu-id="4a950-118">Typ danych</span><span class="sxs-lookup"><span data-stu-id="4a950-118">Data Type</span></span> | <span data-ttu-id="4a950-119">Potrzebne</span><span class="sxs-lookup"><span data-stu-id="4a950-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="4a950-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="4a950-120">dataAreaId</span></span>        | <span data-ttu-id="4a950-121">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-121">String</span></span>    | <span data-ttu-id="4a950-122">X</span><span class="sxs-lookup"><span data-stu-id="4a950-122">X</span></span>        |
  | <span data-ttu-id="4a950-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="4a950-123">RequestId</span></span>         | <span data-ttu-id="4a950-124">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-124">String</span></span>    | <span data-ttu-id="4a950-125">X</span><span class="sxs-lookup"><span data-stu-id="4a950-125">X</span></span>        |
  | <span data-ttu-id="4a950-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="4a950-126">LeaveType</span></span>         | <span data-ttu-id="4a950-127">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-127">String</span></span>    | <span data-ttu-id="4a950-128">X</span><span class="sxs-lookup"><span data-stu-id="4a950-128">X</span></span>        |
  | <span data-ttu-id="4a950-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="4a950-129">LeaveDate</span></span>         | <span data-ttu-id="4a950-130">Data</span><span class="sxs-lookup"><span data-stu-id="4a950-130">Date</span></span>      | <span data-ttu-id="4a950-131">X</span><span class="sxs-lookup"><span data-stu-id="4a950-131">X</span></span>        |
  | <span data-ttu-id="4a950-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="4a950-132">ReasonCodeId</span></span>      | <span data-ttu-id="4a950-133">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-133">String</span></span>    |          |
  | <span data-ttu-id="4a950-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="4a950-134">PersonnelNumber</span></span>   | <span data-ttu-id="4a950-135">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-135">String</span></span>    | <span data-ttu-id="4a950-136">X</span><span class="sxs-lookup"><span data-stu-id="4a950-136">X</span></span>        |
  | <span data-ttu-id="4a950-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="4a950-137">RequestDate</span></span>       | <span data-ttu-id="4a950-138">Data</span><span class="sxs-lookup"><span data-stu-id="4a950-138">Date</span></span>      | <span data-ttu-id="4a950-139">X</span><span class="sxs-lookup"><span data-stu-id="4a950-139">X</span></span>        |
  | <span data-ttu-id="4a950-140">Komentarz</span><span class="sxs-lookup"><span data-stu-id="4a950-140">Comment</span></span>           | <span data-ttu-id="4a950-141">Ciąg</span><span class="sxs-lookup"><span data-stu-id="4a950-141">String</span></span>    |          |
  | <span data-ttu-id="4a950-142">Stan</span><span class="sxs-lookup"><span data-stu-id="4a950-142">Status</span></span>            | <span data-ttu-id="4a950-143">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="4a950-143">Enum</span></span>      | <span data-ttu-id="4a950-144">X</span><span class="sxs-lookup"><span data-stu-id="4a950-144">X</span></span>        |
  | <span data-ttu-id="4a950-145">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="4a950-145">Amount</span></span>            | <span data-ttu-id="4a950-146">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="4a950-146">Real</span></span>      |          |
  | <span data-ttu-id="4a950-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="4a950-147">HalfDayDefinition</span></span> | <span data-ttu-id="4a950-148">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="4a950-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="4a950-149">Akcje</span><span class="sxs-lookup"><span data-stu-id="4a950-149">Actions</span></span>

 | <span data-ttu-id="4a950-150">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="4a950-150">Action Name</span></span>                               | <span data-ttu-id="4a950-151">Opis</span><span class="sxs-lookup"><span data-stu-id="4a950-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="4a950-152">przesyłanie</span><span class="sxs-lookup"><span data-stu-id="4a950-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="4a950-153">Przesyłanie wniosku do przetworzenia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="4a950-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4a950-154">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4a950-154">See also</span></span>

- [<span data-ttu-id="4a950-155">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="4a950-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="4a950-156">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="4a950-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]