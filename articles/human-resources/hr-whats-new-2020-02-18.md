---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (18 lutego 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 18 lutego 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66ffd9d0ffcf0e8466be785274ef5fb0fceda7a9
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463797"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="967c5-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (18 lutego 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="967c5-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="967c5-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="967c5-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="967c5-105">Zmiany dotyczą kompilacji o numerze 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="967c5-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="967c5-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="967c5-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="967c5-107">Aktualizacja platformy Update 32</span><span class="sxs-lookup"><span data-stu-id="967c5-107">Platform update 32</span></span> 

<span data-ttu-id="967c5-108">Aktualizacja platformy 32 jest teraz dostępna.</span><span class="sxs-lookup"><span data-stu-id="967c5-108">Platform update 32 is now available.</span></span> <span data-ttu-id="967c5-109">Aby uzyskać więcej informacji, należy zapoznać się z [Nowości i zmiany w aktualizacji 32 platformy dla Finance and Operations (Luty 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span><span class="sxs-lookup"><span data-stu-id="967c5-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="967c5-110">Wartości wyszukiwania są zapamiętane podczas zmiany opcji widoku w formularzu usprawnionego pracownika (383833)</span><span class="sxs-lookup"><span data-stu-id="967c5-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="967c5-111">Teraz nowy formularz **Pracownik** zapamiętuje wartości wyszukiwania po zmianie opcji widoku i zastosowaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="967c5-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="967c5-112">Kafelki podsumowania zarządzania kompensacją w funkcji podglądu przekierowują do niewłaściwego formularza (401861)</span><span class="sxs-lookup"><span data-stu-id="967c5-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="967c5-113">Kafelki zarządzania stałymi i zmiennymi wynagrodzeniami wyświetlają poprawne rekordy w nowym formularzu **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="967c5-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="967c5-114">Dotyczy wyłącznie funkcji podglądu usprawnionego formularza pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="967c5-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="967c5-115">Tę funkcję podglądu można włączyć w module **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="967c5-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="967c5-116">Aby uzyskać więcej informacji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="967c5-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="967c5-117">Puste pole stanu dla niektórych rekordów żądań urlopów w Dataverse (414915)</span><span class="sxs-lookup"><span data-stu-id="967c5-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="967c5-118">Ta zmiana powoduje usunięcie błędu w Dataverse, gdy pole **Stan** w żądaniu urlopu jest ustawione na wartość **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="967c5-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="967c5-119">Dataverse teraz odzwierciedla stan.</span><span class="sxs-lookup"><span data-stu-id="967c5-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="967c5-120">Analiza braków kwalifikacji jest możliwa tylko dla przypisanego zadania (411390)</span><span class="sxs-lookup"><span data-stu-id="967c5-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="967c5-121">Można teraz przeprowadzić analizę braków kwalifikacji dla każdego zadania zdefiniowanego w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="967c5-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="967c5-122">Waluta systemowa nie jest synchronizowana z Dataverse do Human Resources w nowych środowiskach (418011)</span><span class="sxs-lookup"><span data-stu-id="967c5-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="967c5-123">Waluta systemowa w Dataverse może teraz być synchronizowana z Human Resources.</span><span class="sxs-lookup"><span data-stu-id="967c5-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="967c5-124">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="967c5-124">In preview</span></span>

- [<span data-ttu-id="967c5-125">Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="967c5-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="967c5-126">Funkcje zarządzania świadczeniami w wersji zapoznawczej: zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="967c5-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="967c5-127">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="967c5-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="967c5-128">Zaktualizowano rozwiązanie Dataverse</span><span class="sxs-lookup"><span data-stu-id="967c5-128">Updated Dataverse solution</span></span>

<span data-ttu-id="967c5-129">Nowe rozwiązanie Dataverse będzie dostępne wkrótce z następującymi zmianami:</span><span class="sxs-lookup"><span data-stu-id="967c5-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="967c5-130">Opis</span><span class="sxs-lookup"><span data-stu-id="967c5-130">Description</span></span> | <span data-ttu-id="967c5-131">Zmiana</span><span class="sxs-lookup"><span data-stu-id="967c5-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="967c5-132">Zmiany encji **Zatrudnienie/Stanowisko**</span><span class="sxs-lookup"><span data-stu-id="967c5-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="967c5-133">Dodano **Region wynagrodzenia**</span><span class="sxs-lookup"><span data-stu-id="967c5-133">**Compensation region** added</span></span></br><span data-ttu-id="967c5-134">Dodano **wymiary finansowe**</span><span class="sxs-lookup"><span data-stu-id="967c5-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="967c5-135">Zmiany jednostki **Pracownik**</span><span class="sxs-lookup"><span data-stu-id="967c5-135">**Worker** entity changes</span></span> | <span data-ttu-id="967c5-136">Dodano **Kolejność w nazwisku**</span><span class="sxs-lookup"><span data-stu-id="967c5-136">**Name sequence** added</span></span></br><span data-ttu-id="967c5-137">Dodano **Pracuje z domu**</span><span class="sxs-lookup"><span data-stu-id="967c5-137">**Works from home** added</span></span></br><span data-ttu-id="967c5-138">Dodano **Język**</span><span class="sxs-lookup"><span data-stu-id="967c5-138">**Language** added</span></span></br><span data-ttu-id="967c5-139">Dodano **Data stażu pracy**</span><span class="sxs-lookup"><span data-stu-id="967c5-139">**Seniority date** added</span></span></br><span data-ttu-id="967c5-140">Dodano **Rocznica**</span><span class="sxs-lookup"><span data-stu-id="967c5-140">**Anniversary date** added</span></span></br><span data-ttu-id="967c5-141">Dodano **Pierwotna data zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="967c5-141">**Original hire date** added</span></span> |
| <span data-ttu-id="967c5-142">Zmiany jednostki **Zatrudnienie**</span><span class="sxs-lookup"><span data-stu-id="967c5-142">**Employment** entity changes</span></span> | <span data-ttu-id="967c5-143">Dodano **wymiary finansowe**</span><span class="sxs-lookup"><span data-stu-id="967c5-143">**Financial dimensions** added</span></span></br><span data-ttu-id="967c5-144">Dodano **Powód rozwiązania umowy**</span><span class="sxs-lookup"><span data-stu-id="967c5-144">**Termination reason** added</span></span></br><span data-ttu-id="967c5-145">**Data zakończenia** zmieniona z **daty przejścia**</span><span class="sxs-lookup"><span data-stu-id="967c5-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="967c5-146">Dodano **Okres próbny**</span><span class="sxs-lookup"><span data-stu-id="967c5-146">**Probation date** added</span></span> |
| <span data-ttu-id="967c5-147">Zmiany jednostki **Adres Pracownika**</span><span class="sxs-lookup"><span data-stu-id="967c5-147">**Worker address** entity changes</span></span> | <span data-ttu-id="967c5-148">Dodano **Ulica**</span><span class="sxs-lookup"><span data-stu-id="967c5-148">**Street address** added</span></span></br><span data-ttu-id="967c5-149">**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania</span><span class="sxs-lookup"><span data-stu-id="967c5-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="967c5-150">Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="967c5-150">New variable compensation setup entities</span></span> | <span data-ttu-id="967c5-151">**Typ planu wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="967c5-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="967c5-152">**Plan wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="967c5-152">**Compensation variable plan**</span></span></br><span data-ttu-id="967c5-153">**Reguły wypłat**</span><span class="sxs-lookup"><span data-stu-id="967c5-153">**Vesting rules**</span></span></br><span data-ttu-id="967c5-154">**Poziom planu wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="967c5-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="967c5-155">Nowa jednostka **Zatrudnienie kalendarza pracownika**</span><span class="sxs-lookup"><span data-stu-id="967c5-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="967c5-156">Dodano **jednostkę kalendarza pracy**</span><span class="sxs-lookup"><span data-stu-id="967c5-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="967c5-157">Nowa jednostka **Szczegół stanowiska listy płac**</span><span class="sxs-lookup"><span data-stu-id="967c5-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="967c5-158">Dodano **Szczegół stanowiska listy płac**</span><span class="sxs-lookup"><span data-stu-id="967c5-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="967c5-159">Nowa jednostka **Tytuł**</span><span class="sxs-lookup"><span data-stu-id="967c5-159">New **Title** entity</span></span> | <span data-ttu-id="967c5-160">Dodano **Tytuł**.</span><span class="sxs-lookup"><span data-stu-id="967c5-160">**Title** added.</span></span> <span data-ttu-id="967c5-161">Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="967c5-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="967c5-162">Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**.</span><span class="sxs-lookup"><span data-stu-id="967c5-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="967c5-163">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="967c5-163">See also</span></span>

[<span data-ttu-id="967c5-164">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="967c5-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="967c5-165">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="967c5-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="967c5-166">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="967c5-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="967c5-167">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="967c5-167">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]