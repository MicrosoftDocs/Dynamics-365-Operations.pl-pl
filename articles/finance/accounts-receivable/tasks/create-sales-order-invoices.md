---
title: Tworzenie faktur zamówienia sprzedaży
description: W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
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
ms.openlocfilehash: c504ef36f61613c7aa7db5a1e5ddba6e69cd7285
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446927"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="a5bd2-103">Tworzenie faktur zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a5bd2-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5bd2-104">W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="a5bd2-105">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="a5bd2-106">Tworzenie faktury na podstawie zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a5bd2-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="a5bd2-107">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Niezafakturowane zamówienia sprzedaży o stanie Wysłano**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="a5bd2-108">Zaznacz zamówienie sprzedaży na liście.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="a5bd2-109">W **okienku akcji** kliknij pozycję **Faktura > Generuj > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="a5bd2-110">Należy zauważyć, że z tym zamówieniem sprzedaży jest skojarzonych wiele dokumentów dostawy.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="a5bd2-111">Zamiast numeru dokumentu dostawy będzie wyświetlane tylko słowo <multiple>.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="a5bd2-112">Rozwiń sekcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="a5bd2-113">W celu zaksięgowania faktury w ustawieniu Księgowanie musi być ustawiona wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="a5bd2-114">Można także wyłączyć księgowania i tylko wydrukować fakturę.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="a5bd2-115">Jednak ten sam efekt można osiągnąć przez utworzenie faktury pro forma zamiast regularnej faktury.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="a5bd2-116">Ta opcja jest używana do zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-116">This option is used for batch jobs.</span></span> <span data-ttu-id="a5bd2-117">Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="a5bd2-118">W polu **Drukuj** wybierz opcję „Po”.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="a5bd2-119">W obszarze **Drukuj fakturę** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="a5bd2-120">Funkcja Zarządzanie drukowaniem może wydrukować wiele kopii faktury i również wysłać ją pocztą e-mail jako plik PDF.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="a5bd2-121">W polu **Drukuj opłaty** zaznacz opcję „Podsumowanie”.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="a5bd2-122">W polu **Sprawdzanie limitu kredytu** zaznacz opcję „Saldo”.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="a5bd2-123">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="a5bd2-124">Łączenie zamówień w jedną fakturę</span><span class="sxs-lookup"><span data-stu-id="a5bd2-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="a5bd2-125">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="a5bd2-126">Odszukaj odbiorcę, który ma otwartych wiele faktur.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="a5bd2-127">Umożliwia wybór wielu otwartych zamówień sprzedaży od tego samego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="a5bd2-128">W **okienku akcji** kliknij pozycję **Faktura > Generuj > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="a5bd2-129">Rozwiń sekcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="a5bd2-130">W polu **Ilość** zaznacz opcję „Wszystko”.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="a5bd2-131">Należy zwrócić uwagę, że w sekcji Przegląd widać dwie faktury.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="a5bd2-132">Scalmy je teraz w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="a5bd2-133">W pola **Aktualizacja zbiorcza dla** zaznacz opcję „Konto płatnika”.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="a5bd2-134">Kliknij przycisk **Rozmieść**, aby scalić zamówienia sprzedaży w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="a5bd2-135">Dwa zamówienia sprzedaży są teraz scalone w jedną fakturę.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="a5bd2-136">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="a5bd2-137">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="a5bd2-138">Zbiorcze księgowanie faktur</span><span class="sxs-lookup"><span data-stu-id="a5bd2-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="a5bd2-139">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Faktury > Fakturowanie zbiorcze > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="a5bd2-140">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-140">Click **Select**.</span></span>
3. <span data-ttu-id="a5bd2-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-141">Click **OK**.</span></span>
4. <span data-ttu-id="a5bd2-142">Kliknij przycisk **Zadanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-142">Click **Batch**.</span></span>
5. <span data-ttu-id="a5bd2-143">W polu **Przetwarzanie wsadowe** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="a5bd2-144">Kliknij **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="a5bd2-145">Wybierz **Dni**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-145">Select **Days**.</span></span>
8. <span data-ttu-id="a5bd2-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-146">Click **OK**.</span></span>
9. <span data-ttu-id="a5bd2-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-147">Click **OK**.</span></span>
10. <span data-ttu-id="a5bd2-148">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="a5bd2-149">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-149">Click **Yes**.</span></span>

