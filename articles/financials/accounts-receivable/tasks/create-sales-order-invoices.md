--- 
title: "Tworzenie faktur zamówienia sprzedaży"
description: "W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 7b5c7419e1f8a775ce4b5b9ba46f582c9be23ad0
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="e654e-103">Tworzenie faktur zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e654e-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e654e-104">W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.</span><span class="sxs-lookup"><span data-stu-id="e654e-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="e654e-105">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="e654e-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="e654e-106">Tworzenie faktury na podstawie zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e654e-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="e654e-107">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Niezafakturowane zamówienia sprzedaży o stanie Wysłano.</span><span class="sxs-lookup"><span data-stu-id="e654e-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="e654e-108">Zaznacz zamówienie sprzedaży na liście.</span><span class="sxs-lookup"><span data-stu-id="e654e-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="e654e-109">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="e654e-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="e654e-110">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="e654e-110">Click Invoice.</span></span>
    * <span data-ttu-id="e654e-111">Należy zauważyć, że z tym zamówieniem sprzedaży jest skojarzonych wiele dokumentów dostawy.</span><span class="sxs-lookup"><span data-stu-id="e654e-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="e654e-112">Zamiast numeru dokumentu dostawy będzie wyświetlane tylko słowo <multiple>.</span><span class="sxs-lookup"><span data-stu-id="e654e-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="e654e-113">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="e654e-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="e654e-114">W celu zaksięgowania faktury w ustawieniu Księgowanie musi być ustawiona wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="e654e-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="e654e-115">Można także wyłączyć księgowania i tylko wydrukować fakturę.</span><span class="sxs-lookup"><span data-stu-id="e654e-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="e654e-116">Jednak ten sam efekt można osiągnąć przez utworzenie faktury pro forma zamiast regularnej faktury.</span><span class="sxs-lookup"><span data-stu-id="e654e-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="e654e-117">Ta opcja jest używana do zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="e654e-117">This option is used for batch jobs.</span></span> <span data-ttu-id="e654e-118">Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="e654e-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="e654e-119">W polu Drukuj wybierz opcję „Po”.</span><span class="sxs-lookup"><span data-stu-id="e654e-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="e654e-120">W obszarze Drukuj fakturę zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e654e-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="e654e-121">Funkcja Zarządzanie drukowaniem może wydrukować wiele kopii faktury i również wysłać ją pocztą e-mail jako plik PDF.</span><span class="sxs-lookup"><span data-stu-id="e654e-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="e654e-122">W polu Drukuj opłaty zaznacz opcję „Podsumowanie”.</span><span class="sxs-lookup"><span data-stu-id="e654e-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="e654e-123">W polu Sprawdzanie limitu kredytu zaznacz opcję „Saldo”.</span><span class="sxs-lookup"><span data-stu-id="e654e-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="e654e-124">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="e654e-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="e654e-125">Łączenie zamówień w jedną fakturę</span><span class="sxs-lookup"><span data-stu-id="e654e-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="e654e-126">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e654e-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="e654e-127">Odszukaj odbiorcę, który ma otwartych wiele faktur.</span><span class="sxs-lookup"><span data-stu-id="e654e-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="e654e-128">Wybierz otwarte zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e654e-128">Select an open sales order.</span></span>
4. <span data-ttu-id="e654e-129">Zaznacz inne otwarte zamówienie sprzedaży tego samego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e654e-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="e654e-130">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="e654e-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="e654e-131">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="e654e-131">Click Invoice.</span></span>
7. <span data-ttu-id="e654e-132">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="e654e-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="e654e-133">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="e654e-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="e654e-134">Należy zwrócić uwagę, że w sekcji Przegląd widać dwie faktury.</span><span class="sxs-lookup"><span data-stu-id="e654e-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="e654e-135">Scalmy je teraz w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="e654e-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="e654e-136">W pola Aktualizacja zbiorcza dla zaznacz opcję „Konto płatnika”.</span><span class="sxs-lookup"><span data-stu-id="e654e-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="e654e-137">Kliknij przycisk Rozmieść, aby scalić zamówienia sprzedaży w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="e654e-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="e654e-138">Dwa zamówienia sprzedaży są teraz scalone w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="e654e-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="e654e-139">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="e654e-139">Click Cancel.</span></span>
12. <span data-ttu-id="e654e-140">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="e654e-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="e654e-141">Zbiorcze księgowanie faktur</span><span class="sxs-lookup"><span data-stu-id="e654e-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="e654e-142">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Fakturowanie zbiorcze > Faktura.</span><span class="sxs-lookup"><span data-stu-id="e654e-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="e654e-143">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="e654e-143">Click Select.</span></span>
3. <span data-ttu-id="e654e-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e654e-144">Click OK.</span></span>
4. <span data-ttu-id="e654e-145">Kliknij przycisk Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="e654e-145">Click Batch.</span></span>
5. <span data-ttu-id="e654e-146">Kliknij przycisk Tak, aby włączyć przetwarzanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="e654e-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="e654e-147">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="e654e-147">Click Recurrence.</span></span>
7. <span data-ttu-id="e654e-148">Wybierz dni</span><span class="sxs-lookup"><span data-stu-id="e654e-148">Select Days</span></span>
8. <span data-ttu-id="e654e-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e654e-149">Click OK.</span></span>
9. <span data-ttu-id="e654e-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e654e-150">Click OK.</span></span>
10. <span data-ttu-id="e654e-151">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="e654e-151">Click Cancel.</span></span>
11. <span data-ttu-id="e654e-152">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="e654e-152">Click Yes.</span></span>


