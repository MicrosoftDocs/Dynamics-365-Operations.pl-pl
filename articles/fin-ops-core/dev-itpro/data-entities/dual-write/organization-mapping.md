---
title: Hierarchia organizacyjna w usłudze Dataverse
description: W tym temacie opisano integrację danych organizacji między aplikacjami Finance and Operations i Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5132fd85fdf2c08ccded9db590328c394a2f984e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744700"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hierarchia organizacyjna w usłudze Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej. Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.

Mimo że w usłudze Dataverse nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży. W ramach integracji z usługą Dataverse struktura danych hierarchii organizacyjnej jest dodawana do usługi Dataverse.

## <a name="data-flow"></a>Przepływ danych

Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Dataverse będzie nadal posiadał hierarchię organizacyjną. Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Dataverse do celów informacyjnych i rozszerzania środowiska. Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Dataverse w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Dataverse.

![Obraz architektury](media/dual-write-data-flow.png)

Mapy tabeli hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Dataverse.

## <a name="templates"></a>Szablony

Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania. W poniższej tabeli przedstawiono kolekcję mapowań tabel, która umożliwia synchronizowanie produktów i informacji pokrewnych.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | opis
-----------------------|--------------------------------|---
Cele hierarchii organizacji | msdyn_internalorganizationhierarchypurposes | Ten szablon umożliwia jednokierunkową synchronizację tabeli celu hierarchii organizacyjnej.
Typ hierarchii organizacyjnej | msdyn_internalorganizationhierarchytypes | Ten szablon umożliwia jednokierunkową synchronizację tabeli typu hierarchii organizacyjnej.
Hierarchia organizacyjna — opublikowana | msdyn_internalorganizationhierarchies | Ten szablon umożliwia jednokierunkową synchronizację tabeli opublikowanej hierarchii organizacyjnej.
Jednostka operacyjna | msdyn_internalorganizations |
Osoby prawne | msdyn_internalorganizations |
Firmy | cdm_companies | Umożliwia synchronizację dwukierunkową informacji firmy (firmy).

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Wewnętrzna organizacja

Informacje o organizacji wewnętrznej Dataverse pochodzą z dwóch tabel, **jednostki operacyjnej** i **firm**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
