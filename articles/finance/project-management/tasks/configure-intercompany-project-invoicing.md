---
title: Konfigurowanie fakturowania projektów międzyfirmowych
description: W tym temacie pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174450"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="13f54-103">Konfigurowanie fakturowania projektów międzyfirmowych</span><span class="sxs-lookup"><span data-stu-id="13f54-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13f54-104">W tym temacie pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="13f54-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="13f54-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="13f54-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="13f54-106">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="13f54-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="13f54-107">Na liście **Wszyscy dostawcy** znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="13f54-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="13f54-108">W okienku akcji wybierz pozycję **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="13f54-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="13f54-109">Wybierz **Międzyfirmowe**.</span><span class="sxs-lookup"><span data-stu-id="13f54-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="13f54-110">W ustawieniu **Aktywne zaznacz** wartość **Tak**, aby włączyć handel międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="13f54-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="13f54-111">W polu **Firma odbiorcy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f54-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="13f54-112">W polu **Moje konto** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f54-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="13f54-113">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13f54-113">Select **Save**.</span></span>
9. <span data-ttu-id="13f54-114">Zamknij te strony, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="13f54-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="13f54-115">W okienku nawigacji przejdź kolejno do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="13f54-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="13f54-116">Wybierz kartę **Międzyfirmowe**.</span><span class="sxs-lookup"><span data-stu-id="13f54-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="13f54-117">Przesuń suwak do pozycji **Tak**, aby włączyć międzyfirmowe planowanie zasobów i karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="13f54-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="13f54-118">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13f54-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="13f54-119">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="13f54-119">Select **New**.</span></span>
15. <span data-ttu-id="13f54-120">W polu **Firma pożyczająca** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f54-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="13f54-121">Zaznacz pole wyboru **Naliczanie przychodu**.</span><span class="sxs-lookup"><span data-stu-id="13f54-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="13f54-122">W polu **Domyślna kategoria karty czasu pracy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f54-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="13f54-123">W polu **Domyślna kategoria wydatku pracy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f54-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="13f54-124">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13f54-124">Select **Save**.</span></span>
20. <span data-ttu-id="13f54-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13f54-125">Close the page.</span></span>
21. <span data-ttu-id="13f54-126">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Księgowanie > Konfiguracja księgowania**.</span><span class="sxs-lookup"><span data-stu-id="13f54-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="13f54-127">W polu **Typy kont księgowych** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="13f54-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="13f54-128">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="13f54-128">Select **New**.</span></span>
24. <span data-ttu-id="13f54-129">W polu **Konto główne** w mpwym wierszu podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="13f54-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="13f54-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13f54-130">Select **Save**.</span></span>
26. <span data-ttu-id="13f54-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13f54-131">Close the page.</span></span>
27. <span data-ttu-id="13f54-132">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena transferowa**.</span><span class="sxs-lookup"><span data-stu-id="13f54-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="13f54-133">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="13f54-133">Select **New**.</span></span>
29. <span data-ttu-id="13f54-134">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="13f54-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="13f54-135">W polu **Firma pożyczająca** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f54-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="13f54-136">W polu **Model ceny transferu** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="13f54-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="13f54-137">W polu **Ceny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="13f54-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="13f54-138">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13f54-138">Select **Save**.</span></span>

