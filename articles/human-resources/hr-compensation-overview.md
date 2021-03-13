---
title: Plany wynagrodzeń
description: Menedżerowie ds. wynagrodzeń i świadczeń mogą za pomocą modułu Zarządzanie wynagrodzeniami obsługiwać i przetwarzać plany wynagrodzeń o stałej i zmiennej wysokości dla pracowników organizacji.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a5843b53ae857f1aa65491008c7f0970f20d53f5
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113787"
---
# <a name="compensation-plans"></a><span data-ttu-id="5af59-103">Plany wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="5af59-103">Compensation plans</span></span>

<span data-ttu-id="5af59-104">Menedżerowie ds. wynagrodzeń i świadczeń mogą za pomocą modułu Zarządzanie wynagrodzeniami obsługiwać i przetwarzać plany wynagrodzeń o stałej i zmiennej wysokości dla pracowników organizacji.</span><span class="sxs-lookup"><span data-stu-id="5af59-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="5af59-105">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="5af59-105">Introduction</span></span>

<span data-ttu-id="5af59-106">Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród.</span><span class="sxs-lookup"><span data-stu-id="5af59-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="5af59-107">Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="5af59-108">Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="5af59-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="5af59-109">Pracownicy mogą być przypisani do jednego lub większej liczby obu typów systemów.</span><span class="sxs-lookup"><span data-stu-id="5af59-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="5af59-110">Pracownik musi spełnić następujące wymagania, aby kwalifikować się do planu wynagrodzeń:</span><span class="sxs-lookup"><span data-stu-id="5af59-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="5af59-111">Pracownik musi mieć aktywne przypisanie stanowiska.</span><span class="sxs-lookup"><span data-stu-id="5af59-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="5af59-112">Pracownik musi spełniać kryteria, które są zdefiniowane przez reguły uprawnienia do systemu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="5af59-113">Konfiguracja wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="5af59-113">Compensation setup</span></span>
<span data-ttu-id="5af59-114">W poniższej tabeli wymieniono składniki procesu wynagrodzenia, który może być integralną częścią w procesie konfigurowania systemu wynagrodzeń w firmie.</span><span class="sxs-lookup"><span data-stu-id="5af59-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5af59-115">Składnik</span><span class="sxs-lookup"><span data-stu-id="5af59-115">Component</span></span></th>
<th><span data-ttu-id="5af59-116">Więcej informacji...</span><span class="sxs-lookup"><span data-stu-id="5af59-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5af59-117">Akcje związane ze stałym wynagrodzeniem</span><span class="sxs-lookup"><span data-stu-id="5af59-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="5af59-118">Akcje dotyczące stałego wynagrodzenia mają dwojaki cel:</span><span class="sxs-lookup"><span data-stu-id="5af59-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="5af59-119">Akcja można określać rodzaj informacji, które muszą być rejestrowane, gdy wynagrodzenie pracownika zmienia się.</span><span class="sxs-lookup"><span data-stu-id="5af59-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="5af59-120">Na przykład, można wymagać rejestrowania powodu zmiany, np. promocji lub degradacji.</span><span class="sxs-lookup"><span data-stu-id="5af59-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="5af59-121">Akcje mogą także zapewnić, że podczas przetwarzania w systemach stałych wynagrodzeń będą stosowane obliczenia.</span><span class="sxs-lookup"><span data-stu-id="5af59-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="5af59-122">Na przykład akcje typu Kapitał własny porównają płace pracowników z minimalnym punktem odniesienia dla poziomu pracownika i zapewnią, że pracownik otrzymuje co najmniej wynagrodzenie minimalne.</span><span class="sxs-lookup"><span data-stu-id="5af59-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee&#39;s and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-123">Poziomy</span><span class="sxs-lookup"><span data-stu-id="5af59-123">Levels</span></span></td>
<td><span data-ttu-id="5af59-124">Poziomy są powiązane z zadaniami i stanowiskami, które są związane z odniesieniami stanowiska.</span><span class="sxs-lookup"><span data-stu-id="5af59-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="5af59-125">Można utworzyć odrębne poziomy dla następujących trzech typów systemów wynagrodzeń: Kategoria, Pasmo i Krok.</span><span class="sxs-lookup"><span data-stu-id="5af59-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-126">Macierz zakresów wykorzystania</span><span class="sxs-lookup"><span data-stu-id="5af59-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="5af59-127">Macierz zakresu wykorzystania pomaga przejść pracownikom do punktu kontrolnego ich zadań.</span><span class="sxs-lookup"><span data-stu-id="5af59-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="5af59-128">Zakresy wykorzystania pozwalają także kontrolować kapitał stawek płacowych w firmie bez uwzględniania wyników osiągniętych przez poszczególnych pracowników bądź całą firmę.</span><span class="sxs-lookup"><span data-stu-id="5af59-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee&#39;s performance or the overall performance of the company.</span></span> <span data-ttu-id="5af59-129">Na przykład, gorzej opłacani pracownicy należący do danego zakresu dostają wyższe podwyżki liczone w procentach niż pracownicy z wyższym wynagrodzeniem.</span><span class="sxs-lookup"><span data-stu-id="5af59-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="5af59-130">W ten sposób można systematycznie kompensować różnice kapitału własnego.</span><span class="sxs-lookup"><span data-stu-id="5af59-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="5af59-131">Zakres wykorzystania jest obliczany w następujący sposób: (Stała stawka płacy – Wartość minimalna zakresu)/(Wartość maksymalna zakresu – Wartość minimalna zakresu).</span><span class="sxs-lookup"><span data-stu-id="5af59-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-132">Konfiguracje punktów odniesienia</span><span class="sxs-lookup"><span data-stu-id="5af59-132">Reference point setups</span></span></td>
<td><span data-ttu-id="5af59-133">Konfiguracja punktów odniesienia obejmuje zbiór punktów odniesienia stanowiących zakresy w macierzy.</span><span class="sxs-lookup"><span data-stu-id="5af59-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="5af59-134">Każdy zakres może być powiązany ze stawką płacy.</span><span class="sxs-lookup"><span data-stu-id="5af59-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="5af59-135">Na przykład systemy stopniowane często mają punkty odniesienia: minimum, środkowy i maksimum.</span><span class="sxs-lookup"><span data-stu-id="5af59-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-136">Macierz wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="5af59-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="5af59-137">Macierz wynagrodzeń jest zbiorem punktów odniesienia i poziomów, które służą do tworzenia struktury wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-138">Struktura wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="5af59-138">Compensation structure</span></span></td>
<td><span data-ttu-id="5af59-139">Struktura wynagrodzeń jest macierzą, która ma stawki płac skojarzone z punktami odniesienia dla każdego poziomu.</span><span class="sxs-lookup"><span data-stu-id="5af59-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-140">Reguły uprawnienia</span><span class="sxs-lookup"><span data-stu-id="5af59-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="5af59-141">Reguły uprawnienia służą do identyfikowania pracowników w określonych zadaniach, ich funkcji, typów, działów, związków zawodowych lub lokalizacji objętych określonym systemem wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="5af59-142">Należy utworzyć reguły uprawnienia dla obu systemów wynagrodzeń: zmiennych i stałych, aby zarejestrować pracowników w systemie.</span><span class="sxs-lookup"><span data-stu-id="5af59-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="5af59-143">Po określeniu reguł uprawnienia dla systemu wynagrodzeń użytkownik może określić zestaw poziomów tego systemu, które powinny być stosowane do zadań objętych systemem.</span><span class="sxs-lookup"><span data-stu-id="5af59-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-144">Częstotliwości wypłat</span><span class="sxs-lookup"><span data-stu-id="5af59-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="5af59-145">Częstotliwości wypłat umożliwiają zdefiniowanie okresu, dla którego określono wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="5af59-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="5af59-146">Na przykład częstotliwość płac pomoże określić, czy kwota wynagrodzenia została zdefiniowana jako płaca roczna, czy stawka godzinowa.</span><span class="sxs-lookup"><span data-stu-id="5af59-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="5af59-147">Częstotliwości wypłat są również używane do ustawiania współczynników konwersji w celu konwersji kwot wynagrodzenia z miesięcznych, tygodniowych, dwutygodniowych i godzinowych na roczne.</span><span class="sxs-lookup"><span data-stu-id="5af59-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-148">Regiony wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="5af59-148">Compensation regions</span></span></td>
<td><span data-ttu-id="5af59-149">Region wynagrodzenia można zastosować do określenia wynagrodzenia pracownika na podstawie lokalizacji miejsca pracy.</span><span class="sxs-lookup"><span data-stu-id="5af59-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-150">Punkt kontrolny</span><span class="sxs-lookup"><span data-stu-id="5af59-150">Control point</span></span></td>
<td><span data-ttu-id="5af59-151">Punkt kontrolny wskazuje idealną stawkę płacową dla wszystkich pracowników, którym przypisano dany poziom wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="5af59-152">W przypadku struktur z kategoriami wynagrodzeń punktami kontrolnymi są zazwyczaj punkty centralne zakresu.</span><span class="sxs-lookup"><span data-stu-id="5af59-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="5af59-153">Punkty kontrolne są rzadko używane odnośnie do struktur pasmowych systemów wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-153">Band structures rarely use control points.</span></span> <span data-ttu-id="5af59-154">Punkt kontrolny stałych wynagrodzeń można określić w formularzu systemów stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-155">Funkcje stanowisk</span><span class="sxs-lookup"><span data-stu-id="5af59-155">Job functions</span></span></td>
<td><span data-ttu-id="5af59-156">Funkcje stanowisk są używane do klasyfikowania i filtrowania systemów wynagrodzeń dla określonych zadań.</span><span class="sxs-lookup"><span data-stu-id="5af59-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-157">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="5af59-157">Job types</span></span></td>
<td><span data-ttu-id="5af59-158">Typy stanowisk są używane do klasyfikowania i filtrowania systemów wynagrodzeń dla określonych zadań.</span><span class="sxs-lookup"><span data-stu-id="5af59-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-159">Typy wynagrodzenia o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="5af59-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="5af59-160">Typy zmiennych wynagrodzeń, takie jak nagroda w postaci akcji lub premia gotówkowa, są stosowane w zmiennych systemach wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-161">Siatki wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="5af59-161">Compensation grids</span></span></td>
<td><span data-ttu-id="5af59-162">Siatki wynagrodzeń zawierają strukturę wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="5af59-163">Siatka wynagrodzeń może być używana w jednym lub kilku systemach wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5af59-164">Plany wydajności</span><span class="sxs-lookup"><span data-stu-id="5af59-164">Performance plans</span></span></td>
<td><span data-ttu-id="5af59-165">Plany wydajności można przypisać do macierzy alokacji (w przypadku realizacji strategii związanej z wypłatą wynagrodzeń za wyniki).</span><span class="sxs-lookup"><span data-stu-id="5af59-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5af59-166">Oceny wydajności</span><span class="sxs-lookup"><span data-stu-id="5af59-166">Performance ratings</span></span></td>
<td><span data-ttu-id="5af59-167">Oceny wydajności są wykorzystywane w planach wydajności do ustalania kwot podwyżek lub wysokości nagród za wydajność.</span><span class="sxs-lookup"><span data-stu-id="5af59-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="5af59-168">Zdarzenia procesowe</span><span class="sxs-lookup"><span data-stu-id="5af59-168">Process events</span></span>
<span data-ttu-id="5af59-169">Zdarzenie procesowe oblicza wysokość wynagrodzenia w danym okresie dla wszystkich pracowników objętych co najmniej jednym stałym lub zmiennym planem wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="5af59-170">Zdarzenie procesu można uruchamiać wielokrotnie, aby na przykład testować lub aktualizować obliczone wyniki wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="5af59-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="5af59-171">Wynagrodzenie — zdarzenia</span><span class="sxs-lookup"><span data-stu-id="5af59-171">Compensation events</span></span>
-------------------

<span data-ttu-id="5af59-172">Po każdym uruchomieniu procesu jest tworzone zdarzenie dotyczące wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="5af59-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="5af59-173">Zdarzenie dotyczące wynagrodzenia zawiera wyniki procesu wynagrodzenia dla każdego pracownika uwzględnionego w zdarzeniu tego procesu.</span><span class="sxs-lookup"><span data-stu-id="5af59-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="5af59-174">Jeśli obliczenia są poprawne, można załadować zdarzenie związane z wynagrodzeniem w celu aktualizacji rekordów wynagrodzeń dla pracowników, których dotyczą zdarzenia procesu.</span><span class="sxs-lookup"><span data-stu-id="5af59-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="5af59-175"> Zalecenia</span><span class="sxs-lookup"><span data-stu-id="5af59-175">Recommendations</span></span>
<span data-ttu-id="5af59-176">Po uruchomieniu zdarzenia procesowego może zalecić korekty podwyżki uznaniowej lub kwoty premii pracownika, zgodnie z obliczonymi wytycznymi zdarzenia procesowego.</span><span class="sxs-lookup"><span data-stu-id="5af59-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="5af59-177">Aby przygotować zalecenia dla pracowników, trzeba włączyć zalecenia podczas konfigurowania systemu wynagrodzeń lub podczas ustawiania zdarzenia procesowego.</span><span class="sxs-lookup"><span data-stu-id="5af59-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>



