---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazynu między aplikacjami Finance and Operations i Dataverse.
author: t-benebo
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
ms.openlocfilehash: 533635ece005636dcee4e24d1d132111e1e2b370
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750673"
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