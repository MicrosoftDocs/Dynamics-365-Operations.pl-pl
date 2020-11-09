---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: d5c2030160f6025c9de63b2c29215364f5f87e6f
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997631"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="70586-103">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="70586-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="70586-104">W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70586-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="70586-105">Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70586-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="70586-106">Służą one do modelowania łańcucha dostaw firmy.</span><span class="sxs-lookup"><span data-stu-id="70586-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="70586-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="70586-107">Templates</span></span>

<span data-ttu-id="70586-108">Dzięki integracji z Common Data Service, te pojęcia i wszystkie informacje związane z nimi są dostępne w Common Data Service przy użyciu stron i magazynów wymienionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="70586-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="70586-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="70586-109">Finance and Operations apps</span></span> | <span data-ttu-id="70586-110">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="70586-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="70586-111">Opis</span><span class="sxs-lookup"><span data-stu-id="70586-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="70586-112">Oddziały</span><span class="sxs-lookup"><span data-stu-id="70586-112">Sites</span></span> | <span data-ttu-id="70586-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="70586-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="70586-114">Magazyny</span><span class="sxs-lookup"><span data-stu-id="70586-114">Warehouses</span></span> | <span data-ttu-id="70586-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="70586-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

