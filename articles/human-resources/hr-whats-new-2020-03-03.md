---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (3 marca 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 3 marca 2020 roku.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e39e0c55fddffa99b0a86dba52da120b1ba0d1b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051144"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a><span data-ttu-id="1a16a-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (3 marca 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="1a16a-103">What's new or changed in Dynamics 365 Human Resources (March 3, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1a16a-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1a16a-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1a16a-105">Zmiany dotyczą kompilacji o numerze 8.1.2955.</span><span class="sxs-lookup"><span data-stu-id="1a16a-105">Changes apply to build number 8.1.2955.</span></span> <span data-ttu-id="1a16a-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="1a16a-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a><span data-ttu-id="1a16a-107">Rozwiązanie Dataverse jest teraz dostępne z następującymi zmianami:</span><span class="sxs-lookup"><span data-stu-id="1a16a-107">Dataverse solution is now available with the following changes:</span></span>

<span data-ttu-id="1a16a-108">Nowe rozwiązanie Dataverse będzie dostępne wkrótce z następującymi zmianami:</span><span class="sxs-lookup"><span data-stu-id="1a16a-108">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="1a16a-109">Opis</span><span class="sxs-lookup"><span data-stu-id="1a16a-109">Description</span></span> | <span data-ttu-id="1a16a-110">Zmiana</span><span class="sxs-lookup"><span data-stu-id="1a16a-110">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="1a16a-111">Zmiany encji **Zatrudnienie/Stanowisko**</span><span class="sxs-lookup"><span data-stu-id="1a16a-111">**Job/Position** entity changes</span></span> | <span data-ttu-id="1a16a-112">Dodano **Region wynagrodzenia**</span><span class="sxs-lookup"><span data-stu-id="1a16a-112">**Compensation region** added</span></span></br><span data-ttu-id="1a16a-113">Dodano **wymiary finansowe**</span><span class="sxs-lookup"><span data-stu-id="1a16a-113">**Financial dimensions** added</span></span> |
| <span data-ttu-id="1a16a-114">Zmiany jednostki **Pracownik**</span><span class="sxs-lookup"><span data-stu-id="1a16a-114">**Worker** entity changes</span></span> | <span data-ttu-id="1a16a-115">Dodano **Kolejność w nazwisku**</span><span class="sxs-lookup"><span data-stu-id="1a16a-115">**Name sequence** added</span></span></br><span data-ttu-id="1a16a-116">Dodano **Pracuje z domu**</span><span class="sxs-lookup"><span data-stu-id="1a16a-116">**Works from home** added</span></span></br><span data-ttu-id="1a16a-117">Dodano **Język**</span><span class="sxs-lookup"><span data-stu-id="1a16a-117">**Language** added</span></span></br><span data-ttu-id="1a16a-118">Dodano **Data stażu pracy**</span><span class="sxs-lookup"><span data-stu-id="1a16a-118">**Seniority date** added</span></span></br><span data-ttu-id="1a16a-119">Dodano **Rocznica**</span><span class="sxs-lookup"><span data-stu-id="1a16a-119">**Anniversary date** added</span></span></br><span data-ttu-id="1a16a-120">Dodano **Pierwotna data zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="1a16a-120">**Original hire date** added</span></span> |
| <span data-ttu-id="1a16a-121">Zmiany jednostki **Zatrudnienie**</span><span class="sxs-lookup"><span data-stu-id="1a16a-121">**Employment** entity changes</span></span> | <span data-ttu-id="1a16a-122">Dodano **wymiary finansowe**</span><span class="sxs-lookup"><span data-stu-id="1a16a-122">**Financial dimensions** added</span></span></br><span data-ttu-id="1a16a-123">Dodano **Powód rozwiązania umowy**</span><span class="sxs-lookup"><span data-stu-id="1a16a-123">**Termination reason** added</span></span></br><span data-ttu-id="1a16a-124">**Data zakończenia** zmieniona z **daty przejścia**</span><span class="sxs-lookup"><span data-stu-id="1a16a-124">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="1a16a-125">Dodano **Okres próbny**</span><span class="sxs-lookup"><span data-stu-id="1a16a-125">**Probation date** added</span></span> |
| <span data-ttu-id="1a16a-126">Zmiany jednostki **Adres Pracownika**</span><span class="sxs-lookup"><span data-stu-id="1a16a-126">**Worker address** entity changes</span></span> | <span data-ttu-id="1a16a-127">Dodano **Ulica**</span><span class="sxs-lookup"><span data-stu-id="1a16a-127">**Street address** added</span></span></br><span data-ttu-id="1a16a-128">**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania</span><span class="sxs-lookup"><span data-stu-id="1a16a-128">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="1a16a-129">Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="1a16a-129">New variable compensation setup entities</span></span> | <span data-ttu-id="1a16a-130">**Typ planu wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="1a16a-130">**Compensation variable plan type**</span></span></br><span data-ttu-id="1a16a-131">**Plan wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="1a16a-131">**Compensation variable plan**</span></span></br><span data-ttu-id="1a16a-132">**Reguły wypłat**</span><span class="sxs-lookup"><span data-stu-id="1a16a-132">**Vesting rules**</span></span></br><span data-ttu-id="1a16a-133">**Poziom planu wynagrodzeń o zmiennej wysokości**</span><span class="sxs-lookup"><span data-stu-id="1a16a-133">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="1a16a-134">Nowa jednostka **Zatrudnienie kalendarza pracownika**</span><span class="sxs-lookup"><span data-stu-id="1a16a-134">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="1a16a-135">Dodano **jednostkę kalendarza pracy**</span><span class="sxs-lookup"><span data-stu-id="1a16a-135">**Work calendar entity** added</span></span> |
| <span data-ttu-id="1a16a-136">Nowa jednostka **Szczegół stanowiska listy płac**</span><span class="sxs-lookup"><span data-stu-id="1a16a-136">New **Payroll position detail** entity</span></span> | <span data-ttu-id="1a16a-137">Dodano **Szczegół stanowiska listy płac**</span><span class="sxs-lookup"><span data-stu-id="1a16a-137">**Payroll position detail** added</span></span> |
| <span data-ttu-id="1a16a-138">Nowa jednostka **Tytuł**</span><span class="sxs-lookup"><span data-stu-id="1a16a-138">New **Title** entity</span></span> | <span data-ttu-id="1a16a-139">Dodano **Tytuł**.</span><span class="sxs-lookup"><span data-stu-id="1a16a-139">**Title** added.</span></span> <span data-ttu-id="1a16a-140">Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1a16a-140">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="1a16a-141">Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**.</span><span class="sxs-lookup"><span data-stu-id="1a16a-141">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="1a16a-142">W czasie następnych kilku tygodni zmiany tych jednostek będą dostępne we wszystkich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="1a16a-142">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="1a16a-143">Aby ręcznie zainstalować najnowsze rozwiązanie Dataverse dla modułu Human Resources:</span><span class="sxs-lookup"><span data-stu-id="1a16a-143">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="1a16a-144">Przejdź do [Centrum administracyjnego usługi Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1a16a-144">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="1a16a-145">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="1a16a-145">Select **Environments**.</span></span>

3.  <span data-ttu-id="1a16a-146">Znajdź środowisko, które chcesz uaktualnić.</span><span class="sxs-lookup"><span data-stu-id="1a16a-146">Find the environment you want to upgrade.</span></span> <span data-ttu-id="1a16a-147">Środowisko powinno odpowiadać **nazwie środowiska** w sekcji **informacji programu Common Data Service** w formularzu **O** w usłudze Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1a16a-147">The environment should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="1a16a-148">Wybierz środowisko, aby wyświetlić szczegóły środowiska.</span><span class="sxs-lookup"><span data-stu-id="1a16a-148">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="1a16a-149">Wybierz przycisk **Zarządzaj rozwiązaniami** na pasku akcji u góry.</span><span class="sxs-lookup"><span data-stu-id="1a16a-149">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="1a16a-150">Zostanie otwarte nowe okno przeglądarki i przejście do **centrum administracyjnego systemu Dynamics 365** w kontekście środowiska użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1a16a-150">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="1a16a-151">Z listy **Rozwiązanie** wybierz pozycję **Zakotwiczenie Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="1a16a-151">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="1a16a-152">Wybierz opcję **Uaktualnij**, aby zastosować najnowsze rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="1a16a-152">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a><span data-ttu-id="1a16a-153">Importowanie problemów z jednostką danych rejestracji urlopu (406082)</span><span class="sxs-lookup"><span data-stu-id="1a16a-153">Import issues with the Leave enrollment data entity (406082)</span></span>

<span data-ttu-id="1a16a-154">Można teraz zarejestrować pracownika w nowym planie dla urlopu tego samego typu, o ile nowa data rejestracji jest późniejsza niż data wygasłej rejestracji poprzedniego planu.</span><span class="sxs-lookup"><span data-stu-id="1a16a-154">You can now enroll an employee in a new leave plan of the same type, as long as the new enrollment date is later than the expired enrollment date of the previous plan.</span></span>

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a><span data-ttu-id="1a16a-155">Problem z eksportowaniem stóp składek w jednostce payrollWorkerEnrolledBenefitDetail 401k w DMF (420700)</span><span class="sxs-lookup"><span data-stu-id="1a16a-155">Issue with exporting contribution rates in the 401k payrollWorkerEnrolledBenefitDetail entity in DMF (420700)</span></span>

<span data-ttu-id="1a16a-156">Ta zmiana koryguje funkcję eksportu dla jednostki **payrollWorkerEnrolledBenefitDetail** w celu odzwierciedlenia bieżących wartości udziału pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="1a16a-156">This change corrects the export functionality for the **payrollWorkerEnrolledBenefitDetail** entity to reflect the current values for employer contribution.</span></span>

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a><span data-ttu-id="1a16a-157">Wyszukiwanie w usprawnionym formularzu Pracownik powoduje pojawienie się informacji, że pole Osoba musi być wypełnione (402525)</span><span class="sxs-lookup"><span data-stu-id="1a16a-157">Searching in the streamlined Worker form causes message saying Person field must be filled in (402525)</span></span>

<span data-ttu-id="1a16a-158">Podczas wyszukiwania pracownika etatowego nie będzie już wyświetlany komunikat z informacją, że należy wypełnić pole **osoba**.</span><span class="sxs-lookup"><span data-stu-id="1a16a-158">When you search for an employee, you'll no longer receive a message saying you must fill in the **Person** field.</span></span>

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a><span data-ttu-id="1a16a-159">Wartość pola uwagi nie jest renderowana w formularzu Dodaj więcej kwalifikacji (380134)</span><span class="sxs-lookup"><span data-stu-id="1a16a-159">Note field value doesn't render on the Add more skills form (380134)</span></span>

<span data-ttu-id="1a16a-160">Ta zmiana powoduje usunięcie zagadnienia podczas personalizowania formularza **Dodaj kolejne umiejętności** w module samoobsługowym pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="1a16a-160">This change corrects an issue when you personalize the **Add more skills** form in Employee self service.</span></span>

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a><span data-ttu-id="1a16a-161">Wiele planów stałych wynagrodzeń nie wygasa podczas przenoszenia pracowników etatowych (389466)</span><span class="sxs-lookup"><span data-stu-id="1a16a-161">Multiple fixed compensation plans don't expire when transferring employees (389466)</span></span>

<span data-ttu-id="1a16a-162">W przypadku zmiany wszystkie aktywne rekordy stałego wynagrodzenia dla starego stanowiska wygasną w dniu przejścia.</span><span class="sxs-lookup"><span data-stu-id="1a16a-162">With this change, all active fixed compensation records for the old position will expire on the transition date.</span></span>

## <a name="in-preview"></a><span data-ttu-id="1a16a-163">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="1a16a-163">In preview</span></span>

<span data-ttu-id="1a16a-164">Następujące funkcje w wersji zapoznawczej zostały udostępnione 3 lutego 2020 r.:</span><span class="sxs-lookup"><span data-stu-id="1a16a-164">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="1a16a-165">**Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="1a16a-165">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="1a16a-166">**Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie obszaru roboczego Zarządzanie świadczeniami](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a16a-166">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a16a-167">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1a16a-167">See also</span></span>

[<span data-ttu-id="1a16a-168">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="1a16a-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="1a16a-169">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="1a16a-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="1a16a-170">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="1a16a-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="1a16a-171">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="1a16a-171">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]