---
title: "Synchronizowanie produktów z jednostką zapasów między aplikacjami Finance and Operations i Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Synchronizowanie produktów z jednostką zapasów między aplikacjami Finance and Operations i Field Service

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Używany szablon **Produkty programu Field Service (z Finance and Operations do Field Service)** jest oparty na szablonie **Produkty (z Finance and Operations do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę. Aby uzyskać więcej informacji, zobacz [Produkty (z rozwiązania Finance and Operations do rozwiązania Sales) – bezpośrednio](products-template-mapping-direct.md).

Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Finance and Operations do Field Service)** i **Produkty Field Service (z Finance and Operations do Field Service) — bezpośrednie**.

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

