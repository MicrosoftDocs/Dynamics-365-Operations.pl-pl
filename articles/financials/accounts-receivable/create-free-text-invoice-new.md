--- 
title: "Tworzenie faktury niezależnej"
description: "W tym artykule przedstawiono tworzenie faktury niezależnej."
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e6f89a6d77ff8e1cd88632df0d9a72915086ee1e
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="025d5-103">Tworzenie faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="025d5-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="025d5-104">W tym artykule przedstawiono tworzenie faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="025d5-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="025d5-105">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="025d5-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="025d5-106">Tworzenie faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="025d5-106">Create a free text invoice</span></span>

1. <span data-ttu-id="025d5-107">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne.</span><span class="sxs-lookup"><span data-stu-id="025d5-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="025d5-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="025d5-108">Click New.</span></span>
3. <span data-ttu-id="025d5-109">W polu Konto odbiorcy wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="025d5-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="025d5-110">Kontem faktury domyślnie będzie konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="025d5-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="025d5-111">Jeśli faktura nie jest zaksięgowana, stan księgowania zaczyna się od stanu W trakcie przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="025d5-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="025d5-112">Identyfikator faktury zostanie przypisany podczas księgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="025d5-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="025d5-113">Jeśli używasz pozwoleń SEPA, zgoda na polecenie zapłaty będzie automatycznie wypełniana po wybraniu konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="025d5-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="025d5-114">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="025d5-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="025d5-115">W polu Konto główne określ numer konta bez wymiarów.</span><span class="sxs-lookup"><span data-stu-id="025d5-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="025d5-116">Można również wpisać jeden lub więcej znaków konta głównego, a następnie za pomocą funkcji wyszukiwania znaleźć konto.</span><span class="sxs-lookup"><span data-stu-id="025d5-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="025d5-117">Wymiar wprowadza się na dalszym etapie procesu w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="025d5-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="025d5-118">Rozwiń skróconą kartę Szczegóły wiersza, tak aby dodać wymiary do konta głównego.</span><span class="sxs-lookup"><span data-stu-id="025d5-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="025d5-119">Kliknij kartę Wiersz wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="025d5-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="025d5-120">Wymiary dotyczą tylko wybranego wiersza.</span><span class="sxs-lookup"><span data-stu-id="025d5-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="025d5-121">Grupa podatków jest wypełniana danymi od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="025d5-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="025d5-122">Jeśli odbiorca nie ma zdefiniowanej grupy podatków, jest używana grupa podatków z konta głównego.</span><span class="sxs-lookup"><span data-stu-id="025d5-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="025d5-123">Grupa podatków dla pozycji jest wypełniana na podstawie konta głównego.</span><span class="sxs-lookup"><span data-stu-id="025d5-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="025d5-124">Jeśli konto główne nie ma zdefiniowanej grupy podatków dla pozycji, jest używana grupa podatków dla pozycji określona w parametrach podatków w Księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="025d5-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="025d5-125">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="025d5-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="025d5-126">Ilość jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="025d5-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="025d5-127">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="025d5-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="025d5-128">Cena jednostkowa jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="025d5-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="025d5-129">Kwota jest obliczana jako ilość pomnożona przez cenę jednostkową.</span><span class="sxs-lookup"><span data-stu-id="025d5-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="025d5-130">Można jednak zastąpić wynik tego obliczenia i wprowadzić kwotę samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="025d5-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="025d5-131">Kliknij opcję Podatek, aby wyświetlić podatek obliczony dla faktury.</span><span class="sxs-lookup"><span data-stu-id="025d5-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="025d5-132">Można wyświetlić kwoty podatków na tej stronie albo zastąpić kwoty na karcie Korekta.</span><span class="sxs-lookup"><span data-stu-id="025d5-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="025d5-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="025d5-133">Click OK.</span></span>
12. <span data-ttu-id="025d5-134">Kliknij opcję Opłaty, aby dodać opłatę do faktury.</span><span class="sxs-lookup"><span data-stu-id="025d5-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="025d5-135">W polu Kod opłat wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="025d5-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="025d5-136">W polu Kod opłat wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="025d5-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="025d5-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="025d5-137">Close the page.</span></span>
16. <span data-ttu-id="025d5-138">Kliknij opcję Sumy, aby wyświetlić szczegóły i sumy faktury zbiorczej.</span><span class="sxs-lookup"><span data-stu-id="025d5-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="025d5-139">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="025d5-139">Click Close.</span></span>
18. <span data-ttu-id="025d5-140">Kliknij przycisk Księguj, aby zaksięgować fakturę.</span><span class="sxs-lookup"><span data-stu-id="025d5-140">Click Post to post the invoice.</span></span> <span data-ttu-id="025d5-141">Przed zaksięgowaniem będzie można anulować operację.</span><span class="sxs-lookup"><span data-stu-id="025d5-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="025d5-142">Aby zmienić harmonogram drukowania faktur: zaznacz opcję Bieżąca, aby drukować każdą fakturę po jej aktualizacji, lub Po, aby drukować po zaktualizowaniu wszystkich faktur.</span><span class="sxs-lookup"><span data-stu-id="025d5-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="025d5-143">Jeśli chcesz zmienić sposób sprawdzania limitu kredytowego odbiorcy przed zaksięgowaniem, zmień typu limitu kredytu.</span><span class="sxs-lookup"><span data-stu-id="025d5-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="025d5-144">Jeśli chcesz wydrukować fakturę, zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="025d5-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="025d5-145">Jeśli chcesz zaksięgować fakturę, zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="025d5-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="025d5-146">Fakturę można wydrukować bez księgowania.</span><span class="sxs-lookup"><span data-stu-id="025d5-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="025d5-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="025d5-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="025d5-148">Kopiuj wiersze</span><span class="sxs-lookup"><span data-stu-id="025d5-148">Copy lines</span></span>
<span data-ttu-id="025d5-149">Aby skopiować wiersze faktury niezależnej, zaznacz jeden lub więcej wierszy, a następnie kliknij przycisk Kopiuj zaznaczone wiersze.</span><span class="sxs-lookup"><span data-stu-id="025d5-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="025d5-150">Można określić liczbę kopii, jaka ma zostać wykonana, oraz skopiować notatki i załączniki.</span><span class="sxs-lookup"><span data-stu-id="025d5-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="025d5-151">Można skopiować dystrybucje lub pozwolić na ich ponowne tworzenie podczas księgowania.</span><span class="sxs-lookup"><span data-stu-id="025d5-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="025d5-152">Po skopiowaniu wierszy można edytować informacje zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="025d5-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="025d5-153">Tworzenie faktury niezależnej z szablonu</span><span class="sxs-lookup"><span data-stu-id="025d5-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="025d5-154">Fakturę niezależną można utworzyć na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="025d5-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="025d5-155">Gdy na karcie Faktura wybierzesz opcję Nowe z szablonu, można wybrać nazwę szablonu i konto odbiorcy dla nowej faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="025d5-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="025d5-156">Można również wybrać wypełnienie wartościami domyślnymi, takimi jak warunki płatności i metoda płatności od odbiorcy, lub użyć wartości zapisanych razem z szablonem.</span><span class="sxs-lookup"><span data-stu-id="025d5-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="025d5-157">Zostanie utworzona nowa faktura niezależna i można w niej edytować wartości.</span><span class="sxs-lookup"><span data-stu-id="025d5-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


