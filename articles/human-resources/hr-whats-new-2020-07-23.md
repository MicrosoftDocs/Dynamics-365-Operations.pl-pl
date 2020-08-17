---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (23 lipiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd71ab5c48be1bec5ce2272bbff37ab10a4aed67
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614417"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="ca39a-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (23 lipiec 2020)</span><span class="sxs-lookup"><span data-stu-id="ca39a-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

<span data-ttu-id="ca39a-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ca39a-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ca39a-105">Zmiany dotyczą kompilacji o numerze 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="ca39a-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="ca39a-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="ca39a-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="ca39a-107">Usunięcie wymiarów finansowych na stanowisku nie działa zgodnie z oczekiwaniami (445476)</span><span class="sxs-lookup"><span data-stu-id="ca39a-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="ca39a-108">Usunięcie wymiarów z stanowiska powoduje obecnie usunięcie tych samych stanowisk z Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ca39a-108">Removing dimensions from a position now removes those same positions from Common Data Service.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="ca39a-109">Pozycje poza hierarchią pokazują nieaktywne pozycje (397257)</span><span class="sxs-lookup"><span data-stu-id="ca39a-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="ca39a-110">Stanowiska, które są nieaktywne (mają wygasły czas trwania), nie są już wyświetlane w hierarchii stanowisk jako **Pozycje poza hierarchią**.</span><span class="sxs-lookup"><span data-stu-id="ca39a-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="ca39a-111">Walidacja zachodząca między LeaveEnrollmentEntity i HcmWorkerEntity na imporcie Data Management Framework (DMF) powoduje powolne ładowanie danych (442324)</span><span class="sxs-lookup"><span data-stu-id="ca39a-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="ca39a-112">Zmiany w tej wersji zwiększają wydajność **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="ca39a-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="ca39a-113">Nie można spersonalizować w administrowaniu organizacją (447490)</span><span class="sxs-lookup"><span data-stu-id="ca39a-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="ca39a-114">Dzięki tej zmianie można teraz personalizować łącza w **Administrowanie organizacją**.</span><span class="sxs-lookup"><span data-stu-id="ca39a-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="ca39a-115">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="ca39a-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="ca39a-116">Pola obowiązkowe</span><span class="sxs-lookup"><span data-stu-id="ca39a-116">Mandatory fields</span></span> 

<span data-ttu-id="ca39a-117">Można teraz wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="ca39a-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="ca39a-118">Ta funkcja wymaga **Zapisanych widoków**.</span><span class="sxs-lookup"><span data-stu-id="ca39a-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="ca39a-119">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="ca39a-119">Human Resources application in Teams</span></span>

<span data-ttu-id="ca39a-120">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca39a-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="ca39a-121">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="ca39a-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="ca39a-122">Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="ca39a-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="ca39a-123">Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="ca39a-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="ca39a-124">Jednostki zarządzania świadczeniami są zwalniane.</span><span class="sxs-lookup"><span data-stu-id="ca39a-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="ca39a-125">Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami.</span><span class="sxs-lookup"><span data-stu-id="ca39a-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="ca39a-126">Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych.</span><span class="sxs-lookup"><span data-stu-id="ca39a-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="ca39a-127">Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.</span><span class="sxs-lookup"><span data-stu-id="ca39a-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="ca39a-128">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="ca39a-128">Buy and sell leave</span></span> 

<span data-ttu-id="ca39a-129">Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy.</span><span class="sxs-lookup"><span data-stu-id="ca39a-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="ca39a-130">Ten proces jest często zarządzany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="ca39a-130">This process is often managed manually.</span></span> <span data-ttu-id="ca39a-131">Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr.</span><span class="sxs-lookup"><span data-stu-id="ca39a-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="ca39a-132">Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy.</span><span class="sxs-lookup"><span data-stu-id="ca39a-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="ca39a-133">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="ca39a-133">For more information, see:</span></span>

- [<span data-ttu-id="ca39a-134">Zarządzaj zasadami Kupowania i Sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="ca39a-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="ca39a-135">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="ca39a-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="ca39a-136">Pozostaw naliczenie dla jednej firmy lub pojedynczego planu</span><span class="sxs-lookup"><span data-stu-id="ca39a-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="ca39a-137">Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności.</span><span class="sxs-lookup"><span data-stu-id="ca39a-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="ca39a-138">Ta możliwość jest dostępna dla procesu naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopów.</span><span class="sxs-lookup"><span data-stu-id="ca39a-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="ca39a-139">Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="ca39a-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="ca39a-140">Dodawanie załączników do żądań czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="ca39a-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="ca39a-141">Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19.</span><span class="sxs-lookup"><span data-stu-id="ca39a-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="ca39a-142">Pracownicy mogą teraz dodawać te załączniki.</span><span class="sxs-lookup"><span data-stu-id="ca39a-142">Employees can now add these attachments.</span></span> <span data-ttu-id="ca39a-143">Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów.</span><span class="sxs-lookup"><span data-stu-id="ca39a-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="ca39a-144">Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="ca39a-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="ca39a-145">Dodano kod przyczyny do wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="ca39a-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="ca39a-146">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="ca39a-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="ca39a-147">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="ca39a-147">Carry forward rules</span></span> 

<span data-ttu-id="ca39a-148">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="ca39a-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="ca39a-149">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="ca39a-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="ca39a-150">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca39a-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="ca39a-151">Wstrzymanie naliczania urlopu dla określonych typów urlopów</span><span class="sxs-lookup"><span data-stu-id="ca39a-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="ca39a-152">Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="ca39a-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="ca39a-153">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="ca39a-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="ca39a-154">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="ca39a-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="ca39a-155">Jednostka DMF dostępna dla wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="ca39a-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="ca39a-156">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="ca39a-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="ca39a-157">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="ca39a-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="ca39a-158">Jednostki listy kontrolnej uwzględnione w Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ca39a-158">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="ca39a-159">Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ca39a-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="ca39a-160">Zmiany w platformie</span><span class="sxs-lookup"><span data-stu-id="ca39a-160">Platform changes</span></span>

<span data-ttu-id="ca39a-161">Aktualizacja Platform Update 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="ca39a-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="ca39a-162">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ca39a-162">See also</span></span>

[<span data-ttu-id="ca39a-163">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="ca39a-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="ca39a-164">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="ca39a-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="ca39a-165">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="ca39a-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="ca39a-166">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="ca39a-166">Manage features</span></span>](hr-admin-manage-features.md)
