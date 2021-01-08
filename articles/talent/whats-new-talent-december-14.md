---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (14 grudnia 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 9887d22a513e820c35c51b6c702e2d9d34ab1214
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529763"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-december-14-2018"></a><span data-ttu-id="c3994-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (14 grudnia 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="c3994-103">What's new or changed in Dynamics 365 Talent - Core HR (December 14, 2018)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c3994-104">**Kompilacja 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="c3994-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="c3994-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="c3994-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="c3994-106">Zmiany</span><span class="sxs-lookup"><span data-stu-id="c3994-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="c3994-107">USA - obsługa ACA (Affordable Care Act) dla formularzy podatkowych 1095-B i 1095-C za rok 2018</span><span class="sxs-lookup"><span data-stu-id="c3994-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="c3994-108">Każdego roku pracodawcy ALE (Applicable Large Employer) muszą wystawiać pełnoetatowym pracownikom formularz 1095-C.</span><span class="sxs-lookup"><span data-stu-id="c3994-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="c3994-109">Ponadto jeśli pracodawca zapewnia opcję samodzielnego ubezpieczenia, musi przedstawić formularz 1095-C (jeśli jest ALE) lub 1095-B (jeśli jest małym pracodawcą) wszystkim pracownikom (pełnoetatowym lub niepełnoetatowym) objętym jednym z oferowanych planów ubezpieczeń zdrowotnych.</span><span class="sxs-lookup"><span data-stu-id="c3994-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="c3994-110">Ta funkcja zapewnia formularze 1095-C i 1095-B do wydrukowania.</span><span class="sxs-lookup"><span data-stu-id="c3994-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="c3994-111">Podczas importowania SubmittedByPersonId pole w HcmPerfJournalEntity jest ignorowane</span><span class="sxs-lookup"><span data-stu-id="c3994-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="c3994-112">Podczas importowania/eksportowania wpisów dziennika wydajności, pole **Przesłano przez** jest ignorowane.</span><span class="sxs-lookup"><span data-stu-id="c3994-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="c3994-113">Dzięki tej zmianie wartość **zaimportowane/wyeksportowane** odpowiada bieżącej wartości w tabeli podczas eksportowania; podczas importowania system zostanie zaktualizowany o wartość podaną w pliku importu.</span><span class="sxs-lookup"><span data-stu-id="c3994-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="c3994-114">Karta analizy w obszarze roboczym „Urlopy i nieobecności” zawiera błąd „OpenConnectionError” dla niesystemowych ról Administrator</span><span class="sxs-lookup"><span data-stu-id="c3994-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="c3994-115">Ta aktualizacja sprawi, że żadne błędy nie będą wyświetlane podczas otwierania na karcie **Analizy** w obszarze roboczym **Urlopy i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="c3994-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="c3994-116">Samoobsługa pracownika, wyświetlanie Hierarchii stanowisk z kafelka nie wyświetla węzła nadrzędnego</span><span class="sxs-lookup"><span data-stu-id="c3994-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="c3994-117">Wprowadzono zmianę w celu skorygowania błędu „Uzyskanie informacji o węźle nadrzędnym nie powiodło się” po dokonaniu personalizacji hierarchii stanowisk aby pojawiała się w istniejącym obszarze roboczym i wybraniu stanowiska w hierarchii.</span><span class="sxs-lookup"><span data-stu-id="c3994-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="c3994-118">Musi być administratorem systemu, aby zobaczyć kartę Lista płac na stronie Stanowisko</span><span class="sxs-lookup"><span data-stu-id="c3994-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="c3994-119">Wprowadzono zmianę w celu objęcia prawidłowych elementów zabezpieczeń istniejącym uprawnieniem: „Obsługa szczegółów listy płac pracownika i stanowiska”.</span><span class="sxs-lookup"><span data-stu-id="c3994-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="c3994-120">Po wprowadzeniu tej zmiany domyślnie administrator listy płac będzie miał dostęp do pól Lista płac na stronie Stanowisko.</span><span class="sxs-lookup"><span data-stu-id="c3994-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="c3994-121">Błąd podczas przesyłania przeglądu wydajności do menedżera i symbol zastępczy %Reviews.PerfPeriod% jest używany w instrukcji przesyłania</span><span class="sxs-lookup"><span data-stu-id="c3994-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="c3994-122">Zmiana została dokonana korygującą błąd „Odwołanie o wartości Null”, używając symbol zastępczy %Reviews.PerfPeriod% w instrukcji przesyłania.</span><span class="sxs-lookup"><span data-stu-id="c3994-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="c3994-123">Raport Power BI siły roboczej zawiera błąd gdy data stażu pracownika jest dniem przestępnym</span><span class="sxs-lookup"><span data-stu-id="c3994-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="c3994-124">Po wprowadzeniu tej zmiany dni przestępne są teraz obsługiwane w Power BI.</span><span class="sxs-lookup"><span data-stu-id="c3994-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="c3994-125">Integracja między Core HR i Attract</span><span class="sxs-lookup"><span data-stu-id="c3994-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="c3994-126">Wprowadzono zmianę w celu aktualizacji integracji między Core HR and Attract w związku z kandydatami do zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="c3994-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="c3994-127">Aby kandydaci do zatrudnienia byli widoczni w przestrzeni roboczej **Zarządzanie personelem**, używane są następujące obiekty Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="c3994-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following Common Data Service entities are used:</span></span>

<span data-ttu-id="c3994-128">Podanie o pracę</span><span class="sxs-lookup"><span data-stu-id="c3994-128">Job Application</span></span>
- <span data-ttu-id="c3994-129">Przyczyna stanu musi być ustawiona do Oferta zaakceptowana</span><span class="sxs-lookup"><span data-stu-id="c3994-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="c3994-130">Zawiera informacje o kandydacie i wakacie</span><span class="sxs-lookup"><span data-stu-id="c3994-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="c3994-131">Kandydat</span><span class="sxs-lookup"><span data-stu-id="c3994-131">Candidate</span></span>
-   <span data-ttu-id="c3994-132">Zawiera informacje o kandydacie</span><span class="sxs-lookup"><span data-stu-id="c3994-132">Provides Candidate information</span></span>

<span data-ttu-id="c3994-133">Wakat</span><span class="sxs-lookup"><span data-stu-id="c3994-133">Job Opening</span></span>
-   <span data-ttu-id="c3994-134">Zawiera identyfikator wakatu i uczestników wakatu</span><span class="sxs-lookup"><span data-stu-id="c3994-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="c3994-135">Uczestnicy wakatu</span><span class="sxs-lookup"><span data-stu-id="c3994-135">Job Opening Participants</span></span>
-   <span data-ttu-id="c3994-136">Zawiera informacje i menedżerze zatrudniającym</span><span class="sxs-lookup"><span data-stu-id="c3994-136">Provides Hiring Manager</span></span>

<span data-ttu-id="c3994-137">Po dodaniu kandydata w zarządzaniu personelem kandydat może również być zwolniony przy użyciu nowej opcji dostępnej na karcie kandydata.</span><span class="sxs-lookup"><span data-stu-id="c3994-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="c3994-138">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="c3994-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="c3994-139">Urlopy i nieobecności: przyszłe i urlopy i prognozowane saldo urlopów</span><span class="sxs-lookup"><span data-stu-id="c3994-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="c3994-140">Zmiany dotyczą opcji zezwalania pracownikom na przewidywanie czasu wolnego i przyszłych wniosków o czas wolny bez wpływu na aktualne saldo czasu wolnego, dlatego zmienia się również sposób wyświetlania czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="c3994-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="c3994-141">Dostępne saldo aktualnie wyświetlana jest ilością czasu wolnego od pracy dostępną na żądania w tym naliczenia do dnia dzisiejszego oraz wszelkie zatwierdzone wnioski urlopowe do końca czasu.</span><span class="sxs-lookup"><span data-stu-id="c3994-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="c3994-142">Po zwolnieniu zdolność do prognozy wyświetlane saldo zmienia się na bieżące saldo czasu wolnego wraz z naliczeniami i wnioskami do dnia dzisiejszego.</span><span class="sxs-lookup"><span data-stu-id="c3994-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="c3994-143">Pracownicy i menedżerowie zobaczą te zaktualizowane salda w panelach samoobsługowych dla pracowników i menedżerów na karcie **Czas wolny** w oknie **Sala czasu wolnego**.</span><span class="sxs-lookup"><span data-stu-id="c3994-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="c3994-144">Menedżerów HR będzie widział te zaktualizowane salda w przestrzeni roboczej **Osoby** i w oknie pracownika **Przypisane plany urlopów**.</span><span class="sxs-lookup"><span data-stu-id="c3994-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="c3994-145">Znany problem</span><span class="sxs-lookup"><span data-stu-id="c3994-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance"></a><span data-ttu-id="c3994-146">Błędy mapowania w integracji z Finance</span><span class="sxs-lookup"><span data-stu-id="c3994-146">Mapping errors in the integration with Finance</span></span>

<span data-ttu-id="c3994-147">Zidentyfikowano następujące problemy w bieżącym szablonie odnośnie do integracji rozwiązania Talent z rozwiązaniem Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="c3994-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 Finance.</span></span> <span data-ttu-id="c3994-148">Nowy szablon zostanie wkrótce opublikowany i będzie stosowany do wszystkich nowych projektów integracji, które zostały utworzone.</span><span class="sxs-lookup"><span data-stu-id="c3994-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="c3994-149">Dla istniejących projektów integracji mapowania zadań mogą być zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c3994-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="c3994-150">Zaktualizowane mapowania można znaleźć w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c3994-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="c3994-151">Zadanie Stanowiska do Przypisania pracy nadrzędnej do stanowisk nie integruje danych.</span><span class="sxs-lookup"><span data-stu-id="c3994-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="c3994-152">Występuje problem, który jest aktualnie badany.</span><span class="sxs-lookup"><span data-stu-id="c3994-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="c3994-153">Obecnie nie ma rozwiązania problemu mapowania.</span><span class="sxs-lookup"><span data-stu-id="c3994-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="c3994-154">Zadanie Działy do Jednostka operacyjna musi mieć zaktualizowane następujące mapowania.</span><span class="sxs-lookup"><span data-stu-id="c3994-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="c3994-155">Pole istniejącego źródła</span><span class="sxs-lookup"><span data-stu-id="c3994-155">Existing source field</span></span>          | <span data-ttu-id="c3994-156">Pole nowego źródła</span><span class="sxs-lookup"><span data-stu-id="c3994-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="c3994-157">cdm_description (Opis)</span><span class="sxs-lookup"><span data-stu-id="c3994-157">cdm_description (Description)</span></span>  | <span data-ttu-id="c3994-158">cdm_name (nazwa)</span><span class="sxs-lookup"><span data-stu-id="c3994-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="c3994-159">Dodatkowe mapowanie również musi zostać dodane.</span><span class="sxs-lookup"><span data-stu-id="c3994-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="c3994-160">Wybierz ostatnie pole **Brak**, aby dodać następujące mapowanie.</span><span class="sxs-lookup"><span data-stu-id="c3994-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="c3994-161">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="c3994-161">Source field</span></span>                   | <span data-ttu-id="c3994-162">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="c3994-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="c3994-163">cdm_description (Opis)</span><span class="sxs-lookup"><span data-stu-id="c3994-163">cdm_description (Description)</span></span>  | <span data-ttu-id="c3994-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="c3994-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="c3994-165">Zaktualizowane mapowanie powinno wyglądać jak na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="c3994-165">The updated mappings should look like the following image.</span></span>

![Zadanie Działy na jednostki operacyjne](./media/DepartmentMapping.png)


<span data-ttu-id="c3994-167">Zadanie Prace na szczegóły pracy musi mieć zaktualizowane następujące mapowania.</span><span class="sxs-lookup"><span data-stu-id="c3994-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="c3994-168">Pole istniejącego źródła</span><span class="sxs-lookup"><span data-stu-id="c3994-168">Existing source field</span></span>          | <span data-ttu-id="c3994-169">Pole nowego źródła</span><span class="sxs-lookup"><span data-stu-id="c3994-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="c3994-170">cdm_name (nazwa)</span><span class="sxs-lookup"><span data-stu-id="c3994-170">cdm_name (Name)</span></span>                | <span data-ttu-id="c3994-171">cdm_description (Opis)</span><span class="sxs-lookup"><span data-stu-id="c3994-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="c3994-172">cdm_name (opis)</span><span class="sxs-lookup"><span data-stu-id="c3994-172">cdm_name (Description)</span></span>         | <span data-ttu-id="c3994-173">cdm_jobdescription(opis zadania)</span><span class="sxs-lookup"><span data-stu-id="c3994-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="c3994-174">Zaktualizowane mapowanie powinno wyglądać jak na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="c3994-174">The updated mappings should look like the image below.</span></span>

![Zadanie Praca na szczegóły pracy](./media/JobMapping.png)

<span data-ttu-id="c3994-176">Zadanie Pracownicy na pracownika musi mieć zaktualizowane następujące mapowania.</span><span class="sxs-lookup"><span data-stu-id="c3994-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="c3994-177">Pole istniejącego źródła</span><span class="sxs-lookup"><span data-stu-id="c3994-177">Existing source field</span></span>                 | <span data-ttu-id="c3994-178">Pole nowego źródła</span><span class="sxs-lookup"><span data-stu-id="c3994-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="c3994-179">cdm_emailaddress1 (adres e-mail 1)</span><span class="sxs-lookup"><span data-stu-id="c3994-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="c3994-180">cdm_primaryemailaddress (główny adres e-mail)</span><span class="sxs-lookup"><span data-stu-id="c3994-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="c3994-181">cdm_telephone1 (telefon 1)</span><span class="sxs-lookup"><span data-stu-id="c3994-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="c3994-182">cdm_primarytelephone (główny numer telefonu)</span><span class="sxs-lookup"><span data-stu-id="c3994-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="c3994-183">Przekształcenie pola płci również musi zostać zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c3994-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="c3994-184">Wybierz typ mapy **fn** (funkcja) dla płci i zaktualizuj następujące mapowania wartości.</span><span class="sxs-lookup"><span data-stu-id="c3994-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="c3994-185">Wartość: Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c3994-185">Common Data Service value</span></span>                   | <span data-ttu-id="c3994-186">Wartość: Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c3994-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="c3994-187">75440000</span><span class="sxs-lookup"><span data-stu-id="c3994-187">75440000</span></span>                    | <span data-ttu-id="c3994-188">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="c3994-188">Male</span></span>                                             |
| <span data-ttu-id="c3994-189">75440001</span><span class="sxs-lookup"><span data-stu-id="c3994-189">75440001</span></span>                    | <span data-ttu-id="c3994-190">Kobieta</span><span class="sxs-lookup"><span data-stu-id="c3994-190">Female</span></span>                                           |
| <span data-ttu-id="c3994-191">75440002</span><span class="sxs-lookup"><span data-stu-id="c3994-191">75440002</span></span>                    | <span data-ttu-id="c3994-192">None</span><span class="sxs-lookup"><span data-stu-id="c3994-192">None</span></span>                                             | 
| <span data-ttu-id="c3994-193">75440003</span><span class="sxs-lookup"><span data-stu-id="c3994-193">75440003</span></span>                    | <span data-ttu-id="c3994-194">NonSpecific</span><span class="sxs-lookup"><span data-stu-id="c3994-194">NonSpecific</span></span>                                      |

<span data-ttu-id="c3994-195">Zaktualizowane mapowanie powinno wyglądać jak na poniższych ilustracjach.</span><span class="sxs-lookup"><span data-stu-id="c3994-195">The updated mappings should look like the following images.</span></span>

![Zadanie Pracownicy na pracownika](./media/WorkerMapping.png)

![Przekształcenie pola płci](./media/WorkerTransform.png)
