--- 
title: "Tworzenie i edytowanie ofert sprzedaży"
description: "Ta procedura przedstawia sposób tworzenia i aktualizowania oferty sprzedaży."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c5e7164633bbb33b436ab7a6fcd8ff62183c6eb5
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="create-and-edit-sales-quotations"></a><span data-ttu-id="ff65f-103">Tworzenie i edytowanie ofert sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ff65f-103">Create and edit sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff65f-104">Ta procedura przedstawia sposób tworzenia i aktualizowania oferty sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-104">This procedure demonstrates how to create and update a sales quotation.</span></span> <span data-ttu-id="ff65f-105">Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ff65f-105">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-sales-quotation"></a><span data-ttu-id="ff65f-106">Tworzenie oferty sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ff65f-106">Create a sales quotation</span></span>
1. <span data-ttu-id="ff65f-107">Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.</span><span class="sxs-lookup"><span data-stu-id="ff65f-107">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="ff65f-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ff65f-108">Click New.</span></span>
3. <span data-ttu-id="ff65f-109">W polu Typ konta wybierz opcję „Prospekt”.</span><span class="sxs-lookup"><span data-stu-id="ff65f-109">In the Account type field, select 'Prospect'.</span></span>
4. <span data-ttu-id="ff65f-110">W polu Potencjalny klient wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff65f-110">In the Prospect field, enter or select a value.</span></span>
5. <span data-ttu-id="ff65f-111">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="ff65f-111">Expand the General section.</span></span>
    * <span data-ttu-id="ff65f-112">Ponieważ wybrano opcję utworzenia oferty sprzedaży z poziomu obszaru Sprzedaż i marketing, typ jest automatycznie ustawiany na Oferta sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-112">Because you chose to create a quotation from the Sales and Marketing area, the type is automatically set to Sales quotation.</span></span> <span data-ttu-id="ff65f-113">Aby utworzyć ofertę dla projektu, trzeba przejść do niego z modułu Zarządzanie projektami i ich księgowanie.</span><span class="sxs-lookup"><span data-stu-id="ff65f-113">To create a quotation for a project you must access it from the Project management and accounting module.</span></span>   
6. <span data-ttu-id="ff65f-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff65f-114">Click OK.</span></span>
    * <span data-ttu-id="ff65f-115">Pola i akcje w wierszach oferty są bardzo podobne do używanych w wierszach zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-115">The fields and actions on the quotation lines are very similar to the ones on the sales order lines.</span></span>   <span data-ttu-id="ff65f-116">Tak jak zamówienia sprzedaży, oferty można tworzyć dla określonego towaru, a gdy towar jest nieznany lub nie istnieje w momencie utworzenia oferty, można je tworzyć dla kategorii sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-116">Like sales orders, quotations can be created for a specific item or, when item number is not known or does not exist at the time of quotation creation, quotations can be created for a sales category.</span></span>  
7. <span data-ttu-id="ff65f-117">W polu Towar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff65f-117">In the Item field, enter or select a value.</span></span>
8. <span data-ttu-id="ff65f-118">W polu Towar wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff65f-118">In the Item field, type a value.</span></span>
9. <span data-ttu-id="ff65f-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-119">Close the page.</span></span>
10. <span data-ttu-id="ff65f-120">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ff65f-120">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ff65f-121">Jeśli istnieją ważne umowy handlowe na towar wybrany w wierszu, odnośna cena i rabaty zostaną automatycznie skopiowane do wiersza oferty.</span><span class="sxs-lookup"><span data-stu-id="ff65f-121">If there are valid trade agreements for the item selected on the line, the applicable price and discounts will be automatically copied to the quotation line.</span></span> <span data-ttu-id="ff65f-122">Upewnij się, że pole Cena jednostkowa zawiera wartość. Jeśli chcesz, można również wprowadzić wartości rabatów.</span><span class="sxs-lookup"><span data-stu-id="ff65f-122">Make sure that the Unit price field contains a value and you can also enter discount values if you want to.</span></span>  
11. <span data-ttu-id="ff65f-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ff65f-123">Click Save.</span></span>
12. <span data-ttu-id="ff65f-124">W okienku akcji kliknij opcję Oferta sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-124">On the Action Pane, click Sales quotation.</span></span>
13. <span data-ttu-id="ff65f-125">Kliknij przycisk Sumy.</span><span class="sxs-lookup"><span data-stu-id="ff65f-125">Click Totals.</span></span>
14. <span data-ttu-id="ff65f-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff65f-126">Click OK.</span></span>
15. <span data-ttu-id="ff65f-127">Kliknij wiersz Oferta sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-127">Click Sales quotation line.</span></span>
16. <span data-ttu-id="ff65f-128">Kliknij opcję Ceny.</span><span class="sxs-lookup"><span data-stu-id="ff65f-128">Click Prices.</span></span>
    * <span data-ttu-id="ff65f-129">Na stronie Uruchom symulację ceny można wypróbować korygowanie spodziewanych przychodów lub rentowności wynikającej z oferty na podstawie żądanej ceny jednostkowej, kwoty rabatu, procentu rabatu, łącznej kwoty, marży lub współczynnika marży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-129">In the Run price simulation page you can experiment with adjusting the expected revenue or profitability of your quotation based on the desired unit price, discount amount, discount percentage, total amount, margin, or contribution ratio.</span></span>   <span data-ttu-id="ff65f-130">Po uzyskaniu zadowalających docelowych wartości zastosuj sugestię do wiersza oferty, a jego pola związane z ceną zostaną odpowiednio zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="ff65f-130">When you are satisfied with the target figures, you apply the suggestion to the quotation line, and its price-related fields will be updated accordingly.</span></span>  
    * <span data-ttu-id="ff65f-131">Można utworzyć tyle symulacji cen, ile trzeba.</span><span class="sxs-lookup"><span data-stu-id="ff65f-131">Y ou can create as many price simulations as you wish.</span></span> <span data-ttu-id="ff65f-132">Po kliknięciu przycisku Nowy warunki cenowe z bieżącego wiersza oferty są kopiowane do strony.</span><span class="sxs-lookup"><span data-stu-id="ff65f-132">When you click New, the price conditions from the current quotation line are copied to the page.</span></span> <span data-ttu-id="ff65f-133">Następnie można zmodyfikować wartości w polach dotyczących ceny na docelowe.</span><span class="sxs-lookup"><span data-stu-id="ff65f-133">You can then modify values in any of the price-related fields to the target ones.</span></span> <span data-ttu-id="ff65f-134">Zmiana w jednym z pól spowoduje uruchomienie ponownego obliczania we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="ff65f-134">A change in one of the fields will trigger recalculation in all the other fields.</span></span> <span data-ttu-id="ff65f-135">Aby system obliczał marżę sprzedaży i współczynnik marży, musi być znany koszt jednostkowy produktu.</span><span class="sxs-lookup"><span data-stu-id="ff65f-135">In order for the system to calculate the sales margin and contribution ratio, the product's unit cost has to be known.</span></span> <span data-ttu-id="ff65f-136">Karta Symulowane ceny zawiera szczegółowy widok oryginalnych cen, proponowanych zmian oraz ich wpływu na sumy w ofercie.</span><span class="sxs-lookup"><span data-stu-id="ff65f-136">Use the Simulated prices tab for a detailed view of the original prices, proposed changes and their effect on the quotation totals.</span></span>   <span data-ttu-id="ff65f-137">Co do zasady zastosowanie do wiersza oferty symulacji ustawiającej nową kwotę powoduje, że system wykuje ponowne obliczenie i wprowadza nową wartość w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="ff65f-137">As a general rule, when a simulation that sets a new amount is applied to the quotation line, the system recalculates and enters a new value in the Unit price field.</span></span> <span data-ttu-id="ff65f-138">Jeśli symulacja opiera się na nowej marży lub nowym współczynniku marży, jest aktualizowane tylko pole Kwota netto, a pole Cena jednostkowa pozostaje puste.</span><span class="sxs-lookup"><span data-stu-id="ff65f-138">If the simulation is based on a new margin or a new contribution ratio, only the Net amount field is updated, and the Unit price is blank.</span></span> <span data-ttu-id="ff65f-139">W obu przypadkach wszelkie rabaty, które istniały w wierszu oferty przed symulacją, zostaną usunięte.</span><span class="sxs-lookup"><span data-stu-id="ff65f-139">In both cases, any discounts that were on the quotation line before simulation will be deleted.</span></span>  
17. <span data-ttu-id="ff65f-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-140">Close the page.</span></span>
18. <span data-ttu-id="ff65f-141">W okienku akcji kliknij pozycję Oferta.</span><span class="sxs-lookup"><span data-stu-id="ff65f-141">On the Action Pane, click Quotation.</span></span>
19. <span data-ttu-id="ff65f-142">Kliknij przycisk Wyślij ofertę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-142">Click Send quotation.</span></span>
20. <span data-ttu-id="ff65f-143">W polu Drukowanie oferty zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="ff65f-143">Select Yes in the Print quotation field.</span></span>
21. <span data-ttu-id="ff65f-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff65f-144">Click OK.</span></span>
    * <span data-ttu-id="ff65f-145">Generowanie raportu może nieco potrwać.</span><span class="sxs-lookup"><span data-stu-id="ff65f-145">The report may take a minute to generate.</span></span> <span data-ttu-id="ff65f-146">Przez ten czas nie zamykaj strony.</span><span class="sxs-lookup"><span data-stu-id="ff65f-146">Don’t close the page until it does so.</span></span>  
22. <span data-ttu-id="ff65f-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-147">Close the page.</span></span>

## <a name="update-a-sales-quotation"></a><span data-ttu-id="ff65f-148">Aktualizowanie oferty sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ff65f-148">Update a sales quotation</span></span>
1. <span data-ttu-id="ff65f-149">W okienku akcji kliknij pozycję Monituj.</span><span class="sxs-lookup"><span data-stu-id="ff65f-149">On the Action Pane, click Follow up.</span></span>
2. <span data-ttu-id="ff65f-150">Kliknij opcję Konwertuj na odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-150">Click Convert to customer.</span></span>
3. <span data-ttu-id="ff65f-151">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff65f-151">In the Customer account field, type a value.</span></span>
4. <span data-ttu-id="ff65f-152">Kliknij przycisk Sprawdź.</span><span class="sxs-lookup"><span data-stu-id="ff65f-152">Click Check.</span></span>
    * <span data-ttu-id="ff65f-153">Upewnij się, że zostanie wyświetlony komunikat, iż wpisany numer konta jest wolny i można go użyć.</span><span class="sxs-lookup"><span data-stu-id="ff65f-153">Make sure you see a message that the account number you typed in is free to use.</span></span>  
5. <span data-ttu-id="ff65f-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff65f-154">Click OK.</span></span>
    * <span data-ttu-id="ff65f-155">System utworzył nowe konto odbiorcy dla potencjalnego klienta w ofercie.</span><span class="sxs-lookup"><span data-stu-id="ff65f-155">The system has now created a new customer account for the prospect on the quotation.</span></span>  
6. <span data-ttu-id="ff65f-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-156">Close the page.</span></span>
7. <span data-ttu-id="ff65f-157">W okienku akcji kliknij pozycję Monituj.</span><span class="sxs-lookup"><span data-stu-id="ff65f-157">On the Action Pane, click Follow up.</span></span>
8. <span data-ttu-id="ff65f-158">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="ff65f-158">Click Confirm.</span></span>
9. <span data-ttu-id="ff65f-159">W polu Przyczyna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ff65f-159">In the Reason field, enter or select a value.</span></span>
10. <span data-ttu-id="ff65f-160">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff65f-160">Click OK.</span></span>
11. <span data-ttu-id="ff65f-161">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="ff65f-161">On the Action Pane, click General.</span></span>
12. <span data-ttu-id="ff65f-162">Kliknij pozycję Zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ff65f-162">Click Sales orders.</span></span>
13. <span data-ttu-id="ff65f-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff65f-163">Close the page.</span></span>


