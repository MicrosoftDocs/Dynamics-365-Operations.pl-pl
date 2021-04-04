---
title: Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania
description: W tej procedurze pokazano sposób obliczania propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych, a następnie aktualizowania zapotrzebowania na pozycje według danych z propozycji.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95dec1dba97923e58cfb603434a01cab6f66a3de
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252805"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="17986-103">Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="17986-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="17986-104">W tej procedurze pokazano sposób obliczania propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych, a następnie aktualizowania zapotrzebowania na pozycje według danych z propozycji.</span><span class="sxs-lookup"><span data-stu-id="17986-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="17986-105">Można to zrobić za pomocą arkusza zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="17986-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="17986-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="17986-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="17986-107">To zadanie jest przeznaczone dla planisty produkcji i ułatwia mu obsługę minimalnego zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="17986-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="17986-108">Tworzenie nowego arkusza zapasu bezpieczeństwa</span><span class="sxs-lookup"><span data-stu-id="17986-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="17986-109">W **Okienku nawigacji** otwórz **Planowanie główne > Konfiguracja > Nazwy arkuszy zapasu bezpieczeństwa**.</span><span class="sxs-lookup"><span data-stu-id="17986-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="17986-110">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="17986-110">Click **New**.</span></span>
3. <span data-ttu-id="17986-111">W polu **Nazwa** wpisz „Materiał”.</span><span class="sxs-lookup"><span data-stu-id="17986-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="17986-112">W polu **Opis** wpisz „Materiał”.</span><span class="sxs-lookup"><span data-stu-id="17986-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="17986-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="17986-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="17986-114">Tworzenie arkusza zapasu bezpieczeństwa</span><span class="sxs-lookup"><span data-stu-id="17986-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="17986-115">W **okienku nawigacji** przejdź do **Planowanie główne > Planowanie główne > Uruchom > Obliczanie zapasu bezpieczeństwa**.</span><span class="sxs-lookup"><span data-stu-id="17986-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="17986-116">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="17986-116">Click **New**.</span></span>
3. <span data-ttu-id="17986-117">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="17986-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="17986-118">Zaznacz nazwę utworzonego arkusza zapasu bezpieczeństwa, na przykład Materiał.</span><span class="sxs-lookup"><span data-stu-id="17986-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="17986-119">Kliknij opcję **Utwórz wiersze**.</span><span class="sxs-lookup"><span data-stu-id="17986-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="17986-120">W polu **Od dnia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="17986-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="17986-121">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="17986-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="17986-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="17986-122">Click **OK**.</span></span> <span data-ttu-id="17986-123">Spowoduje to utworzenie wierszy dla wymiarów, które mają transakcje magazynowe.</span><span class="sxs-lookup"><span data-stu-id="17986-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="17986-124">Obliczanie propozycji</span><span class="sxs-lookup"><span data-stu-id="17986-124">Calculate proposal</span></span>
1. <span data-ttu-id="17986-125">Kliknij opcję **Obliczanie propozycji**.</span><span class="sxs-lookup"><span data-stu-id="17986-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="17986-126">Zaznacz opcję **Użyj średnich rozchodów w czasie realizacji**.</span><span class="sxs-lookup"><span data-stu-id="17986-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="17986-127">W polu **Mnożnik** ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="17986-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="17986-128">Mnożnik służy do korygowania propozycji.</span><span class="sxs-lookup"><span data-stu-id="17986-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="17986-129">Dane demonstracyjne zawierają tylko kilka transakcji, dlatego należy ustawić współczynnik, aby uzyskać realistyczną propozycję.</span><span class="sxs-lookup"><span data-stu-id="17986-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="17986-130">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="17986-130">Click **OK**.</span></span> <span data-ttu-id="17986-131">Przewiń w dół do towarów M0002 i M0003.</span><span class="sxs-lookup"><span data-stu-id="17986-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="17986-132">Wyświetl kolumnę **Obliczona minimalna** ilość.</span><span class="sxs-lookup"><span data-stu-id="17986-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="17986-133">Aktualizacja ilości minimalnej</span><span class="sxs-lookup"><span data-stu-id="17986-133">Update minimum quantity</span></span>
1. <span data-ttu-id="17986-134">W polu **Nowa ilość minimalna** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="17986-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="17986-135">Zaktualizuj wartość Nowa ilość minimalna, aby była zgodna z wartością w polu Obliczona minimalna ilość.</span><span class="sxs-lookup"><span data-stu-id="17986-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="17986-136">Jeśli obliczona minimalna ilość wynosi zero, można wprowadzić żądaną wartość przyszłą.</span><span class="sxs-lookup"><span data-stu-id="17986-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="17986-137">Na przykład w tym polu można wprowadzić obliczoną ilość minimalną towaru M0002 powiązanego z magazynem 12.</span><span class="sxs-lookup"><span data-stu-id="17986-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="17986-138">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="17986-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="17986-139">Na przykład można wybrać towar M0002 powiązany z magazynem 12.</span><span class="sxs-lookup"><span data-stu-id="17986-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="17986-140">W polu **Nowa ilość minimalna** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="17986-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="17986-141">Zaktualizuj wartość Nowa ilość minimalna, aby była zgodna z wartością w polu Obliczona minimalna ilość.</span><span class="sxs-lookup"><span data-stu-id="17986-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="17986-142">Jeśli obliczona minimalna ilość wynosi zero, można wprowadzić żądaną wartość przyszłą.</span><span class="sxs-lookup"><span data-stu-id="17986-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="17986-143">Księgowanie nowej ilości minimalnej i sprawdzanie poprawności wyniku</span><span class="sxs-lookup"><span data-stu-id="17986-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="17986-144">Kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="17986-144">Click **Post**.</span></span>
2. <span data-ttu-id="17986-145">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="17986-145">Click **OK**.</span></span>
3. <span data-ttu-id="17986-146">Kliknij, aby otworzyć łącze znajdujące się w polu **Numer towaru**.</span><span class="sxs-lookup"><span data-stu-id="17986-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="17986-147">Kliknij, aby otworzyć łącze znajdujące się w polu **Numer towaru**.</span><span class="sxs-lookup"><span data-stu-id="17986-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="17986-148">W **okienku akcji** kliknij pozycję Plan.</span><span class="sxs-lookup"><span data-stu-id="17986-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="17986-149">Kliknij opcję **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="17986-149">Click **Item coverage**.</span></span> <span data-ttu-id="17986-150">Zwróć uwagę, że pole **Ilość minimalna** zostało zaktualizowane o nową ilość minimalną z arkusza zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="17986-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]