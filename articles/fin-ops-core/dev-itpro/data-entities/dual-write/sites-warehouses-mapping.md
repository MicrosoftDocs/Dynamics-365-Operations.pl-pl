---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.
author: t-benebo
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
ms.openlocfilehash: 533635ece005636dcee4e24d1d132111e1e2b370
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750673"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="91bb0-103">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="91bb0-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="91bb0-104">W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="91bb0-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="91bb0-105">Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="91bb0-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="91bb0-106">Służą one do modelowania łańcucha dostaw firmy.</span><span class="sxs-lookup"><span data-stu-id="91bb0-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="91bb0-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="91bb0-107">Templates</span></span>

<span data-ttu-id="91bb0-108">Dzięki integracji z Dataverse te pojęcia i wszystkie informacje związane z nimi są dostępne w Dataverse przy użyciu tabel danych witryn i magazynów wymienionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="91bb0-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="91bb0-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="91bb0-109">Finance and Operations apps</span></span> | <span data-ttu-id="91bb0-110">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="91bb0-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="91bb0-111">opis</span><span class="sxs-lookup"><span data-stu-id="91bb0-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="91bb0-112">Oddziały</span><span class="sxs-lookup"><span data-stu-id="91bb0-112">Sites</span></span> | <span data-ttu-id="91bb0-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="91bb0-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="91bb0-114">Magazyny</span><span class="sxs-lookup"><span data-stu-id="91bb0-114">Warehouses</span></span> | <span data-ttu-id="91bb0-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="91bb0-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]