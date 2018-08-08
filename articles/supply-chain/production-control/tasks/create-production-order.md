---
title: Tworzenie zlecenia produkcyjnego
description: "W tej procedurze pokazano sposób tworzenia zlecenia produkcyjnego."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 929864a22db2e9fbfcdbeb8f963bac2293612cfb
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-production-order"></a><span data-ttu-id="d9c23-103">Tworzenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="d9c23-103">Create a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d9c23-104">W tej procedurze pokazano sposób tworzenia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="d9c23-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d9c23-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d9c23-106">Jest to pierwsza z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="d9c23-107">Tworzenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="d9c23-107">Create a production order</span></span>
1. <span data-ttu-id="d9c23-108">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="d9c23-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="d9c23-109">Kliknij opcję Nowe zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="d9c23-109">Click New production order.</span></span>
3. <span data-ttu-id="d9c23-110">W polu Numer pozycji wpisz „D0001”.</span><span class="sxs-lookup"><span data-stu-id="d9c23-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="d9c23-111">W polu Dostawa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="d9c23-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="d9c23-112">Data dostawy wskazuje, kiedy zlecenie produkcyjne powinno się zakończyć, aby dostawa nastąpiła w na czas.</span><span class="sxs-lookup"><span data-stu-id="d9c23-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="d9c23-113">Ta data może być wykorzystywana w procesie planowania.</span><span class="sxs-lookup"><span data-stu-id="d9c23-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="d9c23-114">Na przykład można zaplanować zlecenie z datą wsteczną względem daty dostawy.</span><span class="sxs-lookup"><span data-stu-id="d9c23-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="d9c23-115">W polu Ilość wpisz wartość 20.</span><span class="sxs-lookup"><span data-stu-id="d9c23-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="d9c23-116">Uwaga: W polu Numer BOM jest automatycznie wyświetlana liczba wszystkich aktywnych BOM bieżącego towaru, ale można zmienić BOM zlecenia produkcyjnego, wybierając aktywny BOM z listy zatwierdzonych wersji BOM.</span><span class="sxs-lookup"><span data-stu-id="d9c23-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="d9c23-117">W polu Numer marszruty jest automatycznie wyświetlana liczba wszystkich aktywnych marszrut bieżącego towaru, ale można zmienić marszrutę zlecenia produkcyjnego, wybierając aktywną marszrutę z listy zatwierdzonych wersji marszruty.</span><span class="sxs-lookup"><span data-stu-id="d9c23-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="d9c23-118">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="d9c23-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="d9c23-119">Weryfikacja zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="d9c23-119">Validate the production order</span></span>
1. <span data-ttu-id="d9c23-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d9c23-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d9c23-121">Kliknij łącze do numeru nowo utworzonego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="d9c23-122">Spowoduje to otwarcie strony szczegółów zlecenia.</span><span class="sxs-lookup"><span data-stu-id="d9c23-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="d9c23-123">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d9c23-123">Click Edit.</span></span>
3. <span data-ttu-id="d9c23-124">W polu Dostawa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="d9c23-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="d9c23-125">Na przykład można zmienić datę dostawy zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="d9c23-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d9c23-126">Click Save.</span></span>
5. <span data-ttu-id="d9c23-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9c23-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="d9c23-128">Aktualizacja BOM</span><span class="sxs-lookup"><span data-stu-id="d9c23-128">Update the BOM</span></span>
1. <span data-ttu-id="d9c23-129">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="d9c23-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="d9c23-130">Kliknij opcję BOM.</span><span class="sxs-lookup"><span data-stu-id="d9c23-130">Click BOM.</span></span>
    * <span data-ttu-id="d9c23-131">Otwórz stronę BOM, aby sprawdzić poprawność danych BOM, które zostały skopiowane z domyślnych danych podczas tworzenia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="d9c23-132">W tej procedurze należy zaktualizować ilość w BOM.</span><span class="sxs-lookup"><span data-stu-id="d9c23-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="d9c23-133">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d9c23-133">Click Edit.</span></span>
4. <span data-ttu-id="d9c23-134">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="d9c23-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="d9c23-135">Zmiana ilości w wierszu BOM ma wpływ na szacowane koszty zużycia materiałów dla zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="d9c23-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d9c23-136">Click Save.</span></span>
6. <span data-ttu-id="d9c23-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9c23-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="d9c23-138">Aktualizacja marszruty produkcji</span><span class="sxs-lookup"><span data-stu-id="d9c23-138">Update the production route</span></span>
1. <span data-ttu-id="d9c23-139">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="d9c23-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="d9c23-140">Kliknij opcję Marszruta.</span><span class="sxs-lookup"><span data-stu-id="d9c23-140">Click Route.</span></span>
    * <span data-ttu-id="d9c23-141">Otwórz stronę Marszruta, aby sprawdzić poprawność danych marszruty produkcji, które zostały skopiowane z domyślnych danych podczas tworzenia zlecenia.</span><span class="sxs-lookup"><span data-stu-id="d9c23-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="d9c23-142">W tej procedurze należy zaktualizować ilość w jednej operacji w marszrucie produkcji.</span><span class="sxs-lookup"><span data-stu-id="d9c23-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="d9c23-143">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d9c23-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d9c23-144">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d9c23-144">Click Edit.</span></span>
5. <span data-ttu-id="d9c23-145">W polu Ilość z procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d9c23-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="d9c23-146">Zmiana czasu procesu wpływa na szacowane zużycie w marszrucie i koszt zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9c23-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="d9c23-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d9c23-147">Click Save.</span></span>
7. <span data-ttu-id="d9c23-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9c23-148">Close the page.</span></span>

