--- 
title: "Tworzenie zastępczej reguły Kanban"
description: "Ta procedura skupia się na zastąpieniu istniejącej reguły Kanban nową regułą Kanban w określonym dniu."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: c8a9367d4796999857e473bcbe36a709d534f3b0
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="b97f1-103">Tworzenie zastępczej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="b97f1-103">Create a replacement kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b97f1-104">Ta procedura skupia się na zastąpieniu istniejącej reguły Kanban nową regułą Kanban w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="b97f1-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="b97f1-105">Jest to przydatne, gdy zmiany w przepływie produkcji lub regułach uzupełnienia muszą być skoordynowane i zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="b97f1-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="b97f1-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b97f1-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="b97f1-107">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni produkcję z nowym przepływem lub regułą uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="b97f1-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="b97f1-108">To zadanie powoduje zastąpienie reguły Kanban 000022 nową regułą, która określa zwiększenie maksymalnej ilości z 48 do 100 sztuk.</span><span class="sxs-lookup"><span data-stu-id="b97f1-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="b97f1-109">Wybieranie reguły Kanban do zastąpienia</span><span class="sxs-lookup"><span data-stu-id="b97f1-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="b97f1-110">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="b97f1-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="b97f1-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b97f1-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b97f1-112">Wybierz regułę Kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="b97f1-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="b97f1-113">Tworzenie zastępczej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="b97f1-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="b97f1-114">Kliknij opcję Przywróć regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="b97f1-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="b97f1-115">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="b97f1-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="b97f1-116">Wybierz datę w przyszłości, na przykład jeden tydzień od teraz.</span><span class="sxs-lookup"><span data-stu-id="b97f1-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="b97f1-117">Jest to data i godzina, kiedy nowa reguła Kanban stanie się aktywna i zastąpi starą regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="b97f1-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="b97f1-118">Jeśli reguła Kanban zmienia ścieżkę w przepływie produkcji, można wybrać inne działanie.</span><span class="sxs-lookup"><span data-stu-id="b97f1-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="b97f1-119">W tej procedurze użyjemy działania bez zmian.</span><span class="sxs-lookup"><span data-stu-id="b97f1-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="b97f1-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b97f1-120">Click OK.</span></span>
    * <span data-ttu-id="b97f1-121">Zwróć uwagę, że została utworzona nowa reguła Kanban, aby zastąpić dotychczasową regułę Kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="b97f1-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="b97f1-122">Data wejścia w życie jest ustawiana zgodnie z datą wybraną podczas zamiany reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="b97f1-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="b97f1-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b97f1-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b97f1-124">Zaznacz zastępowaną regułę Kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="b97f1-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="b97f1-125">Zwróć uwagę, że zastąpiona reguła Kanban ma taką samą datę jak data ważności, ponieważ jest to dzień, kiedy reguła wygasa.</span><span class="sxs-lookup"><span data-stu-id="b97f1-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="b97f1-126">Na liście zaznacz wiersz 1.</span><span class="sxs-lookup"><span data-stu-id="b97f1-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="b97f1-127">Zaznacz nową regułę Kanban na szczycie listy.</span><span class="sxs-lookup"><span data-stu-id="b97f1-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="b97f1-128">Jest to reguła Kanban o najwyższym numerze.</span><span class="sxs-lookup"><span data-stu-id="b97f1-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="b97f1-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b97f1-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b97f1-130">Kliknij numer reguły Kanban, aby otworzyć regułę.</span><span class="sxs-lookup"><span data-stu-id="b97f1-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="b97f1-131">Modyfikowanie ilości maksymalnej dla nowej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="b97f1-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="b97f1-132">W polu Ilość maksymalna ustaw wartość „100”.</span><span class="sxs-lookup"><span data-stu-id="b97f1-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="b97f1-133">Rozwiń skróconą kartę Ilości, aby wyświetlić pole Ilość maksymalna.</span><span class="sxs-lookup"><span data-stu-id="b97f1-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="b97f1-134">Zmiana maksymalnej ilości na 100 pozwoli na przetwarzanie maksymalnie 100 kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="b97f1-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="b97f1-135">Jest to ostatni krok w tym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="b97f1-135">This is the last step in this task.</span></span>  


