---
title: "Synchronizowanie produktów w rozwiązaniu Finance and Operations z produktami w rozwiązaniu Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08cfd2cfa24bef0f0c92126f5d1052a12ceba37a
ms.openlocfilehash: 699830ce6cd993f3dd3fd4ff744ce5a8b9645c32
ms.contentlocale: pl-pl
ms.lasthandoff: 04/11/2018

---

# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="d7071-103">Synchronizowanie produktów w rozwiązaniu Finance and Operations z produktami w rozwiązaniu Field Service</span><span class="sxs-lookup"><span data-stu-id="d7071-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d7071-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="d7071-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="d7071-105">Używany szablon **Produkty programu Field Service (z Fin and Ops do Field Service)** jest oparty na szablonie **Produkty (z Fin and Ops do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="d7071-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="d7071-106">Aby uzyskać więcej informacji, zobacz [Produkty (z Fin and Ops do Sales) — bezpośrednie](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="d7071-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="d7071-107">Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Fin and Ops do Field Service)** i **Produkty (z Fin and Ops do Sales) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="d7071-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d7071-108">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="d7071-108">Templates and tasks</span></span>

<span data-ttu-id="d7071-109">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="d7071-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="d7071-110">Produkty programu Field Service (z Fin and Ops do Field Service)</span><span class="sxs-lookup"><span data-stu-id="d7071-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="d7071-111">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="d7071-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="d7071-112">Produkty — produkty</span><span class="sxs-lookup"><span data-stu-id="d7071-112">Products - Products</span></span>

<span data-ttu-id="d7071-113">Szablon **Produkty programu Field Service (z Fin and Ops do Field Service)** zawiera jedno mapowanie, które nie występuje w szablonie **Produkty (z Fin and Ops do Sales) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="d7071-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="d7071-114">To mapowanie zapewnia, że wymagane pole **Typ produktu usługowego** specyficzne dla aplikacji Field Service jest ustawione poprawnie.</span><span class="sxs-lookup"><span data-stu-id="d7071-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="d7071-115">Jest stosowane następujące mapowanie wartości.</span><span class="sxs-lookup"><span data-stu-id="d7071-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="d7071-116">W programie Finance and Operations wartość pola **Typ produktu w rozwiązaniu Field Service** w jednostce danych **Zwolnione produkty możliwe do sprzedaży** jest obliczana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d7071-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="d7071-117">**Zapasy:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Prawda</span><span class="sxs-lookup"><span data-stu-id="d7071-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="d7071-118">**Niemagazynowe:** Typ produktu = Grupa modeli produktów i towarów, Produkt magazynowany = Fałsz</span><span class="sxs-lookup"><span data-stu-id="d7071-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="d7071-119">**Usługa:** Typ produktu = Usługa</span><span class="sxs-lookup"><span data-stu-id="d7071-119">**Service:** Product type = Service</span></span>

