--- 
title: "Rejestrowanie prowizji od sprzedaży"
description: "W tej procedurze pokazano sposób obliczania i rejestrowania prowizji od sprzedaży."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f195f9e466eab3cf87afea2b5d430d0ea25c5a83
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="register-sales-commissions"></a><span data-ttu-id="504f5-103">Rejestrowanie prowizji od sprzedaży</span><span class="sxs-lookup"><span data-stu-id="504f5-103">Register sales commissions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="504f5-104">W tej procedurze pokazano sposób obliczania i rejestrowania prowizji od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="504f5-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="504f5-105">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="504f5-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="504f5-106">Przed rozpoczęciem tego przewodnika wykonaj przewodnik o nazwie „Konfigurowanie reguł dla prowizji od sprzedaży”, aby się upewnić, że wszystkie niezbędne obliczenia prowizji są skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="504f5-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="504f5-107">Zwróć uwagę na odbiorcę i numery towarów wybrane dla procesu naliczania prowizji i używaj ich, kiedy w przewodniku pojawi się monit o utworzenie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="504f5-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="504f5-108">Fakturowanie zamówienia sprzedaży kwalifikującego sprzedawcę do prowizji</span><span class="sxs-lookup"><span data-stu-id="504f5-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="504f5-109">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="504f5-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="504f5-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="504f5-110">Click New.</span></span>
3. <span data-ttu-id="504f5-111">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="504f5-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="504f5-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="504f5-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="504f5-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="504f5-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="504f5-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="504f5-114">Click OK.</span></span>
7. <span data-ttu-id="504f5-115">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="504f5-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="504f5-116">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="504f5-116">Click Change view.</span></span>
9. <span data-ttu-id="504f5-117">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="504f5-117">Click Header view.</span></span>
10. <span data-ttu-id="504f5-118">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="504f5-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="504f5-119">Wartość w polu Grupa sprzedaży reprezentuje grupę z przypisanym jednego lub więcej przedstawicielami handlowymi.</span><span class="sxs-lookup"><span data-stu-id="504f5-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="504f5-120">Osoby w grupie są tymi, które otrzymają prowizję podczas fakturowania zamówienia, zgodnie ze wstępnie zdefiniowanymi stawkami i rozdziałem.</span><span class="sxs-lookup"><span data-stu-id="504f5-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="504f5-121">Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.</span><span class="sxs-lookup"><span data-stu-id="504f5-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="504f5-122">Grupa sprzedaży jest również kopiowana do wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="504f5-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="504f5-123">Można ją zmienić, tak aby była inna niż podana w nagłówku i/lub różniła się między wierszami.</span><span class="sxs-lookup"><span data-stu-id="504f5-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="504f5-124">Wartość w polu Grupa prowizji reprezentuje grupę utworzoną dla jednego lub więcej odbiorców w celu śledzenia prowizji.</span><span class="sxs-lookup"><span data-stu-id="504f5-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="504f5-125">Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.</span><span class="sxs-lookup"><span data-stu-id="504f5-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="504f5-126">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="504f5-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="504f5-127">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="504f5-127">Click Change view.</span></span>
13. <span data-ttu-id="504f5-128">Kliknij opcję Widok wiersza.</span><span class="sxs-lookup"><span data-stu-id="504f5-128">Click Line view.</span></span>
14. <span data-ttu-id="504f5-129">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="504f5-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="504f5-130">Na liście zaznacz towar, który skonfigurowano dla prowizji.</span><span class="sxs-lookup"><span data-stu-id="504f5-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="504f5-131">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="504f5-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="504f5-132">Zwróć uwagę na kwotę netto w wierszu.</span><span class="sxs-lookup"><span data-stu-id="504f5-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="504f5-133">Reprezentuje ona przychody ze sprzedaży, które w tym przykładzie są podstawą do obliczania prowizji.</span><span class="sxs-lookup"><span data-stu-id="504f5-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="504f5-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="504f5-134">Click Save.</span></span>
18. <span data-ttu-id="504f5-135">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="504f5-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="504f5-136">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="504f5-136">Click Invoice.</span></span>
20. <span data-ttu-id="504f5-137">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="504f5-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="504f5-138">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="504f5-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="504f5-139">W polu Księgowanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="504f5-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="504f5-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="504f5-140">Click OK.</span></span>
24. <span data-ttu-id="504f5-141">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="504f5-141">Click OK.</span></span>
    * <span data-ttu-id="504f5-142">Zaksięgowanie transakcji może zająć ok. minutę.</span><span class="sxs-lookup"><span data-stu-id="504f5-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="504f5-143">Poczekaj na zakończenie przetwarzania — nie zamykaj w tym czasie strony.</span><span class="sxs-lookup"><span data-stu-id="504f5-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="504f5-144">Przegląd zarejestrowanych prowizji od sprzedaży</span><span class="sxs-lookup"><span data-stu-id="504f5-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="504f5-145">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="504f5-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="504f5-146">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="504f5-146">Click Invoice.</span></span>
3. <span data-ttu-id="504f5-147">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="504f5-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="504f5-148">Kliknij opcję Transakcje prowizji.</span><span class="sxs-lookup"><span data-stu-id="504f5-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="504f5-149">Na karcie Przegląd są wyświetlane wiersze reprezentujące kwoty prowizji należne przedstawicielom handlowym skojarzonym z fakturowanym zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="504f5-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="504f5-150">Przyjrzyjmy się szczegółom.</span><span class="sxs-lookup"><span data-stu-id="504f5-150">Let's review the details.</span></span>     
    * <span data-ttu-id="504f5-151">Jeśli użyto przewodnika „Konfigurowanie reguł dla prowizji od sprzedaży” w celu skonfigurowania grupy prowizji sprzedaży, istnieje dwoje sprzedawców, którzy otrzymają prowizje od sprzedaży, a prowizja jest dzielona równo między nich.</span><span class="sxs-lookup"><span data-stu-id="504f5-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="504f5-152">W tym przykładzie suma prowizji jest obliczana jako procent przychodu ze sprzedaży (kwota netto wiersza zamówienia).</span><span class="sxs-lookup"><span data-stu-id="504f5-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="504f5-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="504f5-153">Close the page.</span></span>
6. <span data-ttu-id="504f5-154">Kliknij opcję Załącznik.</span><span class="sxs-lookup"><span data-stu-id="504f5-154">Click Voucher.</span></span>
    * <span data-ttu-id="504f5-155">Można przejrzeć transakcje załącznika dla kwot prowizji, które zostały zaksięgowane na wstępnie zdefiniowanych kontach wydatków z tytułu prowizji i należnych prowizji.</span><span class="sxs-lookup"><span data-stu-id="504f5-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


