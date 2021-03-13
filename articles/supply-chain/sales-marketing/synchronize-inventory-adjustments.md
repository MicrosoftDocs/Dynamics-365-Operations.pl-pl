---
title: Synchronizowanie przesunięć magazynowych i korekt z rozwiązania Field Service do rozwiązania Supply Chain Management
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: a598f0356034a22ee7fc0902360b8862a1944558
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010979"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="bc6c8-103">Synchronizowanie przesunięć magazynowych i korekt z rozwiązania Field Service do rozwiązania Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bc6c8-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bc6c8-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="bc6c8-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="bc6c8-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="bc6c8-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="bc6c8-106">Templates and tasks</span></span>
<span data-ttu-id="bc6c8-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania stanu i przeniesień dostepnych zasobów między rozwiązaniami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="bc6c8-108">**Mapowanie szablonów w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="bc6c8-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="bc6c8-109">Korekta zapasów (rozwiązanie Field Service do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="bc6c8-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="bc6c8-110">Przeniesienia zapasów (rozwiązanie Field Service do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="bc6c8-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="bc6c8-111">**Zadania w projektach integracji danych**</span><span class="sxs-lookup"><span data-stu-id="bc6c8-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="bc6c8-112">Korekty zapasów</span><span class="sxs-lookup"><span data-stu-id="bc6c8-112">Inventory Adjustments</span></span>
- <span data-ttu-id="bc6c8-113">Przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="bc6c8-113">Inventory Transfers</span></span>

## <a name="table-set"></a><span data-ttu-id="bc6c8-114">Zestaw tabel</span><span class="sxs-lookup"><span data-stu-id="bc6c8-114">Table set</span></span>
| <span data-ttu-id="bc6c8-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="bc6c8-115">Field Service</span></span>                     | <span data-ttu-id="bc6c8-116">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="bc6c8-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="bc6c8-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="bc6c8-117">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="bc6c8-118">Nagłówki i wiersze arkuszy korekt zapasów w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="bc6c8-118">Dataverse Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="bc6c8-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="bc6c8-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="bc6c8-120">Nagłówki i wiersze arkuszy przesunięć magazynowych w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="bc6c8-120">Dataverse inventory transfer journal headers and lines</span></span>   |

## <a name="table-flow"></a><span data-ttu-id="bc6c8-121">Przepływ tabeli</span><span class="sxs-lookup"><span data-stu-id="bc6c8-121">Table flow</span></span>
<span data-ttu-id="bc6c8-122">Korekty i przeniesienia zapasów dokonane w Field Service będą synchronizowane w Supply Chain Management, gdy **Stan księgowania** zostaje zmieniony z **Utworzone** na **Zaksięgowane**.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="bc6c8-123">Kiedy to nastąpi, zamówienie korekty lub przeniesienia zostanie zablokowane i będzie dostępne tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="bc6c8-124">Oznacza to, że korekty i przeniesienia mogą być księgowane w Supply Chain Management, ale nie mogą być modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="bc6c8-125">W Supply Chain Management możesz ustawić zadanie wsadowe do automatycznego księgowania korekt i przenoszenia arkuszy magazynowych wygenerowanych za pomocą integracji.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="bc6c8-126">Zobacz wymagania wstępne poniżej, aby uzyskać szczegółowe informacje o sposobie włączania zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="bc6c8-127">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="bc6c8-127">Field Service CRM solution</span></span> 
<span data-ttu-id="bc6c8-128">Kolumna **Jednostka magazynowa** została dodana do tabeli **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-128">The **Inventory unit** column has been added to the **Product** table.</span></span> <span data-ttu-id="bc6c8-129">Ta kolumna jest wymagana, ponieważ jednostka sprzedaży i magazynowa nie zawsze jest taka sama w Supply Chain Management i jednostka magazynowa jest wymagana dla Zapasów w magazynie w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-129">This column is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="bc6c8-130">Po ustawieniu produktu w produkcie korekty zapasów dla korekt zapasów i przeniesień zapasów jednostka zostanie pobrana z wartości produktu w magazynie.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="bc6c8-131">Jeśli wartość zostanie znaleziona, kolumna **Jednostka** zostanie zablokowana na Produkt korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-131">If a value is found, the **Unit** column will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="bc6c8-132">Kolumna **Stan księgowania** została dodana zarówno do tabeli **Korekta zapasów**, jak i tabeli **Przeniesienie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-132">The **Post status** column has been added to both the **Inventory adjustment** table and the **Inventory transfer** table.</span></span> <span data-ttu-id="bc6c8-133">Ta kolumna jest używana jako filtr podczas wysyłania korekty lub przeniesienia do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-133">This column is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="bc6c8-134">Domyślną wartością tej kolumny jest Utworzone (1), ale nie jest ono wysyłane do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-134">The default for this column is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="bc6c8-135">Po zaktualizowaniu wartości Zaksięgowane (2) jest ona wysyłana do Supply Chain Management ale potem nie możesz już zmienić korekty ani przeniesienia ani dodawać nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="bc6c8-136">Kolumna **Sekwencja numerów** została dodana do tabeli **Produktu korekty zapasów**.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-136">The **Number sequence** column has been added to the **Inventory adjustment product** table.</span></span> <span data-ttu-id="bc6c8-137">Ta kolumna zapewnia, że integracja ma unikatowy numer, więc integracja może utworzyć i zaktualizować korektę.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-137">This column ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="bc6c8-138">Podczas tworzenia pierwszego produktu korekty zapasów utworzy on nowy rekord w tabeli **P2C AutoNumber** do obsługi serii numerów i używanego prefiksu.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** table to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="bc6c8-139">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="bc6c8-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="bc6c8-140">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="bc6c8-140">Supply Chain Management</span></span>
<span data-ttu-id="bc6c8-141">Arkusze magazynowe integracji wygenerowane przez integrację mogą być automatycznie księgowane za pomocą zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="bc6c8-142">Tę opcję włącza się z: **Zarządzanie zapasami > Zadania okresowe > Integracja z usługą Dataverse > Księguj arkusze magazynowe integracji**.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-142">This is enabled from **Inventory management > Periodic tasks > Dataverse integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="bc6c8-143">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="bc6c8-143">Template mapping in Data integration</span></span>

<span data-ttu-id="bc6c8-144">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="bc6c8-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="bc6c8-145">Korekta zapasów (z rozwiązania Field Service do Supply Chain Management): Korekta zapasów</span><span class="sxs-lookup"><span data-stu-id="bc6c8-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="bc6c8-146">[![Mapowanie szablonu w integracji danych](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="bc6c8-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="bc6c8-147">Przeniesienie zapasów (z rozwiązania Field Service do Supply Chain Management): Przeniesienie zapasów</span><span class="sxs-lookup"><span data-stu-id="bc6c8-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="bc6c8-148">[![Mapowanie szablonu w integracji danych](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="bc6c8-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
