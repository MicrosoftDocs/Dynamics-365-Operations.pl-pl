---
title: Stan wniosku o rekrutację
description: W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125961"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="1a139-103">Stan wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="1a139-103">Recruiting request status</span></span>

<span data-ttu-id="1a139-104">W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1a139-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1a139-105">Nazwa fizyczna: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="1a139-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="1a139-106">To wyliczenie zapewnia zestaw opcji dla wartości statusu RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="1a139-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="1a139-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="1a139-107">Value</span></span> | <span data-ttu-id="1a139-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="1a139-108">Label</span></span> | <span data-ttu-id="1a139-109">opis</span><span class="sxs-lookup"><span data-stu-id="1a139-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1a139-110">200000000</span><span class="sxs-lookup"><span data-stu-id="1a139-110">200000000</span></span> | <span data-ttu-id="1a139-111">Robocza</span><span class="sxs-lookup"><span data-stu-id="1a139-111">Draft</span></span> | <span data-ttu-id="1a139-112">Wniosek jest w wersji roboczej i nie jest gotowy do aktywnej rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="1a139-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="1a139-113">200000001</span><span class="sxs-lookup"><span data-stu-id="1a139-113">200000001</span></span> | <span data-ttu-id="1a139-114">W trakcie przeglądu</span><span class="sxs-lookup"><span data-stu-id="1a139-114">In Review</span></span> | <span data-ttu-id="1a139-115">Żądanie zostało przesłane i jest kierowane do zatwierdzenia przez przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="1a139-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="1a139-116">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1a139-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="1a139-117">200000002</span><span class="sxs-lookup"><span data-stu-id="1a139-117">200000002</span></span> | <span data-ttu-id="1a139-118">Oczekująca</span><span class="sxs-lookup"><span data-stu-id="1a139-118">Pending</span></span> | <span data-ttu-id="1a139-119">Żądanie oczekuje na akcję przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1a139-119">The request is pending workflow action.</span></span> <span data-ttu-id="1a139-120">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1a139-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="1a139-121">200000003</span><span class="sxs-lookup"><span data-stu-id="1a139-121">200000003</span></span> | <span data-ttu-id="1a139-122">Anulowana</span><span class="sxs-lookup"><span data-stu-id="1a139-122">Canceled</span></span> | <span data-ttu-id="1a139-123">Żądanie zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="1a139-123">The request has been canceled.</span></span> <span data-ttu-id="1a139-124">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1a139-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="1a139-125">200000004</span><span class="sxs-lookup"><span data-stu-id="1a139-125">200000004</span></span> | <span data-ttu-id="1a139-126">Odrzucone</span><span class="sxs-lookup"><span data-stu-id="1a139-126">Denied</span></span> | <span data-ttu-id="1a139-127">Żądanie zostało odrzucone.</span><span class="sxs-lookup"><span data-stu-id="1a139-127">The request has been denied.</span></span> <span data-ttu-id="1a139-128">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1a139-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="1a139-129">200000005</span><span class="sxs-lookup"><span data-stu-id="1a139-129">200000005</span></span> | <span data-ttu-id="1a139-130">Aktywni</span><span class="sxs-lookup"><span data-stu-id="1a139-130">Active</span></span> | <span data-ttu-id="1a139-131">Każdy przepływ pracy jest ukończony i zatwierdzony, a żądanie jest gotowe do aktywnej rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="1a139-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="1a139-132">200000006</span><span class="sxs-lookup"><span data-stu-id="1a139-132">200000006</span></span> | <span data-ttu-id="1a139-133">Zamknięte</span><span class="sxs-lookup"><span data-stu-id="1a139-133">Closed</span></span> | <span data-ttu-id="1a139-134">Wniosek o rekrutację jest zakończony.</span><span class="sxs-lookup"><span data-stu-id="1a139-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1a139-135">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1a139-135">See also</span></span>

[<span data-ttu-id="1a139-136">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="1a139-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1a139-137">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="1a139-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
