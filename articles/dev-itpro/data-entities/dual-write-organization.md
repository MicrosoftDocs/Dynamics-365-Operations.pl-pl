---
title: Hierarchia organizacyjna w usłudze Common Data Service
description: W tym temacie opisano integrację danych organizacji między programami Finance and Operations i Common Data Service.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789233"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Hierarchia organizacyjna w usłudze Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Ponieważ Microsoft Dynamics 365 for Finance and Operations jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej. Finanse i operacje biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.

Mimo że w usłudze Common Data Service nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży. W ramach integracji z usługą Common Data Service struktura danych hierarchii organizacyjnej jest dodawana do usługi Common Data Service.

## <a name="data-flow"></a>Przepływ danych

Ekosystem biznesowy składający się z programu Finance and Operations i usługi Common Data Service będzie nadal posiadał hierarchię organizacyjną. Ta hierarchia organizacji jest zbudowana na programie Finance and Operations, ale jest dostępna w usłudze Common Data Service do celów informacyjnych i rozszerzania środowiska. Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Common Data Service w postaci jednokierunkowego przepływu danych z programu Finance and Operations do usługi Common Data Service.

![Obraz architektury](media/dual-write-data-flow.png)

## <a name="templates"></a>Szablony

Mapy encji hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z programu Finance and Operations do usługi Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Wewnętrzne cele hierarchii organizacyjnej

Ten szablon zapewnia jednokierunkową synchronizację encji Cele hierarchii organizacji z programu Finance and Operations do Dynamics 365 for Customer Engagement.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Typ wewnętrznej hierarchii organizacyjnej

Ten szablon zapewnia jednokierunkową synchronizację encji Typ hierarchii organizacji z programu Finance and Operations do Customer Engagement.

<!-- ![architecture image](media/dual-write-type.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAZWA | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Wewnętrzna hierarchia organizacyjna

Ten szablon zapewnia jednokierunkową synchronizację encji Opublikowanej hierarchii organizacji z programu Finance and Operations do Customer Engagement.

<!-- ![architecture image](media/dual-write-organization.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Wewnętrzna organizacja

Informacje o organizacji wewnętrznej Common Data Service pochodzą z dwóch encji Finance and Operations, **jednostki operacyjnej** i **podmiotów prawnych**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Jednostka operacyjna

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namealias
NAZWA | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Firma

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAMEALIAS | \> | msdyn\_namealias
LANGUAGEID | \> | msdyn\_languageid
NAZWA | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
brak | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Firma

Zapewnia dwukierunkową synchronizację informacji podmiotu prawnego (firmy) między programem Finance and Operations a Customer Engagement.

<!-- ![architecture image](media/dual-write-company.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAZWA | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
