---
title: Rejestrowanie prowizji od sprzedaży
description: W tym temacie objaśniono sposób obliczania i rejestrowania prowizji od sprzedaży.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4334fcd996f32b00bb399d3df5c43eb6bf50ab28
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010705"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="acd80-103">Rejestrowanie prowizji od sprzedaży</span><span class="sxs-lookup"><span data-stu-id="acd80-103">Register sales commissions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="acd80-104">W tym temacie objaśniono sposób obliczania i rejestrowania prowizji od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="acd80-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="acd80-105">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="acd80-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="acd80-106">Przed rozpoczęciem tego przewodnika wykonaj przewodnik o nazwie „Konfigurowanie reguł dla prowizji od sprzedaży”, aby się upewnić, że wszystkie niezbędne obliczenia prowizji są skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="acd80-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="acd80-107">Zwróć uwagę na odbiorcę i numery towarów wybrane dla procesu naliczania prowizji i używaj ich, kiedy w przewodniku pojawi się monit o utworzenie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="acd80-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="acd80-108">Fakturowanie zamówienia sprzedaży kwalifikującego sprzedawcę do prowizji</span><span class="sxs-lookup"><span data-stu-id="acd80-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="acd80-109">W okienku nawigacji przejdź do **Moduły > Sprzedaż i marketing >Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="acd80-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="acd80-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="acd80-110">Select **New**.</span></span>
3. <span data-ttu-id="acd80-111">W polu **Konto odbiorcy** wybierz odpowiedni rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="acd80-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="acd80-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="acd80-112">Select **OK**.</span></span>
5. <span data-ttu-id="acd80-113">W okienku akcji kliknij pozycję **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="acd80-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="acd80-114">Wybierz **Zmień widok**.</span><span class="sxs-lookup"><span data-stu-id="acd80-114">Select **Change view**.</span></span>
7. <span data-ttu-id="acd80-115">Wybierz **Widok nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="acd80-115">Select **Header view**.</span></span>
8. <span data-ttu-id="acd80-116">Rozwiń sekcję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="acd80-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="acd80-117">Wartość w polu **Grupa sprzedaży** reprezentuje grupę z przypisanym jednym lub więcej przedstawicielami handlowymi.</span><span class="sxs-lookup"><span data-stu-id="acd80-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="acd80-118">Osoby w grupie są tymi, które otrzymają prowizję podczas fakturowania zamówienia, zgodnie ze wstępnie zdefiniowanymi stawkami i rozdziałem.</span><span class="sxs-lookup"><span data-stu-id="acd80-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="acd80-119">Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.</span><span class="sxs-lookup"><span data-stu-id="acd80-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="acd80-120">Grupa sprzedaży jest również kopiowana do wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="acd80-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="acd80-121">Można ją zmienić, tak aby była inna niż podana w nagłówku i/lub różniła się między wierszami.</span><span class="sxs-lookup"><span data-stu-id="acd80-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="acd80-122">Wartość w polu **Grupa prowizji** reprezentuje grupę utworzoną dla jednego lub więcej odbiorców w celu śledzenia prowizji.</span><span class="sxs-lookup"><span data-stu-id="acd80-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="acd80-123">Wartość jest kopiowana z karty odbiorcy, ale w razie potrzeby można ją zmienić.</span><span class="sxs-lookup"><span data-stu-id="acd80-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="acd80-124">W okienku akcji kliknij pozycję **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="acd80-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="acd80-125">Wybierz **Zmień widok**.</span><span class="sxs-lookup"><span data-stu-id="acd80-125">Select **Change view**.</span></span>
11. <span data-ttu-id="acd80-126">Wybierz **Widok wiersza**.</span><span class="sxs-lookup"><span data-stu-id="acd80-126">Select **Line view**.</span></span>
12. <span data-ttu-id="acd80-127">W menu rozwijanym pola **Kod towaru** wybierz towar skonfigurowany dla prowizji.</span><span class="sxs-lookup"><span data-stu-id="acd80-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="acd80-128">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="acd80-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="acd80-129">Zwróć uwagę na kwotę netto w wierszu.</span><span class="sxs-lookup"><span data-stu-id="acd80-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="acd80-130">Reprezentuje ona przychody ze sprzedaży, które w tym przykładzie są podstawą do obliczania prowizji.</span><span class="sxs-lookup"><span data-stu-id="acd80-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="acd80-131">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="acd80-131">Select **Save**.</span></span>
15. <span data-ttu-id="acd80-132">W okienku akcji kliknij pozycję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="acd80-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="acd80-133">Wybierz **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="acd80-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="acd80-134">Rozwiń sekcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="acd80-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="acd80-135">W polu **Ilość** zaznacz opcję **Wszystko**.</span><span class="sxs-lookup"><span data-stu-id="acd80-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="acd80-136">W polu **Księgowanie** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="acd80-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="acd80-137">Wybierz **OK**, a następnie kliknij przycisk **OK** w następnym okienku.</span><span class="sxs-lookup"><span data-stu-id="acd80-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="acd80-138">Zaksięgowanie transakcji może zająć ok. minutę.</span><span class="sxs-lookup"><span data-stu-id="acd80-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="acd80-139">Poczekaj na zakończenie przetwarzania i nie zamykaj w tym czasie strony.</span><span class="sxs-lookup"><span data-stu-id="acd80-139">Allow the processing to complete and don't close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="acd80-140">Przegląd zarejestrowanych prowizji od sprzedaży</span><span class="sxs-lookup"><span data-stu-id="acd80-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="acd80-141">W okienku akcji wybierz opcję **Faktura**, a następnie ponownie wybierz opcję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="acd80-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="acd80-142">W okienku akcji wybierz opcję **Faktura**, a następnie wybierz opcję **Transakcje prowizji**.</span><span class="sxs-lookup"><span data-stu-id="acd80-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="acd80-143">Na karcie **Przegląd** są wyświetlane wiersze reprezentujące kwoty prowizji należne przedstawicielom handlowym skojarzonym z fakturowanym zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="acd80-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="acd80-144">Przyjrzyjmy się szczegółom.</span><span class="sxs-lookup"><span data-stu-id="acd80-144">Let's review the details.</span></span>  
    - <span data-ttu-id="acd80-145">Jeśli użyto przewodnika „Konfigurowanie reguł dla prowizji od sprzedaży” w celu skonfigurowania grupy **prowizji sprzedaży**, istnieje dwoje sprzedawców, którzy otrzymają prowizje od sprzedaży, a prowizja jest dzielona równo między nich.</span><span class="sxs-lookup"><span data-stu-id="acd80-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="acd80-146">W tym przykładzie suma prowizji jest obliczana jako procent przychodu ze sprzedaży (kwota netto wiersza zamówienia).</span><span class="sxs-lookup"><span data-stu-id="acd80-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="acd80-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="acd80-147">Close the page.</span></span>
4. <span data-ttu-id="acd80-148">Wybierz **Załącznik**.</span><span class="sxs-lookup"><span data-stu-id="acd80-148">Select **Voucher**.</span></span> <span data-ttu-id="acd80-149">Można przejrzeć transakcje załącznika dla kwot prowizji, które zostały zaksięgowane na wstępnie zdefiniowanych kontach wydatków z tytułu prowizji i należnych prowizji.</span><span class="sxs-lookup"><span data-stu-id="acd80-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  

