---
title: Hierarchia organizacyjna w usłudze Dataverse
description: W tym artykule opisano integrację danych organizacji między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a4edaf5b9c50e9d8781ff703328ac786d71ee782
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884740"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hierarchia organizacyjna w usłudze Dataverse

[!include [banner](../../includes/banner.md)]



Ponieważ aplikacja Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej. Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.

Mimo że w usłudze Dataverse nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży. W ramach integracji z usługą Dataverse struktura danych hierarchii organizacyjnej jest dodawana do usługi Dataverse.

## <a name="data-flow"></a>Przepływ danych

Ekosystem biznesowy składający się z aplikacji Finanse i Działania i usługi Dataverse będzie nadal posiadał hierarchię organizacyjną. Ta hierarchia organizacji jest zbudowana na aplikacjach Finanse i Działania, ale jest dostępna w usłudze Dataverse do celów informacyjnych i rozszerzania środowiska. Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Dataverse w postaci jednokierunkowego przepływu danych z aplikacji Finanse i Działania do usługi Dataverse.

![Obraz architektury.](media/dual-write-data-flow.png)

Mapy tabeli hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finanse i Działania do usługi Dataverse.

## <a name="templates"></a>Szablony

Organizacja to grupa osób, które pracują razem, aby przeprowadzić proces biznesowy lub osiągnąć cel. Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę. Można zdefiniować następujące typy organizacji wewnętrznych: podmioty prawne (zwykle dla uproszczenia określane jako firmy), jednostki operacyjne i zespoły. Jak pokazano w poniższej tabeli, tworzona jest kolekcja map tabel w celu synchronizowania informacji o firmach, jednostkach operacyjnych i powiązanej hierarchii organizacji.

Aplikacje Finanse i Działania | Aplikacje Customer Engagement     | Opis
-----------------------|--------------------------------|---
[Osoby prawne](mapping-reference.md#102) | cdm_companies | 
[Osoby prawne](mapping-reference.md#142) | msdyn_internalorganizations |
[Jednostka operacyjna](mapping-reference.md#143) | msdyn_internalorganizations |
[Hierarchia organizacyjna — opublikowana](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Ten szablon umożliwia jednokierunkową synchronizację tabeli opublikowanej hierarchii organizacyjnej.
[Cele hierarchii organizacji](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Ten szablon umożliwia jednokierunkową synchronizację tabeli celu hierarchii organizacyjnej.
[Typ hierarchii organizacyjnej](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Ten szablon umożliwia jednokierunkową synchronizację tabeli typu hierarchii organizacyjnej.

## <a name="internal-organization"></a>Wewnętrzna organizacja

Informacje o organizacji wewnętrznej Dataverse pochodzą z dwóch tabel, **Jednostki operacyjnej** i **Firm**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
