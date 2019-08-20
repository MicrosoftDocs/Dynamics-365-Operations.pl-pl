---
title: Przenoszenie zaplanowanych zadań w systemie Kanban
description: Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu.
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2526c2bd106e35c736e930b5b5114d019718dc5a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836247"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="b8fa0-103">Przenoszenie zaplanowanych zadań w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="b8fa0-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8fa0-104">Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="b8fa0-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b8fa0-106">Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji używających kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="b8fa0-107">Wybieranie zaplanowanych zadań w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="b8fa0-108">Wybierz kolejno opcje **Kontrola produkcji > Kanban > Planowanie zadań Kanban**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="b8fa0-109">W polu **Komórka robocza** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="b8fa0-110">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="b8fa0-111">Zaznacz komórkę roboczą 1250.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="b8fa0-112">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-112">Click **Select**.</span></span> 

5. <span data-ttu-id="b8fa0-113">W polu **Wyświetl stan zadania** zaznacz opcję **Zaplanowane**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="b8fa0-114">Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zaplanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="b8fa0-115">Przenoszenie zadań w systemie Kanban do innego okresu.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="b8fa0-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="b8fa0-117">Wybierz zadanie, które w polu **Planowany okres** ma stan **zaplanowanego zadania**, na przykład na dzień 20 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="b8fa0-118">Następnie przenieś zadanie do poprzedniego okresu.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="b8fa0-119">Kliknij opcję **Poprzedni okres**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="b8fa0-120">Kliknij **Zakończ**, aby przenieść zadanie na koniec listy zadań jako ostatniego zadanie w poprzednim okresie.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="b8fa0-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="b8fa0-122">Wybierz zadanie, które w polu **Planowany okres** ma stan **zaplanowanego zadania**, na przykład na dzień 18 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="b8fa0-123">Następnie przenieś zadanie do następnego okresu.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="b8fa0-124">Kliknij opcję **Następny okres**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="b8fa0-125">Kliknij **Start**, aby przenieść zadanie na początek listy zadań jako pierwsze zadanie w poprzednim okresie.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="b8fa0-126">Przenoszenie zadania wewnątrz okresu.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="b8fa0-127">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="b8fa0-128">Wybierz zadanie, które w polu **Planowany okres** ma stan zaplanowanego zadania, na przykład drugie zadanie planowane na dzień 19 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="b8fa0-129">Następnie przenieś zadanie w granicach planowanego okresu.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="b8fa0-130">Kliknij opcję **W przód**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-130">Click **Forward**.</span></span> <span data-ttu-id="b8fa0-131">Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w dół na liście.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="b8fa0-132">Kliknij opcję **Wstecz**.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-132">Click **Backward**.</span></span> <span data-ttu-id="b8fa0-133">Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w górę na liście.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-133">Notice that the job is moved one line up on the list.</span></span>
