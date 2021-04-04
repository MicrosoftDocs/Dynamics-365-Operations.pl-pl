---
title: Dodawanie zasady obliczania liczby kart Kanban do reguły Kanban
description: Ta procedura skupia się na tworzeniu zasady obliczania liczby kart Kanban oraz dodaniu jej do reguły Kanban w celu zoptymalizowania wielkości i liczby kart Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a32753701c9e06c46ed9b2a9c4b0329f62f15597
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255476"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="7cfa7-103">Dodawanie zasady obliczania liczby kart Kanban do reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="7cfa7-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7cfa7-104">Ta procedura skupia się na tworzeniu zasady obliczania liczby kart Kanban oraz dodaniu jej do reguły Kanban w celu zoptymalizowania wielkości i liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="7cfa7-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7cfa7-106">Procedura jest przeznaczona dla menedżera strumienia wartości.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="7cfa7-107">Procedura jest warunkiem wstępnym tworzenia procedury Obliczanie sugestii liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="7cfa7-108">Tworzenie nowej zasady obliczania liczby kart Kanban</span><span class="sxs-lookup"><span data-stu-id="7cfa7-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="7cfa7-109">Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Zasady obliczania ilości na karcie Kanban.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="7cfa7-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-110">Click New.</span></span>
3. <span data-ttu-id="7cfa7-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="7cfa7-112">Na przykład wpisz Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="7cfa7-113">W polu Plan główny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7cfa7-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7cfa7-115">Wybierz plan statyczny, aby obliczyć popyt.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="7cfa7-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="7cfa7-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-117">Click Save.</span></span>
8. <span data-ttu-id="7cfa7-118">W polu Minimalna ilość na karcie Kanban wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="7cfa7-119">Jest to dodatkowa liczba kart Kanban uwzględniona w obliczeniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="7cfa7-120">W polu Współczynnik bezpieczeństwa ustaw wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="7cfa7-121">Jest to współczynnik używany do obliczania dodatkowej ilości zapasu bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="7cfa7-122">W polu Liczba dni w przód wpisz „30”.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="7cfa7-123">Jest to liczba dni poprzedzających datę obliczenia liczby kart Kanban uwzględniona w obliczaniu popytu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="7cfa7-124">W polu Liczba dni wstecz wpisz „30”.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="7cfa7-125">Jest to liczba dni po dacie obliczenia liczby kart Kanban uwzględniona w obliczaniu popytu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="7cfa7-126">Wzór używany do obliczania jest wyświetlane z wartościami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="7cfa7-127">Na przykład liczba kart Kanban = ((średni dzienny popyt x czas realizacji x 2,00) / ilość produktu na magazynową jednostkę obsługi) + 1</span><span class="sxs-lookup"><span data-stu-id="7cfa7-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="7cfa7-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="7cfa7-129">Dodawanie zasady obliczania liczby kart Kanban do reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="7cfa7-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="7cfa7-130">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="7cfa7-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7cfa7-132">Wybierz regułę Kanban 000020 do wykonania tej procedury.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="7cfa7-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7cfa7-134">Przełącz rozwinięcie sekcji Zasady obliczania ilości na karcie Kanban.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="7cfa7-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-135">Click Add.</span></span>
    * <span data-ttu-id="7cfa7-136">Dodaj zasadę obliczania liczby kart Kanban, którą utworzono w poprzednim podzadaniu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="7cfa7-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="7cfa7-138">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="7cfa7-139">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7cfa7-140">Wybierz zasadę Speaker2016, którą utworzono w poprzednim podzadaniu.</span><span class="sxs-lookup"><span data-stu-id="7cfa7-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]