---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Common Data Service.
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
ms.openlocfilehash: d5c2030160f6025c9de63b2c29215364f5f87e6f
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997631"
---
# <a name="integrated-sites-and-warehouses"></a>Zintegrowane oddziały i magazyny

[!include [banner](../../includes/banner.md)]



W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Common Data Service. Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management. Służą one do modelowania łańcucha dostaw firmy.

## <a name="templates"></a>Szablony

Dzięki integracji z Common Data Service, te pojęcia i wszystkie informacje związane z nimi są dostępne w Common Data Service przy użyciu stron i magazynów wymienionych w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | Opis
--------------------------|---------------------------|---
Oddziały | msdyn_operationalsites | 
Magazyny | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

