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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53871db9223eef6ba78f2e327e60f45110891478
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838278"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="06523-103">Konfigurowanie fakturowania projektów międzyfirmowych</span><span class="sxs-lookup"><span data-stu-id="06523-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="06523-104">W tej procedurze pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="06523-104">This procedure shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="06523-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="06523-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="06523-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawy.</span><span class="sxs-lookup"><span data-stu-id="06523-106">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="06523-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="06523-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="06523-108">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="06523-108">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="06523-109">Kliknij opcję Międzyfirmowe.</span><span class="sxs-lookup"><span data-stu-id="06523-109">Click Intercompany.</span></span>
5. <span data-ttu-id="06523-110">W ustawieniu Aktywne zaznacz wartość Tak, aby włączyć handel międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="06523-110">Set Active to Yes to enable intercompany trading.</span></span>
6. <span data-ttu-id="06523-111">W polu Firma odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="06523-111">In the Customer company field, enter or select a value.</span></span>
7. <span data-ttu-id="06523-112">W polu Moje konto wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="06523-112">In the My account field, enter or select a value.</span></span>
8. <span data-ttu-id="06523-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="06523-113">Click Save.</span></span>
9. <span data-ttu-id="06523-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="06523-114">Close the page.</span></span>
10. <span data-ttu-id="06523-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="06523-115">Close the page.</span></span>
11. <span data-ttu-id="06523-116">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Parametry modułu Zarządzanie projektami i ich księgowanie.</span><span class="sxs-lookup"><span data-stu-id="06523-116">Go to Project management and accounting > Setup > Project management and accounting parameters.</span></span>
12. <span data-ttu-id="06523-117">Kliknij kartę Międzyfirmowe.</span><span class="sxs-lookup"><span data-stu-id="06523-117">Click the Intercompany tab.</span></span>
13. <span data-ttu-id="06523-118">Przesuń suwak do pozycji Tak, aby włączyć międzyfirmowe planowanie zasobów i karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="06523-118">Move the slider to Yes to enable intercompany resource scheduling and timesheets.</span></span>
14. <span data-ttu-id="06523-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="06523-119">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="06523-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="06523-120">Click New.</span></span>
16. <span data-ttu-id="06523-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="06523-121">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="06523-122">W polu Firma pożyczająca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="06523-122">In the Borrowing legal entity field, enter or select a value.</span></span>
18. <span data-ttu-id="06523-123">Zaznacz pole wyboru Nalicz przychód.</span><span class="sxs-lookup"><span data-stu-id="06523-123">Select the Accrue revenue check box.</span></span>
19. <span data-ttu-id="06523-124">W polu Domyślna kategoria karty czasu pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="06523-124">In the Default timesheet category field, enter or select a value.</span></span>
20. <span data-ttu-id="06523-125">W polu Domyślna kategoria wydatku pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="06523-125">In the Default expense category field, enter or select a value.</span></span>
21. <span data-ttu-id="06523-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="06523-126">Click Save.</span></span>
22. <span data-ttu-id="06523-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="06523-127">Close the page.</span></span>
23. <span data-ttu-id="06523-128">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Księgowanie > Konfiguracja księgowania.</span><span class="sxs-lookup"><span data-stu-id="06523-128">Go to Project management and accounting > Setup > Posting > Ledger posting setup.</span></span>
24. <span data-ttu-id="06523-129">W polu Typy kont księgowych zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="06523-129">In the Ledger account types field, select an option.</span></span>
25. <span data-ttu-id="06523-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="06523-130">Click New.</span></span>
26. <span data-ttu-id="06523-131">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="06523-131">In the list, mark the selected row.</span></span>
27. <span data-ttu-id="06523-132">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="06523-132">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="06523-133">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="06523-133">In the Main account field, specify the desired values.</span></span>
29. <span data-ttu-id="06523-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="06523-134">Click Save.</span></span>
30. <span data-ttu-id="06523-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="06523-135">Close the page.</span></span>
31. <span data-ttu-id="06523-136">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena transferowa.</span><span class="sxs-lookup"><span data-stu-id="06523-136">Go to Project management and accounting > Setup > Prices > Transfer price.</span></span>
32. <span data-ttu-id="06523-137">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="06523-137">Click New.</span></span>
33. <span data-ttu-id="06523-138">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="06523-138">In the Effective date field, enter a date.</span></span>
34. <span data-ttu-id="06523-139">W polu Firma pożyczająca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="06523-139">In the Borrowing legal entity field, enter or select a value.</span></span>
35. <span data-ttu-id="06523-140">W polu Model ceny transferu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="06523-140">In the Transfer price model field, select an option.</span></span>
36. <span data-ttu-id="06523-141">W polu Ceny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="06523-141">In the Pricing field, enter a number.</span></span>
37. <span data-ttu-id="06523-142">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="06523-142">Click Save.</span></span>

