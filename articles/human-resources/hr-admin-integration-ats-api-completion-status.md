---
title: Stan ukończenia
description: W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: e9024e00b5d25117fd255084609c4f8db9284f32
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125696"
---
# <a name="completion-status"></a><span data-ttu-id="24dcc-103">Stan ukończenia</span><span class="sxs-lookup"><span data-stu-id="24dcc-103">Completion status</span></span>

<span data-ttu-id="24dcc-104">W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="24dcc-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="24dcc-105">Nazwa fizyczna: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="24dcc-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="24dcc-106">To wyliczenie zawiera zestaw opcji wartości stanu dla kontroli kandydatów.</span><span class="sxs-lookup"><span data-stu-id="24dcc-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="24dcc-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="24dcc-107">Value</span></span> | <span data-ttu-id="24dcc-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="24dcc-108">Label</span></span> | <span data-ttu-id="24dcc-109">opis</span><span class="sxs-lookup"><span data-stu-id="24dcc-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="24dcc-110">200000000</span><span class="sxs-lookup"><span data-stu-id="24dcc-110">200000000</span></span> | <span data-ttu-id="24dcc-111">Nieukończone</span><span class="sxs-lookup"><span data-stu-id="24dcc-111">Not Complete</span></span> | <span data-ttu-id="24dcc-112">Kandydat nie zakończył jeszcze kontroli.</span><span class="sxs-lookup"><span data-stu-id="24dcc-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="24dcc-113">200000001</span><span class="sxs-lookup"><span data-stu-id="24dcc-113">200000001</span></span> | <span data-ttu-id="24dcc-114">Sukces</span><span class="sxs-lookup"><span data-stu-id="24dcc-114">Pass</span></span> | <span data-ttu-id="24dcc-115">Kandydat przeszedł kontrolę.</span><span class="sxs-lookup"><span data-stu-id="24dcc-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="24dcc-116">200000002</span><span class="sxs-lookup"><span data-stu-id="24dcc-116">200000002</span></span> | <span data-ttu-id="24dcc-117">Niepowodzenie</span><span class="sxs-lookup"><span data-stu-id="24dcc-117">Fail</span></span> | <span data-ttu-id="24dcc-118">Kandydat nie przeszedł kontroli.</span><span class="sxs-lookup"><span data-stu-id="24dcc-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="24dcc-119">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="24dcc-119">See also</span></span>

[<span data-ttu-id="24dcc-120">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="24dcc-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="24dcc-121">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="24dcc-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
