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
ms.openlocfilehash: 0032e6bfdbfd2792dafda8bf24a1b0cbc551740d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464653"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="44c58-103">Stan wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="44c58-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="44c58-104">W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="44c58-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="44c58-105">Nazwa fizyczna: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="44c58-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="44c58-106">To wyliczenie zapewnia zestaw opcji dla wartości statusu RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="44c58-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="44c58-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="44c58-107">Value</span></span> | <span data-ttu-id="44c58-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="44c58-108">Label</span></span> | <span data-ttu-id="44c58-109">opis</span><span class="sxs-lookup"><span data-stu-id="44c58-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="44c58-110">200000000</span><span class="sxs-lookup"><span data-stu-id="44c58-110">200000000</span></span> | <span data-ttu-id="44c58-111">Robocza</span><span class="sxs-lookup"><span data-stu-id="44c58-111">Draft</span></span> | <span data-ttu-id="44c58-112">Wniosek jest w wersji roboczej i nie jest gotowy do aktywnej rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="44c58-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="44c58-113">200000001</span><span class="sxs-lookup"><span data-stu-id="44c58-113">200000001</span></span> | <span data-ttu-id="44c58-114">W trakcie przeglądu</span><span class="sxs-lookup"><span data-stu-id="44c58-114">In Review</span></span> | <span data-ttu-id="44c58-115">Żądanie zostało przesłane i jest kierowane do zatwierdzenia przez przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="44c58-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="44c58-116">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="44c58-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="44c58-117">200000002</span><span class="sxs-lookup"><span data-stu-id="44c58-117">200000002</span></span> | <span data-ttu-id="44c58-118">Oczekująca</span><span class="sxs-lookup"><span data-stu-id="44c58-118">Pending</span></span> | <span data-ttu-id="44c58-119">Żądanie oczekuje na akcję przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="44c58-119">The request is pending workflow action.</span></span> <span data-ttu-id="44c58-120">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="44c58-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="44c58-121">200000003</span><span class="sxs-lookup"><span data-stu-id="44c58-121">200000003</span></span> | <span data-ttu-id="44c58-122">Anulowana</span><span class="sxs-lookup"><span data-stu-id="44c58-122">Canceled</span></span> | <span data-ttu-id="44c58-123">Żądanie zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="44c58-123">The request has been canceled.</span></span> <span data-ttu-id="44c58-124">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="44c58-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="44c58-125">200000004</span><span class="sxs-lookup"><span data-stu-id="44c58-125">200000004</span></span> | <span data-ttu-id="44c58-126">Odrzucone</span><span class="sxs-lookup"><span data-stu-id="44c58-126">Denied</span></span> | <span data-ttu-id="44c58-127">Żądanie zostało odrzucone.</span><span class="sxs-lookup"><span data-stu-id="44c58-127">The request has been denied.</span></span> <span data-ttu-id="44c58-128">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="44c58-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="44c58-129">200000005</span><span class="sxs-lookup"><span data-stu-id="44c58-129">200000005</span></span> | <span data-ttu-id="44c58-130">Aktywni</span><span class="sxs-lookup"><span data-stu-id="44c58-130">Active</span></span> | <span data-ttu-id="44c58-131">Każdy przepływ pracy jest ukończony i zatwierdzony, a żądanie jest gotowe do aktywnej rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="44c58-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="44c58-132">200000006</span><span class="sxs-lookup"><span data-stu-id="44c58-132">200000006</span></span> | <span data-ttu-id="44c58-133">Zamknięte</span><span class="sxs-lookup"><span data-stu-id="44c58-133">Closed</span></span> | <span data-ttu-id="44c58-134">Wniosek o rekrutację jest zakończony.</span><span class="sxs-lookup"><span data-stu-id="44c58-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="44c58-135">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="44c58-135">See also</span></span>

[<span data-ttu-id="44c58-136">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="44c58-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="44c58-137">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="44c58-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]