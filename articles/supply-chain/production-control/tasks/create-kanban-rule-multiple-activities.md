---
title: Tworzenie reguły Kanban dla wielu działań
description: W tej procedurze pokazano, jak utworzyć regułę Kanban, która obejmuje wiele działań z przepływu produkcji.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c25d47a78d1cc91ee2625ef628d7b9ba345b097
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977920"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="4d732-103">Tworzenie reguły Kanban dla wielu działań</span><span class="sxs-lookup"><span data-stu-id="4d732-103">Create a kanban rule for multiple activities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d732-104">W tej procedurze pokazano, jak utworzyć regułę Kanban, która obejmuje wiele działań z przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="4d732-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="4d732-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4d732-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="4d732-106">To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="4d732-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="4d732-107">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="4d732-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="4d732-108">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="4d732-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="4d732-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4d732-109">Click New.</span></span>
3. <span data-ttu-id="4d732-110">W polu Strategia uzupełniania wybierz opcję „Zaplanowane”.</span><span class="sxs-lookup"><span data-stu-id="4d732-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="4d732-111">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4d732-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="4d732-112">Wybierz czynność SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="4d732-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="4d732-113">Zaznacz pole wyboru Wiele działań.</span><span class="sxs-lookup"><span data-stu-id="4d732-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="4d732-114">Celem jest umieszczenie więcej niż jednego działania w regule Kanban.</span><span class="sxs-lookup"><span data-stu-id="4d732-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="4d732-115">Wybierasz ścieżkę w przepływie produkcji z chwilą wybrania ostatniego działania w planie.</span><span class="sxs-lookup"><span data-stu-id="4d732-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="4d732-116">W polu Ostatnie działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4d732-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="4d732-117">Wybierz opcję SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="4d732-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="4d732-118">Po zaznaczeniu wartości automatycznie zostanie otwarta strona.</span><span class="sxs-lookup"><span data-stu-id="4d732-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="4d732-119">Wybierz przepływ Kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="4d732-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="4d732-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4d732-120">Click OK.</span></span>  
7. <span data-ttu-id="4d732-121">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="4d732-121">Expand the Details section.</span></span>
8. <span data-ttu-id="4d732-122">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4d732-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="4d732-123">Wybierz towar L0006.</span><span class="sxs-lookup"><span data-stu-id="4d732-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="4d732-124">Tworzenie reguły Kanban i wyświetlanie zadań</span><span class="sxs-lookup"><span data-stu-id="4d732-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="4d732-125">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="4d732-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="4d732-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="4d732-126">Click Add.</span></span>
3. <span data-ttu-id="4d732-127">W polu Liczba nowych kart Kanban wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="4d732-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="4d732-128">Spowoduje to utworzenie jednej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="4d732-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="4d732-129">W polu Ilość produktu ustaw wartość „3”.</span><span class="sxs-lookup"><span data-stu-id="4d732-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="4d732-130">W zadaniu Kanban będą przetwarzane 3 produkty.</span><span class="sxs-lookup"><span data-stu-id="4d732-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="4d732-131">W polu Data/godzina wykonania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="4d732-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="4d732-132">Można wprowadzić wartość Dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="4d732-132">You can enter Today.</span></span>  
6. <span data-ttu-id="4d732-133">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="4d732-133">Click Create.</span></span>
7. <span data-ttu-id="4d732-134">Kliknij przycisk Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="4d732-134">Click Details.</span></span>
    * <span data-ttu-id="4d732-135">Należy zauważyć, że karta Kanban ma dwa zadania przetwarzania z przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="4d732-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="4d732-136">Pierwsze z nich to SpeakerAssemblyAndPolish, a drugim jest SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="4d732-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="4d732-137">To jest ostatni krok!</span><span class="sxs-lookup"><span data-stu-id="4d732-137">This is the last step!</span></span>  

