---
title: Hierarchia organizacyjna w usłudze Common Data Service
description: W tym temacie opisano integrację danych organizacji między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9efc63c385c31a6d8848d016c1a8689460908dcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769667"
---
# <a name="organization-hierarchy-in-common-data-service"></a>Hierarchia organizacyjna w usłudze Common Data Service

[!include [banner](../includes/banner.md)]

Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej. Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.

Mimo że w usłudze Common Data Service nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży. W ramach integracji z usługą Common Data Service struktura danych hierarchii organizacyjnej jest dodawana do usługi Common Data Service.

## <a name="data-flow"></a>Przepływ danych

Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Common Data Service będzie nadal posiadał hierarchię organizacyjną. Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Common Data Service do celów informacyjnych i rozszerzania środowiska. Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Common Data Service w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Common Data Service.

![Obraz architektury](media/dual-write-data-flow.png)

## <a name="templates"></a>Szablony

Mapy encji hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Common Data Service.

## <a name="templates"></a>Szablony

Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania. W poniższej tabeli przedstawiono kolekcję mapowań jednostek, która umożliwia synchronizowanie produktów i informacji pokrewnych.

Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | Opis
-----------------------|--------------------------------|---
Cele hierarchii organizacji | msdyn_internalorganizationhierarchypurposes | Ten szablon umożliwia jednokierunkową synchronizację jednostki cel hierarchii organizacyjnej.
Typ hierarchii organizacyjnej | msdyn_internalorganizationhierarchytypes | Ten szablon umożliwia jednokierunkową synchronizację jednostki typu hierarchii organizacyjnej.
Hierarchia organizacyjna - opublikowana | msdyn_internalorganizationhierarchies | Ten szablon umożliwia jednokierunkową synchronizację jednostki opublikowanej hierarchii organizacyjnej.
Jednostka operacyjna | msdyn_internalorganizations | 
Firmy | msdyn_internalorganizations | 
Firmy | cdm_companies | Umożliwia synchronizację dwukierunkową informacji firmy (firmy).


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](dual-write/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](dual-write/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](dual-write/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Wewnętrzna organizacja

Informacje o organizacji wewnętrznej Common Data Service pochodzą z dwóch encji, **jednostki operacyjnej** i **firm**.

[!include [Operating unit](dual-write/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-Companies.md)]

