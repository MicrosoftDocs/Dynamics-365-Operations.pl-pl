---
title: Tworzenie wpisu w arkuszu za pomocą szablonu
description: Zaksięgowane arkusze załączników mogą być zapisywane jako szablony załączników i stosowane w nowych załącznikach arkuszy.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: babbc5ee067743d368680970556f8e5d3d8585f0
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916165"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="b81b8-103">Tworzenie wpisu w arkuszu za pomocą szablonu</span><span class="sxs-lookup"><span data-stu-id="b81b8-103">Create a journal entry using template</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b81b8-104">Zaksięgowane arkusze załączników mogą być zapisywane jako szablony załączników i stosowane w nowych załącznikach arkuszy.</span><span class="sxs-lookup"><span data-stu-id="b81b8-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="b81b8-105">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="b81b8-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="b81b8-106">Otwórz **Okienko nawigacji > Moduły > Księga główna > Wpisy w arkuszu > Arkusze finansowe**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-106">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
2. <span data-ttu-id="b81b8-107">W **okienku akcji** kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-107">On the **Action pane**, click **New**.</span></span> <span data-ttu-id="b81b8-108">Ta procedura rozpoczyna się od utworzenia i zaksięgowania załącznika arkusza, ale wszelkie wcześniej zaksięgowane załączniki arkusze można zapisać jako szablon.</span><span class="sxs-lookup"><span data-stu-id="b81b8-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
3. <span data-ttu-id="b81b8-109">W polu **Nazwa** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b81b8-109">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b81b8-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b81b8-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b81b8-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b81b8-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b81b8-112">Kliknij przycisk **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-112">Click **Lines**.</span></span>
7. <span data-ttu-id="b81b8-113">W polu **Typ konta** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-113">In the **Account type** field, type a value.</span></span>
8. <span data-ttu-id="b81b8-114">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-114">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="b81b8-115">W polu **Debet** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-115">In the **Debit** field, type a value.</span></span>
10. <span data-ttu-id="b81b8-116">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-116">Click **New**.</span></span>
11. <span data-ttu-id="b81b8-117">W polu **Typ konta** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-117">In the **Account type** field, type a value.</span></span>
12. <span data-ttu-id="b81b8-118">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-118">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="b81b8-119">W polu **Debet** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-119">In the **Debit** field, type a value.</span></span>
14. <span data-ttu-id="b81b8-120">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-120">Click **New**.</span></span>
14. <span data-ttu-id="b81b8-121">W polu **Konto** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="b81b8-121">In the **Account** field, specify the desired values.</span></span>
15. <span data-ttu-id="b81b8-122">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b81b8-122">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="b81b8-123">Wprowadź kwotę w polu **Kredyt**, aby zbilansować załącznik.</span><span class="sxs-lookup"><span data-stu-id="b81b8-123">In the **Credit** field, type a value to balance the voucher.</span></span>
17. <span data-ttu-id="b81b8-124">W **okienku akcji** kliknij pozycję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-124">On the **Action pane**, click **Post**.</span></span>
18. <span data-ttu-id="b81b8-125">Kliknij przycisk **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-125">Click **Functions**.</span></span>
19. <span data-ttu-id="b81b8-126">Kliknij przycisk **Zapisz szablon załącznika**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-126">Click **Save voucher** template.</span></span>
20. <span data-ttu-id="b81b8-127">W tej procedurze przyjęto szablon **typu Procent** .</span><span class="sxs-lookup"><span data-stu-id="b81b8-127">This procedure assumes a **Percent Template** type.</span></span> <span data-ttu-id="b81b8-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b81b8-128">Click OK.</span></span>
    - <span data-ttu-id="b81b8-129">Procent: kwoty w załączniku są konwertowane na współczynniki procentowe, co pozwala na zastosowanie wszelkich kwot podczas wybierania szablonu załącznika.</span><span class="sxs-lookup"><span data-stu-id="b81b8-129">Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>
    - <span data-ttu-id="b81b8-130">Kwota: przechowywane i stosowane będą wartości rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="b81b8-130">Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="b81b8-131">Kliknij **Arkusze finansowe**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-131">Click **General journals**.</span></span>
22. <span data-ttu-id="b81b8-132">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-132">Click **New**.</span></span>
23. <span data-ttu-id="b81b8-133">W polu **Nazwa** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b81b8-133">In the **Name** field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="b81b8-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b81b8-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="b81b8-135">Kliknij przycisk **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-135">Click **Lines**.</span></span>
26. <span data-ttu-id="b81b8-136">Kliknij przycisk **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-136">Click **Functions**.</span></span>
27. <span data-ttu-id="b81b8-137">Kliknij opcję **Wybierz szablon załącznika**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-137">Click **Select voucher template**.</span></span>
28. <span data-ttu-id="b81b8-138">Znajdź szablon utworzony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="b81b8-138">Find the template that you created earlier.</span></span> <span data-ttu-id="b81b8-139">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-139">Click **OK**.</span></span> <span data-ttu-id="b81b8-140">Jeśli istnieją inne szablony, może być konieczne kliknięcie przycisku **Poprzedni krok**, a następnie wybranie właściwego szablonu.</span><span class="sxs-lookup"><span data-stu-id="b81b8-140">You may need to click **Previous step** and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="b81b8-141">W polu **Kwota** wprowadź kwotę, którą chcesz zastosować do załącznika.</span><span class="sxs-lookup"><span data-stu-id="b81b8-141">In the **Amount** field, enter the amount to be applied to the voucher.</span></span> <span data-ttu-id="b81b8-142">Pole **Kwota** jest wyświetlane tylko po wybraniu typu szablonu załącznika Procent.</span><span class="sxs-lookup"><span data-stu-id="b81b8-142">The **Amount** field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="b81b8-143">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b81b8-143">Click **OK**.</span></span>

