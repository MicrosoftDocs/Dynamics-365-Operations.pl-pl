---
title: Konfigurowanie standardowych kosztów robocizny i wydatków
description: W tej procedurze pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572403"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="be907-103">Konfigurowanie standardowych kosztów robocizny i wydatków</span><span class="sxs-lookup"><span data-stu-id="be907-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="be907-104">W tej procedurze pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.</span><span class="sxs-lookup"><span data-stu-id="be907-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="be907-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="be907-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="be907-106">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (godzina).</span><span class="sxs-lookup"><span data-stu-id="be907-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="be907-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="be907-107">Click New.</span></span>
3. <span data-ttu-id="be907-108">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="be907-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="be907-109">W polu Koszt własny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="be907-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="be907-110">Można ustawić standardową wartość kosztu własnego dla kategorii projektu lub ustawić koszt własny według numeru pracownika, numeru projektu, kategorii, daty lub dowolnej kombinacji tych parametrów.</span><span class="sxs-lookup"><span data-stu-id="be907-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="be907-111">Stosowany będzie koszt własny o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="be907-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="be907-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="be907-112">Click Save.</span></span>
6. <span data-ttu-id="be907-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="be907-113">Close the page.</span></span>
7. <span data-ttu-id="be907-114">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (godzina).</span><span class="sxs-lookup"><span data-stu-id="be907-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="be907-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="be907-115">Click New.</span></span>
9. <span data-ttu-id="be907-116">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="be907-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="be907-117">W polu Ważny dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="be907-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="be907-118">W polu Ceny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="be907-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="be907-119">Użytkownik może ustawić standardową cenę sprzedaży dla transakcji godzinowych lub dla kategorii projektu.</span><span class="sxs-lookup"><span data-stu-id="be907-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="be907-120">Może również ustawić ceny sprzedaży według numeru pracownika, numeru projektu, kategorii, daty transakcji albo dowolnej kombinacji tych wartości.</span><span class="sxs-lookup"><span data-stu-id="be907-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="be907-121">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu godzin jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="be907-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="be907-122">Jeśli na przykład ustawiono zarówno ogólną cenę sprzedaży, jak i cenę sprzedaży dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="be907-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="be907-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="be907-123">Click Save.</span></span>
13. <span data-ttu-id="be907-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="be907-124">Close the page.</span></span>
14. <span data-ttu-id="be907-125">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (wydatek).</span><span class="sxs-lookup"><span data-stu-id="be907-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="be907-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="be907-126">Click New.</span></span>
16. <span data-ttu-id="be907-127">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="be907-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="be907-128">W polu Koszt własny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="be907-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="be907-129">Można wypełnić wiele pól, ale to jest minimum niezbędne do zapisania rekordu.</span><span class="sxs-lookup"><span data-stu-id="be907-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="be907-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="be907-130">Click Save.</span></span>
19. <span data-ttu-id="be907-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="be907-131">Close the page.</span></span>
20. <span data-ttu-id="be907-132">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (wydatek).</span><span class="sxs-lookup"><span data-stu-id="be907-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="be907-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="be907-133">Click New.</span></span>
22. <span data-ttu-id="be907-134">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="be907-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="be907-135">W polu Ważny dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="be907-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="be907-136">W polu Ceny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="be907-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="be907-137">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu wydatków jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="be907-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="be907-138">Jeśli na przykład ustawiono cenę sprzedaży zarówno ogólną, jak i dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="be907-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="be907-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="be907-139">Click Save.</span></span>

