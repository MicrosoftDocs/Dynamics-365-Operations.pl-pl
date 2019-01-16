---
title: "Koncepcje urlopów i nieobecności"
description: "W tym temacie opisano pojęcia dotyczące urlopów i nieobecności oraz sposób określania sald czasu wolnego."
author: jcart
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: a388e0efe6c19a3aabe04e7fff039ce11ae023c4
ms.openlocfilehash: 563593d6c93b0488c681f5b43004f5c0d22cc004
ms.contentlocale: pl-pl
ms.lasthandoff: 01/07/2019

---

# <a name="leave-and-absence-concepts"></a><span data-ttu-id="febb5-103">Koncepcje urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="febb5-103">Leave and absence concepts</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="febb5-104">Pojęcia i terminy, które zostały opisane w tym temacie, mogą pomóc określić, jak pracownikowi jest przyznawany czas wolny i jak obliczane są salda czasu wolnego pracownika.</span><span class="sxs-lookup"><span data-stu-id="febb5-104">The concepts and terms that are described in this topic can help you determine how an employee is awarded time off, and how that employee's time balances are calculated.</span></span> <span data-ttu-id="febb5-105">Aby uzyskać więcej informacji dotyczących zarządzania urlopami, zobacz [Zarządzanie urlopami i nieobecnościami](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).</span><span class="sxs-lookup"><span data-stu-id="febb5-105">For more information about leave and absence management, see [Leave and absence management](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).</span></span>

## <a name="leave-plan-details"></a><span data-ttu-id="febb5-106">Szczegóły planu urlopowego</span><span class="sxs-lookup"><span data-stu-id="febb5-106">Leave plan details</span></span>

### <a name="start-date"></a><span data-ttu-id="febb5-107">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="febb5-107">Start date</span></span>

<span data-ttu-id="febb5-108">Data rozpoczęcia jest datą rzeczywistego rozpoczęcia przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="febb5-108">The start date is the date when accrual processing begins.</span></span> <span data-ttu-id="febb5-109">Data rozpoczęcia służy również jako data rocznicy używana do obliczania kwot przenoszonych na następny okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-109">The start date also serves as the anniversary date that is used to calculate carry-forward amounts.</span></span>

## <a name="accruals"></a><span data-ttu-id="febb5-110">Naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-110">Accruals</span></span>

<span data-ttu-id="febb5-111">Naliczenia określają, kiedy i jak często pracownikowi jest przyznawany czas wolny.</span><span class="sxs-lookup"><span data-stu-id="febb5-111">Accruals determine when and how often an employee is awarded time off.</span></span> <span data-ttu-id="febb5-112">Zasady dotyczące przyznawania naliczeń oraz zasady dotyczące podziału proporcjonalnego są zdefiniowane w **Naliczenia** sekcji podczas konfigurowania planu urlopów i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="febb5-112">Policies about when accruals should be awarded and policies about proration are defined in the **Accruals** section when setting up the leave and absence plan.</span></span>

### <a name="accrual-frequency"></a><span data-ttu-id="febb5-113">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-113">Accrual frequency</span></span>

<span data-ttu-id="febb5-114">Częstotliwość naliczania określa, jak często naliczany lub przyznawany jest urlop.</span><span class="sxs-lookup"><span data-stu-id="febb5-114">The accrual frequency defines how often leave is accrued or awarded.</span></span> <span data-ttu-id="febb5-115">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="febb5-115">The following options are available:</span></span>

- <span data-ttu-id="febb5-116">Codziennie</span><span class="sxs-lookup"><span data-stu-id="febb5-116">Daily</span></span>
- <span data-ttu-id="febb5-117">Cykl tygodniowy</span><span class="sxs-lookup"><span data-stu-id="febb5-117">Weekly</span></span>
- <span data-ttu-id="febb5-118">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="febb5-118">Biweekly</span></span>
- <span data-ttu-id="febb5-119">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="febb5-119">Semimonthly</span></span>
- <span data-ttu-id="febb5-120">Miesięcznie</span><span class="sxs-lookup"><span data-stu-id="febb5-120">Monthly</span></span>
- <span data-ttu-id="febb5-121">Kwartalna</span><span class="sxs-lookup"><span data-stu-id="febb5-121">Quarterly</span></span>
- <span data-ttu-id="febb5-122">Co pół roku</span><span class="sxs-lookup"><span data-stu-id="febb5-122">Semiannually</span></span>
- <span data-ttu-id="febb5-123">Rocznie</span><span class="sxs-lookup"><span data-stu-id="febb5-123">Annually</span></span>
- <span data-ttu-id="febb5-124">Brak</span><span class="sxs-lookup"><span data-stu-id="febb5-124">None</span></span>

### <a name="accrual-period-basis"></a><span data-ttu-id="febb5-125">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-125">Accrual period basis</span></span>

<span data-ttu-id="febb5-126">Podstawa okresu naliczania określa datę używaną do obliczania okresów naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-126">The accrual period basis determines the date that is used to calculate accrual periods.</span></span> <span data-ttu-id="febb5-127">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="febb5-127">The following options are available:</span></span>

- <span data-ttu-id="febb5-128">**Data początkowa planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-128">**Plan start date**</span></span>
- <span data-ttu-id="febb5-129">**Data specyficzna dla pracownika** — kiedy ta opcja jest zaznaczona, wartość określa źródło daty początkowej, która jest używana do obliczania okresów naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-129">**Employee specific date** – When this option is selected, the value determines the source of the initial date value that is used to calculate accrual periods.</span></span> <span data-ttu-id="febb5-130">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="febb5-130">The following options are available:</span></span>

    - <span data-ttu-id="febb5-131">Niestandardowy</span><span class="sxs-lookup"><span data-stu-id="febb5-131">Custom</span></span>
    - <span data-ttu-id="febb5-132">Rocznica</span><span class="sxs-lookup"><span data-stu-id="febb5-132">Anniversary date</span></span>
    - <span data-ttu-id="febb5-133">Pierwotna data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="febb5-133">Original hire date</span></span>
    - <span data-ttu-id="febb5-134">Data stażu pracy</span><span class="sxs-lookup"><span data-stu-id="febb5-134">Seniority date</span></span>
    - <span data-ttu-id="febb5-135">Skorygowana data rozpoczęcia pracownika</span><span class="sxs-lookup"><span data-stu-id="febb5-135">Worker's adjusted start date</span></span>
    - <span data-ttu-id="febb5-136">Data rozpoczęcia pracownika</span><span class="sxs-lookup"><span data-stu-id="febb5-136">Worker's start date</span></span>

### <a name="accrual-award-date"></a><span data-ttu-id="febb5-137">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-137">Accrual award date</span></span>

<span data-ttu-id="febb5-138">Rzeczywista data przyznania naliczenia określa, kiedy pracownikowi jest przyznawany czas wolny.</span><span class="sxs-lookup"><span data-stu-id="febb5-138">The accrual award date determines when an employee is awarded time off.</span></span> <span data-ttu-id="febb5-139">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="febb5-139">The following options are available:</span></span>

- <span data-ttu-id="febb5-140">**Data zakończenia okresu naliczania** — pracownikowi zostanie przyznany czas wolny ostatniego dnia okresu przyznawania.</span><span class="sxs-lookup"><span data-stu-id="febb5-140">**Accrual period end date** – The employee will be awarded time off on the last day of the award period.</span></span>

    <span data-ttu-id="febb5-141">Aby naliczyć poprawną kwotę, proces naliczania musi obejmować cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-141">To accrue the correct amount, the accrual process must include the whole period.</span></span> <span data-ttu-id="febb5-142">Na przykład okres naliczania jest od 1 stycznia 2018 do 31 stycznia 2018.</span><span class="sxs-lookup"><span data-stu-id="febb5-142">For example, the accrual period is January 1, 2018, through January 31, 2018.</span></span> <span data-ttu-id="febb5-143">W takim przypadku, aby styczeń został uwzględniony, naliczenie musi trwać do 1 lutego 2018.</span><span class="sxs-lookup"><span data-stu-id="febb5-143">In this case, for January to be included, the accrual must be run for February 1, 2018.</span></span>

- <span data-ttu-id="febb5-144">**Data rozpoczęcia okresu naliczania** — pracownikowi zostanie przyznany czas wolny pierwszego dnia okresu przyznawania.</span><span class="sxs-lookup"><span data-stu-id="febb5-144">**Accrual period start date** – The employee will be awarded time off on the first day of the award period.</span></span>

### <a name="accrual-policy-on-enrollment"></a><span data-ttu-id="febb5-145">Zasady dotyczące naliczania przy rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-145">Accrual policy on enrollment</span></span>

<span data-ttu-id="febb5-146">Zasada naliczania przy rejestracji definiują sposób obliczania naliczeń, gdy pracownik zostanie zarejestrowany w trakcie okresu naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-146">The accrual policy on enrollment defines how accrual is calculated when an employee is enrolled in the middle of an accrual period.</span></span> <span data-ttu-id="febb5-147">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="febb5-147">The following options are available:</span></span>

- <span data-ttu-id="febb5-148">**Proporcjonalna** — zakres dat między datą początkową i datą rejestracji jest używana do określania różnicy w dniach.</span><span class="sxs-lookup"><span data-stu-id="febb5-148">**Prorated** – The date range between the enrollment date and the start date is used to determine the difference in days.</span></span> <span data-ttu-id="febb5-149">Ta różnica jest stosowana podczas przetwarzania naliczeń.</span><span class="sxs-lookup"><span data-stu-id="febb5-149">That difference is applied when accruals are processed.</span></span>
- <span data-ttu-id="febb5-150">**Pełne naliczenia** — pełna kwota naliczeń w oparciu o warstwę jest przyznawana podczas wstępnego przetwarzania naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-150">**Full accrual** – The full accrual amount, based on the tier, is awarded during the first accrual processing.</span></span>
- <span data-ttu-id="febb5-151">**Bez naliczenia** — żadne naliczenie nie jest przyznawane aż do rozpoczęcia następnego okresu naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-151">**No accrual** – No accrual is awarded until the next accrual period.</span></span>

### <a name="accrual-policy-on-unenrollment"></a><span data-ttu-id="febb5-152">Zasady dotyczące naliczania przy wyrejestrowaniu</span><span class="sxs-lookup"><span data-stu-id="febb5-152">Accrual policy on unenrollment</span></span>

<span data-ttu-id="febb5-153">Zasada naliczania przy wyrejestrowaniu definiują sposób obliczania naliczeń, gdy pracownik zostanie wyrejestrowany w trakcie okresu naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-153">The accrual policy on unenrollment defines how accrual is calculated when an employee is unenrolled in the middle of an accrual period.</span></span> <span data-ttu-id="febb5-154">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="febb5-154">The following options are available:</span></span>

- <span data-ttu-id="febb5-155">**Proporcjonalna** — zakres dat między datą początkową i datą rejestracji jest używana do określania różnicy w dniach.</span><span class="sxs-lookup"><span data-stu-id="febb5-155">**Prorated** – The date range between the enrollment date and the start date is used to determine the difference in days.</span></span> <span data-ttu-id="febb5-156">Ta różnica jest stosowana podczas przetwarzania naliczeń.</span><span class="sxs-lookup"><span data-stu-id="febb5-156">That difference is applied when accruals are processed.</span></span>
- <span data-ttu-id="febb5-157">**Pełne naliczenia** — pełna kwota naliczeń w oparciu o warstwę jest przyznawana podczas wstępnego przetwarzania naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-157">**Full accrual** – The full accrual amount, based on the tier, is awarded during the first accrual processing.</span></span>
- <span data-ttu-id="febb5-158">**Bez naliczenia** — żadne naliczenie nie jest przyznawane aż do rozpoczęcia następnego okresu naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-158">**No accrual** – No accrual is awarded until the next accrual period.</span></span>

## <a name="accrual-schedule"></a><span data-ttu-id="febb5-159">Harmonogram naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-159">Accrual schedule</span></span>

<span data-ttu-id="febb5-160">Harmonogram naliczania określa sposób naliczania czasu wolnego przez pracownika oraz jakie kwoty zostaną temu pracownikowi naliczone i przeniesienie na następny okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-160">The accrual schedule determines how an employee will accrue time off, and what amounts that employee will accrue and carry forward.</span></span> <span data-ttu-id="febb5-161">Można tworzyć warstwy, dzięki którym czas wolny jest przyznawany na podstawie różnych poziomów.</span><span class="sxs-lookup"><span data-stu-id="febb5-161">Tiers can be created so that time off is awarded based on different levels.</span></span>

### <a name="months-of-service"></a><span data-ttu-id="febb5-162">Miesiące zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="febb5-162">Months of service</span></span>

<span data-ttu-id="febb5-163">Wartość **Miesiące usługi** definiują minimalną liczbę miesięcy, które pracownicy muszą przepracować, aby mieć prawo do naliczeń.</span><span class="sxs-lookup"><span data-stu-id="febb5-163">The **Months of service** value defines the minimum number of months that employees must work to be entitled to accruals.</span></span> <span data-ttu-id="febb5-164">Jeśli nie ustalono minimum niezbędnego dla pracowników, ustaw wartość na **0**.</span><span class="sxs-lookup"><span data-stu-id="febb5-164">If no minimum is required for employees, set the value to **0**.</span></span>

### <a name="hours-worked"></a><span data-ttu-id="febb5-165">Przepracowane godziny</span><span class="sxs-lookup"><span data-stu-id="febb5-165">Hours worked</span></span>

<span data-ttu-id="febb5-166">Wartość **Przepracowane godziny** definiują minimalną liczbę godzin, które pracownicy muszą przepracować w okresie naliczania, aby mieć prawo do naliczeń.</span><span class="sxs-lookup"><span data-stu-id="febb5-166">The **Hours worked** value defines the minimum number of hours that employees must work per accrual period to be entitled to accruals.</span></span> <span data-ttu-id="febb5-167">Jeśli nie ustalono minimum niezbędnego dla pracowników, ustaw wartość na **0**.</span><span class="sxs-lookup"><span data-stu-id="febb5-167">If no minimum is required for employees, set the value to **0**.</span></span>

### <a name="accrual-amount"></a><span data-ttu-id="febb5-168">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-168">Accrual amount</span></span>

<span data-ttu-id="febb5-169">Kwota naliczeń jest liczb ą godzin lub dni, które zostaną naliczone pracownikom według okresu.</span><span class="sxs-lookup"><span data-stu-id="febb5-169">The accrual amount is the number of hours or days that employees will accrue per period.</span></span> <span data-ttu-id="febb5-170">Okres zależy od częstotliwości naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-170">The period is based on the accrual frequency.</span></span>

### <a name="minimum-balance"></a><span data-ttu-id="febb5-171">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-171">Minimum balance</span></span>

<span data-ttu-id="febb5-172">Wartość ujemna może zostać użyta w przypadku minimalnego salda, jeśli pracownicy mogą zażądać więcej urlopu niż mają dostępnego.</span><span class="sxs-lookup"><span data-stu-id="febb5-172">A negative value can be used for the minimum balance if employees can request more leave than they have available.</span></span>

### <a name="maximum-carry-forward"></a><span data-ttu-id="febb5-173">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-173">Maximum carry-forward</span></span>

<span data-ttu-id="febb5-174">Proces naliczania dostosuje salda urlopów przekraczające maksymalne saldo przeniesienia na następny okres w rocznicą daty rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="febb5-174">The accrual process will adjust leave balances that exceed the maximum carry-forward balance on the anniversary of the start date.</span></span>

### <a name="grant-amount"></a><span data-ttu-id="febb5-175">Kwota dotacji</span><span class="sxs-lookup"><span data-stu-id="febb5-175">Grant amount</span></span>

<span data-ttu-id="febb5-176">Kwota dotacji jest początkową liczbą godzin lub dni, które pracownicy otrzymują, gdy po raz pierwszy zarejestrują się w planie urlopów.</span><span class="sxs-lookup"><span data-stu-id="febb5-176">The grant amount is the initial number of hours or days that employees are granted when they first enroll in the leave plan.</span></span> <span data-ttu-id="febb5-177">Kwota nie jest naliczana dla każdego okresu naliczania.</span><span class="sxs-lookup"><span data-stu-id="febb5-177">The amount doesn't accrue for each accrual period.</span></span>

## <a name="enrollments-and-balances"></a><span data-ttu-id="febb5-178">Rejestracje i salda</span><span class="sxs-lookup"><span data-stu-id="febb5-178">Enrollments and balances</span></span>

### <a name="enrollment-date"></a><span data-ttu-id="febb5-179">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-179">Enrollment date</span></span>

<span data-ttu-id="febb5-180">Data rejestracji określa, kiedy pracownik może rozpocząć naliczanie czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="febb5-180">The enrollment date determines when an employee can start to accrue time off.</span></span> <span data-ttu-id="febb5-181">Na przykład, jeśli pracownik zostanie zarejestrowany w systemie urlopowym 15 czerwca 2018, nie może naliczać czasu przed 15 czerwca 2018.</span><span class="sxs-lookup"><span data-stu-id="febb5-181">For example, if an employee is enrolled in a vacation plan on June 15, 2018, she can't accrue any time off before June 15, 2018.</span></span>

### <a name="current-balance"></a><span data-ttu-id="febb5-182">Bieżące saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-182">Current balance</span></span>

<span data-ttu-id="febb5-183">Bieżące saldo jest czasem urlopu, który jest dostępny dla żądań czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="febb5-183">The current balance is the amount of leave that is available for time off requests.</span></span> <span data-ttu-id="febb5-184">Ta wartość obejmuje naliczenia, zatwierdzone wnioski oraz dostosowania względem bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="febb5-184">This amount includes accruals, approved requests, and adjustments through the current date.</span></span>

### <a name="current-balance-examples"></a><span data-ttu-id="febb5-185">Przykłady salda bieżącego</span><span class="sxs-lookup"><span data-stu-id="febb5-185">Current balance examples</span></span>

#### <a name="annual-plan"></a><span data-ttu-id="febb5-186">Plan roczny</span><span class="sxs-lookup"><span data-stu-id="febb5-186">Annual plan</span></span>

<span data-ttu-id="febb5-187">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-187">**Plan setup**</span></span>

| <span data-ttu-id="febb5-188">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-188">Plan start date</span></span> | <span data-ttu-id="febb5-189">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-189">Enrollment date</span></span> | <span data-ttu-id="febb5-190">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-190">Accrual frequency</span></span> | <span data-ttu-id="febb5-191">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-191">Accrual period basis</span></span> | <span data-ttu-id="febb5-192">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-192">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="febb5-193">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-193">1/1/2018</span></span>        | <span data-ttu-id="febb5-194">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-194">1/1/2018</span></span>        | <span data-ttu-id="febb5-195">Roczny</span><span class="sxs-lookup"><span data-stu-id="febb5-195">Annual</span></span>            | <span data-ttu-id="febb5-196">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-196">Plan start date</span></span>      | <span data-ttu-id="febb5-197">Koniec okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-197">End of accrual period</span></span> |

<span data-ttu-id="febb5-198">Naliczenia są przetwarzane 1 stycznia 2019 (1/1/2019), dlatego uwzględniany jest cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-198">Accruals are processed on January 1, 2019 (1/1/2019), so that that whole period is included.</span></span>

<span data-ttu-id="febb5-199">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-199">**Results**</span></span>

| <span data-ttu-id="febb5-200">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-200">Accrual amount</span></span> | <span data-ttu-id="febb5-201">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-201">Minimum balance</span></span> | <span data-ttu-id="febb5-202">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-202">Maximum carry-forward</span></span> | <span data-ttu-id="febb5-203">Kwota żądania</span><span class="sxs-lookup"><span data-stu-id="febb5-203">Request amount</span></span> | <span data-ttu-id="febb5-204">Bieżące saldo (z dnia 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="febb5-204">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="febb5-205">200</span><span class="sxs-lookup"><span data-stu-id="febb5-205">200</span></span>            | <span data-ttu-id="febb5-206">0</span><span class="sxs-lookup"><span data-stu-id="febb5-206">0</span></span>               | <span data-ttu-id="febb5-207">120</span><span class="sxs-lookup"><span data-stu-id="febb5-207">120</span></span>                   | <span data-ttu-id="febb5-208">40</span><span class="sxs-lookup"><span data-stu-id="febb5-208">40</span></span>             | <span data-ttu-id="febb5-209">160</span><span class="sxs-lookup"><span data-stu-id="febb5-209">160</span></span>                              |

<span data-ttu-id="febb5-210">Bieżące saldo (160) = naliczona kwota (200) — kwota żądania (40)</span><span class="sxs-lookup"><span data-stu-id="febb5-210">Current balance (160) = Accrual amount (200) – Request amount (40)</span></span>

#### <a name="semimonthly-plan"></a><span data-ttu-id="febb5-211">Plan półmiesięczny</span><span class="sxs-lookup"><span data-stu-id="febb5-211">Semimonthly plan</span></span>

<span data-ttu-id="febb5-212">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-212">**Plan setup**</span></span>

| <span data-ttu-id="febb5-213">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-213">Plan start date</span></span> | <span data-ttu-id="febb5-214">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-214">Enrollment date</span></span> | <span data-ttu-id="febb5-215">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-215">Accrual frequency</span></span> | <span data-ttu-id="febb5-216">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-216">Accrual period basis</span></span> | <span data-ttu-id="febb5-217">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-217">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="febb5-218">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-218">1/1/2018</span></span>        | <span data-ttu-id="febb5-219">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-219">2/1/2018</span></span>        | <span data-ttu-id="febb5-220">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="febb5-220">Semimonthly</span></span>       | <span data-ttu-id="febb5-221">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-221">Plan start date</span></span>      | <span data-ttu-id="febb5-222">Koniec okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-222">End of accrual period</span></span> |

<span data-ttu-id="febb5-223">Naliczenia są przetwarzane 1 maja 2018 (5/1/2018), dlatego uwzględniany jest cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-223">Accruals are processed on May 1, 2018 (5/1/2018), so that that whole period is included.</span></span>

<span data-ttu-id="febb5-224">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-224">**Results**</span></span>

| <span data-ttu-id="febb5-225">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-225">Accrual amount</span></span> | <span data-ttu-id="febb5-226">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-226">Minimum balance</span></span> | <span data-ttu-id="febb5-227">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-227">Maximum carry-forward</span></span> | <span data-ttu-id="febb5-228">Kwota żądania</span><span class="sxs-lookup"><span data-stu-id="febb5-228">Request amount</span></span> | <span data-ttu-id="febb5-229">Bieżące saldo (z dnia 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="febb5-229">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="febb5-230">5</span><span class="sxs-lookup"><span data-stu-id="febb5-230">5</span></span>              | <span data-ttu-id="febb5-231">0</span><span class="sxs-lookup"><span data-stu-id="febb5-231">0</span></span>               | <span data-ttu-id="febb5-232">120</span><span class="sxs-lookup"><span data-stu-id="febb5-232">120</span></span>                   | <span data-ttu-id="febb5-233">8</span><span class="sxs-lookup"><span data-stu-id="febb5-233">8</span></span>              | <span data-ttu-id="febb5-234">22</span><span class="sxs-lookup"><span data-stu-id="febb5-234">22</span></span>                               |

<span data-ttu-id="febb5-235">Bieżące saldo (22) = naliczona kwota (5 × 6) — kwota żądania (8)</span><span class="sxs-lookup"><span data-stu-id="febb5-235">Current balance (22) = Accrual amount (5 × 6) – Request amount (8)</span></span>

#### <a name="monthly-plan"></a><span data-ttu-id="febb5-236">Plan miesięczny</span><span class="sxs-lookup"><span data-stu-id="febb5-236">Monthly plan</span></span>

<span data-ttu-id="febb5-237">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-237">**Plan setup**</span></span>

| <span data-ttu-id="febb5-238">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-238">Plan start date</span></span> | <span data-ttu-id="febb5-239">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-239">Enrollment date</span></span> | <span data-ttu-id="febb5-240">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-240">Accrual frequency</span></span> | <span data-ttu-id="febb5-241">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-241">Accrual period basis</span></span> | <span data-ttu-id="febb5-242">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-242">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="febb5-243">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-243">1/1/2018</span></span>        | <span data-ttu-id="febb5-244">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-244">2/1/2018</span></span>        | <span data-ttu-id="febb5-245">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="febb5-245">Semimonthly</span></span>       | <span data-ttu-id="febb5-246">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-246">Plan start date</span></span>      | <span data-ttu-id="febb5-247">Koniec okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-247">End of accrual period</span></span> |

<span data-ttu-id="febb5-248">Naliczenia są przetwarzane 1 maja 2018 (5/1/2018), dlatego uwzględniany jest cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-248">Accruals are processed on May 1, 2018 (5/1/2018), so that that whole period is included.</span></span>

<span data-ttu-id="febb5-249">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-249">**Results**</span></span>

| <span data-ttu-id="febb5-250">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-250">Accrual amount</span></span> | <span data-ttu-id="febb5-251">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-251">Minimum balance</span></span> | <span data-ttu-id="febb5-252">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-252">Maximum carry-forward</span></span> | <span data-ttu-id="febb5-253">Kwota żądania</span><span class="sxs-lookup"><span data-stu-id="febb5-253">Request amount</span></span> | <span data-ttu-id="febb5-254">Bieżące saldo (z dnia 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="febb5-254">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="febb5-255">5</span><span class="sxs-lookup"><span data-stu-id="febb5-255">5</span></span>              | <span data-ttu-id="febb5-256">0</span><span class="sxs-lookup"><span data-stu-id="febb5-256">0</span></span>               | <span data-ttu-id="febb5-257">120</span><span class="sxs-lookup"><span data-stu-id="febb5-257">120</span></span>                   | <span data-ttu-id="febb5-258">8</span><span class="sxs-lookup"><span data-stu-id="febb5-258">8</span></span>              | <span data-ttu-id="febb5-259">7</span><span class="sxs-lookup"><span data-stu-id="febb5-259">7</span></span>                                |

<span data-ttu-id="febb5-260">Bieżące saldo (7) = naliczona kwota (5 × 3) — kwota żądania (8)</span><span class="sxs-lookup"><span data-stu-id="febb5-260">Current balance (7) = Accrual amount (5 × 3) – Request amount (8)</span></span>

### <a name="forecasted-balance"></a><span data-ttu-id="febb5-261">Prognozowane saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-261">Forecasted balance</span></span>

<span data-ttu-id="febb5-262">*Prognozowane saldo* jest kwotą urlopu dostępną w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="febb5-262">The *forecasted balance* is the amount of leave that is available on a future date.</span></span> <span data-ttu-id="febb5-263">Korekty naliczeń i przeniesień na następny okres są prognozowane do tej daty.</span><span class="sxs-lookup"><span data-stu-id="febb5-263">Accruals and carry-forward adjustments are forecasted up to that date.</span></span>

<span data-ttu-id="febb5-264">Stosowany jest poniższy wzór:</span><span class="sxs-lookup"><span data-stu-id="febb5-264">The following formula is used:</span></span>

<span data-ttu-id="febb5-265">Saldo prognozowane na poniedziałek = Saldo bieżące – Żądania + Naliczenia – Korekta o przeniesienia na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-265">Monday forecasted balance = Current balance – Requests + Accruals – Carry-forward adjustment</span></span>

### <a name="forecasted-balance-examples"></a><span data-ttu-id="febb5-266">Przykład prognozowanego salda</span><span class="sxs-lookup"><span data-stu-id="febb5-266">Forecasted balance examples</span></span>

#### <a name="annual-plan"></a><span data-ttu-id="febb5-267">Plan roczny</span><span class="sxs-lookup"><span data-stu-id="febb5-267">Annual plan</span></span>

<span data-ttu-id="febb5-268">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-268">**Plan setup**</span></span>

| <span data-ttu-id="febb5-269">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-269">Plan start date</span></span> | <span data-ttu-id="febb5-270">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-270">Enrollment date</span></span> | <span data-ttu-id="febb5-271">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-271">Accrual frequency</span></span> | <span data-ttu-id="febb5-272">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-272">Accrual period basis</span></span> | <span data-ttu-id="febb5-273">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-273">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="febb5-274">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-274">1/1/2018</span></span>        | <span data-ttu-id="febb5-275">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-275">1/1/2018</span></span>        | <span data-ttu-id="febb5-276">Roczny</span><span class="sxs-lookup"><span data-stu-id="febb5-276">Annual</span></span>            | <span data-ttu-id="febb5-277">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-277">Plan start date</span></span>      | <span data-ttu-id="febb5-278">Koniec okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-278">End of accrual period</span></span> |

<span data-ttu-id="febb5-279">Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), dlatego uwzględniany jest cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-279">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="febb5-280">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-280">**Results**</span></span>

| <span data-ttu-id="febb5-281">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-281">Accrual amount</span></span> | <span data-ttu-id="febb5-282">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-282">Minimum balance</span></span> | <span data-ttu-id="febb5-283">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-283">Maximum carry-forward</span></span> | <span data-ttu-id="febb5-284">Bieżące saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-284">Current balance</span></span> | <span data-ttu-id="febb5-285">Prognozowane saldo (z dnia 2/15/2019)</span><span class="sxs-lookup"><span data-stu-id="febb5-285">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="febb5-286">20</span><span class="sxs-lookup"><span data-stu-id="febb5-286">20</span></span>             | <span data-ttu-id="febb5-287">0</span><span class="sxs-lookup"><span data-stu-id="febb5-287">0</span></span>               | <span data-ttu-id="febb5-288">20</span><span class="sxs-lookup"><span data-stu-id="febb5-288">20</span></span>                    | <span data-ttu-id="febb5-289">40</span><span class="sxs-lookup"><span data-stu-id="febb5-289">40</span></span>              | <span data-ttu-id="febb5-290">40</span><span class="sxs-lookup"><span data-stu-id="febb5-290">40</span></span>                                   |

<span data-ttu-id="febb5-291">Prognozowane saldo (40) = Kwota naliczeń (20) + Saldo bieżące (40) – Korekta o przeniesienia na następny okres (20)</span><span class="sxs-lookup"><span data-stu-id="febb5-291">Forecasted balance (40) = Accrual amount (20) + Current balance (40) – Carry-forward adjustment (20)</span></span>

#### <a name="semimonthly-plan"></a><span data-ttu-id="febb5-292">Plan półmiesięczny</span><span class="sxs-lookup"><span data-stu-id="febb5-292">Semimonthly plan</span></span>

<span data-ttu-id="febb5-293">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-293">**Plan setup**</span></span>

| <span data-ttu-id="febb5-294">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-294">Plan start date</span></span> | <span data-ttu-id="febb5-295">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-295">Enrollment date</span></span> | <span data-ttu-id="febb5-296">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-296">Accrual frequency</span></span> | <span data-ttu-id="febb5-297">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-297">Accrual period basis</span></span> | <span data-ttu-id="febb5-298">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-298">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="febb5-299">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-299">1/1/2018</span></span>        | <span data-ttu-id="febb5-300">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-300">2/1/2018</span></span>        | <span data-ttu-id="febb5-301">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="febb5-301">Semimonthly</span></span>       | <span data-ttu-id="febb5-302">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-302">Plan start date</span></span>      | <span data-ttu-id="febb5-303">Koniec okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-303">End of accrual period</span></span> |

<span data-ttu-id="febb5-304">Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), dlatego uwzględniany jest cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-304">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="febb5-305">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-305">**Results**</span></span>

| <span data-ttu-id="febb5-306">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-306">Accrual amount</span></span> | <span data-ttu-id="febb5-307">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-307">Minimum balance</span></span> | <span data-ttu-id="febb5-308">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-308">Maximum carry-forward</span></span> | <span data-ttu-id="febb5-309">Bieżące saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-309">Current balance</span></span> | <span data-ttu-id="febb5-310">Prognozowane saldo (z dnia 2/15/2019)</span><span class="sxs-lookup"><span data-stu-id="febb5-310">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="febb5-311">5</span><span class="sxs-lookup"><span data-stu-id="febb5-311">5</span></span>              | <span data-ttu-id="febb5-312">0</span><span class="sxs-lookup"><span data-stu-id="febb5-312">0</span></span>               | <span data-ttu-id="febb5-313">20</span><span class="sxs-lookup"><span data-stu-id="febb5-313">20</span></span>                    | <span data-ttu-id="febb5-314">40</span><span class="sxs-lookup"><span data-stu-id="febb5-314">40</span></span>              | <span data-ttu-id="febb5-315">35</span><span class="sxs-lookup"><span data-stu-id="febb5-315">35</span></span>                                   |

<span data-ttu-id="febb5-316">Prognozowane saldo (35) = Kwota naliczeń (5 × 3) + Saldo bieżące (40) – Korekta o przeniesienia na następny okres (20)</span><span class="sxs-lookup"><span data-stu-id="febb5-316">Forecasted balance (35) = Accrual amount (5 × 3) + Current balance (40) – Carry-forward adjustment (20)</span></span>

#### <a name="monthly-plan"></a><span data-ttu-id="febb5-317">Plan miesięczny</span><span class="sxs-lookup"><span data-stu-id="febb5-317">Monthly plan</span></span>

<span data-ttu-id="febb5-318">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-318">**Plan setup**</span></span>

| <span data-ttu-id="febb5-319">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-319">Plan start date</span></span> | <span data-ttu-id="febb5-320">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-320">Enrollment date</span></span> | <span data-ttu-id="febb5-321">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-321">Accrual frequency</span></span> | <span data-ttu-id="febb5-322">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-322">Accrual period basis</span></span> | <span data-ttu-id="febb5-323">Data przyznania naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-323">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="febb5-324">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-324">1/1/2018</span></span>        | <span data-ttu-id="febb5-325">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-325">2/1/2018</span></span>        | <span data-ttu-id="febb5-326">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="febb5-326">Semimonthly</span></span>       | <span data-ttu-id="febb5-327">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-327">Plan start date</span></span>      | <span data-ttu-id="febb5-328">Koniec okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-328">End of accrual period</span></span> |

<span data-ttu-id="febb5-329">Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), dlatego uwzględniany jest cały okres.</span><span class="sxs-lookup"><span data-stu-id="febb5-329">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="febb5-330">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-330">**Results**</span></span>

| <span data-ttu-id="febb5-331">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-331">Accrual amount</span></span> | <span data-ttu-id="febb5-332">Minimalne saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-332">Minimum balance</span></span> | <span data-ttu-id="febb5-333">Maksymalne przeniesienie na następny okres</span><span class="sxs-lookup"><span data-stu-id="febb5-333">Maximum carry-forward</span></span> | <span data-ttu-id="febb5-334">Bieżące saldo</span><span class="sxs-lookup"><span data-stu-id="febb5-334">Current balance</span></span> | <span data-ttu-id="febb5-335">Prognozowane saldo (z dnia 2/15/2019)</span><span class="sxs-lookup"><span data-stu-id="febb5-335">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="febb5-336">10</span><span class="sxs-lookup"><span data-stu-id="febb5-336">10</span></span>             | <span data-ttu-id="febb5-337">0</span><span class="sxs-lookup"><span data-stu-id="febb5-337">0</span></span>               | <span data-ttu-id="febb5-338">20</span><span class="sxs-lookup"><span data-stu-id="febb5-338">20</span></span>                    | <span data-ttu-id="febb5-339">40</span><span class="sxs-lookup"><span data-stu-id="febb5-339">40</span></span>              | <span data-ttu-id="febb5-340">30</span><span class="sxs-lookup"><span data-stu-id="febb5-340">30</span></span>                                   |

<span data-ttu-id="febb5-341">Prognozowane saldo (30) = Kwota naliczeń (10 × 1) + Saldo bieżące (40) – Korekta o przeniesienia na następny okres (20)</span><span class="sxs-lookup"><span data-stu-id="febb5-341">Forecasted balance (30) = Accrual amount (10 × 1) + Current balance (40) – Carry-forward adjustment (20)</span></span>

### <a name="proration-balance-examples"></a><span data-ttu-id="febb5-342">Przykłady salda proporcjonalnego</span><span class="sxs-lookup"><span data-stu-id="febb5-342">Proration balance examples</span></span>

#### <a name="prorated-monthly-plan"></a><span data-ttu-id="febb5-343">Miesięczny plan proporcjonalny</span><span class="sxs-lookup"><span data-stu-id="febb5-343">Prorated monthly plan</span></span>

<span data-ttu-id="febb5-344">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-344">**Plan setup**</span></span>

| <span data-ttu-id="febb5-345">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-345">Plan start date</span></span> | <span data-ttu-id="febb5-346">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-346">Accrual frequency</span></span> | <span data-ttu-id="febb5-347">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-347">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="febb5-348">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-348">1/1/2018</span></span>        | <span data-ttu-id="febb5-349">Miesięcznie</span><span class="sxs-lookup"><span data-stu-id="febb5-349">Monthly</span></span>           | <span data-ttu-id="febb5-350">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-350">Plan start date</span></span>      |

<span data-ttu-id="febb5-351">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-351">**Results**</span></span>

| <span data-ttu-id="febb5-352">Pracownik</span><span class="sxs-lookup"><span data-stu-id="febb5-352">Employee</span></span>            | <span data-ttu-id="febb5-353">Miesiące zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="febb5-353">Months of service</span></span> | <span data-ttu-id="febb5-354">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-354">Enrollment date</span></span> | <span data-ttu-id="febb5-355">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="febb5-355">Start date</span></span> | <span data-ttu-id="febb5-356">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-356">Accrual amount</span></span> | <span data-ttu-id="febb5-357">Proces naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-357">Process accrual</span></span> | <span data-ttu-id="febb5-358">Bilansowe</span><span class="sxs-lookup"><span data-stu-id="febb5-358">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="febb5-359">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="febb5-359">Jeannette Nicholson</span></span> | <span data-ttu-id="febb5-360">0,00</span><span class="sxs-lookup"><span data-stu-id="febb5-360">0.00</span></span>              | <span data-ttu-id="febb5-361">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-361">6/1/2018</span></span>        | <span data-ttu-id="febb5-362">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-362">6/1/2018</span></span>   | <span data-ttu-id="febb5-363">1.00</span><span class="sxs-lookup"><span data-stu-id="febb5-363">1.00</span></span>           | <span data-ttu-id="febb5-364">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-364">9/1/2018</span></span>        | <span data-ttu-id="febb5-365">3,00</span><span class="sxs-lookup"><span data-stu-id="febb5-365">3.00</span></span>    |
| <span data-ttu-id="febb5-366">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="febb5-366">Jay Norman</span></span>          | <span data-ttu-id="febb5-367">0,00</span><span class="sxs-lookup"><span data-stu-id="febb5-367">0.00</span></span>              | <span data-ttu-id="febb5-368">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-368">6/15/2018</span></span>       | <span data-ttu-id="febb5-369">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-369">6/15/2018</span></span>  | <span data-ttu-id="febb5-370">1.00</span><span class="sxs-lookup"><span data-stu-id="febb5-370">1.00</span></span>           | <span data-ttu-id="febb5-371">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-371">9/1/2018</span></span>        | <span data-ttu-id="febb5-372">2.53</span><span class="sxs-lookup"><span data-stu-id="febb5-372">2.53</span></span>    |

#### <a name="full-accrual-monthly-plan"></a><span data-ttu-id="febb5-373">Plan miesięczny pełnego naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-373">Full accrual monthly plan</span></span>

<span data-ttu-id="febb5-374">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-374">**Plan setup**</span></span>

| <span data-ttu-id="febb5-375">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-375">Plan start date</span></span> | <span data-ttu-id="febb5-376">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-376">Accrual frequency</span></span> | <span data-ttu-id="febb5-377">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-377">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="febb5-378">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-378">1/1/2018</span></span>        | <span data-ttu-id="febb5-379">Miesięcznie</span><span class="sxs-lookup"><span data-stu-id="febb5-379">Monthly</span></span>           | <span data-ttu-id="febb5-380">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-380">Plan start date</span></span>      |

<span data-ttu-id="febb5-381">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-381">**Results**</span></span>

| <span data-ttu-id="febb5-382">Pracownik</span><span class="sxs-lookup"><span data-stu-id="febb5-382">Employee</span></span>            | <span data-ttu-id="febb5-383">Miesiące zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="febb5-383">Months of service</span></span> | <span data-ttu-id="febb5-384">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-384">Enrollment date</span></span> | <span data-ttu-id="febb5-385">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="febb5-385">Start date</span></span> | <span data-ttu-id="febb5-386">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-386">Accrual amount</span></span> | <span data-ttu-id="febb5-387">Proces naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-387">Process accrual</span></span> | <span data-ttu-id="febb5-388">Bilansowe</span><span class="sxs-lookup"><span data-stu-id="febb5-388">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="febb5-389">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="febb5-389">Jeannette Nicholson</span></span> | <span data-ttu-id="febb5-390">0,00</span><span class="sxs-lookup"><span data-stu-id="febb5-390">0.00</span></span>              | <span data-ttu-id="febb5-391">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-391">6/1/2018</span></span>        | <span data-ttu-id="febb5-392">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-392">6/1/2018</span></span>   | <span data-ttu-id="febb5-393">1.00</span><span class="sxs-lookup"><span data-stu-id="febb5-393">1.00</span></span>           | <span data-ttu-id="febb5-394">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-394">9/1/2018</span></span>        | <span data-ttu-id="febb5-395">3,00</span><span class="sxs-lookup"><span data-stu-id="febb5-395">3.00</span></span>    |
| <span data-ttu-id="febb5-396">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="febb5-396">Jay Norman</span></span>          | <span data-ttu-id="febb5-397">0,00</span><span class="sxs-lookup"><span data-stu-id="febb5-397">0.00</span></span>              | <span data-ttu-id="febb5-398">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-398">6/15/2018</span></span>       | <span data-ttu-id="febb5-399">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-399">6/15/2018</span></span>  | <span data-ttu-id="febb5-400">1.00</span><span class="sxs-lookup"><span data-stu-id="febb5-400">1.00</span></span>           | <span data-ttu-id="febb5-401">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-401">9/1/2018</span></span>        | <span data-ttu-id="febb5-402">3,00</span><span class="sxs-lookup"><span data-stu-id="febb5-402">3.00</span></span>    |

#### <a name="no-accrual-monthly-plan"></a><span data-ttu-id="febb5-403">Plan miesięczny bez naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-403">No accrual monthly plan</span></span>

<span data-ttu-id="febb5-404">**Konfiguracja planu**</span><span class="sxs-lookup"><span data-stu-id="febb5-404">**Plan setup**</span></span>

| <span data-ttu-id="febb5-405">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-405">Plan start date</span></span> | <span data-ttu-id="febb5-406">Częstotliwość naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-406">Accrual frequency</span></span> | <span data-ttu-id="febb5-407">Podstawa okresu naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-407">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="febb5-408">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-408">1/1/2018</span></span>        | <span data-ttu-id="febb5-409">Miesięcznie</span><span class="sxs-lookup"><span data-stu-id="febb5-409">Monthly</span></span>           | <span data-ttu-id="febb5-410">Data początkowa planu</span><span class="sxs-lookup"><span data-stu-id="febb5-410">Plan start date</span></span>      |

<span data-ttu-id="febb5-411">**Wyniki**</span><span class="sxs-lookup"><span data-stu-id="febb5-411">**Results**</span></span>

| <span data-ttu-id="febb5-412">Pracownik</span><span class="sxs-lookup"><span data-stu-id="febb5-412">Employee</span></span>            | <span data-ttu-id="febb5-413">Miesiące zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="febb5-413">Months of service</span></span> | <span data-ttu-id="febb5-414">Data rejestracji</span><span class="sxs-lookup"><span data-stu-id="febb5-414">Enrollment date</span></span> | <span data-ttu-id="febb5-415">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="febb5-415">Start date</span></span> | <span data-ttu-id="febb5-416">Kwota naliczenia</span><span class="sxs-lookup"><span data-stu-id="febb5-416">Accrual amount</span></span> | <span data-ttu-id="febb5-417">Proces naliczania</span><span class="sxs-lookup"><span data-stu-id="febb5-417">Process accrual</span></span> | <span data-ttu-id="febb5-418">Bilansowe</span><span class="sxs-lookup"><span data-stu-id="febb5-418">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="febb5-419">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="febb5-419">Jeannette Nicholson</span></span> | <span data-ttu-id="febb5-420">0,00</span><span class="sxs-lookup"><span data-stu-id="febb5-420">0.00</span></span>              | <span data-ttu-id="febb5-421">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-421">6/1/2018</span></span>        | <span data-ttu-id="febb5-422">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-422">6/1/2018</span></span>   | <span data-ttu-id="febb5-423">1.00</span><span class="sxs-lookup"><span data-stu-id="febb5-423">1.00</span></span>           | <span data-ttu-id="febb5-424">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-424">9/1/2018</span></span>        | <span data-ttu-id="febb5-425">3,00</span><span class="sxs-lookup"><span data-stu-id="febb5-425">3.00</span></span>    |
| <span data-ttu-id="febb5-426">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="febb5-426">Jay Norman</span></span>          | <span data-ttu-id="febb5-427">0,00</span><span class="sxs-lookup"><span data-stu-id="febb5-427">0.00</span></span>              | <span data-ttu-id="febb5-428">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-428">6/15/2018</span></span>       | <span data-ttu-id="febb5-429">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-429">6/15/2018</span></span>  | <span data-ttu-id="febb5-430">1.00</span><span class="sxs-lookup"><span data-stu-id="febb5-430">1.00</span></span>           | <span data-ttu-id="febb5-431">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="febb5-431">9/1/2018</span></span>        | <span data-ttu-id="febb5-432">2.00</span><span class="sxs-lookup"><span data-stu-id="febb5-432">2.00</span></span>    |

