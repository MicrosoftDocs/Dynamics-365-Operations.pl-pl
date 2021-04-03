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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468210"
---
# <a name="completion-status"></a><span data-ttu-id="9b845-103">Stan ukończenia</span><span class="sxs-lookup"><span data-stu-id="9b845-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9b845-104">W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9b845-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="9b845-105">Nazwa fizyczna: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="9b845-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="9b845-106">To wyliczenie zawiera zestaw opcji wartości stanu dla kontroli kandydatów.</span><span class="sxs-lookup"><span data-stu-id="9b845-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="9b845-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="9b845-107">Value</span></span> | <span data-ttu-id="9b845-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="9b845-108">Label</span></span> | <span data-ttu-id="9b845-109">opis</span><span class="sxs-lookup"><span data-stu-id="9b845-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9b845-110">200000000</span><span class="sxs-lookup"><span data-stu-id="9b845-110">200000000</span></span> | <span data-ttu-id="9b845-111">Nieukończone</span><span class="sxs-lookup"><span data-stu-id="9b845-111">Not Complete</span></span> | <span data-ttu-id="9b845-112">Kandydat nie zakończył jeszcze kontroli.</span><span class="sxs-lookup"><span data-stu-id="9b845-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="9b845-113">200000001</span><span class="sxs-lookup"><span data-stu-id="9b845-113">200000001</span></span> | <span data-ttu-id="9b845-114">Sukces</span><span class="sxs-lookup"><span data-stu-id="9b845-114">Pass</span></span> | <span data-ttu-id="9b845-115">Kandydat przeszedł kontrolę.</span><span class="sxs-lookup"><span data-stu-id="9b845-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="9b845-116">200000002</span><span class="sxs-lookup"><span data-stu-id="9b845-116">200000002</span></span> | <span data-ttu-id="9b845-117">Niepowodzenie</span><span class="sxs-lookup"><span data-stu-id="9b845-117">Fail</span></span> | <span data-ttu-id="9b845-118">Kandydat nie przeszedł kontroli.</span><span class="sxs-lookup"><span data-stu-id="9b845-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9b845-119">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="9b845-119">See also</span></span>

[<span data-ttu-id="9b845-120">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="9b845-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="9b845-121">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="9b845-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]