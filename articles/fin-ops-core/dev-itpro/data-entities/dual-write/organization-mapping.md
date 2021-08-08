---
title: Hierarchia organizacyjna w usłudze Dataverse
description: W tym temacie opisano integrację danych organizacji między aplikacjami Finance and Operations i Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d1ad3bc4eef1650b927d9f6dd699f788994c7e87
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542594"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hierarchia organizacyjna w usłudze Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej. Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.

Mimo że w usłudze Dataverse nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży. W ramach integracji z usługą Dataverse struktura danych hierarchii organizacyjnej jest dodawana do usługi Dataverse.

## <a name="data-flow"></a>Przepływ danych

Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Dataverse będzie nadal posiadał hierarchię organizacyjną. Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Dataverse do celów informacyjnych i rozszerzania środowiska. Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Dataverse w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Dataverse.

![Obraz architektury.](media/dual-write-data-flow.png)

Mapy tabeli hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Dataverse.

## <a name="templates"></a>Szablony

Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania. W poniższej tabeli przedstawiono kolekcję mapowań tabel, która umożliwia synchronizowanie produktów i informacji pokrewnych.

Aplikacje Finance and Operations | Aplikacje Customer Engagement     | opis
-----------------------|--------------------------------|---
[Osoby prawne](mapping-reference.md#102) | cdm_companies | Umożliwia synchronizację dwukierunkową informacji firmy (firmy).
[Osoby prawne](mapping-reference.md#142) | msdyn_internalorganizations |
[Jednostka operacyjna](mapping-reference.md#143) | msdyn_internalorganizations |
[Hierarchia organizacyjna — opublikowana](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Ten szablon umożliwia jednokierunkową synchronizację tabeli opublikowanej hierarchii organizacyjnej.
[Cele hierarchii organizacji](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Ten szablon umożliwia jednokierunkową synchronizację tabeli celu hierarchii organizacyjnej.
[Typ hierarchii organizacyjnej](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Ten szablon umożliwia jednokierunkową synchronizację tabeli typu hierarchii organizacyjnej.

## <a name="internal-organization"></a>Wewnętrzna organizacja

Informacje o organizacji wewnętrznej Dataverse pochodzą z dwóch tabel, **Jednostki operacyjnej** i **Firm**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
