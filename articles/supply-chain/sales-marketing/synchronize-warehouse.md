---
title: Synchronizowanie magazynów między aplikacjami Finance and Operations i Field Service
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: ae99624076eecda2969961d0361d1adf42c6c5f3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835677"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="66ddd-103">Synchronizowanie magazynów z rozwiązania Finance and Operations do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="66ddd-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="66ddd-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="66ddd-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="66ddd-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="66ddd-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="66ddd-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="66ddd-106">Templates and tasks</span></span>
<span data-ttu-id="66ddd-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="66ddd-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="66ddd-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="66ddd-108">**Template in Data integration**</span></span>
- <span data-ttu-id="66ddd-109">Magazyny (z Fin and Ops do Field Service)</span><span class="sxs-lookup"><span data-stu-id="66ddd-109">Warehouses (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="66ddd-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="66ddd-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="66ddd-111">Magazyn</span><span class="sxs-lookup"><span data-stu-id="66ddd-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="66ddd-112">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="66ddd-112">Entity set</span></span>
| <span data-ttu-id="66ddd-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="66ddd-113">Field Service</span></span>    | <span data-ttu-id="66ddd-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="66ddd-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="66ddd-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="66ddd-115">msdyn_warehouses</span></span> | <span data-ttu-id="66ddd-116">Magazyny</span><span class="sxs-lookup"><span data-stu-id="66ddd-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="66ddd-117">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="66ddd-117">Entity flow</span></span>
<span data-ttu-id="66ddd-118">Magazyny tworzone i obsługiwane w Finance and Operations mogą być synchronizowane z Field Service za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="66ddd-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="66ddd-119">Żądane magazyny synchronizowane z Field Service mogą kontrolowane za pomocą zaawansowanych zapytań i filtrów w projekcie.</span><span class="sxs-lookup"><span data-stu-id="66ddd-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="66ddd-120">Magazyny synchronizowane z Finance and Operations są tworzone w Field Service z polem **Obsługiwane zewnętrznie** ustawionym na **Tak**, a rekord jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="66ddd-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="66ddd-121">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="66ddd-121">Field Service CRM solution</span></span>
<span data-ttu-id="66ddd-122">Aby umożliwić integrację między programami Field Service i Finance and Operations, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service.</span><span class="sxs-lookup"><span data-stu-id="66ddd-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="66ddd-123">W rozwiązaniu pole **Obsługiwane zewnętrznie** zostało dodane do jednostki **Magazyn (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="66ddd-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="66ddd-124">To pomaga w identyfikacji, czy magazyn jest obsługiwany z Finance and Operations czy tylko istnieje w Field Service.</span><span class="sxs-lookup"><span data-stu-id="66ddd-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="66ddd-125">Ustawienia tego pól obejmują:</span><span class="sxs-lookup"><span data-stu-id="66ddd-125">The settings for this field include:</span></span>
- <span data-ttu-id="66ddd-126">**Tak** — magazyn pochodził z rozwiązania Finance and Operations i nie będzie można edytować w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="66ddd-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="66ddd-127">**Nie** — magazyn został wprowadzony bezpośrednio w Field Service jest obsługiwany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="66ddd-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="66ddd-128">Pole **Obsługiwane zewnętrznie** pomaga kontrolować synchronizację poziomów zapasów, korekty, przeniesienia i wykorzystanie w zleceniach.</span><span class="sxs-lookup"><span data-stu-id="66ddd-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="66ddd-129">Tylko magazyny z polem **Obsługiwane zewnętrznie** ustawionym na **Tak** mogą być używane do synchronizowania bezpośrednio z tym samym magazynem w innym systemie.</span><span class="sxs-lookup"><span data-stu-id="66ddd-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="66ddd-130">Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie = Nie**), a następnie mapowania ich na jeden magazyn w Finance and Operations z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="66ddd-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="66ddd-131">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66ddd-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="66ddd-132">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66ddd-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="66ddd-133">Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="66ddd-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="66ddd-134">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="66ddd-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="66ddd-135">Projekt integracji danych</span><span class="sxs-lookup"><span data-stu-id="66ddd-135">Data Integration project</span></span>
<span data-ttu-id="66ddd-136">Przed synchronizacją magazynów należy upewnić się, że funkcja zaawansowanych zapytań i filtrów w projekcie obejmuje tylko magazyny, które chcesz przenieść z Finance and Operations do Field Service.</span><span class="sxs-lookup"><span data-stu-id="66ddd-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="66ddd-137">Należy zwrócić uwagę, że konieczny będzie magazyn w Field Service, aby zastosować go do zleceń, korekt i przeniesień.</span><span class="sxs-lookup"><span data-stu-id="66ddd-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="66ddd-138">Aby mieć pewność, że istnieje wartość **Klucz integracji** dla jednostki **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="66ddd-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="66ddd-139">Przejdź do narzędzia Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="66ddd-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="66ddd-140">Wybierz kartę **Zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="66ddd-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="66ddd-141">Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="66ddd-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="66ddd-142">Wybierz kartę **Klucz integracji**.</span><span class="sxs-lookup"><span data-stu-id="66ddd-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="66ddd-143">Znajdź jednostkę msdyn_warehouses i sprawdź, czy został dodany klucz **msdyn_name (name)**.</span><span class="sxs-lookup"><span data-stu-id="66ddd-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="66ddd-144">Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.</span><span class="sxs-lookup"><span data-stu-id="66ddd-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="66ddd-145">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="66ddd-145">Template mapping in Data integration</span></span>

<span data-ttu-id="66ddd-146">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="66ddd-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a><span data-ttu-id="66ddd-147">Magazyny (z Fin and Ops do Field Service): magazyny</span><span class="sxs-lookup"><span data-stu-id="66ddd-147">Warehouses (Fin and Ops to Field Service): Warehouse</span></span>

<span data-ttu-id="66ddd-148">[![Mapowanie szablonu w integracji danych](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="66ddd-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
