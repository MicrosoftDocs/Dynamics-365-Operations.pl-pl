---
title: Tworzenie reguły Kanban ze stałą ilością dla produkcji
description: Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia stałej reguły Kanban produkcji w celu wyzwalania działań przekształcających w komórce roboczej w środowisku produkcji oszczędnej.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ece72971d2bc67482cbdda4fb0d1b3176a3f3071
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829193"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="4cead-103">Tworzenie reguły Kanban ze stałą ilością dla produkcji</span><span class="sxs-lookup"><span data-stu-id="4cead-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4cead-104">Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia stałej reguły Kanban produkcji w celu wyzwalania działań przekształcających w komórce roboczej w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="4cead-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="4cead-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4cead-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4cead-106">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.</span><span class="sxs-lookup"><span data-stu-id="4cead-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="4cead-107">Tworzenie nowej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="4cead-107">Create new kanban rule</span></span>
1. <span data-ttu-id="4cead-108">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="4cead-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4cead-109">Click New.</span></span>
    * <span data-ttu-id="4cead-110">Zauważ, że domyślnym typem jest Produkcja, a pole Strategia uzupełniania ma wartość Stały.</span><span class="sxs-lookup"><span data-stu-id="4cead-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="4cead-111">Nie trzeba zmieniać tych parametrów.</span><span class="sxs-lookup"><span data-stu-id="4cead-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="4cead-112">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4cead-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="4cead-113">Jest to działanie, które będzie wykonywane dla kart Kanban opartych na tej regule Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="4cead-114">Wybierz opcję „SpeakerTestAndPackaging”.</span><span class="sxs-lookup"><span data-stu-id="4cead-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="4cead-115">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="4cead-115">Expand the Details section.</span></span>
5. <span data-ttu-id="4cead-116">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4cead-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="4cead-117">Wybierz opcję L0050.</span><span class="sxs-lookup"><span data-stu-id="4cead-117">Select L0050.</span></span>  
6. <span data-ttu-id="4cead-118">W polu Jednostka miary wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4cead-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="4cead-119">Wybierz opcję Minuty.</span><span class="sxs-lookup"><span data-stu-id="4cead-119">Select minutes.</span></span>  
7. <span data-ttu-id="4cead-120">W polu Czas realizacji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4cead-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="4cead-121">Wpisz 5.</span><span class="sxs-lookup"><span data-stu-id="4cead-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="4cead-122">Konfigurowanie ilości</span><span class="sxs-lookup"><span data-stu-id="4cead-122">Set quantities</span></span>
1. <span data-ttu-id="4cead-123">Rozwiń sekcję Ilości.</span><span class="sxs-lookup"><span data-stu-id="4cead-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="4cead-124">W polu Ilość domyślna ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="4cead-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="4cead-125">Jest to ilość, która zostanie przeniesiona za pomocą każdej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="4cead-126">Zaznacz pole wyboru Odchylenie ilości produktów.</span><span class="sxs-lookup"><span data-stu-id="4cead-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="4cead-127">Dzięki temu zaznaczone karty Kanban można wypełnić z odchyleniem od domyślnej ilości.</span><span class="sxs-lookup"><span data-stu-id="4cead-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="4cead-128">Aby umożliwić wypełnianie kart Kanban ilościami od 8 do 12, ustaw dla obu odchyleń wartość 2.</span><span class="sxs-lookup"><span data-stu-id="4cead-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="4cead-129">W polu Odchylenie poniżej ustaw wartość „2”.</span><span class="sxs-lookup"><span data-stu-id="4cead-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="4cead-130">Umożliwi to wypełnienie ilością 10-2 = 8.</span><span class="sxs-lookup"><span data-stu-id="4cead-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="4cead-131">W polu Odchylenie powyżej ustaw wartość „2”.</span><span class="sxs-lookup"><span data-stu-id="4cead-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="4cead-132">Umożliwi to wypełnienie ilością 10+2 = 12.</span><span class="sxs-lookup"><span data-stu-id="4cead-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="4cead-133">W polu Stała liczba kart Kanban wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="4cead-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="4cead-134">Jest to ilość kart Kanban, które powinny być aktywne.</span><span class="sxs-lookup"><span data-stu-id="4cead-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="4cead-135">W tym przypadku jest to 5 kart Kanban, każda na ilość 10.</span><span class="sxs-lookup"><span data-stu-id="4cead-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="4cead-136">W polu Minimum graniczne alertu wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="4cead-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="4cead-137">Służy do śledzenia minimalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="4cead-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="4cead-138">Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="4cead-139">W polu Maksimum graniczne alertu wpisz „4”.</span><span class="sxs-lookup"><span data-stu-id="4cead-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="4cead-140">Służy do śledzenia maksymalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="4cead-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="4cead-141">Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="4cead-142">W polu Ilość w automatycznym planowaniu wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="4cead-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="4cead-143">Ustawienie wartości 1 oznacza, że każda karta kanban będzie automatycznie planowana.</span><span class="sxs-lookup"><span data-stu-id="4cead-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="4cead-144">Jeśli wprowadzono by liczbę 3, karty Kanban byłyby planowane dopiero wtedy, gdy istniałyby 3 puste karty Kanban gotowe do planowania.</span><span class="sxs-lookup"><span data-stu-id="4cead-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="4cead-145">Jest to przydatne do grupowania pracy i unikania zbyt wielu czynności konfiguracyjnych.</span><span class="sxs-lookup"><span data-stu-id="4cead-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="4cead-146">Tworzenie kart Kanban</span><span class="sxs-lookup"><span data-stu-id="4cead-146">Create Kanbans</span></span>
1. <span data-ttu-id="4cead-147">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="4cead-148">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4cead-148">Click Save.</span></span>
    * <span data-ttu-id="4cead-149">Aby można było tworzyć karty Kanban, musi być zapisana reguła Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="4cead-150">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="4cead-150">Click Add.</span></span>
    * <span data-ttu-id="4cead-151">Należy zauważyć, że nie ma żadnych aktywnych kart Kanban. Z tego powodu sugerowana wartość w polu „Liczba nowych kart Kanban” wynosi 5.</span><span class="sxs-lookup"><span data-stu-id="4cead-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="4cead-152">Jest to równe wartości w polu „Stała liczba kart Kanban”.</span><span class="sxs-lookup"><span data-stu-id="4cead-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="4cead-153">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="4cead-153">Click Create.</span></span>
    * <span data-ttu-id="4cead-154">Spowoduje to utworzenie 5 kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="4cead-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="4cead-155">Należy zwrócić uwagę, że dla tej reguły Kanban produkcji zostało utworzonych 5 kart Kanban, każda na 10 sztuk.</span><span class="sxs-lookup"><span data-stu-id="4cead-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="4cead-156">Jest to ostatni krok w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="4cead-156">This is the last step in this procedure.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]