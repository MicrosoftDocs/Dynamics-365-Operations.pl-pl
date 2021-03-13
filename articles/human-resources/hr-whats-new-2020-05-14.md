---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (14 maja 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 14 maja 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b8d65236d316035722451a871afabedc6ab73f7a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127856"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a><span data-ttu-id="65529-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (14 maja 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="65529-103">What's new or changed in Dynamics 365 Human Resources (May 14, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="65529-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="65529-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="65529-105">Zmiany dotyczą kompilacji o numerze 8.1.3244.</span><span class="sxs-lookup"><span data-stu-id="65529-105">Changes apply to build number 8.1.3244.</span></span> <span data-ttu-id="65529-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="65529-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="65529-107">Zmiany w platformie</span><span class="sxs-lookup"><span data-stu-id="65529-107">Platform changes</span></span>

<span data-ttu-id="65529-108">Zmiany w platformie są uwzględniane w wydaniu z danego tygodnia.</span><span class="sxs-lookup"><span data-stu-id="65529-108">Platform changes are included in this week's release.</span></span> <span data-ttu-id="65529-109">Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.10 aplikacji Finance and Operations (maj 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34).</span><span class="sxs-lookup"><span data-stu-id="65529-109">For more information, see [Platform updates for version 10.0.10 of Finance and Operations apps (May 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34).</span></span> <span data-ttu-id="65529-110">Ta wersja zawiera poprawki usterek i zmiany w zapisanych widokach.</span><span class="sxs-lookup"><span data-stu-id="65529-110">This release includes bug fixes and changes to saved views.</span></span>
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a><span data-ttu-id="65529-111">Upewnij się, że listy wyboru usługi Dataverse są spójne z wyliczeniami nieobecności (436343)</span><span class="sxs-lookup"><span data-stu-id="65529-111">Ensure Dataverse picklists are consistent with Leave enums (436343)</span></span>

<span data-ttu-id="65529-112">Listy wyboru usługi Dataverse są teraz spójne z wyliczeniami nieobecności.</span><span class="sxs-lookup"><span data-stu-id="65529-112">Dataverse picklists are now consistent with Leave enums.</span></span>

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a><span data-ttu-id="65529-113">Umożliwienie użytkownikom konfigurowania przepływu pracy wniosku o urlop na podstawie ilości żądania (300044)</span><span class="sxs-lookup"><span data-stu-id="65529-113">Allow users to configure leave request workflow based on the request amount (300044)</span></span>

<span data-ttu-id="65529-114">Użytkownicy mogą konfigurować przepływy pracy wniosku o urlop na podstawie ilości żądania.</span><span class="sxs-lookup"><span data-stu-id="65529-114">Users can configure leave requests workflows based on request amounts.</span></span>
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a><span data-ttu-id="65529-115">Nowy formularz pracownika ujawniane dane za pomocą menu widoku po włączeniu zabezpieczeń zaawansowanych (403185)</span><span class="sxs-lookup"><span data-stu-id="65529-115">New worker form exposes data through the View menu when advanced security is enabled (403185)</span></span>

<span data-ttu-id="65529-116">Ta wersja koryguje sposób, w jaki pracownicy w różnych firmach będą działać w przypadku, gdy jest włączony zaawansowany dostęp, a pracownicy w innych firmach są dostępni.</span><span class="sxs-lookup"><span data-stu-id="65529-116">This release corrects how viewing workers across legal entities functions when advanced access is enabled and workers in other companies are accessible.</span></span>

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a><span data-ttu-id="65529-117">Zezwalanie na uruchamianie naliczania urlopu dla pojedynczego planu lub pojedynczej firmy (318844)</span><span class="sxs-lookup"><span data-stu-id="65529-117">Allow running leave accruals for a single plan or a single company (318844)</span></span>

<span data-ttu-id="65529-118">Dzięki tej zmianie można uruchamiać naliczenia dla firmy lub planu.</span><span class="sxs-lookup"><span data-stu-id="65529-118">With this change, you can run accruals for a company or a plan.</span></span>
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a><span data-ttu-id="65529-119">Wyświetlanie ekwiwalent pełnego wymiaru czasu pozycji (FTE) w formularzu zarejestrowanych pracowników (414658)</span><span class="sxs-lookup"><span data-stu-id="65529-119">Show the position's full-time equivalent (FTE) in the Enrolled workers form (414658)</span></span>

<span data-ttu-id="65529-120">Wartość pełnego etatu pozycji pracownika określa stawkę naliczania dla pracownika, jeśli dla typu urlopu jest włączona opcja FTE.</span><span class="sxs-lookup"><span data-stu-id="65529-120">The FTE value from a worker's position determines a worker's accrual rate when the FTE option is enabled on the leave type.</span></span> <span data-ttu-id="65529-121">To pole jest teraz uwzględniane w formularzu **zarejestrowanych pracowników** i w oknie dialogowym **rejestracji grupowej**.</span><span class="sxs-lookup"><span data-stu-id="65529-121">This field is now included in **Enrolled workers** form and the **Mass enrollment** dialog.</span></span>

## <a name="add-leave-balance-expiration-batch-job-431266"></a><span data-ttu-id="65529-122">Dodawania zadania wsadowego wygasania sald urlopu (431266)</span><span class="sxs-lookup"><span data-stu-id="65529-122">Add leave balance expiration batch job (431266)</span></span>

<span data-ttu-id="65529-123">Jest teraz dostępne nowe zadanie wsadowe, które będzie uruchamiane codziennie.</span><span class="sxs-lookup"><span data-stu-id="65529-123">A new batch job is now available that runs daily.</span></span> <span data-ttu-id="65529-124">Pozostałe saldo urlopu jest zmniejszane, jeśli daty ważności stają się aktualne.</span><span class="sxs-lookup"><span data-stu-id="65529-124">It decreases the remaining leave balance when expiration dates become current.</span></span>

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a><span data-ttu-id="65529-125">Eksportowanie osobistych osób kontaktowych pracownika za pomocą jednostki osobistej osoby kontaktowej pracownika nie powoduje eksportowania osobistych osób kontaktowych z nadrzędnym typem relacji (345893)</span><span class="sxs-lookup"><span data-stu-id="65529-125">Exporting personal contacts for an employee using the Worker personal contact person entity doesn't export personal contacts with the Parent relationship type (345893)</span></span>

<span data-ttu-id="65529-126">Jednostka danych **Osobista osoba kontaktowa pracownika** (**HcmPersonalContactPersonEntity** w DMF i **PersonalContactPerson** w OData) nie mogła wyeksportować osobistych osób kontaktowych, które mają typ relacji **Nadrzędna**.</span><span class="sxs-lookup"><span data-stu-id="65529-126">The **Worker personal contact person** data entity (**HcmPersonalContactPersonEntity** in DMF and **PersonalContactPerson** in OData) couldn't export personal contacts that have a relationship type of **Parent**.</span></span> <span data-ttu-id="65529-127">Ten problem został rozwiązany dla osobistych osób kontaktowych utworzonych po tej zmianie.</span><span class="sxs-lookup"><span data-stu-id="65529-127">This issue is fixed for personal contacts that are created after this change.</span></span> <span data-ttu-id="65529-128">Problem w przypadku osobistych osób kontaktowych typu **Nadrzędna** zostanie rozwiązany w późniejszej wersji.</span><span class="sxs-lookup"><span data-stu-id="65529-128">Existing personal contacts of type **Parent** will be fixed in a later release.</span></span>

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a><span data-ttu-id="65529-129">Kody przyczyn są wyświetlane w różnych scenariuszach, gdy są oznaczone jako Urlop i nieobecność, a udoskonalony formularz pracownika jest włączony (434163)</span><span class="sxs-lookup"><span data-stu-id="65529-129">Reason codes display across different scenarios when they're marked as Leave and absence and the streamlined employee form is enabled (434163)</span></span>

<span data-ttu-id="65529-130">Ta zmiana ogranicza kody przyczyn tylko do kodów urlopów i nieobecności po włączeniu udoskonalonego wpisu pracownika.</span><span class="sxs-lookup"><span data-stu-id="65529-130">This change restricts the reason codes to only Leave and absence codes when you enable streamlined employee entry.</span></span>

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a><span data-ttu-id="65529-131">Funkcja podglądu Przypisywanie plan urlopu do pracowników w przyszłości powoduje wyświetlanie błędu (433555)</span><span class="sxs-lookup"><span data-stu-id="65529-131">The preview feature Assign a leave plan to employees in the future displays error (433555)</span></span>

<span data-ttu-id="65529-132">Ta zmiana naprawia błąd występujący w przypadku, gdy do planu urlopu przypisano dwa typy urlopów i podjęto próbę przypisania pracownika.</span><span class="sxs-lookup"><span data-stu-id="65529-132">This change corrects an error when a leave plan has two leave types assigned and you attempt to assign an employee.</span></span>

## <a name="getting-started-banner-appears-for-all-users-441731"></a><span data-ttu-id="65529-133">Transparent wprowadzający jest widoczny dla wszystkich użytkowników (441731)</span><span class="sxs-lookup"><span data-stu-id="65529-133">Getting started banner appears for all users (441731)</span></span>

<span data-ttu-id="65529-134">W przypadku tej zmiany transparent wprowadzający jest ukryty dla użytkowników, którzy nie są administratorami systemu ani administratorami zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="65529-134">With this change, the Getting started banner is hidden for users that aren't System administrators or Data management administrators.</span></span> 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a><span data-ttu-id="65529-135">Jednostka adresu pracownika Dataverse działa inaczej w zależności od daty i godziny dla czasu obowiązywania dat w aplikacji Human Resources (425071)</span><span class="sxs-lookup"><span data-stu-id="65529-135">The Dataverse Worker Address entity works differently in terms of date time effective dates in Human Resources (425071)</span></span>

<span data-ttu-id="65529-136">Ta zmiana powoduje, że informacje adresowe są wyrównywane w określonych scenariuszach na podstawie dat adresu.</span><span class="sxs-lookup"><span data-stu-id="65529-136">This change keeps address information aligned in certain scenarios, based on the dates of the address.</span></span>

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a><span data-ttu-id="65529-137">Nie można dodać załącznika do zatwierdzonego wniosku o urlop (425407)</span><span class="sxs-lookup"><span data-stu-id="65529-137">Unable to add an attachment to an approved leave request (425407)</span></span>

<span data-ttu-id="65529-138">Od wersji z tego tygodnia można dodawać załączniki do zatwierdzonych wniosków o urlop bez zmiany wniosku o urlop.</span><span class="sxs-lookup"><span data-stu-id="65529-138">With this week's release, you can add attachments to approved leave requests without changing the leave request.</span></span>

## <a name="in-preview"></a><span data-ttu-id="65529-139">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="65529-139">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="65529-140">Zawieszenie urlopu</span><span class="sxs-lookup"><span data-stu-id="65529-140">Leave suspension</span></span>

<span data-ttu-id="65529-141">Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="65529-141">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="65529-142">Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="65529-142">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="65529-143">Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika.</span><span class="sxs-lookup"><span data-stu-id="65529-143">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="65529-144">Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="65529-144">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="65529-145">Zaktualizowano środowisko użytkownika, aby umożliwić wskazanie, że naliczanie zostało zawieszone (429550)</span><span class="sxs-lookup"><span data-stu-id="65529-145">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="65529-146">Środowisko użytkownika wskazuje teraz, że naliczanie dla planu zostało zawieszone.</span><span class="sxs-lookup"><span data-stu-id="65529-146">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="65529-147">Wstrzymanie naliczania urlopu dla określonych typów urlopów (272447)</span><span class="sxs-lookup"><span data-stu-id="65529-147">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="65529-148">W tym wydaniu dział zasobów ludzkich może utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="65529-148">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="65529-149">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="65529-149">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="65529-150">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="65529-150">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="65529-151">Jednostka DMF dostępna dla wstrzymań naliczania (429549)</span><span class="sxs-lookup"><span data-stu-id="65529-151">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="65529-152">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="65529-152">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="65529-153">Dodano kod przyczyny do wstrzymań naliczania (429547)</span><span class="sxs-lookup"><span data-stu-id="65529-153">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="65529-154">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="65529-154">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="65529-155">Rozpoczęto przejście od parametrów zasobów ludzkich do parametrów urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="65529-155">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="65529-156">W tym wydaniu rozpoczęto łączenie parametrów zasobów ludzkich z parametrami urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="65529-156">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="65529-157">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="65529-157">Carry forward rules</span></span>

<span data-ttu-id="65529-158">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="65529-158">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="65529-159">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="65529-159">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="65529-160">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="65529-160">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65529-161">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="65529-161">See also</span></span>

[<span data-ttu-id="65529-162">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="65529-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="65529-163">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="65529-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="65529-164">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="65529-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="65529-165">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="65529-165">Manage features</span></span>](hr-admin-manage-features.md)