---
title: Synchronizowanie informacji poziomu zapasów między aplikacjami Finance and Operations i Field Service
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 05/07/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 6b56eb545f87c31ef30d6a897f48539068583486
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843440"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="483d7-103">Synchronizowanie informacji na poziomie zapasów z rozwiązania Finance and Operations do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="483d7-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="483d7-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="483d7-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="483d7-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="483d7-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="483d7-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="483d7-106">Templates and tasks</span></span>
<span data-ttu-id="483d7-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania poziomów dostępnych zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="483d7-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="483d7-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="483d7-108">**Template in Data integration**</span></span>
- <span data-ttu-id="483d7-109">Zapasy produktu (z Fin and Ops do Field Service)</span><span class="sxs-lookup"><span data-stu-id="483d7-109">Product Inventory (Fin and Ops to Field Service)</span></span>
  
<span data-ttu-id="483d7-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="483d7-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="483d7-111">Zapasy produktu</span><span class="sxs-lookup"><span data-stu-id="483d7-111">Product inventory</span></span>

<span data-ttu-id="483d7-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować poziomy zapasów:</span><span class="sxs-lookup"><span data-stu-id="483d7-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="483d7-113">Magazyny (z Fin and Ops do Field Service)</span><span class="sxs-lookup"><span data-stu-id="483d7-113">Warehouses (Fin and Ops to Field Service)</span></span> 
- <span data-ttu-id="483d7-114">Produkty Field Service z jednostką magazynową (Finance and Operations do Sales)</span><span class="sxs-lookup"><span data-stu-id="483d7-114">Field Service products with Inventory unit (Fin and Ops to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="483d7-115">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="483d7-115">Entity set</span></span>

| <span data-ttu-id="483d7-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="483d7-116">Field Service</span></span>                      | <span data-ttu-id="483d7-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="483d7-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="483d7-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="483d7-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="483d7-119">CDS Dostępne zapasy według magazynu</span><span class="sxs-lookup"><span data-stu-id="483d7-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="483d7-120">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="483d7-120">Entity flow</span></span>
<span data-ttu-id="483d7-121">Informacje poziomu zapasów z Finance and Operations są wysyłane do Field Service dla wybranych produktów.</span><span class="sxs-lookup"><span data-stu-id="483d7-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="483d7-122">Informacje poziomu zapasów obejmują:</span><span class="sxs-lookup"><span data-stu-id="483d7-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="483d7-123">Dostępna ilość (aktualnie zarejestrowana fizyczna ilość znajdująca się w magazynie)</span><span class="sxs-lookup"><span data-stu-id="483d7-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="483d7-124">Ilość na zamówieniach (łączna ilość na zamówieniach sprzedaży)</span><span class="sxs-lookup"><span data-stu-id="483d7-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="483d7-125">Zamówiona ilość (łączna ilość na zamówieniach zakupu)</span><span class="sxs-lookup"><span data-stu-id="483d7-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="483d7-126">Te informacje są rejestrowane według zwalnianych produktów dla każdego magazynu i synchronizowane w oparciu o śledzenie zmian, gdy poziomy zapasów się zmieniają.</span><span class="sxs-lookup"><span data-stu-id="483d7-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="483d7-127">W Field Service rozwiązanie integracji tworzy arkusze magazynowe dla różnicy, aby dopasować w Field Service z poziomami w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="483d7-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="483d7-128">Finance and Operations będzie działać jako wzorzec poziomów zapasów.</span><span class="sxs-lookup"><span data-stu-id="483d7-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="483d7-129">Dlatego ważne jest skonfigurowanie integracji dla zleceń, przeniesień i korekt z Field Service do Finance and Operations, jeśli ta funkcja jest używana w Field Service, razem z synchronizacją poziomów zapasów z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="483d7-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="483d7-130">Produkty i magazyny, w których poziomy zapasów są wzorowane na Finance and Operations mogą być kontrolowane za pomocą funkcji Zaawansowane zapytania i filtrowanie (Zapytanie zaawansowane).</span><span class="sxs-lookup"><span data-stu-id="483d7-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="483d7-131">Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie = Nie**), a następnie mapowania ich na jeden magazyn w Finance and Operations z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="483d7-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="483d7-132">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="483d7-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="483d7-133">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="483d7-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="483d7-134">Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="483d7-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="483d7-135">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="483d7-135">Field Service CRM solution</span></span>
<span data-ttu-id="483d7-136">**Jednostka magazynowa Produkt zewnętrzny** jest używana tylko do integracji w systemach zaplecza.</span><span class="sxs-lookup"><span data-stu-id="483d7-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="483d7-137">Ta jednostka odbiera wartości poziomu zapasów z Finance and Operations w ramach integracji, a następnie przekształca te wartości na ręczne arkusze magazynowe, które następnie zmieniają produkty zapasów w magazynie.</span><span class="sxs-lookup"><span data-stu-id="483d7-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="483d7-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="483d7-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="483d7-139">Integracja danych</span><span class="sxs-lookup"><span data-stu-id="483d7-139">Data integration</span></span>
<span data-ttu-id="483d7-140">Aby projekt działał, należy upewnić się, że klucz integracji został zaktualizowany dla msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="483d7-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="483d7-141">Przejdź do **Integracja danych > Zbiory połączeń**.</span><span class="sxs-lookup"><span data-stu-id="483d7-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="483d7-142">Wybierz używany zbiór połączeń.</span><span class="sxs-lookup"><span data-stu-id="483d7-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="483d7-143">Na karcie **klucz integracji** upewnij się, że następujące klucze zostały dodane do msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="483d7-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="483d7-144">msdynce_productnumber (numer produktu)</span><span class="sxs-lookup"><span data-stu-id="483d7-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="483d7-145">msdynce_warehouseid (Identyfikator magazynu)</span><span class="sxs-lookup"><span data-stu-id="483d7-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="483d7-146">Projekt integracji danych</span><span class="sxs-lookup"><span data-stu-id="483d7-146">Data integration project</span></span>
<span data-ttu-id="483d7-147">Można zastosować filtry za pomocą funkcji Zaawansowane zapytanie i filtrowanie, aby tylko niektóre produkty i magazyny wysyłały informacji o poziomie zapasów z Finance and Operations do Field Service.</span><span class="sxs-lookup"><span data-stu-id="483d7-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="483d7-148">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="483d7-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a><span data-ttu-id="483d7-149">Zapasy produktu (Finance and Operations do Field Service): Zapasy produktu</span><span class="sxs-lookup"><span data-stu-id="483d7-149">Product inventory (Fin and Ops to Field Service): Product inventory</span></span>

<span data-ttu-id="483d7-150">[![Mapowanie szablonu w integracji danych](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="483d7-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
