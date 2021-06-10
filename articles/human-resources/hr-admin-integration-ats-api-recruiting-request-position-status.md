---
title: Stan stanowiska dla wniosku o rekrutację
description: W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051888"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="447dd-103">Stan stanowiska dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="447dd-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="447dd-104">W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="447dd-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="447dd-105">Nazwa fizyczna: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="447dd-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="447dd-106">W tym wyliczeniu jest ustawiana opcja wartości stanu poszczególnych stanowisk, do których jest zatrudniane w jednostce RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="447dd-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="447dd-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="447dd-107">Value</span></span> | <span data-ttu-id="447dd-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="447dd-108">Label</span></span> | <span data-ttu-id="447dd-109">opis</span><span class="sxs-lookup"><span data-stu-id="447dd-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="447dd-110">200000000</span><span class="sxs-lookup"><span data-stu-id="447dd-110">200000000</span></span> | <span data-ttu-id="447dd-111">Wolne</span><span class="sxs-lookup"><span data-stu-id="447dd-111">Open</span></span> | <span data-ttu-id="447dd-112">Stanowisko w wniosku o rekrutację jest otwarte do rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="447dd-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="447dd-113">Nie oznacza to, że obecnie nie ma aktywnego przypisania stanowiska do tego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="447dd-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="447dd-114">W czasie rekrutacji na to stanowisko może być zatrudniony pracownik.</span><span class="sxs-lookup"><span data-stu-id="447dd-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="447dd-115">Wskazuje tylko, że stanowisko jest dostępne do rekrutacji w kontekście wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="447dd-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="447dd-116">200000001</span><span class="sxs-lookup"><span data-stu-id="447dd-116">200000001</span></span> | <span data-ttu-id="447dd-117">Obsadzone</span><span class="sxs-lookup"><span data-stu-id="447dd-117">Filled</span></span> | <span data-ttu-id="447dd-118">Wybrano pracownika do przypisania do stanowiska.</span><span class="sxs-lookup"><span data-stu-id="447dd-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="447dd-119">200000002</span><span class="sxs-lookup"><span data-stu-id="447dd-119">200000002</span></span> | <span data-ttu-id="447dd-120">Anulowana</span><span class="sxs-lookup"><span data-stu-id="447dd-120">Canceled</span></span> | <span data-ttu-id="447dd-121">Wniosek o rekrutację na to stanowisko został anulowany.</span><span class="sxs-lookup"><span data-stu-id="447dd-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="447dd-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="447dd-122">See also</span></span>

[<span data-ttu-id="447dd-123">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="447dd-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="447dd-124">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="447dd-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]