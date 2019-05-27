---
title: Tworzenie reguły Kanban dla wypłaty
description: W tej procedurze pokazano konfigurację niezbędną do utworzenia reguły Kanban wycofania w celu przeniesienia materiałów w środowisku produkcji oszczędnej.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a77c66b64512274f2703543293c2f48f2df2acf5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570154"
---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="e6bb8-103">Tworzenie reguły Kanban dla wypłaty</span><span class="sxs-lookup"><span data-stu-id="e6bb8-103">Create a withdrawal kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e6bb8-104">W tej procedurze pokazano konfigurację niezbędną do utworzenia reguły Kanban wycofania w celu przeniesienia materiałów w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="e6bb8-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e6bb8-106">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni uzupełnienie zapasów nowego lub zmodyfikowanego materiału.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="e6bb8-107">Tworzenie nowej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="e6bb8-107">Create new kanban rule</span></span>
1. <span data-ttu-id="e6bb8-108">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="e6bb8-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-109">Click New.</span></span>
3. <span data-ttu-id="e6bb8-110">W polu Typ zaznacz opcję „Wycofanie”.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="e6bb8-111">Typ Wycofanie jest używany w regułach Kanban do przenoszenia materiałów lub towarów.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="e6bb8-112">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="e6bb8-113">Wybierz opcję ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="e6bb8-114">Konfiguracja tego działania przewiduje przeniesienie składników z lokalizacji 11 w magazynie 11 do lokalizacji 12 w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="e6bb8-115">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="e6bb8-116">Wybierz opcję M0007.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-116">Select M0007.</span></span>  
6. <span data-ttu-id="e6bb8-117">W polu Czas realizacji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="e6bb8-118">Na przykład 60.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-118">For example, 60.</span></span>  
7. <span data-ttu-id="e6bb8-119">W polu Jednostka miary wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="e6bb8-120">Na przykład Minuty.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="e6bb8-121">Ustawianie ilości dla karty Kanban</span><span class="sxs-lookup"><span data-stu-id="e6bb8-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="e6bb8-122">W polu Ilość domyślna ustaw wartość „5”.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="e6bb8-123">Jest to ilość, która zostanie przeniesiona za pomocą każdej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="e6bb8-124">W polu Stała liczba kart Kanban wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="e6bb8-125">Jest to ilość kart Kanban, które powinny być aktywne.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="e6bb8-126">W tym przypadku 2 karty Kanban przenoszą każda po 5 sztuk.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="e6bb8-127">W polu Minimum graniczne alertu wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="e6bb8-128">Służy do śledzenia minimalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="e6bb8-129">Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="e6bb8-130">W polu Maksimum graniczne alertu wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="e6bb8-131">Służy do śledzenia maksymalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="e6bb8-132">Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="e6bb8-133">Tworzenie kart Kanban</span><span class="sxs-lookup"><span data-stu-id="e6bb8-133">Create kanbans</span></span>
1. <span data-ttu-id="e6bb8-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-134">Click Save.</span></span>
    * <span data-ttu-id="e6bb8-135">Aby można było tworzyć karty Kanban, musi być zapisana reguła Kanban.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="e6bb8-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-136">Click Add.</span></span>
    * <span data-ttu-id="e6bb8-137">Należy zauważyć, że nie ma żadnych aktywnych kart Kanban, ponieważ sugerowana wartość w polu „Liczba nowych kart Kanban” wynosi 2, czyli jest równa wartości w polu „Stała liczba kart Kanban”.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="e6bb8-138">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-138">Click Create.</span></span>
    * <span data-ttu-id="e6bb8-139">Spowoduje to utworzenie 2 kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="e6bb8-140">Należy zwrócić uwagę, że dla tej reguły Kanban wycofania zostały utworzone 2 karty Kanban, każda na 5 sztuk.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="e6bb8-141">Jest to ostatni krok w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-141">This is the last step in this procedure.</span></span>  

