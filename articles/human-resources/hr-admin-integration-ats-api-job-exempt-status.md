---
title: Status zwolnienia z pracy
description: W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125576"
---
# <a name="job-exempt-status"></a><span data-ttu-id="13df7-103">Status zwolnienia z pracy</span><span class="sxs-lookup"><span data-stu-id="13df7-103">Job exempt status</span></span>

<span data-ttu-id="13df7-104">W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13df7-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="13df7-105">Nazwa fizyczna: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="13df7-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="13df7-106">To wyliczenie określa zestaw opcji dla wartości statusu zwolnienia z zadań FLSA.</span><span class="sxs-lookup"><span data-stu-id="13df7-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="13df7-107">Te informacje są dostępne w istniejącym zestawie opcji cdm_jobexemptstatus.</span><span class="sxs-lookup"><span data-stu-id="13df7-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="13df7-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="13df7-108">Value</span></span> | <span data-ttu-id="13df7-109">Etykiety</span><span class="sxs-lookup"><span data-stu-id="13df7-109">Label</span></span> | <span data-ttu-id="13df7-110">opis</span><span class="sxs-lookup"><span data-stu-id="13df7-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="13df7-111">200000000</span><span class="sxs-lookup"><span data-stu-id="13df7-111">200000000</span></span> | <span data-ttu-id="13df7-112">Zwolnienie</span><span class="sxs-lookup"><span data-stu-id="13df7-112">Exempt</span></span> | <span data-ttu-id="13df7-113">Stanowisko ma status zwolnienia na podstawie wytycznych FLSA.</span><span class="sxs-lookup"><span data-stu-id="13df7-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="13df7-114">200000001</span><span class="sxs-lookup"><span data-stu-id="13df7-114">200000001</span></span> | <span data-ttu-id="13df7-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="13df7-115">NonExempt</span></span> | <span data-ttu-id="13df7-116">Stanowisko nie ma statusu zwolnienia na podstawie wytycznych FLSA.</span><span class="sxs-lookup"><span data-stu-id="13df7-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="13df7-117">200000002</span><span class="sxs-lookup"><span data-stu-id="13df7-117">200000002</span></span> | <span data-ttu-id="13df7-118">Nie ma zastosowania</span><span class="sxs-lookup"><span data-stu-id="13df7-118">Does Not Apply</span></span> | <span data-ttu-id="13df7-119">Wytyczne dotyczące stanu FLSA nie mają zastosowania do tego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="13df7-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="13df7-120">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="13df7-120">See also</span></span>

[<span data-ttu-id="13df7-121">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="13df7-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="13df7-122">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="13df7-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)