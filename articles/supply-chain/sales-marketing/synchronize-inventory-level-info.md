---
title: Synchronizowanie informacji na poziomie zapasów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
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
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215914"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="9d973-103">Synchronizowanie informacji na poziomie zapasów z rozwiązania Supply Chain Management do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="9d973-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9d973-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="9d973-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="9d973-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="9d973-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9d973-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="9d973-106">Templates and tasks</span></span>
<span data-ttu-id="9d973-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania stanu dostepnych zasobów między rozwiązaniami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="9d973-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="9d973-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="9d973-108">**Template in Data integration**</span></span>
- <span data-ttu-id="9d973-109">Zasoby produktu (rozwiązanie Supply Chain Management do rozwiązania Field Service)</span><span class="sxs-lookup"><span data-stu-id="9d973-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="9d973-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="9d973-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="9d973-111">Zapasy produktu</span><span class="sxs-lookup"><span data-stu-id="9d973-111">Product inventory</span></span>

<span data-ttu-id="9d973-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować poziomy zapasów:</span><span class="sxs-lookup"><span data-stu-id="9d973-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="9d973-113">Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service)</span><span class="sxs-lookup"><span data-stu-id="9d973-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="9d973-114">Synchronizowanie produktów Field Service z jednostką magazynową (z rozwiązania Supply Chain Management do rozwiązania Sales)</span><span class="sxs-lookup"><span data-stu-id="9d973-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="9d973-115">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="9d973-115">Entity set</span></span>

| <span data-ttu-id="9d973-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="9d973-116">Field Service</span></span>                      | <span data-ttu-id="9d973-117">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="9d973-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="9d973-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="9d973-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="9d973-119">CDS Dostępne zapasy według magazynu</span><span class="sxs-lookup"><span data-stu-id="9d973-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="9d973-120">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="9d973-120">Entity flow</span></span>
<span data-ttu-id="9d973-121">Informacje poziomu zapasów z Finance and Operations są wysyłane do Field Service dla wybranych produktów.</span><span class="sxs-lookup"><span data-stu-id="9d973-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="9d973-122">Informacje poziomu zapasów obejmują:</span><span class="sxs-lookup"><span data-stu-id="9d973-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="9d973-123">Dostępna ilość (aktualnie zarejestrowana fizyczna ilość znajdująca się w magazynie)</span><span class="sxs-lookup"><span data-stu-id="9d973-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="9d973-124">Ilość na zamówieniach (łączna ilość na zamówieniach sprzedaży)</span><span class="sxs-lookup"><span data-stu-id="9d973-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="9d973-125">Zamówiona ilość (łączna ilość na zamówieniach zakupu)</span><span class="sxs-lookup"><span data-stu-id="9d973-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="9d973-126">Te informacje są rejestrowane według zwalnianych produktów dla każdego magazynu i synchronizowane w oparciu o śledzenie zmian, gdy poziomy zapasów się zmieniają.</span><span class="sxs-lookup"><span data-stu-id="9d973-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="9d973-127">W Field Service rozwiązanie integracji tworzy arkusze magazynowe dla różnicy, aby dopasować w Field Service z poziomami w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9d973-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="9d973-128">Supply Chain Management będzie działać jako wzorzec poziomów zapasów.</span><span class="sxs-lookup"><span data-stu-id="9d973-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="9d973-129">Dlatego ważne jest skonfigurowanie integracji dla zleceń, przeniesień i korekt z Field Service do Supply Chain Management, jeśli ta funkcja jest używana w Field Service, razem z synchronizacją poziomów zapasów z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9d973-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="9d973-130">Produkty i magazyny, w których poziomy zapasów są wzorowane na Supply Chain Management mogą być kontrolowane za pomocą funkcji Zaawansowane zapytania i filtrowanie (Zapytanie zaawansowane).</span><span class="sxs-lookup"><span data-stu-id="9d973-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="9d973-131">Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie = Nie**), a następnie mapowania ich na jeden magazyn w Supply Chain Management z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="9d973-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="9d973-132">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9d973-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="9d973-133">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9d973-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="9d973-134">Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="9d973-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="9d973-135">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="9d973-135">Field Service CRM solution</span></span>
<span data-ttu-id="9d973-136">**Jednostka magazynowa Produkt zewnętrzny** jest używana tylko do integracji w systemach zaplecza.</span><span class="sxs-lookup"><span data-stu-id="9d973-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="9d973-137">Ta jednostka odbiera wartości poziomu zapasów z Supply Chain Management w ramach integracji, a następnie przekształca te wartości na ręczne arkusze magazynowe, które następnie zmieniają produkty zapasów w magazynie.</span><span class="sxs-lookup"><span data-stu-id="9d973-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="9d973-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="9d973-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="9d973-139">Integracja danych</span><span class="sxs-lookup"><span data-stu-id="9d973-139">Data integration</span></span>
<span data-ttu-id="9d973-140">Aby projekt działał, należy upewnić się, że klucz integracji został zaktualizowany dla msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="9d973-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="9d973-141">Przejdź do **Integracja danych > Zbiory połączeń**.</span><span class="sxs-lookup"><span data-stu-id="9d973-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="9d973-142">Wybierz używany zbiór połączeń.</span><span class="sxs-lookup"><span data-stu-id="9d973-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="9d973-143">Na karcie **klucz integracji** upewnij się, że następujące klucze zostały dodane do msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="9d973-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="9d973-144">msdynce_productnumber (numer produktu)</span><span class="sxs-lookup"><span data-stu-id="9d973-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="9d973-145">msdynce_warehouseid (Identyfikator magazynu)</span><span class="sxs-lookup"><span data-stu-id="9d973-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="9d973-146">Projekt integracji danych</span><span class="sxs-lookup"><span data-stu-id="9d973-146">Data integration project</span></span>
<span data-ttu-id="9d973-147">Można zastosować filtry za pomocą funkcji Zaawansowane zapytanie i filtrowanie, aby tylko niektóre produkty i magazyny wysyłały informacji o poziomie zapasów z Supply Chain Management do Field Service.</span><span class="sxs-lookup"><span data-stu-id="9d973-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9d973-148">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="9d973-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="9d973-149">Zapasy produkt (z rozwiązania Supply Chain Management do rozwiązania Field Service): Zapasy produktu</span><span class="sxs-lookup"><span data-stu-id="9d973-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="9d973-150">[![Mapowanie szablonu w integracji danych](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="9d973-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
