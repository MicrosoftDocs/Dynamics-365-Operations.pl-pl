---
title: Stan stanowiska dla wniosku o rekrutację
description: W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126057"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="e96a3-103">Stan stanowiska dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="e96a3-103">Recruiting request position status</span></span>

<span data-ttu-id="e96a3-104">W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e96a3-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e96a3-105">Nazwa fizyczna: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="e96a3-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="e96a3-106">W tym wyliczeniu jest ustawiana opcja wartości stanu poszczególnych stanowisk, do których jest zatrudniane w jednostce RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="e96a3-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="e96a3-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="e96a3-107">Value</span></span> | <span data-ttu-id="e96a3-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="e96a3-108">Label</span></span> | <span data-ttu-id="e96a3-109">opis</span><span class="sxs-lookup"><span data-stu-id="e96a3-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e96a3-110">200000000</span><span class="sxs-lookup"><span data-stu-id="e96a3-110">200000000</span></span> | <span data-ttu-id="e96a3-111">Wolne</span><span class="sxs-lookup"><span data-stu-id="e96a3-111">Open</span></span> | <span data-ttu-id="e96a3-112">Stanowisko w wniosku o rekrutację jest otwarte do rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="e96a3-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="e96a3-113">Nie oznacza to, że obecnie nie ma aktywnego przypisania stanowiska do tego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="e96a3-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="e96a3-114">W czasie rekrutacji na to stanowisko może być zatrudniony pracownik.</span><span class="sxs-lookup"><span data-stu-id="e96a3-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="e96a3-115">Wskazuje tylko, że stanowisko jest dostępne do rekrutacji w kontekście wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="e96a3-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="e96a3-116">200000001</span><span class="sxs-lookup"><span data-stu-id="e96a3-116">200000001</span></span> | <span data-ttu-id="e96a3-117">Obsadzone</span><span class="sxs-lookup"><span data-stu-id="e96a3-117">Filled</span></span> | <span data-ttu-id="e96a3-118">Wybrano pracownika do przypisania do stanowiska.</span><span class="sxs-lookup"><span data-stu-id="e96a3-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="e96a3-119">200000002</span><span class="sxs-lookup"><span data-stu-id="e96a3-119">200000002</span></span> | <span data-ttu-id="e96a3-120">Anulowana</span><span class="sxs-lookup"><span data-stu-id="e96a3-120">Canceled</span></span> | <span data-ttu-id="e96a3-121">Wniosek o rekrutację na to stanowisko został anulowany.</span><span class="sxs-lookup"><span data-stu-id="e96a3-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e96a3-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e96a3-122">See also</span></span>

[<span data-ttu-id="e96a3-123">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="e96a3-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e96a3-124">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="e96a3-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
