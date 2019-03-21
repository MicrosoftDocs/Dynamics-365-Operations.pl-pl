---
title: Synchronizowanie produktów z jednostką zapasów między aplikacjami Finance and Operations i Field Service
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2019
ms.locfileid: "836309"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Synchronizowanie produktów z jednostką magazynową z rozwiązania Finance and Operations do rozwiązania Field Service

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Szablon **Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service)** jest oparty na szablonie **Produkt Field Service (Finance and Operations do Field Service)**. Aby uzyskać więcej informacji, zobacz [Produkty Field Service (z rozwiązania Finance and Operations do rozwiązania Field Service)](field-service-product.md).

W tym temacie opisano tylko różnice między dwoma szablonami: 
- **Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)**
- **Produkty Field Service (z rozwiązania Finance and Operations do rozwiązania Field Service)** 

## <a name="templates-and-tasks"></a>Szablony i zadania

**Nazwa szablonu w integracji danych:**

- Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)

**Nazwa zadania w projekcie integracji danych:**

- Produkty

Szablon **Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service)** zawiera jedno mapowanie, którego nie ma w szablonie **Produkt Field Service (Finance and Operations do Field Service)**. To mapowanie gwarantuje, że jednostka magazynowa potrzebna do synchronizacji poziom zapasów jest uwzględniona.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service): Produkty

[![Mapowanie szablonu w integracji danych](./media/FSProduct1.png)](./media/FSProduct1.png)
