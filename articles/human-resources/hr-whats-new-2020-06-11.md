---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (11 czerwiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 11 czerwca 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0720b2024a865fcd42cd80fd905586d626388f8f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420112"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="6d413-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (11 czerwiec 2020)</span><span class="sxs-lookup"><span data-stu-id="6d413-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

<span data-ttu-id="6d413-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6d413-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6d413-105">Zmiany dotyczą kompilacji o numerze 8.1.3316.</span><span class="sxs-lookup"><span data-stu-id="6d413-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="6d413-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="6d413-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="6d413-107">Uproszczony formularz pracownika czasami powoduje, że przyciski zamykania (X) formularza podrzędnego (442369) powodują zatrzymanie pracy</span><span class="sxs-lookup"><span data-stu-id="6d413-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="6d413-108">Po włączeniu nowego formularza **Pracownik** przycisk Zamknij (**X**) czasami nie działał w formularzach podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="6d413-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="6d413-109">Ten problem był sporadyczny.</span><span class="sxs-lookup"><span data-stu-id="6d413-109">This problem was intermittent.</span></span> <span data-ttu-id="6d413-110">Można zamknąć formularz po opuszczeniu i przyjściu z powrotem do niego.</span><span class="sxs-lookup"><span data-stu-id="6d413-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="6d413-111">Można na przykład zaznaczyć element menu po lewej stronie i przejść z powrotem do formularza **Pracownik** i zamknąć go.</span><span class="sxs-lookup"><span data-stu-id="6d413-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="6d413-112">Wydanie tego tygodnia rozwiązuje ten problem.</span><span class="sxs-lookup"><span data-stu-id="6d413-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="6d413-113">Osobista osoba kontaktowa pracownika nie eksportuje kontaktów osobistych z nadrzędnym typem relacji</span><span class="sxs-lookup"><span data-stu-id="6d413-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="6d413-114">W tym wydaniu encja **Osoby kontaktowej dla pracownika** eksportuje wszystkie typy relacji.</span><span class="sxs-lookup"><span data-stu-id="6d413-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="6d413-115">HcmPositionWorkerAssignmentV2Entity powinna być domyślnie częścią pakietu integracji Ceridian (448506)</span><span class="sxs-lookup"><span data-stu-id="6d413-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="6d413-116">Przy tej zmianie **HcmPositionWorkerAssignmentV2Entity** jest uwzględniony w pakiecie integracji Ceridian.</span><span class="sxs-lookup"><span data-stu-id="6d413-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="6d413-117">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="6d413-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="6d413-118">Logowanie do bazy danych</span><span class="sxs-lookup"><span data-stu-id="6d413-118">Database logging</span></span>

<span data-ttu-id="6d413-119">Funkcja rejestrowania bazy danych umożliwia określenie, która tabele i pola mają być monitorowane.</span><span class="sxs-lookup"><span data-stu-id="6d413-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="6d413-120">Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian.</span><span class="sxs-lookup"><span data-stu-id="6d413-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="6d413-121">Korzystasz z możliwości rejestrowania bazy danych, aby zobaczyć te zmiany w czasie.</span><span class="sxs-lookup"><span data-stu-id="6d413-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="6d413-122">Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie i zarządzanie rejestrowaniem bazy danych](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="6d413-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="6d413-123">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="6d413-123">Human Resources application in Teams</span></span>

<span data-ttu-id="6d413-124">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d413-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="6d413-125">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="6d413-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="6d413-126">Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="6d413-126">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="6d413-127">Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="6d413-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="6d413-128">Jednostki zarządzania świadczeniami są zwalniane.</span><span class="sxs-lookup"><span data-stu-id="6d413-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="6d413-129">Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami.</span><span class="sxs-lookup"><span data-stu-id="6d413-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="6d413-130">Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych.</span><span class="sxs-lookup"><span data-stu-id="6d413-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="6d413-131">Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.</span><span class="sxs-lookup"><span data-stu-id="6d413-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="6d413-132">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="6d413-132">Buy and sell leave</span></span> 

<span data-ttu-id="6d413-133">Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy.</span><span class="sxs-lookup"><span data-stu-id="6d413-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="6d413-134">Ten proces jest często zarządzany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="6d413-134">This process is often managed manually.</span></span> <span data-ttu-id="6d413-135">Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr.</span><span class="sxs-lookup"><span data-stu-id="6d413-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="6d413-136">Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy.</span><span class="sxs-lookup"><span data-stu-id="6d413-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="6d413-137">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="6d413-137">For more information, see:</span></span>

- [<span data-ttu-id="6d413-138">Zarządzaj zasadami Kupowania i Sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="6d413-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="6d413-139">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="6d413-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="6d413-140">Pozostaw naliczenie dla jednej firmy lub pojedynczego planu</span><span class="sxs-lookup"><span data-stu-id="6d413-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="6d413-141">Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności.</span><span class="sxs-lookup"><span data-stu-id="6d413-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="6d413-142">Ta możliwość jest dostępna w procesie naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopu.</span><span class="sxs-lookup"><span data-stu-id="6d413-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="6d413-143">Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="6d413-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="6d413-144">Dodawanie załączników do żądań czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="6d413-144">Add attachments to time off requests</span></span>

<span data-ttu-id="6d413-145">Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19.</span><span class="sxs-lookup"><span data-stu-id="6d413-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="6d413-146">Pracownicy mogą teraz dodawać te załączniki.</span><span class="sxs-lookup"><span data-stu-id="6d413-146">Employees can now add these attachments.</span></span> <span data-ttu-id="6d413-147">Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów.</span><span class="sxs-lookup"><span data-stu-id="6d413-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="6d413-148">Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="6d413-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="6d413-149">Dodano kod przyczyny do wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="6d413-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="6d413-150">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="6d413-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="6d413-151">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="6d413-151">Carry forward rules</span></span> 

<span data-ttu-id="6d413-152">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="6d413-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="6d413-153">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="6d413-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="6d413-154">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="6d413-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="6d413-155">Wstrzymanie naliczania urlopu dla określonych typów urlopów</span><span class="sxs-lookup"><span data-stu-id="6d413-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="6d413-156">Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="6d413-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="6d413-157">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="6d413-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="6d413-158">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="6d413-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="6d413-159">Jednostka DMF dostępna dla wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="6d413-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="6d413-160">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="6d413-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="6d413-161">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="6d413-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="6d413-162">Nowe możliwości platformy</span><span class="sxs-lookup"><span data-stu-id="6d413-162">New platform capabilities</span></span> 

<span data-ttu-id="6d413-163">Pola można uczynić obowiązkowymi za pomocą personalizacji.</span><span class="sxs-lookup"><span data-stu-id="6d413-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="6d413-164">Ta funkcja będzie wymagała włączania **Zapisanych widoków**.</span><span class="sxs-lookup"><span data-stu-id="6d413-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="6d413-165">Konfigurowanie nazwy Samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="6d413-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="6d413-166">Nowa opcja będzie dostępna w parametrach modułu Human Resources w celu zaktualizowania nazwy Samoobsługowego obszaru roboczego pracownika do Samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="6d413-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6d413-167">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="6d413-167">See also</span></span>

[<span data-ttu-id="6d413-168">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="6d413-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="6d413-169">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="6d413-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="6d413-170">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="6d413-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="6d413-171">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="6d413-171">Manage features</span></span>](hr-admin-manage-features.md)