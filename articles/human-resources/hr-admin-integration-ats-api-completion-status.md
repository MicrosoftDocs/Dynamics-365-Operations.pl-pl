---
title: Stan ukończenia
description: W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798376"
---
# <a name="completion-status"></a><span data-ttu-id="250f3-103">Stan ukończenia</span><span class="sxs-lookup"><span data-stu-id="250f3-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="250f3-104">W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="250f3-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="250f3-105">Nazwa fizyczna: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="250f3-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="250f3-106">To wyliczenie zawiera zestaw opcji wartości stanu dla kontroli kandydatów.</span><span class="sxs-lookup"><span data-stu-id="250f3-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="250f3-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="250f3-107">Value</span></span> | <span data-ttu-id="250f3-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="250f3-108">Label</span></span> | <span data-ttu-id="250f3-109">opis</span><span class="sxs-lookup"><span data-stu-id="250f3-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="250f3-110">200000000</span><span class="sxs-lookup"><span data-stu-id="250f3-110">200000000</span></span> | <span data-ttu-id="250f3-111">Nieukończone</span><span class="sxs-lookup"><span data-stu-id="250f3-111">Not Complete</span></span> | <span data-ttu-id="250f3-112">Kandydat nie zakończył jeszcze kontroli.</span><span class="sxs-lookup"><span data-stu-id="250f3-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="250f3-113">200000001</span><span class="sxs-lookup"><span data-stu-id="250f3-113">200000001</span></span> | <span data-ttu-id="250f3-114">Sukces</span><span class="sxs-lookup"><span data-stu-id="250f3-114">Pass</span></span> | <span data-ttu-id="250f3-115">Kandydat przeszedł kontrolę.</span><span class="sxs-lookup"><span data-stu-id="250f3-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="250f3-116">200000002</span><span class="sxs-lookup"><span data-stu-id="250f3-116">200000002</span></span> | <span data-ttu-id="250f3-117">Niepowodzenie</span><span class="sxs-lookup"><span data-stu-id="250f3-117">Fail</span></span> | <span data-ttu-id="250f3-118">Kandydat nie przeszedł kontroli.</span><span class="sxs-lookup"><span data-stu-id="250f3-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="250f3-119">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="250f3-119">See also</span></span>

[<span data-ttu-id="250f3-120">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="250f3-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="250f3-121">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="250f3-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]