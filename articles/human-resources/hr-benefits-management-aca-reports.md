---
title: Generuj raporty Affordable Care Act w zarządzaniu świadczeniami
description: W tym temacie opisano, w jaki sposób zarządzanie świadczeniami pomaga w śledzeniu informacji, które są zgłaszane na formularzu 1095-B i formularzu 1095-C dotyczącym mandatu pracodawcy na podstawie ustawy o przystępnej opiece (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 24df18f428e4ca14859bc34048a6bda5e03d1b2f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464381"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="6f6ca-103">Generowanie raportów ACA w zarządzaniu świadczeniami</span><span class="sxs-lookup"><span data-stu-id="6f6ca-103">Generate ACA reports in Benefits management</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6f6ca-104">W jaki sposób zarządzanie świadczeniami pomaga w śledzeniu informacji, które są zgłaszane na formularzu 1095-B i formularzu 1095-C dotyczącym mandatu pracodawcy na podstawie ustawy o przystępnej opiece (ACA).</span><span class="sxs-lookup"><span data-stu-id="6f6ca-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="6f6ca-105">Podobnie jak funkcja raportowania ACA w starym obszarze roboczym **Świadczenia**, ta funkcja dotyczy wyłącznie firm w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="6f6ca-106">Aby korzystać z tej funkcji, należy najpierw włączyć **Zarządzanie zaawansowanymi świadczeniami**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="6f6ca-107">Aby uzyskać więcej informacji, w tym ważne informacje dotyczące zarządzania świadczeniami, zobacz temat [Włączanie lub wyłączanie funkcji zarządzania świadczeniami](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="6f6ca-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f6ca-108">Raportowania ACA można używać tylko z obszaru roboczego **Zarządzanie świadczeniami** lub starego obszaru roboczego **Świadczenia**, a nie z obu tych obszarów.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="6f6ca-109">Na przykład po przełączeniu do obszaru roboczego Zarządzanie świadczeniami raportowanie ACA jest dostępne tylko z obszaru roboczego **Zarządzanie świadczeniami**, a nie ze starego obszaru roboczego **Świadczenia**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="6f6ca-110">Jeśli przełączysz się na zarządzanie świadczeniami w środku roku rejestracji, musisz poprawnie skonfigurować dane pracowników za cały rok w Zarządzaniu świadczeniami.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="6f6ca-111">Zapewnia to otrzymywanie dokładnych informacji dotyczących raportowania przez cały rok.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="6f6ca-112">Rozpoczęcie pracy</span><span class="sxs-lookup"><span data-stu-id="6f6ca-112">Getting started</span></span>

<span data-ttu-id="6f6ca-113">Aby śledzić informacje dotyczące formularzy 1095, najpierw utwórz jedną lub więcej grup objętych usługą Affordable Care.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="6f6ca-114">Grupy te wskazują następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="6f6ca-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="6f6ca-115">Oferta świadczenia dostarczonego pracownikowi</span><span class="sxs-lookup"><span data-stu-id="6f6ca-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="6f6ca-116">Udział pracownika w najniższej miesięcznej składce, jeśli koszt przekracza federalną granicę ubóstwa</span><span class="sxs-lookup"><span data-stu-id="6f6ca-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="6f6ca-117">Program „Bezpieczna Przystań” używany przez pracodawcę, jeśli ma zastosowanie</span><span class="sxs-lookup"><span data-stu-id="6f6ca-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="6f6ca-118">Grupy objęcia świadczeniami ACA pomagają w zarządzaniu informacjami w przypadku wielu rekordów pracowników, które mają te same warunki.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="6f6ca-119">Grupy można łatwo przypisywać do jednego lub większej liczby pracowników.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="6f6ca-120">Utwórz lub edytuj grupę ubezpieczenia w przystępnej cenie</span><span class="sxs-lookup"><span data-stu-id="6f6ca-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="6f6ca-121">W obszarze roboczym **Zarządzanie świadczeniami** wybierz **Grupa ubezpieczeniowa Affordable Care**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Wybieranie grupy Affordable Care](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="6f6ca-123">Wybierz pozycję **Nowy**, aby utworzyć nową grupę pokrycia Affordable Care lub **Edytuj**, aby zmienić istniejącą grupę.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Wybieranie nowej lub edycji](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="6f6ca-125">Ustaw wartości w następujących polach.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-125">Set the following fields.</span></span>

    | <span data-ttu-id="6f6ca-126">Pole</span><span class="sxs-lookup"><span data-stu-id="6f6ca-126">Field</span></span> | <span data-ttu-id="6f6ca-127">opis</span><span class="sxs-lookup"><span data-stu-id="6f6ca-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="6f6ca-128">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="6f6ca-128">Name</span></span> | <span data-ttu-id="6f6ca-129">Umożliwia wprowadzenie nazwy grupy.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="6f6ca-130">opis</span><span class="sxs-lookup"><span data-stu-id="6f6ca-130">Description</span></span> | <span data-ttu-id="6f6ca-131">Służy do wprowadzania opisu grupy.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="6f6ca-132">Oferta świadczenia</span><span class="sxs-lookup"><span data-stu-id="6f6ca-132">Offer of coverage</span></span> | <span data-ttu-id="6f6ca-133">Ubezpieczenie oferowane pracownikom, ich małżonkom lub partnerom oraz osobom na ich utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="6f6ca-134">Udział pracownika w koszcie</span><span class="sxs-lookup"><span data-stu-id="6f6ca-134">Employee share of cost</span></span> | <span data-ttu-id="6f6ca-135">Kwota, za którą odpowiada pracownik.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="6f6ca-136">Odpowiednia sekcja 4980H w zakresie struktury zabezpieczeń informacji (program Safe Harbor)</span><span class="sxs-lookup"><span data-stu-id="6f6ca-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="6f6ca-137">Kod bezpiecznej przystani 4980H lub kod zwolnienia w okresie przejściowym.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="6f6ca-138">Miesiąc rozpoczęcia planu</span><span class="sxs-lookup"><span data-stu-id="6f6ca-138">Plan start month</span></span> | <span data-ttu-id="6f6ca-139">Wybierz miesiąc kalendarzowy, w którym rozpoczyna się rok planu świadczeń.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="6f6ca-140">Grupa ważna od</span><span class="sxs-lookup"><span data-stu-id="6f6ca-140">Group valid from</span></span> | <span data-ttu-id="6f6ca-141">Data, od kiedy ten rekord jest ważny.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="6f6ca-142">Grupa ważna do</span><span class="sxs-lookup"><span data-stu-id="6f6ca-142">Group valid through</span></span> | <span data-ttu-id="6f6ca-143">Ostatnia data ważności tego rekordu.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-143">The last date when this record is valid.</span></span> <span data-ttu-id="6f6ca-144">Jeśli nie ma daty ważności, wprowadź wartość **Nigdy**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Tworzenie grupy zapotrzebowania](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="6f6ca-146">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="6f6ca-147">Przydziel wielu pracowników do grupy objętej usługą Affordable Care</span><span class="sxs-lookup"><span data-stu-id="6f6ca-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="6f6ca-148">W obszarze roboczym **Zarządzanie świadczeniami** wybierz **Grupa ubezpieczeniowa Affordable Care**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="6f6ca-149">Wybierz grupę, do których mają zostać przypisani pracownicy.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="6f6ca-150">Wybierz **Przypisanie grupowe**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-150">Select **Mass assignment**.</span></span>

    ![Wybierz Przypisanie grupowe](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="6f6ca-152">Wybierz pracowników z listy, a następnie **Przypisz**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Przydzielanie wybranych pracowników do grupy](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="6f6ca-154">Utrzymuj wiele wersji opcji pokrycia</span><span class="sxs-lookup"><span data-stu-id="6f6ca-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="6f6ca-155">Możesz utrzymywać wiele wersji dowolnej grupy pokrycia.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="6f6ca-156">Gdy coś się zmieni w Twojej organizacji lub w oferowanych korzyściach, możesz aktualizować informacje o grupie bez konieczności tworzenia nowej grupy i ponownego przypisywania do niej pracowników.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="6f6ca-157">Po utworzeniu grup ubezpieczenia w przystępnej cenie Affordable Care możesz masowo przypisywać do nich pracowników.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="6f6ca-158">Możesz również indywidualnie przypisywać pracowników do grup i wskazywać, czy informacje ACA są śledzone i raportowane.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="6f6ca-159">Jeśli nie ma potrzeby śledzenia i zgłaszania informacji ACA pracownika, w opcji **Zgłaszaj objęcie świadczeniem** można ustawić wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="6f6ca-160">Na przykład mogą to być pracownicy na część czasu, którzy nie wymagają zgłaszania do ACA.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="6f6ca-161">Zastępowanie wartości domyślnych dla pracownika</span><span class="sxs-lookup"><span data-stu-id="6f6ca-161">Override default values for an employee</span></span>

<span data-ttu-id="6f6ca-162">W przypadku pracowników przypisanych do grupy ACA można zmienić następujące opcje na dowolne miesiące wymagające różnych wartości:</span><span class="sxs-lookup"><span data-stu-id="6f6ca-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="6f6ca-163">Oferta świadczenia</span><span class="sxs-lookup"><span data-stu-id="6f6ca-163">Offer of coverage</span></span>
- <span data-ttu-id="6f6ca-164">Udział pracownika w koszcie</span><span class="sxs-lookup"><span data-stu-id="6f6ca-164">Employee share of cost</span></span>
- <span data-ttu-id="6f6ca-165">Odpowiednia sekcja 4980H w zakresie struktury zabezpieczeń informacji (program Safe Harbor)</span><span class="sxs-lookup"><span data-stu-id="6f6ca-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="6f6ca-166">W przypadku zgłoszeń ACA 2020 raporty pracy i kody pocztowe są raportami w formularzu 1095-C.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="6f6ca-167">Wartości są wypełniane automatycznie na podstawie bieżących aktywnych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="6f6ca-168">Jeśli w trakcie dowolnej części roku każda z tych lokalizacji różniła się między lokalizacjami, należy zastąpić tę wartość.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="6f6ca-169">Pole **Kod pocztowy** (wiersz 17) raportu 1095-C jest wypełniane tylko w przypadku, gdy kod **Oferta świadczenia** zawiera kod od **1L** do **1Q**, w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6f6ca-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="6f6ca-170">**1L, 1M lub 1N:** kod pocztowy siedziby głównej</span><span class="sxs-lookup"><span data-stu-id="6f6ca-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="6f6ca-171">**1O, 1P, 1Q:** główny kod pocztowy pracy</span><span class="sxs-lookup"><span data-stu-id="6f6ca-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="6f6ca-172">Aby wprowadzić wyjątki dla dowolnej wartości grupy świadczeń Affordable Care, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="6f6ca-173">W obszarze roboczym **Zarządzanie personelem** wybierz opcję **Łącza**, a następnie wybierz **Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="6f6ca-174">Na liście zaznacz pracownika.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="6f6ca-175">Na karcie **Zatrudnienie** w sekcji **Więcej informacji** wybierz opcję **Świadczenia ACA**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Zmienianie opcji dla jednego pracownika](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="6f6ca-177">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-177">Select **Edit**.</span></span>
5. <span data-ttu-id="6f6ca-178">Dla każdego miesiąca wymagającego zmian zaznacz pole wyboru **Zastąp domyślne**, a następnie w razie potrzeby zmień inne wartości.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Zastępowanie wartości domyślnych](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="6f6ca-180">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="6f6ca-181">Zgłoś objęcie świadczeniem zdrowotnym</span><span class="sxs-lookup"><span data-stu-id="6f6ca-181">Report health care coverage</span></span>

<span data-ttu-id="6f6ca-182">Musisz śledzić wszystkie ubezpieczenia zdrowotne sponsorowane przez pracodawcę, ubezpieczone przez samych siebie, dla pracowników zatrudnionych w pełnym i niepełnym wymiarze godzin.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="6f6ca-183">Uwzględnij każdego pracownika razem z ich na utrzymaniu w raporcie 1095-C dla miesięcy, w których zostały objęte.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="6f6ca-184">Aby wskazać, czy ma zostać zgłoszony plan świadczeń, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="6f6ca-185">W obszarze roboczym **Zarządzanie świadczeniami** wybierz opcję **Plany świadczeń**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="6f6ca-186">Wybierz program świadczeń do zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="6f6ca-187">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-187">Select **Edit**.</span></span>
4. <span data-ttu-id="6f6ca-188">Ustaw wartość opcji **Zgłoszone do Affordable Care Act** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Zgłaszanie objęcia świadczeniem zdrowotnym](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="6f6ca-190">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-190">Select **Save**.</span></span>

<span data-ttu-id="6f6ca-191">Jeśli pracownik wybiera ubezpieczenie zdrowotne dla osoby pozostającej na utrzymaniu, okres ubezpieczenia osoby pozostającej na utrzymaniu jest określany na podstawie daty zapisania lub usunięcia osoby pozostającej na utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="6f6ca-192">Daty ubezpieczenia osób pozostających na utrzymaniu są obliczane automatycznie na podstawie okresu, w którym osoba pozostająca na utrzymaniu kwalifikowała się i była aktywna w ramach planu w ciągu roku rejestracji.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="6f6ca-193">Generowanie formularzy 1095-B i 1095-C</span><span class="sxs-lookup"><span data-stu-id="6f6ca-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="6f6ca-194">Formularze 1095-B i 1095-C ACA można również wygenerować i rozesłać je odnośnym pracownikom.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="6f6ca-195">Możesz również wygenerować elektronicznie formularz 1095-C i odpowiednie pliki przekazu 1094-C, aby wysłać je do Internal Revenue Service (IRS).</span><span class="sxs-lookup"><span data-stu-id="6f6ca-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="6f6ca-196">W obszarze roboczym **Zarządzanie świadczeniami** wybierz formularz **ACA 1095-B** lub formularz **ACA 1095-C**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="6f6ca-197">W razie potrzeby zmień parametry i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f6ca-198">W wypadku drukowania formularzy 1095-C dla więcej niż 500 pracowników otrzymasz więcej niż jeden plik PDF.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="6f6ca-199">Zaleca się zwiększenie wartości pola **Maksymalny rozmiar pliku w megabajtach** na stronie **Parametry zarządzania dokumentami** do **150**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="6f6ca-200">(Aby szybko otworzyć tę stronę, można użyć pola wyszukiwania na pasku nawigacji.)</span><span class="sxs-lookup"><span data-stu-id="6f6ca-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![Zmienianie maksymalnego rozmiaru pliku](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="6f6ca-202">Aby sprawdzić stan raportów i wyświetlić je, użyj pola wyszukiwania na pasku nawigacyjnym, aby otworzyć stronę **Zadania raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Wyszukiwanie strony zadań raportowania elektronicznego](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="6f6ca-204">Wybierz raport do wyświetlenia, a następnie wybierz polecenie **Pokaż pliki**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-204">Select the report to view, and then select **Show files**.</span></span>

    ![Wyświetlanie plików](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="6f6ca-206">Kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-206">Select **Open**.</span></span>

    ![Otwieranie pliku](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="6f6ca-208">Na pasku powiadomień w dolnej części okna przeglądarki otwórz plik ZIP, a następnie wybierz raport.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="6f6ca-209">Plik PDF można wyświetlić lub wydrukować.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-209">You can view or print the PDF file.</span></span>

    ![Przykładowy formularz 1095-C](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="6f6ca-211">Wyświetlanie informacji o świadczeniach ACA</span><span class="sxs-lookup"><span data-stu-id="6f6ca-211">View ACA coverage information</span></span>

<span data-ttu-id="6f6ca-212">Na stronie **Świadczenia Worker Affordable Care** dla pracownika są podane następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="6f6ca-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="6f6ca-213">Pracownicy przypisani do poszczególnych grup świadczeń</span><span class="sxs-lookup"><span data-stu-id="6f6ca-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="6f6ca-214">Pracownicy, którzy nie muszą być uwzględniani w raporcie</span><span class="sxs-lookup"><span data-stu-id="6f6ca-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="6f6ca-215">Nieprzypisani pracownicy</span><span class="sxs-lookup"><span data-stu-id="6f6ca-215">Unassigned employees</span></span>

<span data-ttu-id="6f6ca-216">Aby wyświetlić informacje, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="6f6ca-217">W obszarze roboczym **Zarządzanie świadczeniami** wybierz **Pracownik objęty ubezpieczeniem Affordable Care**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="6f6ca-218">W polu **Nazwa grupy** wprowadź grupę.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-218">In the **Group name** field, select a group.</span></span>

    ![Wyświetlanie świadczeń ACA](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="6f6ca-220">Jeśli którakolwiek domyślna wartość grupy objętej świadczeniem ACA zostanie zastąpiona, obok niej będzie widoczna gwiazdka.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="6f6ca-221">Jeśli wartości dla wszystkich dwunastu miesięcy są takie same i nie zostały zastąpione, wartość zostanie wydrukowana w kolumnie **Wszystkie 12 miesięcy**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="6f6ca-222">Można wyświetlać pracowników, których oznaczono jako nie podlega zgłoszenia ACA i którzy nie wymagają formularza 1095-C.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="6f6ca-223">W polu **Filtruj według** wybierz opcję **Nie do zgłoszenia do ACA**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="6f6ca-224">Można wyświetlać pracowników, którzy nie są przypisani do grupy lub są przypisani do grupy, których ważność wygasła.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="6f6ca-225">W polu **Filtruj według** wybierz grupę **Nieprzypisane lub Wygasłe**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="6f6ca-226">Eksportuj do programu Excel</span><span class="sxs-lookup"><span data-stu-id="6f6ca-226">Export to Excel</span></span>

<span data-ttu-id="6f6ca-227">Aby wyeksportować dowolną z list do programu Microsoft Excel, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="6f6ca-228">Wybierz przycisk **Otwórz w pakiecie Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="6f6ca-229">Wybierz **Tymczasowa tabela HCM Human Resources do użytku wewnętrznego**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="6f6ca-230">Wybierz opcję **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="6f6ca-231">Wyświetlanie osób na utrzymaniu podlegających świadczeniom ACA</span><span class="sxs-lookup"><span data-stu-id="6f6ca-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="6f6ca-232">Jeśli trzeba zgłosić osoby objęte świadczeniem, ponieważ zapewnia się objęcie ubezpieczeniam własnym, można wyświetlać osoby na utrzymaniu objęte planami świadczeń oznaczonymi jako **Objęte zgłoszeniem do ACA**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="6f6ca-233">Na okienku akcji wybierz opcję **Wyświetl świadczenia osób na utrzymaniu**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Wyświetlanie zakresu osób na utrzymaniu](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="6f6ca-235">Wyświetlane są informacje o świadczeniach osób na utrzymaniu pracownika.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-235">Coverage information for the employee's dependents is shown.</span></span>

![Świadczenie dla osoby na utrzymaniu](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="6f6ca-237">Na stronie są dostępne tylko plany świadczeń oznaczone jako **objęte zgłoszeniem do ACA**.</span><span class="sxs-lookup"><span data-stu-id="6f6ca-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]