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
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="7ad31-103">Synchronizowanie produktów z jednostką magazynową z rozwiązania Supply Chain Management do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="7ad31-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7ad31-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów z jednostką zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="7ad31-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="7ad31-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="7ad31-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="7ad31-106">Szablon **Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service)** jest oparty na szablonie **Produkt Field Service (Supply Chain Management do Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="7ad31-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="7ad31-107">Więcej informacji znajduje się w temacie [Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service](field-service-product.md)</span><span class="sxs-lookup"><span data-stu-id="7ad31-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="7ad31-108">W tym temacie opisano tylko różnice między dwoma szablonami:</span><span class="sxs-lookup"><span data-stu-id="7ad31-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="7ad31-109">**Synchronizowanie produktów Field Service z jednostką magazynową (z rozwiązania Supply Chain Management do rozwiązania Sales)**</span><span class="sxs-lookup"><span data-stu-id="7ad31-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="7ad31-110">**Produkty Field Service (z rozwiązania Supply Chain Management do rozwiązania Field Service)**</span><span class="sxs-lookup"><span data-stu-id="7ad31-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="7ad31-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="7ad31-111">Templates and tasks</span></span>

<span data-ttu-id="7ad31-112">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="7ad31-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="7ad31-113">Synchronizowanie produktów Field Service z jednostką magazynową (z rozwiązania Supply Chain Management do rozwiązania Sales)</span><span class="sxs-lookup"><span data-stu-id="7ad31-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="7ad31-114">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="7ad31-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="7ad31-115">Produkty</span><span class="sxs-lookup"><span data-stu-id="7ad31-115">Products</span></span>

<span data-ttu-id="7ad31-116">Szablon **Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service)** jest oparty na szablonie zawierającym jedno mapowanie, które nie jest dostępne w **Produktach Field Service (Supply Chain Management do Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="7ad31-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="7ad31-117">To mapowanie gwarantuje, że jednostka magazynowa potrzebna do synchronizacji poziom zapasów jest uwzględniona.</span><span class="sxs-lookup"><span data-stu-id="7ad31-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7ad31-118">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="7ad31-118">Template mapping in Data integration</span></span>

<span data-ttu-id="7ad31-119">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="7ad31-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="7ad31-120">Produkty Field Service z jednostką magazynową (Supply Chain Management do Field Service): Produkty</span><span class="sxs-lookup"><span data-stu-id="7ad31-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="7ad31-121">[![Mapowanie szablonu w integracji danych](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="7ad31-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
