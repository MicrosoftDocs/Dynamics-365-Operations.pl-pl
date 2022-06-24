---
title: Synchronizowanie produktów z jednostką magazynową z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten artykuł zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5f7658eacd20aa69a64d6288e9d29e53b6ccb002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887262"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synchronizowanie produktów z jednostką magazynową z rozwiązania Supply Chain Management do rozwiązania Field Service

[!include[banner](../includes/banner.md)]

Ten artykuł zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Szablon **Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service)** jest oparty na szablonie **Produkt Field Service (Supply Chain Management do Field Service)**. Więcej informacji znajduje się w temacie [Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service](field-service-product.md)

W tym artykule opisano tylko różnice między dwoma szablonami: 
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

[![Mapowanie szablonu w integracji danych.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]