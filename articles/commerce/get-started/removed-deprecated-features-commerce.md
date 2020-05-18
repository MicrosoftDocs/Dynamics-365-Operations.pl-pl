---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Commerce
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335283"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="1645e-103">Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1645e-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1645e-104">W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1645e-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="1645e-105">*Usunięta* funkcja nie jest już dostępna w produkcie.</span><span class="sxs-lookup"><span data-stu-id="1645e-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="1645e-106">*Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="1645e-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="1645e-107">Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu.</span><span class="sxs-lookup"><span data-stu-id="1645e-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="1645e-108">Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="1645e-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="1645e-109">Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1645e-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="1645e-110">Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.10</span><span class="sxs-lookup"><span data-stu-id="1645e-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="1645e-111">Operacja punktu sprzedaży 803 — pobranie i przyjęcie</span><span class="sxs-lookup"><span data-stu-id="1645e-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="1645e-112">**Przyczyna wycofania/usunięcia**</span><span class="sxs-lookup"><span data-stu-id="1645e-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="1645e-113">Operacje pobrania i przyjęcia są uznawane za przestarzałe z powodu zmian w projekcie nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="1645e-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="1645e-114">**Zamieniona przez inną funkcję?**</span><span class="sxs-lookup"><span data-stu-id="1645e-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="1645e-115">Tak.</span><span class="sxs-lookup"><span data-stu-id="1645e-115">Yes.</span></span> <span data-ttu-id="1645e-116">Zastępują je dwie nowe operacje punktu sprzedaży: operacja przychodząca (804) i operacja wychodząca (805).</span><span class="sxs-lookup"><span data-stu-id="1645e-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="1645e-117">**Powiązane obszary produktów**</span><span class="sxs-lookup"><span data-stu-id="1645e-117">**Product areas affected**</span></span>         | <span data-ttu-id="1645e-118">Aplikacja punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="1645e-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="1645e-119">**Opcja wdrażania**</span><span class="sxs-lookup"><span data-stu-id="1645e-119">**Deployment option**</span></span>              | <span data-ttu-id="1645e-120">Wszystkich</span><span class="sxs-lookup"><span data-stu-id="1645e-120">All</span></span> |
| <span data-ttu-id="1645e-121">**Stan**</span><span class="sxs-lookup"><span data-stu-id="1645e-121">**Status**</span></span>                         | <span data-ttu-id="1645e-122">Przestarzałe: od wydania 10.0.10 operacja pobrania i przyjęcia nie będzie już otrzymywać żadnych nowych aktualizacji funkcji.</span><span class="sxs-lookup"><span data-stu-id="1645e-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="1645e-123">W przyszłych wersjach dla tej operacji będą przeprowadzane tylko krytyczne poprawki usterek.</span><span class="sxs-lookup"><span data-stu-id="1645e-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="1645e-124">Wszystkich klientów zachęcamy do przejścia do nowych [operacji przychodzących](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) i [operacji wychodzących](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), które będą w dalszym ciągu częścią naszego długoterminowego planu rozwoju produktu.</span><span class="sxs-lookup"><span data-stu-id="1645e-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="1645e-125">Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.7</span><span class="sxs-lookup"><span data-stu-id="1645e-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="1645e-126">Interfejsy API rozwiązania Commerce GetProductAvailabilities i GetAvailableInventoryNearby</span><span class="sxs-lookup"><span data-stu-id="1645e-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="1645e-127">**Przyczyna wycofania/usunięcia**</span><span class="sxs-lookup"><span data-stu-id="1645e-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="1645e-128">Utworzono nowe zoptymalizowane interfejsy API w celu zastąpienia interfejsów API GetProductAvailabilities i GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="1645e-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="1645e-129">**Zamieniona przez inną funkcję?**</span><span class="sxs-lookup"><span data-stu-id="1645e-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="1645e-130">Tak: zastępowane przez interfejsy API GetEstimatedAvailability i GetEstimatedProductWarehouseAvailability.</span><span class="sxs-lookup"><span data-stu-id="1645e-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="1645e-131">**Powiązane obszary produktów**</span><span class="sxs-lookup"><span data-stu-id="1645e-131">**Product areas affected**</span></span>         | <span data-ttu-id="1645e-132">Zestaw SDK aplikacji handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1645e-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="1645e-133">**Opcja wdrażania**</span><span class="sxs-lookup"><span data-stu-id="1645e-133">**Deployment option**</span></span>              | <span data-ttu-id="1645e-134">Wszystkich</span><span class="sxs-lookup"><span data-stu-id="1645e-134">All</span></span> |
| <span data-ttu-id="1645e-135">**Stan**</span><span class="sxs-lookup"><span data-stu-id="1645e-135">**Status**</span></span>                         | <span data-ttu-id="1645e-136">Przestarzałe: w przypadku wydania 10.0.7 nie będą już obsługiwane inwestycje inżynieryjne dotyczące interfejsów API GetProductAvailabilities i GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="1645e-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="1645e-137">Organizacje korzystające z tych interfejsów API we wdrożeniach handlu elektronicznego należy przekonwertować na nowe interfejsy API GetEstimatedAvailability i GetEstimatedProductWarehouseAvailability oraz włączyć [funkcję obliczania zoptymalizowanej dostępności produktów](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="1645e-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="1645e-138">Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach</span><span class="sxs-lookup"><span data-stu-id="1645e-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="1645e-139">Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="1645e-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
