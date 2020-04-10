---
title: Tworzenie reguły Kanban dla zdarzenia wiersza BOM
description: To zadanie skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban zdarzenia w celu zapewnienia dostaw dla wierszy BOM produkcji w mieszanym środowisku produkcji oszczędnej i klasycznej.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fefb33d568153670dbcb92db478e33db806809fc
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147107"
---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="3dc18-103">Tworzenie reguły Kanban dla zdarzenia wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="3dc18-103">Create a BOM line event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3dc18-104">To zadanie skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban zdarzenia w celu zapewnienia dostaw dla wierszy BOM produkcji w mieszanym środowisku produkcji oszczędnej i klasycznej.</span><span class="sxs-lookup"><span data-stu-id="3dc18-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="3dc18-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3dc18-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="3dc18-106">Zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.</span><span class="sxs-lookup"><span data-stu-id="3dc18-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="3dc18-107">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="3dc18-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="3dc18-108">Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="3dc18-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="3dc18-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3dc18-109">Click New.</span></span>
3. <span data-ttu-id="3dc18-110">W polu Typ zaznacz opcję „Wycofanie”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="3dc18-111">Typ Wycofanie służy do tworzenia zadań Kanban przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="3dc18-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="3dc18-112">W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="3dc18-113">Strategia zdarzenia jest wybierana, aby utworzyć przeniesienie pozycji z kart Kanban na podstawie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="3dc18-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="3dc18-114">W dalszej części przewodnika po zadaniach zainicjujemy tę operację poprzez oszacowanie zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="3dc18-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="3dc18-115">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dc18-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="3dc18-116">Wpisz lub wybierz czynność ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="3dc18-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="3dc18-117">To działanie przeniesienia ma magazyn przyjęcia (wyjścia) oraz lokalizację 12, co oznacza, że materiał zostanie przeniesiony do lokalizacji 12 w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="3dc18-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="3dc18-118">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="3dc18-118">Expand the Details section.</span></span>
7. <span data-ttu-id="3dc18-119">W polu Produkt wprowadź lub wybierz wartość M0001.</span><span class="sxs-lookup"><span data-stu-id="3dc18-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="3dc18-120">Rozwiń sekcję Zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="3dc18-120">Expand the Events section.</span></span>
9. <span data-ttu-id="3dc18-121">W polu Zdarzenie wiersza BOM wybierz opcję „Automatyczne”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="3dc18-122">Z ustawieniem Automatyczne w polu Zdarzenie wiersza BOM zostanie utworzone zadanie Kanban, aby zaspokoić potrzeby materiałowe wierszy BOM zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="3dc18-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="3dc18-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3dc18-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="3dc18-124">Tworzenie i modyfikowanie nowego zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="3dc18-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="3dc18-125">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="3dc18-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="3dc18-126">Kliknij opcję Nowe zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="3dc18-126">Click New production order.</span></span>
3. <span data-ttu-id="3dc18-127">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dc18-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="3dc18-128">Wprowadź lub wybierz wartość „L0001”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="3dc18-129">Używamy towaru L0001, ponieważ towar M0001 jest zawarty w BOM towaru L0001.</span><span class="sxs-lookup"><span data-stu-id="3dc18-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="3dc18-130">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="3dc18-130">Click Create.</span></span>
5. <span data-ttu-id="3dc18-131">Na liście kliknij łącze w wierszu towaru L0001.</span><span class="sxs-lookup"><span data-stu-id="3dc18-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="3dc18-132">Kliknij opcję BOM.</span><span class="sxs-lookup"><span data-stu-id="3dc18-132">Click BOM.</span></span>
7. <span data-ttu-id="3dc18-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3dc18-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="3dc18-134">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="3dc18-134">Click Edit.</span></span>
9. <span data-ttu-id="3dc18-135">W polu Typ wiersza wybierz opcję „Ustalona dostawa”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="3dc18-136">Została wybrana opcja Ustalona dostawa, aby spowodować tworzenie dostaw za pomocą karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="3dc18-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="3dc18-137">W polu Zużycie zasobów wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="3dc18-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="3dc18-138">Wyczyszczenie pola wyboru Zużycie zasobów pozwoli nam zmienić magazyn.</span><span class="sxs-lookup"><span data-stu-id="3dc18-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="3dc18-139">Rozwiń sekcję Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="3dc18-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="3dc18-140">W polu Magazyn wpisz wartość „12”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="3dc18-141">Ustawiono magazyn 12, ponieważ jest to magazyn wyjściowy dla działania wycofania.</span><span class="sxs-lookup"><span data-stu-id="3dc18-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="3dc18-142">W polu Lokalizacja wpisz „12”.</span><span class="sxs-lookup"><span data-stu-id="3dc18-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="3dc18-143">Ustawiono lokalizację 12, ponieważ jest to lokalizacja wyjściowa dla działania wycofania.</span><span class="sxs-lookup"><span data-stu-id="3dc18-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="3dc18-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3dc18-144">Close the page.</span></span>
15. <span data-ttu-id="3dc18-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3dc18-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="3dc18-146">Szacowania zlecenia produkcyjnego i wyświetlanie utworzonej karty Kanban</span><span class="sxs-lookup"><span data-stu-id="3dc18-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="3dc18-147">Kliknij przycisk Szacuj.</span><span class="sxs-lookup"><span data-stu-id="3dc18-147">Click Estimate.</span></span>
    * <span data-ttu-id="3dc18-148">Szacowanie zlecenia produkcyjnego wywoła tworzenie powiązanej karty Kanban w celu dostarczenia towaru M0001 .</span><span class="sxs-lookup"><span data-stu-id="3dc18-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="3dc18-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3dc18-149">Click OK.</span></span>
3. <span data-ttu-id="3dc18-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3dc18-150">Close the page.</span></span>
4. <span data-ttu-id="3dc18-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3dc18-151">Close the page.</span></span>
5. <span data-ttu-id="3dc18-152">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="3dc18-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="3dc18-153">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3dc18-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3dc18-154">Zaznacz regułę Kanban zdarzenia utworzoną dla towaru M0001.</span><span class="sxs-lookup"><span data-stu-id="3dc18-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="3dc18-155">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="3dc18-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="3dc18-156">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3dc18-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3dc18-157">Zwróć uwagę na kartę Kanban utworzoną w celu dostarczenia towaru M0001 dla szacowanego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="3dc18-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="3dc18-158">To jest ostatni krok!</span><span class="sxs-lookup"><span data-stu-id="3dc18-158">This is the last step!</span></span>  

