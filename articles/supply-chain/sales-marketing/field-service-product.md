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
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="cf4fb-103">Synchronizowanie produktów w rozwiązaniu Finance and Operations z produktami w rozwiązaniu Field Service</span><span class="sxs-lookup"><span data-stu-id="cf4fb-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cf4fb-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="cf4fb-105">Używany szablon **Produkty programu Field Service (z Fin and Ops do Field Service)** jest oparty na szablonie **Produkty (z Fin and Ops do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="cf4fb-106">Aby uzyskać więcej informacji, zobacz [Produkty (z Fin and Ops do Sales) — bezpośrednie](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="cf4fb-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="cf4fb-107">Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Fin and Ops do Field Service)** i **Produkty (z Fin and Ops do Sales) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="cf4fb-108">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="cf4fb-108">Templates and tasks</span></span>

<span data-ttu-id="cf4fb-109">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="cf4fb-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="cf4fb-110">Produkty programu Field Service (z Fin and Ops do Field Service)</span><span class="sxs-lookup"><span data-stu-id="cf4fb-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="cf4fb-111">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="cf4fb-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="cf4fb-112">Produkty — produkty</span><span class="sxs-lookup"><span data-stu-id="cf4fb-112">Products - Products</span></span>

<span data-ttu-id="cf4fb-113">Szablon **Produkty programu Field Service (z Fin and Ops do Field Service)** zawiera jedno mapowanie, które nie występuje w szablonie **Produkty (z Fin and Ops do Sales) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="cf4fb-114">To mapowanie zapewnia, że wymagane pole **Typ produktu usługowego** specyficzne dla aplikacji Field Service jest ustawione poprawnie.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="cf4fb-115">Jest stosowane następujące mapowanie wartości.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="cf4fb-116">W programie Finance and Operations wartość pola **Typ produktu w rozwiązaniu Field Service** w jednostce danych **Zwolnione produkty możliwe do sprzedaży** jest obliczana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="cf4fb-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="cf4fb-117">**Zapasy:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Prawda</span><span class="sxs-lookup"><span data-stu-id="cf4fb-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="cf4fb-118">**Niemagazynowe:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Fałsz</span><span class="sxs-lookup"><span data-stu-id="cf4fb-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="cf4fb-119">**Usługa:** Typ produktu = Usługa</span><span class="sxs-lookup"><span data-stu-id="cf4fb-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cf4fb-120">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="cf4fb-120">Template mapping in Data integration</span></span>

<span data-ttu-id="cf4fb-121">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="cf4fb-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a><span data-ttu-id="cf4fb-122">Produkty programu Field Service (z Fin and Ops do Field Service): Produkty — produkty</span><span class="sxs-lookup"><span data-stu-id="cf4fb-122">Field Service Products (Fin and Ops to Field Service): Products - Products</span></span>

<span data-ttu-id="cf4fb-123">[![Mapowanie szablonu w integracji danych](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="cf4fb-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
