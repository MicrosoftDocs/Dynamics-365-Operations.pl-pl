--- 
title: "Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur"
description: "W tym przewodniku po zadaniach zostanie pokazane, jak korzystać z rejestru faktur do tworzenia faktur."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 96040b1c1ba130f773ba0defbf7bf1dcebedfc13
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="05d91-103">Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur</span><span class="sxs-lookup"><span data-stu-id="05d91-103">Key invoice data into the AP system using invoice pool</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="05d91-104">W tym przewodniku po zadaniach zostanie pokazane, jak korzystać z rejestru faktur do tworzenia faktur.</span><span class="sxs-lookup"><span data-stu-id="05d91-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="05d91-105">Następnie pula faktur posłuży dopasowaniu faktury do zamówienia zakupu i sfinalizowaniu wydatku na stronie faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="05d91-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="05d91-106">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="05d91-106">Create a purchase order</span></span>
1. <span data-ttu-id="05d91-107">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="05d91-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="05d91-108">Kliknij przycisk Nowy, aby utworzyć zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="05d91-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="05d91-109">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="05d91-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="05d91-110">Wybierz dostawcę z listy.</span><span class="sxs-lookup"><span data-stu-id="05d91-110">Select the vendor from the list.</span></span> <span data-ttu-id="05d91-111">Na przykład dostawcę 1001.</span><span class="sxs-lookup"><span data-stu-id="05d91-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="05d91-112">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="05d91-112">Click OK.</span></span>
6. <span data-ttu-id="05d91-113">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="05d91-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="05d91-114">Na liście odszukaj numer towaru będącego usługami.</span><span class="sxs-lookup"><span data-stu-id="05d91-114">Find the services item number in the list.</span></span> <span data-ttu-id="05d91-115">Na przykład zaznacz S0001.</span><span class="sxs-lookup"><span data-stu-id="05d91-115">For example, select S0001.</span></span>
8. <span data-ttu-id="05d91-116">Kliknij numer towaru i go zaznacz.</span><span class="sxs-lookup"><span data-stu-id="05d91-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="05d91-117">Kwota netto wynosi 75,00 zł.</span><span class="sxs-lookup"><span data-stu-id="05d91-117">The net amount is 75.00.</span></span>  <span data-ttu-id="05d91-118">To kwota, której oczekujemy na fakturze.</span><span class="sxs-lookup"><span data-stu-id="05d91-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="05d91-119">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="05d91-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="05d91-120">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="05d91-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="05d91-121">Tworzenie i księgowanie faktury</span><span class="sxs-lookup"><span data-stu-id="05d91-121">Create and post and invoice</span></span>
1. <span data-ttu-id="05d91-122">Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Rejestr faktur.</span><span class="sxs-lookup"><span data-stu-id="05d91-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="05d91-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="05d91-123">Click New.</span></span>
3. <span data-ttu-id="05d91-124">Otwórz wyszukiwanie i zaznacz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="05d91-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="05d91-125">Wybierz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="05d91-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="05d91-126">Kliknij przycisk Wiersze, aby otworzyć rejestr i wprowadzić wiersze wydatków.</span><span class="sxs-lookup"><span data-stu-id="05d91-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="05d91-127">W wyszukiwaniu wybierz dostawcę.</span><span class="sxs-lookup"><span data-stu-id="05d91-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="05d91-128">Na przykład kliknij dostawcę 1001.</span><span class="sxs-lookup"><span data-stu-id="05d91-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="05d91-129">W polu Faktura wprowadź numer faktury.</span><span class="sxs-lookup"><span data-stu-id="05d91-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="05d91-130">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="05d91-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="05d91-131">W polu Kredyt wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="05d91-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="05d91-132">W polu Zamówienie zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="05d91-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="05d91-133">Zaznacz utworzone wcześniej zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="05d91-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="05d91-134">W polu Zatwierdzone przez kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="05d91-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="05d91-135">Zaznacz osobę zatwierdzającą i kliknij przycisk Wybierz, aby ją wybrać.</span><span class="sxs-lookup"><span data-stu-id="05d91-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="05d91-136">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="05d91-136">Click Post.</span></span>
15. <span data-ttu-id="05d91-137">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="05d91-137">Close the form.</span></span>
16. <span data-ttu-id="05d91-138">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="05d91-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="05d91-139">Otwieranie faktury z puli i uzgadnianie jej z zamówieniem zakupu w celu dokończenia procesu fakturowania</span><span class="sxs-lookup"><span data-stu-id="05d91-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="05d91-140">Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Pula faktur.</span><span class="sxs-lookup"><span data-stu-id="05d91-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="05d91-141">Kliknij opcję Zamówienie zakupu, aby utworzyć fakturę od dostawcy na bazie faktury z puli.</span><span class="sxs-lookup"><span data-stu-id="05d91-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="05d91-142">Wybierz fakturę, którą chcesz przejrzeć.</span><span class="sxs-lookup"><span data-stu-id="05d91-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="05d91-143">Kliknij przycisk Aktualizuj stan uzgadniania, aby dokończyć uzgadnianie.</span><span class="sxs-lookup"><span data-stu-id="05d91-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="05d91-144">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="05d91-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="05d91-145">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="05d91-145">Click Change view.</span></span>
7. <span data-ttu-id="05d91-146">Kliknij opcję Widok siatki.</span><span class="sxs-lookup"><span data-stu-id="05d91-146">Click Grid view.</span></span>
8. <span data-ttu-id="05d91-147">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="05d91-147">Click Post.</span></span>
9. <span data-ttu-id="05d91-148">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="05d91-148">Close the form.</span></span>
10. <span data-ttu-id="05d91-149">Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Dostawcy.</span><span class="sxs-lookup"><span data-stu-id="05d91-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="05d91-150">Zaznacz dostawcę, który figurował w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="05d91-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="05d91-151">Na przykład zaznacz dostawcę 1001.</span><span class="sxs-lookup"><span data-stu-id="05d91-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="05d91-152">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="05d91-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="05d91-153">W okienku akcji kliknij pozycję Dostawca.</span><span class="sxs-lookup"><span data-stu-id="05d91-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="05d91-154">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="05d91-154">Click Transactions.</span></span>
15. <span data-ttu-id="05d91-155">Zaznacz utworzoną przez siebie fakturę.</span><span class="sxs-lookup"><span data-stu-id="05d91-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="05d91-156">Naliczenie w rejestrze faktur zostało wycofane, a następnie zaksięgowane na odpowiednim koncie wydatków.</span><span class="sxs-lookup"><span data-stu-id="05d91-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  


