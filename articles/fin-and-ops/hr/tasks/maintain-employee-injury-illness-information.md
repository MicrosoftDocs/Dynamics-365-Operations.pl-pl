---
title: Obsługa informacji dotyczących urazów i chorób pracowników
description: Zaleca się najpierw wykonać przewodnik po zadaniach „Ustawienia urazów i chorób”, ponieważ część informacji konfiguracyjnych z niego jest używanych w tym miejscu.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7324a1ce08bfe07a7ef96f4a733ebd44cd392ba6
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "856791"
---
# <a name="maintain-employee-injury-and-illness-information"></a><span data-ttu-id="285b5-103">Obsługa informacji dotyczących urazów i chorób pracowników</span><span class="sxs-lookup"><span data-stu-id="285b5-103">Maintain employee injury and illness information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="285b5-104">Zaleca się najpierw wykonać przewodnik po zadaniach „Ustawienia urazów i chorób”, ponieważ część informacji konfiguracyjnych z niego jest używanych w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="285b5-104">It is recommended to complete the 'Setup injury and illness' task guide first, as some of the setup information is used here.</span></span> 



<span data-ttu-id="285b5-105">To nagranie zadania obejmuje podstawowe kroki tworzenia sprawy dotyczącej urazu lub choroby.</span><span class="sxs-lookup"><span data-stu-id="285b5-105">This task recording covers the basic steps to creating an injury or illness case.</span></span> <span data-ttu-id="285b5-106">Oprócz śledzenia szczegółów urazu lub choroby jest również śledzony stan całej sprawy.</span><span class="sxs-lookup"><span data-stu-id="285b5-106">Besides tracking the details of the injury or illness, there is a case status that is tracked as well.</span></span>  <span data-ttu-id="285b5-107">Domyślnie sprawa otrzymuje stan „Otwarta”.</span><span class="sxs-lookup"><span data-stu-id="285b5-107">The case defaults with an 'open' status.</span></span>  <span data-ttu-id="285b5-108">Stanami można zarządzać za pomocą elementu menu „Stan sprawy” na pasku aplikacji w górnej części formularza.</span><span class="sxs-lookup"><span data-stu-id="285b5-108">The statuses can be managed from the 'Case status' menu item in the application bar at the top of the form.</span></span>

1. <span data-ttu-id="285b5-109">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Uraz i choroba > Przypadki urazów lub chorób.</span><span class="sxs-lookup"><span data-stu-id="285b5-109">Go to Human resources > Workers > Injury and illness > Injury or illness incidents.</span></span>
2. <span data-ttu-id="285b5-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="285b5-110">Click New.</span></span>
3. <span data-ttu-id="285b5-111">W polu Opis sprawy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-111">In the Case description field, type a value.</span></span>
    * <span data-ttu-id="285b5-112">Przykład: Uraz nadgarstka</span><span class="sxs-lookup"><span data-stu-id="285b5-112">Example:  Wrist injury</span></span>  
4. <span data-ttu-id="285b5-113">W polu Pracownik wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-113">In the Worker field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-114">Przykład: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="285b5-114">Example: Ahmed Barnett</span></span>  
5. <span data-ttu-id="285b5-115">W polu Data i godzina zdarzenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="285b5-115">In the Date and time of incident field, enter a date and time.</span></span>
    * <span data-ttu-id="285b5-116">Przykład: 1/20/2016 10:00</span><span class="sxs-lookup"><span data-stu-id="285b5-116">Example:  1/20/2016 10:00 AM</span></span>  
6. <span data-ttu-id="285b5-117">W polu Typ urazu lub choroby wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-117">In the Injury or illness type field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-118">Przykład: Złamanie</span><span class="sxs-lookup"><span data-stu-id="285b5-118">Example:  Fracture</span></span>  
7. <span data-ttu-id="285b5-119">W polu Część ciała wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-119">In the Body part field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-120">Przykład: Nadgarstek</span><span class="sxs-lookup"><span data-stu-id="285b5-120">Example:  Wrist</span></span>  
8. <span data-ttu-id="285b5-121">W polu Typ wyniku wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-121">In the Outcome type field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-122">Przykład: Leczenie</span><span class="sxs-lookup"><span data-stu-id="285b5-122">Example:  Therapy</span></span>  
9. <span data-ttu-id="285b5-123">W polu Data i godzina raportowania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="285b5-123">In the Date and time reported field, enter a date and time.</span></span>
    * <span data-ttu-id="285b5-124">Data i godzina zgłoszenia musi być późniejsza niż data i godzina zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="285b5-124">The date and time reported must be later than the date and time of incident.</span></span>  
10. <span data-ttu-id="285b5-125">W polu Osoba, która zgłosiła sprawę wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-125">In the Person who reported case field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-126">Może to być pracownik lub inny światek zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="285b5-126">This could be the employee or another witness to the incident.</span></span>  <span data-ttu-id="285b5-127">Przykład: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="285b5-127">Example: Ahmed Barnett</span></span>  
11. <span data-ttu-id="285b5-128">Rozwiń sekcję Zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="285b5-128">Expand the Incident section.</span></span>
12. <span data-ttu-id="285b5-129">W polu Miejsce wystąpienia zdarzenia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-129">In the Where incident occurred field, type a value.</span></span>
    * <span data-ttu-id="285b5-130">Przykład: Magazyn</span><span class="sxs-lookup"><span data-stu-id="285b5-130">Example:  Warehouse</span></span>  
13. <span data-ttu-id="285b5-131">W polu W miejscu pracy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="285b5-131">Select Yes in the On work premises field.</span></span>
    * <span data-ttu-id="285b5-132">Jeśli zdarzenie wystąpiło w miejscu pracy, zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="285b5-132">If the incident occurred on work premises, select yes.</span></span>  
14. <span data-ttu-id="285b5-133">W polu Data i godzina rozpoczęcia pracy wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="285b5-133">In the Date and time began work field, enter a date and time.</span></span>
    * <span data-ttu-id="285b5-134">Wprowadź datę i godzinę, kiedy przedmiotowa osoba rozpoczęła pracę, zanim doszło do zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="285b5-134">Enter the date and time that affected individual started working, prior to the incident occurring.</span></span>  
15. <span data-ttu-id="285b5-135">W polu Zadania pracownika wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-135">In the Employee job or task field, type a value.</span></span>
    * <span data-ttu-id="285b5-136">Wprowadzania zadanie, które pracownik wykonywał w momencie wystąpienia zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="285b5-136">Enter the job or task the worker was performing when the incident occurred.</span></span>  <span data-ttu-id="285b5-137">Przykład: Ładowanie pudełek.</span><span class="sxs-lookup"><span data-stu-id="285b5-137">Example:  Loading boxes</span></span>  
16. <span data-ttu-id="285b5-138">W polu Przyczyna zdarzenia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-138">In the Cause of incident field, type a value.</span></span>
    * <span data-ttu-id="285b5-139">Wprowadź przyczynę zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="285b5-139">Enter the cause of the incident.</span></span>  <span data-ttu-id="285b5-140">Przykład: Pośliźnięcie na mokrej podłodze.</span><span class="sxs-lookup"><span data-stu-id="285b5-140">Example:  Slipped on wet floor</span></span>  
17. <span data-ttu-id="285b5-141">W polu Poziom ważności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-141">In the Severity level field, enter or select a value.</span></span>
18. <span data-ttu-id="285b5-142">W polu Akcja, która ma być podjęta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-142">In the Action to be taken field, type a value.</span></span>
    * <span data-ttu-id="285b5-143">Przykład: Niezwłocznie usuwanie rozlanych substancji.</span><span class="sxs-lookup"><span data-stu-id="285b5-143">Example:  Clean up spills promptly</span></span>  
19. <span data-ttu-id="285b5-144">W polu Oczekiwane dni nieobecności w pracy wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="285b5-144">In the Expected days away from work field, enter a number.</span></span>
    * <span data-ttu-id="285b5-145">Wprowadź liczbę oczekiwanych dni nieobecności osoby w pracy.</span><span class="sxs-lookup"><span data-stu-id="285b5-145">Enter the number of days that the individual is expected to be away from work.</span></span>  <span data-ttu-id="285b5-146">Gdy osoba powróci do pracy, zaktualizuj pole „Dni na zwolnieniu” o rzeczywistą liczbę dni nieobecności.</span><span class="sxs-lookup"><span data-stu-id="285b5-146">Once the individual returns to work, update the 'Days away from work' field with the actual number of days away.</span></span>  
20. <span data-ttu-id="285b5-147">Rozwiń sekcję Koszty urazu lub choroby.</span><span class="sxs-lookup"><span data-stu-id="285b5-147">Expand the Injury or illness costs section.</span></span>
21. <span data-ttu-id="285b5-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="285b5-148">Click Add.</span></span>
22. <span data-ttu-id="285b5-149">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="285b5-149">In the Date field, enter a date.</span></span>
23. <span data-ttu-id="285b5-150">W polu Typ kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-150">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-151">Przykład:  Leczenie    Można również wprowadzić kwotę i dołączyć do zestawienia kosztów wszelką dokumentację uzupełniającą, taką jak faktury lub notatki lekarza.</span><span class="sxs-lookup"><span data-stu-id="285b5-151">Example:  Therapy    You can also enter in an amount, and attach any supporting documentation such as invoices or doctor's notes to the cost.</span></span>  
24. <span data-ttu-id="285b5-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="285b5-152">Click Add.</span></span>
25. <span data-ttu-id="285b5-153">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="285b5-153">In the Date field, enter a date.</span></span>
26. <span data-ttu-id="285b5-154">W polu Typ kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-154">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-155">Przykład: Lekarz</span><span class="sxs-lookup"><span data-stu-id="285b5-155">Example: Doctor</span></span>  
27. <span data-ttu-id="285b5-156">Rozwiń sekcję Leczenie urazów lub chorób.</span><span class="sxs-lookup"><span data-stu-id="285b5-156">Expand the Injury or illness treatments section.</span></span>
28. <span data-ttu-id="285b5-157">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="285b5-157">Click Add.</span></span>
29. <span data-ttu-id="285b5-158">W polu Data leczenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="285b5-158">In the Treatment date field, enter a date and time.</span></span>
30. <span data-ttu-id="285b5-159">W polu Typ leczenia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-159">In the Treatment type field, enter or select a value.</span></span>
    * <span data-ttu-id="285b5-160">Przykład: Szyna unieruchamiająca</span><span class="sxs-lookup"><span data-stu-id="285b5-160">Example:  Splint</span></span>  
31. <span data-ttu-id="285b5-161">Opcjonalnie w sekcji Pobyt w szpitalnym oddziale pomocy doraźnej w nagłych wypadkach ustaw wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="285b5-161">Optionally, set the emergency room hospital visit section to Yes.</span></span>
32. <span data-ttu-id="285b5-162">W polu Komentarze dotyczące leczenia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-162">In the Treatment comments field, type a value.</span></span>
    * <span data-ttu-id="285b5-163">Przykład: Szyna unieruchamiająca przez 2 tygodnie</span><span class="sxs-lookup"><span data-stu-id="285b5-163">Example:  Splint for 2 weeks</span></span>  
33. <span data-ttu-id="285b5-164">W polu Nazwisko lekarza wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-164">In the Physician name field, type a value.</span></span>
    * <span data-ttu-id="285b5-165">Przykład:  Dr Kowalski</span><span class="sxs-lookup"><span data-stu-id="285b5-165">Example:  Dr. Anderson</span></span>  
34. <span data-ttu-id="285b5-166">W polu Zakład i lokalizacja leczenia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-166">In the Treatment facility and location field, type a value.</span></span>
    * <span data-ttu-id="285b5-167">Przykład: Izba przyjęć szpitala wojewódzkiego</span><span class="sxs-lookup"><span data-stu-id="285b5-167">Example:  Elm St. Emergency</span></span>  
35. <span data-ttu-id="285b5-168">W polu Szczegóły leczenia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="285b5-168">In the Treatment details field, type a value.</span></span>
    * <span data-ttu-id="285b5-169">Przykład: Badanie rentgenowskie potwierdza złamanie, nosić szynę unieruchamiającą</span><span class="sxs-lookup"><span data-stu-id="285b5-169">Example:  Xray confirms fracture, wear splint</span></span>  
36. <span data-ttu-id="285b5-170">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="285b5-170">Click Save.</span></span>
    * <span data-ttu-id="285b5-171">Stan sprawy można zaktualizować w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="285b5-171">The case status can be updated at any time.</span></span>  <span data-ttu-id="285b5-172">Ustaw stan sprawy na W toku, jeśli rozpatrywanie zgłoszenia urazu lub choroby nadal trwa.</span><span class="sxs-lookup"><span data-stu-id="285b5-172">Set the case to in process, if the processing of the injury or illness is in process.</span></span>  <span data-ttu-id="285b5-173">Po zamknięciu zdarzenia można tylko dodawać lub usuwać koszty, zabiegi lub dokumenty związane ze zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="285b5-173">Once you close the incident you can only add or remove costs, treatments or filings related to the incident.</span></span>  <span data-ttu-id="285b5-174">Aby zmodyfikować inne informacje, należy ponownie otworzyć sprawę.</span><span class="sxs-lookup"><span data-stu-id="285b5-174">To modify other information, reopen the case.</span></span>  

