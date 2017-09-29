--- 
title: "Konfigurowanie standardowych kosztów robocizny i wydatków"
description: "W tej procedurze pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 432b5b195b29fb03786cb0560e277735b531b7d7
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="3fd08-103">Konfigurowanie standardowych kosztów robocizny i wydatków</span><span class="sxs-lookup"><span data-stu-id="3fd08-103">Configure standard costs for labor and expenses</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fd08-104">W tej procedurze pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.</span><span class="sxs-lookup"><span data-stu-id="3fd08-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="3fd08-105">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="3fd08-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="3fd08-106">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (godzina).</span><span class="sxs-lookup"><span data-stu-id="3fd08-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="3fd08-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3fd08-107">Click New.</span></span>
3. <span data-ttu-id="3fd08-108">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="3fd08-109">W polu Koszt własny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="3fd08-110">Można ustawić standardową wartość kosztu własnego dla kategorii projektu lub ustawić koszt własny według numeru pracownika, numeru projektu, kategorii, daty lub dowolnej kombinacji tych parametrów.</span><span class="sxs-lookup"><span data-stu-id="3fd08-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="3fd08-111">Stosowany będzie koszt własny o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="3fd08-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="3fd08-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3fd08-112">Click Save.</span></span>
6. <span data-ttu-id="3fd08-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-113">Close the page.</span></span>
7. <span data-ttu-id="3fd08-114">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (godzina).</span><span class="sxs-lookup"><span data-stu-id="3fd08-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="3fd08-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3fd08-115">Click New.</span></span>
9. <span data-ttu-id="3fd08-116">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="3fd08-117">W polu Ważny dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="3fd08-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="3fd08-118">W polu Ceny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="3fd08-119">Użytkownik może ustawić standardową cenę sprzedaży dla transakcji godzinowych lub dla kategorii projektu.</span><span class="sxs-lookup"><span data-stu-id="3fd08-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="3fd08-120">Może również ustawić ceny sprzedaży według numeru pracownika, numeru projektu, kategorii, daty transakcji albo dowolnej kombinacji tych wartości.</span><span class="sxs-lookup"><span data-stu-id="3fd08-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="3fd08-121">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu godzin jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="3fd08-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="3fd08-122">Jeśli na przykład ustawiono zarówno ogólną cenę sprzedaży, jak i cenę sprzedaży dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="3fd08-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="3fd08-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3fd08-123">Click Save.</span></span>
13. <span data-ttu-id="3fd08-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-124">Close the page.</span></span>
14. <span data-ttu-id="3fd08-125">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (wydatek).</span><span class="sxs-lookup"><span data-stu-id="3fd08-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="3fd08-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3fd08-126">Click New.</span></span>
16. <span data-ttu-id="3fd08-127">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="3fd08-128">W polu Koszt własny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="3fd08-129">Można wypełnić wiele pól, ale to jest minimum niezbędne do zapisania rekordu.</span><span class="sxs-lookup"><span data-stu-id="3fd08-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="3fd08-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3fd08-130">Click Save.</span></span>
19. <span data-ttu-id="3fd08-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-131">Close the page.</span></span>
20. <span data-ttu-id="3fd08-132">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (wydatek).</span><span class="sxs-lookup"><span data-stu-id="3fd08-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="3fd08-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3fd08-133">Click New.</span></span>
22. <span data-ttu-id="3fd08-134">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="3fd08-135">W polu Ważny dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="3fd08-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="3fd08-136">W polu Ceny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3fd08-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="3fd08-137">Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu wydatków jest ceną sprzedaży o najwyższym poziomie szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="3fd08-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="3fd08-138">Jeśli na przykład ustawiono cenę sprzedaży zarówno ogólną, jak i dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="3fd08-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="3fd08-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3fd08-139">Click Save.</span></span>


