---
title: Synchronizowanie magazynów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b4503b0fea259d30e32dffe636bc0a7ac5528033
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807783"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="66dc7-103">Synchronizowanie magazynów z rozwiązania Supply Chain Management do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="66dc7-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="66dc7-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="66dc7-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="66dc7-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="66dc7-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="66dc7-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="66dc7-106">Templates and tasks</span></span>
<span data-ttu-id="66dc7-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania magazynów między rozwiązaniami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="66dc7-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="66dc7-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="66dc7-108">**Template in Data integration**</span></span>
- <span data-ttu-id="66dc7-109">Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service)</span><span class="sxs-lookup"><span data-stu-id="66dc7-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="66dc7-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="66dc7-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="66dc7-111">Magazyn</span><span class="sxs-lookup"><span data-stu-id="66dc7-111">Warehouse</span></span>

## <a name="table-set"></a><span data-ttu-id="66dc7-112">Zestaw tabel</span><span class="sxs-lookup"><span data-stu-id="66dc7-112">Table set</span></span>
| <span data-ttu-id="66dc7-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="66dc7-113">Field Service</span></span>    | <span data-ttu-id="66dc7-114">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="66dc7-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="66dc7-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="66dc7-115">msdyn_warehouses</span></span> | <span data-ttu-id="66dc7-116">Magazyny</span><span class="sxs-lookup"><span data-stu-id="66dc7-116">Warehouses</span></span>                             |

## <a name="table-flow"></a><span data-ttu-id="66dc7-117">Przepływ tabeli</span><span class="sxs-lookup"><span data-stu-id="66dc7-117">Table flow</span></span>
<span data-ttu-id="66dc7-118">Magazyny tworzone i obsługiwane w aplikacji Supply Chain Management mogą być synchronizowane z Field Service za pomocą projektu integracji danych realizowanego w usłudze Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="66dc7-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="66dc7-119">Żądane magazyny synchronizowane z Field Service mogą kontrolowane za pomocą zaawansowanych zapytań i filtrów w projekcie.</span><span class="sxs-lookup"><span data-stu-id="66dc7-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="66dc7-120">Magazyny synchronizowane z Supply Chain Management są tworzone w Field Service z kolumną **Obsługiwane zewnętrznie** ustawioną na **Tak**, a rekord jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="66dc7-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** column set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="66dc7-121">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="66dc7-121">Field Service CRM solution</span></span>
<span data-ttu-id="66dc7-122">Aby umożliwić integrację między programami Field Service i Supply Chain Management, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service.</span><span class="sxs-lookup"><span data-stu-id="66dc7-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="66dc7-123">W rozwiązaniu kolumna **Obsługiwane zewnętrznie** została dodane do tabeli **Magazyn (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="66dc7-123">In the solution, the **Is Maintained Externally** column has been added to the **Warehouse (msdyn_warehouses)** table.</span></span> <span data-ttu-id="66dc7-124">Kolumna ta pomaga w identyfikacji, czy magazyn jest obsługiwany z Supply Chain Management, czy tylko istnieje w Field Service.</span><span class="sxs-lookup"><span data-stu-id="66dc7-124">This column helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="66dc7-125">Ustawienia tej kolumny obejmują:</span><span class="sxs-lookup"><span data-stu-id="66dc7-125">The settings for this column include:</span></span>
- <span data-ttu-id="66dc7-126">**Tak** — Magazyn pochodził z rozwiązania Supply Chain Management i nie będzie można edytować w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="66dc7-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="66dc7-127">**Nie** — magazyn został wprowadzony bezpośrednio w Field Service jest obsługiwany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="66dc7-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="66dc7-128">Kolumna **Obsługiwane zewnętrznie** pomaga kontrolować synchronizację poziomów zapasów, korekty, przeniesienia i wykorzystanie w zleceniach.</span><span class="sxs-lookup"><span data-stu-id="66dc7-128">The **Is Externally Maintained** column helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="66dc7-129">Tylko magazyny z polem **Obsługiwane zewnętrznie** ustawionym na **Tak** mogą być używane do synchronizowania bezpośrednio z tym samym magazynem w innym systemie.</span><span class="sxs-lookup"><span data-stu-id="66dc7-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="66dc7-130">Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie** = Nie), a następnie mapowania ich na jeden magazyn z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="66dc7-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="66dc7-131">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="66dc7-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="66dc7-132">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="66dc7-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="66dc7-133">Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="66dc7-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="66dc7-134">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="66dc7-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="66dc7-135">Projekt integracji danych</span><span class="sxs-lookup"><span data-stu-id="66dc7-135">Data Integration project</span></span>
<span data-ttu-id="66dc7-136">Przed synchronizacją magazynów należy upewnić się, że funkcja zaawansowanych zapytań i filtrów w projekcie obejmuje tylko magazyny, które chcesz przenieść z Supply Chain Management do Field Service.</span><span class="sxs-lookup"><span data-stu-id="66dc7-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="66dc7-137">Należy zwrócić uwagę, że konieczny będzie magazyn w Field Service, aby zastosować go do zleceń, korekt i przeniesień.</span><span class="sxs-lookup"><span data-stu-id="66dc7-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="66dc7-138">Aby mieć pewność, że istnieje wartość **Klucz integracji** dla jednostki **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="66dc7-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="66dc7-139">Przejdź do narzędzia Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="66dc7-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="66dc7-140">Wybierz kartę **Zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="66dc7-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="66dc7-141">Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="66dc7-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="66dc7-142">Wybierz kartę **Klucz integracji**.</span><span class="sxs-lookup"><span data-stu-id="66dc7-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="66dc7-143">Znajdź jednostkę msdyn_warehouses i sprawdź, czy został dodany klucz **msdyn_name (name)**.</span><span class="sxs-lookup"><span data-stu-id="66dc7-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="66dc7-144">Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.</span><span class="sxs-lookup"><span data-stu-id="66dc7-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="66dc7-145">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="66dc7-145">Template mapping in Data integration</span></span>

<span data-ttu-id="66dc7-146">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="66dc7-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="66dc7-147">Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service): Magazyn</span><span class="sxs-lookup"><span data-stu-id="66dc7-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="66dc7-148">[![Mapowanie szablonu w integracji danych](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="66dc7-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]