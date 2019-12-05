---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazyny między programami Finance and Operations i Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771002"
---
# <a name="integrated-sites-and-warehouses"></a>Zintegrowane witryny i magazyny

[!include [banner](../includes/banner.md)]

W tym temacie opisano integrację danych witryny i magazyny między programami Finance and Operations i Common Data Service. Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management. Służą one do modelowania łańcucha dostaw firmy.

## <a name="templates"></a>Szablony

Dzięki integracji z Common Data Service, te pojęcia i wszystkie informacje związane z nimi są dostępne w Common Data Service przy użyciu stron i magazynów wymienionych w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | Opis
--------------------------|---------------------------|---
Oddziały | msdyn_operationalsites | 
Magazyny | msdyn_warehouses | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

