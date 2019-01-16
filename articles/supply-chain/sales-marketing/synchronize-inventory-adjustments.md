---
title: "Synchronizowanie przeniesień i korekt zapasów z Field Service do Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="9908d-103">Synchronizowanie korekt zapasów z Field Service do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9908d-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9908d-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="9908d-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="9908d-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="9908d-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9908d-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="9908d-106">Templates and tasks</span></span>
<span data-ttu-id="9908d-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania korekt przeniesień zapasów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="9908d-107">The following template and underlying tasks are used to run synchronization of inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="9908d-108">**Nazwa szablonów w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="9908d-108">**Name of the templates in Data integration:**</span></span>
- <span data-ttu-id="9908d-109">Korekta zapasów (Field Service do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="9908d-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="9908d-110">Przeniesienia zapasów (Field Service do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="9908d-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="9908d-111">**Nazwy zadań w projektach integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="9908d-111">**Names of the tasks in the Data integration projects:**</span></span>
- <span data-ttu-id="9908d-112">Korekty zapasów</span><span class="sxs-lookup"><span data-stu-id="9908d-112">Inventory Adjustments</span></span>
- <span data-ttu-id="9908d-113">Przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="9908d-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="9908d-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="9908d-114">Entity set</span></span>
| <span data-ttu-id="9908d-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="9908d-115">Field Service</span></span>                     | <span data-ttu-id="9908d-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9908d-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="9908d-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="9908d-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="9908d-118">CDS Nagłówki i wiersze arkuszy korekt zapasów</span><span class="sxs-lookup"><span data-stu-id="9908d-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="9908d-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="9908d-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="9908d-120">CDS Nagłówki i wiersze arkuszy przesunięć magazynowych</span><span class="sxs-lookup"><span data-stu-id="9908d-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="9908d-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="9908d-121">Entity flow</span></span>
<span data-ttu-id="9908d-122">Korekty i przeniesienia zapasów dokonane w Field Service będą synchronizowane w Finance and Operations, gdy **Stan księgowania** zostaje zmieniony z Utworzone na Zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="9908d-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations, once the **Post status** is changed from Created to Posted.</span></span> <span data-ttu-id="9908d-123">Gdy to się dzieje, zlecenie korekty lub przeniesienie zostanie zablokowane i stanie się tylko do odczytu, ponieważ korekty i przeniesienia mogą być księgowane w Finance and Operations i dlatego nie mogą być modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="9908d-123">When this happen the adjustment or transfer order will be locked and become read-only, as adjustments and transfers might be posted in Finance and Operations and therefor can't be modified.</span></span>
<span data-ttu-id="9908d-124">W Finance and Operations możesz ustawić zadanie wsadowe do automatycznego księgowania korekt i przenoszenia arkuszy magazynowych wygenerowanych za pomocą integracji.</span><span class="sxs-lookup"><span data-stu-id="9908d-124">In Finance and Operations you can setup a batch job to automatically post the adjustments and transfer inventory journals generated with the integration.</span></span> <span data-ttu-id="9908d-125">Zobacz wymaganie wstępne poniżej, aby uzyskać szczegółowe informacje o sposobie włączania zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="9908d-125">See prerequisite below for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="9908d-126">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="9908d-126">Field Service CRM solution</span></span> 
<span data-ttu-id="9908d-127">Pole Jednostka magazynowa zostało dodane do jednostki Produkt.</span><span class="sxs-lookup"><span data-stu-id="9908d-127">The Inventory Unit field has been added to the Product entity.</span></span> <span data-ttu-id="9908d-128">To pole jest wymagane ponieważ jednostka sprzedaży i magazynowa nie zawsze jest taka sama w Operations i dla Zapasów w magazynie w operacjach potrzebujemy jednostki magazynowej.</span><span class="sxs-lookup"><span data-stu-id="9908d-128">This field is needed since the Sales and Inventory Unit is not always the same in Operations, and for the Warehouse Inventory in operations we need the Inventory Unit.</span></span>
<span data-ttu-id="9908d-129">Po ustawieniu produktu w produkcie korekty zapasów dla korekt zapasów i przeniesień zapasów jednostka zostanie pobrana z wartości produktu w magazynie.</span><span class="sxs-lookup"><span data-stu-id="9908d-129">When you set the Product on an Inventory Adjustment Product for both Inventory Adjustments and Inventory Transfers the Unit will be fetched from the Products Inventory Product value.</span></span> <span data-ttu-id="9908d-130">Jeśli wartość zostanie znaleziona, pole Jednostka zostanie zablokowane na Produkt korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="9908d-130">If a value is found the Unit field will be locked on the Inventory Adjustment Product</span></span>

<span data-ttu-id="9908d-131">Pole Stan księgowania zostało dodane zarówno do jednostki Korekta zapasów, jak i Przeniesienie zapasów.</span><span class="sxs-lookup"><span data-stu-id="9908d-131">The Post Status field has been added to both the Inventory Adjustment entity and the Inventory Transfer entity.</span></span> <span data-ttu-id="9908d-132">To pole jest używane jako filtr podczas wysyłania korekty lub przeniesienia do Operations.</span><span class="sxs-lookup"><span data-stu-id="9908d-132">This field is used as a filter for when a adjustment or transfer is sent to Operations.</span></span> <span data-ttu-id="9908d-133">To pole jest ustawiane domyślnie na wartość Utworzono (1), a następnie nie jest wysyłane do Operations.</span><span class="sxs-lookup"><span data-stu-id="9908d-133">The field is defaulted to Created (1) and its then not sent over to Operations.</span></span> <span data-ttu-id="9908d-134">Po wprowadzeniu zmiany na Zaksięgowane (2) następuje wysłanie do operacji, ale nie możesz już zmienić niczego w opcji Korekta lub Przeniesienie anie dodawać tam nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="9908d-134">Ones you change is to Posted (2) It is sent over to operations, but you will then no longer be able to change anything in the Adjustment or Transfer or add any new lines to it.</span></span>
<span data-ttu-id="9908d-135">Pole Sekwencja numerów zostało dodane do jednostki produktu korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="9908d-135">The Number Sequence field has been added to the Inventory Adjustment Product entity.</span></span> <span data-ttu-id="9908d-136">To pole pozwala ustawić dla integracji niepowtarzalny numer, dzięki czemu integracja wie, kiedy tworzyć a kiedy aktualizować.</span><span class="sxs-lookup"><span data-stu-id="9908d-136">This field helps the integration to have a Unique number, so the integration knows when to do creates and when to do updates.</span></span> <span data-ttu-id="9908d-137">Podczas tworzenia pierwszego produktu korekty zapasów utworzy on nowy rekord w jednostce P2C AutoNumber do obsługi serii numerów i używanego prefiksu.</span><span class="sxs-lookup"><span data-stu-id="9908d-137">When you create your first Inventory Adjustment Product it will create a new record in the P2C AutoNumber entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="9908d-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="9908d-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="9908d-139">W programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9908d-139">In Finance and Operations</span></span>
<span data-ttu-id="9908d-140">Arkusze magazynowe integracji wygenerowane przez integrację mogą być automatycznie księgowane za pomocą zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="9908d-140">The integration inventory journals generated by the integration can automatically be posted with a batch job.</span></span> <span data-ttu-id="9908d-141">Tę opcję włącza się z: Zarządzanie zapasami > Zadania okresowe > Integracja z usługą CDS > Księguj arkusze magazynowe integracji</span><span class="sxs-lookup"><span data-stu-id="9908d-141">This is enabled from: Inventory management > Periodic tasks > CDS integration > Post integration inventory journals</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9908d-142">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="9908d-142">Template mapping in Data integration</span></span>

<span data-ttu-id="9908d-143">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="9908d-143">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="9908d-144">Korekta zapasów (Field Service do Finance and Operations): Korekta zapasów</span><span class="sxs-lookup"><span data-stu-id="9908d-144">Inventory Adjustment (Field Service to Finance and Operations): Inventory Adjustment</span></span>

<span data-ttu-id="9908d-145">[![Mapowanie szablonu w integracji danych](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="9908d-145">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="9908d-146">Przeniesienie zapasów (Field Service do Finance and Operations): Przeniesienie zapasów</span><span class="sxs-lookup"><span data-stu-id="9908d-146">Inventory Transfer (Field Service to Finance and Operations): Inventory Transfer</span></span>

<span data-ttu-id="9908d-147">[![Mapowanie szablonu w integracji danych](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="9908d-147">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>

