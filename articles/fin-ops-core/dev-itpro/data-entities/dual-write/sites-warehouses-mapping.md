---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.
author: t-benebo
manager: AnnBe
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
ms.openlocfilehash: b93e5f15e281c20f8688d496fc78f8b46b8aa996
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560368"
---
# <a name="integrated-sites-and-warehouses"></a>Zintegrowane oddziały i magazyny

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse. Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management. Służą one do modelowania łańcucha dostaw firmy.

## <a name="templates"></a>Szablony

Dzięki integracji z Dataverse te pojęcia i wszystkie informacje związane z nimi są dostępne w Dataverse przy użyciu tabel danych witryn i magazynów wymienionych w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | opis
--------------------------|---------------------------|---
Oddziały | msdyn_operationalsites | 
Magazyny | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]