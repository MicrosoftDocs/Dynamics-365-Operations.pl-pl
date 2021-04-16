---
title: Stan stanowiska dla wniosku o rekrutację
description: W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7e59e9381fb15b339095d6a71296813e0141e9ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789739"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="a95e2-103">Stan stanowiska dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="a95e2-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a95e2-104">W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a95e2-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a95e2-105">Nazwa fizyczna: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="a95e2-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="a95e2-106">W tym wyliczeniu jest ustawiana opcja wartości stanu poszczególnych stanowisk, do których jest zatrudniane w jednostce RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="a95e2-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="a95e2-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="a95e2-107">Value</span></span> | <span data-ttu-id="a95e2-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="a95e2-108">Label</span></span> | <span data-ttu-id="a95e2-109">opis</span><span class="sxs-lookup"><span data-stu-id="a95e2-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a95e2-110">200000000</span><span class="sxs-lookup"><span data-stu-id="a95e2-110">200000000</span></span> | <span data-ttu-id="a95e2-111">Wolne</span><span class="sxs-lookup"><span data-stu-id="a95e2-111">Open</span></span> | <span data-ttu-id="a95e2-112">Stanowisko w wniosku o rekrutację jest otwarte do rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="a95e2-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="a95e2-113">Nie oznacza to, że obecnie nie ma aktywnego przypisania stanowiska do tego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="a95e2-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="a95e2-114">W czasie rekrutacji na to stanowisko może być zatrudniony pracownik.</span><span class="sxs-lookup"><span data-stu-id="a95e2-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="a95e2-115">Wskazuje tylko, że stanowisko jest dostępne do rekrutacji w kontekście wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="a95e2-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="a95e2-116">200000001</span><span class="sxs-lookup"><span data-stu-id="a95e2-116">200000001</span></span> | <span data-ttu-id="a95e2-117">Obsadzone</span><span class="sxs-lookup"><span data-stu-id="a95e2-117">Filled</span></span> | <span data-ttu-id="a95e2-118">Wybrano pracownika do przypisania do stanowiska.</span><span class="sxs-lookup"><span data-stu-id="a95e2-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="a95e2-119">200000002</span><span class="sxs-lookup"><span data-stu-id="a95e2-119">200000002</span></span> | <span data-ttu-id="a95e2-120">Anulowana</span><span class="sxs-lookup"><span data-stu-id="a95e2-120">Canceled</span></span> | <span data-ttu-id="a95e2-121">Wniosek o rekrutację na to stanowisko został anulowany.</span><span class="sxs-lookup"><span data-stu-id="a95e2-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a95e2-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a95e2-122">See also</span></span>

[<span data-ttu-id="a95e2-123">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="a95e2-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a95e2-124">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="a95e2-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]