---
title: Zasoby wewnętrzne do obsługi
description: W tym temacie opisano sposób korzystania z usługi Microsoft Dynamics 365 Field Service w celu obsługi zarówno składników majątku odbiorcy, jak i wewnętrznych składników majątku.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 0e87a3d645c19fab3bb0560ba5114d193e2d0be7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997177"
---
# <a name="in-house-assets-for-servicing"></a>Zasoby wewnętrzne do obsługi

[!include [banner](../../includes/banner.md)]



Usługa Microsoft Dynamics 365 Field Service jest przeznaczona do obsługi składników majątku odbiorców. Zarządzanie składnikami majątku dla Dynamics 365 Supply Chain Management jest przeznaczone do obsługi wewnętrznych składników majątku. Integracja tych dwóch aplikacji umożliwia korzystanie z usługi Field Service w celu obsługi zarówno składników majątku odbiorców, jak i wewnętrznych. Można również sklasyfikować składniki majątku, opierając się na lokalizacji funkcjonalnej lub hierarchii, oraz śledzić obsługę na poziomie szczegółowości.

Aby uzyskać więcej informacji, zajrzyj do [integracji Dynamics 365 Field Service i Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Szablony

Moduł wewnętrzne składniki majątku zawiera mapy jednostek podstawowych, które działają wspólnie podczas interakcji, jak pokazano w poniższej tabeli.

| Aplikacje Finance and Operations | Aplikacje oparte na modelu w systemie Dynamics 365 | opis |
|-----------------------------|-----------------------------------|-------------|
| Modele cyklu życia składnika majątku zarządzania składnikami majątku | msdyn\_assetlifecyclemodels | |
| Stany cyklu życia składnika majątku zarządzania składnikami majątku | msdyn\_assetlifecyclestates | |
| Składniki majątku zarządzania składnikami majątku | msdyn\_customerassets | |
| Typy składników majątku zarządzania składnikami majątku | msdyn\_customerassetcategories | |
| Modele cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn\_functionallocationlifecyclemodels | |
| Stany cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn\_functionallocationlifecyclestates | |
| Lokalizacje czynności konserwacyjnych zarządzania składnikami majątku | msdyn\_functionallocations | |
| Typy lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn\_functionallocationtypes | |
| Producenci zarządzania składnikami majątku | msdyn\_manufacturers | |
| Modele zarządzania składnikami majątku | msdyn\_models | |
| Gwarancja zarządzania składnikami majątku | msdyn\_warranties | |

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
