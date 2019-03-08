---
title: Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "329857"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="a48c1-103">Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a48c1-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a48c1-104">Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a48c1-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="a48c1-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="a48c1-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="a48c1-106">Używany szablon **Produkty programu Field Service (z Finance and Operations do Field Service)** jest oparty na szablonie **Produkty (z Finance and Operations do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="a48c1-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="a48c1-107">Aby uzyskać więcej informacji, zobacz [Produkty (z rozwiązania Finance and Operations do rozwiązania Sales) – bezpośrednio](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="a48c1-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="a48c1-108">Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Finance and Operations do Field Service)** i **Produkty Field Service (z Finance and Operations do Field Service) — bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="a48c1-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="a48c1-109">Główna różnica polega na tym, że ten szablon obejmuje mapowanie numeru projektu przypisanego do zlecenia w aplikacji Field Service, który zapewnia, że zlecenie sprzedaży utworzone w aplikacji Finance and Operations zawiera numer projektu i że fakturowanie może zostać wykonane w odniesieniu do powiązanego projektu.</span><span class="sxs-lookup"><span data-stu-id="a48c1-109">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="a48c1-110">Poza tym szablon używa Zaawansowanego zapytania i filtrowania.</span><span class="sxs-lookup"><span data-stu-id="a48c1-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a48c1-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="a48c1-111">Templates and tasks</span></span>

<span data-ttu-id="a48c1-112">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="a48c1-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="a48c1-113">Zlecenia z projektem (z Field Service do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="a48c1-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="a48c1-114">**Nazwa zadania w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="a48c1-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="a48c1-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="a48c1-115">WorkOrderHeader</span></span>
- <span data-ttu-id="a48c1-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="a48c1-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="a48c1-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="a48c1-117">WorkOrderProduct</span></span>
- <span data-ttu-id="a48c1-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="a48c1-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="a48c1-119">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="a48c1-119">Field Service CRM solution</span></span>
<span data-ttu-id="a48c1-120">Pole **Projekt zewnętrzny** zostało dodane do jednostka Zlecenie.</span><span class="sxs-lookup"><span data-stu-id="a48c1-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="a48c1-121">To pole jest wyszukiwaniem i zakupem, które wyzwalają Zlecenie z projektem; następnie Zlecenie sprzedaży jest łączone z Projektem w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a48c1-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="a48c1-122">Gdy **Stan systemu** zmieni się z Otwarte — w toku (690,970,000) na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.</span><span class="sxs-lookup"><span data-stu-id="a48c1-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a48c1-123">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="a48c1-123">Template mapping in Data integration</span></span>

<span data-ttu-id="a48c1-124">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="a48c1-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="a48c1-125">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="a48c1-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="a48c1-126">[![Mapowanie szablonu w integracji danych](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="a48c1-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="a48c1-127">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="a48c1-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="a48c1-128">[![Mapowanie szablonu w integracji danych](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="a48c1-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="a48c1-129">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="a48c1-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="a48c1-130">[![Mapowanie szablonu w integracji danych](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="a48c1-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="a48c1-131">Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="a48c1-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="a48c1-132">[![Mapowanie szablonu w integracji danych](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="a48c1-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
