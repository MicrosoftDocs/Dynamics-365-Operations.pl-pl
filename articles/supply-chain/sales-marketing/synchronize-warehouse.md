---
title: "Synchronizowanie magazynów między aplikacjami Finance and Operations i Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="f27f5-103">Synchronizowanie magazynów między aplikacjami Finance and Operations i Field Service</span><span class="sxs-lookup"><span data-stu-id="f27f5-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f27f5-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="f27f5-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f27f5-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="f27f5-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f27f5-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="f27f5-106">Templates and tasks</span></span>
<span data-ttu-id="f27f5-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="f27f5-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f27f5-108">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="f27f5-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="f27f5-109">Magazyny (Finance and Operations do Field Service)</span><span class="sxs-lookup"><span data-stu-id="f27f5-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="f27f5-110">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="f27f5-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="f27f5-111">Magazyn</span><span class="sxs-lookup"><span data-stu-id="f27f5-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="f27f5-112">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="f27f5-112">Entity set</span></span>
| <span data-ttu-id="f27f5-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="f27f5-113">Field Service</span></span>    | <span data-ttu-id="f27f5-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f27f5-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="f27f5-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="f27f5-115">msdyn_warehouses</span></span> | <span data-ttu-id="f27f5-116">Magazyny</span><span class="sxs-lookup"><span data-stu-id="f27f5-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="f27f5-117">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="f27f5-117">Entity flow</span></span>
<span data-ttu-id="f27f5-118">Magazyny tworzone i obsługiwane w Finance and Operations mogą być synchronizowane z Field Service za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="f27f5-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="f27f5-119">Żądane magazyny synchronizowane z Field Service mogą kontrolowane za pomocą zaawansowanych zapytań i filtrów w projekcie.</span><span class="sxs-lookup"><span data-stu-id="f27f5-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="f27f5-120">Magazyny synchronizowane z Finance and Operations są tworzone w Field Service z polem Obsługiwane zewnętrznie ustawionym na Tak, a rekord jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="f27f5-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="f27f5-121">Rozwiązanie CRM Field Service Aby umożliwić integrację między programami Field Service i Finance and Operations, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service.</span><span class="sxs-lookup"><span data-stu-id="f27f5-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="f27f5-122">To rozwiązanie obejmuje następujące zmiany.</span><span class="sxs-lookup"><span data-stu-id="f27f5-122">The solution includes the following changes.</span></span>
<span data-ttu-id="f27f5-123">Pole **Obsługiwane zewnętrznie** zostało dodane do jednostki **Magazyn (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="f27f5-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="f27f5-124">To pomaga w identyfikacji, czy magazyn jest obsługiwany z operacji czy tylko istnieje w Field Service.</span><span class="sxs-lookup"><span data-stu-id="f27f5-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="f27f5-125">Tak — magazyn pochodził z rozwiązania Finance and Operations i nie będzie można edytować w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="f27f5-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="f27f5-126">Nie — magazyn został wprowadzony bezpośrednio w Field Service jest obsługiwany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="f27f5-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="f27f5-127">Pole **Obsługiwane zewnętrznie** pomaga kontrolować synchronizację poziomów zapasów, korekty, przeniesienia i wykorzystanie w zleceniach.</span><span class="sxs-lookup"><span data-stu-id="f27f5-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="f27f5-128">Tylko magazyny z polem **Obsługiwane zewnętrznie** ustawionym na Tak mogą być używane do synchronizowania bezpośrednio z tym samym magazynem w innym systemie.</span><span class="sxs-lookup"><span data-stu-id="f27f5-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="f27f5-129">Uwaga: Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie** = Nie), a następnie mapowania ich na jeden magazyn w Finance and Operations z funkcją zaawansowanych zapytań i filtrów.</span><span class="sxs-lookup"><span data-stu-id="f27f5-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="f27f5-130">Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f27f5-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="f27f5-131">W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f27f5-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="f27f5-132">Zobacz dodatkowe informacje w tematach Synchronizowanie korekt zapasów z Field Service do Finance and Operations oraz Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f27f5-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f27f5-133">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="f27f5-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="f27f5-134">W projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="f27f5-134">In the Data Integration project</span></span>
<span data-ttu-id="f27f5-135">Przed synchronizacją magazynów należy upewnić się, że funkcja zaawansowanych zapytań i filtrów w projekcie obejmuje tylko magazyny, które chcesz przenieść z Finance and Operations do Field Service.</span><span class="sxs-lookup"><span data-stu-id="f27f5-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="f27f5-136">Należy zwrócić uwagę, że konieczny będzie magazyn w Field Service, aby zastosować go do zleceń, korekt i przeniesień.</span><span class="sxs-lookup"><span data-stu-id="f27f5-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="f27f5-137">Upewnij się, istnieje wartość **Klucz integracji** dla jednostki **msdyn_warehouses**</span><span class="sxs-lookup"><span data-stu-id="f27f5-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="f27f5-138">Przejdź do narzędzia Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="f27f5-138">Go to Data Integration</span></span>
2. <span data-ttu-id="f27f5-139">Wybierz kartę **Zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="f27f5-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="f27f5-140">Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="f27f5-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="f27f5-141">Wybierz kartę **Klucz integracji**.</span><span class="sxs-lookup"><span data-stu-id="f27f5-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="f27f5-142">Znajdź jednostkę msdyn_warehouses i sprawdź, czy został dodany klucz **msdyn_name (name)**.</span><span class="sxs-lookup"><span data-stu-id="f27f5-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="f27f5-143">Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.</span><span class="sxs-lookup"><span data-stu-id="f27f5-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f27f5-144">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="f27f5-144">Template mapping in Data integration</span></span>

<span data-ttu-id="f27f5-145">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="f27f5-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="f27f5-146">Magazyny (Finance and Operations do Field Service): Magazyn</span><span class="sxs-lookup"><span data-stu-id="f27f5-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="f27f5-147">[![Mapowanie szablonu w integracji danych](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="f27f5-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

