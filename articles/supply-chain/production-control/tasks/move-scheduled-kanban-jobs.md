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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ae6ea66f0e0ce03008882e59140ad7a0d89f0e30
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="2a375-103">Przenoszenie zaplanowanych zadań w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="2a375-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2a375-104">Ta procedura skupia się na przenoszeniu planowanych zadań przetwarzania w systemie Kanban do innego okresu.</span><span class="sxs-lookup"><span data-stu-id="2a375-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="2a375-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2a375-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2a375-106">Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji używających kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2a375-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="2a375-107">Wybieranie zaplanowanych zadań w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="2a375-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="2a375-108">Wybierz kolejno opcje Produkcja > Kanban > Zarządzanie czasem zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="2a375-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="2a375-109">!MtCMR!W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2a375-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="2a375-110">áçêìõý!</span><span class="sxs-lookup"><span data-stu-id="2a375-110">áçêìõý !</span></span>
3. <span data-ttu-id="2a375-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="2a375-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="2a375-112">Zaznacz komórkę roboczą 1250.</span><span class="sxs-lookup"><span data-stu-id="2a375-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="2a375-113">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="2a375-113">Klik på Select.</span></span>
5. <span data-ttu-id="2a375-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="2a375-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="2a375-115">Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zaplanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="2a375-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="2a375-116">Przenoszenie zadań w systemie Kanban do innego okresu</span><span class="sxs-lookup"><span data-stu-id="2a375-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="2a375-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="2a375-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="2a375-118">Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład na dzień 20 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="2a375-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="2a375-119">Następnie przenieś zadanie do poprzedniego okresu.</span><span class="sxs-lookup"><span data-stu-id="2a375-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="2a375-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="2a375-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="2a375-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="2a375-121">Klik på End.</span></span>
    * <span data-ttu-id="2a375-122">Spowoduje to przeniesienie zadania na koniec listy zadań jako ostatniego zadania w poprzednim okresie.</span><span class="sxs-lookup"><span data-stu-id="2a375-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="2a375-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="2a375-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="2a375-124">Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład na dzień 18 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="2a375-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="2a375-125">Następnie przenieś zadanie do następnego okresu.</span><span class="sxs-lookup"><span data-stu-id="2a375-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="2a375-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="2a375-126">Klik på Next period.</span></span>
6. <span data-ttu-id="2a375-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="2a375-127">Klik på Start.</span></span>
    * <span data-ttu-id="2a375-128">Spowoduje to przeniesienie zadania na początek listy zadań jako pierwszego zadania w poprzednim okresie.</span><span class="sxs-lookup"><span data-stu-id="2a375-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="2a375-129">Zadanie: Przenoszenie zadania wewnątrz okresu</span><span class="sxs-lookup"><span data-stu-id="2a375-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="2a375-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="2a375-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="2a375-131">Wybierz zadanie, które w polu Planowany okres ma stan zaplanowanego zadania, na przykład drugie zadanie planowane na dzień 19 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="2a375-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="2a375-132">Następnie przenieś zadanie w granicach planowanego okresu.</span><span class="sxs-lookup"><span data-stu-id="2a375-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="2a375-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="2a375-133">Klik på Forward.</span></span>
    * <span data-ttu-id="2a375-134">Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w dół na liście.</span><span class="sxs-lookup"><span data-stu-id="2a375-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="2a375-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="2a375-135">Klik på Backward.</span></span>
    * <span data-ttu-id="2a375-136">Należy zauważyć, że zadanie zostało przeniesione o jeden wiersz w górę na liście.</span><span class="sxs-lookup"><span data-stu-id="2a375-136">Notice that the job is moved one line up on the list.</span></span>  


