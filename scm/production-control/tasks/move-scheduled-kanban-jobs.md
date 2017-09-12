--- 
title: "Przenoszenie zaplanowanych zadań w systemie Kanban"
description: "Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="9c026-103">Przenoszenie zaplanowanych zadań w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="9c026-103">Move scheduled kanban jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c026-104">Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu.</span><span class="sxs-lookup"><span data-stu-id="9c026-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="9c026-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="9c026-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="9c026-106">Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji używających kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="9c026-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="9c026-107">Wybieranie zaplanowanych zadań w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="9c026-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="9c026-108">Wybierz kolejno opcje Produkcja > Kanban > Zarządzanie czasem zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="9c026-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="9c026-109">!MtCMR!W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c026-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="9c026-110">áçêìõý!</span><span class="sxs-lookup"><span data-stu-id="9c026-110">áçêìõý !</span></span>
3. <span data-ttu-id="9c026-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="9c026-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="9c026-112">Zaznacz komórkę roboczą 1250.</span><span class="sxs-lookup"><span data-stu-id="9c026-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="9c026-113">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="9c026-113">Klik på Select.</span></span>
5. <span data-ttu-id="9c026-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="9c026-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="9c026-115">Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zaplanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="9c026-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="9c026-116">Przenoszenie zadań w systemie Kanban do innego okresu</span><span class="sxs-lookup"><span data-stu-id="9c026-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="9c026-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="9c026-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="9c026-118">Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład na dzień 20 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="9c026-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="9c026-119">Następnie przenieś zadanie do poprzedniego okresu.</span><span class="sxs-lookup"><span data-stu-id="9c026-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="9c026-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="9c026-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="9c026-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="9c026-121">Klik på End.</span></span>
    * <span data-ttu-id="9c026-122">Spowoduje to przeniesienie zadania na koniec listy zadań jako ostatniego zadania w poprzednim okresie.</span><span class="sxs-lookup"><span data-stu-id="9c026-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="9c026-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="9c026-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="9c026-124">Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład na dzień 18 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="9c026-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="9c026-125">Następnie przenieś zadanie do następnego okresu.</span><span class="sxs-lookup"><span data-stu-id="9c026-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="9c026-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="9c026-126">Klik på Next period.</span></span>
6. <span data-ttu-id="9c026-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="9c026-127">Klik på Start.</span></span>
    * <span data-ttu-id="9c026-128">Spowoduje to przeniesienie zadania na początek listy zadań jako pierwszego zadania w poprzednim okresie.</span><span class="sxs-lookup"><span data-stu-id="9c026-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="9c026-129">Zadanie: Przenoszenie zadania wewnątrz okresu</span><span class="sxs-lookup"><span data-stu-id="9c026-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="9c026-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="9c026-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="9c026-131">Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład drugie zadanie planowane na dzień 19 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="9c026-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="9c026-132">Następnie przenieś zadanie w granicach planowanego okresu.</span><span class="sxs-lookup"><span data-stu-id="9c026-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="9c026-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="9c026-133">Klik på Forward.</span></span>
    * <span data-ttu-id="9c026-134">Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w dół na liście.</span><span class="sxs-lookup"><span data-stu-id="9c026-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="9c026-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="9c026-135">Klik på Backward.</span></span>
    * <span data-ttu-id="9c026-136">Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w górę na liście.</span><span class="sxs-lookup"><span data-stu-id="9c026-136">Notice that the job is moved one line up on the list.</span></span>  


