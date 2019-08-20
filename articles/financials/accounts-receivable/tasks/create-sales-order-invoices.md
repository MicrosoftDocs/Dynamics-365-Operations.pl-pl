---
title: Tworzenie faktur zamówienia sprzedaży
description: W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba8e0f02f2d1eb12cecc2c434fbca1e198cddbe9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842960"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="6d44d-103">Tworzenie faktur zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6d44d-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6d44d-104">W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.</span><span class="sxs-lookup"><span data-stu-id="6d44d-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="6d44d-105">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="6d44d-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="6d44d-106">Tworzenie faktury na podstawie zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6d44d-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="6d44d-107">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Niezafakturowane zamówienia sprzedaży o stanie Wysłano.</span><span class="sxs-lookup"><span data-stu-id="6d44d-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="6d44d-108">Zaznacz zamówienie sprzedaży na liście.</span><span class="sxs-lookup"><span data-stu-id="6d44d-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="6d44d-109">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="6d44d-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="6d44d-110">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="6d44d-110">Click Invoice.</span></span>
    * <span data-ttu-id="6d44d-111">Należy zauważyć, że z tym zamówieniem sprzedaży jest skojarzonych wiele dokumentów dostawy.</span><span class="sxs-lookup"><span data-stu-id="6d44d-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="6d44d-112">Zamiast numeru dokumentu dostawy będzie wyświetlane tylko słowo <multiple>.</span><span class="sxs-lookup"><span data-stu-id="6d44d-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="6d44d-113">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="6d44d-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="6d44d-114">W celu zaksięgowania faktury w ustawieniu Księgowanie musi być ustawiona wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="6d44d-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="6d44d-115">Można także wyłączyć księgowania i tylko wydrukować fakturę.</span><span class="sxs-lookup"><span data-stu-id="6d44d-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="6d44d-116">Jednak ten sam efekt można osiągnąć przez utworzenie faktury pro forma zamiast regularnej faktury.</span><span class="sxs-lookup"><span data-stu-id="6d44d-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="6d44d-117">Ta opcja jest używana do zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="6d44d-117">This option is used for batch jobs.</span></span> <span data-ttu-id="6d44d-118">Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="6d44d-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="6d44d-119">W polu Drukuj wybierz opcję „Po”.</span><span class="sxs-lookup"><span data-stu-id="6d44d-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="6d44d-120">W obszarze Drukuj fakturę zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="6d44d-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="6d44d-121">Funkcja Zarządzanie drukowaniem może wydrukować wiele kopii faktury i również wysłać ją pocztą e-mail jako plik PDF.</span><span class="sxs-lookup"><span data-stu-id="6d44d-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="6d44d-122">W polu Drukuj opłaty zaznacz opcję „Podsumowanie”.</span><span class="sxs-lookup"><span data-stu-id="6d44d-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="6d44d-123">W polu Sprawdzanie limitu kredytu zaznacz opcję „Saldo”.</span><span class="sxs-lookup"><span data-stu-id="6d44d-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="6d44d-124">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="6d44d-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="6d44d-125">Łączenie zamówień w jedną fakturę</span><span class="sxs-lookup"><span data-stu-id="6d44d-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="6d44d-126">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6d44d-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6d44d-127">Odszukaj odbiorcę, który ma otwartych wiele faktur.</span><span class="sxs-lookup"><span data-stu-id="6d44d-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="6d44d-128">Wybierz otwarte zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6d44d-128">Select an open sales order.</span></span>
4. <span data-ttu-id="6d44d-129">Zaznacz inne otwarte zamówienie sprzedaży tego samego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="6d44d-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="6d44d-130">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="6d44d-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="6d44d-131">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="6d44d-131">Click Invoice.</span></span>
7. <span data-ttu-id="6d44d-132">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="6d44d-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="6d44d-133">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="6d44d-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="6d44d-134">Należy zwrócić uwagę, że w sekcji Przegląd widać dwie faktury.</span><span class="sxs-lookup"><span data-stu-id="6d44d-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="6d44d-135">Scalmy je teraz w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="6d44d-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="6d44d-136">W pola Aktualizacja zbiorcza dla zaznacz opcję „Konto płatnika”.</span><span class="sxs-lookup"><span data-stu-id="6d44d-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="6d44d-137">Kliknij przycisk Rozmieść, aby scalić zamówienia sprzedaży w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="6d44d-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="6d44d-138">Dwa zamówienia sprzedaży są teraz scalone w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="6d44d-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="6d44d-139">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="6d44d-139">Click Cancel.</span></span>
12. <span data-ttu-id="6d44d-140">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="6d44d-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="6d44d-141">Zbiorcze księgowanie faktur</span><span class="sxs-lookup"><span data-stu-id="6d44d-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="6d44d-142">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Fakturowanie zbiorcze > Faktura.</span><span class="sxs-lookup"><span data-stu-id="6d44d-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="6d44d-143">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="6d44d-143">Click Select.</span></span>
3. <span data-ttu-id="6d44d-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6d44d-144">Click OK.</span></span>
4. <span data-ttu-id="6d44d-145">Kliknij przycisk Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="6d44d-145">Click Batch.</span></span>
5. <span data-ttu-id="6d44d-146">Kliknij przycisk Tak, aby włączyć przetwarzanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="6d44d-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="6d44d-147">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="6d44d-147">Click Recurrence.</span></span>
7. <span data-ttu-id="6d44d-148">Wybierz dni</span><span class="sxs-lookup"><span data-stu-id="6d44d-148">Select Days</span></span>
8. <span data-ttu-id="6d44d-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6d44d-149">Click OK.</span></span>
9. <span data-ttu-id="6d44d-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6d44d-150">Click OK.</span></span>
10. <span data-ttu-id="6d44d-151">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="6d44d-151">Click Cancel.</span></span>
11. <span data-ttu-id="6d44d-152">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="6d44d-152">Click Yes.</span></span>

