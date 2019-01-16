---
title: "Synchronizowanie listy projekty między aplikacjami Finance and Operations i Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="f5ccb-103">Synchronizowanie listy projekty między aplikacjami Finance and Operations i Field Service</span><span class="sxs-lookup"><span data-stu-id="f5ccb-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f5ccb-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f5ccb-105">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="f5ccb-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f5ccb-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="f5ccb-106">Templates and tasks</span></span>
<span data-ttu-id="f5ccb-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f5ccb-108">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="f5ccb-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="f5ccb-109">Projekty (Finance and Operations do Field Service)</span><span class="sxs-lookup"><span data-stu-id="f5ccb-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="f5ccb-110">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="f5ccb-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="f5ccb-111">Projekty</span><span class="sxs-lookup"><span data-stu-id="f5ccb-111">Projects</span></span>

<span data-ttu-id="f5ccb-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować listę projektu:</span><span class="sxs-lookup"><span data-stu-id="f5ccb-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="f5ccb-113">Konta (Sales do Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="f5ccb-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="f5ccb-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="f5ccb-114">Entity set</span></span>
<span data-ttu-id="f5ccb-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f5ccb-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="f5ccb-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="f5ccb-116">Field Service</span></span>           | <span data-ttu-id="f5ccb-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f5ccb-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="f5ccb-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="f5ccb-118">msdynce_externalprojects</span></span> | <span data-ttu-id="f5ccb-119">Projekty</span><span class="sxs-lookup"><span data-stu-id="f5ccb-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="f5ccb-120">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="f5ccb-120">Entity flow</span></span>
<span data-ttu-id="f5ccb-121">Projekty są tworzone w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="f5ccb-122">Projekty z **Typem projektu** Czas i materiał i **Etapem projektu** W toku będą synchronizowały się z jednostką **Projekt zewnętrzny** w Field Service, w tym z numerem projektu, nazwą projektu, etapem projektu i kontem klienta.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="f5ccb-123">Lista **Projekt zewnętrzny** jest używana do tworzenia par zleceń Field service i projektów Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="f5ccb-124">Rozwiązanie CRM Field Service Projekt zewnętrzny jest nową jednostką, która otrzymuje wszystkie projekty z Operations.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="f5ccb-125">Pole Projekt zewnętrzny zostało dodane do jednostka Zlecenie.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="f5ccb-126">To pole jest wyszukiwaniem i zakupem, które wyzwalają Zlecenie z projektem; następnie Zlecenie sprzedaży jest łączone z Projektem w Operations.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="f5ccb-127">Gdy Stan systemu zmieni się z Otwarte — w toku (690,970,000) na wyższy status, pole Projekt zewnętrzny zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.</span><span class="sxs-lookup"><span data-stu-id="f5ccb-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f5ccb-128">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="f5ccb-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="f5ccb-129">W programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f5ccb-129">In Finance and Operations</span></span>
<span data-ttu-id="f5ccb-130">Włączanie śledzenia zmian w projektach jednostek danych</span><span class="sxs-lookup"><span data-stu-id="f5ccb-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f5ccb-131">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="f5ccb-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="f5ccb-132">Projekty (Finance and Operations do Field Service): Projekty</span><span class="sxs-lookup"><span data-stu-id="f5ccb-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="f5ccb-133">[![Mapowanie szablonu w integracji danych](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="f5ccb-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

