---
title: "Synchronizowanie zadań w projekcie z programu Project Service Automation"
description: "Ten temat zawiera opis szablonu i podstawowego zadania, które jest używane do synchronizowania zadań projektu bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="46392-103">Synchronizowanie zadań w projekcie z programu Project Service Automation bezpośrednio do działań w projekcie w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="46392-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="46392-104">Ten temat zawiera opis szablonu i podstawowego zadania, które jest używane do synchronizowania zadań projektu bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="46392-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="46392-105">Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Dynamics 365 for Finance and Operations w wersji 8.0.</span><span class="sxs-lookup"><span data-stu-id="46392-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="46392-106">Przepływ danych z programu Project Service Automation do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="46392-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="46392-107">Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="46392-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="46392-108">Szablon integracji, który jest dostępny z funkcji integracji danych, umożliwia przepływ danych dotyczących zadań projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="46392-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="46392-109">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="46392-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="46392-110">[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="46392-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="46392-111">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="46392-111">Template and task</span></span>

<span data-ttu-id="46392-112">Aby uzyskać dostęp do szablonu w programie Microsoft PowerApps Admin Center wybierz **Projekty**i w prawym górnym rogu, wybierz **Nowy projekt**, aby wybierać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="46392-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="46392-113">Następujący szablon i zadanie podrzędne służy do synchronizowania zadań projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="46392-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="46392-114">-**Nazwa szablonu w narzędziu Integracja danych:** Zadania w projekcie (PSA do Fin and Ops) -**Nazwa zadania w projekcie:** Zadania w projekcie</span><span class="sxs-lookup"><span data-stu-id="46392-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="46392-115">Zanim będzie możliwa synchronizacja zadań w projektach, należy zsynchronizować umowy na projekty i projekty.</span><span class="sxs-lookup"><span data-stu-id="46392-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="46392-116">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="46392-116">Entity set</span></span>

|<span data-ttu-id="46392-117">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="46392-117">Project Service Automation</span></span>               | <span data-ttu-id="46392-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="46392-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="46392-119">Zadania w projekcie</span><span class="sxs-lookup"><span data-stu-id="46392-119">Project Tasks</span></span>                           | <span data-ttu-id="46392-120">Jednostka integracji zadania projektu.</span><span class="sxs-lookup"><span data-stu-id="46392-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="46392-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="46392-121">Entity flow</span></span>

<span data-ttu-id="46392-122">Zarządzanie zadaniami w projekcie odbywa się w aplikacji Project Service Automation i są one synchronizowane z programem Finance and Operations jako działania w projekcie.</span><span class="sxs-lookup"><span data-stu-id="46392-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="46392-123">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="46392-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="46392-124">Zanim będzie możliwa synchronizacja zadań w projektach, należy zsynchronizować umowy na projekty i projekty.</span><span class="sxs-lookup"><span data-stu-id="46392-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="46392-125">Zapytanie zaawansowane</span><span class="sxs-lookup"><span data-stu-id="46392-125">Power Query</span></span>

<span data-ttu-id="46392-126">Należy użyć programu Microsoft Power Query do odfiltrowania danych, jeśli są spełnione te warunki:</span><span class="sxs-lookup"><span data-stu-id="46392-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="46392-127">Masz rekordy przypisane do zasobów w ramach zadania w projekcie.</span><span class="sxs-lookup"><span data-stu-id="46392-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="46392-128">Jeśli musisz używać narzędzia Power Query, przestrzegaj następujących wytycznych:</span><span class="sxs-lookup"><span data-stu-id="46392-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="46392-129">Szablon Zadania w projekcie (PSA do Fin and Ops) ma domyślny filtr do wykluczania rekordów określonego zasobu z w ramach zadania w projekcie przez ustawienie filtru na **IsLineTask** na wartość **False**.</span><span class="sxs-lookup"><span data-stu-id="46392-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="46392-130">Jeśli tworzysz własny szablon, musisz dodać ten filtr.</span><span class="sxs-lookup"><span data-stu-id="46392-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="46392-131">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="46392-131">Template mapping in Data integration</span></span>

<span data-ttu-id="46392-132">Poniższa ilustracja przedstawia przykład mapowań zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="46392-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="46392-133">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="46392-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="46392-134">[![Mapowanie szablonu](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="46392-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


