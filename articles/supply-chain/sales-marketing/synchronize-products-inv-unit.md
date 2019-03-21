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
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="60671-103">Synchronizowanie produktów z jednostką magazynową z rozwiązania Finance and Operations do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="60671-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="60671-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="60671-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="60671-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="60671-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="60671-106">Szablon **Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service)** jest oparty na szablonie **Produkt Field Service (Finance and Operations do Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="60671-106">The used **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template is based on the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="60671-107">Aby uzyskać więcej informacji, zobacz [Produkty Field Service (z rozwiązania Finance and Operations do rozwiązania Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="60671-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="60671-108">W tym temacie opisano tylko różnice między dwoma szablonami:</span><span class="sxs-lookup"><span data-stu-id="60671-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="60671-109">**Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)**</span><span class="sxs-lookup"><span data-stu-id="60671-109">**Field Service Products with Inventory unit (Finance and Operations to Sales)**</span></span>
- <span data-ttu-id="60671-110">**Produkty Field Service (z rozwiązania Finance and Operations do rozwiązania Field Service)**</span><span class="sxs-lookup"><span data-stu-id="60671-110">**Field Service Products (Finance and Operations to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="60671-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="60671-111">Templates and tasks</span></span>

<span data-ttu-id="60671-112">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="60671-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="60671-113">Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)</span><span class="sxs-lookup"><span data-stu-id="60671-113">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="60671-114">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="60671-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="60671-115">Produkty</span><span class="sxs-lookup"><span data-stu-id="60671-115">Products</span></span>

<span data-ttu-id="60671-116">Szablon **Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service)** zawiera jedno mapowanie, którego nie ma w szablonie **Produkt Field Service (Finance and Operations do Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="60671-116">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="60671-117">To mapowanie gwarantuje, że jednostka magazynowa potrzebna do synchronizacji poziom zapasów jest uwzględniona.</span><span class="sxs-lookup"><span data-stu-id="60671-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="60671-118">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="60671-118">Template mapping in Data integration</span></span>

<span data-ttu-id="60671-119">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="60671-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="60671-120">Produkty Field Service z jednostką magazynową (Finance and Operations do Field Service): Produkty</span><span class="sxs-lookup"><span data-stu-id="60671-120">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="60671-121">[![Mapowanie szablonu w integracji danych](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="60671-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
