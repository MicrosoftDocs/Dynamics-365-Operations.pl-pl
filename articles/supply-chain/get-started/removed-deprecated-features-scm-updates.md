---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Supply Chain Management
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia w Dynamics 365 Supply Chain Management.
author: kamaybac
manager: AnnBe
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7502cd16129431d41d152508fb3b49ff85a5a9f8
ms.sourcegitcommit: f1db998ecfccca660eb15cc2739b12c8463fa54d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2020
ms.locfileid: "3331255"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="4f817-103">Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4f817-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f817-104">Ten temat zostanie zaktualizowany, jeśli w systemie Dynamics 365 Supply Chain Management zostaną udokumentowane nowe lub wycofane funkcje.</span><span class="sxs-lookup"><span data-stu-id="4f817-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="4f817-105">*Usunięta* funkcja nie jest już dostępna w produkcie.</span><span class="sxs-lookup"><span data-stu-id="4f817-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="4f817-106">*Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="4f817-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="4f817-107">Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu.</span><span class="sxs-lookup"><span data-stu-id="4f817-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="4f817-108">Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="4f817-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="4f817-109">Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f817-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="4f817-110">Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.11</span><span class="sxs-lookup"><span data-stu-id="4f817-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="4f817-111">Użycie wbudowanego aparatu planowania głównego Supply Chain Management na potrzeby scenariuszy dotyczących dystrybucji</span><span class="sxs-lookup"><span data-stu-id="4f817-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="4f817-112">**Przyczyna wycofania/usunięcia**</span><span class="sxs-lookup"><span data-stu-id="4f817-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="4f817-113">Aby zwiększyć wydajność i zminimalizować obciążenie pracą bazy danych SQL podczas przebiegów planowania głównego, aparat planowania głównego aplikacji Supply Chain Management jest zastępowany przez optymalizację planowania.</span><span class="sxs-lookup"><span data-stu-id="4f817-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="4f817-114">Optymalizacja planowania umożliwia szybkie przebiegi planowania, które można wykonywać nawet w godzinach pracy.</span><span class="sxs-lookup"><span data-stu-id="4f817-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="4f817-115">Pozwala to planistom na natychmiastowe reagowanie na zmiany wprowadzone w parametrach popytu lub planowania.</span><span class="sxs-lookup"><span data-stu-id="4f817-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="4f817-116">**Zamieniona przez inną funkcję?**</span><span class="sxs-lookup"><span data-stu-id="4f817-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="4f817-117">Tak, optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4f817-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="4f817-118">**Powiązane obszary produktów**</span><span class="sxs-lookup"><span data-stu-id="4f817-118">**Product areas affected**</span></span>         | <span data-ttu-id="4f817-119">Supply Chain Management — planowanie główne</span><span class="sxs-lookup"><span data-stu-id="4f817-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="4f817-120">**Opcja wdrażania**</span><span class="sxs-lookup"><span data-stu-id="4f817-120">**Deployment option**</span></span>              | <span data-ttu-id="4f817-121">Tylko chmura.</span><span class="sxs-lookup"><span data-stu-id="4f817-121">Cloud only.</span></span> <span data-ttu-id="4f817-122">Optymalizacja planowania nie jest obsługiwana w przypadku wdrożeń lokalnych.</span><span class="sxs-lookup"><span data-stu-id="4f817-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="4f817-123">**Stan**</span><span class="sxs-lookup"><span data-stu-id="4f817-123">**Status**</span></span>                         | <span data-ttu-id="4f817-124">Wycofane.</span><span class="sxs-lookup"><span data-stu-id="4f817-124">Deprecated.</span></span> <span data-ttu-id="4f817-125">W kwietniu 2021 r. scenariusze dystrybucji nie będą już obsługiwane za pomocą wbudowanego aparatu planowania głównego aplikacji Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4f817-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="4f817-126">W scenariuszach dystrybucji klienci muszą korzystać z optymalizacji planowania podczas obliczeń planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="4f817-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="4f817-127">Aby uzyskać więcej informacji, zobacz temat [Dokumentacja dotycząca optymalizacji planowania](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="4f817-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="4f817-128">Klienci z wdrożeniami lokalnymi aplikacji Dynamics 365 Supply Chain Management będą mogli nadal korzystać z aparatu planowania głównego aplikacji Supply Chain Management w scenariuszach dystrybucji po kwietniu 2021 r.</span><span class="sxs-lookup"><span data-stu-id="4f817-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="4f817-129">Nie będą jednak wprowadzane dodatkowe ulepszenia funkcji.</span><span class="sxs-lookup"><span data-stu-id="4f817-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="4f817-130">Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach</span><span class="sxs-lookup"><span data-stu-id="4f817-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="4f817-131">Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="4f817-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
