---
title: Tworzenie reguły Kanban przy użyciu zdarzenia minimalnych zapasów
description: Ta procedura skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban za pomocą zdarzenia minimalnych zapasów, aby upewnić się, że określony produkt jest zawsze dostępny w określonej lokalizacji.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b578a664e9e3b6496e5665b2eefd9d75f86ecc3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837837"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="4944d-103">Tworzenie reguły Kanban przy użyciu zdarzenia minimalnych zapasów</span><span class="sxs-lookup"><span data-stu-id="4944d-103">Create a kanban rule using a minimum stock event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4944d-104">Ta procedura skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban za pomocą zdarzenia minimalnych zapasów, aby upewnić się, że określony produkt jest zawsze dostępny w określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4944d-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="4944d-105">Reguła kanban jest tworzona w celu przenoszenia materiału do lokalizacji, gdy poziom zapasów spadnie poniżej 200 sztuk.</span><span class="sxs-lookup"><span data-stu-id="4944d-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="4944d-106">Uruchomienie przetwarzania powiązania zlecenia z popytem źródłowym powoduje utworzenie niezbędnych kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="4944d-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="4944d-107">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4944d-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="4944d-108">To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="4944d-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="4944d-109">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="4944d-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="4944d-110">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="4944d-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="4944d-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4944d-111">Click New.</span></span>
3. <span data-ttu-id="4944d-112">W polu Typ zaznacz opcję „Wycofanie”.</span><span class="sxs-lookup"><span data-stu-id="4944d-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="4944d-113">Ten typ służy do tworzenia kart Kanban przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="4944d-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="4944d-114">W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="4944d-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="4944d-115">Strategia zdarzenia służy do tworzenia kart Kanban przeniesienia na podstawie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4944d-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="4944d-116">W dalszej części procedury zainicjujesz karty Kanban przeniesienia przy użyciu procesu uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="4944d-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="4944d-117">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4944d-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="4944d-118">Wpisz lub wybierz czynność ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="4944d-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="4944d-119">To działanie przeniesienia ma magazyn przyjęcia (wyjścia) oraz lokalizację 12, co oznacza, że materiały zostaną przeniesione do lokalizacji 12 w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="4944d-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="4944d-120">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="4944d-120">Expand the Details section.</span></span>
7. <span data-ttu-id="4944d-121">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4944d-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="4944d-122">Wybierz opcję M0007.</span><span class="sxs-lookup"><span data-stu-id="4944d-122">Select M0007.</span></span>  
8. <span data-ttu-id="4944d-123">Rozwiń sekcję Zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4944d-123">Expand the Events section.</span></span>
9. <span data-ttu-id="4944d-124">W polu Zdarzenie uzupełniania zapasów wybierz opcję „Partia”.</span><span class="sxs-lookup"><span data-stu-id="4944d-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="4944d-125">Spowoduje to utworzenie kart Kanban w celu zaspokojenia potrzeb materiałowych w powiązanej lokalizacji podczas przetwarzania powiązania zlecenia z popytem źródłowym.</span><span class="sxs-lookup"><span data-stu-id="4944d-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="4944d-126">Ustawianie minimalnej ilości pozycji</span><span class="sxs-lookup"><span data-stu-id="4944d-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="4944d-127">Kliknij, aby śledzić łącze w polu Produkt.</span><span class="sxs-lookup"><span data-stu-id="4944d-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="4944d-128">Kliknij, aby otworzyć łącze znajdujące się w polu Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="4944d-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="4944d-129">Rozwiń pole informacji Obraz produktu.</span><span class="sxs-lookup"><span data-stu-id="4944d-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="4944d-130">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="4944d-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="4944d-131">Kliknij opcję Zapotrzebowanie na towary.</span><span class="sxs-lookup"><span data-stu-id="4944d-131">Click Item coverage.</span></span>
6. <span data-ttu-id="4944d-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4944d-132">Click New.</span></span>
7. <span data-ttu-id="4944d-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="4944d-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="4944d-134">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4944d-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="4944d-135">W polu Magazyn ustaw 12.</span><span class="sxs-lookup"><span data-stu-id="4944d-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="4944d-136">W polu Minimum ustaw wartość „200”.</span><span class="sxs-lookup"><span data-stu-id="4944d-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="4944d-137">Wykonywanie zadania tworzenia partii dla zdarzenia</span><span class="sxs-lookup"><span data-stu-id="4944d-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="4944d-138">Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Przetwarzanie wsadowe zadań Kanban > Przetwarzanie powiązań zlecenia z popytem źródłowym.</span><span class="sxs-lookup"><span data-stu-id="4944d-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="4944d-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4944d-139">Click OK.</span></span>
3. <span data-ttu-id="4944d-140">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="4944d-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="4944d-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4944d-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4944d-142">Wybierz utworzoną wcześniej regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="4944d-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="4944d-143">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="4944d-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="4944d-144">Należy zauważyć, że została utworzona karta Kanban w celu przeniesienia potrzebnego materiału do magazynu 12.</span><span class="sxs-lookup"><span data-stu-id="4944d-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  

