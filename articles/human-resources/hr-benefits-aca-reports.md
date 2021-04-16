---
title: Generowanie raportów do amerykańskiej ustawy o powszechnym dostępie do opieki zdrowotnej (Affordable Care Act, ACA)
description: Sprawozdawczość ACA (ACA) generuje formularze 1095-B i 1095-C na podstawie części z **Upoważnieniem pracodawcy** w ustawieACA.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 055de1f0ff3f8fd4fadba0a685fd703b9d19d918
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5806001"
---
# <a name="generate-aca-reports"></a><span data-ttu-id="7967b-103">Generowanie raportów ACA</span><span class="sxs-lookup"><span data-stu-id="7967b-103">Generate ACA reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7967b-104">Sprawozdawczość ACA (ACA) generuje formularze 1095-B i 1095-C na podstawie części z **Upoważnieniem pracodawcy** w ustawieACA.</span><span class="sxs-lookup"><span data-stu-id="7967b-104">Affordable Care Act (ACA) reporting generates forms 1095-B and 1095-C in support of the **Employer Mandate** portion of the Affordable Care Act.</span></span>

> [!NOTE]
> <span data-ttu-id="7967b-105">Raportowanie ACA jest włączone tylko dla firm w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="7967b-105">ACA reporting is only enabled for legal entities in the United States.</span></span>

## <a name="getting-started"></a><span data-ttu-id="7967b-106">Rozpoczęcie pracy</span><span class="sxs-lookup"><span data-stu-id="7967b-106">Getting started</span></span>

<span data-ttu-id="7967b-107">Aby śledzić informacje dla formularzy 1095-B i 1095-C, musisz najpierw utworzyć jedną lub więcej grup objętych opieką w przystępnej cenie.</span><span class="sxs-lookup"><span data-stu-id="7967b-107">To track information for forms 1095-B and 1095-C, you must first create one or more Affordable care coverage groups.</span></span> <span data-ttu-id="7967b-108">Grupy ubezpieczeniowe w przystępnej cenie wskazują:</span><span class="sxs-lookup"><span data-stu-id="7967b-108">Affordable Care coverage groups indicate:</span></span>

- <span data-ttu-id="7967b-109">Oferta świadczenia dla pracownika</span><span class="sxs-lookup"><span data-stu-id="7967b-109">The offer of coverage for an employee</span></span>
- <span data-ttu-id="7967b-110">Udział pracownika w najniższej miesięcznej składce, jeśli koszt przekracza federalną granicę ubóstwa</span><span class="sxs-lookup"><span data-stu-id="7967b-110">The employee’s share of the lowest cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="7967b-111">Bezpieczna Przystań, z którego korzysta pracodawca, jeśli ma to zastosowanie</span><span class="sxs-lookup"><span data-stu-id="7967b-111">Safe Harbor used by the employer, if applicable</span></span>

<span data-ttu-id="7967b-112">Grupy ubezpieczenia Affordable Care pozwalają na zarządzanie informacjami w tych polach bez zmiany każdego rekordu pracownika, gdy warunki są takie same.</span><span class="sxs-lookup"><span data-stu-id="7967b-112">Affordable Care coverage groups allow you to manage the information for these fields without changing every employee record where the conditions are the same.</span></span> <span data-ttu-id="7967b-113">Możesz łatwo przypisać grupy ubezpieczeniowe Affordable Care jednemu lub większej liczbie pracowników, korzystając z opcji **Przydzielania masowego** na stronie.</span><span class="sxs-lookup"><span data-stu-id="7967b-113">You can easily assign Affordable Care coverage groups to one or more employees by using the **Mass assign** option on the page.</span></span>

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a><span data-ttu-id="7967b-114">Prowadzenie wielu wersji grupy objętej świadczeniem</span><span class="sxs-lookup"><span data-stu-id="7967b-114">Maintaining multiple versions of a coverage group</span></span>

<span data-ttu-id="7967b-115">Możesz utrzymywać wiele wersji dowolnej grupy pokrycia.</span><span class="sxs-lookup"><span data-stu-id="7967b-115">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="7967b-116">Ta funkcja umożliwia wprowadzać zmiany bez konieczności tworzenia nowej grupy i ponownego przypisania do niej pracowników.</span><span class="sxs-lookup"><span data-stu-id="7967b-116">This functionality allows you to make changes without having to create a new group and reassign employees to it.</span></span> 

<span data-ttu-id="7967b-117">Po utworzeniu grup zapotrzebowania ACA można je grupnie przypisywać do pracowników za pomocą opcji **Grupowe przypisywanie**.</span><span class="sxs-lookup"><span data-stu-id="7967b-117">After you’ve created ACA coverage groups, you can mass assign the groups to employees with the **Mass assignment** option.</span></span> <span data-ttu-id="7967b-118">Można również indywidualnie określić, czy mają być śledzone i zgłaszane informacje ACA, oraz przypisać pracownika do grupy świadczenia ACA.</span><span class="sxs-lookup"><span data-stu-id="7967b-118">You can also individually indicate whether to track and report ACA information, and assign an employee to an Affordable Care coverage group.</span></span>

<span data-ttu-id="7967b-119">Nie musisz śledzić niektórych informacji o zasięgu ACA, na przykład dla pracowników zatrudnionych w niepełnym wymiarze godzin.</span><span class="sxs-lookup"><span data-stu-id="7967b-119">You don't need to track some ACA coverage information, such as for part-time employees.</span></span> <span data-ttu-id="7967b-120">W takim przypadku w polu **Zgłaszaj objęcie świadczeniem** należy ustawić wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="7967b-120">In this case, set the **Report coverage** field to **No**.</span></span> <span data-ttu-id="7967b-121">Chociaż musisz przypisać każdego pracownika z możliwymi do śledzenia informacjami ACA do grupy objętej ubezpieczeniem Affordable Care, nadal możesz zmienić następujące opcje dla miesięcy z różnymi wartościami:</span><span class="sxs-lookup"><span data-stu-id="7967b-121">Although you must assign each employee with trackable ACA information to an Affordable Care coverage group, you can still change the following options for months with different values:</span></span>

- <span data-ttu-id="7967b-122">**Oferta świadczenia**</span><span class="sxs-lookup"><span data-stu-id="7967b-122">**Offer of coverage**</span></span>
- <span data-ttu-id="7967b-123">**Udział pracownika w koszcie**</span><span class="sxs-lookup"><span data-stu-id="7967b-123">**Employee share of cost**</span></span>
- <span data-ttu-id="7967b-124">**Bezpieczna przystań**</span><span class="sxs-lookup"><span data-stu-id="7967b-124">**Safe Harbor**</span></span>

<span data-ttu-id="7967b-125">Aby wprowadzić wyjątki od którychkolwiek wartości grupy objętej świadczeniem Affordable Care, kliknij łącze **Świadczenie ACA** znajdujące się na stronie **Szczegóły pracownika**, pod sekcją **Informacje dodatkowe**: na **karcie Zatrudnienie**.</span><span class="sxs-lookup"><span data-stu-id="7967b-125">To enter exceptions for Affordable Care coverage group values, select the **Affordable Care Coverage** link on the **Worker detail** page under the **Additional information** section on the **Employment tab**.</span></span>

## <a name="reporting-health-care-coverage"></a><span data-ttu-id="7967b-126">Zgłaszanie objęcia świadczeniem zdrowotnym</span><span class="sxs-lookup"><span data-stu-id="7967b-126">Reporting health care coverage</span></span>

<span data-ttu-id="7967b-127">Można śledzić nie tylko, jaki zakres ubezpieczenia zdrowotnego zaoferowano pracownikom pełnoetatowym, ale jeśli pracodawca oferuje dodatkowe finansowane przez firmę ubezpieczenie zdrowotne, z którego korzysta pracownik (niezależnie od tego, czy jest zatrudniony w pełnym czy niepełnym wymiarze godzin), w deklaracji 1095-C trzeba podać dodatkowe informacje.</span><span class="sxs-lookup"><span data-stu-id="7967b-127">In addition to tracking health insurance coverage offered to full-time employees, if the employer offers employer-sponsored self-insured health coverage for which the employee is enrolled (regardless of whether their employment status is full-time or part-time), additional information needs to be reported on the 1095-C.</span></span> <span data-ttu-id="7967b-128">Każdy pracownik (w tym osoby na jego utrzymaniu) objęty systemem świadczeń finansowanym przez pracodawcę musi być wykazany w raporcie za miesiące, w których był objęty świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="7967b-128">Each employee (including dependents) covered by the employer-sponsored benefit plans needs to be included on the report for the months they were covered.</span></span> 

<span data-ttu-id="7967b-129">Aby wskazać, że dany plan świadczeń musi być zgłaszany, można zaznaczyć pole wyboru **Podlega zgłoszeniu na mocy ACA**.</span><span class="sxs-lookup"><span data-stu-id="7967b-129">You can indicate whether or not each benefit plan must be reported by selecting the **ACA reportable** check box.</span></span>

<span data-ttu-id="7967b-130">Ponadto jeśli pracownicy wybrali objęcie świadczeniem jakichkolwiek osób pozostających na ich utrzymaniu, na stronie **Obsługa świadczeń** można podać daty objęcia osób zależnych dla każdego pracownika.</span><span class="sxs-lookup"><span data-stu-id="7967b-130">In addition, if employees have chosen to have any of their dependents covered under a benefit, you can indicate the dates the dependent was covered for each employee on the **Maintain benefits** page.</span></span> <span data-ttu-id="7967b-131">Aby wskazać, że osoba na utrzymaniu jest objęta świadczeniem, kliknij przycisk **Edytuj** w okienku akcji na skróconej karcie **Osoby zależne**.</span><span class="sxs-lookup"><span data-stu-id="7967b-131">To indicate that the dependent is covered under the benefit, select the **Edit** button in the action pane of the **Dependents** fast tab.</span></span>

<span data-ttu-id="7967b-132">Na stronie **Menedżer dat świadczenia dla osoby będącej na utrzymaniu** można podać daty objęcia osoby na utrzymaniu świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="7967b-132">On the **Dependent coverage date manager** page, you can indicate the dates the dependent was covered by the benefit.</span></span> <span data-ttu-id="7967b-133">Wprowadzenie dat na tej stronie spowoduje automatyczne zaznaczenie pola wyboru **Pokryte** na stronie **Obsługa świadczeń**.</span><span class="sxs-lookup"><span data-stu-id="7967b-133">Entering dates on this page will automatically select the **Covered** checkbox on the **Maintain benefits** page.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="7967b-134">Generowanie formularzy 1095-B i 1095-C</span><span class="sxs-lookup"><span data-stu-id="7967b-134">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="7967b-135">Formularze 1095-B i 1095-C można również wygenerować z poziomu programu i rozesłać je odnośnym pracownikom.</span><span class="sxs-lookup"><span data-stu-id="7967b-135">You can also generate 1095-B and 1095-C forms from within the product, and distribute them to each of your employees.</span></span> <span data-ttu-id="7967b-136">System może także elektronicznie generować formularze 1095-C oraz pliki przekazu 1094-C IRS.</span><span class="sxs-lookup"><span data-stu-id="7967b-136">The system can also electronically generate 1095-C forms and the 1094-C IRS transmittal files.</span></span>  

<span data-ttu-id="7967b-137">Podczas generowania formularza 1095-C należy wprowadzić odpowiedni rok podatkowy i wskazać, czy numer ubezpieczenia społecznego powinien być zakryty.</span><span class="sxs-lookup"><span data-stu-id="7967b-137">When generating the 1095-C form, enter the appropriate tax year and indicate if social security numbers should be masked.</span></span> <span data-ttu-id="7967b-138">W wypadku drukowania formularzy 1095-C dla więcej niż 500 pracowników otrzymasz więcej niż jeden plik PDF.</span><span class="sxs-lookup"><span data-stu-id="7967b-138">If you're printing 1095-C forms for more than 500 employees, you'll receive more than one PDF file.</span></span> <span data-ttu-id="7967b-139">Zaleca się zwiększenie **maksymalnego rozmiaru pliku** w oknie **Parametry zarządzania dokumentami** na 150 MB.</span><span class="sxs-lookup"><span data-stu-id="7967b-139">It’s recommended that you increase the **Maximum file size** in the **Document management parameters** window to 150 MB.</span></span>

## <a name="viewing-information"></a><span data-ttu-id="7967b-140">Wyświetlanie informacji</span><span class="sxs-lookup"><span data-stu-id="7967b-140">Viewing information</span></span>

<span data-ttu-id="7967b-141">Na stronie **Świadczenie ACA dla pracownika** można zobaczyć, których pracowników przypisano do poszczególnych grup objętych świadczeniem, których pracowników nie trzeba uwzględniać w raporcie i którzy pracownicy są nieprzypisani.</span><span class="sxs-lookup"><span data-stu-id="7967b-141">You can use the **Worker Affordable Care coverage** page to see which employees have been assigned to each coverage group, which employees don’t need to be included on a report, and which employees are unassigned.</span></span>

<span data-ttu-id="7967b-142">Jeśli którakolwiek domyślna wartość grupy objętej świadczeniem ACA zostanie zastąpiona, obok niej będzie widoczna gwiazdka.</span><span class="sxs-lookup"><span data-stu-id="7967b-142">If any of the default values from the Affordable Care coverage group have been overridden, an asterisk will appear next to the value that was changed.</span></span> <span data-ttu-id="7967b-143">Jeśli wartości dla wszystkich dwunastu miesięcy są takie same i nie zostały zastąpione, wartość zostanie wydrukowana w kolumnie **Wszystkie 12 miesięcy**.</span><span class="sxs-lookup"><span data-stu-id="7967b-143">If the values for all 12 months are the same and haven’t been overridden, the value will print in the **All 12 months** column.</span></span>

<span data-ttu-id="7967b-144">Ponadto za pomocą okna informacji można zrozumieć, którzy pracownicy zostały oflagowane jako nie mogą być raportowane na podstawie ACA.</span><span class="sxs-lookup"><span data-stu-id="7967b-144">You can also use the inquiry window to understand which employees have been flagged as not ACA reportable.</span></span> <span data-ttu-id="7967b-145">Nie trzeba śledzić, czy zaoferował im pokrycie i nie trzeba na koniec roku wystawiać im 1095-C.</span><span class="sxs-lookup"><span data-stu-id="7967b-145">You don’t need to track whether coverage was offered to them and won't need to issue a 1095-C to them at the end of the year.</span></span> <span data-ttu-id="7967b-146">Wybierz opcję **Nie do zgłoszenia do ACA** w polu **Filtruj według**, aby wygenerować listę wszystkich pracowników, którzy nie otrzymają raportu1095-C.</span><span class="sxs-lookup"><span data-stu-id="7967b-146">Select **Not ACA reportable** in the **Filter by** field to generate a list of all employees who won't receive a 1095-C.</span></span>

<span data-ttu-id="7967b-147">Można również wyświetlić pracowników, którzy nie są przypisani (mają puste pole **Objęcie zgłaszaniem na mocy**) lub zostali przypisani do grupy objętej świadczeniem ACA, która wygasła dla roku wybranego w polu **Rok**.</span><span class="sxs-lookup"><span data-stu-id="7967b-147">In addition, you can view any employees who are unassigned (the **ACA Report coverage** field is empty) or who have been assigned to an Affordable Care coverage group that is expired for the year selected in the **Year** field.</span></span>

<span data-ttu-id="7967b-148">Można wyeksportować wygenerowaną listę pracowników, używając dowolnej opcji filtrowania do programu Excel.</span><span class="sxs-lookup"><span data-stu-id="7967b-148">You can export lists of employees that were generated using any of the filtering options to Excel.</span></span>

<span data-ttu-id="7967b-149">Jeśli chcesz zgłosić osoby objęte ubezpieczeniem, ponieważ zapewniasz ubezpieczenie samodzielnie, możesz wyświetlić wszystkie osoby na utrzymaniu objęte planem świadczeń oznaczonych jako **Objęte zgłoszeniem do ACA**.</span><span class="sxs-lookup"><span data-stu-id="7967b-149">If you need to report covered individuals because you provide self-insured coverage, you can view any dependents covered under benefit plans marked as **ACA reportable**.</span></span> <span data-ttu-id="7967b-150">Na okienku akcji wybierz **Wyświetl świadczenia osób na utrzymaniu**.</span><span class="sxs-lookup"><span data-stu-id="7967b-150">Select **View Dependent coverage** on the action pane.</span></span>

> [!NOTE]
> <span data-ttu-id="7967b-151">W oknie informacji można wyświetlać tylko plany świadczeń oznaczone jako **Objęte zgłoszeniem do ACA**.</span><span class="sxs-lookup"><span data-stu-id="7967b-151">Only benefit plans marked as **ACA reportable** display in the inquiry window.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]