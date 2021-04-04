---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b93e5f15e281c20f8688d496fc78f8b46b8aa996
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560368"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="906a4-103">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="906a4-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="906a4-104">W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="906a4-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="906a4-105">Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="906a4-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="906a4-106">Służą one do modelowania łańcucha dostaw firmy.</span><span class="sxs-lookup"><span data-stu-id="906a4-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="906a4-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="906a4-107">Templates</span></span>

<span data-ttu-id="906a4-108">Dzięki integracji z Dataverse te pojęcia i wszystkie informacje związane z nimi są dostępne w Dataverse przy użyciu tabel danych witryn i magazynów wymienionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="906a4-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="906a4-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="906a4-109">Finance and Operations apps</span></span> | <span data-ttu-id="906a4-110">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="906a4-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="906a4-111">opis</span><span class="sxs-lookup"><span data-stu-id="906a4-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="906a4-112">Oddziały</span><span class="sxs-lookup"><span data-stu-id="906a4-112">Sites</span></span> | <span data-ttu-id="906a4-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="906a4-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="906a4-114">Magazyny</span><span class="sxs-lookup"><span data-stu-id="906a4-114">Warehouses</span></span> | <span data-ttu-id="906a4-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="906a4-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]