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
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140100"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="f0da0-103">Konfigurowanie standardowych kosztów robocizny i wydatków</span><span class="sxs-lookup"><span data-stu-id="f0da0-103">Configure standard costs for labor and expenses</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f0da0-104">W tym temacie pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.</span><span class="sxs-lookup"><span data-stu-id="f0da0-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="f0da0-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="f0da0-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="f0da0-106">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (godzina)**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="f0da0-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-107">Select **New**.</span></span>
3. <span data-ttu-id="f0da0-108">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="f0da0-109">W polu **Koszt własny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="f0da0-110">Można ustawić standardową wartość kosztu własnego dla kategorii projektu lub ustawić koszt własny według numeru pracownika, numeru projektu, kategorii, daty lub dowolnej kombinacji tych parametrów.</span><span class="sxs-lookup"><span data-stu-id="f0da0-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="f0da0-111">Stosowany będzie koszt własny o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="f0da0-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="f0da0-112">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-112">Select **Save**.</span></span>
6. <span data-ttu-id="f0da0-113">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (godzina)**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="f0da0-114">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-114">Select **New**.</span></span>
8. <span data-ttu-id="f0da0-115">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="f0da0-116">W polu **Ważny dla** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="f0da0-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="f0da0-117">W polu **Ceny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="f0da0-118">Użytkownik może ustawić standardową cenę sprzedaży dla transakcji godzinowych lub dla kategorii projektu.</span><span class="sxs-lookup"><span data-stu-id="f0da0-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="f0da0-119">Może również ustawić ceny sprzedaży według numeru pracownika, numeru projektu, kategorii, daty transakcji albo dowolnej kombinacji tych wartości.</span><span class="sxs-lookup"><span data-stu-id="f0da0-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="f0da0-120">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu godzin jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="f0da0-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="f0da0-121">Jeśli na przykład ustawiono zarówno ogólną cenę sprzedaży, jak i cenę sprzedaży dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="f0da0-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="f0da0-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-122">Select **Save**.</span></span>
12. <span data-ttu-id="f0da0-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-123">Close the page.</span></span>
13. <span data-ttu-id="f0da0-124">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (wydatek)**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="f0da0-125">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-125">Select **New**.</span></span>
15. <span data-ttu-id="f0da0-126">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="f0da0-127">W polu **Koszt własny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="f0da0-128">Można wypełnić wiele pól, ale to jest minimum niezbędne do zapisania rekordu.</span><span class="sxs-lookup"><span data-stu-id="f0da0-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="f0da0-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-129">Select **Save**.</span></span>
18. <span data-ttu-id="f0da0-130">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (wydatek)**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="f0da0-131">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-131">Select **New**.</span></span>
20. <span data-ttu-id="f0da0-132">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="f0da0-133">W polu **Ważny dla** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="f0da0-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="f0da0-134">W polu **Ceny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0da0-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="f0da0-135">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu wydatków jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="f0da0-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="f0da0-136">Jeśli na przykład ustawiono cenę sprzedaży zarówno ogólną, jak i dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="f0da0-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="f0da0-137">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f0da0-137">Select **Save**.</span></span>

