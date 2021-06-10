---
title: Status zwolnienia z pracy
description: W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8e91fbb420009d5131e2faa7dbea8a302a027e0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053858"
---
# <a name="job-exempt-status"></a><span data-ttu-id="0896a-103">Status zwolnienia z pracy</span><span class="sxs-lookup"><span data-stu-id="0896a-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0896a-104">W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0896a-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0896a-105">Nazwa fizyczna: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="0896a-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="0896a-106">To wyliczenie określa zestaw opcji dla wartości statusu zwolnienia z zadań FLSA.</span><span class="sxs-lookup"><span data-stu-id="0896a-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="0896a-107">Te informacje są dostępne w istniejącym zestawie opcji cdm_jobexemptstatus.</span><span class="sxs-lookup"><span data-stu-id="0896a-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="0896a-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="0896a-108">Value</span></span> | <span data-ttu-id="0896a-109">Etykiety</span><span class="sxs-lookup"><span data-stu-id="0896a-109">Label</span></span> | <span data-ttu-id="0896a-110">opis</span><span class="sxs-lookup"><span data-stu-id="0896a-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0896a-111">200000000</span><span class="sxs-lookup"><span data-stu-id="0896a-111">200000000</span></span> | <span data-ttu-id="0896a-112">Zwolnienie</span><span class="sxs-lookup"><span data-stu-id="0896a-112">Exempt</span></span> | <span data-ttu-id="0896a-113">Stanowisko ma status zwolnienia na podstawie wytycznych FLSA.</span><span class="sxs-lookup"><span data-stu-id="0896a-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="0896a-114">200000001</span><span class="sxs-lookup"><span data-stu-id="0896a-114">200000001</span></span> | <span data-ttu-id="0896a-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="0896a-115">NonExempt</span></span> | <span data-ttu-id="0896a-116">Stanowisko nie ma statusu zwolnienia na podstawie wytycznych FLSA.</span><span class="sxs-lookup"><span data-stu-id="0896a-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="0896a-117">200000002</span><span class="sxs-lookup"><span data-stu-id="0896a-117">200000002</span></span> | <span data-ttu-id="0896a-118">Nie ma zastosowania</span><span class="sxs-lookup"><span data-stu-id="0896a-118">Does Not Apply</span></span> | <span data-ttu-id="0896a-119">Wytyczne dotyczące stanu FLSA nie mają zastosowania do tego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="0896a-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0896a-120">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="0896a-120">See also</span></span>

[<span data-ttu-id="0896a-121">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="0896a-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="0896a-122">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="0896a-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]