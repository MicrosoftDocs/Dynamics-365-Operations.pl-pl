---
title: Synchronizowanie magazynów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: b55a0b9e54eabdcdbd3f858cf3725b8fe833f65d
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653401"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="7830a-103">Synchronizowanie magazynów z rozwiązania Supply Chain Management do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="7830a-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7830a-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="7830a-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="7830a-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="7830a-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7830a-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="7830a-106">Templates and tasks</span></span>
<span data-ttu-id="7830a-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania magazynów między rozwiązaniami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="7830a-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="7830a-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="7830a-108">**Template in Data integration**</span></span>
- <span data-ttu-id="7830a-109">Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service)</span><span class="sxs-lookup"><span data-stu-id="7830a-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="7830a-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="7830a-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="7830a-111">Magazyn</span><span class="sxs-lookup"><span data-stu-id="7830a-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="7830a-112">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="7830a-112">Entity set</span></span>
| <span data-ttu-id="7830a-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="7830a-113">Field Service</span></span>    | <span data-ttu-id="7830a-114">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="7830a-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="7830a-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="7830a-115">msdyn_warehouses</span></span> | <span data-ttu-id="7830a-116">Magazyny</span><span class="sxs-lookup"><span data-stu-id="7830a-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="7830a-117">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="7830a-117">Entity flow</span></span>
<span data-ttu-id="7830a-118">Magazyny tworzone i obsługiwane w Supply Chain Management mogą być synchronizowane z Field Service za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="7830a-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="7830a-119">Żądane magazyny synchronizowane z Field Service mogą kontrolowane za pomocą zaawansowanych zapytań i filtrów w projekcie.</span><span class="sxs-lookup"><span data-stu-id="7830a-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="7830a-120">Magazyny synchronizowane z Supply Chain Management są tworzone w Field Service z polem **Obsługiwane zewnętrznie** ustawionym na **Tak**, a rekord jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="7830a-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="7830a-121">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="7830a-121">Field Service CRM solution</span></span>
<span data-ttu-id="7830a-122">Aby umożliwić integrację między programami Field Service i Supply Chain Management, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service.</span><span class="sxs-lookup"><span data-stu-id="7830a-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="7830a-123">W rozwiązaniu pole **Obsługiwane zewnętrznie** zostało dodane do jednostki **Magazyn (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="7830a-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="7830a-124">To pomaga w identyfikacji, czy magazyn jest obsługiwany z Supply Chain Management czy tylko istnieje w Field Service.</span><span class="sxs-lookup"><span data-stu-id="7830a-124">This field helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="7830a-125">Ustawienia tego pól obejmują:</span><span class="sxs-lookup"><span data-stu-id="7830a-125">The settings for this field include:</span></span>
- <span data-ttu-id="7830a-126">**Tak** — Magazyn pochodził z rozwiązania Supply Chain Management i nie będzie można edytować w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="7830a-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="7830a-127">**Nie** — magazyn został wprowadzony bezpośrednio w Field Service jest obsługiwany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="7830a-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="7830a-128">Pole **Obsługiwane zewnętrznie** pomaga kontrolować synchronizację poziomów zapasów, korekty, przeniesienia i wykorzystanie w zleceniach.</span><span class="sxs-lookup"><span data-stu-id="7830a-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="7830a-129">Tylko magazyny z polem **Obsługiwane zewnętrznie** ustawionym na **Tak** mogą być używane do synchronizowania bezpośrednio z tym samym magazynem w innym systemie.</span><span class="sxs-lookup"><span data-stu-id="7830a-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="7830a-130">Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie** = Nie), a następnie mapowania ich na jeden magazyn z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="7830a-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="7830a-131">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7830a-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="7830a-132">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7830a-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="7830a-133">Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="7830a-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="7830a-134">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="7830a-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="7830a-135">Projekt integracji danych</span><span class="sxs-lookup"><span data-stu-id="7830a-135">Data Integration project</span></span>
<span data-ttu-id="7830a-136">Przed synchronizacją magazynów należy upewnić się, że funkcja zaawansowanych zapytań i filtrów w projekcie obejmuje tylko magazyny, które chcesz przenieść z Supply Chain Management do Field Service.</span><span class="sxs-lookup"><span data-stu-id="7830a-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="7830a-137">Należy zwrócić uwagę, że konieczny będzie magazyn w Field Service, aby zastosować go do zleceń, korekt i przeniesień.</span><span class="sxs-lookup"><span data-stu-id="7830a-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="7830a-138">Aby mieć pewność, że istnieje wartość **Klucz integracji** dla jednostki **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="7830a-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="7830a-139">Przejdź do narzędzia Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="7830a-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="7830a-140">Wybierz kartę **Zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="7830a-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="7830a-141">Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="7830a-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="7830a-142">Wybierz kartę **Klucz integracji**.</span><span class="sxs-lookup"><span data-stu-id="7830a-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="7830a-143">Znajdź jednostkę msdyn_warehouses i sprawdź, czy został dodany klucz **msdyn_name (name)**.</span><span class="sxs-lookup"><span data-stu-id="7830a-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="7830a-144">Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.</span><span class="sxs-lookup"><span data-stu-id="7830a-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7830a-145">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="7830a-145">Template mapping in Data integration</span></span>

<span data-ttu-id="7830a-146">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="7830a-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="7830a-147">Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service): Magazyn</span><span class="sxs-lookup"><span data-stu-id="7830a-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="7830a-148">[![Mapowanie szablonu w integracji danych](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="7830a-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
