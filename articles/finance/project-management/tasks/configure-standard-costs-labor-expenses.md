---
title: Konfigurowanie standardowych kosztów robocizny i wydatków
description: W tym temacie pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185412"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="40aec-103">Konfigurowanie standardowych kosztów robocizny i wydatków</span><span class="sxs-lookup"><span data-stu-id="40aec-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="40aec-104">W tym temacie pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.</span><span class="sxs-lookup"><span data-stu-id="40aec-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="40aec-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="40aec-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="40aec-106">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (godzina)**.</span><span class="sxs-lookup"><span data-stu-id="40aec-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="40aec-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="40aec-107">Select **New**.</span></span>
3. <span data-ttu-id="40aec-108">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="40aec-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="40aec-109">W polu **Koszt własny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="40aec-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="40aec-110">Można ustawić standardową wartość kosztu własnego dla kategorii projektu lub ustawić koszt własny według numeru pracownika, numeru projektu, kategorii, daty lub dowolnej kombinacji tych parametrów.</span><span class="sxs-lookup"><span data-stu-id="40aec-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="40aec-111">Stosowany będzie koszt własny o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="40aec-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="40aec-112">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="40aec-112">Select **Save**.</span></span>
6. <span data-ttu-id="40aec-113">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (godzina)**.</span><span class="sxs-lookup"><span data-stu-id="40aec-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="40aec-114">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="40aec-114">Select **New**.</span></span>
8. <span data-ttu-id="40aec-115">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="40aec-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="40aec-116">W polu **Ważny dla** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="40aec-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="40aec-117">W polu **Ceny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="40aec-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="40aec-118">Użytkownik może ustawić standardową cenę sprzedaży dla transakcji godzinowych lub dla kategorii projektu.</span><span class="sxs-lookup"><span data-stu-id="40aec-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="40aec-119">Może również ustawić ceny sprzedaży według numeru pracownika, numeru projektu, kategorii, daty transakcji albo dowolnej kombinacji tych wartości.</span><span class="sxs-lookup"><span data-stu-id="40aec-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="40aec-120">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu godzin jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="40aec-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="40aec-121">Jeśli na przykład ustawiono zarówno ogólną cenę sprzedaży, jak i cenę sprzedaży dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="40aec-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="40aec-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="40aec-122">Select **Save**.</span></span>
12. <span data-ttu-id="40aec-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="40aec-123">Close the page.</span></span>
13. <span data-ttu-id="40aec-124">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (wydatek)**.</span><span class="sxs-lookup"><span data-stu-id="40aec-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="40aec-125">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="40aec-125">Select **New**.</span></span>
15. <span data-ttu-id="40aec-126">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="40aec-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="40aec-127">W polu **Koszt własny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="40aec-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="40aec-128">Można wypełnić wiele pól, ale to jest minimum niezbędne do zapisania rekordu.</span><span class="sxs-lookup"><span data-stu-id="40aec-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="40aec-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="40aec-129">Select **Save**.</span></span>
18. <span data-ttu-id="40aec-130">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (wydatek)**.</span><span class="sxs-lookup"><span data-stu-id="40aec-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="40aec-131">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="40aec-131">Select **New**.</span></span>
20. <span data-ttu-id="40aec-132">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="40aec-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="40aec-133">W polu **Ważny dla** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="40aec-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="40aec-134">W polu **Ceny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="40aec-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="40aec-135">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu wydatków jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="40aec-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="40aec-136">Jeśli na przykład ustawiono cenę sprzedaży zarówno ogólną, jak i dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="40aec-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="40aec-137">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="40aec-137">Select **Save**.</span></span>

