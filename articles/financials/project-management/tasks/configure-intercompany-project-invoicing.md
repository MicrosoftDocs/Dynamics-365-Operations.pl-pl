---
title: Konfigurowanie fakturowania projektów międzyfirmowych
description: W tej procedurze pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fe06978d3a1c41a1133a568cca61df05b49d235
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "352765"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="7a06d-103">Konfigurowanie fakturowania projektów międzyfirmowych</span><span class="sxs-lookup"><span data-stu-id="7a06d-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a06d-104">W tej procedurze pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="7a06d-104">This procedure shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="7a06d-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="7a06d-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="7a06d-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawy.</span><span class="sxs-lookup"><span data-stu-id="7a06d-106">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="7a06d-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7a06d-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7a06d-108">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="7a06d-108">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="7a06d-109">Kliknij opcję Międzyfirmowe.</span><span class="sxs-lookup"><span data-stu-id="7a06d-109">Click Intercompany.</span></span>
5. <span data-ttu-id="7a06d-110">W ustawieniu Aktywne zaznacz wartość Tak, aby włączyć handel międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="7a06d-110">Set Active to Yes to enable intercompany trading.</span></span>
6. <span data-ttu-id="7a06d-111">W polu Firma odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a06d-111">In the Customer company field, enter or select a value.</span></span>
7. <span data-ttu-id="7a06d-112">W polu Moje konto wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a06d-112">In the My account field, enter or select a value.</span></span>
8. <span data-ttu-id="7a06d-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-113">Click Save.</span></span>
9. <span data-ttu-id="7a06d-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7a06d-114">Close the page.</span></span>
10. <span data-ttu-id="7a06d-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7a06d-115">Close the page.</span></span>
11. <span data-ttu-id="7a06d-116">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Parametry modułu Zarządzanie projektami i ich księgowanie.</span><span class="sxs-lookup"><span data-stu-id="7a06d-116">Go to Project management and accounting > Setup > Project management and accounting parameters.</span></span>
12. <span data-ttu-id="7a06d-117">Kliknij kartę Międzyfirmowe.</span><span class="sxs-lookup"><span data-stu-id="7a06d-117">Click the Intercompany tab.</span></span>
13. <span data-ttu-id="7a06d-118">Przesuń suwak do pozycji Tak, aby włączyć międzyfirmowe planowanie zasobów i karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="7a06d-118">Move the slider to Yes to enable intercompany resource scheduling and timesheets.</span></span>
14. <span data-ttu-id="7a06d-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-119">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="7a06d-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7a06d-120">Click New.</span></span>
16. <span data-ttu-id="7a06d-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-121">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="7a06d-122">W polu Firma pożyczająca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a06d-122">In the Borrowing legal entity field, enter or select a value.</span></span>
18. <span data-ttu-id="7a06d-123">Zaznacz pole wyboru Nalicz przychód.</span><span class="sxs-lookup"><span data-stu-id="7a06d-123">Select the Accrue revenue check box.</span></span>
19. <span data-ttu-id="7a06d-124">W polu Domyślna kategoria karty czasu pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a06d-124">In the Default timesheet category field, enter or select a value.</span></span>
20. <span data-ttu-id="7a06d-125">W polu Domyślna kategoria wydatku pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a06d-125">In the Default expense category field, enter or select a value.</span></span>
21. <span data-ttu-id="7a06d-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-126">Click Save.</span></span>
22. <span data-ttu-id="7a06d-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7a06d-127">Close the page.</span></span>
23. <span data-ttu-id="7a06d-128">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Księgowanie > Konfiguracja księgowania.</span><span class="sxs-lookup"><span data-stu-id="7a06d-128">Go to Project management and accounting > Setup > Posting > Ledger posting setup.</span></span>
24. <span data-ttu-id="7a06d-129">W polu Typy kont księgowych zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="7a06d-129">In the Ledger account types field, select an option.</span></span>
25. <span data-ttu-id="7a06d-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7a06d-130">Click New.</span></span>
26. <span data-ttu-id="7a06d-131">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-131">In the list, mark the selected row.</span></span>
27. <span data-ttu-id="7a06d-132">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-132">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="7a06d-133">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="7a06d-133">In the Main account field, specify the desired values.</span></span>
29. <span data-ttu-id="7a06d-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-134">Click Save.</span></span>
30. <span data-ttu-id="7a06d-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7a06d-135">Close the page.</span></span>
31. <span data-ttu-id="7a06d-136">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena transferowa.</span><span class="sxs-lookup"><span data-stu-id="7a06d-136">Go to Project management and accounting > Setup > Prices > Transfer price.</span></span>
32. <span data-ttu-id="7a06d-137">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7a06d-137">Click New.</span></span>
33. <span data-ttu-id="7a06d-138">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="7a06d-138">In the Effective date field, enter a date.</span></span>
34. <span data-ttu-id="7a06d-139">W polu Firma pożyczająca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a06d-139">In the Borrowing legal entity field, enter or select a value.</span></span>
35. <span data-ttu-id="7a06d-140">W polu Model ceny transferu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7a06d-140">In the Transfer price model field, select an option.</span></span>
36. <span data-ttu-id="7a06d-141">W polu Ceny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7a06d-141">In the Pricing field, enter a number.</span></span>
37. <span data-ttu-id="7a06d-142">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7a06d-142">Click Save.</span></span>

