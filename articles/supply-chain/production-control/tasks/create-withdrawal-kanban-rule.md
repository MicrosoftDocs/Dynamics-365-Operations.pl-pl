---
title: Tworzenie reguły Kanban dla wypłaty
description: W tej procedurze pokazano konfigurację niezbędną do utworzenia reguły Kanban wycofania w celu przeniesienia materiałów w środowisku produkcji oszczędnej.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1694472e20c28a0b0f94c1ced8544b7258c22b40
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007098"
---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="f4882-103">Tworzenie reguły Kanban dla wypłaty</span><span class="sxs-lookup"><span data-stu-id="f4882-103">Create a withdrawal kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f4882-104">W tej procedurze pokazano konfigurację niezbędną do utworzenia reguły Kanban wycofania w celu przeniesienia materiałów w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="f4882-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="f4882-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f4882-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f4882-106">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni uzupełnienie zapasów nowego lub zmodyfikowanego materiału.</span><span class="sxs-lookup"><span data-stu-id="f4882-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="f4882-107">Tworzenie nowej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="f4882-107">Create new kanban rule</span></span>
1. <span data-ttu-id="f4882-108">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="f4882-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="f4882-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f4882-109">Click New.</span></span>
3. <span data-ttu-id="f4882-110">W polu Typ zaznacz opcję „Wycofanie”.</span><span class="sxs-lookup"><span data-stu-id="f4882-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="f4882-111">Typ Wycofanie jest używany w regułach Kanban do przenoszenia materiałów lub towarów.</span><span class="sxs-lookup"><span data-stu-id="f4882-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="f4882-112">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f4882-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="f4882-113">Wybierz opcję ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="f4882-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="f4882-114">Konfiguracja tego działania przewiduje przeniesienie składników z lokalizacji 11 w magazynie 11 do lokalizacji 12 w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="f4882-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="f4882-115">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f4882-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="f4882-116">Wybierz opcję M0007.</span><span class="sxs-lookup"><span data-stu-id="f4882-116">Select M0007.</span></span>  
6. <span data-ttu-id="f4882-117">W polu Czas realizacji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f4882-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="f4882-118">Na przykład 60.</span><span class="sxs-lookup"><span data-stu-id="f4882-118">For example, 60.</span></span>  
7. <span data-ttu-id="f4882-119">W polu Jednostka miary wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f4882-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="f4882-120">Na przykład Minuty.</span><span class="sxs-lookup"><span data-stu-id="f4882-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="f4882-121">Ustawianie ilości dla karty Kanban</span><span class="sxs-lookup"><span data-stu-id="f4882-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="f4882-122">W polu Ilość domyślna ustaw wartość „5”.</span><span class="sxs-lookup"><span data-stu-id="f4882-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="f4882-123">Jest to ilość, która zostanie przeniesiona za pomocą każdej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="f4882-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="f4882-124">W polu Stała liczba kart Kanban wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="f4882-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="f4882-125">Jest to ilość kart Kanban, które powinny być aktywne.</span><span class="sxs-lookup"><span data-stu-id="f4882-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="f4882-126">W tym przypadku 2 karty Kanban przenoszą każda po 5 sztuk.</span><span class="sxs-lookup"><span data-stu-id="f4882-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="f4882-127">W polu Minimum graniczne alertu wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="f4882-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="f4882-128">Służy do śledzenia minimalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="f4882-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="f4882-129">Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="f4882-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="f4882-130">W polu Maksimum graniczne alertu wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="f4882-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="f4882-131">Służy do śledzenia maksymalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="f4882-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="f4882-132">Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="f4882-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="f4882-133">Tworzenie kart Kanban</span><span class="sxs-lookup"><span data-stu-id="f4882-133">Create kanbans</span></span>
1. <span data-ttu-id="f4882-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f4882-134">Click Save.</span></span>
    * <span data-ttu-id="f4882-135">Aby można było tworzyć karty Kanban, musi być zapisana reguła Kanban.</span><span class="sxs-lookup"><span data-stu-id="f4882-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="f4882-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f4882-136">Click Add.</span></span>
    * <span data-ttu-id="f4882-137">Należy zauważyć, że nie ma żadnych aktywnych kart Kanban, ponieważ sugerowana wartość w polu „Liczba nowych kart Kanban” wynosi 2, czyli jest równa wartości w polu „Stała liczba kart Kanban”.</span><span class="sxs-lookup"><span data-stu-id="f4882-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="f4882-138">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="f4882-138">Click Create.</span></span>
    * <span data-ttu-id="f4882-139">Spowoduje to utworzenie 2 kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="f4882-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="f4882-140">Należy zwrócić uwagę, że dla tej reguły Kanban wycofania zostały utworzone 2 karty Kanban, każda na 5 sztuk.</span><span class="sxs-lookup"><span data-stu-id="f4882-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="f4882-141">Jest to ostatni krok w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="f4882-141">This is the last step in this procedure.</span></span>  

