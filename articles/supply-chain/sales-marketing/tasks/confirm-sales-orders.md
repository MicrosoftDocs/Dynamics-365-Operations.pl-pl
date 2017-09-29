--- 
title: "Potwierdzanie zamówień sprzedaży"
description: "Ta procedura przedstawia sposób potwierdzenia zamówień sprzedaży."
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
ms.openlocfilehash: 7cab69222c5004e6a62c632a9e85085403434ffd
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="confirm-sales-orders"></a><span data-ttu-id="688c8-103">Potwierdzanie zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="688c8-103">Confirm sales orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="688c8-104">Ta procedura przedstawia sposób potwierdzenia zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="688c8-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="688c8-105">Zobaczysz, jak potwierdzić pojedyncze zamówienie, a jak wiele zamówień na raz.</span><span class="sxs-lookup"><span data-stu-id="688c8-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="688c8-106">Te zadania zazwyczaj wykonuje agenta rozliczeniowego zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="688c8-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="688c8-107">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="688c8-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="688c8-108">Przed rozpoczęciem upewnij się, że istnieje kilka otwartych zamówień sprzedaży dla tego samego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="688c8-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="688c8-109">Jeśli używasz firmy USMF, można użyć odbiorcy US-027.</span><span class="sxs-lookup"><span data-stu-id="688c8-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="688c8-110">Potwierdzanie jednego zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="688c8-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="688c8-111">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="688c8-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="688c8-112">Na liście odszukaj i zaznacz zamówienie, które chcesz potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="688c8-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="688c8-113">Kliknij łącze na numerze zamówienia sprzedaży, aby otworzyć wybrane zamówienie.</span><span class="sxs-lookup"><span data-stu-id="688c8-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="688c8-114">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="688c8-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="688c8-115">Kliknij opcję Potwierdź zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="688c8-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="688c8-116">Rozwiń lub zwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="688c8-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="688c8-117">Upewnij się, że pole księgowania jest aktywne.</span><span class="sxs-lookup"><span data-stu-id="688c8-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="688c8-118">W opcji Drukowanie potwierdzenia zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="688c8-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="688c8-119">Pole Sprawdzanie limitu kredytu określa metodę używaną do obliczania pozostałego kredytu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="688c8-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="688c8-120">Domyślnie kod jest kopiowany ze strony Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="688c8-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="688c8-121">Jeśli chcesz pominąć sprawdzanie limitu kredytu podczas potwierdzania określonego zamówienia sprzedaży, ustawić pole Sprawdzanie limitu kredytu na Brak.</span><span class="sxs-lookup"><span data-stu-id="688c8-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="688c8-122">Należy jednak pamiętać, że nawet w przypadku, gdy to pole ustawiono na wartość Brak, sprawdzanie limitu kredytu będzie wciąż wykonywane, jeśli w danych głównych odbiorcy wybrano opcję Wymagany limit kredytu.</span><span class="sxs-lookup"><span data-stu-id="688c8-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="688c8-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="688c8-123">Click OK.</span></span>
9. <span data-ttu-id="688c8-124">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="688c8-124">Click Yes.</span></span>
10. <span data-ttu-id="688c8-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="688c8-125">Close the page.</span></span>
11. <span data-ttu-id="688c8-126">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="688c8-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="688c8-127">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="688c8-127">Click Change view.</span></span>
13. <span data-ttu-id="688c8-128">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="688c8-128">Click Header view.</span></span>
    * <span data-ttu-id="688c8-129">Po potwierdzeniu zamówienia pole Stan dokumentu jest ustawiane na Potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="688c8-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="688c8-130">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="688c8-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="688c8-131">Kliknij opcję Potwierdzenie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="688c8-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="688c8-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="688c8-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="688c8-133">Potwierdzanie wielu zamówień sprzedaży jednocześnie</span><span class="sxs-lookup"><span data-stu-id="688c8-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="688c8-134">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Potwierdzenie zamówienia > Potwierdź zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="688c8-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="688c8-135">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="688c8-135">Click Select.</span></span>
3. <span data-ttu-id="688c8-136">Na karcie Zakres na liście znajdź i zaznacz rekord odwołujący się do pola Konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="688c8-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="688c8-137">W polu Kryteria kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="688c8-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="688c8-138">Na liście znajdź i wybierz konto odbiorcy mające wiele zamówień, które chcesz potwierdzić grupowo.</span><span class="sxs-lookup"><span data-stu-id="688c8-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="688c8-139">Jeśli używasz firmy USMF, można wybrać klienta US-027.</span><span class="sxs-lookup"><span data-stu-id="688c8-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="688c8-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="688c8-140">Click OK.</span></span>
    * <span data-ttu-id="688c8-141">Karta Przegląd zawiera listę zamówień, które spełniają kryteria zapytania.</span><span class="sxs-lookup"><span data-stu-id="688c8-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="688c8-142">Zamówienia te zostaną uwzględnione w potwierdzeniu.</span><span class="sxs-lookup"><span data-stu-id="688c8-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="688c8-143">Pole Aktualizacja zbiorcza dla określa parametr, przy użyciu którego wiele zamówień ma być sumowanych do jednego dokumentu potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="688c8-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="688c8-144">Domyślnie opcja jest kopiowana z ustawienia Wartości domyślne aktualizacji zbiorczej znajdującego się na stronie Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="688c8-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="688c8-145">W pola Aktualizacja zbiorcza dla zaznacz opcję „Zamówienie”.</span><span class="sxs-lookup"><span data-stu-id="688c8-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="688c8-146">Minimalne parametry, które są wymagane do tworzenia aktualizacji zbiorczych, to Konto płatnika i Waluta.</span><span class="sxs-lookup"><span data-stu-id="688c8-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="688c8-147">Oznacza to, że aktualizacje zbiorcze mające różne konta płatnika i różne waluty są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="688c8-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="688c8-148">Dodatkowe parametry można skonfigurować na stronie Parametry aktualizacji zbiorczej, która jest dostępna ze strony Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="688c8-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="688c8-149">W polu Zamówienie sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="688c8-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="688c8-150">Na liście zaznacz numer zamówienia, które chcesz, aby było zamówieniem zbiorczym.</span><span class="sxs-lookup"><span data-stu-id="688c8-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="688c8-151">Kliknij przycisk Rozmieść.</span><span class="sxs-lookup"><span data-stu-id="688c8-151">Click Arrange.</span></span>
11. <span data-ttu-id="688c8-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="688c8-152">Click OK.</span></span>
12. <span data-ttu-id="688c8-153">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="688c8-153">Click OK.</span></span>


