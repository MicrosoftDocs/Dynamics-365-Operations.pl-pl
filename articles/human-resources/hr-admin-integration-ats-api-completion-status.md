---
title: Stan ukończenia
description: W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 54ad5cc8f5f18d57b6713304cceb985acfdc93d1
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055371"
---
# <a name="completion-status"></a><span data-ttu-id="4fd0b-103">Stan ukończenia</span><span class="sxs-lookup"><span data-stu-id="4fd0b-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4fd0b-104">W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="4fd0b-105">Nazwa fizyczna: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="4fd0b-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="4fd0b-106">To wyliczenie zawiera zestaw opcji wartości stanu dla kontroli kandydatów.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="4fd0b-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="4fd0b-107">Value</span></span> | <span data-ttu-id="4fd0b-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="4fd0b-108">Label</span></span> | <span data-ttu-id="4fd0b-109">opis</span><span class="sxs-lookup"><span data-stu-id="4fd0b-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4fd0b-110">200000000</span><span class="sxs-lookup"><span data-stu-id="4fd0b-110">200000000</span></span> | <span data-ttu-id="4fd0b-111">Nieukończone</span><span class="sxs-lookup"><span data-stu-id="4fd0b-111">Not Complete</span></span> | <span data-ttu-id="4fd0b-112">Kandydat nie zakończył jeszcze kontroli.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="4fd0b-113">200000001</span><span class="sxs-lookup"><span data-stu-id="4fd0b-113">200000001</span></span> | <span data-ttu-id="4fd0b-114">Sukces</span><span class="sxs-lookup"><span data-stu-id="4fd0b-114">Pass</span></span> | <span data-ttu-id="4fd0b-115">Kandydat przeszedł kontrolę.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="4fd0b-116">200000002</span><span class="sxs-lookup"><span data-stu-id="4fd0b-116">200000002</span></span> | <span data-ttu-id="4fd0b-117">Niepowodzenie</span><span class="sxs-lookup"><span data-stu-id="4fd0b-117">Fail</span></span> | <span data-ttu-id="4fd0b-118">Kandydat nie przeszedł kontroli.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4fd0b-119">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4fd0b-119">See also</span></span>

[<span data-ttu-id="4fd0b-120">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="4fd0b-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="4fd0b-121">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="4fd0b-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]