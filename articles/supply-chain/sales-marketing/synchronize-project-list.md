---
title: Synchronizowanie listy projekty między aplikacjami Finance and Operations i Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "312515"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="5708e-103">Synchronizowanie listy projektów z rozwiązania Finance and Operations do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="5708e-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5708e-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="5708e-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="5708e-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="5708e-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="5708e-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="5708e-106">Templates and tasks</span></span>
<span data-ttu-id="5708e-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="5708e-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="5708e-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="5708e-108">**Template in Data integration**</span></span>
- <span data-ttu-id="5708e-109">Projekty (Finance and Operations do Field Service)</span><span class="sxs-lookup"><span data-stu-id="5708e-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="5708e-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="5708e-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="5708e-111">Projekty</span><span class="sxs-lookup"><span data-stu-id="5708e-111">Projects</span></span>

<span data-ttu-id="5708e-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować listę projektu:</span><span class="sxs-lookup"><span data-stu-id="5708e-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="5708e-113">Konta (Sales do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="5708e-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="5708e-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="5708e-114">Entity set</span></span>
| <span data-ttu-id="5708e-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="5708e-115">Field Service</span></span>           | <span data-ttu-id="5708e-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5708e-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="5708e-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="5708e-117">msdynce_externalprojects</span></span> | <span data-ttu-id="5708e-118">Projekty</span><span class="sxs-lookup"><span data-stu-id="5708e-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="5708e-119">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="5708e-119">Entity flow</span></span>
<span data-ttu-id="5708e-120">Projekty są tworzone w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5708e-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="5708e-121">Projekty z **Typem projektu** ustawionym na **Czas i materiał** i **Etapem projektu** ustawionym na **W toku** będą synchronizowały się z jednostką **Projekt zewnętrzny** w Field Service, w tym z numerem projektu, nazwą projektu, etapem projektu i kontem klienta.</span><span class="sxs-lookup"><span data-stu-id="5708e-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="5708e-122">**Projekt zewnętrzny** jest listą używaną do tworzenia par zleceń Field service i projektów Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5708e-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="5708e-123">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="5708e-123">Field Service CRM solution</span></span>
<span data-ttu-id="5708e-124">Jednostka **Projekt zewnętrzny** pobiera wszystkie projekty z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5708e-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="5708e-125">Pole **Projekt zewnętrzny** zostało dodane do jednostka **Zlecenie**.</span><span class="sxs-lookup"><span data-stu-id="5708e-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="5708e-126">Jest to pole wyszukiwania, więc dzięki oznaczeniu zlecenia za pomocą projektu, zlecenie sprzedaży będzie połączone z projektem w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5708e-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="5708e-127">Gdy **Stan systemu** zmieni się z **Otwarte — w toku (690,970,000)** na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.</span><span class="sxs-lookup"><span data-stu-id="5708e-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="5708e-128">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="5708e-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="5708e-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5708e-129">Finance and Operations</span></span>
<span data-ttu-id="5708e-130">Włączanie śledzenia zmian w projektach jednostek danych</span><span class="sxs-lookup"><span data-stu-id="5708e-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="5708e-131">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="5708e-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="5708e-132">Projekty (Finance and Operations do Field Service): Projekty</span><span class="sxs-lookup"><span data-stu-id="5708e-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="5708e-133">[![Mapowanie szablonu w integracji danych](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="5708e-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
