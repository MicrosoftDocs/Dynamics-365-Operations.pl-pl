---
title: Wewnętrzne składniki majątku do obsługi
description: W tym artykule opisano, jak można korzystać z usług Microsoft Dynamics 365 Field Service do obsługi środków trwałych odbiorcy i własnych.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: b3e741c85fcad2abc18879280ef7332ae091c984
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289259"
---
# <a name="in-house-assets-for-servicing"></a>Wewnętrzne składniki majątku do obsługi

[!include [banner](../../includes/banner.md)]

Usługa Microsoft Dynamics 365 Field Service jest przeznaczona do obsługi składników majątku odbiorców. Zarządzanie składnikami majątku dla Dynamics 365 Supply Chain Management jest przeznaczone do obsługi wewnętrznych składników majątku. Integracja tych dwóch aplikacji umożliwia korzystanie z usługi Field Service w celu obsługi zarówno składników majątku odbiorców, jak i wewnętrznych. Można również sklasyfikować składniki majątku, opierając się na lokalizacji funkcjonalnej lub hierarchii, oraz śledzić obsługę na poziomie szczegółowości.

Aby uzyskać więcej informacji, zajrzyj do [integracji Dynamics 365 Field Service i Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Szablony

Moduł Wewnętrzne składniki majątku zawiera podstawowe mapowania tabel, które działają wspólnie podczas interakcji z danymi, jak pokazano w poniższej tabeli.

| Aplikacje Finance and Operations | Aplikacje Customer Engagement | opis |
|-----------------------------|-----------------------------------|-------------|
[Modele cyklu życia składnika majątku zarządzania składnikami majątku](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Stany cyklu życia składnika majątku zarządzania składnikami majątku](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Typy składników majątku zarządzania składnikami majątku](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Składniki majątku zarządzania składnikami majątku](mapping-reference.md#125) | msdyn_customerassets | |
[Modele cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Stany cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Typy lokalizacji czynności konserwacyjnych zarządzania składnikami majątku](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Lokalizacje czynności konserwacyjnych zarządzania składnikami majątku](mapping-reference.md#136) | msdyn_functionallocations | |
[Producenci zarządzania składnikami majątku](mapping-reference.md#153) | msdyn_manufacturers | |
[Modele zarządzania składnikami majątku](mapping-reference.md#154) | msdyn_models | |
[Gwarancja zarządzania składnikami majątku](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
