---
title: Opracowywanie struktury wynagrodzeń
description: W tym artykule przedstawiono proces tworzenia stałego planu wynagrodzeń i przypisywania pracowników do planu za pomocą reguł kwalifikowalności.
author: andreabichsel
manager: AnnBe
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 124d0f7f83feebabf622f00732c25bfa0f6eccdd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420096"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="70c79-103">Opracowywanie struktury wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="70c79-103">Develop a compensation structure</span></span>

<span data-ttu-id="70c79-104">W tym artykule przedstawiono proces tworzenia stałego planu wynagrodzeń i przypisywania pracowników do planu za pomocą reguł kwalifikowalności.</span><span class="sxs-lookup"><span data-stu-id="70c79-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="70c79-105">W tym artykule używane są dane demonstracyjne USMF i dotyczą menedżerów wynagrodzeń i świadczeń.</span><span class="sxs-lookup"><span data-stu-id="70c79-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="70c79-106">Tworzenie systemu stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="70c79-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="70c79-107">Wybierz **Zarządzanie wynagrodzeniami**.</span><span class="sxs-lookup"><span data-stu-id="70c79-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="70c79-108">Wybierz **Systemy stałych wynagrodzeń**.</span><span class="sxs-lookup"><span data-stu-id="70c79-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="70c79-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="70c79-109">Select **New**.</span></span>

4. <span data-ttu-id="70c79-110">Wprowadź wartość w polu **Plan**.</span><span class="sxs-lookup"><span data-stu-id="70c79-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="70c79-111">W polu **Opis** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="70c79-112">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="70c79-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="70c79-113">W polu **Typ** określ, czy system stałych wynagrodzeń to plan typu **Pasmo**, **Kategoria** lub **Krok**.</span><span class="sxs-lookup"><span data-stu-id="70c79-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="70c79-114">Pole wyboru **Rekomendacje dozwolone** służy jako wartość domyślna dla wszystkich czynności dodawanych do tego planu w zdarzeniu procesowym.</span><span class="sxs-lookup"><span data-stu-id="70c79-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="70c79-115">Zezwolenie na rekomendacje umożliwi zastąpienie obliczonej kwoty podstawowej podczas przetwarzania wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="70c79-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="70c79-116">Pole **Tolerancja wyjścia poza zakres** pozwala określić sposób postępowania z kwotami wynagrodzeń, które nie mieszczą się w zakresie podanej struktury wynagrodzeń dla danego poziomu.</span><span class="sxs-lookup"><span data-stu-id="70c79-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="70c79-117">Ustawienie pola **Tolerancja wyjścia poza zakres** na wartość **Brak** pozwala na użycie dowolnej kwoty wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="70c79-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="70c79-118">**Miękka tolarancja** ostrzega użytkowników, jeśli kwota wynagrodzenia jest mniejsza niż minimalna lub większa niż maksymalna kwota punktu odniesienia dla tego poziomu.</span><span class="sxs-lookup"><span data-stu-id="70c79-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="70c79-119">Użytkownicy mogą zignorować ostrzeżenie i kontynuować.</span><span class="sxs-lookup"><span data-stu-id="70c79-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="70c79-120">**Twarda tolerancja** spowoduje generowanie błędu, jeśli wynagrodzenie pracownika zostanie ustawione poza punktami odniesienia minimalnym i maksymalnym dla poziomu, oraz automatycznie dopasowanie wynagrodzenia pracownika, aby się mieściło w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="70c79-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="70c79-121">Pole **Reguły zatrudnienia** oblicza wynagrodzenie pracownika podczas zdarzenia procesowego.</span><span class="sxs-lookup"><span data-stu-id="70c79-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="70c79-122">**Reguła zatrudnienia** **Procentu** oblicza wzrost proporcjonalny do długości czasu zatrudnienia pracownika w cyklu.</span><span class="sxs-lookup"><span data-stu-id="70c79-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="70c79-123">W polu **Waluta** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="70c79-124">W polu **Konwersja stawki płacy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="70c79-125">Rozwiń sekcję **Macierz zakresów wykorzystania**.</span><span class="sxs-lookup"><span data-stu-id="70c79-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="70c79-126">Opcjonalnie dodaj rekordy zakresu wykorzystania, aby umożliwić pracownikom szybsze dotarcie ich punktów środkowych, a spowolnić osiągnięcie wartości maksymalnej w zakresie.</span><span class="sxs-lookup"><span data-stu-id="70c79-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="70c79-127">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="70c79-127">Select **Save**.</span></span> <span data-ttu-id="70c79-128">Spowoduje to włączenie przycisku **Ustaw wynagrodzenie** i kontynuowanie definiowania struktury wynagrodzeń dla planu.</span><span class="sxs-lookup"><span data-stu-id="70c79-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="70c79-129">Wybierz **Konfiguruj wynagrodzenie**.</span><span class="sxs-lookup"><span data-stu-id="70c79-129">Select **Set up compensation**.</span></span> <span data-ttu-id="70c79-130">Możesz utworzyć strukturę wynagrodzeń, korzystając z jednej z trzech poniższych metod:</span><span class="sxs-lookup"><span data-stu-id="70c79-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="70c79-131">Utworzenie całkowicie nowej struktury przez wybranie zbioru punktów odniesienia i dodanie poziomów, aby utworzyć własną strukturę.</span><span class="sxs-lookup"><span data-stu-id="70c79-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="70c79-132">Skopiowanie struktury wynagrodzeń z istniejącego planu i jej zmodyfikowanie dla nowego planu.</span><span class="sxs-lookup"><span data-stu-id="70c79-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="70c79-133">Wybór istniejącej siatki wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="70c79-133">Select an existing compensation grid.</span></span> <span data-ttu-id="70c79-134">Jeśli inny plan już korzysta z siatki wynagrodzeń, drugi plan również odzwierciedla wszelkie zmiany wprowadzone w siatce.</span><span class="sxs-lookup"><span data-stu-id="70c79-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="70c79-135">Wybierz **Utwórz nową na podstawie istniejącej macierzy wynagrodzeń**.</span><span class="sxs-lookup"><span data-stu-id="70c79-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="70c79-136">W polu **Kopiuj z siatki** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="70c79-137">Opcjonalnie można zmienić nazwę nowej siatki wynagrodzeń, którą tworzysz przez kopiowanie wybranej siatki.</span><span class="sxs-lookup"><span data-stu-id="70c79-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="70c79-138">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="70c79-138">Select **OK**.</span></span>

19. <span data-ttu-id="70c79-139">Wybierz **Zmianę grupową**.</span><span class="sxs-lookup"><span data-stu-id="70c79-139">Select **Mass change**.</span></span> <span data-ttu-id="70c79-140">**Zmiana grupowa** pozwala zachować kwoty macierzy wynagrodzeń poprzez zastosowanie wzrostu procentowego lub o stałej kwocie do jednego lub więcej poziomów lub punktów odniesienia.</span><span class="sxs-lookup"><span data-stu-id="70c79-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="70c79-141">W polu **Kwota korekty** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="70c79-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="70c79-142">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="70c79-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="70c79-143">Kliknij przycisk **Zastosuj do siatki**.</span><span class="sxs-lookup"><span data-stu-id="70c79-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="70c79-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70c79-144">Close the page.</span></span> <span data-ttu-id="70c79-145">Po utworzeniu struktury wynagrodzeń możesz wybrać, które punkty odniesienia mają być używane jako punkt kontrolny dla stałego planu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="70c79-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="70c79-146">Punkt kontrolny służy do obliczania wskaźnika porównawczego pracownika.</span><span class="sxs-lookup"><span data-stu-id="70c79-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="70c79-147">W polu **Punkt kontrolny** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="70c79-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70c79-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="70c79-149">Tworzenie reguły uprawnienia dla systemu stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="70c79-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="70c79-150">Nie możesz przypisać systemu stałych wynagrodzeń pracownikowi, dopóki nie zdefiniujesz reguł kwalifikujących do tego planu.</span><span class="sxs-lookup"><span data-stu-id="70c79-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="70c79-151">Wybierz **Reguły uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="70c79-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="70c79-152">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="70c79-152">Select **New**.</span></span>

3. <span data-ttu-id="70c79-153">Wprowadź wartość w polu **Uprawnienie**.</span><span class="sxs-lookup"><span data-stu-id="70c79-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="70c79-154">W polu **Opis** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="70c79-155">W polu **Data wejścia w życie** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="70c79-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="70c79-156">Zarówno stałe, jak i zmienne plany wynagrodzeń wykorzystują zasady kwalifikowalności.</span><span class="sxs-lookup"><span data-stu-id="70c79-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="70c79-157">W polu **Typ** wybierz typ planu.</span><span class="sxs-lookup"><span data-stu-id="70c79-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="70c79-158">W polu **Plan** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="70c79-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="70c79-159">Wybierz kryteria, które pracownik musi spełnić, aby kwalifikować się do planu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="70c79-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="70c79-160">Kryteria mogą obejmować:</span><span class="sxs-lookup"><span data-stu-id="70c79-160">Criteria can include:</span></span>

    - <span data-ttu-id="70c79-161">**Dział**</span><span class="sxs-lookup"><span data-stu-id="70c79-161">**Department**</span></span>
    - <span data-ttu-id="70c79-162">**Związek zawodowy**</span><span class="sxs-lookup"><span data-stu-id="70c79-162">**Labor union**</span></span>
    - <span data-ttu-id="70c79-163">**Lokalizację** (**Region wynagrodzenia**)</span><span class="sxs-lookup"><span data-stu-id="70c79-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="70c79-164">**Zadanie**</span><span class="sxs-lookup"><span data-stu-id="70c79-164">**Job**</span></span>
    - <span data-ttu-id="70c79-165">**Funkcja**</span><span class="sxs-lookup"><span data-stu-id="70c79-165">**Function**</span></span>
    - <span data-ttu-id="70c79-166">**Typ zadania**</span><span class="sxs-lookup"><span data-stu-id="70c79-166">**Job type**</span></span>
    - <span data-ttu-id="70c79-167">**Poziom wynagrodzeń**</span><span class="sxs-lookup"><span data-stu-id="70c79-167">**Compensation level**</span></span>
    
    <span data-ttu-id="70c79-168">Aby kwalifikować się do planu wynagrodzeń, pracownik musi spełniać wszystkie kryteria.</span><span class="sxs-lookup"><span data-stu-id="70c79-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="70c79-169">W razie nieokreślenia żadnych kryteriów wszyscy pracownicy kwalifikują się do planu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="70c79-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="70c79-170">Jeśli pracownik nie spełnia kryteriów określonych w regule uprawnienia lub jeśli nie określono reguły uprawnienia dla planu wynagrodzeń, plan wynagrodzeń nie pojawi się w wynikach wyszukiwania podczas tworzenia rekordu stałego wynagrodzenia dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="70c79-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="70c79-171">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70c79-171">Close the page.</span></span>

8. <span data-ttu-id="70c79-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70c79-172">Close the page.</span></span>

