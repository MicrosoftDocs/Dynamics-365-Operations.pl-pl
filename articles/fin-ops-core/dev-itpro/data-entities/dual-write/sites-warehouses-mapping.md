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
ms.openlocfilehash: 1b9181211bbb65cdfc46e63f3cee0e9f5bc9f6a4
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173069"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="bc5f7-103">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="bc5f7-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="bc5f7-104">W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bc5f7-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="bc5f7-105">Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bc5f7-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="bc5f7-106">Służą one do modelowania łańcucha dostaw firmy.</span><span class="sxs-lookup"><span data-stu-id="bc5f7-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="bc5f7-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="bc5f7-107">Templates</span></span>

<span data-ttu-id="bc5f7-108">Dzięki integracji z Common Data Service, te pojęcia i wszystkie informacje związane z nimi są dostępne w Common Data Service przy użyciu stron i magazynów wymienionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="bc5f7-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="bc5f7-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bc5f7-109">Finance and Operations apps</span></span> | <span data-ttu-id="bc5f7-110">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bc5f7-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="bc5f7-111">Opis</span><span class="sxs-lookup"><span data-stu-id="bc5f7-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="bc5f7-112">Oddziały</span><span class="sxs-lookup"><span data-stu-id="bc5f7-112">Sites</span></span> | <span data-ttu-id="bc5f7-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="bc5f7-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="bc5f7-114">Magazyny</span><span class="sxs-lookup"><span data-stu-id="bc5f7-114">Warehouses</span></span> | <span data-ttu-id="bc5f7-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="bc5f7-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

