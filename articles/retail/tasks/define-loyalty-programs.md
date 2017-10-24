--- 
title: "Definiowanie programów lojalnościowych"
description: "W tej procedurze pokazano sposób konfigurowania programu lojalnościowego z dwoma warstwami lojalnościowymi."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7a949d5cb4f01518b46bc4b1769de34196109050
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-loyalty-programs"></a><span data-ttu-id="6d78b-103">Definiowanie programów lojalnościowych</span><span class="sxs-lookup"><span data-stu-id="6d78b-103">Define loyalty programs</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="6d78b-104">W tej procedurze pokazano sposób konfigurowania programu lojalnościowego z dwoma warstwami lojalnościowymi.</span><span class="sxs-lookup"><span data-stu-id="6d78b-104">This procedure shows how to set up a loyalty program with two loyalty tiers.</span></span> <span data-ttu-id="6d78b-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="6d78b-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="6d78b-106">Wybierz kolejno opcje Handel detaliczny i inny > ..</span><span class="sxs-lookup"><span data-stu-id="6d78b-106">Go to Retail and commerce > ..</span></span> <span data-ttu-id="6d78b-107">> Programy lojalnościowe.</span><span class="sxs-lookup"><span data-stu-id="6d78b-107">> Loyalty programs.</span></span>
2. <span data-ttu-id="6d78b-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-108">Click New.</span></span>
3. <span data-ttu-id="6d78b-109">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d78b-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6d78b-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="6d78b-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6d78b-111">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-111">Click Add line.</span></span>
6. <span data-ttu-id="6d78b-112">W polu Poziom wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="6d78b-112">In the Level field, enter a number.</span></span>
7. <span data-ttu-id="6d78b-113">W polu Warstwa nadaj nazwę warstwie lojalnościowej.</span><span class="sxs-lookup"><span data-stu-id="6d78b-113">In the Tier field, enter a name for the loyalty tier.</span></span>
8. <span data-ttu-id="6d78b-114">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d78b-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="6d78b-115">W polu Zakres dat kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-115">In the Date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6d78b-116">Ten zakres dat powinien sięgać w przyszłość.</span><span class="sxs-lookup"><span data-stu-id="6d78b-116">This date interval should extend into the future.</span></span> <span data-ttu-id="6d78b-117">Na przykład jeśli wybrany interwał dat dla warstwy Gold ma jeden rok, wszyscy odbiorcy, którzy kwalifikują się do warstwy Gold, mogą otrzymać nagrody przypisane do warstwy Gold poziomu przez okres jednego roku.</span><span class="sxs-lookup"><span data-stu-id="6d78b-117">For example, if the date interval that is selected for gold tier is a one-year period, any customer who qualifies for the gold tier can receive the rewards that are assigned to the gold tier for one year.</span></span> <span data-ttu-id="6d78b-118">Jeśli odbiorca kwalifikuje się ponownie do warstwy Gold, kiedy jest w tej warstwie, data wygaśnięcia jego statusu w tej warstwie zostaje przedłużona o kolejny rok od daty ponownej kwalifikacji.</span><span class="sxs-lookup"><span data-stu-id="6d78b-118">If the customer re-qualifies for the gold tier while they are in the tier, the date that the tier expires is extended by another year from the date when they re-qualify.</span></span>  
10. <span data-ttu-id="6d78b-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-119">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="6d78b-120">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-120">Click Add line.</span></span>
12. <span data-ttu-id="6d78b-121">W polu Poziom wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="6d78b-121">In the Level field, enter a number.</span></span>
13. <span data-ttu-id="6d78b-122">W polu Warstwa nadaj nazwę warstwie lojalnościowej.</span><span class="sxs-lookup"><span data-stu-id="6d78b-122">In the Tier field, enter a name for the loyalty tier.</span></span>
14. <span data-ttu-id="6d78b-123">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d78b-123">In the Description field, type a value.</span></span>
15. <span data-ttu-id="6d78b-124">W polu Zakres dat kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-124">In the Date interval field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="6d78b-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-125">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="6d78b-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-126">Click Save.</span></span>
18. <span data-ttu-id="6d78b-127">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6d78b-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6d78b-128">Zasady warstwy definiują minimalną liczbę punktów lojalnościowych, jaką należy uzyskać w przedziale czasu, aby kwalifikować się do warstwy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-128">Tier rules define the minimum number of a reward point needed to be earned during a time period to qualify for the tier.</span></span>  
19. <span data-ttu-id="6d78b-129">Przełącz rozwinięcie sekcji Zasady warstwy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-129">Toggle the expansion of the Tier rules section.</span></span>
20. <span data-ttu-id="6d78b-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-130">Click New.</span></span>
    * <span data-ttu-id="6d78b-131">Można mieć kilka zasad warstwy w jednej warstwie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-131">You can have more than one tier rule per tier.</span></span> <span data-ttu-id="6d78b-132">Na przykład można mieć trzy różne kryteria osiągnięcia warstwy: wydanie 500 USD w ciągu miesiąca, wydanie 1000 USD w ciągu roku i zawarcie 20 transakcji w ciągu roku.</span><span class="sxs-lookup"><span data-stu-id="6d78b-132">For example, you could have three different criteria to earn a tier; by spending $500 in one month, by spending $1000 over one year, and by having 20 transactions in one year.</span></span> <span data-ttu-id="6d78b-133">W tym celu należałoby utworzyć trzy zasady warstwy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-133">To do this, you would need to create three tier rules.</span></span>  
21. <span data-ttu-id="6d78b-134">W polu Punkty lojalnościowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-134">In the Reward point field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6d78b-135">Powinien to być niewymienialny punkt lojalnościowy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-135">This should be a non-redeemable loyalty reward point.</span></span>  
22. <span data-ttu-id="6d78b-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-136">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="6d78b-137">W polu Minimalna liczba przyznanych punktów lojalnościowych wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="6d78b-137">In the Minimum issued points field, enter a number.</span></span>
    * <span data-ttu-id="6d78b-138">Jeśli wszyscy odbiorcy mogą kwalifikować się do najniższej warstwy lojalnościowej po prostu przez uczestnictwo w programie, wprowadź „0”.</span><span class="sxs-lookup"><span data-stu-id="6d78b-138">For the lowest level tier, if all customers qualify simply by participating in the program, enter '0'.</span></span>  
24. <span data-ttu-id="6d78b-139">W polu Zakres dat oceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-139">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6d78b-140">Ten zakres dat powinien sięgać w przeszłość.</span><span class="sxs-lookup"><span data-stu-id="6d78b-140">This date interval should extend into the past.</span></span> <span data-ttu-id="6d78b-141">Tylko punkty zdobyte w tym przedziale dat wliczają się do minimalnej wartości przyznanych punktów.</span><span class="sxs-lookup"><span data-stu-id="6d78b-141">Only points earned during this date interval will be counted towards reaching the minimum issued points value.</span></span>  
25. <span data-ttu-id="6d78b-142">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-142">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="6d78b-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-143">Click Save.</span></span>
27. <span data-ttu-id="6d78b-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6d78b-144">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="6d78b-145">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6d78b-145">Click New.</span></span>
29. <span data-ttu-id="6d78b-146">W polu Punkty lojalnościowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-146">In the Reward point field, click the drop-down button to open the lookup.</span></span>
30. <span data-ttu-id="6d78b-147">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-147">In the list, click the link in the selected row.</span></span>
31. <span data-ttu-id="6d78b-148">W polu Minimalna liczba przyznanych punktów lojalnościowych wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="6d78b-148">In the Minimum issued points field, enter a number.</span></span>
32. <span data-ttu-id="6d78b-149">W polu Zakres dat oceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-149">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6d78b-150">Ten zakres dat powinien sięgać w przeszłość.</span><span class="sxs-lookup"><span data-stu-id="6d78b-150">This date interval should extend into the past.</span></span>  
33. <span data-ttu-id="6d78b-151">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-151">In the list, click the link in the selected row.</span></span>
34. <span data-ttu-id="6d78b-152">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-152">Click Save.</span></span>
35. <span data-ttu-id="6d78b-153">Kliknij opcję Grupy cenowe.</span><span class="sxs-lookup"><span data-stu-id="6d78b-153">Click Price groups.</span></span>
    * <span data-ttu-id="6d78b-154">Jeśli chcesz przyznać odbiorcom rabaty lojalnościowe,</span><span class="sxs-lookup"><span data-stu-id="6d78b-154">If you want to give loyalty customers discounts.</span></span> <span data-ttu-id="6d78b-155">musisz przypisać jedną lub więcej grup cenowych do programu lojalnościowego i do rabatów.</span><span class="sxs-lookup"><span data-stu-id="6d78b-155">you'll need to assign one or more price groups to the loyalty program and assign the price groups to discounts.</span></span> <span data-ttu-id="6d78b-156">Najlepiej nie mieszać grup cenowych między różnymi typami rozwiązań rabatowych.</span><span class="sxs-lookup"><span data-stu-id="6d78b-156">It is a best practise to not mix price groups across different types of discounting entities.</span></span>  <span data-ttu-id="6d78b-157">Na przykład nie używaj jednej grupy cenowej dla rabatu lojalnościowego i rabat kanału.</span><span class="sxs-lookup"><span data-stu-id="6d78b-157">For example, don't use the same price group for a loyalty discount and a channel discount.</span></span>  
36. <span data-ttu-id="6d78b-158">W polu Grupa cenowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d78b-158">In the Price group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6d78b-159">Łącze Grupy cenowe u góry strony jest dla programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="6d78b-159">The Price groups link at the top of the page is for the loyalty program.</span></span> <span data-ttu-id="6d78b-160">Łącze Grupy cenowe na skróconej karcie Warstwy programu jest tylko dla określonej warstwy lojalności.</span><span class="sxs-lookup"><span data-stu-id="6d78b-160">The Price groups link in the Program tiers fasttab is for a specific loyalty tier only.</span></span>  
37. <span data-ttu-id="6d78b-161">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6d78b-161">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="6d78b-162">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-162">Click Save.</span></span>
39. <span data-ttu-id="6d78b-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d78b-163">Close the page.</span></span>
40. <span data-ttu-id="6d78b-164">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d78b-164">Click Save.</span></span>


