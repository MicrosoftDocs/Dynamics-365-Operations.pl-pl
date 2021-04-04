---
title: Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d3dc21a39c9866d09e500e2f14ff810bac7d57fe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261052"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="e4b1a-103">Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service</span><span class="sxs-lookup"><span data-stu-id="e4b1a-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e4b1a-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="e4b1a-105">Używany szablon **Produkty programu Field Service (z Supply Chain Management do Field Service)** jest oparty na szablonie **Produkty (z Supply Chain Management do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="e4b1a-106">Aby uzyskać więcej informacji, zobacz [Produkty (z rozwiązania Supply Chain Management do rozwiązania Sales) – bezpośrednio](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="e4b1a-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="e4b1a-107">Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Supply Chain Management do Field Service)** i **Produkty (z Supply Chain Management do Sales) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e4b1a-108">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="e4b1a-108">Templates and tasks</span></span>

<span data-ttu-id="e4b1a-109">**Nazwa szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="e4b1a-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="e4b1a-110">Produkty Field Service (z rozwiązania Supply Chain Management do rozwiązania Field Service)</span><span class="sxs-lookup"><span data-stu-id="e4b1a-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="e4b1a-111">**Nazwa zadania w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="e4b1a-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="e4b1a-112">Produkty — produkty</span><span class="sxs-lookup"><span data-stu-id="e4b1a-112">Products - Products</span></span>

<span data-ttu-id="e4b1a-113">Używany szablon **Produkty programu Field Service (z Supply Chain Management do Field Service)** posiada mapowanie, które nie jest zawarte w szablonie **Produkty (z Supply Chain Management do Sales) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="e4b1a-114">To mapowanie zapewnia, że wymagane pole **Typ produktu usługowego** specyficzne dla aplikacji Field Service jest ustawione poprawnie.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="e4b1a-115">Jest stosowane następujące mapowanie wartości.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="e4b1a-116">W programie Supply Chain Management wartość pola **Typ produktu w rozwiązaniu Field Service** w jednostce danych **Zwolnione produkty możliwe do sprzedaży** jest obliczana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e4b1a-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="e4b1a-117">**Zapasy:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Prawda</span><span class="sxs-lookup"><span data-stu-id="e4b1a-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="e4b1a-118">**Niemagazynowe:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Fałsz</span><span class="sxs-lookup"><span data-stu-id="e4b1a-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="e4b1a-119">**Usługa:** Typ produktu = Usługa</span><span class="sxs-lookup"><span data-stu-id="e4b1a-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e4b1a-120">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="e4b1a-120">Template mapping in Data integration</span></span>

<span data-ttu-id="e4b1a-121">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="e4b1a-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="e4b1a-122">Produkty Field Service (z rozwiązania Supply Chain Management do rozwiązania Field Service): Produkty - Produkty</span><span class="sxs-lookup"><span data-stu-id="e4b1a-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="e4b1a-123">[![Mapowanie szablonu w integracji danych](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="e4b1a-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]