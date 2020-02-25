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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 0f5ed58ad50df49250aa4c001401ff52d460dfa6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019955"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="3268d-103">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="3268d-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="3268d-104">W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3268d-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="3268d-105">Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3268d-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="3268d-106">Służą one do modelowania łańcucha dostaw firmy.</span><span class="sxs-lookup"><span data-stu-id="3268d-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="3268d-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="3268d-107">Templates</span></span>

<span data-ttu-id="3268d-108">Dzięki integracji z Common Data Service, te pojęcia i wszystkie informacje związane z nimi są dostępne w Common Data Service przy użyciu stron i magazynów wymienionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="3268d-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="3268d-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3268d-109">Finance and Operations apps</span></span> | <span data-ttu-id="3268d-110">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3268d-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="3268d-111">Opis</span><span class="sxs-lookup"><span data-stu-id="3268d-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="3268d-112">Oddziały</span><span class="sxs-lookup"><span data-stu-id="3268d-112">Sites</span></span> | <span data-ttu-id="3268d-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="3268d-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="3268d-114">Magazyny</span><span class="sxs-lookup"><span data-stu-id="3268d-114">Warehouses</span></span> | <span data-ttu-id="3268d-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="3268d-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

