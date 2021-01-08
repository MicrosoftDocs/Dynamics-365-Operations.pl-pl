---
title: Używanie programu sprzedaży ciągłej
description: Ta procedura przeprowadzi Cię przez proces sprzedawania w programie sprzedaży ciągłej i przetwarzania powiązanych zamówień sprzedaży.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2baf0127a35cc62952fd78daaf8204d35ec8d2b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414970"
---
# <a name="using-continuity-program"></a><span data-ttu-id="2d597-103">Używanie programu sprzedaży ciągłej</span><span class="sxs-lookup"><span data-stu-id="2d597-103">Using continuity program</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d597-104">Ta procedura przeprowadzi Cię przez proces sprzedawania w programie sprzedaży ciągłej i przetwarzania powiązanych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2d597-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="2d597-105">Aby wykonać tę procedurę, użytkownik musi być skonfigurowany jako użytkownik biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="2d597-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="2d597-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="2d597-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="2d597-107">Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Obsługa klienta.</span><span class="sxs-lookup"><span data-stu-id="2d597-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="2d597-108">W polu Wyszukiwany tekst wpisz „Karen”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="2d597-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="2d597-109">Powinno się pojawić okno dialogowe zaawansowanego wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="2d597-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="2d597-110">Jeśli tak się nie stanie, kliknij przycisk Szukaj umieszczony na prawo od tego pola.</span><span class="sxs-lookup"><span data-stu-id="2d597-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="2d597-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2d597-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2d597-112">Powinien być wyświetlany tylko jeden wiersz z osobą Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="2d597-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="2d597-113">Zaznacz wiersz, klikając kolumnę ze znacznikiem wyboru przy lewej krawędzi siatki.</span><span class="sxs-lookup"><span data-stu-id="2d597-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="2d597-114">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="2d597-114">Click Select.</span></span>
5. <span data-ttu-id="2d597-115">Kliknij opcję Nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2d597-115">Click New sales order.</span></span>
    * <span data-ttu-id="2d597-116">Dobrym pomysłem jest zanotowanie numeru zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2d597-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="2d597-117">Będzie on potrzebny w dalszej części tej procedury.</span><span class="sxs-lookup"><span data-stu-id="2d597-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="2d597-118">W polu Numer pozycji wpisz „88000”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="2d597-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="2d597-119">Jest to pozycja w sprzedaży ciągłej wśród danych firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="2d597-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="2d597-120">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="2d597-120">Click Complete.</span></span>
8. <span data-ttu-id="2d597-121">W polu Metoda płatności wprowadź wartość „Visa”.</span><span class="sxs-lookup"><span data-stu-id="2d597-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="2d597-122">Kliknij opcję Dodaj kartę kredytową.</span><span class="sxs-lookup"><span data-stu-id="2d597-122">Click Add credit card.</span></span>
    * <span data-ttu-id="2d597-123">Na tej stronie wprowadź wymagane dane karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="2d597-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="2d597-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2d597-124">Click OK.</span></span>
11. <span data-ttu-id="2d597-125">Rozwiń sekcję Płatność.</span><span class="sxs-lookup"><span data-stu-id="2d597-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="2d597-126">Aby przesłać zamówienie biura obsługi, muszą zostać wprowadzone płatności dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="2d597-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="2d597-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2d597-127">Click OK.</span></span>
13. <span data-ttu-id="2d597-128">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="2d597-128">Click Submit.</span></span>
    * <span data-ttu-id="2d597-129">Zakończono tworzenie nowego zamówienia ciągłego.</span><span class="sxs-lookup"><span data-stu-id="2d597-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="2d597-130">Teraz wykonasz dwa procesy wsadowe, które służą do przetwarzania zamówień ciągłych.</span><span class="sxs-lookup"><span data-stu-id="2d597-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="2d597-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2d597-131">Close the page.</span></span>
15. <span data-ttu-id="2d597-132">Wybierz kolejno opcje Handel detaliczny i inny > Ciągłość > Przetwarzanie płatności w sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="2d597-132">Go to Retail and Commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="2d597-133">W polu Pozycja w sprzedaży ciągłej wpisz „88000”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="2d597-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="2d597-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2d597-134">Click OK.</span></span>
18. <span data-ttu-id="2d597-135">Wybierz kolejno opcje Handel detaliczny i inny > Ciągłość > Tworzenie zamówień podrzędnych dla sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="2d597-135">Go to Retail and Commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="2d597-136">Proces spowoduje utworzenie nowych zamówień sprzedaży na podstawie ustawień programów sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="2d597-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="2d597-137">W polu Pozycja w sprzedaży ciągłej wpisz „88000”, a następnie naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="2d597-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="2d597-138">Towar „88000” jest pozycją w sprzedaży ciągłej wśród danych firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="2d597-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="2d597-139">W polu Zamówienie sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2d597-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="2d597-140">Wprowadź numer zamówienia sprzedaży zanotowany wcześniej w procedurze.</span><span class="sxs-lookup"><span data-stu-id="2d597-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="2d597-141">Pozwoli to maksymalnie skrócić czas przetwarzania tej procedury.</span><span class="sxs-lookup"><span data-stu-id="2d597-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="2d597-142">Pole Zamówienia sprzedaży jest opcjonalne — można przetwarzać wszystkie zamówienia z każdego programu.</span><span class="sxs-lookup"><span data-stu-id="2d597-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="2d597-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2d597-143">Click OK.</span></span>

