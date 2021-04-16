---
title: Wynik integracji kandydata
description: W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: e8e41fe485cc70a668d4610ce6eabba5cd16ac86
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795124"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="72db4-103">Wynik integracji kandydata</span><span class="sxs-lookup"><span data-stu-id="72db4-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="72db4-104">W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72db4-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="72db4-105">Nazwa fizyczna: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="72db4-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="72db4-106">To wyliczenie zapewnia stan rekordu kandydata.</span><span class="sxs-lookup"><span data-stu-id="72db4-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="72db4-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="72db4-107">Value</span></span> | <span data-ttu-id="72db4-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="72db4-108">Label</span></span> | <span data-ttu-id="72db4-109">opis</span><span class="sxs-lookup"><span data-stu-id="72db4-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="72db4-110">200000000</span><span class="sxs-lookup"><span data-stu-id="72db4-110">200000000</span></span> | <span data-ttu-id="72db4-111">Nieprzetworzone</span><span class="sxs-lookup"><span data-stu-id="72db4-111">Not processed</span></span> | <span data-ttu-id="72db4-112">Kandydat jest nadal uwzględniany.</span><span class="sxs-lookup"><span data-stu-id="72db4-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="72db4-113">200000001</span><span class="sxs-lookup"><span data-stu-id="72db4-113">200000001</span></span> | <span data-ttu-id="72db4-114">Zatrudniono</span><span class="sxs-lookup"><span data-stu-id="72db4-114">Hired</span></span> | <span data-ttu-id="72db4-115">Kandydat został zatrudniony.</span><span class="sxs-lookup"><span data-stu-id="72db4-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="72db4-116">200000002</span><span class="sxs-lookup"><span data-stu-id="72db4-116">200000002</span></span> | <span data-ttu-id="72db4-117">Nie zatrudniono</span><span class="sxs-lookup"><span data-stu-id="72db4-117">Not hired</span></span> | <span data-ttu-id="72db4-118">Podjęto decyzję, aby nie zatrudniać kandydata.</span><span class="sxs-lookup"><span data-stu-id="72db4-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="72db4-119">200000003</span><span class="sxs-lookup"><span data-stu-id="72db4-119">200000003</span></span> | <span data-ttu-id="72db4-120">Odrzucono</span><span class="sxs-lookup"><span data-stu-id="72db4-120">Dismissed</span></span> | <span data-ttu-id="72db4-121">Kandydat już nie jest brany pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="72db4-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="72db4-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="72db4-122">See also</span></span>

[<span data-ttu-id="72db4-123">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="72db4-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="72db4-124">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="72db4-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]