---
title: Tworzenie faktur zamówienia sprzedaży
description: W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 984bb482f357e35dcfa4c08597a6be9e39817b98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837112"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="d98e0-103">Tworzenie faktur zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d98e0-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d98e0-104">W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.</span><span class="sxs-lookup"><span data-stu-id="d98e0-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="d98e0-105">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="d98e0-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="d98e0-106">Tworzenie faktury na podstawie zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d98e0-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="d98e0-107">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Niezafakturowane zamówienia sprzedaży o stanie Wysłano**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="d98e0-108">Zaznacz zamówienie sprzedaży na liście.</span><span class="sxs-lookup"><span data-stu-id="d98e0-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="d98e0-109">W **okienku akcji** kliknij pozycję **Faktura > Generuj > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="d98e0-110">Należy zauważyć, że z tym zamówieniem sprzedaży jest skojarzonych wiele dokumentów dostawy.</span><span class="sxs-lookup"><span data-stu-id="d98e0-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="d98e0-111">Zamiast numeru dokumentu dostawy będzie wyświetlane tylko słowo <multiple>.</span><span class="sxs-lookup"><span data-stu-id="d98e0-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="d98e0-112">Rozwiń sekcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="d98e0-113">W celu zaksięgowania faktury w ustawieniu Księgowanie musi być ustawiona wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="d98e0-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="d98e0-114">Można także wyłączyć księgowania i tylko wydrukować fakturę.</span><span class="sxs-lookup"><span data-stu-id="d98e0-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="d98e0-115">Jednak ten sam efekt można osiągnąć przez utworzenie faktury pro forma zamiast regularnej faktury.</span><span class="sxs-lookup"><span data-stu-id="d98e0-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="d98e0-116">Ta opcja jest używana do zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="d98e0-116">This option is used for batch jobs.</span></span> <span data-ttu-id="d98e0-117">Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="d98e0-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="d98e0-118">W polu **Drukuj** wybierz opcję „Po”.</span><span class="sxs-lookup"><span data-stu-id="d98e0-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="d98e0-119">W obszarze **Drukuj fakturę** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="d98e0-120">Funkcja Zarządzanie drukowaniem może wydrukować wiele kopii faktury i również wysłać ją pocztą e-mail jako plik PDF.</span><span class="sxs-lookup"><span data-stu-id="d98e0-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="d98e0-121">W polu **Drukuj opłaty** zaznacz opcję „Podsumowanie”.</span><span class="sxs-lookup"><span data-stu-id="d98e0-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="d98e0-122">W polu **Sprawdzanie limitu kredytu** zaznacz opcję „Saldo”.</span><span class="sxs-lookup"><span data-stu-id="d98e0-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="d98e0-123">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="d98e0-124">Łączenie zamówień w jedną fakturę</span><span class="sxs-lookup"><span data-stu-id="d98e0-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="d98e0-125">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="d98e0-126">Odszukaj odbiorcę, który ma otwartych wiele faktur.</span><span class="sxs-lookup"><span data-stu-id="d98e0-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="d98e0-127">Umożliwia wybór wielu otwartych zamówień sprzedaży od tego samego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d98e0-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="d98e0-128">W **okienku akcji** kliknij pozycję **Faktura > Generuj > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="d98e0-129">Rozwiń sekcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="d98e0-130">W polu **Ilość** zaznacz opcję „Wszystko”.</span><span class="sxs-lookup"><span data-stu-id="d98e0-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="d98e0-131">Należy zwrócić uwagę, że w sekcji Przegląd widać dwie faktury.</span><span class="sxs-lookup"><span data-stu-id="d98e0-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="d98e0-132">Scalmy je teraz w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="d98e0-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="d98e0-133">W pola **Aktualizacja zbiorcza dla** zaznacz opcję „Konto płatnika”.</span><span class="sxs-lookup"><span data-stu-id="d98e0-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="d98e0-134">Kliknij przycisk **Rozmieść**, aby scalić zamówienia sprzedaży w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="d98e0-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="d98e0-135">Dwa zamówienia sprzedaży są teraz scalone w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="d98e0-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="d98e0-136">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="d98e0-137">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="d98e0-138">Zbiorcze księgowanie faktur</span><span class="sxs-lookup"><span data-stu-id="d98e0-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="d98e0-139">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Faktury > Fakturowanie zbiorcze > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="d98e0-140">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-140">Click **Select**.</span></span>
3. <span data-ttu-id="d98e0-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-141">Click **OK**.</span></span>
4. <span data-ttu-id="d98e0-142">Kliknij przycisk **Zadanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-142">Click **Batch**.</span></span>
5. <span data-ttu-id="d98e0-143">W polu **Przetwarzanie wsadowe** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="d98e0-144">Kliknij **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="d98e0-145">Wybierz **Dni**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-145">Select **Days**.</span></span>
8. <span data-ttu-id="d98e0-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-146">Click **OK**.</span></span>
9. <span data-ttu-id="d98e0-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-147">Click **OK**.</span></span>
10. <span data-ttu-id="d98e0-148">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="d98e0-149">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d98e0-149">Click **Yes**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]