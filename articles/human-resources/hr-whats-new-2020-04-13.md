---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (13 kwietnia 2020)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 13 kwietnia 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 729490e7516d8c7aef7232c9f5c227d3207dcd68
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712431"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="c13fb-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (13 kwietnia 2020)</span><span class="sxs-lookup"><span data-stu-id="c13fb-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

<span data-ttu-id="c13fb-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c13fb-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c13fb-105">Zmiany dotyczą kompilacji o numerze 8.1.3136.</span><span class="sxs-lookup"><span data-stu-id="c13fb-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="c13fb-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="c13fb-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="c13fb-107">Nowa frekwencja wydania produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="c13fb-107">New production release cadence</span></span>

<span data-ttu-id="c13fb-108">Wraz z wejściem wersji z tego tygodnia frekwencja wydwania nowych aktualizacji dla Human Resources przesunie się z cotygodniowej aktualizacji na aktualizację typu dwutygodniowego.</span><span class="sxs-lookup"><span data-stu-id="c13fb-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="c13fb-109">Aby zapewnić zgodność z zasadami bezpiecznego wdrażania systemu oraz utrzymywać wysokie standardy stabilności i niezawodności w usłudze, proces wdrażania aktualizacji usług we wszystkich regionach będzie teraz zmieniony na aktualizacje co dwa tygodnie.</span><span class="sxs-lookup"><span data-stu-id="c13fb-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="c13fb-110">Na każdym etapie procesu są umieszczone dodatkowe testy i urządzenia kontrolne.</span><span class="sxs-lookup"><span data-stu-id="c13fb-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="c13fb-111">Aby uzyskać więcej informacji o frekwencjji aktualizacji wersji, odwiedź [Proces aktualizacji](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="c13fb-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="c13fb-112">Pole dokładności zaokrąglania nie jest edytowalne po określeniu typu zaokrąglania (435616)</span><span class="sxs-lookup"><span data-stu-id="c13fb-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="c13fb-113">W przypadku zmiany pole **Dokładność zaokrąglania** jest teraz dostępne po zaktualizowaniu pola **Typ zaokrąglania**.</span><span class="sxs-lookup"><span data-stu-id="c13fb-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="c13fb-114">Nie można edytować daty zakończenia rejestracji urlopów, gdy plan urlopów nie ma okresów naliczania (413628)</span><span class="sxs-lookup"><span data-stu-id="c13fb-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="c13fb-115">Teraz można edytować datę zakończenia rejestracji bez uzyskiwania błędu „Podstawa daty naliczania pola musi być wypełniona”.</span><span class="sxs-lookup"><span data-stu-id="c13fb-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a><span data-ttu-id="c13fb-116">Jednostka zatrudnienia nie jest synchronizowana z Common Data Service (430834)</span><span class="sxs-lookup"><span data-stu-id="c13fb-116">Employment entity doesn't sync to Common Data Service (430834)</span></span>

<span data-ttu-id="c13fb-117">Ta zmiana polega na usunięciu usterki, do której nie wykonano synchronizacji z Common Data Service danych dotyczących zatrudnienia po dodaniu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="c13fb-117">This change corrects an issue where the employment data wasn't syncing to Common Data Service after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="c13fb-118">Usuń wiele obiektów nadrzędnych dla jednostki Zakres czasu w kalendarzu roboczym (431775)</span><span class="sxs-lookup"><span data-stu-id="c13fb-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="c13fb-119">Ta zmiana usuwa wiele obiektów nadrzędnych dla jednostki **Zakres czasu w kalendarzu roboczym**.</span><span class="sxs-lookup"><span data-stu-id="c13fb-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="c13fb-120">Filtr z funkcją CAST nie działa w odniesieniu do jednostki Przypisanie pracownika do stanowiska wywołania OData (431699)</span><span class="sxs-lookup"><span data-stu-id="c13fb-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="c13fb-121">Ta aktualizacja zawiera zmianę zezwalającą na Filtrowanie za pomocą funkcji CAST w OData dla jednostki **Przypisanie pracownika do stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="c13fb-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="c13fb-122">W wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="c13fb-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="c13fb-123">Zawieszenie urlopu</span><span class="sxs-lookup"><span data-stu-id="c13fb-123">Leave suspension</span></span>

<span data-ttu-id="c13fb-124">Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="c13fb-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="c13fb-125">Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="c13fb-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="c13fb-126">Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika.</span><span class="sxs-lookup"><span data-stu-id="c13fb-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="c13fb-127">Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="c13fb-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="c13fb-128">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="c13fb-128">Carry forward rules</span></span>

<span data-ttu-id="c13fb-129">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="c13fb-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="c13fb-130">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="c13fb-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="c13fb-131">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="c13fb-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="c13fb-132">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="c13fb-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="c13fb-133">Jednostka szczegółów zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="c13fb-133">Employment Details entity</span></span>

<span data-ttu-id="c13fb-134">Jednostka **Szczegółów zatrudnienia** została zaktualizowana o następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c13fb-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="c13fb-135">**Częstotliwość wypłat**</span><span class="sxs-lookup"><span data-stu-id="c13fb-135">**PayFrequency**</span></span>
- <span data-ttu-id="c13fb-136">**Numer identyfikacyjny kategorii zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="c13fb-136">**Employment Category ID**</span></span>
- <span data-ttu-id="c13fb-137">**Typ zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="c13fb-137">**Employment Type**</span></span>
- <span data-ttu-id="c13fb-138">**Numer identyfikacyjny typu zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="c13fb-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="c13fb-139">**Stan świadczeń zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="c13fb-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="c13fb-140">Dane konfiguracyjne tych pól zależą od sposobu włączenia funkcji zarządzania świadczeniami w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="c13fb-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="c13fb-141">Te pola nie powinny być wypełniane ani aktualizowane w jednostce **Szczegółów zatrudnienia**, ponieważ powoduje to błędy podczas importowania.</span><span class="sxs-lookup"><span data-stu-id="c13fb-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="c13fb-142">Podgląd SharePoint nie działa w niektórych środowiskach</span><span class="sxs-lookup"><span data-stu-id="c13fb-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="c13fb-143">Jeśli Podgląd dokumentów przechowywanych w SharePoint nie działa, spróbuj wykonać poniższą procedurę:</span><span class="sxs-lookup"><span data-stu-id="c13fb-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="c13fb-144">Sprawdź, czy konto użytkownika administratora zawiera wiadomość e-mail skojarzoną z rekordem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c13fb-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="c13fb-145">Można przejrzeć te informacje na stronie **Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="c13fb-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="c13fb-146">Jeśli poczta e-mail nie jest skonfigurowana, należy dodać wiadomość e-mail i dostawcę za pomocą dodatku OData dla programu Excel.</span><span class="sxs-lookup"><span data-stu-id="c13fb-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="c13fb-147">Domyślnie adres e-mail nie jest obecny w projekcie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="c13fb-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="c13fb-148">Musisz edytować projekt programu Excel, dodać wszystkie pola, zastosować je i odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="c13fb-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="c13fb-149">Po wykonaniu tych kroków można zaktualizować konto administratora.</span><span class="sxs-lookup"><span data-stu-id="c13fb-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="c13fb-150">Gdy konto Administratora ma skojarzone konto e-mail, zaloguj się do modułu Human Resources z poświadczeniami administratora.</span><span class="sxs-lookup"><span data-stu-id="c13fb-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="c13fb-151">Aby uruchomić podgląd dokumentu, uzyskaj dostęp do załącznika SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c13fb-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="c13fb-152">Zaloguj się przy użyciu konta innego użytkownika, które ma dostęp do załączników i sprawdź, czy podgląd działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="c13fb-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="c13fb-153">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c13fb-153">See also</span></span>

[<span data-ttu-id="c13fb-154">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="c13fb-154">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="c13fb-155">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="c13fb-155">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="c13fb-156">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="c13fb-156">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="c13fb-157">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="c13fb-157">Manage features</span></span>](hr-admin-manage-features.md)