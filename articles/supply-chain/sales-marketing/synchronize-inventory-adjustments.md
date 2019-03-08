---
title: Synchronizowanie przeniesień i korekt zapasów z Field Service do Finance and Operations
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: aa54945cea5821da163e1f6ea1747ac29b31a3ce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "308375"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="0bdb1-103">Synchronizowanie korekt zapasów z Field Service do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bdb1-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0bdb1-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="0bdb1-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="0bdb1-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="0bdb1-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="0bdb1-106">Templates and tasks</span></span>
<span data-ttu-id="0bdb1-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Field Service a programem Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="0bdb1-108">**Mapowanie szablonów w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="0bdb1-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="0bdb1-109">Korekta zapasów (Field Service do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="0bdb1-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="0bdb1-110">Przeniesienia zapasów (Field Service do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="0bdb1-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="0bdb1-111">**Zadania w projektach integracji danych**</span><span class="sxs-lookup"><span data-stu-id="0bdb1-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="0bdb1-112">Korekty zapasów</span><span class="sxs-lookup"><span data-stu-id="0bdb1-112">Inventory Adjustments</span></span>
- <span data-ttu-id="0bdb1-113">Przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="0bdb1-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="0bdb1-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="0bdb1-114">Entity set</span></span>
| <span data-ttu-id="0bdb1-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="0bdb1-115">Field Service</span></span>                     | <span data-ttu-id="0bdb1-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bdb1-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="0bdb1-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="0bdb1-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="0bdb1-118">CDS Nagłówki i wiersze arkuszy korekt zapasów</span><span class="sxs-lookup"><span data-stu-id="0bdb1-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="0bdb1-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="0bdb1-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="0bdb1-120">CDS Nagłówki i wiersze arkuszy przesunięć magazynowych</span><span class="sxs-lookup"><span data-stu-id="0bdb1-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="0bdb1-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="0bdb1-121">Entity flow</span></span>
<span data-ttu-id="0bdb1-122">Korekty i przeniesienia zapasów dokonane w Field Service będą synchronizowane w Finance and Operations, gdy **Stan księgowania** zostaje zmieniony z **Utworzone** na **Zaksięgowane**.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="0bdb1-123">Kiedy to nastąpi, zamówienie korekty lub przeniesienia zostanie zablokowane i będzie dostępne tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="0bdb1-124">Oznacza to, że korekty i przeniesienia mogą być księgowane w Finance and Operations, ale nie mogą być modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-124">This means that adjustments and transfers can be posted in Finance and Operations, but cannot be modified.</span></span> <span data-ttu-id="0bdb1-125">W Finance and Operations możesz ustawić zadanie wsadowe do automatycznego księgowania korekt i przenoszenia arkuszy magazynowych wygenerowanych za pomocą integracji.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-125">In Finance and Operations, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="0bdb1-126">Zobacz wymagania wstępne poniżej, aby uzyskać szczegółowe informacje o sposobie włączania zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="0bdb1-127">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="0bdb1-127">Field Service CRM solution</span></span> 
<span data-ttu-id="0bdb1-128">Pole **Jednostka magazynowa** zostało dodane do jednostki **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="0bdb1-129">To pole jest wymagane ponieważ jednostka sprzedaży i magazynowa nie zawsze jest taka sama w Finance and Operations i jednostka magazynowa jest wymagana dla Zapasów w magazynie w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-129">This field is needed because the Sales and Inventory unit is not always the same in Finance and Operations, and the Inventory Unit is needed for the Warehouse Inventory in Finance and Operations.</span></span>
<span data-ttu-id="0bdb1-130">Po ustawieniu produktu w produkcie korekty zapasów dla korekt zapasów i przeniesień zapasów jednostka zostanie pobrana z wartości produktu w magazynie.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="0bdb1-131">Jeśli wartość zostanie znaleziona, pole **Jednostka** zostanie zablokowane na Produkt korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="0bdb1-132">Pole **Stan księgowania** zostało dodane zarówno do jednostki **Korekta zapasów**, jak i **Przeniesienie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="0bdb1-133">To pole jest używane jako filtr podczas wysyłania korekty lub przeniesienia do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-133">This field is used as a filter when an adjustment or transfer is sent to Finance and Operations.</span></span> <span data-ttu-id="0bdb1-134">Domyślną wartością tego pola jest Utworzone (1), ale nie jest ono wysyłane do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-134">The default for this field is Created (1), however it is not sent to Finance and Operations.</span></span> <span data-ttu-id="0bdb1-135">Po zaktualizowaniu wartości Zaksięgowane (2) jest ona wysyłana do Finance and Operations ale potem nie możesz już zmienić korekty ani przeniesienia ani dodawać nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-135">When you update the value to Posted (2), it is sent to Finance and Operations, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="0bdb1-136">Pole **Sekwencja numerów** zostało dodane do jednostki **Produktu korekty zapasów**.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="0bdb1-137">To pole zapewnia, że integracja ma unikatowy numer, więc integracja może utworzyć i zaktualizować korektę.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="0bdb1-138">Podczas tworzenia pierwszego produktu korekty zapasów utworzy on nowy rekord w jednostce **P2C AutoNumber** do obsługi serii numerów i używanego prefiksu.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="0bdb1-139">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="0bdb1-139">Prerequisites and mapping setup</span></span>

### <a name="finance-and-operations"></a><span data-ttu-id="0bdb1-140">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bdb1-140">Finance and Operations</span></span>
<span data-ttu-id="0bdb1-141">Arkusze magazynowe integracji wygenerowane przez integrację mogą być automatycznie księgowane za pomocą zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="0bdb1-142">Tę opcję włącza się z: **Zarządzanie zapasami > Zadania okresowe > Integracja z usługą CDS > Księguj arkusze magazynowe integracji**.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0bdb1-143">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="0bdb1-143">Template mapping in Data integration</span></span>

<span data-ttu-id="0bdb1-144">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="0bdb1-145">Korekta zapasów (Field Service do Finance and Operations): Korekta zapasów</span><span class="sxs-lookup"><span data-stu-id="0bdb1-145">Inventory adjustment (Field Service to Finance and Operations): Inventory adjustment</span></span>

<span data-ttu-id="0bdb1-146">[![Mapowanie szablonu w integracji danych](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="0bdb1-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="0bdb1-147">Przeniesienie zapasów (Field Service do Finance and Operations): Przeniesienie zapasów</span><span class="sxs-lookup"><span data-stu-id="0bdb1-147">Inventory transfer (Field Service to Finance and Operations): Inventory transfer</span></span>

<span data-ttu-id="0bdb1-148">[![Mapowanie szablonu w integracji danych](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="0bdb1-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
