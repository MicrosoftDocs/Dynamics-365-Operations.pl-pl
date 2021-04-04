---
title: Omówienie programowania
description: Ten przewodnik dewelopera zawiera informacje o interfejsie API i polach niestandardowych. Zawiera również informacje dotyczące integrowania z innymi aplikacjami.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8e390592b000c8f6006aa489fd3823c4f15cb2cb
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467802"
---
# <a name="development-overview"></a><span data-ttu-id="9a3c3-104">Omówienie programowania</span><span class="sxs-lookup"><span data-stu-id="9a3c3-104">Development overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="9a3c3-105">Ten przewodnik dewelopera zawiera informacje o interfejsie API i polach niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="9a3c3-105">This Developer Guide provides an API and custom fields reference.</span></span> <span data-ttu-id="9a3c3-106">Zawiera również informacje dotyczące integrowania z innymi aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="9a3c3-106">It also provides information on integrating with other apps.</span></span>

- [<span data-ttu-id="9a3c3-107">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9a3c3-107">Overview</span></span>](hr-developer-overview.md)

- [<span data-ttu-id="9a3c3-108">Rozszerz aplikację Power Apps i Power Automate</span><span class="sxs-lookup"><span data-stu-id="9a3c3-108">Extend with Power Apps and Power Automate</span></span>](hr-developer-power-apps.md)

- [<span data-ttu-id="9a3c3-109">Jednostki Human Resources w Dataverse</span><span class="sxs-lookup"><span data-stu-id="9a3c3-109">Human Resources entities in Dataverse</span></span>](hr-developer-entities.md)

- [<span data-ttu-id="9a3c3-110">Pola niestandardowe</span><span class="sxs-lookup"><span data-stu-id="9a3c3-110">Custom fields</span></span>](hr-developer-custom-fields.md)

- <span data-ttu-id="9a3c3-111">Ustawianie integracji danych</span><span class="sxs-lookup"><span data-stu-id="9a3c3-111">Set up data integration</span></span>
  - [<span data-ttu-id="9a3c3-112">Wybieranie technologii integracji danych</span><span class="sxs-lookup"><span data-stu-id="9a3c3-112">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)
  - [<span data-ttu-id="9a3c3-113">Konfiguruj integrację z programem Dataverse</span><span class="sxs-lookup"><span data-stu-id="9a3c3-113">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)
  - [<span data-ttu-id="9a3c3-114">Konfigurowanie integracji z rozwiązaniem Finance</span><span class="sxs-lookup"><span data-stu-id="9a3c3-114">Configure integration with Finance</span></span>](hr-admin-integration-finance.md)
  - [<span data-ttu-id="9a3c3-115">Konfigurowanie integracji z rozwiązaniem Dayforce</span><span class="sxs-lookup"><span data-stu-id="9a3c3-115">Configure integration with Dayforce</span></span>](hr-admin-integration-dayforce.md)
  - [<span data-ttu-id="9a3c3-116">Tworzenie aplikacji do cyklicznego eksportowania danych</span><span class="sxs-lookup"><span data-stu-id="9a3c3-116">Create a recurring data export app</span></span>](hr-admin-integration-recurring-data-export.md)
  - <span data-ttu-id="9a3c3-117">Integracja z pakietem Office</span><span class="sxs-lookup"><span data-stu-id="9a3c3-117">Integrate with Office</span></span>
    - [<span data-ttu-id="9a3c3-118">Integracja z pakietem Office — samouczek</span><span class="sxs-lookup"><span data-stu-id="9a3c3-118">Office integration tutorial</span></span>](../dev-itpro/office-integration/office-integration-tutorial.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="9a3c3-119">Aktualizowanie danych jednostki w programie Excel</span><span class="sxs-lookup"><span data-stu-id="9a3c3-119">Update entity data in Excel</span></span>](../dev-itpro/office-integration/use-excel-add-in.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="9a3c3-120">Tworzenie funkcji otwierania w programie Excel</span><span class="sxs-lookup"><span data-stu-id="9a3c3-120">Create Open in Excel experiences</span></span>](../dev-itpro/office-integration/office-integration-edit-excel.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="9a3c3-121">Rozwiązywanie problemów z integracją z pakietem Office</span><span class="sxs-lookup"><span data-stu-id="9a3c3-121">Troubleshoot Office integration</span></span>](../dev-itpro/office-integration/office-integration-troubleshooting.md?toc=/dynamics365/unified-operations/talent/toc.json)

- <span data-ttu-id="9a3c3-122">Dokumentacja interfejsu API jednostki</span><span class="sxs-lookup"><span data-stu-id="9a3c3-122">Entity API reference</span></span>
  - [<span data-ttu-id="9a3c3-123">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="9a3c3-123">Authentication</span></span>](hr-developer-api-authentication.md)
  - <span data-ttu-id="9a3c3-124">Jednostki</span><span class="sxs-lookup"><span data-stu-id="9a3c3-124">Entities</span></span>
    - [<span data-ttu-id="9a3c3-125">MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="9a3c3-125">MyLeaveRequests</span></span>](hr-developer-api-myleaverequests-overview.md)
    - [<span data-ttu-id="9a3c3-126">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9a3c3-126">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)

## <a name="see-also"></a><span data-ttu-id="9a3c3-127">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="9a3c3-127">See also</span></span>

- [<span data-ttu-id="9a3c3-128">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="9a3c3-128">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="9a3c3-129">Przewodnik administratora</span><span class="sxs-lookup"><span data-stu-id="9a3c3-129">Administrator Guide</span></span>](hr-admin-overview.md)
- [<span data-ttu-id="9a3c3-130">Przewodnik użytkownika</span><span class="sxs-lookup"><span data-stu-id="9a3c3-130">User Guide</span></span>](hr-hrpro-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]