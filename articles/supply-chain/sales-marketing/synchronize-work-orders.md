---
title: Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2019
ms.locfileid: "836449"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="ed397-103">Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ed397-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ed397-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ed397-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="ed397-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="ed397-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="ed397-106">Używany szablon **Zlecenia z projektem (z Field Service do Fin and Ops)** jest oparty na szablonie **Zlecenia (z Field Service do Fin Ops)**.</span><span class="sxs-lookup"><span data-stu-id="ed397-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="ed397-107">Więcej informacji znajduje się w temacie [Synchronizowanie zleceń pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)</span><span class="sxs-lookup"><span data-stu-id="ed397-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="ed397-108">W tym temacie opisano tylko różnice między dwoma szablonami:</span><span class="sxs-lookup"><span data-stu-id="ed397-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="ed397-109">**Zlecenia z projektem (z Field Service do Finance and Operations)**</span><span class="sxs-lookup"><span data-stu-id="ed397-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="ed397-110">**Zlecenia (z Field Service do Finance and Operations)**</span><span class="sxs-lookup"><span data-stu-id="ed397-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="ed397-111">Główna różnica polega na tym, że ten szablon obejmuje mapowanie numeru projektu przypisanego do zlecenia w aplikacji Field Service, który zapewnia, że zlecenie sprzedaży utworzone w aplikacji Finance and Operations zawiera numer projektu i że fakturowanie może zostać wykonane w odniesieniu do powiązanego projektu.</span><span class="sxs-lookup"><span data-stu-id="ed397-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="ed397-112">Poza tym szablon używa Zaawansowanego zapytania i filtrowania.</span><span class="sxs-lookup"><span data-stu-id="ed397-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ed397-113">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="ed397-113">Templates and tasks</span></span>

<span data-ttu-id="ed397-114">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="ed397-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="ed397-115">Zlecenia z projektem (z Field Service do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="ed397-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="ed397-116">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="ed397-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="ed397-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="ed397-117">WorkOrderHeader</span></span>
- <span data-ttu-id="ed397-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="ed397-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="ed397-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="ed397-119">WorkOrderProduct</span></span>
- <span data-ttu-id="ed397-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="ed397-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="ed397-121">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="ed397-121">Field Service CRM solution</span></span>
<span data-ttu-id="ed397-122">Pole **Projekt zewnętrzny** zostało dodane do jednostka Zlecenie.</span><span class="sxs-lookup"><span data-stu-id="ed397-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="ed397-123">To pole jest wyszukiwaniem i zakupem, które wyzwalają Zlecenie z projektem; następnie Zlecenie sprzedaży jest łączone z Projektem w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ed397-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="ed397-124">Gdy **Stan systemu** zmieni się z Otwarte — w toku (690,970,000) na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.</span><span class="sxs-lookup"><span data-stu-id="ed397-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ed397-125">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="ed397-125">Template mapping in Data integration</span></span>

<span data-ttu-id="ed397-126">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="ed397-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="ed397-127">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="ed397-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="ed397-128">[![Mapowanie szablonu w integracji danych](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="ed397-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="ed397-129">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="ed397-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="ed397-130">[![Mapowanie szablonu w integracji danych](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="ed397-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="ed397-131">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="ed397-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="ed397-132">[![Mapowanie szablonu w integracji danych](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="ed397-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="ed397-133">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="ed397-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="ed397-134">[![Mapowanie szablonu w integracji danych](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="ed397-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
