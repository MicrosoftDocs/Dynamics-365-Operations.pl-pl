---
title: Zasoby wewnętrzne do obsługi
description: W tym temacie opisano sposób korzystania z usługi Microsoft Dynamics 365 Field Service w celu obsługi zarówno składników majątku odbiorcy, jak i wewnętrznych składników majątku.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: d4d681b2362c90b69007ea44c01c886f96cc1db1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568085"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="c68b0-103">Wewnętrzne składniki majątku do obsługi</span><span class="sxs-lookup"><span data-stu-id="c68b0-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="c68b0-104">Usługa Microsoft Dynamics 365 Field Service jest przeznaczona do obsługi składników majątku odbiorców.</span><span class="sxs-lookup"><span data-stu-id="c68b0-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="c68b0-105">Zarządzanie składnikami majątku dla Dynamics 365 Supply Chain Management jest przeznaczone do obsługi wewnętrznych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="c68b0-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="c68b0-106">Integracja tych dwóch aplikacji umożliwia korzystanie z usługi Field Service w celu obsługi zarówno składników majątku odbiorców, jak i wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="c68b0-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="c68b0-107">Można również sklasyfikować składniki majątku, opierając się na lokalizacji funkcjonalnej lub hierarchii, oraz śledzić obsługę na poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="c68b0-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="c68b0-108">Aby uzyskać więcej informacji, zajrzyj do [integracji Dynamics 365 Field Service i Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="c68b0-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="c68b0-109">Szablony</span><span class="sxs-lookup"><span data-stu-id="c68b0-109">Templates</span></span>

<span data-ttu-id="c68b0-110">Moduł Wewnętrzne składniki majątku zawiera podstawowe mapowania tabel, które działają wspólnie podczas interakcji z danymi, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c68b0-110">In-house-assets include a collection of core table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="c68b0-111">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c68b0-111">Finance and Operations apps</span></span> | <span data-ttu-id="c68b0-112">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c68b0-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="c68b0-113">opis</span><span class="sxs-lookup"><span data-stu-id="c68b0-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="c68b0-114">Modele cyklu życia składnika majątku zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="c68b0-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="c68b0-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="c68b0-116">Stany cyklu życia składnika majątku zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="c68b0-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="c68b0-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="c68b0-118">Składniki majątku zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-118">Asset management assets</span></span> | <span data-ttu-id="c68b0-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="c68b0-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="c68b0-120">Typy składników majątku zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-120">Asset management asset types</span></span> | <span data-ttu-id="c68b0-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="c68b0-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="c68b0-122">Modele cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="c68b0-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="c68b0-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="c68b0-124">Stany cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="c68b0-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="c68b0-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="c68b0-126">Lokalizacje czynności konserwacyjnych zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-126">Asset management functional locations</span></span> | <span data-ttu-id="c68b0-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="c68b0-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="c68b0-128">Typy lokalizacji czynności konserwacyjnych zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-128">Asset management functional location types</span></span> | <span data-ttu-id="c68b0-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="c68b0-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="c68b0-130">Producenci zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-130">Asset management manufacturers</span></span> | <span data-ttu-id="c68b0-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="c68b0-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="c68b0-132">Modele zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-132">Asset management models</span></span> | <span data-ttu-id="c68b0-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="c68b0-133">msdyn\_models</span></span> | |
| <span data-ttu-id="c68b0-134">Gwarancja zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c68b0-134">Asset management warranty</span></span> | <span data-ttu-id="c68b0-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="c68b0-135">msdyn\_warranties</span></span> | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]