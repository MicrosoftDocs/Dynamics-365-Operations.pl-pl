---
title: Synchronizowanie zleceń z projektem z rozwiązania Field Service do Supply Chain Management
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Dynamics 365 Field Service a Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 03/12/2019
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
ms.openlocfilehash: 3ee512c2814b45a0bf35d1bee718b1ce37867bbb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010821"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a><span data-ttu-id="21a5a-103">Synchronizowanie zleceń z projektem z rozwiązania Field Service do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="21a5a-103">Synchronize work orders with project from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="21a5a-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Dynamics 365 Field Service a Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21a5a-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Dynamics 365 Field Service to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="21a5a-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="21a5a-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="21a5a-106">Używany szablon **Zlecenia z projektem (z Field Service do Supply Chain Management)** jest oparty na szablonie **Zlecenia (z Field Service do Supply Chain Management)**.</span><span class="sxs-lookup"><span data-stu-id="21a5a-106">The used **Work Orders with Project (Field Service to Supply Chain Management)** template is based on the **Work Orders (Field Service to Supply Chain Management)** template.</span></span> <span data-ttu-id="21a5a-107">Więcej informacji znajduje się w temacie [Synchronizowanie zleceń pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)</span><span class="sxs-lookup"><span data-stu-id="21a5a-107">For more information, see [Synchronize work orders in Field Service to sales orders in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="21a5a-108">W tym temacie opisano tylko różnice między dwoma szablonami:</span><span class="sxs-lookup"><span data-stu-id="21a5a-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="21a5a-109">**Zlecenia pracy z projektem (Field Service do Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="21a5a-109">**Work Orders with Project (Field Service to Supply Chain Management)**</span></span>
- <span data-ttu-id="21a5a-110">**Zlecenia pracy (Field Service do Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="21a5a-110">**Work Orders (Field Service to Supply Chain Management)**</span></span>

<span data-ttu-id="21a5a-111">Główna różnica polega na tym, że ten szablon obejmuje mapowanie numeru projektu przypisanego do zlecenia w aplikacji Field Service, który zapewnia, że zlecenie sprzedaży utworzone w aplikacji Supply Chain Management zawiera numer projektu i że fakturowanie może zostać wykonane w odniesieniu do powiązanego projektu.</span><span class="sxs-lookup"><span data-stu-id="21a5a-111">The main difference is that this template includes mapping of the project number assigned to the Work order in Field Service, ensuring that the Sales order created in Supply Chain Management include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="21a5a-112">Poza tym szablon używa Zaawansowanego zapytania i filtrowania.</span><span class="sxs-lookup"><span data-stu-id="21a5a-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="21a5a-113">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="21a5a-113">Templates and tasks</span></span>

<span data-ttu-id="21a5a-114">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="21a5a-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="21a5a-115">Zlecenia pracy z projektem (Field Service do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="21a5a-115">Work Orders with Project (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="21a5a-116">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="21a5a-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="21a5a-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="21a5a-117">WorkOrderHeader</span></span>
- <span data-ttu-id="21a5a-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="21a5a-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="21a5a-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="21a5a-119">WorkOrderProduct</span></span>
- <span data-ttu-id="21a5a-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="21a5a-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="21a5a-121">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="21a5a-121">Field Service CRM solution</span></span>
<span data-ttu-id="21a5a-122">Pole **Projekt zewnętrzny** zostało dodane do jednostka Zlecenie.</span><span class="sxs-lookup"><span data-stu-id="21a5a-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="21a5a-123">Jest to pole wyszukiwania, więc dzięki oznaczeniu zlecenia pracy za pomocą projektu, zlecenie sprzedaży będzie połączone z projektem w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21a5a-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Supply Chain Management.</span></span> <span data-ttu-id="21a5a-124">Gdy **Stan systemu** zmieni się z Otwarte — w toku (690 970 000) na wyższy status, to pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.</span><span class="sxs-lookup"><span data-stu-id="21a5a-124">When the **System Status** changes from Open – In Progress(690,970,000) to a higher status, the **External Project** field will be locked and you can't add, remove, or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="21a5a-125">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="21a5a-125">Template mapping in Data integration</span></span>

<span data-ttu-id="21a5a-126">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="21a5a-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a><span data-ttu-id="21a5a-127">Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="21a5a-127">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeader</span></span>

<span data-ttu-id="21a5a-128">[![Mapowanie szablonu w integracji danych](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="21a5a-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a><span data-ttu-id="21a5a-129">Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="21a5a-129">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeaderProject</span></span>

<span data-ttu-id="21a5a-130">[![Mapowanie szablonu w integracji danych](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="21a5a-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a><span data-ttu-id="21a5a-131">Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="21a5a-131">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderProduct</span></span>

<span data-ttu-id="21a5a-132">[![Mapowanie szablonu w integracji danych](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="21a5a-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a><span data-ttu-id="21a5a-133">Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="21a5a-133">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderService</span></span>

<span data-ttu-id="21a5a-134">[![Mapowanie szablonu w integracji danych](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="21a5a-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
