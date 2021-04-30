---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (1 maja 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 1 maja 2020 roku.
author: andreabichsel
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d1c97d0e332cb81391ec3095fcb5d4d42a0d6bff
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891992"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a><span data-ttu-id="ef632-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (1 maja 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="ef632-103">What's new or changed in Dynamics 365 Human Resources (May 1, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ef632-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ef632-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ef632-105">Zmiany dotyczą kompilacji o numerze 8.1.3196.</span><span class="sxs-lookup"><span data-stu-id="ef632-105">Changes apply to build number 8.1.3196.</span></span> <span data-ttu-id="ef632-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="ef632-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a><span data-ttu-id="ef632-107">Nowe jednostki zarządzania wydajnością dostępne w strukturze DMF (Data Management Framework)</span><span class="sxs-lookup"><span data-stu-id="ef632-107">New Performance Management entities available in Data Management Framework (DMF)</span></span>

<span data-ttu-id="ef632-108">Dostępne są teraz nowe jednostki.</span><span class="sxs-lookup"><span data-stu-id="ef632-108">The following entities are now available.</span></span> <span data-ttu-id="ef632-109">Jeśli te jednostki nie są widoczne na liście jednostek, należy skorzystać z opcji **Odśwież jednostki** w **Parametry struktury > Ustawienia jednostki > Odśwież listę jednostek**.</span><span class="sxs-lookup"><span data-stu-id="ef632-109">If you don't see these entities listed in the entities list, use the **Refresh entities** option in **Framework Parameters > Entity settings > Refresh entity list**.</span></span>

- <span data-ttu-id="ef632-110">**Kompetencje dotyczące dyskusji**</span><span class="sxs-lookup"><span data-stu-id="ef632-110">**Discussion Competency**</span></span>
- <span data-ttu-id="ef632-111">**Cele dyskusji**</span><span class="sxs-lookup"><span data-stu-id="ef632-111">**Discussion Goals**</span></span>
- <span data-ttu-id="ef632-112">**Miara dyskusji**</span><span class="sxs-lookup"><span data-stu-id="ef632-112">**Discussion Measurement**</span></span>
- <span data-ttu-id="ef632-113">**Temat dyskusji**</span><span class="sxs-lookup"><span data-stu-id="ef632-113">**Discussion Topic**</span></span>
- <span data-ttu-id="ef632-114">**Arkusz wydajności**</span><span class="sxs-lookup"><span data-stu-id="ef632-114">**Performance Journal**</span></span>
- <span data-ttu-id="ef632-115">**Miara**</span><span class="sxs-lookup"><span data-stu-id="ef632-115">**Measurement**</span></span>
- <span data-ttu-id="ef632-116">**Miara celu**</span><span class="sxs-lookup"><span data-stu-id="ef632-116">**Goal Measurement**</span></span>

<span data-ttu-id="ef632-117">Ponadto dodano elementy **Łączny wynik** i **Średni wynik** do jednostki **Dyskusja**.</span><span class="sxs-lookup"><span data-stu-id="ef632-117">In addition, **Total score** and **Average score** were added to the **Discussion** entity.</span></span>

## <a name="increase-length-of-leave-request-comments-275641"></a><span data-ttu-id="ef632-118">Zwiększona długość komentarzy do wniosku o urlop (275641)</span><span class="sxs-lookup"><span data-stu-id="ef632-118">Increase length of leave request comments (275641)</span></span>

<span data-ttu-id="ef632-119">Komentarze we wnioskach o urlop mogą teraz zawierać więcej niż 100 znaków.</span><span class="sxs-lookup"><span data-stu-id="ef632-119">Comments on leave requests now allow more than 100 characters.</span></span>

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a><span data-ttu-id="ef632-120">Ostateczne komentarze dotyczące recenzji nie są wyświetlane, gdy kierownik lub pracownik etatowy są zalogowani do innej firmy (431688)</span><span class="sxs-lookup"><span data-stu-id="ef632-120">Final comments on reviews don't appear when the manager or employee is signed into a different company (431688)</span></span>

<span data-ttu-id="ef632-121">Wszystkie komentarze będą teraz widoczne podczas przeglądania recenzji.</span><span class="sxs-lookup"><span data-stu-id="ef632-121">All comments will now appear when viewing reviews.</span></span>

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a><span data-ttu-id="ef632-122">Linki zdefiniowane przez użytkownika nie są obsługiwane w formularzu nowego pracownika (390374)</span><span class="sxs-lookup"><span data-stu-id="ef632-122">User-defined links aren't supported on new Worker form (390374)</span></span>

<span data-ttu-id="ef632-123">Linki zdefiniowane przez użytkownika są teraz włączone w udoskonalonym formularzu **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="ef632-123">User-defined links are now enabled on the streamlined **Worker** form.</span></span>

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a><span data-ttu-id="ef632-124">Jednostka HcmRatingLevelEntity powoduje awarię interfejsu API OData (439476)</span><span class="sxs-lookup"><span data-stu-id="ef632-124">HcmRatingLevelEntity causes OData API crash (439476)</span></span>

<span data-ttu-id="ef632-125">Ta zmiana powoduje usunięcie awarii interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="ef632-125">This change corrects the API crash.</span></span> <span data-ttu-id="ef632-126">Ten błąd powoduje zduplikowana nazwa.</span><span class="sxs-lookup"><span data-stu-id="ef632-126">A duplicate name cased this error.</span></span>

## <a name="in-preview"></a><span data-ttu-id="ef632-127">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="ef632-127">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="ef632-128">Zawieszenie urlopu</span><span class="sxs-lookup"><span data-stu-id="ef632-128">Leave suspension</span></span>

<span data-ttu-id="ef632-129">Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="ef632-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="ef632-130">Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="ef632-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="ef632-131">Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika.</span><span class="sxs-lookup"><span data-stu-id="ef632-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="ef632-132">Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="ef632-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="ef632-133">Zaktualizowano środowisko użytkownika, aby umożliwić wskazanie, że naliczanie zostało zawieszone (429550)</span><span class="sxs-lookup"><span data-stu-id="ef632-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="ef632-134">Środowisko użytkownika wskazuje teraz, że naliczanie dla planu zostało zawieszone.</span><span class="sxs-lookup"><span data-stu-id="ef632-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="ef632-135">Wstrzymanie naliczania urlopu dla określonych typów urlopów (272447)</span><span class="sxs-lookup"><span data-stu-id="ef632-135">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="ef632-136">W tym wydaniu dział zasobów ludzkich może utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="ef632-136">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="ef632-137">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="ef632-137">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="ef632-138">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="ef632-138">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="ef632-139">Jednostka DMF dostępna dla wstrzymań naliczania (429549)</span><span class="sxs-lookup"><span data-stu-id="ef632-139">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="ef632-140">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="ef632-140">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="ef632-141">Dodano kod przyczyny do wstrzymań naliczania (429547)</span><span class="sxs-lookup"><span data-stu-id="ef632-141">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="ef632-142">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="ef632-142">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="ef632-143">Rozpoczęto przejście od parametrów zasobów ludzkich do parametrów urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="ef632-143">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="ef632-144">W tym wydaniu rozpoczęto łączenie parametrów zasobów ludzkich z parametrami urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="ef632-144">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="ef632-145">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="ef632-145">Carry forward rules</span></span>

<span data-ttu-id="ef632-146">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="ef632-146">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="ef632-147">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="ef632-147">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="ef632-148">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="ef632-148">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="ef632-149">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="ef632-149">Known issues</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="ef632-150">Podgląd SharePoint nie działa w niektórych środowiskach</span><span class="sxs-lookup"><span data-stu-id="ef632-150">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="ef632-151">Jeśli Podgląd dokumentów przechowywanych w SharePoint nie działa, spróbuj wykonać poniższą procedurę:</span><span class="sxs-lookup"><span data-stu-id="ef632-151">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="ef632-152">Sprawdź, czy konto użytkownika administratora zawiera wiadomość e-mail skojarzoną z rekordem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ef632-152">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="ef632-153">Można przejrzeć te informacje na stronie **Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="ef632-153">You can view this information in the **User** page.</span></span> <span data-ttu-id="ef632-154">Jeśli poczta e-mail nie jest skonfigurowana, należy dodać wiadomość e-mail i dostawcę za pomocą dodatku OData dla programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef632-154">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="ef632-155">Domyślnie adres e-mail nie jest obecny w projekcie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef632-155">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="ef632-156">Musisz edytować projekt programu Excel, dodać wszystkie pola, zastosować je i odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="ef632-156">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="ef632-157">Po wykonaniu tych kroków można zaktualizować konto administratora.</span><span class="sxs-lookup"><span data-stu-id="ef632-157">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="ef632-158">Gdy konto Administratora ma skojarzone konto e-mail, zaloguj się do modułu Human Resources z poświadczeniami administratora.</span><span class="sxs-lookup"><span data-stu-id="ef632-158">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="ef632-159">Aby uruchomić podgląd dokumentu, uzyskaj dostęp do załącznika SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef632-159">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="ef632-160">Zaloguj się przy użyciu konta innego użytkownika, które ma dostęp do załączników i sprawdź, czy podgląd działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="ef632-160">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef632-161">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ef632-161">See also</span></span>

[<span data-ttu-id="ef632-162">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="ef632-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="ef632-163">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="ef632-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="ef632-164">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="ef632-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="ef632-165">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="ef632-165">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]