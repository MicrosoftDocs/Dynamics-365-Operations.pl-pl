---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (28 maja 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c386025843edef83d229a42d3f2314678fadae20
ms.sourcegitcommit: beddfba095c23b3265f0004f5124c4e9dc6404cc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411937"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="a4a49-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (28 maja 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="a4a49-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

<span data-ttu-id="a4a49-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a4a49-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a4a49-105">Zmiany dotyczą kompilacji o numerze 8.1.3287.</span><span class="sxs-lookup"><span data-stu-id="a4a49-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="a4a49-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="a4a49-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="a4a49-107">Jednostka LeaveRequest nie działa w przypadku włączenia wielu typów dla każdego planu urlopu (447498)</span><span class="sxs-lookup"><span data-stu-id="a4a49-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="a4a49-108">Po wprowadzeniu tej zmiany **LeaveEnrollmentV2Entity** jest teraz dostępny, aby poprawić błąd występujący po włączeniu wielu typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="a4a49-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="a4a49-109">Funkcja redukcji rywalizacji partii (wersja zapoznawcza) (446619)</span><span class="sxs-lookup"><span data-stu-id="a4a49-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="a4a49-110">Po włączeniu tej funkcji można oczekiwać zmniejszenia blokowania w tabelach struktury przetwarzania wsadowego podczas wybierania zadań i kończenia zadań.</span><span class="sxs-lookup"><span data-stu-id="a4a49-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="a4a49-111">UpdateConflict podczas zapisywania pracownika uniemożliwia edytowanie rekordu w osobach (427915)</span><span class="sxs-lookup"><span data-stu-id="a4a49-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="a4a49-112">Ta zmiana poprawia błąd podczas dodawania nowego pracownika, aktualizowania informacji adresowych i zmiany preferencji językowych.</span><span class="sxs-lookup"><span data-stu-id="a4a49-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="a4a49-113">W tym unikatowym scenariuszu wyświetlany jest błąd wskazujący, że nie można zaktualizować rekordu.</span><span class="sxs-lookup"><span data-stu-id="a4a49-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="a4a49-114">Nie można dodać załącznika do zatwierdzonego wniosku o urlop, aby ponownie go złożyć (425407)</span><span class="sxs-lookup"><span data-stu-id="a4a49-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="a4a49-115">Ta zmiana umożliwia teraz załączniki do zatwierdzonych wniosków o urlop.</span><span class="sxs-lookup"><span data-stu-id="a4a49-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="a4a49-116">Użytkownik może wprowadzić wynagrodzenie dla pracownika w formularzu innej firmy (409529)</span><span class="sxs-lookup"><span data-stu-id="a4a49-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="a4a49-117">Ta zmiana wyłącza opcje kompensacji zapobiegające przypadkowemu wprowadzeniu rekordów wynagrodzenia dla niewłaściwej firmy.</span><span class="sxs-lookup"><span data-stu-id="a4a49-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="a4a49-118">Błąd podczas przenoszenia pracownika, a data przypisania stanowiska pracownika jest wcześniejsza niż czas trwania stanowiska (429402)</span><span class="sxs-lookup"><span data-stu-id="a4a49-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="a4a49-119">Komunikaty o błędach podczas przenoszenia pracownika w tym scenariuszu zostały zaktualizowane w celu lepszego opisywania niezbędnych zmian w celu rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="a4a49-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="a4a49-120">Możliwości załączników w rejestracji świadczeń samoobsługowych dla pracowników</span><span class="sxs-lookup"><span data-stu-id="a4a49-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="a4a49-121">Teraz możesz dodawać załączniki podczas procesu rejestracji świadczeń dla każdego planu, w którym pracownik się rejestruje.</span><span class="sxs-lookup"><span data-stu-id="a4a49-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="a4a49-122">Następnie można wyświetlić te załączniki w formularzu **Zarejestrowane świadczenia pracownika**.</span><span class="sxs-lookup"><span data-stu-id="a4a49-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a4a49-123">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="a4a49-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="a4a49-124">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="a4a49-124">Human Resources application in Teams</span></span>

<span data-ttu-id="a4a49-125">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a4a49-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="a4a49-126">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="a4a49-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="a4a49-127">Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="a4a49-127">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="a4a49-128">Zawieszenie urlopu</span><span class="sxs-lookup"><span data-stu-id="a4a49-128">Leave suspension</span></span>

<span data-ttu-id="a4a49-129">Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="a4a49-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="a4a49-130">Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="a4a49-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="a4a49-131">Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika.</span><span class="sxs-lookup"><span data-stu-id="a4a49-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="a4a49-132">Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="a4a49-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="a4a49-133">Zaktualizowano środowisko użytkownika, aby umożliwić wskazanie, że naliczanie zostało zawieszone (429550)</span><span class="sxs-lookup"><span data-stu-id="a4a49-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="a4a49-134">Środowisko użytkownika wskazuje teraz, że naliczanie dla planu zostało zawieszone.</span><span class="sxs-lookup"><span data-stu-id="a4a49-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a4a49-135">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="a4a49-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="a4a49-136">Rejestrowanie w bazie danych (w wersji zapoznawczej w czerwcu)</span><span class="sxs-lookup"><span data-stu-id="a4a49-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="a4a49-137">Funkcja rejestrowania bazy danych umożliwia określenie, która tabela i które pola mają być monitorowane.</span><span class="sxs-lookup"><span data-stu-id="a4a49-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="a4a49-138">Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian.</span><span class="sxs-lookup"><span data-stu-id="a4a49-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="a4a49-139">Dostępne są możliwości zapytania, aby zmiany były widoczne w czasie.</span><span class="sxs-lookup"><span data-stu-id="a4a49-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="a4a49-140">Kupuj i sprzedawaj urlop (w wersji zapoznawczej 1 czerwca)</span><span class="sxs-lookup"><span data-stu-id="a4a49-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="a4a49-141">Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy.</span><span class="sxs-lookup"><span data-stu-id="a4a49-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="a4a49-142">Ten proces jest często zarządzany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="a4a49-142">This process is often managed manually.</span></span> <span data-ttu-id="a4a49-143">Ta funkcja zapewnia bardziej zautomatyzowany sposób zarządzania zasadami i wnioskami dotyczącymi działu kadr, a także eliminuje pomyłki przy jednoczesnym usprawnieniu procesu zarządzania urlopami.</span><span class="sxs-lookup"><span data-stu-id="a4a49-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span>

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="a4a49-144">Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="a4a49-144">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="a4a49-145">Jednostki zarządzania świadczeniami są zwalniane.</span><span class="sxs-lookup"><span data-stu-id="a4a49-145">Benefits management entities are releasing.</span></span> <span data-ttu-id="a4a49-146">Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami.</span><span class="sxs-lookup"><span data-stu-id="a4a49-146">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="a4a49-147">Dostępny jest również szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych.</span><span class="sxs-lookup"><span data-stu-id="a4a49-147">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="a4a49-148">Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.</span><span class="sxs-lookup"><span data-stu-id="a4a49-148">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="a4a49-149">Dodano kod przyczyny do wstrzymań naliczania (1 czerwca)</span><span class="sxs-lookup"><span data-stu-id="a4a49-149">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="a4a49-150">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="a4a49-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="a4a49-151">Zasady przenoszenia na następny okres (1 czerwca)</span><span class="sxs-lookup"><span data-stu-id="a4a49-151">Carry forward rules (June 1)</span></span>

<span data-ttu-id="a4a49-152">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="a4a49-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a4a49-153">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="a4a49-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a4a49-154">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a4a49-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="a4a49-155">Wstrzymanie naliczania urlopu dla określonych typów urlopów (1 czerwca)</span><span class="sxs-lookup"><span data-stu-id="a4a49-155">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="a4a49-156">W tym wydaniu dział zasobów ludzkich może utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="a4a49-156">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a4a49-157">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="a4a49-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a4a49-158">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="a4a49-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="a4a49-159">Jednostka DMF dostępna dla wstrzymań naliczania (1 czerwca)</span><span class="sxs-lookup"><span data-stu-id="a4a49-159">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="a4a49-160">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="a4a49-160">A DMF entity is now available for accrual suspensions.</span></span>