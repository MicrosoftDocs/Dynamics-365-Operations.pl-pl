--- 
title: "Tworzenie reguły Kanban dla wielu działań"
description: "W tej procedurze pokazano, jak utworzyć regułę Kanban, która obejmuje wiele działań z przepływu produkcji."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d6d0c50da3124553124b65f6ba0e1c5ed35e8613
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="f7881-103">Tworzenie reguły Kanban dla wielu działań</span><span class="sxs-lookup"><span data-stu-id="f7881-103">Create a kanban rule for multiple activities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f7881-104">W tej procedurze pokazano, jak utworzyć regułę Kanban, która obejmuje wiele działań z przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="f7881-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="f7881-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f7881-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="f7881-106">To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="f7881-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="f7881-107">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="f7881-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="f7881-108">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="f7881-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="f7881-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f7881-109">Click New.</span></span>
3. <span data-ttu-id="f7881-110">W polu Strategia uzupełniania wybierz opcję „Zaplanowane”.</span><span class="sxs-lookup"><span data-stu-id="f7881-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="f7881-111">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f7881-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="f7881-112">Wybierz czynność SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="f7881-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="f7881-113">Zaznacz pole wyboru Wiele działań.</span><span class="sxs-lookup"><span data-stu-id="f7881-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="f7881-114">Celem jest umieszczenie więcej niż jednego działania w regule Kanban.</span><span class="sxs-lookup"><span data-stu-id="f7881-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="f7881-115">Wybierasz ścieżkę w przepływie produkcji z chwilą wybrania ostatniego działania w planie.</span><span class="sxs-lookup"><span data-stu-id="f7881-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="f7881-116">W polu Ostatnie działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f7881-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="f7881-117">Wybierz opcję SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="f7881-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="f7881-118">Po zaznaczeniu wartości automatycznie zostanie otwarta strona.</span><span class="sxs-lookup"><span data-stu-id="f7881-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="f7881-119">Wybierz przepływ Kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="f7881-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="f7881-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f7881-120">Click OK.</span></span>  
7. <span data-ttu-id="f7881-121">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="f7881-121">Expand the Details section.</span></span>
8. <span data-ttu-id="f7881-122">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f7881-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="f7881-123">Wybierz towar L0006.</span><span class="sxs-lookup"><span data-stu-id="f7881-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="f7881-124">Tworzenie reguły Kanban i wyświetlanie zadań</span><span class="sxs-lookup"><span data-stu-id="f7881-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="f7881-125">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="f7881-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="f7881-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f7881-126">Click Add.</span></span>
3. <span data-ttu-id="f7881-127">W polu Liczba nowych kart Kanban wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="f7881-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="f7881-128">Spowoduje to utworzenie jednej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="f7881-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="f7881-129">W polu Ilość produktu ustaw wartość „3”.</span><span class="sxs-lookup"><span data-stu-id="f7881-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="f7881-130">W zadaniu Kanban będą przetwarzane 3 produkty.</span><span class="sxs-lookup"><span data-stu-id="f7881-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="f7881-131">W polu Data/godzina wykonania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="f7881-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="f7881-132">Można wprowadzić wartość Dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="f7881-132">You can enter Today.</span></span>  
6. <span data-ttu-id="f7881-133">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="f7881-133">Click Create.</span></span>
7. <span data-ttu-id="f7881-134">Kliknij przycisk Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="f7881-134">Click Details.</span></span>
    * <span data-ttu-id="f7881-135">Należy zauważyć, że karta Kanban ma dwa zadania przetwarzania z przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="f7881-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="f7881-136">Pierwsze z nich to SpeakerAssemblyAndPolish, a drugim jest SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="f7881-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="f7881-137">To jest ostatni krok!</span><span class="sxs-lookup"><span data-stu-id="f7881-137">This is the last step!</span></span>  


