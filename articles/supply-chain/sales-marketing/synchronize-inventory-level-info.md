---
title: "Synchronizowanie informacji poziomu zapasów między aplikacjami Finance and Operations i Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 3ccc4d406fa4f9800dcdf8697a91892408783196
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="582cd-103">Synchronizowanie informacji poziomu zapasów między aplikacjami Finance and Operations i Field Service</span><span class="sxs-lookup"><span data-stu-id="582cd-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="582cd-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="582cd-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="582cd-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="582cd-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="582cd-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="582cd-106">Templates and tasks</span></span>
<span data-ttu-id="582cd-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania poziomów dostępnych zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="582cd-107">The following template and underlying tasks are used to run synchronization of inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="582cd-108">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="582cd-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="582cd-109">Zapasy produktu (Finance and Operations do Field Service)</span><span class="sxs-lookup"><span data-stu-id="582cd-109">Product Inventory (Finance and Operations to Field Service)</span></span>
  
<span data-ttu-id="582cd-110">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="582cd-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="582cd-111">Zapasy produktu</span><span class="sxs-lookup"><span data-stu-id="582cd-111">Product inventory</span></span>

<span data-ttu-id="582cd-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować poziomy zapasów:</span><span class="sxs-lookup"><span data-stu-id="582cd-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="582cd-113">Magazyny (Finance and Operations do Field Service)</span><span class="sxs-lookup"><span data-stu-id="582cd-113">Warehouses (Finance and Operations to Field Service)</span></span> 
- <span data-ttu-id="582cd-114">Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)</span><span class="sxs-lookup"><span data-stu-id="582cd-114">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="582cd-115">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="582cd-115">Entity set</span></span>

| <span data-ttu-id="582cd-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="582cd-116">Field Service</span></span>                      | <span data-ttu-id="582cd-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="582cd-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="582cd-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="582cd-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="582cd-119">CDS Dostępne zapasy według magazynu</span><span class="sxs-lookup"><span data-stu-id="582cd-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="582cd-120">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="582cd-120">Entity flow</span></span>
<span data-ttu-id="582cd-121">Informacje poziomu zapasów z Finance and Operations są wysyłane do Field Service dla wybranych produktów.</span><span class="sxs-lookup"><span data-stu-id="582cd-121">Inventory level information from Finance and Operation is send to Field Service for selected products.</span></span> <span data-ttu-id="582cd-122">Informacje poziomu zapasów obejmują:</span><span class="sxs-lookup"><span data-stu-id="582cd-122">The inventory level information include:</span></span> 
- <span data-ttu-id="582cd-123">Dostępna ilość (aktualnie zarejestrowana fizyczna ilość znajdująca się w magazynie)</span><span class="sxs-lookup"><span data-stu-id="582cd-123">On hand quantity (current recorded physically quantity located in the warehouse)</span></span>
- <span data-ttu-id="582cd-124">Ilość na zamówieniach (łączna ilość na zamówieniach sprzedaży)</span><span class="sxs-lookup"><span data-stu-id="582cd-124">On order quantity (total recorded quantity on order - i.e. sales orders)</span></span>
- <span data-ttu-id="582cd-125">Zamówiona ilość (łączna ilość na zamówieniach zakupu)</span><span class="sxs-lookup"><span data-stu-id="582cd-125">Ordered quantity (total recorded ordered quantity - i.e. purchase orders)</span></span>

<span data-ttu-id="582cd-126">Te informacje są rejestrowane według zwalnianych produktów dla każdego magazynu i synchronizowane w oparciu o śledzenie zmian, gdy poziomy zapasów się zmieniają.</span><span class="sxs-lookup"><span data-stu-id="582cd-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="582cd-127">W Field Service rozwiązanie integracji tworzy arkusze magazynowe dla różnicy, aby dopasować w Field Service z poziomami w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="582cd-127">In Field Service the integration solution create inventory journals for the delta, to get the levels in Field Service to match the levels in Finance and Operations.</span></span>

<span data-ttu-id="582cd-128">Finance and Operations będzie działać jako wzorzec poziomów zapasów.</span><span class="sxs-lookup"><span data-stu-id="582cd-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="582cd-129">Dlatego ważne jest skonfigurowanie integracji dla zleceń, przeniesień i korekt z Field Service do Finance and Operations, jeśli ta funkcja jest używana w Field Service, razem z synchronizacją poziomów zapasów z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="582cd-129">So it is important to setup integration for workorders, transfers and adjustments from Field Service to Finance and Operations if the this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="582cd-130">Produkty i magazyny, w których poziomy zapasów są wzorowane na Finance and Operations mogą być kontrolowane za pomocą funkcji Zaawansowane zapytania i filtrowanie (Zapytanie zaawansowane).</span><span class="sxs-lookup"><span data-stu-id="582cd-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

<span data-ttu-id="582cd-131">Uwaga: Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem Obsługiwane zewnętrznie = Nie), a następnie mapowania ich na jeden magazyn w Finance and Operations z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="582cd-131">Note: It is possible to create multiple warehouses in Field Services (with Is Externally Maintained = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="582cd-132">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="582cd-132">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="582cd-133">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="582cd-133">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="582cd-134">Zobacz dodatkowe informacje w tematach Synchronizowanie korekt zapasów z Field Service do Finance and Operations oraz Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="582cd-134">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="582cd-135">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="582cd-135">Field Service CRM solution</span></span>
<span data-ttu-id="582cd-136">Jednostka magazynowa Produkt zewnętrzny jest nową jednostką, która jest używana tylko do integracji w systemach zaplecza.</span><span class="sxs-lookup"><span data-stu-id="582cd-136">The External Product Inventory entity is a new entity that’s only used for backend in the integration.</span></span> <span data-ttu-id="582cd-137">Odbieranych wartości poziomu zapasów z Finance and Operations w ramach integracji, a następnie przekształca te wartości na ręczne arkusze magazynowe, które następnie zmieniają produkty zapasów w magazynie.</span><span class="sxs-lookup"><span data-stu-id="582cd-137">It receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manuel Inventory journals, that then changes the Inventory Products on the Warehouse.</span></span> 

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="582cd-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="582cd-138">Prerequisites and mapping setup</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="582cd-139">W projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="582cd-139">In the Data Integration project</span></span>
<span data-ttu-id="582cd-140">Zastosuj filtry za pomocą funkcji Zaawansowane zapytanie i filtrowanie, aby tylko żądane produkty i magazyny wysyłały informacji o poziomie zapasów z Finance and Operations do Field Service.</span><span class="sxs-lookup"><span data-stu-id="582cd-140">Apply filters with the Advanced  Query and Filtering to control that only desired products and warehouses send inventory level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="582cd-141">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="582cd-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a><span data-ttu-id="582cd-142">Zapasy produktu (Finance and Operations do Field Service): Zapasy produktu</span><span class="sxs-lookup"><span data-stu-id="582cd-142">Product Inventory (Finance and Operations to Field Service): Product inventory</span></span>

<span data-ttu-id="582cd-143">[![Mapowanie szablonu w integracji danych](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="582cd-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>

