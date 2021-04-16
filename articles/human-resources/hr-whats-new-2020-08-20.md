---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (20 sierpnia 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 20 sierpnia 2020 roku.
author: andreabichsel
ms.date: 08/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 69304cbffafa4c20dbbbb31d5c19920f669761b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800172"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a><span data-ttu-id="1bd04-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (20 sierpnia 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="1bd04-103">What's new or changed in Dynamics 365 Human Resources (August 20, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1bd04-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1bd04-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1bd04-105">Zmiany dotyczą kompilacji o numerze 8.1.3478.</span><span class="sxs-lookup"><span data-stu-id="1bd04-105">Changes apply to build number 8.1.3478.</span></span> <span data-ttu-id="1bd04-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="1bd04-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a><span data-ttu-id="1bd04-107">Umożliwia wyświetlenie kart informacji dotyczących nadchodzącego i oczekującego urlopu w obszarze roboczym Osoby</span><span class="sxs-lookup"><span data-stu-id="1bd04-107">Show upcoming and pending leave of absence information to cards in People workspace</span></span>

<span data-ttu-id="1bd04-108">Opcje nadchodzącego i oczekującego urlopu są dostępne na kartach urlop i nieobecność w obszarze roboczym **Osoby**.</span><span class="sxs-lookup"><span data-stu-id="1bd04-108">Pending and upcoming leave request options are now available on the Leave and absence cards in the **People** workspace.</span></span>

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a><span data-ttu-id="1bd04-109">Pole prywatne nie jest ustawione domyślnie na „tak” w przypadku roli pracownika w samoobsłudze pracownika (477106)</span><span class="sxs-lookup"><span data-stu-id="1bd04-109">Private field isn't Yes by default for Employee role in Employee self service (477106)</span></span>

<span data-ttu-id="1bd04-110">Pole **Prywatne** jest domyślnie ustawione na wartość **Tak**, gdy pracownicy dodają nowe rekordy adresów za pomocą strony **Informacje osobiste** w samoobsłudze pracowników.</span><span class="sxs-lookup"><span data-stu-id="1bd04-110">The **Private** field now defaults to **Yes** when employees add new address records through the **Personal information** page in Employee self service.</span></span> 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a><span data-ttu-id="1bd04-111">Skrócona karta Kandydaci do zatrudnienia w sekcji Zarządzania kadrami wyświetla niepoprawną liczbę kandydatów (470110)</span><span class="sxs-lookup"><span data-stu-id="1bd04-111">Candidates to hire FastTab in Personnel management shows an incorrect count of candidates (470110)</span></span>

<span data-ttu-id="1bd04-112">Na stronie **Zarządzanie personelem** jest teraz wyświetlana poprawna liczba kandydatów do zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="1bd04-112">The **Personnel management** page now accurately displays the number of candidates to hire.</span></span> 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a><span data-ttu-id="1bd04-113">Nie można wprowadzić choroby dla byłego pracownika, jeśli w naliczeniu ustawiono wartość zero (446195)</span><span class="sxs-lookup"><span data-stu-id="1bd04-113">Can’t enter sickness for terminated employee when accrual is set to zero (446195)</span></span>

<span data-ttu-id="1bd04-114">Transakcje urlopowe są teraz dozwolone dla pracowników, którzy zostali zwolnieni w przyszłości, a naliczenie jest ustawione na zero.</span><span class="sxs-lookup"><span data-stu-id="1bd04-114">Leave transactions are now allowed for employees that have been terminated in the future and the accrual is set to zero.</span></span> <span data-ttu-id="1bd04-115">Transakcje urlopowe mogą być wprowadzane aż do momentu daty zakończenia zatrudnienia pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="1bd04-115">Leave transactions can be entered up to the termination date of the employee.</span></span> 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a><span data-ttu-id="1bd04-116">Dodanie pól niestandardowych do nowego formularza powoduje wyłączenie pól w okienku akcji dotyczącego zarządzania urlopem (473314)</span><span class="sxs-lookup"><span data-stu-id="1bd04-116">Adding custom fields to the new Worker form disables the fields in the action pane for Manage leave (473314)</span></span>

<span data-ttu-id="1bd04-117">Opcje okienka akcji w nowym formularzu **Pracownik** w obszarze **Zarządzanie urlopem** nie będą już wyłączane, jeśli dodano pola niestandardowe do nowego formularza **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="1bd04-117">Action pane options on the new **Worker** form in **Manage leave** will no longer be disabled if custom fields have been added to the new **Worker** form.</span></span>

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a><span data-ttu-id="1bd04-118">Wprowadzenie obowiązkowości wypełnienia komentarza pola urlopowego pozwala na przesłanie żądania urlopowego, nawet gdy nie ma żadnego komentarza (473543)</span><span class="sxs-lookup"><span data-stu-id="1bd04-118">Making the Leave comment field mandatory allows a leave request to be submitted when no comment is entered (473543)</span></span>

<span data-ttu-id="1bd04-119">Pole komentarza jest wymagane i należy je wypełnić przed zamknięciem procesu.</span><span class="sxs-lookup"><span data-stu-id="1bd04-119">Comment fields can now be mandatory, and leave requests honor this setting.</span></span> <span data-ttu-id="1bd04-120">Pola wymagane to funkcja w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="1bd04-120">Mandatory fields is a preview feature.</span></span>

### <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="1bd04-121">Jednostka DMF dostępna dla wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="1bd04-121">DMF entity available for accrual suspensions</span></span>

<span data-ttu-id="1bd04-122">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="1bd04-122">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="in-preview"></a><span data-ttu-id="1bd04-123">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="1bd04-123">In preview</span></span>

### <a name="mandatory-fields"></a><span data-ttu-id="1bd04-124">Pola obowiązkowe</span><span class="sxs-lookup"><span data-stu-id="1bd04-124">Mandatory fields</span></span>

<span data-ttu-id="1bd04-125">Można wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="1bd04-125">You can make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="1bd04-126">Ta funkcja wymaga **Zapisanych widoków**.</span><span class="sxs-lookup"><span data-stu-id="1bd04-126">This feature requires **Saved views**.</span></span> <span data-ttu-id="1bd04-127">Aby uzyskać więcej informacji na temat zapisanych widoków, zobacz:</span><span class="sxs-lookup"><span data-stu-id="1bd04-127">For more information about saved views, see:</span></span>

- <span data-ttu-id="1bd04-128">[Zapisane widoki — ogólna dostępność](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) w planie wydania Dynamics 365 2020 aktualizacja 2</span><span class="sxs-lookup"><span data-stu-id="1bd04-128">[Saved views - general availability](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) in the Dynamics 365 2020 release wave 2 plan</span></span>
- [<span data-ttu-id="1bd04-129">Tworzenie formularzy, które w pełni wykorzystują zapisane widoki</span><span class="sxs-lookup"><span data-stu-id="1bd04-129">Build forms that fully utilize saved views</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/user-interface/understanding-saved-views)

### <a name="human-resources-application-in-teams"></a><span data-ttu-id="1bd04-130">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="1bd04-130">Human Resources application in Teams</span></span>

<span data-ttu-id="1bd04-131">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1bd04-131">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="1bd04-132">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="1bd04-132">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="1bd04-133">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="1bd04-133">For more information, see:</span></span>

- <span data-ttu-id="1bd04-134">[Urlop i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 1</span><span class="sxs-lookup"><span data-stu-id="1bd04-134">[Employee leave and absence experience in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- [<span data-ttu-id="1bd04-135">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="1bd04-135">Human Resources app in Teams</span></span>](https://go.microsoft.com/fwlink/?linkid=2127841)

## <a name="coming-soon"></a><span data-ttu-id="1bd04-136">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="1bd04-136">Coming soon</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="1bd04-137">Aplikacja Human Resources w Teams — funkcje w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="1bd04-137">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="1bd04-138">**Powiadomienia**: osoby przesyłające i osoby zatwierdzające żądania czasu wolnego będą powiadamiane w aplikacji Human Resources w Teams.</span><span class="sxs-lookup"><span data-stu-id="1bd04-138">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="1bd04-139">Osoby zatwierdzające będą mogły zatwierdzić lub odmówić żądanie czasu wolnego, a osoby przesyłające otrzymają powiadomienie o zatwierdzeniu lub odrzuceniu żądania.</span><span class="sxs-lookup"><span data-stu-id="1bd04-139">Approvers will be able to approve or deny time-off requests, and submitters will be notified if the request was approved or denied.</span></span>
 
- <span data-ttu-id="1bd04-140">**Kalendarz czasu wolnego kierownika**: Kierownicy będą mogli zobaczyć zatwierdzone i oczekujące prośby o czas wolny dla bezpośrednio podległych pracowników w widoku kalendarza.</span><span class="sxs-lookup"><span data-stu-id="1bd04-140">**Manager time-off calendar**: Managers will be able to see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="1bd04-141">Ten widok umożliwia w łatwy sposób sprawdzić, kiedy członkowie zespołu mają czas wolny.</span><span class="sxs-lookup"><span data-stu-id="1bd04-141">This view provides an easy understanding of when their team members are away from work.</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="1bd04-142">Jednostki listy kontrolnej uwzględnione w Dataverse</span><span class="sxs-lookup"><span data-stu-id="1bd04-142">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="1bd04-143">Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1bd04-143">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1bd04-144">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="1bd04-144">Known issues</span></span>

<span data-ttu-id="1bd04-145">W obszarze roboczym **Zarządzanie funkcjami** mogą być wyświetlane funkcje, które są wyłączone w postaci funkcji podglądu, gdy są one zazwyczaj dostępne.</span><span class="sxs-lookup"><span data-stu-id="1bd04-145">The **Feature management** workspace may be displaying features that are disabled as preview features when they are generally available.</span></span> <span data-ttu-id="1bd04-146">Poniżej znajduje się lista ogólnie dostępnych funkcji, które pokazują nieprawidłowy stan.</span><span class="sxs-lookup"><span data-stu-id="1bd04-146">Below is a list of generally available features that show an incorrect status.</span></span> 

- <span data-ttu-id="1bd04-147">Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="1bd04-147">Benefits management</span></span>
- <span data-ttu-id="1bd04-148">Zarządzanie sprawami</span><span class="sxs-lookup"><span data-stu-id="1bd04-148">Case management</span></span>
- <span data-ttu-id="1bd04-149">Rejestrowanie z bazie danych (inspekcja)</span><span class="sxs-lookup"><span data-stu-id="1bd04-149">Database logging (Auditing)</span></span>
- <span data-ttu-id="1bd04-150">Naliczanie urlopów dla jednej firmy lub pojedynczego planu</span><span class="sxs-lookup"><span data-stu-id="1bd04-150">Leave accrual for a single company or a single plan</span></span>
- <span data-ttu-id="1bd04-151">Zawieszenie naliczania urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="1bd04-151">Leave and absence accrual suspension</span></span>
- <span data-ttu-id="1bd04-152">Kod przyczyny korekty salda i komentarz</span><span class="sxs-lookup"><span data-stu-id="1bd04-152">Balance adjustment reason code and comment</span></span>
- <span data-ttu-id="1bd04-153">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="1bd04-153">Buy and sell leave</span></span>
- <span data-ttu-id="1bd04-154">Kalendarz urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="1bd04-154">Leave and absence calendar</span></span>
- <span data-ttu-id="1bd04-155">Reguły przeniesienia na następny okres urlopu</span><span class="sxs-lookup"><span data-stu-id="1bd04-155">Leave carry-forward rules</span></span>
- <span data-ttu-id="1bd04-156">Inspekcja naliczania urlopów</span><span class="sxs-lookup"><span data-stu-id="1bd04-156">Leave accrual auditing</span></span>
- <span data-ttu-id="1bd04-157">Usunięcie naliczenia urlopów</span><span class="sxs-lookup"><span data-stu-id="1bd04-157">Leave accrual deletion</span></span>
- <span data-ttu-id="1bd04-158">Zaokrąglanie naliczania urlopów</span><span class="sxs-lookup"><span data-stu-id="1bd04-158">Leave accrual rounding</span></span>
- <span data-ttu-id="1bd04-159">Konfiguruj wiele typów urlopów w jednym planie urlopów</span><span class="sxs-lookup"><span data-stu-id="1bd04-159">Configure multiple leave types on a single leave plan</span></span>
- <span data-ttu-id="1bd04-160">Aktualizuj udoskonalenia czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="1bd04-160">Update time-off enhancements</span></span>
- <span data-ttu-id="1bd04-161">Użyj równoważnika pełnego etatu pracownika etatowego do naliczeń</span><span class="sxs-lookup"><span data-stu-id="1bd04-161">Use an employee's FTE for accruals</span></span>
- <span data-ttu-id="1bd04-162">Widok wynagrodzeń między firmami</span><span class="sxs-lookup"><span data-stu-id="1bd04-162">Cross company compensation view</span></span>
- <span data-ttu-id="1bd04-163">Drukowanie przeglądów wydajności</span><span class="sxs-lookup"><span data-stu-id="1bd04-163">Print performance reviews</span></span>
- <span data-ttu-id="1bd04-164">Świąteczne korekty naliczania nieobecności</span><span class="sxs-lookup"><span data-stu-id="1bd04-164">Leave accrual holiday corrections</span></span>

### <a name="benefit-plan-employee-entity"></a><span data-ttu-id="1bd04-165">Encja planu świadczeń pracownika</span><span class="sxs-lookup"><span data-stu-id="1bd04-165">Benefit plan employee entity</span></span> 

<span data-ttu-id="1bd04-166">Ostatnio wykryto dwa problemy dotyczące encji **BenefitsPlanEmployee**.</span><span class="sxs-lookup"><span data-stu-id="1bd04-166">We have recently discovered two issues regarding the **BenefitsPlanEmployee** entity.</span></span> <span data-ttu-id="1bd04-167">Podczas importowania rejestracji pracowników **Kod objęcia świadczeniem** i **Kod typu planu** są ustawiane niepoprawnie.</span><span class="sxs-lookup"><span data-stu-id="1bd04-167">When importing worker enrollments, the **Coverage code** and the **Plan type code** are being set incorrectly.</span></span> <span data-ttu-id="1bd04-168">Ten błąd powoduje, że plany świadczeń pracowniczych są wyświetlane niepoprawnie w formularzu **Plan świadczeń pracownika** i w formularzu **Otwarcie rejestracji** w module samoobsługowym pracownika.</span><span class="sxs-lookup"><span data-stu-id="1bd04-168">This issue causes employee benefit plans to display incorrectly in the **Worker benefits plan** form and in the **Open enrollment** form in Employee self service.</span></span> <span data-ttu-id="1bd04-169">Ten problem może również wpływać na zdolność pracownika do wyboru planów w module samoobsługowym.</span><span class="sxs-lookup"><span data-stu-id="1bd04-169">This issue can also impact the employee's ability to select plans in Employee self service.</span></span> <span data-ttu-id="1bd04-170">Obecnie nie ma rozwiązania tego problemu.</span><span class="sxs-lookup"><span data-stu-id="1bd04-170">Currently there isn't a workaround.</span></span> <span data-ttu-id="1bd04-171">Ta poprawka jest traktowana jako poprawka o wysokim priorytecie i zostanie wydana w następnej wersji oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="1bd04-171">We're treating this as a high-priority fix and will roll out the fix with our next release.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bd04-172">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1bd04-172">See also</span></span>

[<span data-ttu-id="1bd04-173">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="1bd04-173">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="1bd04-174">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="1bd04-174">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="1bd04-175">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="1bd04-175">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="1bd04-176">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="1bd04-176">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]