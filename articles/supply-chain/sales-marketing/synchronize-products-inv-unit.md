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

# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="d199b-103">Synchronizowanie produktów z jednostką zapasów między aplikacjami Finance and Operations i Field Service</span><span class="sxs-lookup"><span data-stu-id="d199b-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d199b-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="d199b-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="d199b-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="d199b-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="d199b-106">Używany szablon **Produkty programu Field Service (z Finance and Operations do Field Service)** jest oparty na szablonie **Produkty (z Finance and Operations do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="d199b-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="d199b-107">Aby uzyskać więcej informacji, zobacz [Produkty (z rozwiązania Finance and Operations do rozwiązania Sales) – bezpośrednio](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="d199b-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="d199b-108">Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Finance and Operations do Field Service)** i **Produkty Field Service (z Finance and Operations do Field Service) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="d199b-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d199b-109">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="d199b-109">Templates and tasks</span></span>

<span data-ttu-id="d199b-110">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="d199b-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="d199b-111">Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)</span><span class="sxs-lookup"><span data-stu-id="d199b-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="d199b-112">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="d199b-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="d199b-113">Produkty</span><span class="sxs-lookup"><span data-stu-id="d199b-113">Products</span></span>

<span data-ttu-id="d199b-114">Szablon **Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service)** zawiera jedno mapowanie, którego nie ma w szablonie **Produkt Field Service (Finance and Operations do Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="d199b-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="d199b-115">To mapowanie gwarantuje, że jednostka magazynowa potrzebna do synchronizacji poziom zapasów jest uwzględniona.</span><span class="sxs-lookup"><span data-stu-id="d199b-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d199b-116">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="d199b-116">Template mapping in Data integration</span></span>

<span data-ttu-id="d199b-117">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="d199b-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="d199b-118">Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service): Produkty</span><span class="sxs-lookup"><span data-stu-id="d199b-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="d199b-119">[![Mapowanie szablonu w integracji danych](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="d199b-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>

