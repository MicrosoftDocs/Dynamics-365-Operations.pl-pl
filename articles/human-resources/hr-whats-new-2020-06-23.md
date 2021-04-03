---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (25 czerwiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 23 czerwca 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f767ad634a37b7231a7998184ef130668c8a8dc
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463629"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a><span data-ttu-id="96ace-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (23 czerwiec 2020)</span><span class="sxs-lookup"><span data-stu-id="96ace-103">What's new or changed in Dynamics 365 Human Resources (June 23, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="96ace-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96ace-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="96ace-105">Zmiany dotyczą kompilacji o numerze 8.1.3347.</span><span class="sxs-lookup"><span data-stu-id="96ace-105">Changes apply to build number 8.1.3347.</span></span> <span data-ttu-id="96ace-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="96ace-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a><span data-ttu-id="96ace-107">Po wygaśnięciu rejestracji pracownika, który zakończył pracę, typ urlopu, saldo i kwota są usuwane z formularza Rejestracja urlopu (444867)</span><span class="sxs-lookup"><span data-stu-id="96ace-107">When an enrollment is expired for a terminated employee, the leave type, balance, and amount are all cleared in the Leave enrollment form (444867)</span></span>

<span data-ttu-id="96ace-108">Wartości **Typ urlopu**, **Saldo** i **Kwota** są obecnie utrzymywane, a nie wyczyszczone po dokonaniu wyboru.</span><span class="sxs-lookup"><span data-stu-id="96ace-108">Values in the **Leave type**, **Balance**, and **Amount** are now maintained instead of cleared upon making this selection.</span></span>

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a><span data-ttu-id="96ace-109">Nieprawidłowe prognozowane saldo, gdy jest uruchamiana nowa funkcja (Naliczanie urlopów dla jednej firmy lub jednego planu) (456553)</span><span class="sxs-lookup"><span data-stu-id="96ace-109">Incorrect forecasted balance when new feature (Leave accrual for a single company or a single plan) is enabled (456553)</span></span>

<span data-ttu-id="96ace-110">Prawidłowe prognozowane saldo jest wyświetlane, gdy jest uruchamiana nowa funkcja Naliczanie urlopów dla jednej firmy lub jednego planu.</span><span class="sxs-lookup"><span data-stu-id="96ace-110">The correct forecasted balance now displays when the leave accrual for a single company or single plan has been enabled.</span></span>

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a><span data-ttu-id="96ace-111">Jednostki z relacjami, które powodują powstanie zduplikowanych właściwości nawigacji (456486)</span><span class="sxs-lookup"><span data-stu-id="96ace-111">Entities with relations that result in duplicate navigation properties (456486)</span></span>

<span data-ttu-id="96ace-112">Ta wersja koryguje kwestię dotyczącą właściwości nawigacji (relacji) wielu jednostek.</span><span class="sxs-lookup"><span data-stu-id="96ace-112">This release corrects an issue with the navigation properties (relation) of multiple entities.</span></span> <span data-ttu-id="96ace-113">Wykryto zduplikowane relacje.</span><span class="sxs-lookup"><span data-stu-id="96ace-113">Duplicate relations are detected.</span></span> <span data-ttu-id="96ace-114">Te scenariusze zostały poprawione.</span><span class="sxs-lookup"><span data-stu-id="96ace-114">These scenarios have all been corrected.</span></span>
 
## <a name="cross-company-comments-on-performance-review-455536"></a><span data-ttu-id="96ace-115">Komentarze międzyfirmowe dotyczące przeglądu wydajności (455536)</span><span class="sxs-lookup"><span data-stu-id="96ace-115">Cross-company comments on Performance review (455536)</span></span>

<span data-ttu-id="96ace-116">Komentarze międzyfirmowe są teraz widoczne na monitorach wydajności za pomocą tej poprawki.</span><span class="sxs-lookup"><span data-stu-id="96ace-116">Cross-company comments are now visible on performance reviews with this fix.</span></span> <span data-ttu-id="96ace-117">Ta zmiana umożliwia skorygowanie komentarzy recenzentów wprowadzonych w różnych firmach w związku z tym samym przeglądem wydajności.</span><span class="sxs-lookup"><span data-stu-id="96ace-117">This change corrects the view of reviewer comments that were entered in different companies for the same performance review.</span></span>
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a><span data-ttu-id="96ace-118">Niespójność w wyświetlaniu danych zarządzania wynagrodzeniem (432562)</span><span class="sxs-lookup"><span data-stu-id="96ace-118">Inconsistency in showing compensation management data (432562)</span></span>

<span data-ttu-id="96ace-119">Spójny widok danych dotyczących wynagrodzenia jest obecnie utrzymywany w usłudze samoobsługowej kierownika.</span><span class="sxs-lookup"><span data-stu-id="96ace-119">A consistent view of compensation data is now maintained in Manager self service.</span></span> <span data-ttu-id="96ace-120">Zależnie od sposobu przechodzenia do **Szczegółów dotyczących wynagrodzenia** pracownika, dane o wynagrodzeniach są teraz poprawnie wyświetlane kierownikom.</span><span class="sxs-lookup"><span data-stu-id="96ace-120">Depending on how you navigate to a worker's **Compensation details**, compensation data now consistently displays to managers.</span></span>
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a><span data-ttu-id="96ace-121">Naprawiono błąd, w którym domyślna Data wprowadzenia w systemie stałych wynagrodzeń była równa dacie dzisiejszej (411994)</span><span class="sxs-lookup"><span data-stu-id="96ace-121">Fixed compensation plan's effective date defaults to today's date (411994)</span></span>

<span data-ttu-id="96ace-122">Data początkowa wynagrodzenia jest teraz określana na podstawie daty rozpoczęcia pracy na stanowisku przypisanym do pracownika.</span><span class="sxs-lookup"><span data-stu-id="96ace-122">The compensation start date is now based on the start date of the position being assigned to the employee.</span></span>

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a><span data-ttu-id="96ace-123">Formularz urlop i nieobecności – opcja Włączanie definicji połowy dnia jest wyłączona po otwarciu formularza (452607)</span><span class="sxs-lookup"><span data-stu-id="96ace-123">Leave and absence form Enable half day definition is disabled when form opens (452607)</span></span>

<span data-ttu-id="96ace-124">Ta zmiana powoduje, że **Włączanie definicji połowy dnia** będzie włączona do momentu, aż będą istnieć nowe transakcje urlopowe.</span><span class="sxs-lookup"><span data-stu-id="96ace-124">With this change, the **Enable half day definition** will be enabled until new leave transactions exist.</span></span> 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a><span data-ttu-id="96ace-125">Nie można publikować w HcmDiscussionEntity za pośrednictwem programu Excel; Błąd pola TotalRatingScore (453899)</span><span class="sxs-lookup"><span data-stu-id="96ace-125">Unable to publish to HcmDiscussionEntity via Excel; TotalRatingScore field error (453899)</span></span>

<span data-ttu-id="96ace-126">Teraz można zaktualizować pole **TotalRatingScore** za pomocą **HCMDiscussionEntity** w projektancie skoroszytów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="96ace-126">You can now update the **TotalRatingScore** field using **HCMDiscussionEntity** in the Excel workbook designer.</span></span>

## <a name="in-preview"></a><span data-ttu-id="96ace-127">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="96ace-127">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="96ace-128">Logowanie do bazy danych</span><span class="sxs-lookup"><span data-stu-id="96ace-128">Database logging</span></span>

<span data-ttu-id="96ace-129">Rejestrowanie bazy danych umożliwia określenie, która tabele i pola mają być monitorowane.</span><span class="sxs-lookup"><span data-stu-id="96ace-129">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="96ace-130">Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian.</span><span class="sxs-lookup"><span data-stu-id="96ace-130">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="96ace-131">Korzystasz z możliwości rejestrowania bazy danych, aby zobaczyć te zmiany w czasie.</span><span class="sxs-lookup"><span data-stu-id="96ace-131">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="96ace-132">Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie i zarządzanie rejestrowaniem bazy danych](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="96ace-132">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="96ace-133">Pola obowiązkowe</span><span class="sxs-lookup"><span data-stu-id="96ace-133">Mandatory fields</span></span> 

<span data-ttu-id="96ace-134">Można teraz wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="96ace-134">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="96ace-135">Ta funkcja wymaga **Zapisanych widoków**.</span><span class="sxs-lookup"><span data-stu-id="96ace-135">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="96ace-136">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="96ace-136">Human Resources application in Teams</span></span>

<span data-ttu-id="96ace-137">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96ace-137">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="96ace-138">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="96ace-138">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="96ace-139">Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="96ace-139">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="96ace-140">Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="96ace-140">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="96ace-141">Jednostki zarządzania świadczeniami są zwalniane.</span><span class="sxs-lookup"><span data-stu-id="96ace-141">Benefits management entities are releasing.</span></span> <span data-ttu-id="96ace-142">Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami.</span><span class="sxs-lookup"><span data-stu-id="96ace-142">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="96ace-143">Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych.</span><span class="sxs-lookup"><span data-stu-id="96ace-143">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="96ace-144">Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.</span><span class="sxs-lookup"><span data-stu-id="96ace-144">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="96ace-145">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="96ace-145">Buy and sell leave</span></span> 

<span data-ttu-id="96ace-146">Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy.</span><span class="sxs-lookup"><span data-stu-id="96ace-146">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="96ace-147">Ten proces jest często zarządzany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="96ace-147">This process is often managed manually.</span></span> <span data-ttu-id="96ace-148">Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr.</span><span class="sxs-lookup"><span data-stu-id="96ace-148">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="96ace-149">Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy.</span><span class="sxs-lookup"><span data-stu-id="96ace-149">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="96ace-150">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="96ace-150">For more information, see:</span></span>

- [<span data-ttu-id="96ace-151">Zarządzaj zasadami Kupowania i Sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="96ace-151">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="96ace-152">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="96ace-152">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="96ace-153">Pozostaw naliczenie dla jednej firmy lub pojedynczego planu</span><span class="sxs-lookup"><span data-stu-id="96ace-153">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="96ace-154">Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności.</span><span class="sxs-lookup"><span data-stu-id="96ace-154">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="96ace-155">Ta możliwość jest dostępna w procesie naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopu.</span><span class="sxs-lookup"><span data-stu-id="96ace-155">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="96ace-156">Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="96ace-156">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="96ace-157">Dodawanie załączników do żądań czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="96ace-157">Add attachments to time off requests</span></span>

<span data-ttu-id="96ace-158">Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19.</span><span class="sxs-lookup"><span data-stu-id="96ace-158">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="96ace-159">Pracownicy mogą teraz dodawać te załączniki.</span><span class="sxs-lookup"><span data-stu-id="96ace-159">Employees can now add these attachments.</span></span> <span data-ttu-id="96ace-160">Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów.</span><span class="sxs-lookup"><span data-stu-id="96ace-160">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="96ace-161">Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="96ace-161">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="96ace-162">Dodano kod przyczyny do wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="96ace-162">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="96ace-163">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="96ace-163">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="96ace-164">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="96ace-164">Carry forward rules</span></span> 

<span data-ttu-id="96ace-165">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="96ace-165">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="96ace-166">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="96ace-166">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="96ace-167">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="96ace-167">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="96ace-168">Wstrzymanie naliczania urlopu dla określonych typów urlopów</span><span class="sxs-lookup"><span data-stu-id="96ace-168">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="96ace-169">Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="96ace-169">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="96ace-170">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="96ace-170">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="96ace-171">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="96ace-171">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="96ace-172">Jednostka DMF dostępna dla wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="96ace-172">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="96ace-173">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="96ace-173">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="96ace-174">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="96ace-174">Coming soon</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="96ace-175">Konfigurowanie nazwy Samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="96ace-175">Configure the name of Employee self-service</span></span>

<span data-ttu-id="96ace-176">Nowa opcja będzie dostępna w parametrach **modułu Human Resources** w celu zaktualizowania nazwy „Samoobsługowy obszar roboczy pracownika” na nazwę „Samoobsługa”.</span><span class="sxs-lookup"><span data-stu-id="96ace-176">A new option will be available in **Human Resources parameters** to update the name of the Employee self service workspace to Self service.</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="96ace-177">Jednostki listy kontrolnej uwzględnione w Dataverse</span><span class="sxs-lookup"><span data-stu-id="96ace-177">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="96ace-178">Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w systemie Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96ace-178">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon within Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="96ace-179">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="96ace-179">See also</span></span>

[<span data-ttu-id="96ace-180">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="96ace-180">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="96ace-181">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="96ace-181">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="96ace-182">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="96ace-182">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="96ace-183">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="96ace-183">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]