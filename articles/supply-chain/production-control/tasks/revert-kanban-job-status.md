---
title: Przywróć stan zadania Kanban
description: Ta procedura skupia się na cofnięciu błędnego stanu zadania w systemie Kanban.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 94618494b9c338ed27b2558c91dc662c853d3cda
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261101"
---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="94e06-103">Przywróć stan zadania Kanban</span><span class="sxs-lookup"><span data-stu-id="94e06-103">Revert kanban job status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="94e06-104">Ta procedura skupia się na cofnięciu błędnego stanu zadania w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="94e06-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="94e06-105">Jest to przydatne w przypadku, gdy operator maszyny zaktualizuje niewłaściwe zadanie lub ustawi przez pomyłkę niewłaściwy stan.</span><span class="sxs-lookup"><span data-stu-id="94e06-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="94e06-106">W tej procedurze zadanie w systemie Kanban jest rejestrowane jako przygotowane przez pomyłkę, a stan zostanie przywrócony.</span><span class="sxs-lookup"><span data-stu-id="94e06-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="94e06-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="94e06-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="94e06-108">Procedura jest przeznaczona dla kierownika produkcji lub operatora maszyny w firmie stosującej zasady produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="94e06-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="94e06-109">Otwieranie tablicy procesów komórki roboczej</span><span class="sxs-lookup"><span data-stu-id="94e06-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="94e06-110">Przejdź do tablicy Kanban pokazującej zadania przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="94e06-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="94e06-111">W polu Komórka robocza wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="94e06-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="94e06-112">Zaznacz komórkę roboczą 1260.</span><span class="sxs-lookup"><span data-stu-id="94e06-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="94e06-113">Przygotowanie zadania w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="94e06-113">Prepare kanban job</span></span>
1. <span data-ttu-id="94e06-114">Kliknij przycisk Przygotuj.</span><span class="sxs-lookup"><span data-stu-id="94e06-114">Click Prepare.</span></span>
    * <span data-ttu-id="94e06-115">Jeśli nie możesz kliknąć przycisku Przygotuj, ponieważ jest on wyszarzony, upewnij się, że wybrane zadanie w systemie Kanban ma stan Zaplanowane, co jest wskazywane przez pustą ikonę na karcie Kanban.</span><span class="sxs-lookup"><span data-stu-id="94e06-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="94e06-116">Jeśli przygotowanie się nie powiedzie, upewnij się, że wszystkie materiały na liście pobrania są dostępne.</span><span class="sxs-lookup"><span data-stu-id="94e06-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="94e06-117">Na liście zaznacz przygotowane zadanie.</span><span class="sxs-lookup"><span data-stu-id="94e06-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="94e06-118">Wybierz pierwsze zadanie, które właśnie zostało przygotowane.</span><span class="sxs-lookup"><span data-stu-id="94e06-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="94e06-119">Należy zauważyć, że stan zadania to „przygotowane”, co jest wskazane trójkątem wewnątrz ikony karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="94e06-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="94e06-120">Przywracanie stanu przygotowanego zadania w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="94e06-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="94e06-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="94e06-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="94e06-122">Wybierz pierwsze zadanie, które właśnie zostało przygotowane.</span><span class="sxs-lookup"><span data-stu-id="94e06-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="94e06-123">W okienku akcji kliknij pozycję Produkcja.</span><span class="sxs-lookup"><span data-stu-id="94e06-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="94e06-124">Kliknij opcję Przywrócenie stanu.</span><span class="sxs-lookup"><span data-stu-id="94e06-124">Click Revert status.</span></span>
    * <span data-ttu-id="94e06-125">Można użyć alternatywnej reguły Kanban, gdy są spełnione następujące warunki:  - Strategia uzupełniania jest taka sama dla obu reguł.</span><span class="sxs-lookup"><span data-stu-id="94e06-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="94e06-126">- Wersja przepływu produkcji jest taka sama dla obu reguł.</span><span class="sxs-lookup"><span data-stu-id="94e06-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="94e06-127">- Dostarczany produkt jest taki sam dla obu reguł.</span><span class="sxs-lookup"><span data-stu-id="94e06-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="94e06-128">- Wszelkie działania poprzedzające skonfigurowane dla ostatniego działania w regułach Kanban muszą być takie same w obu regułach.</span><span class="sxs-lookup"><span data-stu-id="94e06-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="94e06-129">- Te same wymiary dostarczanych zapasów muszą być skonfigurowane dla obu reguł.</span><span class="sxs-lookup"><span data-stu-id="94e06-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="94e06-130">- Jednostka załadunkowa musi mieć stan Nie przypisano.</span><span class="sxs-lookup"><span data-stu-id="94e06-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="94e06-131">- Konfiguracja kart Kanban zdarzeń musi być taka sama.</span><span class="sxs-lookup"><span data-stu-id="94e06-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="94e06-132">Upewnij się, że nowy stan to Zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="94e06-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="94e06-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="94e06-133">Click OK.</span></span>
5. <span data-ttu-id="94e06-134">Na liście usuń oznaczenie wybranego wiersza.</span><span class="sxs-lookup"><span data-stu-id="94e06-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="94e06-135">Wybierz to samo zadanie.</span><span class="sxs-lookup"><span data-stu-id="94e06-135">Select the same job.</span></span>  
    * <span data-ttu-id="94e06-136">Należy zauważyć, że stan zadania w systemie kanban został przywrócony do Zaplanowane, co jest wskazywane przez pustą ikonę na karcie Kanban.</span><span class="sxs-lookup"><span data-stu-id="94e06-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]