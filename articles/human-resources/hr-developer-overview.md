---
title: Omówienie programowania
description: Ten przewodnik dewelopera zawiera informacje o interfejsie API i polach niestandardowych. Zawiera również informacje dotyczące integrowania z innymi aplikacjami.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5e67749e6f10b1c9202605b26164e30e5d39aa28
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793592"
---
# <a name="development-overview"></a><span data-ttu-id="d3ae6-104">Omówienie programowania</span><span class="sxs-lookup"><span data-stu-id="d3ae6-104">Development overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d3ae6-105">Ten przewodnik dewelopera zawiera informacje o interfejsie API i polach niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-105">This Developer Guide provides an API and custom fields reference.</span></span> <span data-ttu-id="d3ae6-106">Zawiera również informacje dotyczące integrowania z innymi aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-106">It also provides information on integrating with other apps.</span></span>

- [<span data-ttu-id="d3ae6-107">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d3ae6-107">Overview</span></span>](hr-developer-overview.md)

- [<span data-ttu-id="d3ae6-108">Rozszerz aplikację Power Apps i Power Automate</span><span class="sxs-lookup"><span data-stu-id="d3ae6-108">Extend with Power Apps and Power Automate</span></span>](hr-developer-power-apps.md)

- [<span data-ttu-id="d3ae6-109">Jednostki Human Resources w Dataverse</span><span class="sxs-lookup"><span data-stu-id="d3ae6-109">Human Resources entities in Dataverse</span></span>](hr-developer-entities.md)

- [<span data-ttu-id="d3ae6-110">Pola niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d3ae6-110">Custom fields</span></span>](hr-developer-custom-fields.md)

- <span data-ttu-id="d3ae6-111">Ustawianie integracji danych</span><span class="sxs-lookup"><span data-stu-id="d3ae6-111">Set up data integration</span></span>
  - [<span data-ttu-id="d3ae6-112">Wybieranie technologii integracji danych</span><span class="sxs-lookup"><span data-stu-id="d3ae6-112">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)
  - [<span data-ttu-id="d3ae6-113">Konfiguruj integrację z programem Dataverse</span><span class="sxs-lookup"><span data-stu-id="d3ae6-113">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)
  - [<span data-ttu-id="d3ae6-114">Konfigurowanie integracji z rozwiązaniem Finance</span><span class="sxs-lookup"><span data-stu-id="d3ae6-114">Configure integration with Finance</span></span>](hr-admin-integration-finance.md)
  - [<span data-ttu-id="d3ae6-115">Konfigurowanie integracji z rozwiązaniem Dayforce</span><span class="sxs-lookup"><span data-stu-id="d3ae6-115">Configure integration with Dayforce</span></span>](hr-admin-integration-dayforce.md)
  - [<span data-ttu-id="d3ae6-116">Tworzenie aplikacji do cyklicznego eksportowania danych</span><span class="sxs-lookup"><span data-stu-id="d3ae6-116">Create a recurring data export app</span></span>](hr-admin-integration-recurring-data-export.md)
  - <span data-ttu-id="d3ae6-117">Integracja z pakietem Office</span><span class="sxs-lookup"><span data-stu-id="d3ae6-117">Integrate with Office</span></span>
    - [<span data-ttu-id="d3ae6-118">Integracja z pakietem Office — samouczek</span><span class="sxs-lookup"><span data-stu-id="d3ae6-118">Office integration tutorial</span></span>](../dev-itpro/office-integration/office-integration-tutorial.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="d3ae6-119">Aktualizowanie danych jednostki w programie Excel</span><span class="sxs-lookup"><span data-stu-id="d3ae6-119">Update entity data in Excel</span></span>](../dev-itpro/office-integration/use-excel-add-in.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="d3ae6-120">Tworzenie funkcji otwierania w programie Excel</span><span class="sxs-lookup"><span data-stu-id="d3ae6-120">Create Open in Excel experiences</span></span>](../dev-itpro/office-integration/office-integration-edit-excel.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="d3ae6-121">Rozwiązywanie problemów z integracją z pakietem Office</span><span class="sxs-lookup"><span data-stu-id="d3ae6-121">Troubleshoot Office integration</span></span>](../dev-itpro/office-integration/office-integration-troubleshooting.md?toc=/dynamics365/unified-operations/talent/toc.json)

- <span data-ttu-id="d3ae6-122">Dokumentacja interfejsu API jednostki</span><span class="sxs-lookup"><span data-stu-id="d3ae6-122">Entity API reference</span></span>
  - [<span data-ttu-id="d3ae6-123">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="d3ae6-123">Authentication</span></span>](hr-developer-api-authentication.md)
  - <span data-ttu-id="d3ae6-124">Jednostki</span><span class="sxs-lookup"><span data-stu-id="d3ae6-124">Entities</span></span>
    - [<span data-ttu-id="d3ae6-125">MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="d3ae6-125">MyLeaveRequests</span></span>](hr-developer-api-myleaverequests-overview.md)
    - [<span data-ttu-id="d3ae6-126">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="d3ae6-126">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)

## <a name="see-also"></a><span data-ttu-id="d3ae6-127">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="d3ae6-127">See also</span></span>

- [<span data-ttu-id="d3ae6-128">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="d3ae6-128">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="d3ae6-129">Przewodnik administratora</span><span class="sxs-lookup"><span data-stu-id="d3ae6-129">Administrator Guide</span></span>](hr-admin-overview.md)
- [<span data-ttu-id="d3ae6-130">Przewodnik użytkownika</span><span class="sxs-lookup"><span data-stu-id="d3ae6-130">User Guide</span></span>](hr-hrpro-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]