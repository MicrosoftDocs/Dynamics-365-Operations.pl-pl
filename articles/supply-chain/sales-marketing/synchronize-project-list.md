---
title: Synchronizowanie listy projektów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.
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
ms.openlocfilehash: 5cb7f8b9a3107a7787c787ace71ab574457b1646
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828498"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="e3922-103">Synchronizowanie listy projektów z rozwiązania Supply Chain Management do rozwiązania Field Service</span><span class="sxs-lookup"><span data-stu-id="e3922-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e3922-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="e3922-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="e3922-105">[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="e3922-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e3922-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="e3922-106">Templates and tasks</span></span>
<span data-ttu-id="e3922-107">Poniższy szablon i podstawowe zadania są używane do synchronizowania projektów między rozwiązaniami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="e3922-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="e3922-108">**Mapowanie szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="e3922-108">**Template in Data integration**</span></span>
- <span data-ttu-id="e3922-109">Projekty (rozwiązanie Supply Chain Management do rozwiązania Field Service)</span><span class="sxs-lookup"><span data-stu-id="e3922-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="e3922-110">**Zadani w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="e3922-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="e3922-111">Projekty</span><span class="sxs-lookup"><span data-stu-id="e3922-111">Projects</span></span>

<span data-ttu-id="e3922-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować listę projektu:</span><span class="sxs-lookup"><span data-stu-id="e3922-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="e3922-113">Konta (Sales do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="e3922-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="e3922-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="e3922-114">Entity set</span></span>
| <span data-ttu-id="e3922-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="e3922-115">Field Service</span></span>           | <span data-ttu-id="e3922-116">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="e3922-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="e3922-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="e3922-117">msdynce_externalprojects</span></span> | <span data-ttu-id="e3922-118">Projekty</span><span class="sxs-lookup"><span data-stu-id="e3922-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="e3922-119">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="e3922-119">Entity flow</span></span>
<span data-ttu-id="e3922-120">Projekt zewnętrzny jest utworzony w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3922-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="e3922-121">Projekty z **Typem projektu** ustawionym na **Czas i materiał** i **Etapem projektu** ustawionym na **W toku** będą synchronizowały się z jednostką **Projekt zewnętrzny** w Field Service, w tym z numerem projektu, nazwą projektu, etapem projektu i kontem klienta.</span><span class="sxs-lookup"><span data-stu-id="e3922-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="e3922-122">**Projekt zewnętrzny** jest listą używaną do tworzenia par zleceń Field service i projektów Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3922-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="e3922-123">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="e3922-123">Field Service CRM solution</span></span>
<span data-ttu-id="e3922-124">Jednostka **Projekt zewnętrzny** pobiera wszystkie projekty z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3922-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="e3922-125">Pole **Projekt zewnętrzny** zostało dodane do jednostka **Zlecenie**.</span><span class="sxs-lookup"><span data-stu-id="e3922-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="e3922-126">Jest to pole wyszukiwania, więc dzięki oznaczeniu zlecenia za pomocą projektu, zlecenie sprzedaży będzie połączone z projektem w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3922-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="e3922-127">Gdy **Stan systemu** zmieni się z **Otwarte — w toku (690,970,000)** na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.</span><span class="sxs-lookup"><span data-stu-id="e3922-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="e3922-128">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="e3922-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="e3922-129">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="e3922-129">Supply Chain Management</span></span>
<span data-ttu-id="e3922-130">Włączanie śledzenia zmian w projektach jednostek danych</span><span class="sxs-lookup"><span data-stu-id="e3922-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e3922-131">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="e3922-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="e3922-132">Projekty (rozwiązanie Supply Chain Management do rozwiązania Field Service): Porjekty</span><span class="sxs-lookup"><span data-stu-id="e3922-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="e3922-133">[![Mapowanie szablonu w integracji danych](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="e3922-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]