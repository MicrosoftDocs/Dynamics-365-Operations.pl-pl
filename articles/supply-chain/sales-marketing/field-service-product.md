---
title: Synchronizowanie produktów w rozwiązaniu Finance and Operations z produktami w rozwiązaniu Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 06d7ff272ecb79abded3c3d3ade1f6bc0ef1f095
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742362"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>Synchronizowanie produktów w rozwiązaniu Finance and Operations z produktami w rozwiązaniu Field Service

[!include[banner](../includes/banner.md)]

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.

Używany szablon **Produkty programu Field Service (z Fin and Ops do Field Service)** jest oparty na szablonie **Produkty (z Fin and Ops do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę. Aby uzyskać więcej informacji, zobacz [Produkty (z Fin and Ops do Sales) — bezpośrednie](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Fin and Ops do Field Service)** i **Produkty (z Fin and Ops do Sales) — bezpośrednie**.

## <a name="templates-and-tasks"></a>Szablony i zadania

**Nazwa szablonu w integracji danych:**

- Produkty programu Field Service (z Fin and Ops do Field Service)

**Nazwa zadania w projekcie integracji danych:**

- Produkty — produkty

Szablon **Produkty programu Field Service (z Fin and Ops do Field Service)** zawiera jedno mapowanie, które nie występuje w szablonie **Produkty (z Fin and Ops do Sales) — bezpośrednie**. To mapowanie zapewnia, że wymagane pole **Typ produktu usługowego** specyficzne dla aplikacji Field Service jest ustawione poprawnie.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Jest stosowane następujące mapowanie wartości.

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

W programie Finance and Operations wartość pola **Typ produktu w rozwiązaniu Field Service** w jednostce danych **Zwolnione produkty możliwe do sprzedaży** jest obliczana w następujący sposób:

- **Zapasy:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Prawda
- **Niemagazynowe:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Fałsz
- **Usługa:** Typ produktu = Usługa

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a>Produkty programu Field Service (z Fin and Ops do Field Service): Produkty — produkty

[![Mapowanie szablonu w integracji danych](./media/FSProduct.png)](./media/FSProduct.png)
