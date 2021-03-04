---
title: Synchronizowanie produktów z jednostką magazynową z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 911c5cc79ae359bbb77d31f366ccfeabf282a33e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435367"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synchronizowanie produktów z jednostką magazynową z rozwiązania Supply Chain Management do rozwiązania Field Service

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Szablon **Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service)** jest oparty na szablonie **Produkt Field Service (Supply Chain Management do Field Service)**. Więcej informacji znajduje się w temacie [Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service](field-service-product.md)

W tym temacie opisano tylko różnice między dwoma szablonami: 
- **Synchronizowanie produktów Field Service z jednostką magazynową (z rozwiązania Supply Chain Management do rozwiązania Sales)**
- **Produkty Field Service (z rozwiązania Supply Chain Management do rozwiązania Field Service)** 

## <a name="templates-and-tasks"></a>Szablony i zadania

**Nazwa szablonu w integracji danych:**

- Synchronizowanie produktów Field Service z jednostką magazynową (z rozwiązania Supply Chain Management do rozwiązania Sales)

**Nazwa zadania w projekcie integracji danych:**

- Produkty

Szablon **Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service)** jest oparty na szablonie zawierającym jedno mapowanie, które nie jest dostępne w **Produktach Field Service (Supply Chain Management do Field Service)**. To mapowanie gwarantuje, że jednostka magazynowa potrzebna do synchronizacji poziom zapasów jest uwzględniona.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service): Produkty

[![Mapowanie szablonu w integracji danych](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]