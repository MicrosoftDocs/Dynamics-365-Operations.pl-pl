---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (03 września 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 3 września 2020 roku.
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 10978d8843e7bce2800d62b63e58152569be9631
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891776"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a><span data-ttu-id="4974f-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (3 września 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="4974f-103">What's new or changed in Dynamics 365 Human Resources (September 3, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="4974f-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4974f-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="4974f-105">Zmiany dotyczą kompilacji o numerze 8.1.3504.</span><span class="sxs-lookup"><span data-stu-id="4974f-105">Changes apply to build number 8.1.3504.</span></span> <span data-ttu-id="4974f-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4974f-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

<span data-ttu-id="4974f-107">Aby uzyskać więcej informacji o nadchodzących funkcjach w module Human Resources, zapoznaj się [z omówieniem Dynamics 365 Human Resources 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).</span><span class="sxs-lookup"><span data-stu-id="4974f-107">For more information about upcoming features in Human Resources, see [Overview of Dynamics 365 Human Resources 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).</span></span> <span data-ttu-id="4974f-108">Aby uzyskać więcej informacji na temat procesu aktualizacji dla modułu Human Resources, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="4974f-108">For more information about the update process for Human Resources, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="in-this-release"></a><span data-ttu-id="4974f-109">W tej wersji</span><span class="sxs-lookup"><span data-stu-id="4974f-109">In this release</span></span>

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a><span data-ttu-id="4974f-110">Nowa siatka i wzorzec okna dialogowego dla wymiarów finansowych są ustawiane w całym module Human Resources (469495)</span><span class="sxs-lookup"><span data-stu-id="4974f-110">New default financial dimensions grid and dialog pattern throughout Human Resources (469495)</span></span>

<span data-ttu-id="4974f-111">Nowy wzorzec wymiarów finansowych jest teraz dostępny w następujących obszarach:</span><span class="sxs-lookup"><span data-stu-id="4974f-111">The new pattern for financial dimensions is now available in the following areas:</span></span>

- <span data-ttu-id="4974f-112">Akcje dotyczące stanowisk (formularz: **HcmPositionActionDetail**)</span><span class="sxs-lookup"><span data-stu-id="4974f-112">Position actions  (Form: **HcmPositionActionDetail**)</span></span>
- <span data-ttu-id="4974f-113">Kody zarobków dla listy płac (formularz: **PayrollEarningCode**)</span><span class="sxs-lookup"><span data-stu-id="4974f-113">Payroll earning codes  (Form: **PayrollEarningCode**)</span></span>

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a><span data-ttu-id="4974f-114">Wpisy nie pojawiają się w kalendarzu wystawiania w firmie, jeśli nie są włączone rozszerzenia kalendarza urlopu i nieobecności (484406)</span><span class="sxs-lookup"><span data-stu-id="4974f-114">Entries don't appear in company leave calendar if Leave and absence calendar enhancements aren't enabled (484406)</span></span>

<span data-ttu-id="4974f-115">Ta wersja dotyczy rozwiązania problemów, w przypadku których wpisy urlopowe nie są wyświetlane w kalendarzu urlopów firmy.</span><span class="sxs-lookup"><span data-stu-id="4974f-115">This release corrects an issue where leave entries aren't displayed in the company leave calendar.</span></span> <span data-ttu-id="4974f-116">Ten problem występuje tylko wtedy, gdy opcja zarządzania funkcjami **Ulepszenia kalendarza nieobecności i urlopów** nie jest włączona.</span><span class="sxs-lookup"><span data-stu-id="4974f-116">This issue only occurs when the Feature management option **Leave and absence calendar enhancements** isn't enabled.</span></span>

### <a name="benefitplanemployeeentity-issue-467597"></a><span data-ttu-id="4974f-117">Problem z BenefitPlanEmployeeEntity (467597)</span><span class="sxs-lookup"><span data-stu-id="4974f-117">BenefitPlanEmployeeEntity issue (467597)</span></span>

<span data-ttu-id="4974f-118">Ta wersja koryguje problem dotyczący encji **BenefitsPlanEmployee**.</span><span class="sxs-lookup"><span data-stu-id="4974f-118">This release corrects an issue with the **BenefitsPlanEmployee** entity.</span></span> <span data-ttu-id="4974f-119">Podczas importowania rejestracji pracowników **Kod objęcia świadczeniem** i **Kod typu planu** są ustawiane poprawnie.</span><span class="sxs-lookup"><span data-stu-id="4974f-119">When importing worker enrollments, the **Coverage code** and the **Plan type code** are now set correctly.</span></span> <span data-ttu-id="4974f-120">Ten błąd powodował, że plany świadczeń pracowniczych były wyświetlane niepoprawnie w formularzach **Plan świadczeń pracownika** i **Otwarcie rejestracji** w module samoobsługowym pracownika.</span><span class="sxs-lookup"><span data-stu-id="4974f-120">This issue caused employee benefit plans to display incorrectly in the **Worker benefits plan** and **Open enrollment** forms in Employee self service.</span></span>

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a><span data-ttu-id="4974f-121">Plik elektroniczny 1094-C — brakuje litery w XML (435190)</span><span class="sxs-lookup"><span data-stu-id="4974f-121">Electronic file 1094-C output missing letter in XML (435190)</span></span>

<span data-ttu-id="4974f-122">Ta zmiana polega na usunięciu problemu dotyczącego pliku wyjściowego 1094-C — brak znaku wymaganego podczas przesyłania do urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="4974f-122">This change corrects an issue with the 1094-C output file missing a character needed when submitting to the IRS.</span></span>

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a><span data-ttu-id="4974f-123">Tabela wynagrodzeń pracownika o zmiennej wysokości mapowana na formę stałego wynagrodzenia (476117)</span><span class="sxs-lookup"><span data-stu-id="4974f-123">Employee variable compensation table mapped to fixed compensation form (476117)</span></span>

<span data-ttu-id="4974f-124">Ta zmiana powoduje wyrównanie pól stałych wynagrodzeń za pomocą formularza stałego wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="4974f-124">This change aligns the fixed compensation fields with the fixed compensation form.</span></span> <span data-ttu-id="4974f-125">Pola wynagrodzeń o zmiennej wysokości są teraz dostępne tylko w formularzu wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="4974f-125">Variable compensation fields are now only available with the variable compensation form.</span></span>

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a><span data-ttu-id="4974f-126">Prośby o urlop były możliwe przed rejestracją, jeśli typ urlopu zawierał ujemne saldo minimalne (469917)</span><span class="sxs-lookup"><span data-stu-id="4974f-126">Leave requests allowed before enrollment if that leave type has a negative minimum balance (469917)</span></span>

<span data-ttu-id="4974f-127">Ta zmiana uniemożliwia wprowadzanie żądań urlopu przed zarejestrowaniem w planie, nawet jeśli rejestracja ma ujemne salda minimalne.</span><span class="sxs-lookup"><span data-stu-id="4974f-127">This change prohibits entering leave requests before being enrolled in the plan, even if the enrollment has a negative minimum balance.</span></span> <span data-ttu-id="4974f-128">Można wprowadzać i przesyłać tylko żądania, gdy plan jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="4974f-128">You can only enter or submit requests when the plan is active.</span></span>

### <a name="document-templates-dont-download-457279"></a><span data-ttu-id="4974f-129">Szablony dokumentów nie pobierają się (457279)</span><span class="sxs-lookup"><span data-stu-id="4974f-129">Document templates don't download (457279)</span></span>

<span data-ttu-id="4974f-130">Można teraz pobrać wszystkie szablony dokumentów.</span><span class="sxs-lookup"><span data-stu-id="4974f-130">With this change, you can now download all document templates.</span></span> 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a><span data-ttu-id="4974f-131">Dane są wyświetlane jako nagłówki kolumn zamiast wierszy w polu stawka płacy w raporcie planu wynagrodzeń (476077)</span><span class="sxs-lookup"><span data-stu-id="4974f-131">Data displays as column headers instead of rows for the Pay rate field in the compensation plan report (476077)</span></span>

<span data-ttu-id="4974f-132">W raporcie analizy są teraz wyświetlane poprawne informacje o **Stawce wynagrodzenia**.</span><span class="sxs-lookup"><span data-stu-id="4974f-132">The analytics report now displays the correct information for **Pay rate**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="4974f-133">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="4974f-133">In preview</span></span>

### <a name="human-resources-application-in-teams"></a><span data-ttu-id="4974f-134">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="4974f-134">Human Resources application in Teams</span></span>

<span data-ttu-id="4974f-135">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4974f-135">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="4974f-136">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="4974f-136">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="4974f-137">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="4974f-137">For more information, see:</span></span>

- <span data-ttu-id="4974f-138">[Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 1</span><span class="sxs-lookup"><span data-stu-id="4974f-138">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- <span data-ttu-id="4974f-139">[Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md) w dokumentacji dot. Human Resources</span><span class="sxs-lookup"><span data-stu-id="4974f-139">[Human Resources app in Teams](./hr-admin-teams-leave-app.md) in Human Resources documentation</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="4974f-140">Aplikacja Human Resources w Teams — funkcje w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="4974f-140">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="4974f-141">**Powiadomienia**: osoby przesyłające i osoby zatwierdzające żądania czasu wolnego będą powiadamiane w aplikacji Human Resources w Teams.</span><span class="sxs-lookup"><span data-stu-id="4974f-141">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="4974f-142">Osoby zatwierdzające będą mogły zatwierdzać i odmawiać żądania czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="4974f-142">Approvers will be able to approve or deny time-off requests.</span></span> <span data-ttu-id="4974f-143">Osoby przesyłające będą powiadamiane o zaakceptowaniu lub odrzuceniu żądania.</span><span class="sxs-lookup"><span data-stu-id="4974f-143">Submitters will be notified if the request was approved or denied.</span></span> <span data-ttu-id="4974f-144">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="4974f-144">For more information, see:</span></span>
   - <span data-ttu-id="4974f-145">[Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 2</span><span class="sxs-lookup"><span data-stu-id="4974f-145">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="4974f-146">[Uruchom powiadomienia dla aplikacji Human Resources w Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) w dokumentacji dot. Human Resources</span><span class="sxs-lookup"><span data-stu-id="4974f-146">[Enable notifications for the Human Resources app in Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) in Human Resources documentation</span></span>
   - <span data-ttu-id="4974f-147">[Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) w dokumentacji dot. Human Resources</span><span class="sxs-lookup"><span data-stu-id="4974f-147">[Turn Teams notifications on or off for individual users](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) in Human Resources documentation</span></span>
   - <span data-ttu-id="4974f-148">[Powiadomienia Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) w dokumentacji dot. Human Resorces</span><span class="sxs-lookup"><span data-stu-id="4974f-148">[Teams notifications](./hr-teams-leave-app.md#respond-to-teams-notifications) in Human Resources documentation</span></span>
   - <span data-ttu-id="4974f-149">[Wyświetlanie kalendarza urlopu zespołu](./hr-teams-leave-app.md#view-your-teams-leave-calendar) w dokumentacji dot. Human Resorces</span><span class="sxs-lookup"><span data-stu-id="4974f-149">[View your team's leave calendar](./hr-teams-leave-app.md#view-your-teams-leave-calendar) in Human Resources documentation</span></span>
 
- <span data-ttu-id="4974f-150">**Kalendarz czasu wolnego kierownika**: Kierownicy będą mogli zobaczyć zatwierdzone i oczekujące prośby o czas wolny dla bezpośrednio podległych pracowników w widoku kalendarza.</span><span class="sxs-lookup"><span data-stu-id="4974f-150">**Manager time-off calendar**: Managers will be able to see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="4974f-151">Ten widok umożliwia w łatwy sposób sprawdzić, kiedy członkowie zespołu mają czas wolny.</span><span class="sxs-lookup"><span data-stu-id="4974f-151">This view provides an easy understanding of when their team members are away from work.</span></span> <span data-ttu-id="4974f-152">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="4974f-152">For more information, see:</span></span>
   - <span data-ttu-id="4974f-153">[Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 2</span><span class="sxs-lookup"><span data-stu-id="4974f-153">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="4974f-154">[Wyświetlanie kalendarza urlopu zespołu](./hr-teams-leave-app.md#view-your-teams-leave-calendar) w dokumentacji dot. Human Resorces</span><span class="sxs-lookup"><span data-stu-id="4974f-154">[View your team's leave calendar](./hr-teams-leave-app.md#view-your-teams-leave-calendar) in Human Resources documentation</span></span>

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a><span data-ttu-id="4974f-155">Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych (477004)</span><span class="sxs-lookup"><span data-stu-id="4974f-155">Configuration option to position Work items assigned to me list (477004)</span></span>

<span data-ttu-id="4974f-156">Nowa opcja jest teraz dostępna w celu umieszczenia **Elementów pracy przypisanych do mnie** w prawej kolumnie pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="4974f-156">A new option is now available to position the **Work items assigned to me** list in the right-hand column of the dashboard.</span></span> <span data-ttu-id="4974f-157">W przypadku zmiany wszystkie elementy pracy i listy zadań do wykonania są wyświetlane w tym samym obszarze.</span><span class="sxs-lookup"><span data-stu-id="4974f-157">With this change, all work items and to do lists display in the same area.</span></span> <span data-ttu-id="4974f-158">Włącz tę funkcję, włączając **Podgląd — udoskonalenia środowiska przepływu pracy** w module Zarządzanie funkcjami.</span><span class="sxs-lookup"><span data-stu-id="4974f-158">Enable this functionality by turning on **Preview - Workflow experience enhancements** in Feature management.</span></span> <span data-ttu-id="4974f-159">Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="4974f-159">For more information about turning on preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

<span data-ttu-id="4974f-160">Ta funkcja promuje także opcje przepływu pracy, które znajdują się w formularzach akcji dotyczących pracowników.</span><span class="sxs-lookup"><span data-stu-id="4974f-160">This feature also promotes the workflow options that appear in the personnel actions forms.</span></span> <span data-ttu-id="4974f-161">Opcje przepływu pracy są również wyświetlane powyżej karty działania w ramach szybkiego dostępu.</span><span class="sxs-lookup"><span data-stu-id="4974f-161">Workflow options also appear above the action fast tab for quick access.</span></span> <span data-ttu-id="4974f-162">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="4974f-162">For more information, see:</span></span> 

- <span data-ttu-id="4974f-163">[Udoskonalenia środowiska przepływu pracy — zarządzanie organizacją i pracownikami](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) w planie wydawniczym Dynamics 365 2020 wave 2</span><span class="sxs-lookup"><span data-stu-id="4974f-163">[Organization and personnel management workflow experience enhancements](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) in the Dynamics 365 2020 release wave 2 plan</span></span>

![Elementy pracy przypisane do mnie](./media/hr-workflow-work-items-assigned-to-me.png)

![Szybki dostęp do elementów przepływu pracy](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a><span data-ttu-id="4974f-166">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="4974f-166">Coming Soon</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="4974f-167">Jednostki listy kontrolnej uwzględnione w Dataverse</span><span class="sxs-lookup"><span data-stu-id="4974f-167">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="4974f-168">Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4974f-168">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

### <a name="benefits-management-reason-codes"></a><span data-ttu-id="4974f-169">Kody przyczyn zarządzania korzyściami</span><span class="sxs-lookup"><span data-stu-id="4974f-169">Benefits management reason codes</span></span>

<span data-ttu-id="4974f-170">Kody przyczyn zarządzania korzyściami zostaną wkrótce połączone z istniejącymi kodami przyczyn w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4974f-170">Benefits management reason codes will soon be combined with existing reason codes in Human Resources.</span></span> <span data-ttu-id="4974f-171">Jeśli kody przyczyn zostały utworzone w ramach zarządzania świadczeniami o długości przekraczającej 15 znaków, należy zmienić nazwę kodu przyczyny w formularzu **Kody przyczyn** na nazwę zawierającą 15 lub mniej znaków.</span><span class="sxs-lookup"><span data-stu-id="4974f-171">If you created reason codes in Benefits management that are over 15 characters, you must change the name of the reason code in the Benefits management **Reason codes** form to be 15 characters or less.</span></span> <span data-ttu-id="4974f-172">Po zaktualizowaniu nazwy kod przyczyny pojawi się pod istniejącym formularzem w module Zarządzanie kadrami.</span><span class="sxs-lookup"><span data-stu-id="4974f-172">After you update the name, the reason code will appear under the existing reason code form in Personnel management.</span></span> <span data-ttu-id="4974f-173">Ta zmiana będzie dostępna w przyszłości i nie będzie miała wpływu na istniejącą funkcję.</span><span class="sxs-lookup"><span data-stu-id="4974f-173">This change will be available in the future and won't affect existing functionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="4974f-174">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4974f-174">See also</span></span>

[<span data-ttu-id="4974f-175">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="4974f-175">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="4974f-176">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="4974f-176">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="4974f-177">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="4974f-177">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="4974f-178">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="4974f-178">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
