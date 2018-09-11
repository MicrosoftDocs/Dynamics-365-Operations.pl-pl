--- 
title: "Konfigurowanie profili księgowania środków trwałych"
description: "W tym przewodniku po zadaniach zostaną skonfigurowane profile księgowania środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: b00ad7f8dc77eb80e0ed322c1e09624398cfc4d5
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="08552-103">Konfigurowanie profili księgowania środków trwałych</span><span class="sxs-lookup"><span data-stu-id="08552-103">Set up fixed asset posting profiles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08552-104">W tym przewodniku po zadaniach zostaną skonfigurowane profile księgowania środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="08552-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="08552-105">Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="08552-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="08552-106">Przykłady zamieszczone w przewodniku po zadaniach dotyczą podstawowego profilu księgowania, podczas gdy faktycznie profile księgowania należy utworzyć dla określonych planów kont oraz wymagań dotyczących sprawozdawczości finansowej.</span><span class="sxs-lookup"><span data-stu-id="08552-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="08552-107">Wybierz kolejno opcje Środki trwałe > Ustawienia > Profile księgowania środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="08552-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="08552-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="08552-108">Click New.</span></span>
3. <span data-ttu-id="08552-109">W polu Profil księgowania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="08552-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="08552-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="08552-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="08552-111">Należy utworzyć profil księgowania dla każdego typu transakcji środków trwałych, którego będziesz używać podczas pracy ze środkami trwałymi.</span><span class="sxs-lookup"><span data-stu-id="08552-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="08552-112">W tym przewodniku po zadaniach proces rozpoczyna się od typu transakcji Nabycie.</span><span class="sxs-lookup"><span data-stu-id="08552-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="08552-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-113">Click Add.</span></span>
6. <span data-ttu-id="08552-114">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="08552-115">Pole Grupowania pozwala zdefiniować profil księgowania do poziomu Tabela (jedno konto utworzone dla każdego środka trwałego) lub Grupa (jedno konto utworzone dla każdej grupy środków trwałych).</span><span class="sxs-lookup"><span data-stu-id="08552-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="08552-116">W tym przewodniku po zadaniach pozostawię ustawioną wartość „Wszystko”, aby profil był stosowany do wszystkich środków trwałych wpisanych do określonej księgi.</span><span class="sxs-lookup"><span data-stu-id="08552-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="08552-117">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="08552-118">Dla transakcji nabycia można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.</span><span class="sxs-lookup"><span data-stu-id="08552-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="08552-119">W polu Typ transakcji zaznacz opcję „Korekta wartości początkowej”.</span><span class="sxs-lookup"><span data-stu-id="08552-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="08552-120">Dla transakcji korekty wartości początkowej zostaną wykorzystane te same konta, jak dla transakcji nabycia.</span><span class="sxs-lookup"><span data-stu-id="08552-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="08552-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-121">Click Add.</span></span>
10. <span data-ttu-id="08552-122">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="08552-123">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="08552-124">Dla transakcji korekt wartości początkowej można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.</span><span class="sxs-lookup"><span data-stu-id="08552-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="08552-125">W polu Typ transakcji zaznacz opcję „Amortyzacja”.</span><span class="sxs-lookup"><span data-stu-id="08552-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="08552-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-126">Click Add.</span></span>
14. <span data-ttu-id="08552-127">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="08552-128">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="08552-129">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="08552-130">W polu Typ transakcji zaznacz opcję „Korekta amortyzacji”.</span><span class="sxs-lookup"><span data-stu-id="08552-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="08552-131">Dla transakcji korekty amortyzacji zostaną wykorzystane te same konta, jak dla transakcji amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="08552-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="08552-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-132">Click Add.</span></span>
19. <span data-ttu-id="08552-133">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="08552-134">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="08552-135">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="08552-136">W polu Typ transakcji zaznacz opcję „Likwidacja — sprzedaż”.</span><span class="sxs-lookup"><span data-stu-id="08552-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="08552-137">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-137">Click Add.</span></span>
24. <span data-ttu-id="08552-138">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="08552-139">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="08552-140">Dla transakcji likwidacji można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.</span><span class="sxs-lookup"><span data-stu-id="08552-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="08552-141">W polu Typ transakcji zaznacz opcję „Likwidacja — odpadki”.</span><span class="sxs-lookup"><span data-stu-id="08552-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="08552-142">Te same konta zostaną wykorzystane do likwidacji przez sprzedaż i przez uznanie za odpadki.</span><span class="sxs-lookup"><span data-stu-id="08552-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="08552-143">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-143">Click Add.</span></span>
28. <span data-ttu-id="08552-144">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="08552-145">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="08552-146">Dla transakcji likwidacji można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.</span><span class="sxs-lookup"><span data-stu-id="08552-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="08552-147">Rozwiń sekcję Likwidacja.</span><span class="sxs-lookup"><span data-stu-id="08552-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="08552-148">Profile księgowania likwidacji należy skonfigurować zarówno dla operacji sprzedaży, jak i uznawania za odpadki.</span><span class="sxs-lookup"><span data-stu-id="08552-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="08552-149">Zaczniemy od transakcji likwidacji przez sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="08552-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="08552-150">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-150">Click Add.</span></span>
32. <span data-ttu-id="08552-151">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="08552-152">W polu Księguj wartość zaznacz opcję „Wartość nabycia”.</span><span class="sxs-lookup"><span data-stu-id="08552-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="08552-153">Wartość nabycia uwzględni wartości nabycia i korekty wartości początkowej we wszystkich latach.</span><span class="sxs-lookup"><span data-stu-id="08552-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="08552-154">Można także zdefiniować konta dla tych typów transakcji osobno.</span><span class="sxs-lookup"><span data-stu-id="08552-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="08552-155">W procesie likwidacji można ustawić używanie różnych kont w zależności od tego, czy likwidacja skutkuje zyskiem czy stratą.</span><span class="sxs-lookup"><span data-stu-id="08552-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="08552-156">W polu Typu wartości sprzedaży ustawię „Wszystko”, aby używać tych samych kont dla wszystkich typów likwidacji.</span><span class="sxs-lookup"><span data-stu-id="08552-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="08552-157">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="08552-158">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="08552-159">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-159">Click Add.</span></span>
37. <span data-ttu-id="08552-160">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="08552-161">W polu Księguj wartość zaznacz opcję „Amortyzacja (lata ubiegłe)”.</span><span class="sxs-lookup"><span data-stu-id="08552-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="08552-162">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="08552-163">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="08552-164">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-164">Click Add.</span></span>
41. <span data-ttu-id="08552-165">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="08552-166">W polu Księguj wartość zaznacz opcję „Amortyzacja (ten rok)”.</span><span class="sxs-lookup"><span data-stu-id="08552-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="08552-167">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="08552-168">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="08552-169">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-169">Click Add.</span></span>
46. <span data-ttu-id="08552-170">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="08552-171">W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (lata ubiegłe)”.</span><span class="sxs-lookup"><span data-stu-id="08552-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="08552-172">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="08552-173">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="08552-174">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-174">Click Add.</span></span>
51. <span data-ttu-id="08552-175">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="08552-176">W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (ten rok)”.</span><span class="sxs-lookup"><span data-stu-id="08552-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="08552-177">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="08552-178">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="08552-179">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-179">Click Add.</span></span>
56. <span data-ttu-id="08552-180">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="08552-181">W polu Księguj wartość zaznacz opcję „Wartość księgowa netto”.</span><span class="sxs-lookup"><span data-stu-id="08552-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="08552-182">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="08552-183">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="08552-184">W polu Sprzedaż lub uznanie za odpadki wybierz opcję „Odpadki”.</span><span class="sxs-lookup"><span data-stu-id="08552-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="08552-185">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-185">Click Add.</span></span>
62. <span data-ttu-id="08552-186">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="08552-187">W polu Księguj wartość zaznacz opcję „Wartość nabycia”.</span><span class="sxs-lookup"><span data-stu-id="08552-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="08552-188">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="08552-189">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="08552-190">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-190">Click Add.</span></span>
67. <span data-ttu-id="08552-191">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="08552-192">W polu Księguj wartość zaznacz opcję „Amortyzacja (lata ubiegłe)”.</span><span class="sxs-lookup"><span data-stu-id="08552-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="08552-193">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="08552-194">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="08552-195">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-195">Click Add.</span></span>
71. <span data-ttu-id="08552-196">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="08552-197">W polu Księguj wartość zaznacz opcję „Amortyzacja (ten rok)”.</span><span class="sxs-lookup"><span data-stu-id="08552-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="08552-198">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="08552-199">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="08552-200">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-200">Click Add.</span></span>
76. <span data-ttu-id="08552-201">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="08552-202">W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (lata ubiegłe)”.</span><span class="sxs-lookup"><span data-stu-id="08552-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="08552-203">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="08552-204">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="08552-205">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-205">Click Add.</span></span>
81. <span data-ttu-id="08552-206">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="08552-207">W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (ten rok)”.</span><span class="sxs-lookup"><span data-stu-id="08552-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="08552-208">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="08552-209">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="08552-210">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="08552-210">Click Add.</span></span>
86. <span data-ttu-id="08552-211">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="08552-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="08552-212">W polu Księguj wartość zaznacz opcję „Wartość księgowa netto”.</span><span class="sxs-lookup"><span data-stu-id="08552-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="08552-213">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="08552-214">W polu Konto przeciwstawne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="08552-214">In the Offset account field, specify the desired values.</span></span>


