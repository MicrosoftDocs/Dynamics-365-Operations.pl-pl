---
title: Stan wniosku o rekrutację
description: W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3b05cc531a84144708ff52913927bbd04574a3b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059191"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="a2caa-103">Stan wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="a2caa-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a2caa-104">W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a2caa-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a2caa-105">Nazwa fizyczna: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="a2caa-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="a2caa-106">To wyliczenie zapewnia zestaw opcji dla wartości statusu RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="a2caa-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="a2caa-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="a2caa-107">Value</span></span> | <span data-ttu-id="a2caa-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="a2caa-108">Label</span></span> | <span data-ttu-id="a2caa-109">opis</span><span class="sxs-lookup"><span data-stu-id="a2caa-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a2caa-110">200000000</span><span class="sxs-lookup"><span data-stu-id="a2caa-110">200000000</span></span> | <span data-ttu-id="a2caa-111">Robocza</span><span class="sxs-lookup"><span data-stu-id="a2caa-111">Draft</span></span> | <span data-ttu-id="a2caa-112">Wniosek jest w wersji roboczej i nie jest gotowy do aktywnej rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="a2caa-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="a2caa-113">200000001</span><span class="sxs-lookup"><span data-stu-id="a2caa-113">200000001</span></span> | <span data-ttu-id="a2caa-114">W trakcie przeglądu</span><span class="sxs-lookup"><span data-stu-id="a2caa-114">In Review</span></span> | <span data-ttu-id="a2caa-115">Żądanie zostało przesłane i jest kierowane do zatwierdzenia przez przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="a2caa-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="a2caa-116">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a2caa-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a2caa-117">200000002</span><span class="sxs-lookup"><span data-stu-id="a2caa-117">200000002</span></span> | <span data-ttu-id="a2caa-118">Oczekująca</span><span class="sxs-lookup"><span data-stu-id="a2caa-118">Pending</span></span> | <span data-ttu-id="a2caa-119">Żądanie oczekuje na akcję przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a2caa-119">The request is pending workflow action.</span></span> <span data-ttu-id="a2caa-120">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a2caa-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a2caa-121">200000003</span><span class="sxs-lookup"><span data-stu-id="a2caa-121">200000003</span></span> | <span data-ttu-id="a2caa-122">Anulowana</span><span class="sxs-lookup"><span data-stu-id="a2caa-122">Canceled</span></span> | <span data-ttu-id="a2caa-123">Żądanie zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="a2caa-123">The request has been canceled.</span></span> <span data-ttu-id="a2caa-124">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a2caa-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a2caa-125">200000004</span><span class="sxs-lookup"><span data-stu-id="a2caa-125">200000004</span></span> | <span data-ttu-id="a2caa-126">Odrzucone</span><span class="sxs-lookup"><span data-stu-id="a2caa-126">Denied</span></span> | <span data-ttu-id="a2caa-127">Żądanie zostało odrzucone.</span><span class="sxs-lookup"><span data-stu-id="a2caa-127">The request has been denied.</span></span> <span data-ttu-id="a2caa-128">Dostępne tylko po włączeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a2caa-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a2caa-129">200000005</span><span class="sxs-lookup"><span data-stu-id="a2caa-129">200000005</span></span> | <span data-ttu-id="a2caa-130">Aktywni</span><span class="sxs-lookup"><span data-stu-id="a2caa-130">Active</span></span> | <span data-ttu-id="a2caa-131">Każdy przepływ pracy jest ukończony i zatwierdzony, a żądanie jest gotowe do aktywnej rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="a2caa-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="a2caa-132">200000006</span><span class="sxs-lookup"><span data-stu-id="a2caa-132">200000006</span></span> | <span data-ttu-id="a2caa-133">Zamknięte</span><span class="sxs-lookup"><span data-stu-id="a2caa-133">Closed</span></span> | <span data-ttu-id="a2caa-134">Wniosek o rekrutację jest zakończony.</span><span class="sxs-lookup"><span data-stu-id="a2caa-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a2caa-135">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a2caa-135">See also</span></span>

[<span data-ttu-id="a2caa-136">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="a2caa-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a2caa-137">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="a2caa-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]