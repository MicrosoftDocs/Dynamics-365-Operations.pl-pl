--- 
title: Tworzenie harmonogramu dostaw
description: "W tej procedurze pokazano sposób tworzenia harmonogramu dostaw na podstawie zamówienia sprzedaży."
author: omulvad
manager: AnnBe
ms.date: 02/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 956edeac33f8531ecebef64301f2318333000429
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-delivery-schedule"></a><span data-ttu-id="8f16e-103">Tworzenie harmonogramu dostaw</span><span class="sxs-lookup"><span data-stu-id="8f16e-103">Create a delivery schedule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f16e-104">W tej procedurze pokazano sposób tworzenia harmonogramu dostaw na podstawie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8f16e-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="8f16e-105">Harmonogram dostaw jest używany w reakcji na żądanie dostarczenia ilości z zamówienia lub oferty w kilku dostawach.</span><span class="sxs-lookup"><span data-stu-id="8f16e-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="8f16e-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="8f16e-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="8f16e-107">Tworzenie harmonogramu dostaw</span><span class="sxs-lookup"><span data-stu-id="8f16e-107">Create delivery schedule</span></span>
1. <span data-ttu-id="8f16e-108">Przejdź do okna Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8f16e-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="8f16e-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-109">Click New.</span></span>
3. <span data-ttu-id="8f16e-110">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8f16e-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="8f16e-111">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f16e-111">Click OK.</span></span>
5. <span data-ttu-id="8f16e-112">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8f16e-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="8f16e-113">W polu Ilość wprowadź liczbę większą niż 1.</span><span class="sxs-lookup"><span data-stu-id="8f16e-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="8f16e-114">Kliknij wiersz Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8f16e-114">Click Sales order line.</span></span>
8. <span data-ttu-id="8f16e-115">Kliknij przycisk Harmonogram dostaw.</span><span class="sxs-lookup"><span data-stu-id="8f16e-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="8f16e-116">Strona Harmonogram dostaw to miejsce, gdzie można określić liczbę wysyłek, w których łączna ilość z wiersza zamówienia zostanie dostarczona do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="8f16e-117">Domyślnie system kopiuje łączną ilość i inne szczegóły dostawy z oryginalnego wiersza sprzedaży do pierwszego wiersza harmonogramu dostawy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="8f16e-118">W tym przykładzie utworzymy harmonogram dla dwóch wysyłek, gdzie data drugiej wysyłki będzie przesunięta o tydzień względem daty pierwszej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="8f16e-118">In this example, we’ll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="8f16e-119">W polu Ilość wprowadź liczbę będącą częścią całkowitej ilości.</span><span class="sxs-lookup"><span data-stu-id="8f16e-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="8f16e-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-120">Click New.</span></span>
11. <span data-ttu-id="8f16e-121">W polu Ilość wprowadź pozostałą ilość.</span><span class="sxs-lookup"><span data-stu-id="8f16e-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="8f16e-122">W polu Żądana data wysyłki wprowadź datę przypadającą tydzień po dacie z pierwszego wiersza dostawy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="8f16e-123">Dwie opcje na skróconej karcie Konwersja opłat kontrolują sposób rozdziału opłat między wiersze harmonogramu dostawy po przypisaniu do oryginalnego wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8f16e-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they’ve been assigned to the original order line.</span></span> <span data-ttu-id="8f16e-124">Jeśli wybierzesz opcję Kopiuj kwoty brutto, ta sama kwota opłaty zostanie skopiowana do każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="8f16e-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="8f16e-125">Opcja Przenieś do wierszy dostawy rozdziela opłatę równo między wszystkie wierszy dostawy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="8f16e-126">Można dzielić tylko opłaty stałe, natomiast opłaty zmienne zostaną skopiowane do wierszy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="8f16e-127">Odsuń kursor z drugiego wiersza dostawy, a nastąpi aktualizacja zawartości strony.</span><span class="sxs-lookup"><span data-stu-id="8f16e-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="8f16e-128">Ilość całkowitą przydzieloną do wierszy harmonogramu dostaw można śledzić w polach Razem i Pozostałe.</span><span class="sxs-lookup"><span data-stu-id="8f16e-128">You can keep track of the total quantity that’s allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="8f16e-129">Jeśli pozostała ilość wynosi zero, cała ilość z oryginalnego wiersza została przydzielona do harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="8f16e-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="8f16e-130">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f16e-130">Click OK.</span></span>
    * <span data-ttu-id="8f16e-131">Harmonogram dostaw został skopiowany do wierszy zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8f16e-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="8f16e-132">Oryginalny wiersz zamówienia, nazywany wierszem handlowym, został przekonwertowany na wiersz zamówienia z wieloma dostawami.</span><span class="sxs-lookup"><span data-stu-id="8f16e-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="8f16e-133">Jest oznaczony specjalną ikoną i pełni rolę nagłówka wierszy dostawy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="8f16e-134">Te dwa nowe wiersze, nazywane wierszami dostawy, tworzą jeden harmonogram dostaw.</span><span class="sxs-lookup"><span data-stu-id="8f16e-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="8f16e-135">Zamówienie będzie przetwarzane dla tych wierszy, a nie dla oryginalnego wiersza.</span><span class="sxs-lookup"><span data-stu-id="8f16e-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="8f16e-136">Jeśli są drukowane dokumenty takie jak potwierdzenia, listy pobrania, dokumenty dostawy lub faktury, wyświetlane są tylko wiersze dostaw.</span><span class="sxs-lookup"><span data-stu-id="8f16e-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="8f16e-137">Wiersze dostawy mogą mieć różne daty dostawy, ilości, metody dostawy i wymiary magazynowania, takie jak oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="8f16e-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="8f16e-138">Jednak wymiary produktów zawsze muszą być takie same jak w wierszu handlowym i nie można ich zmienić.</span><span class="sxs-lookup"><span data-stu-id="8f16e-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="8f16e-139">W polu Ilość wprowadź liczbę większą niż obecna.</span><span class="sxs-lookup"><span data-stu-id="8f16e-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="8f16e-140">Zaznacz wiersz handlowy, aby zobaczyć wynik ponownego obliczania ilości.</span><span class="sxs-lookup"><span data-stu-id="8f16e-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="8f16e-141">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="8f16e-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="8f16e-142">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="8f16e-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="8f16e-143">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="8f16e-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="8f16e-144">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="8f16e-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="8f16e-145">Należy zauważyć, że dokument dostawy będzie tworzony dla dwóch wierszy harmonogramu dostaw, a nie oryginalnego wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8f16e-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="8f16e-146">W polu Drukuj dokument dostawy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8f16e-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="8f16e-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f16e-147">Click OK.</span></span>
23. <span data-ttu-id="8f16e-148">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="8f16e-148">Click Yes.</span></span>
24. <span data-ttu-id="8f16e-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8f16e-149">Close the page.</span></span>


