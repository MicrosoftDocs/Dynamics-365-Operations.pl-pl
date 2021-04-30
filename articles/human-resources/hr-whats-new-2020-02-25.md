---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (25 lutego 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 25 lutego 2020 roku.
author: andreabichsel
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e0ff8fa382ea186426b6f6ceff6044dc35496373
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893383"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="a661c-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (25 lutego 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="a661c-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a661c-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a661c-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a661c-105">Zmiany dotyczą kompilacji o numerze 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="a661c-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="a661c-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="a661c-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="a661c-107">Włącz jednostkę nawigacji zarządzania sprawami i narzędzia do zarządzania danymi (DMF) (414754)</span><span class="sxs-lookup"><span data-stu-id="a661c-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="a661c-108">Ta funkcja podglądu umożliwia dodatkową nawigację w przypadkach zarządzania sprawami.</span><span class="sxs-lookup"><span data-stu-id="a661c-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="a661c-109">Tę funkcję podglądu można włączyć w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="a661c-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="a661c-110">Te elementy menu są wyświetlane w obszarze roboczym **Zgodność** programu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a661c-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a661c-111">W przypadku tej zmiany usługa Human Resources może uzyskiwać dostęp do:</span><span class="sxs-lookup"><span data-stu-id="a661c-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="a661c-112">Wszystkie sprawy</span><span class="sxs-lookup"><span data-stu-id="a661c-112">All cases</span></span>
- <span data-ttu-id="a661c-113">Moje sprawy</span><span class="sxs-lookup"><span data-stu-id="a661c-113">My cases</span></span>
- <span data-ttu-id="a661c-114">Moje otwarte sprawy</span><span class="sxs-lookup"><span data-stu-id="a661c-114">My open cases</span></span>
- <span data-ttu-id="a661c-115">Moje zaległe sprawy</span><span class="sxs-lookup"><span data-stu-id="a661c-115">My overdue cases</span></span>
- <span data-ttu-id="a661c-116">Sprawy przypisane do mnie za pośrednictwem przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a661c-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="a661c-117">Wraz z tymi nowymi widokami dostępna jest również jednostka DMF **Szczegóły sprawy**.</span><span class="sxs-lookup"><span data-stu-id="a661c-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="a661c-118">Włącz definicje relacji w globalnej książce adresowej (414762)</span><span class="sxs-lookup"><span data-stu-id="a661c-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="a661c-119">Relacje są teraz włączone w globalnej książce adresowej.</span><span class="sxs-lookup"><span data-stu-id="a661c-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="a661c-120">Przed wydaniem z tego tygodnia pole informacji **relacji** wyświetlało wszystkie relacje zdefiniowane w systemie.</span><span class="sxs-lookup"><span data-stu-id="a661c-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="a661c-121">Teraz można zdefiniować te relacje na stronie globalnej książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="a661c-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="a661c-122">W przypadku istnienia aktywnych rekordów wynagrodzeń dla danego stanowiska można usunąć stanowisko (414568)</span><span class="sxs-lookup"><span data-stu-id="a661c-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="a661c-123">Przy tej zmianie zostanie wyświetlone ostrzeżenie podczas próby usunięcia stanowiska, jeśli pracownik ma aktywny rekord wynagrodzenia dla tego samego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="a661c-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="a661c-124">W takim przypadku należy zaktualizować rekord stałego wynagrodzenia pracownika przed usunięciem stanowiska.</span><span class="sxs-lookup"><span data-stu-id="a661c-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="a661c-125">Przepływ pracy recenzji wydajności okazjonalnie dodaje podpisy, które nie są częścią procesu (414171)</span><span class="sxs-lookup"><span data-stu-id="a661c-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="a661c-126">Ta zmiana powoduje usunięcie problemy, gdy do przeglądu wydajności zostaną dodane dodatkowi podpisani uczestnicy.</span><span class="sxs-lookup"><span data-stu-id="a661c-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="a661c-127">Przypisanie stanowiska roboczego nie zostało utworzone w Dataverse w przypadku wybrania opcji w oknie dialogowym Nowy pracownik (413479)</span><span class="sxs-lookup"><span data-stu-id="a661c-127">Worker position assignment not created in Dataverse when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="a661c-128">Ta zmiana powoduje usunięcie błędu podczas zatrudniania nowego pracownika i przypisywania nowego zatrudnienia do stanowiska za pośrednictwem okna dialogowego **Nowy pracownik**.</span><span class="sxs-lookup"><span data-stu-id="a661c-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="a661c-129">Przypisana pozycja jest teraz odzwierciedlona w programie Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a661c-129">Now the position assignment is reflected in Dataverse.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a661c-130">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="a661c-130">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="a661c-131">Zaktualizowano rozwiązanie Dataverse</span><span class="sxs-lookup"><span data-stu-id="a661c-131">Updated Dataverse solution</span></span>

<span data-ttu-id="a661c-132">Nowe rozwiązanie Dataverse będzie dostępne wkrótce z następującymi zmianami:</span><span class="sxs-lookup"><span data-stu-id="a661c-132">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="a661c-133">Opis</span><span class="sxs-lookup"><span data-stu-id="a661c-133">Description</span></span> | <span data-ttu-id="a661c-134">Zmiana</span><span class="sxs-lookup"><span data-stu-id="a661c-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="a661c-135">Zmiany encji **Zatrudnienie/Stanowisko**</span><span class="sxs-lookup"><span data-stu-id="a661c-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="a661c-136">Dodano **Region wynagrodzenia**</span><span class="sxs-lookup"><span data-stu-id="a661c-136">**Compensation region** added</span></span></br><span data-ttu-id="a661c-137">Dodano **wymiary finansowe**</span><span class="sxs-lookup"><span data-stu-id="a661c-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="a661c-138">Zmiany jednostki **Pracownik**</span><span class="sxs-lookup"><span data-stu-id="a661c-138">**Worker** entity changes</span></span> | <span data-ttu-id="a661c-139">Dodano **Kolejność w nazwisku**</span><span class="sxs-lookup"><span data-stu-id="a661c-139">**Name sequence** added</span></span></br><span data-ttu-id="a661c-140">Dodano **Pracuje z domu**</span><span class="sxs-lookup"><span data-stu-id="a661c-140">**Works from home** added</span></span></br><span data-ttu-id="a661c-141">Dodano **Język**</span><span class="sxs-lookup"><span data-stu-id="a661c-141">**Language** added</span></span></br><span data-ttu-id="a661c-142">Dodano **Data stażu pracy**</span><span class="sxs-lookup"><span data-stu-id="a661c-142">**Seniority date** added</span></span></br><span data-ttu-id="a661c-143">Dodano **Rocznica**</span><span class="sxs-lookup"><span data-stu-id="a661c-143">**Anniversary date** added</span></span></br><span data-ttu-id="a661c-144">Dodano **Pierwotna data zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="a661c-144">**Original hire date** added</span></span> |
| <span data-ttu-id="a661c-145">Zmiany jednostki **Zatrudnienie**</span><span class="sxs-lookup"><span data-stu-id="a661c-145">**Employment** entity changes</span></span> | <span data-ttu-id="a661c-146">Dodano **wymiary finansowe**</span><span class="sxs-lookup"><span data-stu-id="a661c-146">**Financial dimensions** added</span></span></br><span data-ttu-id="a661c-147">Dodano **Powód rozwiązania umowy**</span><span class="sxs-lookup"><span data-stu-id="a661c-147">**Termination reason** added</span></span></br><span data-ttu-id="a661c-148">**Data zakończenia** zmieniona z **daty przejścia**</span><span class="sxs-lookup"><span data-stu-id="a661c-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="a661c-149">Dodano **Okres próbny**</span><span class="sxs-lookup"><span data-stu-id="a661c-149">**Probation date** added</span></span> |
| <span data-ttu-id="a661c-150">Zmiany jednostki **Adres Pracownika**</span><span class="sxs-lookup"><span data-stu-id="a661c-150">**Worker address** entity changes</span></span> | <span data-ttu-id="a661c-151">Dodano **Ulica**</span><span class="sxs-lookup"><span data-stu-id="a661c-151">**Street address** added</span></span></br><span data-ttu-id="a661c-152">**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania</span><span class="sxs-lookup"><span data-stu-id="a661c-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="a661c-153">Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="a661c-153">New variable compensation setup entities</span></span> | <span data-ttu-id="a661c-154">**Typ planu wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="a661c-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="a661c-155">**Plan wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="a661c-155">**Compensation variable plan**</span></span></br><span data-ttu-id="a661c-156">**Reguły wypłat**</span><span class="sxs-lookup"><span data-stu-id="a661c-156">**Vesting rules**</span></span></br><span data-ttu-id="a661c-157">**Poziom planu wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="a661c-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="a661c-158">Nowa jednostka **Zatrudnienie kalendarza pracownika**</span><span class="sxs-lookup"><span data-stu-id="a661c-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="a661c-159">Dodano **jednostkę kalendarza pracy**</span><span class="sxs-lookup"><span data-stu-id="a661c-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="a661c-160">Nowa jednostka **Szczegół stanowiska listy płac**</span><span class="sxs-lookup"><span data-stu-id="a661c-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="a661c-161">Dodano **Szczegół stanowiska listy płac**</span><span class="sxs-lookup"><span data-stu-id="a661c-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="a661c-162">Nowa jednostka **Tytuł**</span><span class="sxs-lookup"><span data-stu-id="a661c-162">New **Title** entity</span></span> | <span data-ttu-id="a661c-163">Dodano **Tytuł**.</span><span class="sxs-lookup"><span data-stu-id="a661c-163">**Title** added.</span></span> <span data-ttu-id="a661c-164">Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a661c-164">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="a661c-165">Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**.</span><span class="sxs-lookup"><span data-stu-id="a661c-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="a661c-166">W czasie następnych kilku tygodni zmiany tych jednostek będą dostępne we wszystkich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="a661c-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="a661c-167">Aby ręcznie zainstalować najnowsze rozwiązanie Dataverse dla modułu Human Resources:</span><span class="sxs-lookup"><span data-stu-id="a661c-167">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="a661c-168">Przejdź do [Centrum administracyjnego usługi Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a661c-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="a661c-169">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="a661c-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="a661c-170">Znajdź środowisko, które chcesz uaktualnić.</span><span class="sxs-lookup"><span data-stu-id="a661c-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="a661c-171">Powinno ono odpowiadać **nazwie środowiska** w sekcji **informacji programu Common Data Service** w formularzu **O** w usłudze Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a661c-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="a661c-172">Wybierz środowisko, aby wyświetlić szczegóły środowiska.</span><span class="sxs-lookup"><span data-stu-id="a661c-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="a661c-173">Wybierz przycisk **Zarządzaj rozwiązaniami** na pasku akcji u góry.</span><span class="sxs-lookup"><span data-stu-id="a661c-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="a661c-174">Zostanie otwarte nowe okno przeglądarki i przejście do **centrum administracyjnego systemu Dynamics 365** w kontekście środowiska użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a661c-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="a661c-175">Z listy **Rozwiązanie** wybierz pozycję **Zakotwiczenie Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="a661c-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="a661c-176">Wybierz opcję **Uaktualnij**, aby zastosować najnowsze rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="a661c-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a661c-177">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="a661c-177">In preview</span></span>

<span data-ttu-id="a661c-178">Następujące funkcje w wersji zapoznawczej zostały udostępnione 3 lutego 2020 r.:</span><span class="sxs-lookup"><span data-stu-id="a661c-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="a661c-179">**Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="a661c-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="a661c-180">**Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie obszaru roboczego Zarządzanie świadczeniami](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a661c-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a661c-181">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a661c-181">See also</span></span>

[<span data-ttu-id="a661c-182">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="a661c-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a661c-183">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="a661c-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a661c-184">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="a661c-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a661c-185">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="a661c-185">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]