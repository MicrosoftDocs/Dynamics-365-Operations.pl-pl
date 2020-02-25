---
title: Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: c87e4cbfa375ef99d00c9a145c190af78e912d56
ms.sourcegitcommit: d8a2301eda0e5d0a6244ebbbe4459ab6caa88a95
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029412"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service

[!include[banner](../includes/banner.md)]

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.

Używany szablon **Produkty programu Field Service (z Supply Chain Management do Field Service)** jest oparty na szablonie **Produkty (z Supply Chain Management do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę. Aby uzyskać więcej informacji, zobacz [Produkty (z rozwiązania Supply Chain Management do rozwiązania Sales) – bezpośrednio](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Supply Chain Management do Field Service)** i **Produkty (z Supply Chain Management do Sales) — bezpośrednie**.

## <a name="templates-and-tasks"></a>Szablony i zadania

**Nazwa szablonu w integracji danych**

- Produkty Field Service (z rozwiązania Supply Chain Management do rozwiązania Field Service)

**Nazwa zadania w projekcie integracji danych**

- Produkty — produkty

Używany szablon **Produkty programu Field Service (z Supply Chain Management do Field Service)** posiada mapowanie, które nie jest zawarte w szablonie **Produkty (z Supply Chain Management do Sales) — bezpośrednie**. To mapowanie zapewnia, że wymagane pole **Typ produktu usługowego** specyficzne dla aplikacji Field Service jest ustawione poprawnie.

```Text
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Jest stosowane następujące mapowanie wartości.

```Text
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

W programie Supply Chain Management wartość pola **Typ produktu w rozwiązaniu Field Service** w jednostce danych **Zwolnione produkty możliwe do sprzedaży** jest obliczana w następujący sposób:

- **Zapasy:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Prawda
- **Niemagazynowe:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Fałsz
- **Usługa:** Typ produktu = Usługa

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Produkty Field Service (z rozwiązania Supply Chain Management do rozwiązania Field Service): Produkty - Produkty

[![Mapowanie szablonu w integracji danych](./media/FSProduct.png)](./media/FSProduct.png)
