---
title: Wynik integracji kandydata
description: W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053906"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="db100-103">Wynik integracji kandydata</span><span class="sxs-lookup"><span data-stu-id="db100-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="db100-104">W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="db100-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="db100-105">Nazwa fizyczna: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="db100-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="db100-106">To wyliczenie zapewnia stan rekordu kandydata.</span><span class="sxs-lookup"><span data-stu-id="db100-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="db100-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="db100-107">Value</span></span> | <span data-ttu-id="db100-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="db100-108">Label</span></span> | <span data-ttu-id="db100-109">opis</span><span class="sxs-lookup"><span data-stu-id="db100-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="db100-110">200000000</span><span class="sxs-lookup"><span data-stu-id="db100-110">200000000</span></span> | <span data-ttu-id="db100-111">Nieprzetworzone</span><span class="sxs-lookup"><span data-stu-id="db100-111">Not processed</span></span> | <span data-ttu-id="db100-112">Kandydat jest nadal uwzględniany.</span><span class="sxs-lookup"><span data-stu-id="db100-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="db100-113">200000001</span><span class="sxs-lookup"><span data-stu-id="db100-113">200000001</span></span> | <span data-ttu-id="db100-114">Zatrudniono</span><span class="sxs-lookup"><span data-stu-id="db100-114">Hired</span></span> | <span data-ttu-id="db100-115">Kandydat został zatrudniony.</span><span class="sxs-lookup"><span data-stu-id="db100-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="db100-116">200000002</span><span class="sxs-lookup"><span data-stu-id="db100-116">200000002</span></span> | <span data-ttu-id="db100-117">Nie zatrudniono</span><span class="sxs-lookup"><span data-stu-id="db100-117">Not hired</span></span> | <span data-ttu-id="db100-118">Podjęto decyzję, aby nie zatrudniać kandydata.</span><span class="sxs-lookup"><span data-stu-id="db100-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="db100-119">200000003</span><span class="sxs-lookup"><span data-stu-id="db100-119">200000003</span></span> | <span data-ttu-id="db100-120">Odrzucono</span><span class="sxs-lookup"><span data-stu-id="db100-120">Dismissed</span></span> | <span data-ttu-id="db100-121">Kandydat już nie jest brany pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="db100-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="db100-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="db100-122">See also</span></span>

[<span data-ttu-id="db100-123">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="db100-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="db100-124">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="db100-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]