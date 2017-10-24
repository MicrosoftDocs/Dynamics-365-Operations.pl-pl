--- 
title: "Tworzenie reguły Kanban dla zdarzenia wiersza BOM"
description: "To zadanie skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban zdarzenia w celu zapewnienia dostaw dla wierszy BOM produkcji w mieszanym środowisku produkcji oszczędnej i klasycznej."
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 452cc5cf6060b71f91ad43e39e756dc23d759448
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="92b0b-103">Tworzenie reguły Kanban dla zdarzenia wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="92b0b-103">Create a BOM line event kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92b0b-104">To zadanie skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban zdarzenia w celu zapewnienia dostaw dla wierszy BOM produkcji w mieszanym środowisku produkcji oszczędnej i klasycznej.</span><span class="sxs-lookup"><span data-stu-id="92b0b-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="92b0b-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="92b0b-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="92b0b-106">Zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.</span><span class="sxs-lookup"><span data-stu-id="92b0b-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="92b0b-107">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="92b0b-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="92b0b-108">Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="92b0b-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="92b0b-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="92b0b-109">Click New.</span></span>
3. <span data-ttu-id="92b0b-110">W polu Typ zaznacz opcję „Wycofanie”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="92b0b-111">Typ Wycofanie służy do tworzenia zadań Kanban przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="92b0b-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="92b0b-112">W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="92b0b-113">Strategia zdarzenia jest wybierana, aby utworzyć przeniesienie pozycji z kart Kanban na podstawie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="92b0b-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="92b0b-114">W dalszej części przewodnika po zadaniach zainicjujemy tę operację poprzez oszacowanie zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="92b0b-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="92b0b-115">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="92b0b-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="92b0b-116">Wpisz lub wybierz czynność ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="92b0b-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="92b0b-117">To działanie przeniesienia ma magazyn przyjęcia (wyjścia) oraz lokalizację 12, co oznacza, że materiał zostanie przeniesiony do lokalizacji 12 w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="92b0b-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="92b0b-118">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="92b0b-118">Expand the Details section.</span></span>
7. <span data-ttu-id="92b0b-119">W polu Produkt wprowadź lub wybierz wartość M0001.</span><span class="sxs-lookup"><span data-stu-id="92b0b-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="92b0b-120">Rozwiń sekcję Zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="92b0b-120">Expand the Events section.</span></span>
9. <span data-ttu-id="92b0b-121">W polu Zdarzenie wiersza BOM wybierz opcję „Automatyczne”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="92b0b-122">Z ustawieniem Automatyczne w polu Zdarzenie wiersza BOM zostanie utworzone zadanie Kanban, aby zaspokoić potrzeby materiałowe wierszy BOM zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="92b0b-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="92b0b-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="92b0b-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="92b0b-124">Tworzenie i modyfikowanie nowego zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="92b0b-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="92b0b-125">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="92b0b-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="92b0b-126">Kliknij opcję Nowe zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="92b0b-126">Click New production order.</span></span>
3. <span data-ttu-id="92b0b-127">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="92b0b-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="92b0b-128">Wprowadź lub wybierz wartość „L0001”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="92b0b-129">Używamy towaru L0001, ponieważ towar M0001 jest zawarty w BOM towaru L0001.</span><span class="sxs-lookup"><span data-stu-id="92b0b-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="92b0b-130">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="92b0b-130">Click Create.</span></span>
5. <span data-ttu-id="92b0b-131">Na liście kliknij łącze w wierszu towaru L0001.</span><span class="sxs-lookup"><span data-stu-id="92b0b-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="92b0b-132">Kliknij opcję BOM.</span><span class="sxs-lookup"><span data-stu-id="92b0b-132">Click BOM.</span></span>
7. <span data-ttu-id="92b0b-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="92b0b-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="92b0b-134">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="92b0b-134">Click Edit.</span></span>
9. <span data-ttu-id="92b0b-135">W polu Typ wiersza wybierz opcję „Ustalona dostawa”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="92b0b-136">Została wybrana opcja Ustalona dostawa, aby spowodować tworzenie dostaw za pomocą karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="92b0b-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="92b0b-137">W polu Zużycie zasobów wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="92b0b-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="92b0b-138">Wyczyszczenie pola wyboru Zużycie zasobów pozwoli nam zmienić magazyn.</span><span class="sxs-lookup"><span data-stu-id="92b0b-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="92b0b-139">Rozwiń sekcję Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="92b0b-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="92b0b-140">W polu Magazyn wpisz wartość „12”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="92b0b-141">Ustawiono magazyn 12, ponieważ jest to magazyn wyjściowy dla działania wycofania.</span><span class="sxs-lookup"><span data-stu-id="92b0b-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="92b0b-142">W polu Lokalizacja wpisz „12”.</span><span class="sxs-lookup"><span data-stu-id="92b0b-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="92b0b-143">Ustawiono lokalizację 12, ponieważ jest to lokalizacja wyjściowa dla działania wycofania.</span><span class="sxs-lookup"><span data-stu-id="92b0b-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="92b0b-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="92b0b-144">Close the page.</span></span>
15. <span data-ttu-id="92b0b-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="92b0b-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="92b0b-146">Szacowania zlecenia produkcyjnego i wyświetlanie utworzonej karty Kanban</span><span class="sxs-lookup"><span data-stu-id="92b0b-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="92b0b-147">Kliknij przycisk Szacuj.</span><span class="sxs-lookup"><span data-stu-id="92b0b-147">Click Estimate.</span></span>
    * <span data-ttu-id="92b0b-148">Szacowanie zlecenia produkcyjnego wywoła tworzenie powiązanej karty Kanban w celu dostarczenia towaru M0001 .</span><span class="sxs-lookup"><span data-stu-id="92b0b-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="92b0b-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="92b0b-149">Click OK.</span></span>
3. <span data-ttu-id="92b0b-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="92b0b-150">Close the page.</span></span>
4. <span data-ttu-id="92b0b-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="92b0b-151">Close the page.</span></span>
5. <span data-ttu-id="92b0b-152">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="92b0b-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="92b0b-153">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="92b0b-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="92b0b-154">Zaznacz regułę Kanban zdarzenia utworzoną dla towaru M0001.</span><span class="sxs-lookup"><span data-stu-id="92b0b-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="92b0b-155">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="92b0b-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="92b0b-156">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="92b0b-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="92b0b-157">Zwróć uwagę na kartę Kanban utworzoną w celu dostarczenia towaru M0001 dla szacowanego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="92b0b-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="92b0b-158">To jest ostatni krok!</span><span class="sxs-lookup"><span data-stu-id="92b0b-158">This is the last step!</span></span>  


