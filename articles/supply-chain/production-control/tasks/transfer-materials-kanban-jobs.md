---
title: Przenoszenie materiałów za pomocą zadań systemu Kanban
description: Ta procedura skupia się na wycofywaniu zadania przeniesienia materiałów w systemie Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcab5d27d1e5bb2f86910fe083168e7b97c52e2f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148816"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="00d75-103">Przenoszenie materiałów za pomocą zadań systemu Kanban</span><span class="sxs-lookup"><span data-stu-id="00d75-103">Transfer materials with kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="00d75-104">Ta procedura skupia się na wycofywaniu zadania przeniesienia materiałów w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="00d75-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="00d75-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="00d75-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="00d75-106">Ta procedura jest przeznaczona dla pracownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="00d75-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="00d75-107">Wyświetlanie zadań przeniesienia</span><span class="sxs-lookup"><span data-stu-id="00d75-107">Display transfer jobs</span></span>
1. <span data-ttu-id="00d75-108">Wybierz kolejno opcje Kontrola produkcji > Kanban > Tablica Kanban zadań przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="00d75-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="00d75-109">Rozwiń lub zwiń sekcję Filtry.</span><span class="sxs-lookup"><span data-stu-id="00d75-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="00d75-110">W sekcji Filtry można określić, które zadania mają być widoczne, filtrując według przepływu produkcji, nazwy działania, magazynu i lokalizacji źródłowej oraz magazynu i lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="00d75-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="00d75-111">W polu Z magazynu wpisz „11”.</span><span class="sxs-lookup"><span data-stu-id="00d75-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="00d75-112">W polu Do lokalizacji wpisz „12”.</span><span class="sxs-lookup"><span data-stu-id="00d75-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="00d75-113">Rozpocznij zadanie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="00d75-113">Start a transfer job</span></span>
1. <span data-ttu-id="00d75-114">Na liście usuń zaznaczenie wybranego wiersza, jeśli takie istnieje.</span><span class="sxs-lookup"><span data-stu-id="00d75-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="00d75-115">Na liście zaznacz wiersz 4.</span><span class="sxs-lookup"><span data-stu-id="00d75-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="00d75-116">Zaznacz pierwsze zadanie o stanie Niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="00d75-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="00d75-117">Upewnij się, że jest to jedyne zaznaczone zadanie.</span><span class="sxs-lookup"><span data-stu-id="00d75-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="00d75-118">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="00d75-118">Click Start.</span></span>
    * <span data-ttu-id="00d75-119">Należy zauważyć, że ikona wskazuje rozpoczęcie zadania.</span><span class="sxs-lookup"><span data-stu-id="00d75-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="00d75-120">Wybór drugiego zadania przeniesienia i zmiana ilości</span><span class="sxs-lookup"><span data-stu-id="00d75-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="00d75-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="00d75-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="00d75-122">Można mieć zaznaczonych wiele zadań, ale na razie zaznacz tylko wiersz 5.</span><span class="sxs-lookup"><span data-stu-id="00d75-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="00d75-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="00d75-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="00d75-124">Upewnij się, że zadanie w poprzednim kroku jest jednym zaznaczonym zadaniem.</span><span class="sxs-lookup"><span data-stu-id="00d75-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="00d75-125">Anuluj zaznaczenie wszystkich innych zadań.</span><span class="sxs-lookup"><span data-stu-id="00d75-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="00d75-126">Zanotuj wartość z pola Ilość zadania w celu późniejszego wykorzystania</span><span class="sxs-lookup"><span data-stu-id="00d75-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="00d75-127">W polu Ilość zadania ustaw wartość „30”.</span><span class="sxs-lookup"><span data-stu-id="00d75-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="00d75-128">Zwróć uwagę na ostrzeżenie!</span><span class="sxs-lookup"><span data-stu-id="00d75-128">Notice the warning!</span></span> <span data-ttu-id="00d75-129">Nie możesz przenieść 30.</span><span class="sxs-lookup"><span data-stu-id="00d75-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="00d75-130">Zgodnie z ustawieniami reguły Kanban możesz przenieść tylko oryginalną ilość.</span><span class="sxs-lookup"><span data-stu-id="00d75-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="00d75-131">Użyj wartości zanotowanej uprzednio z pola Ilość zadania.</span><span class="sxs-lookup"><span data-stu-id="00d75-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="00d75-132">W polu Ilość zadania ustaw poprzednią wartość.</span><span class="sxs-lookup"><span data-stu-id="00d75-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="00d75-133">Rozpoczynanie drugiego zadania przeniesienia</span><span class="sxs-lookup"><span data-stu-id="00d75-133">Start the second transfer job</span></span>
1. <span data-ttu-id="00d75-134">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="00d75-134">Click Start.</span></span>
    * <span data-ttu-id="00d75-135">Spowoduje to rozpoczęcie przeniesienia określonego w zadaniu w wierszu 5.</span><span class="sxs-lookup"><span data-stu-id="00d75-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="00d75-136">Kończenie obu zadań przeniesienia</span><span class="sxs-lookup"><span data-stu-id="00d75-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="00d75-137">Na liście zaznacz wiersz 4.</span><span class="sxs-lookup"><span data-stu-id="00d75-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="00d75-138">Teraz są wybrane dwa zadania przeniesienia, w wierszach 4 i 5.</span><span class="sxs-lookup"><span data-stu-id="00d75-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="00d75-139">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="00d75-139">Click Complete.</span></span>
    * <span data-ttu-id="00d75-140">Spowoduje to zakończenie przeniesienia w obu zadaniach.</span><span class="sxs-lookup"><span data-stu-id="00d75-140">This will complete the transfer of both jobs.</span></span>  

