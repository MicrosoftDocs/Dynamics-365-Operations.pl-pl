--- 
title: "Badanie lub rozwiązywanie wyjątków"
description: "Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców."
author: abruer
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0008ec19fb9a465a8b342d5c96654f109133f705
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="c240c-103">Badanie lub rozwiązywanie wyjątków</span><span class="sxs-lookup"><span data-stu-id="c240c-103">Research or resolve exceptions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c240c-104">Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="c240c-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="c240c-105">Można także skonfigurować przepływ pracy faktur od dostawcy, aby uruchamiał zasady dotyczące faktur od dostawców podczas każdego przesłania faktur do przepływu.</span><span class="sxs-lookup"><span data-stu-id="c240c-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="c240c-106">Zasady faktur od dostawców nie dotyczą faktur, które zostały utworzone w rejestrze faktur lub arkuszu faktur.</span><span class="sxs-lookup"><span data-stu-id="c240c-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="c240c-107">Funkcja sprawdzania poprawności uzgadniania faktur nie używa zasad dotyczących faktur od dostawców, ale jest konfigurowana na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="c240c-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="c240c-108">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="c240c-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="c240c-109">Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.</span><span class="sxs-lookup"><span data-stu-id="c240c-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="c240c-110">Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.</span><span class="sxs-lookup"><span data-stu-id="c240c-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="c240c-111">Przygotowanie do tworzenia zasad dotyczących faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="c240c-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="c240c-112">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="c240c-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="c240c-113">Kliknij kartę Weryfikacja faktury.</span><span class="sxs-lookup"><span data-stu-id="c240c-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="c240c-114">Zaznacz lub wyczyść pole wyboru Automatycznie aktualizuj stan nagłówka faktury.</span><span class="sxs-lookup"><span data-stu-id="c240c-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="c240c-115">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c240c-115">Click OK.</span></span>
5. <span data-ttu-id="c240c-116">W polu Księguj fakturę z rozbieżnościami zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="c240c-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="c240c-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c240c-117">Close the page.</span></span>
7. <span data-ttu-id="c240c-118">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="c240c-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="c240c-119">Kliknij opcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="c240c-119">Click Parameters.</span></span>
9. <span data-ttu-id="c240c-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c240c-120">Click btnAdd.</span></span>
10. <span data-ttu-id="c240c-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c240c-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="c240c-122">Tworzenie typów reguł dla faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="c240c-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="c240c-123">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia zasad > Typy reguł faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="c240c-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="c240c-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c240c-124">Click New.</span></span>
3. <span data-ttu-id="c240c-125">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c240c-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="c240c-126">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c240c-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c240c-127">W polu Nazwa kwerendy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c240c-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c240c-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c240c-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c240c-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c240c-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c240c-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c240c-130">Click Save.</span></span>
9. <span data-ttu-id="c240c-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c240c-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="c240c-132">Definiowanie zasad dotyczących faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="c240c-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="c240c-133">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="c240c-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="c240c-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c240c-134">Click New.</span></span>
3. <span data-ttu-id="c240c-135">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c240c-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c240c-136">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c240c-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c240c-137">Rozwiń lub zwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="c240c-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="c240c-138">W drzewie zaznacz pozycję „Contoso Entertainment System USA”.</span><span class="sxs-lookup"><span data-stu-id="c240c-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="c240c-139">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c240c-139">Click Add.</span></span>
8. <span data-ttu-id="c240c-140">Rozwiń lub zwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="c240c-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="c240c-141">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="c240c-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="c240c-142">W polu Opis reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c240c-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="c240c-143">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="c240c-143">Click Filter.</span></span>
12. <span data-ttu-id="c240c-144">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c240c-144">Click Add.</span></span>
13. <span data-ttu-id="c240c-145">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c240c-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="c240c-146">W polu Tabela kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c240c-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="c240c-147">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c240c-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="c240c-148">W polu Tabela pochodna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c240c-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="c240c-149">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c240c-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="c240c-150">W polu Pole kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c240c-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="c240c-151">W polu Pole wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c240c-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="c240c-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c240c-152">Close the page.</span></span>
21. <span data-ttu-id="c240c-153">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c240c-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="c240c-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c240c-154">Click OK.</span></span>
23. <span data-ttu-id="c240c-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c240c-155">Click OK.</span></span>
24. <span data-ttu-id="c240c-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c240c-156">Close the page.</span></span>
25. <span data-ttu-id="c240c-157">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c240c-157">Close the page.</span></span>


