--- 
title: "Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania"
description: "W tej procedurze pokazano sposób obliczania propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych, a następnie aktualizowania zapotrzebowania na pozycje według danych z propozycji."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ad194efd151dab8c8fe5542cb40de2d811fb4b3d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="dee9a-103">Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="dee9a-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dee9a-104">W tej procedurze pokazano sposób obliczania propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych, a następnie aktualizowania zapotrzebowania na pozycje według danych z propozycji.</span><span class="sxs-lookup"><span data-stu-id="dee9a-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="dee9a-105">Można to zrobić za pomocą arkusza zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="dee9a-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="dee9a-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="dee9a-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="dee9a-107">To zadanie jest przeznaczone dla planisty produkcji i ułatwia mu obsługę minimalnego zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="dee9a-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="dee9a-108">Tworzenie nowego arkusza zapasu bezpieczeństwa</span><span class="sxs-lookup"><span data-stu-id="dee9a-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="dee9a-109">Przejdź do okna Nazwy arkuszy zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="dee9a-109">Go to Safety stock journal names.</span></span>
2. <span data-ttu-id="dee9a-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dee9a-110">Click New.</span></span>
3. <span data-ttu-id="dee9a-111">W polu Nazwa wpisz „Materiał”.</span><span class="sxs-lookup"><span data-stu-id="dee9a-111">In the Name field, type 'Material'.</span></span>
4. <span data-ttu-id="dee9a-112">W polu Opis wpisz „Materiał”.</span><span class="sxs-lookup"><span data-stu-id="dee9a-112">In the Description field, type 'Material'.</span></span>
5. <span data-ttu-id="dee9a-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dee9a-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="dee9a-114">Tworzenie arkusza zapasu bezpieczeństwa</span><span class="sxs-lookup"><span data-stu-id="dee9a-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="dee9a-115">Przejdź do okna Obliczanie zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="dee9a-115">Go to Safety stock calculation.</span></span>
2. <span data-ttu-id="dee9a-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dee9a-116">Click New.</span></span>
3. <span data-ttu-id="dee9a-117">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dee9a-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="dee9a-118">Zaznacz nazwę utworzonego arkusza zapasu bezpieczeństwa, na przykład Materiał.</span><span class="sxs-lookup"><span data-stu-id="dee9a-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="dee9a-119">Kliknij opcję Utwórz wiersze.</span><span class="sxs-lookup"><span data-stu-id="dee9a-119">Click Create lines.</span></span>
5. <span data-ttu-id="dee9a-120">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="dee9a-120">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="dee9a-121">Ustaw datę „2015-01-02”.</span><span class="sxs-lookup"><span data-stu-id="dee9a-121">Set the date to '2015-01-02'.</span></span>  
6. <span data-ttu-id="dee9a-122">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="dee9a-122">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="dee9a-123">Ustaw datę „2015-12-30”.</span><span class="sxs-lookup"><span data-stu-id="dee9a-123">Set the date to '2015-12-30'.</span></span>  
7. <span data-ttu-id="dee9a-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dee9a-124">Click OK.</span></span>
    * <span data-ttu-id="dee9a-125">Spowoduje to utworzenie wierszy dla wymiarów, które mają transakcje magazynowe.</span><span class="sxs-lookup"><span data-stu-id="dee9a-125">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="dee9a-126">Obliczanie propozycji</span><span class="sxs-lookup"><span data-stu-id="dee9a-126">Calculate proposal</span></span>
1. <span data-ttu-id="dee9a-127">Kliknij opcję Obliczanie propozycji.</span><span class="sxs-lookup"><span data-stu-id="dee9a-127">Click Calculate proposal.</span></span>
2. <span data-ttu-id="dee9a-128">Zaznacz opcję Użyj średnich rozchodów w czasie realizacji.</span><span class="sxs-lookup"><span data-stu-id="dee9a-128">Select the Use average issue during lead time option.</span></span>
3. <span data-ttu-id="dee9a-129">W polu Mnożnik ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="dee9a-129">Set Multiplication factor to '10'.</span></span>
    * <span data-ttu-id="dee9a-130">Mnożnik służy do korygowania propozycji.</span><span class="sxs-lookup"><span data-stu-id="dee9a-130">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="dee9a-131">Dane demonstracyjne zawierają tylko kilka transakcji, dlatego należy ustawić współczynnik, aby uzyskać realistyczną propozycję.</span><span class="sxs-lookup"><span data-stu-id="dee9a-131">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="dee9a-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dee9a-132">Click OK.</span></span>
    * <span data-ttu-id="dee9a-133">Przewiń w dół do towarów M0002 i M0003.</span><span class="sxs-lookup"><span data-stu-id="dee9a-133">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="dee9a-134">Wyświetl kolumnę Obliczona minimalna ilość.</span><span class="sxs-lookup"><span data-stu-id="dee9a-134">View the Calculated minimum quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="dee9a-135">Aktualizacja ilości minimalnej</span><span class="sxs-lookup"><span data-stu-id="dee9a-135">Update minimum quantity</span></span>
1. <span data-ttu-id="dee9a-136">W polu Nowa ilość minimalna wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="dee9a-136">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="dee9a-137">Zaktualizuj wartość Nowa ilość minimalna, aby była zgodna z wartością w polu Obliczona minimalna ilość.</span><span class="sxs-lookup"><span data-stu-id="dee9a-137">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="dee9a-138">Jeśli obliczona minimalna ilość wynosi zero, można wprowadzić żądaną wartość przyszłą.</span><span class="sxs-lookup"><span data-stu-id="dee9a-138">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="dee9a-139">Na przykład w tym polu można wprowadzić obliczoną ilość minimalną towaru M0002 powiązanego z magazynem 12.</span><span class="sxs-lookup"><span data-stu-id="dee9a-139">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="dee9a-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dee9a-140">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dee9a-141">Na przykład można wybrać towar M0002 powiązany z magazynem 12.</span><span class="sxs-lookup"><span data-stu-id="dee9a-141">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="dee9a-142">W polu Nowa ilość minimalna wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="dee9a-142">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="dee9a-143">Zaktualizuj wartość Nowa ilość minimalna, aby była zgodna z wartością w polu Obliczona minimalna ilość.</span><span class="sxs-lookup"><span data-stu-id="dee9a-143">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="dee9a-144">Jeśli obliczona minimalna ilość wynosi zero, można wprowadzić żądaną wartość przyszłą.</span><span class="sxs-lookup"><span data-stu-id="dee9a-144">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="dee9a-145">Księgowanie nowej ilości minimalnej i sprawdzanie poprawności wyniku</span><span class="sxs-lookup"><span data-stu-id="dee9a-145">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="dee9a-146">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="dee9a-146">Click Post.</span></span>
2. <span data-ttu-id="dee9a-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dee9a-147">Click OK.</span></span>
3. <span data-ttu-id="dee9a-148">Kliknij, aby otworzyć łącze znajdujące się w polu Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="dee9a-148">Click to follow the link in the Item number field.</span></span>
4. <span data-ttu-id="dee9a-149">Kliknij, aby otworzyć łącze znajdujące się w polu Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="dee9a-149">Click to follow the link in the Item number field.</span></span>
5. <span data-ttu-id="dee9a-150">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="dee9a-150">On the Action Pane, click Plan.</span></span>
6. <span data-ttu-id="dee9a-151">Kliknij opcję Zapotrzebowanie na towary.</span><span class="sxs-lookup"><span data-stu-id="dee9a-151">Click Item coverage.</span></span>
    * <span data-ttu-id="dee9a-152">Zwróć uwagę, że pole Ilość minimalna zostało zaktualizowane o nową ilość minimalną z arkusza zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="dee9a-152">Notice that the Minimum quantity has been updated with the new minimum quantity from the safety stock journal.</span></span>  


