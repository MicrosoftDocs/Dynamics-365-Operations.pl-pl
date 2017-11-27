--- 
title: "Tworzenie faktury niezależnej"
description: "W tym przewodniku po zadaniach zilustrowano tworzenie faktury niezależnej."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 87e293008fd748aa0dcc6b3caa94a4889bed35de
ms.contentlocale: pl-pl
ms.lasthandoff: 10/26/2017

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="1f3df-103">Tworzenie faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="1f3df-103">Create a free text invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f3df-104">W tym przewodniku po zadaniach zilustrowano tworzenie faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="1f3df-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="1f3df-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="1f3df-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="1f3df-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne.</span><span class="sxs-lookup"><span data-stu-id="1f3df-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="1f3df-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1f3df-107">Click New.</span></span>
3. <span data-ttu-id="1f3df-108">W polu Konto odbiorcy wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1f3df-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="1f3df-109">Kontem faktury domyślnie będzie konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1f3df-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="1f3df-110">Jeśli faktura nie jest zaksięgowana, stan księgowania zaczyna się od stanu W trakcie przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="1f3df-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="1f3df-111">Identyfikator faktury zostanie przypisany podczas księgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="1f3df-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="1f3df-112">Jeśli używasz pozwoleń SEPA, zgoda na polecenie zapłaty będzie automatycznie wypełniana po wybraniu konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1f3df-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="1f3df-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1f3df-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1f3df-114">W polu Konto główne określ numer konta bez wymiarów.</span><span class="sxs-lookup"><span data-stu-id="1f3df-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="1f3df-115">Można również wpisać jeden lub więcej znaków konta głównego, a następnie za pomocą funkcji wyszukiwania znaleźć konto.</span><span class="sxs-lookup"><span data-stu-id="1f3df-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="1f3df-116">Wymiar wprowadza się na dalszym etapie procesu w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="1f3df-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="1f3df-117">Rozwiń skróconą kartę Szczegóły wiersza, tak aby dodać wymiary do konta głównego.</span><span class="sxs-lookup"><span data-stu-id="1f3df-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="1f3df-118">Kliknij kartę Wiersz wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="1f3df-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="1f3df-119">Wymiary dotyczą tylko wybranego wiersza.</span><span class="sxs-lookup"><span data-stu-id="1f3df-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="1f3df-120">Grupa podatków jest wypełniana danymi od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1f3df-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="1f3df-121">Jeśli odbiorca nie ma zdefiniowanej grupy podatków, jest używana grupa podatków z konta głównego.</span><span class="sxs-lookup"><span data-stu-id="1f3df-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="1f3df-122">Grupa podatków dla pozycji jest wypełniana na podstawie konta głównego.</span><span class="sxs-lookup"><span data-stu-id="1f3df-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="1f3df-123">Jeśli konto główne nie ma zdefiniowanej grupy podatków dla pozycji, jest używana grupa podatków dla pozycji określona w parametrach podatków w Księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="1f3df-123">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="1f3df-124">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="1f3df-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1f3df-125">Ilość jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="1f3df-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="1f3df-126">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="1f3df-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="1f3df-127">Cena jednostkowa jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="1f3df-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="1f3df-128">Kwota jest obliczana jako ilość pomnożona przez cenę jednostkową.</span><span class="sxs-lookup"><span data-stu-id="1f3df-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="1f3df-129">Można jednak zastąpić wynik tego obliczenia i wprowadzić kwotę samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="1f3df-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="1f3df-130">Kliknij opcję Podatek, aby wyświetlić podatek obliczony dla faktury.</span><span class="sxs-lookup"><span data-stu-id="1f3df-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="1f3df-131">Można wyświetlić kwoty podatków na tej stronie albo zastąpić kwoty na karcie Korekta.</span><span class="sxs-lookup"><span data-stu-id="1f3df-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="1f3df-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1f3df-132">Click OK.</span></span>
12. <span data-ttu-id="1f3df-133">Kliknij opcję Opłaty, aby dodać opłatę do faktury.</span><span class="sxs-lookup"><span data-stu-id="1f3df-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="1f3df-134">W polu Kod opłat wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1f3df-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="1f3df-135">W polu Kod opłat wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1f3df-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="1f3df-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1f3df-136">Close the page.</span></span>
16. <span data-ttu-id="1f3df-137">Kliknij opcję Sumy, aby wyświetlić szczegóły i sumy faktury zbiorczej.</span><span class="sxs-lookup"><span data-stu-id="1f3df-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="1f3df-138">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="1f3df-138">Click Close.</span></span>
18. <span data-ttu-id="1f3df-139">Kliknij przycisk Księguj, aby zaksięgować fakturę.</span><span class="sxs-lookup"><span data-stu-id="1f3df-139">Click Post to post the invoice.</span></span> <span data-ttu-id="1f3df-140">Przed zaksięgowaniem będzie można anulować operację.</span><span class="sxs-lookup"><span data-stu-id="1f3df-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="1f3df-141">Aby zmienić harmonogram drukowania faktur: zaznacz opcję Bieżąca, aby drukować każdą fakturę po jej aktualizacji, lub Po, aby drukować po zaktualizowaniu wszystkich faktur.</span><span class="sxs-lookup"><span data-stu-id="1f3df-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="1f3df-142">Jeśli chcesz zmienić sposób sprawdzania limitu kredytowego odbiorcy przed zaksięgowaniem, zmień typu limitu kredytu.</span><span class="sxs-lookup"><span data-stu-id="1f3df-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="1f3df-143">Jeśli chcesz wydrukować fakturę, zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1f3df-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="1f3df-144">Jeśli chcesz zaksięgować fakturę, zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1f3df-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="1f3df-145">Fakturę można wydrukować bez księgowania.</span><span class="sxs-lookup"><span data-stu-id="1f3df-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="1f3df-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1f3df-146">Click OK.</span></span>


