---
title: Wynik integracji kandydata
description: W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467560"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="88751-103">Wynik integracji kandydata</span><span class="sxs-lookup"><span data-stu-id="88751-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="88751-104">W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="88751-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="88751-105">Nazwa fizyczna: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="88751-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="88751-106">To wyliczenie zapewnia stan rekordu kandydata.</span><span class="sxs-lookup"><span data-stu-id="88751-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="88751-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="88751-107">Value</span></span> | <span data-ttu-id="88751-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="88751-108">Label</span></span> | <span data-ttu-id="88751-109">opis</span><span class="sxs-lookup"><span data-stu-id="88751-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="88751-110">200000000</span><span class="sxs-lookup"><span data-stu-id="88751-110">200000000</span></span> | <span data-ttu-id="88751-111">Nieprzetworzone</span><span class="sxs-lookup"><span data-stu-id="88751-111">Not processed</span></span> | <span data-ttu-id="88751-112">Kandydat jest nadal uwzględniany.</span><span class="sxs-lookup"><span data-stu-id="88751-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="88751-113">200000001</span><span class="sxs-lookup"><span data-stu-id="88751-113">200000001</span></span> | <span data-ttu-id="88751-114">Zatrudniono</span><span class="sxs-lookup"><span data-stu-id="88751-114">Hired</span></span> | <span data-ttu-id="88751-115">Kandydat został zatrudniony.</span><span class="sxs-lookup"><span data-stu-id="88751-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="88751-116">200000002</span><span class="sxs-lookup"><span data-stu-id="88751-116">200000002</span></span> | <span data-ttu-id="88751-117">Nie zatrudniono</span><span class="sxs-lookup"><span data-stu-id="88751-117">Not hired</span></span> | <span data-ttu-id="88751-118">Podjęto decyzję, aby nie zatrudniać kandydata.</span><span class="sxs-lookup"><span data-stu-id="88751-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="88751-119">200000003</span><span class="sxs-lookup"><span data-stu-id="88751-119">200000003</span></span> | <span data-ttu-id="88751-120">Odrzucono</span><span class="sxs-lookup"><span data-stu-id="88751-120">Dismissed</span></span> | <span data-ttu-id="88751-121">Kandydat już nie jest brany pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="88751-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="88751-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="88751-122">See also</span></span>

[<span data-ttu-id="88751-123">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="88751-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="88751-124">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="88751-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]