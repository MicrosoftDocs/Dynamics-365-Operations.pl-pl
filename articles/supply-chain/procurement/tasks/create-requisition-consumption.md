--- 
title: "Tworzenie zapotrzebowania na zużycie"
description: "Ta procedura poprowadzi Cię przez proces tworzenia zapotrzebowania."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 07fe007005fcbbac1beecadb14dbd752376a0bd4
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-for-consumption"></a><span data-ttu-id="0dcb7-103">Tworzenie zapotrzebowania na zużycie</span><span class="sxs-lookup"><span data-stu-id="0dcb7-103">Create a requisition for consumption</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0dcb7-104">Ta procedura poprowadzi Cię przez proces tworzenia zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-104">This procedure walks you through the process of creating a requisition.</span></span> <span data-ttu-id="0dcb7-105">Pokazuje różne sposoby wyszukiwania produktów w katalogu zaopatrzenia oraz sposoby dodawania produktu, którego nie ma w katalogu.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-105">It shows you different ways to search for products in your procurement catalogue and how to add a product that isn’t in your catalogue.</span></span> <span data-ttu-id="0dcb7-106">Przed rozpoczęciem tej procedury musisz mieć skonfigurowaną zasadę zakupów z domyślnym typem zapotrzebowania Zużycie.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-106">Before you start this procedure, you must have a purchasing policy set up with Consumption as the default type of requisition.</span></span> <span data-ttu-id="0dcb7-107">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="0dcb7-108">Procedurę można wykonać tylko przy użyciu profilu użytkownika skonfigurowanego jako pracownik.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-108">The procedure can only be carried out by a user profile that is set up as worker.</span></span>  <span data-ttu-id="0dcb7-109">To zadanie normalnie wykonuje pracownik.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-109">This task would normally be carried out by an employee.</span></span> <span data-ttu-id="0dcb7-110">Rola zabezpieczeń Pracownik pozwoli wykonać te zadania. Jeśli używasz firmy USMF, możesz się zalogować jako Alicia.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-110">The Employee employ security role will allow you to carry out the tasks, or if you’re using USMF, you can log in as Alicia.</span></span>


## <a name="create-a-new-requisition"></a><span data-ttu-id="0dcb7-111">Tworzenie nowego zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="0dcb7-111">Create a new requisition</span></span>
1. <span data-ttu-id="0dcb7-112">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-112">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="0dcb7-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-113">Click New.</span></span>
3. <span data-ttu-id="0dcb7-114">W polu Nazwa nadaj zapotrzebowaniu nazwę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-114">In the Name field, give the requisition a name.</span></span>
4. <span data-ttu-id="0dcb7-115">W polu Data wymagalności wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-115">In the Requested date field, enter a date.</span></span>
    * <span data-ttu-id="0dcb7-116">Domyślnie data wymagalności i data księgowania są kopiowane do wierszy zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-116">By default, the requested date and accounting date are copied to the purchase requisition lines.</span></span> <span data-ttu-id="0dcb7-117">Można je zmienić na poziomie wierszy.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-117">They can be changed at the line level.</span></span> <span data-ttu-id="0dcb7-118">Data wymagalności jest wnioskowaną datą dostawy.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-118">The requested date is the requested delivery date.</span></span>  
5. <span data-ttu-id="0dcb7-119">W polu Data księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-119">In the Accounting date field, enter a date.</span></span>
    * <span data-ttu-id="0dcb7-120">Data księgowania jest używana do rejestrowania wpisu księgowania w księdze głównej i do sprawdzania dostępności środków budżetowych.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-120">The accounting date is used to record the accounting entry in the general ledger, and to validate whether budget funds are available.</span></span>  
6. <span data-ttu-id="0dcb7-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-121">Click OK.</span></span>
7. <span data-ttu-id="0dcb7-122">W polu Przyczyna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-122">In the Reason field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0dcb7-123">Wybrana przyczyna uzasadnienia biznesowego pojawia się domyślnie dla wierszy zapotrzebowania na zakup, ale można ją zmienić na poziomie wierszy.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-123">By default, the business justification reason that you select appears for the purchase requisition lines, but you can change it at the line level.</span></span>    
8. <span data-ttu-id="0dcb7-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-124">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="0dcb7-125">Wybierz przyczynę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-125">Select the reason</span></span>
10. <span data-ttu-id="0dcb7-126">W polu Szczegóły wprowadź bardziej opisowe uzasadnienie dla zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-126">In the details field enter a more descriptive justification for the requisition</span></span>

## <a name="add-a-line-to-the-requisition"></a><span data-ttu-id="0dcb7-127">Dodawanie wiersza do zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="0dcb7-127">Add a line to the requisition</span></span>
1. <span data-ttu-id="0dcb7-128">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-128">Click Add line.</span></span>
    * <span data-ttu-id="0dcb7-129">Istnieją dwa sposoby dodawania wierszy do zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-129">There are two ways of adding lines to the purchase requisition.</span></span> <span data-ttu-id="0dcb7-130">Jeśli znasz już numer produktu lub wiesz, że prosić o produkt, który nie znajduje się w katalogu produktów, można dodać wiersz bezpośrednio za pomocą opcji „Dodaj wiersz”.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-130">If you already know the product number or you already  know that you are requesting a product that is not in the product catalogueue, then you can add the line directly with "Add line".</span></span> <span data-ttu-id="0dcb7-131">Drugi sposób to użycie opcji „Dodaj produkty”, gdzie można użyć funkcji wyszukiwania i filtrowania w celu znalezienia towarów w katalogu produktów.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-131">The other way is to use "Add products" where you can use searching and filtering to find items in the product catalogueue.</span></span>    
2. <span data-ttu-id="0dcb7-132">Kliknij nowo utworzony wiersz.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-132">Click on the row you just created.</span></span>
    * <span data-ttu-id="0dcb7-133">Zleceniodawcą jest pracownik, który zgłosił zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-133">The requester is the worker that has requested the requisition.</span></span>   
    * <span data-ttu-id="0dcb7-134">Domyślnie osobą przygotowującą zapotrzebowanie jest pracownik, który je złożył.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-134">By default the person preparing the requisition is the worker who has requested it.</span></span> <span data-ttu-id="0dcb7-135">Musisz otrzymać pozwolenie na przygotowanie wiersza zapotrzebowania w imieniu innego pracownika.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-135">You have to be given permission to prepare a requisition line on behalf of another worker.</span></span> <span data-ttu-id="0dcb7-136">Jeśli masz takie pozwolenie, drugi pracownik będzie widoczny w tym wyszukiwaniu.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-136">If you have such permissions then the other workers will show up in this lookup.</span></span>  
3. <span data-ttu-id="0dcb7-137">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-137">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="0dcb7-138">Towary dostępne do wyboru są ograniczone przez zasady dostępu do kategorii oraz przez katalog zaopatrzenia ustawiony dla firmy dokonującej zakupu. </span><span class="sxs-lookup"><span data-stu-id="0dcb7-138">The items that are available for you to choose are limited by the category access policy and the procurement catalogue for the buying legal entity.</span></span>   
4. <span data-ttu-id="0dcb7-139">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-139">In the Quantity field, enter a number.</span></span>

## <a name="add-more-products-to-the-requisition"></a><span data-ttu-id="0dcb7-140">Dodawanie kolejnych produktów do zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="0dcb7-140">Add more products to the requisition</span></span>
1. <span data-ttu-id="0dcb7-141">Kliknij przycisk Dodaj produkty.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-141">Click Add products.</span></span>
    * <span data-ttu-id="0dcb7-142">Jest to opcja, która umożliwia wyszukiwanie produktów w katalogu produktów.  </span><span class="sxs-lookup"><span data-stu-id="0dcb7-142">This is the option where you can search for products in the product catalogueue.</span></span>    
2. <span data-ttu-id="0dcb7-143">W polu Znajdź węzeł kategorii zaopatrzenia wpisz pierwszą częścią nazwy kategorii, której szukasz, a następnie kliknij przycisk Wprowadź.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-143">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="0dcb7-144">Na przykład wpisz komput.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-144">For example, type comput.</span></span>  
3. <span data-ttu-id="0dcb7-145">Użyj skrótu InvokeDefaultButton.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-145">Use the InvokeDefaultButton shortcut.</span></span>
4. <span data-ttu-id="0dcb7-146">Użyj opcji Filtr, aby wyfiltrować listę produktów w wybranej kategorii.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-146">Use the Filter to filter the list of products in the selected category.</span></span>
5. <span data-ttu-id="0dcb7-147">Zaznacz kartę produktu, który ma zostać dodany do zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-147">Select the product card that you want to add to the requisition.</span></span>
6. <span data-ttu-id="0dcb7-148">Kliknij opcję Dodaj do wierszy.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-148">Click Add to lines.</span></span>
7. <span data-ttu-id="0dcb7-149">W polu Ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-149">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="0dcb7-150">W polu Znajdź węzeł kategorii zaopatrzenia wpisz pierwszą częścią nazwy kategorii, której szukasz, a następnie kliknij przycisk Wprowadź.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-150">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="0dcb7-151">Na przykład wpisz Wysoki (wyróżnione).</span><span class="sxs-lookup"><span data-stu-id="0dcb7-151">For example, type High (highlighters).</span></span>  
9. <span data-ttu-id="0dcb7-152">Użyj skrótu InvokeDefaultButton.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-152">Use the InvokeDefaultButton shortcut.</span></span>
10. <span data-ttu-id="0dcb7-153">Kliknij przycisk Dodaj niewymieniony na liście produkt do wierszy, aby dodać produkt, który nie znajduje się w katalogu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-153">Click Add unlisted product to lines to add a product that’s not listed in the procurement catalogue.</span></span>
11. <span data-ttu-id="0dcb7-154">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-154">In the Product name field, type a value.</span></span>
12. <span data-ttu-id="0dcb7-155">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-155">In the Unit field, type a value.</span></span>
13. <span data-ttu-id="0dcb7-156">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-156">Click OK.</span></span>
14. <span data-ttu-id="0dcb7-157">W polu Opis towaru wprowadź opis produktu.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-157">In the Item description field, add a description of the product.</span></span>
15. <span data-ttu-id="0dcb7-158">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-158">In the Quantity field, enter a number.</span></span>
16. <span data-ttu-id="0dcb7-159">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-159">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="0dcb7-160">Jeśli znasz cenę określonego dostawcy (wybranego w polu Konto dostawcy), można wprowadzić cenę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-160">If you know the price for a particular vendor (that you select in the vendor account field) then that price can be entered</span></span>   
17. <span data-ttu-id="0dcb7-161">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-161">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0dcb7-162">Dostępność dostawców w tym polu zależy od zasad zakupów oraz od stanu dostawcy w bieżącej kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-162">The vendors that are available in this field depend on the purchasing policies and the status that the vendor has for the current procurement category.</span></span> <span data-ttu-id="0dcb7-163">Zamiast wybierać dostawcę w tym polu, można kliknąć przycisk Sugeruj dostawców.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-163">As an alternative to selecting a vendor here, you can click the Suggest vendor button.</span></span>    
18. <span data-ttu-id="0dcb7-164">Na liście zaznacz dostawcę, z którego chcesz skorzystać.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-164">In the list, select the vendor you want to use.</span></span>
19. <span data-ttu-id="0dcb7-165">W polu Zewnętrzny kod towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-165">In the External item number field, type a value.</span></span>
    * <span data-ttu-id="0dcb7-166">Jest to numer referencyjny produktu znany przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-166">This is a reference number for the product that is known by the vendor.</span></span> <span data-ttu-id="0dcb7-167">Na przykład może to być numer produktu z własnego katalogu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-167">For example, this could be the item number of the product in the vendor's own catalogue.</span></span>  
20. <span data-ttu-id="0dcb7-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-168">Click OK.</span></span>

## <a name="distribute-amounts"></a><span data-ttu-id="0dcb7-169">Dystrybuuj kwoty</span><span class="sxs-lookup"><span data-stu-id="0dcb7-169">Distribute amounts</span></span>
1. <span data-ttu-id="0dcb7-170">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-170">Click Financials.</span></span>
2. <span data-ttu-id="0dcb7-171">Kliknij opcję Rozdziel kwoty.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-171">Click Distribute amounts.</span></span>
    * <span data-ttu-id="0dcb7-172">Ten proces pokazuje sposób rozdziału kosztów dla pierwszego wiersza między 2 konta.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-172">This process shows you how to distribute the cost for the first line between 2 accounts.</span></span> <span data-ttu-id="0dcb7-173">Można to również zrobić później, gdy zapotrzebowanie jest w weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-173">This can also be done later when the requisition is in review.</span></span>  
3. <span data-ttu-id="0dcb7-174">Kliknij opcję Podziel, aby utworzyć nowy wiersz dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-174">Click Split to create a new distribution line.</span></span>
4. <span data-ttu-id="0dcb7-175">W polu Konto księgowe zaznacz pierwsze centrum kosztów, które ma przejąć część kosztu.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-175">In the Ledger account field select the first cost centre that should take part of the cost.</span></span>
5. <span data-ttu-id="0dcb7-176">Zaznacz drugi wiersz dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-176">Select the other distribution line.</span></span>
6. <span data-ttu-id="0dcb7-177">W polu Konto księgowe określ drugie centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-177">In the Ledger account field specify the other cost centre.</span></span>
7. <span data-ttu-id="0dcb7-178">Kliknij opcję Podziel równo.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-178">Click Distribute equally.</span></span>
8. <span data-ttu-id="0dcb7-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-179">Close the page.</span></span>

## <a name="view-line-details"></a><span data-ttu-id="0dcb7-180">Wyświetl szczegóły wiersza</span><span class="sxs-lookup"><span data-stu-id="0dcb7-180">View line details</span></span>
1. <span data-ttu-id="0dcb7-181">Przełącz rozwinięcie sekcji Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-181">Toggle the expansion of the Line details section.</span></span>

## <a name="submit-the-requisition"></a><span data-ttu-id="0dcb7-182">Przesyłanie zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="0dcb7-182">Submit the requisition</span></span>
1. <span data-ttu-id="0dcb7-183">Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-183">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="0dcb7-184">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-184">Click Submit.</span></span>
3. <span data-ttu-id="0dcb7-185">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-185">Close the page.</span></span>
4. <span data-ttu-id="0dcb7-186">W polu Komentarz wpisz uwagi do osoby zatwierdzającej zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-186">In the Comment field, type a note for the approver of the requisition.</span></span>
5. <span data-ttu-id="0dcb7-187">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-187">Click Submit.</span></span>
6. <span data-ttu-id="0dcb7-188">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-188">Close the page.</span></span>
7. <span data-ttu-id="0dcb7-189">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="0dcb7-189">Refresh the page.</span></span>


