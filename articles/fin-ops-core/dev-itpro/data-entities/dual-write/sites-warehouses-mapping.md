---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.
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
ms.openlocfilehash: d192343d78f9248e4d1232d6aee1a1f800383805
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679327"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="cfc9b-103">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="cfc9b-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="cfc9b-104">W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cfc9b-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="cfc9b-105">Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cfc9b-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="cfc9b-106">Służą one do modelowania łańcucha dostaw firmy.</span><span class="sxs-lookup"><span data-stu-id="cfc9b-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="cfc9b-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="cfc9b-107">Templates</span></span>

<span data-ttu-id="cfc9b-108">Dzięki integracji z Dataverse te pojęcia i wszystkie informacje związane z nimi są dostępne w Dataverse przy użyciu tabel danych witryn i magazynów wymienionych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="cfc9b-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="cfc9b-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cfc9b-109">Finance and Operations apps</span></span> | <span data-ttu-id="cfc9b-110">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="cfc9b-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="cfc9b-111">opis</span><span class="sxs-lookup"><span data-stu-id="cfc9b-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="cfc9b-112">Oddziały</span><span class="sxs-lookup"><span data-stu-id="cfc9b-112">Sites</span></span> | <span data-ttu-id="cfc9b-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="cfc9b-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="cfc9b-114">Magazyny</span><span class="sxs-lookup"><span data-stu-id="cfc9b-114">Warehouses</span></span> | <span data-ttu-id="cfc9b-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="cfc9b-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

