---
title: Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur
description: W tym temacie opisano sposób używania rejestru faktur do tworzenia faktur.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 670dd2ec15aa26791758ec4bea2b431482499436
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227167"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="c3e26-103">Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur</span><span class="sxs-lookup"><span data-stu-id="c3e26-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c3e26-104">W tym temacie opisano sposób używania rejestru faktur do tworzenia faktur.</span><span class="sxs-lookup"><span data-stu-id="c3e26-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="c3e26-105">Następnie pula faktur posłuży dopasowaniu faktury do zamówienia zakupu i sfinalizowaniu wydatku na stronie faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c3e26-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="c3e26-106">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="c3e26-106">Create a purchase order</span></span>
1. <span data-ttu-id="c3e26-107">W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="c3e26-108">Kliknij przycisk **Nowe**, aby utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="c3e26-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="c3e26-109">W polu **Konto dostawcy** otwórz listę rozwijaną, aby wybrać dostaawcę.</span><span class="sxs-lookup"><span data-stu-id="c3e26-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="c3e26-110">Na przykład zaznacz dostawcę **1001**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="c3e26-111">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-111">Select **OK**.</span></span>
5. <span data-ttu-id="c3e26-112">W polu **Numer produktu** wybierz odpowiedni numer produktu z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="c3e26-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="c3e26-113">Na przykład zaznacz **S0001**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-113">For example, select **S0001**.</span></span> <span data-ttu-id="c3e26-114">Kwota netto wynosi 75,00 zł.</span><span class="sxs-lookup"><span data-stu-id="c3e26-114">The net amount is 75.00.</span></span>  <span data-ttu-id="c3e26-115">To kwota, której oczekujemy na fakturze.</span><span class="sxs-lookup"><span data-stu-id="c3e26-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="c3e26-116">W okienku akcji wybierz pozycję **Zakup**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="c3e26-117">Wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="c3e26-118">Tworzenie i księgowanie faktury</span><span class="sxs-lookup"><span data-stu-id="c3e26-118">Create and post and invoice</span></span>
1. <span data-ttu-id="c3e26-119">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Rejestr faktur**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="c3e26-120">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-120">Select **New**.</span></span>
3. <span data-ttu-id="c3e26-121">Otwórz wyszukiwanie i zaznacz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="c3e26-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="c3e26-122">Wybierz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="c3e26-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="c3e26-123">Kliknij przycisk **Wiersze**, aby otworzyć rejestr i wprowadzić wiersze wydatków.</span><span class="sxs-lookup"><span data-stu-id="c3e26-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="c3e26-124">W wyszukiwaniu wybierz dostawcę.</span><span class="sxs-lookup"><span data-stu-id="c3e26-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="c3e26-125">Na przykład zaznacz dostawcę **1001**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="c3e26-126">W polu **Faktura** wprowadź numer faktury.</span><span class="sxs-lookup"><span data-stu-id="c3e26-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="c3e26-127">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c3e26-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="c3e26-128">W polu **Kredyt** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c3e26-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="c3e26-129">W polu **zamówienie zakupu** otwórz listę rozwijaną, aby wybrać utworzone wcześniej zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="c3e26-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="c3e26-130">W polu **zatwierdzone przez** wybierz pozycję osoba zatwierdzająca z listy rozwijanej i kliknij przycisk **wybierz**, aby wybrać tę osobę zatwierdzającą.</span><span class="sxs-lookup"><span data-stu-id="c3e26-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="c3e26-131">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="c3e26-132">Otwieranie faktury z puli i uzgadnianie jej z zamówieniem zakupu w celu dokończenia procesu fakturowania</span><span class="sxs-lookup"><span data-stu-id="c3e26-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="c3e26-133">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Pula faktur**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="c3e26-134">Kliknij opcję **Zamówienie zakupu**, aby utworzyć fakturę od dostawcy na bazie faktury z puli.</span><span class="sxs-lookup"><span data-stu-id="c3e26-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="c3e26-135">Wybierz fakturę, którą chcesz przejrzeć.</span><span class="sxs-lookup"><span data-stu-id="c3e26-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="c3e26-136">Kliknij **Aktualizuj stan uzgadniania**, aby dokończyć uzgadnianie.</span><span class="sxs-lookup"><span data-stu-id="c3e26-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="c3e26-137">W okienku akcji kliknij pozycję **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="c3e26-138">Wybierz **Zmień widok**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-138">Select **Change view**.</span></span>
7. <span data-ttu-id="c3e26-139">Wybierz **Widok siatki**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="c3e26-140">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-140">Select **Post**.</span></span>
9. <span data-ttu-id="c3e26-141">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="c3e26-141">Close the form.</span></span>
10. <span data-ttu-id="c3e26-142">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Dostawcy > Dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="c3e26-143">Zaznacz dostawcę, który figurował w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="c3e26-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="c3e26-144">Na przykład zaznacz dostawcę **1001**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="c3e26-145">W okienku akcji wybierz pozycję **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="c3e26-146">Wybierz **transakcje**.</span><span class="sxs-lookup"><span data-stu-id="c3e26-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="c3e26-147">Zaznacz utworzoną przez siebie fakturę.</span><span class="sxs-lookup"><span data-stu-id="c3e26-147">Select the invoice that you created.</span></span> <span data-ttu-id="c3e26-148">Naliczenie w rejestrze faktur zostało wycofane, a następnie zaksięgowane na odpowiednim koncie wydatków.</span><span class="sxs-lookup"><span data-stu-id="c3e26-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]