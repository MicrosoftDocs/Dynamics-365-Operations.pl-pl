--- 
title: "Programy sprzedaży ciągłej i przetwarzanie powiązanych zamówień sprzedaży"
description: "Ta procedura przeprowadzi Cię przez proces sprzedawania w programie sprzedaży ciągłej i przetwarzania powiązanych zamówień sprzedaży."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 5fe1823c9b684bbc5ac5bd0871cc5c0a0e6ce678
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="selling-continuity-programs-and-processing-related-sales-orders"></a><span data-ttu-id="91fb7-103">Programy sprzedaży ciągłej i przetwarzanie powiązanych zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="91fb7-103">Selling continuity programs and processing related sales orders</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="91fb7-104">Ta procedura przeprowadzi Cię przez proces sprzedawania w programie sprzedaży ciągłej i przetwarzania powiązanych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="91fb7-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="91fb7-105">Aby wykonać tę procedurę, użytkownik musi być skonfigurowany jako użytkownik biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="91fb7-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="91fb7-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="91fb7-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="91fb7-107">Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Obsługa klienta.</span><span class="sxs-lookup"><span data-stu-id="91fb7-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="91fb7-108">W polu Wyszukiwany tekst wpisz „Karen”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="91fb7-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="91fb7-109">Powinno się pojawić okno dialogowe zaawansowanego wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="91fb7-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="91fb7-110">Jeśli tak się nie stanie, kliknij przycisk Szukaj umieszczony na prawo od tego pola.</span><span class="sxs-lookup"><span data-stu-id="91fb7-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="91fb7-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="91fb7-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="91fb7-112">Powinien być wyświetlany tylko jeden wiersz z osobą Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="91fb7-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="91fb7-113">Zaznacz wiersz, klikając kolumnę ze znacznikiem wyboru przy lewej krawędzi siatki.</span><span class="sxs-lookup"><span data-stu-id="91fb7-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="91fb7-114">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="91fb7-114">Click Select.</span></span>
5. <span data-ttu-id="91fb7-115">Kliknij opcję Nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="91fb7-115">Click New sales order.</span></span>
    * <span data-ttu-id="91fb7-116">Dobrym pomysłem jest zanotowanie numeru zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="91fb7-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="91fb7-117">Będzie on potrzebny w dalszej części tej procedury.</span><span class="sxs-lookup"><span data-stu-id="91fb7-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="91fb7-118">W polu Numer pozycji wpisz „88000”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="91fb7-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="91fb7-119">Jest to pozycja w sprzedaży ciągłej wśród danych firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="91fb7-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="91fb7-120">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="91fb7-120">Click Complete.</span></span>
8. <span data-ttu-id="91fb7-121">W polu Metoda płatności wprowadź wartość „Visa”.</span><span class="sxs-lookup"><span data-stu-id="91fb7-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="91fb7-122">Kliknij opcję Dodaj kartę kredytową.</span><span class="sxs-lookup"><span data-stu-id="91fb7-122">Click Add credit card.</span></span>
    * <span data-ttu-id="91fb7-123">Na tej stronie wprowadź wymagane dane karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="91fb7-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="91fb7-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="91fb7-124">Click OK.</span></span>
11. <span data-ttu-id="91fb7-125">Rozwiń sekcję Płatność.</span><span class="sxs-lookup"><span data-stu-id="91fb7-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="91fb7-126">Aby przesłać zamówienie biura obsługi, muszą zostać wprowadzone płatności dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="91fb7-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="91fb7-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="91fb7-127">Click OK.</span></span>
13. <span data-ttu-id="91fb7-128">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="91fb7-128">Click Submit.</span></span>
    * <span data-ttu-id="91fb7-129">Zakończono tworzenie nowego zamówienia ciągłego.</span><span class="sxs-lookup"><span data-stu-id="91fb7-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="91fb7-130">Teraz wykonasz dwa procesy wsadowe, które służą do przetwarzania zamówień ciągłych.</span><span class="sxs-lookup"><span data-stu-id="91fb7-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="91fb7-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="91fb7-131">Close the page.</span></span>
15. <span data-ttu-id="91fb7-132">Wybierz kolejno opcje Handel detaliczny i inny > Ciągłość > Przetwarzanie płatności w sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="91fb7-132">Go to Retail and commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="91fb7-133">W polu Pozycja w sprzedaży ciągłej wpisz „88000”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="91fb7-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="91fb7-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="91fb7-134">Click OK.</span></span>
18. <span data-ttu-id="91fb7-135">Wybierz kolejno opcje Handel detaliczny i inny > Ciągłość > Tworzenie zamówień podrzędnych dla sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="91fb7-135">Go to Retail and commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="91fb7-136">Proces spowoduje utworzenie nowych zamówień sprzedaży na podstawie ustawień programów sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="91fb7-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="91fb7-137">W polu Pozycja w sprzedaży ciągłej wpisz „88000”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="91fb7-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="91fb7-138">Towar „88000” jest pozycją w sprzedaży ciągłej wśród danych firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="91fb7-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="91fb7-139">W polu Zamówienie sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="91fb7-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="91fb7-140">Wprowadź numer zamówienia sprzedaży zanotowany wcześniej w procedurze.</span><span class="sxs-lookup"><span data-stu-id="91fb7-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="91fb7-141">Pozwoli to maksymalnie skrócić czas przetwarzania tej procedury.</span><span class="sxs-lookup"><span data-stu-id="91fb7-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="91fb7-142">Pole Zamówienia sprzedaży jest opcjonalne — można przetwarzać wszystkie zamówienia z każdego programu.</span><span class="sxs-lookup"><span data-stu-id="91fb7-142">The Sales order field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="91fb7-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="91fb7-143">Click OK.</span></span>


