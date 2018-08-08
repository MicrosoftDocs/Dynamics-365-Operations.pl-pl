---
title: "Rejestracja nieobecności w module Czas i frekwencja"
description: "W tym temacie opisano sposób obsługi nieobecności w module Czas i frekwencja."
author: johanhoffmann
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 7ef244d5abf762bcaab426cf1cefb232383a8109
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="absence-registration-in-time-and-attendance"></a><span data-ttu-id="91e2c-103">Rejestracja nieobecności w module Czas i frekwencja</span><span class="sxs-lookup"><span data-stu-id="91e2c-103">Absence registration in Time and attendance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91e2c-104">W tym temacie opisano koncepcję nieobecności i wyjaśniono sposób obsługi nieobecności w module Czas i frekwencja.</span><span class="sxs-lookup"><span data-stu-id="91e2c-104">This topic describes the concepts for absence and explains how to handle absence in Time and attendance.</span></span>

## <a name="absence-that-is-based-on-regular-work-hours"></a><span data-ttu-id="91e2c-105">Nieobecność w normalnych godzinach pracy</span><span class="sxs-lookup"><span data-stu-id="91e2c-105">Absence that is based on regular work hours</span></span>

<span data-ttu-id="91e2c-106">Pracownicy są uznawani za nieobecnych, jeżeli nie pracują w normalnych godzinach pracy.</span><span class="sxs-lookup"><span data-stu-id="91e2c-106">Workers are considered absent for any hours that they don't work during their regular work hours.</span></span> <span data-ttu-id="91e2c-107">Normalne godziny pracy są zdefiniowane w standardowym profilu czasu pracownika.</span><span class="sxs-lookup"><span data-stu-id="91e2c-107">Regular work hours are defined in a worker's standard time profile.</span></span>

<span data-ttu-id="91e2c-108">Przykład: pracownik pracuje w profilu dziennym, w którym wejście ustawiono na godzinę 7:00, a wyjście na godzinę 15:00.</span><span class="sxs-lookup"><span data-stu-id="91e2c-108">For example, a worker is working on a day profile that has clock-in at 7:00 AM and clock-out at 3:00 PM.</span></span> <span data-ttu-id="91e2c-109">Jeżeli pracownik zarejestruje wejście o 9:00, jest uznawany za nieobecnego od 7:00 to 9:00 tego dnia.</span><span class="sxs-lookup"><span data-stu-id="91e2c-109">If the worker clocks in at 9:00 AM, he is considered absent from 7:00 AM to 9:00 AM on that day.</span></span>

<span data-ttu-id="91e2c-110">W takim przypadku pracownikowi zostaje wyświetlony monit o wprowadzenie powodu nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-110">In this case, workers are prompted to enter a reason for their absence.</span></span> <span data-ttu-id="91e2c-111">Mogą określić powód, wybierając kod nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-111">They can specify a reason by selecting an absence code.</span></span>

## <a name="absence-codes"></a><span data-ttu-id="91e2c-112">Kody nieobecności</span><span class="sxs-lookup"><span data-stu-id="91e2c-112">Absence codes</span></span>

<span data-ttu-id="91e2c-113">Kody nieobecności określają różne typy nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-113">Absence codes define the various types of absence.</span></span> <span data-ttu-id="91e2c-114">Kody nieobecności są definiowane przez firmę.</span><span class="sxs-lookup"><span data-stu-id="91e2c-114">Absence codes are defined by the company.</span></span>

<span data-ttu-id="91e2c-115">Do kodów nieobecności można zastosować różne zasady.</span><span class="sxs-lookup"><span data-stu-id="91e2c-115">Various rules can be applied to absence codes.</span></span> <span data-ttu-id="91e2c-116">Kod nieobecności można na przykład skonfigurować w celu odjęcia lub dodania płacy.</span><span class="sxs-lookup"><span data-stu-id="91e2c-116">For example, an absence code can be configured to deduct or grant pay.</span></span>

<span data-ttu-id="91e2c-117">Przykładowo firma definiuje kod nieobecności **Spóźnienie** używany przez pracowników w przypadku spóźnienia bez określonego powodu.</span><span class="sxs-lookup"><span data-stu-id="91e2c-117">For example, a company defines a **Late** absence code that workers use if they come in late and don't have a good reason.</span></span> <span data-ttu-id="91e2c-118">Firma określa także kod nieobecności **Kurs wewnętrzny** używany przez pracowników w odniesieniu do czasu poświęconego na udział w kursie wewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="91e2c-118">The company also defines an **Internal course** absence code that workers use for time that they spend attending internal courses.</span></span> <span data-ttu-id="91e2c-119">Te kody nieobecności można skonfigurować tak, aby kod **Spóźnienie** zmniejszał płacę pracownika, ale kod **Kurs wewnętrzny** nie zmniejszał płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="91e2c-119">These absence codes can be set up so that **Late** deducts from a worker's pay but **Internal course** doesn't deduct from a worker's pay.</span></span>

<span data-ttu-id="91e2c-120">Można skonfigurować automatyczne kody nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-120">You can set up automatic absence codes.</span></span> <span data-ttu-id="91e2c-121">Tych kodów nieobecności można użyć do obliczenia czasu pracy pracownika, jeżeli nie zarejestrowano nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-121">These absence codes can be used to calculate a worker's time when no absence is registered.</span></span> <span data-ttu-id="91e2c-122">Profil czasu pracownika określa, czy używany jest kod nieobecności czasu standardowego czy czasu elastycznego.</span><span class="sxs-lookup"><span data-stu-id="91e2c-122">The worker's time profile determines whether the absence code for standard time or flex time is used.</span></span>

### <a name="set-up-standard-time-and-flex-time"></a><span data-ttu-id="91e2c-123">Konfigurowanie czasu standardowego i czasu elastycznego</span><span class="sxs-lookup"><span data-stu-id="91e2c-123">Set up standard time and flex time</span></span>

- <span data-ttu-id="91e2c-124">Parametry czas standardowego i czasu elastycznego można skonfigurować, używając opcji **Automatyczne wstawianie nieobecności** i **Automatyczne wstawianie elastycznego czasu pracy-** na stronie **Parametry modułu Czas i frekwencja**.</span><span class="sxs-lookup"><span data-stu-id="91e2c-124">Configure the parameters for standard time and flex time by using the **Auto insert absence** and **Auto insert Flex-** options on the **Time and attendance parameters** page.</span></span>

## <a name="absence-groups"></a><span data-ttu-id="91e2c-125">Grupy nieobecności</span><span class="sxs-lookup"><span data-stu-id="91e2c-125">Absence groups</span></span>

<span data-ttu-id="91e2c-126">Kody nieobecności są zgrupowane w grupach nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-126">Absence codes are grouped into absence groups.</span></span> <span data-ttu-id="91e2c-127">Grupy nieobecności służą do grupowania kodów nieobecności o wspólnych cechach.</span><span class="sxs-lookup"><span data-stu-id="91e2c-127">You use absence groups to group absence codes that have common characteristics.</span></span> <span data-ttu-id="91e2c-128">Przykłady obejmują kody nieobecności dotyczące nieobecności usprawiedliwionej lub nieobecności z powodu wizyty lekarskiej, obowiązków sędziego przysięgłego lub choroby dziecka.</span><span class="sxs-lookup"><span data-stu-id="91e2c-128">Examples include absence codes for a legal absence, or absence because of a doctor's appointment, jury duty, or a sick child.</span></span>

## <a name="planned-absence"></a><span data-ttu-id="91e2c-129">Planowana nieobecność</span><span class="sxs-lookup"><span data-stu-id="91e2c-129">Planned absence</span></span>

<span data-ttu-id="91e2c-130">Jeżeli wiadomo, że pracownik będzie nieobecny przez pewien okres, taki jak zbliżające się wakacje, można użyć zaplanowanej nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-130">If you know that a worker will be absent for a period, such as an upcoming vacation, you can use planned absence.</span></span> <span data-ttu-id="91e2c-131">Planowaną nieobecność można ustawić, konfigurując kod nieobecności tak, aby uwzględniał planowaną nieobecność.</span><span class="sxs-lookup"><span data-stu-id="91e2c-131">You set up planned absence by configuring the absence code so that it considers the planned absence.</span></span> <span data-ttu-id="91e2c-132">Podczas konfigurowania planowanej nie obecności nie jest wyświetlany monit o podanie kodu nieobecności podczas okresu nieobecności, gdy obliczane są rejestracje czasu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="91e2c-132">When you set up a planned absence, you aren't prompted for an absence code during the absence period when user time registrations are calculated.</span></span> <span data-ttu-id="91e2c-133">Planowaną obecność można zdefiniować dla jednego pracownika lub można zdefiniować zadanie wsadowe w celu zbiorczej aktualizacji planowanej nieobecności pracowników.</span><span class="sxs-lookup"><span data-stu-id="91e2c-133">Planned absence can be defined for a single worker, or you can define a batch job to bulk update the planned absence for workers.</span></span>

### <a name="set-up-planned-absence"></a><span data-ttu-id="91e2c-134">Ustawianie planowanej nieobecności</span><span class="sxs-lookup"><span data-stu-id="91e2c-134">Set up planned absence</span></span>

1. <span data-ttu-id="91e2c-135">Wybierz opcję **Zasoby ludzkie** &gt; **Pracownicy** &gt; **Pracownicy etatowi** i wybierz pracownika.</span><span class="sxs-lookup"><span data-stu-id="91e2c-135">Select **Human resources** &gt; **Workers** &gt; **Employees**, and select an employee.</span></span>
2. <span data-ttu-id="91e2c-136">Wybierz opcję **Czas** &gt; **Przypisania czasu** &gt; **Rejestracja czasu nieobecności** i ustaw planowaną nieobecność.</span><span class="sxs-lookup"><span data-stu-id="91e2c-136">Select **Time** &gt; **Time assignments** &gt; **Time Absence registration**, and set up the planned absence.</span></span>

## <a name="interrupted-planned-absence"></a><span data-ttu-id="91e2c-137">Przerwana planowana nieobecność</span><span class="sxs-lookup"><span data-stu-id="91e2c-137">Interrupted planned absence</span></span>

<span data-ttu-id="91e2c-138">Po zastosowaniu opcji **Przerwij** przy ustawianiu planowanej nieobecności zostanie ona przerwana, jeżeli pracownik zaloguje się w okresie planowanej nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-138">If you apply the **Interrupt** option when you set up a planned absence, the planned absence will be interrupted if the worker signs in during the planned absence period.</span></span> <span data-ttu-id="91e2c-139">Planowana obecność zostanie oznaczona jako **Przerwana** i nie będzie miała wpływu na przyszłe obliczenia.</span><span class="sxs-lookup"><span data-stu-id="91e2c-139">The planned absence will be marked as **Interrupted** and won't have any effect on future calculations.</span></span>

### <a name="set-up-a-planned-absence-for-interruption"></a><span data-ttu-id="91e2c-140">Ustawianie planowanej nieobecności dla przerwania</span><span class="sxs-lookup"><span data-stu-id="91e2c-140">Set up a planned absence for interruption</span></span>

1. <span data-ttu-id="91e2c-141">Otwórz stronę **Rejestracja czasu nieobecności** zgodnie z opisem w procedurze ustawiania planowanej nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-141">Open the **Time Absence registration** page as described in the procedure for setting up planned absence.</span></span>
2. <span data-ttu-id="91e2c-142">Wybierz opcję **Przerwij**.</span><span class="sxs-lookup"><span data-stu-id="91e2c-142">Select **Interrupt**.</span></span>

<span data-ttu-id="91e2c-143">Opcja **Przerwij** ma zastosowanie, gdy czas jest rejestrowany za pomocą terminala produkcji lub urządzenia produkcji.</span><span class="sxs-lookup"><span data-stu-id="91e2c-143">The **Interrupt** option applies when time is registered through the shop floor terminal or the shop floor device.</span></span> <span data-ttu-id="91e2c-144">Ta opcja nie ma zastosowania, jeżeli rejestracje są wprowadzane na stronach obliczania i zatwierdzania lub na stronie **Elektroniczna karta czasowa**.</span><span class="sxs-lookup"><span data-stu-id="91e2c-144">The option doesn't apply if the registrations are entered on the calculation and approval pages, or on the **Electronic timecard** page.</span></span>

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a><span data-ttu-id="91e2c-145">Przykłady użycia nieobecności w profilu elastycznym</span><span class="sxs-lookup"><span data-stu-id="91e2c-145">Examples of the use of absence in a flex profile</span></span>

<span data-ttu-id="91e2c-146">Poniższe trzy przykłady przedstawiają sposób obliczania nieobecności w profilu zawierającym okresy elastyczne.</span><span class="sxs-lookup"><span data-stu-id="91e2c-146">The following three examples show how absence is calculated in a profile that has flex periods.</span></span>

<span data-ttu-id="91e2c-147">W przykładach używany jest poniższy profil.</span><span class="sxs-lookup"><span data-stu-id="91e2c-147">The examples use the following profile.</span></span>

| <span data-ttu-id="91e2c-148">Wejście</span><span class="sxs-lookup"><span data-stu-id="91e2c-148">Clock-in</span></span> | <span data-ttu-id="91e2c-149">Czas standardowy</span><span class="sxs-lookup"><span data-stu-id="91e2c-149">Standard time</span></span>    | <span data-ttu-id="91e2c-150">Przerwa</span><span class="sxs-lookup"><span data-stu-id="91e2c-150">Break</span></span>             | <span data-ttu-id="91e2c-151">Czas standardowy</span><span class="sxs-lookup"><span data-stu-id="91e2c-151">Standard time</span></span> | <span data-ttu-id="91e2c-152">Elastyczny czas pracy -</span><span class="sxs-lookup"><span data-stu-id="91e2c-152">Flex-</span></span>        | <span data-ttu-id="91e2c-153">Wyjście</span><span class="sxs-lookup"><span data-stu-id="91e2c-153">Clock-out</span></span> | <span data-ttu-id="91e2c-154">Elastyczny czas pracy (+)</span><span class="sxs-lookup"><span data-stu-id="91e2c-154">Flex+</span></span>        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| <span data-ttu-id="91e2c-155">8:00</span><span class="sxs-lookup"><span data-stu-id="91e2c-155">8 AM</span></span>     | <span data-ttu-id="91e2c-156">9:00 do 11:30</span><span class="sxs-lookup"><span data-stu-id="91e2c-156">9 AM to 11:30 AM</span></span> | <span data-ttu-id="91e2c-157">11:30 do 12:00</span><span class="sxs-lookup"><span data-stu-id="91e2c-157">11:30 AM to 12 PM</span></span> | <span data-ttu-id="91e2c-158">12:00 do 15:00</span><span class="sxs-lookup"><span data-stu-id="91e2c-158">12 PM to 3 PM</span></span> | <span data-ttu-id="91e2c-159">15:00 do 16:00</span><span class="sxs-lookup"><span data-stu-id="91e2c-159">3 PM to 4 PM</span></span> | <span data-ttu-id="91e2c-160">16:00</span><span class="sxs-lookup"><span data-stu-id="91e2c-160">4 PM</span></span>      | <span data-ttu-id="91e2c-161">16:00 do 18:00</span><span class="sxs-lookup"><span data-stu-id="91e2c-161">4 PM to 6 PM</span></span> |

### <a name="example-1-signing-out-during-a-flex--period"></a><span data-ttu-id="91e2c-162">Przykład 1: Wylogowanie podczas okresu elastycznego-</span><span class="sxs-lookup"><span data-stu-id="91e2c-162">Example 1: Signing out during a Flex- period</span></span>

<span data-ttu-id="91e2c-163">Pracownik rejestruje się przy wejściu o 8:00, a przy wyjściu o 15:30.</span><span class="sxs-lookup"><span data-stu-id="91e2c-163">The worker clocks in at 8:00 AM and clocks out at 3:30 PM.</span></span> <span data-ttu-id="91e2c-164">W tym przypadku, ponieważ pracownik rejestruje się przy wyjściu podczas okresu elastycznego-, nieobecność nie jest obliczana, a od salda elastycznego pracownika odliczane jest pół godziny.</span><span class="sxs-lookup"><span data-stu-id="91e2c-164">In this case, because the worker clocks out during a Flex- period, no absence is calculated, and half an hour is deducted from the worker's flex balance.</span></span>

### <a name="example-2-signing-out-in-during-standard-time-period"></a><span data-ttu-id="91e2c-165">Przykład 2: Wylogowanie w okresie czasu standardowego</span><span class="sxs-lookup"><span data-stu-id="91e2c-165">Example 2: Signing out in during Standard time period</span></span>

<span data-ttu-id="91e2c-166">Pracownik rejestruje się przy wejściu o 8:00, a przy wyjściu o 14:30.</span><span class="sxs-lookup"><span data-stu-id="91e2c-166">The worker clocks in at 8:00 AM and clocks out at 2:30 PM.</span></span> <span data-ttu-id="91e2c-167">W tym przypadku, ponieważ pracownik rejestruje się przy wyjściu podczas okresu standardowego, nieobecność jest obliczana od 14:30 do 16:00 i rejestrowany jest okres nieobecności wynoszący 1,5 godziny.</span><span class="sxs-lookup"><span data-stu-id="91e2c-167">In this case, because the worker clocks out during the Standard time period, absence is calculated from 2:30 PM to 4 PM, and an absence period of 1.5 hours is registered.</span></span> <span data-ttu-id="91e2c-168">Dla tego okresu wymagany jest kod nieobecności.</span><span class="sxs-lookup"><span data-stu-id="91e2c-168">An absence code for that period is required.</span></span>

### <a name="example-3-signing-out-during-a-flex-period"></a><span data-ttu-id="91e2c-169">Przykład 3: Wylogowanie podczas okresu elastycznego+</span><span class="sxs-lookup"><span data-stu-id="91e2c-169">Example 3: Signing out during a Flex+ period</span></span>

<span data-ttu-id="91e2c-170">Pracownik rejestruje się przy wejściu o 8:00, a przy wyjściu o 16:30.</span><span class="sxs-lookup"><span data-stu-id="91e2c-170">The worker clocks in at 8:00 AM and clocks out at 4:30 PM.</span></span> <span data-ttu-id="91e2c-171">W tym przypadku, ponieważ pracownik rejestruje się przy wyjściu podczas okresu elastycznego+, nieobecność nie jest obliczana, a do salda elastycznego pracownika dodawane jest pół godziny.</span><span class="sxs-lookup"><span data-stu-id="91e2c-171">In this case, because the worker clocks out during a Flex+ period, no absence is calculated, and half an hour is added to the worker's flex balance.</span></span>

## <a name="absence-in-the-calculation-and-approval-process"></a><span data-ttu-id="91e2c-172">Nieobecność w obliczeniu i proces zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="91e2c-172">Absence in the calculation and approval process</span></span>

<span data-ttu-id="91e2c-173">Rejestracje czasu pracownika muszą zostać obliczone i zatwierdzone przed przeniesieniem do systemu listy płac jako elementy płac.</span><span class="sxs-lookup"><span data-stu-id="91e2c-173">Worker time registrations must be calculated and approved before they can be transferred to a payroll system as pay items.</span></span>

<span data-ttu-id="91e2c-174">Osoba zatwierdzająca może zmienić rejestracje czasu pracownika.</span><span class="sxs-lookup"><span data-stu-id="91e2c-174">An approver can change a worker's time registrations.</span></span> <span data-ttu-id="91e2c-175">Osoba zatwierdzająca także zmienić wszystkie nieobecności, które zarejestrował pracownik.</span><span class="sxs-lookup"><span data-stu-id="91e2c-175">The approver can even change any absence that the worker has registered.</span></span> <span data-ttu-id="91e2c-176">Jeżeli osoba zatwierdzająca ręcznie wprowadzi okres, który zawiera kod nieobecności, kod nieobecności dla tego okresu nie zostanie zastąpiony przez domyślny kod nieobecności z parametrów modułu Czas i frekwencja.</span><span class="sxs-lookup"><span data-stu-id="91e2c-176">If the approver manually enters a time period that has an absence code, the absence code for that period isn't overridden by the default absence code from the Time and attendance parameters.</span></span>

<span data-ttu-id="91e2c-177">Przykładowo pracownica rejestruje się przy wyjściu o 10:00 i wybiera kod nieobecności oznaczający, że się spóźniła.</span><span class="sxs-lookup"><span data-stu-id="91e2c-177">For example, a worker clocks in at 10 AM and selects an absence code that indicates that she is late.</span></span> <span data-ttu-id="91e2c-178">Następnie informuje przełożonego, ze ma wizytę u lekarza od 8:00 do 10:00.</span><span class="sxs-lookup"><span data-stu-id="91e2c-178">Later, the worker informs her supervisor that she had a doctor's appointment from 8 AM to 10 AM.</span></span> <span data-ttu-id="91e2c-179">Wizyta u lekarza nie powinna spowodować zmniejszenia płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="91e2c-179">A doctor's appointment should not cause a deduction in the worker's pay.</span></span> <span data-ttu-id="91e2c-180">Dlatego w tym przypadku przełożony może dostosować dwugodzinną nieobecność od 8:00 do 10:00, ręcznie wprowadzając kod nieobecności, który oznacza chorobę przez te dwie godziny.</span><span class="sxs-lookup"><span data-stu-id="91e2c-180">Therefore, in this case, the supervisor can adjust the two hours of absence from 8 AM to 10 AM by manually entering an absence code that indicates illness for those two hours.</span></span>

### <a name="calculate-and-approve-absence"></a><span data-ttu-id="91e2c-181">Obliczanie i zatwierdzanie nieobecności</span><span class="sxs-lookup"><span data-stu-id="91e2c-181">Calculate and approve absence</span></span>

- <span data-ttu-id="91e2c-182">Wybierz opcję **Czas i frekwencja** &gt; **Przejrzyj i zatwierdź** &gt; **Zatwierdź lub oblicz**.</span><span class="sxs-lookup"><span data-stu-id="91e2c-182">Select **Time attendance** &gt; **Review and approve** &gt; **Approve or Calculate**.</span></span>

