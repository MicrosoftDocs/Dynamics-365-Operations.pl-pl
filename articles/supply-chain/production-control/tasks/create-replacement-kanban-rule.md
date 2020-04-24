---
title: Tworzenie zastępczej reguły Kanban
description: Ta procedura skupia się na zastąpieniu istniejącej reguły Kanban nową regułą Kanban w określonym dniu.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae589f81811c1586e0e24de94eaf5f467f19debb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210877"
---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="2bdd3-103">Tworzenie zastępczej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="2bdd3-103">Create a replacement kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2bdd3-104">Ta procedura skupia się na zastąpieniu istniejącej reguły Kanban nową regułą Kanban w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="2bdd3-105">Jest to przydatne, gdy zmiany w przepływie produkcji lub regułach uzupełnienia muszą być skoordynowane i zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="2bdd3-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="2bdd3-107">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni produkcję z nowym przepływem lub regułą uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="2bdd3-108">To zadanie powoduje zastąpienie reguły Kanban 000022 nową regułą, która określa zwiększenie maksymalnej ilości z 48 do 100 sztuk.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="2bdd3-109">Wybieranie reguły Kanban do zastąpienia</span><span class="sxs-lookup"><span data-stu-id="2bdd3-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="2bdd3-110">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="2bdd3-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2bdd3-112">Wybierz regułę Kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="2bdd3-113">Tworzenie zastępczej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="2bdd3-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="2bdd3-114">Kliknij opcję Przywróć regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="2bdd3-115">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="2bdd3-116">Wybierz datę w przyszłości, na przykład jeden tydzień od teraz.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="2bdd3-117">Jest to data i godzina, kiedy nowa reguła Kanban stanie się aktywna i zastąpi starą regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="2bdd3-118">Jeśli reguła Kanban zmienia ścieżkę w przepływie produkcji, można wybrać inne działanie.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="2bdd3-119">W tej procedurze użyjemy działania bez zmian.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="2bdd3-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-120">Click OK.</span></span>
    * <span data-ttu-id="2bdd3-121">Zwróć uwagę, że została utworzona nowa reguła Kanban, aby zastąpić dotychczasową regułę Kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="2bdd3-122">Data wejścia w życie jest ustawiana zgodnie z datą wybraną podczas zamiany reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="2bdd3-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2bdd3-124">Zaznacz zastępowaną regułę Kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="2bdd3-125">Zwróć uwagę, że zastąpiona reguła Kanban ma taką samą datę jak data ważności, ponieważ jest to dzień, kiedy reguła wygasa.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="2bdd3-126">Na liście zaznacz wiersz 1.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="2bdd3-127">Zaznacz nową regułę Kanban na szczycie listy.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="2bdd3-128">Jest to reguła Kanban o najwyższym numerze.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="2bdd3-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2bdd3-130">Kliknij numer reguły Kanban, aby otworzyć regułę.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="2bdd3-131">Modyfikowanie ilości maksymalnej dla nowej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="2bdd3-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="2bdd3-132">W polu Ilość maksymalna ustaw wartość „100”.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="2bdd3-133">Rozwiń skróconą kartę Ilości, aby wyświetlić pole Ilość maksymalna.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="2bdd3-134">Zmiana maksymalnej ilości na 100 pozwoli na przetwarzanie maksymalnie 100 kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="2bdd3-135">Jest to ostatni krok w tym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="2bdd3-135">This is the last step in this task.</span></span>  

