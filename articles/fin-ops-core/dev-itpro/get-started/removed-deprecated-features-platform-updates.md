---
title: Usunięte lub wycofane funkcje Platform
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087890"
---
# <a name="removed-or-deprecated-platform-features"></a><span data-ttu-id="242b0-103">Usunięte lub wycofane funkcje Platform</span><span class="sxs-lookup"><span data-stu-id="242b0-103">Removed or deprecated platform features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="242b0-104">W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="242b0-104">This topic describes features that have been removed, or that are planned for removal in platform updates of Finance and Operations apps.</span></span>

- <span data-ttu-id="242b0-105">*Usunięta* funkcja nie jest już dostępna w produkcie.</span><span class="sxs-lookup"><span data-stu-id="242b0-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="242b0-106">*Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="242b0-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="242b0-107">Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu.</span><span class="sxs-lookup"><span data-stu-id="242b0-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="242b0-108">Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="242b0-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="242b0-109">Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="242b0-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="242b0-110">Aktualizacja platformy Update 32</span><span class="sxs-lookup"><span data-stu-id="242b0-110">Platform update 32</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="242b0-111">Okno dialogowe zmiana żądania przepływu pracy nie zawiera już listy rozwijanej wyboru użytkownika</span><span class="sxs-lookup"><span data-stu-id="242b0-111">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="242b0-112">**Przyczyna wycofania/usunięcia**</span><span class="sxs-lookup"><span data-stu-id="242b0-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="242b0-113">Była to kwestia błędu zabezpieczeń, ponieważ żądanie zmiany może zostać wysłane do niezamierzonego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="242b0-113">This was a security issue because the request for change could be sent to an unintended user.</span></span> <span data-ttu-id="242b0-114">Był to również błąd użyteczności, ponieważ zmuszał użytkownika do określenia, kto był wytwórcą przepływu pracy został i ręczny jego wybór.</span><span class="sxs-lookup"><span data-stu-id="242b0-114">This was also a usability issue because it forced the user to determine who the workflow originator was and manually select them.</span></span>  |
| <span data-ttu-id="242b0-115">**Zamieniona przez inną funkcję?**</span><span class="sxs-lookup"><span data-stu-id="242b0-115">**Replaced by another feature?**</span></span>   | <span data-ttu-id="242b0-116">Nie</span><span class="sxs-lookup"><span data-stu-id="242b0-116">No</span></span> |
| <span data-ttu-id="242b0-117">**Powiązane obszary produktów**</span><span class="sxs-lookup"><span data-stu-id="242b0-117">**Product areas affected**</span></span>         | <span data-ttu-id="242b0-118">Przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="242b0-118">Workflow</span></span> |
| <span data-ttu-id="242b0-119">**Opcja wdrażania**</span><span class="sxs-lookup"><span data-stu-id="242b0-119">**Deployment option**</span></span>              | <span data-ttu-id="242b0-120">Wszystkich</span><span class="sxs-lookup"><span data-stu-id="242b0-120">All</span></span> |
| <span data-ttu-id="242b0-121">**Stan**</span><span class="sxs-lookup"><span data-stu-id="242b0-121">**Status**</span></span>                         | <span data-ttu-id="242b0-122">Lista rozwijana wyboru użytkownika została usunięta z okna dialogowego zmiany żądania w aktualizacji platformy 32.</span><span class="sxs-lookup"><span data-stu-id="242b0-122">The user selection drop-down list was removed from the request change dialog box in Platform update 32.</span></span> <span data-ttu-id="242b0-123">Żądania zmiany żądania zostaną automatycznie wysłane do inicjatora zgodnie z zamierzeniem.</span><span class="sxs-lookup"><span data-stu-id="242b0-123">Request change requests will be automatically sent to the originator as intended.</span></span> <span data-ttu-id="242b0-124">Aby uzyskać więcej informacji o tych funkcjach, zapoznaj się z tematem [Akcje w procesach zatwierdzania w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span><span class="sxs-lookup"><span data-stu-id="242b0-124">For more information about this functionality, see [Actions in workflow approval processes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="242b0-125">Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach</span><span class="sxs-lookup"><span data-stu-id="242b0-125">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="242b0-126">Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="242b0-126">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../migration-upgrade/deprecated-features.md).</span></span>

