---
title: Grupowanie wierszy pobrania
description: Ten temat zawiera omówienie grupowania wierszy pobrania.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435557"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="74669-103">Grupowanie wierszy pobrania</span><span class="sxs-lookup"><span data-stu-id="74669-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74669-104">Podczas grupowania wierszy pobrania wiele wierszy pracy, które mają ten sam element i lokalizację, można łączyć w jednym pobraniu prezentowanym użytkownikowi na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="74669-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="74669-105">Dzięki temu pracownicy magazynu mogą odbierać najbardziej efektywne instrukcje, które są możliwe, ale wymagane rozdzielenie wierszy pracy w systemie jest również zachowane (na przykład dla różnych kontenerów i zamówień).</span><span class="sxs-lookup"><span data-stu-id="74669-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="74669-106">Konfigurowanie grupowania wierszy pobrania</span><span class="sxs-lookup"><span data-stu-id="74669-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="74669-107">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="74669-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="74669-108">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego** i utwórz nowy element menu o nazwie **Pobieranie wierszy grupy sprzedaży — sterowane przez użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="74669-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="74669-109">W obszarze **Elementy menu urządzenia przenośnego** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="74669-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="74669-110">W polu **Nazwa elementu menu** wprowadź pozycję **Pobranie sprzedaży — wiersz grupy**.</span><span class="sxs-lookup"><span data-stu-id="74669-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="74669-111">W polu **Tytuł** wprowadź pozycję **Pobranie sprzedaży — wiersz grupy**.</span><span class="sxs-lookup"><span data-stu-id="74669-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="74669-112">W polu **Tryb** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="74669-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="74669-113">W opcji **Użyj istniejącej pracy** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="74669-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="74669-114">Na skróconej karcie **Ogólne** możesz ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="74669-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="74669-115">W polu **Sterowane przez** wybierz opcję **Sterowane przez użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="74669-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="74669-116">Ustaw opcję **Generuj numer identyfikacyjny:** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="74669-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="74669-117">Ustaw opcję **Pobranie grupowe** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="74669-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="74669-118">Na skróconej karcie **Klasy robocze** wykonaj następujące kroki, aby skonfigurować prawidłowe klasy robocze dla elementu menu urządzenia przenośnego:</span><span class="sxs-lookup"><span data-stu-id="74669-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="74669-119">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="74669-119">Select **New**.</span></span>
    2. <span data-ttu-id="74669-120">W polu **Identyfikator klasy roboczej** wybierz pozycję **Sprzedaż** lub **Pobranie zamówienia sprzedaży**, zależnie od magazynu, którego będziesz używać.</span><span class="sxs-lookup"><span data-stu-id="74669-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="74669-121">W polu **Typ zlecenia pracy** wybierz opcję **Zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="74669-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="74669-122">Konfigurowanie menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="74669-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="74669-123">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="74669-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="74669-124">Dodaj element menu, który został właśnie utworzony, do żądanego menu.</span><span class="sxs-lookup"><span data-stu-id="74669-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="74669-125">Konfigurowanie szablonów pracy</span><span class="sxs-lookup"><span data-stu-id="74669-125">Set up a work template</span></span>

1. <span data-ttu-id="74669-126">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="74669-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="74669-127">Znajdź szablon pracy, który ma być używany z tą funkcją.</span><span class="sxs-lookup"><span data-stu-id="74669-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="74669-128">W tym przykładzie wybierz standardowy szablon pracy Contoso **51 Pobranie do lokalizacji przejściowej**.</span><span class="sxs-lookup"><span data-stu-id="74669-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="74669-129">W menu wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="74669-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="74669-130">Na karcie **Sortowanie** wybierz pozycję **Dodaj**, a następnie ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="74669-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="74669-131">W polu **Tabela** wybierz pozycję **Transakcje pracy tymczasowej**.</span><span class="sxs-lookup"><span data-stu-id="74669-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="74669-132">W polu **Tabela pochodna** wybierz pozycję **Transakcje pracy tymczasowej**.</span><span class="sxs-lookup"><span data-stu-id="74669-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="74669-133">W polu **Pole** wybierz pozycję **Numer elementu**.</span><span class="sxs-lookup"><span data-stu-id="74669-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="74669-134">W polu **Kierunek wyszukiwania** wybierz opcję **Rosnąco**.</span><span class="sxs-lookup"><span data-stu-id="74669-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="74669-135">Aby funkcja grupowania wierszy pobrania mogła działać, wiersze pracy muszą być sortowane według identyfikatora elementu.</span><span class="sxs-lookup"><span data-stu-id="74669-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="74669-136">Jeśli wiersze, które mają te same elementy, nie są sekwencjonowane jeden po drugim, nie zostaną zgrupowane.</span><span class="sxs-lookup"><span data-stu-id="74669-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="74669-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="74669-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="74669-138">Tworzenie pracy pobrania</span><span class="sxs-lookup"><span data-stu-id="74669-138">Create picking work</span></span>

<span data-ttu-id="74669-139">Aby można było skonfigurować grupowanie wierszy pobrania, należy utworzyć kilka kwalifikujących się prac wychodzących.</span><span class="sxs-lookup"><span data-stu-id="74669-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="74669-140">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="74669-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="74669-141">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="74669-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="74669-142">W polu **Konto klienta** wybierz dowolnego klienta.</span><span class="sxs-lookup"><span data-stu-id="74669-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="74669-143">Na skróconej karcie **Ogólne** w polu **Magazyn** wybierz wartość **51**.</span><span class="sxs-lookup"><span data-stu-id="74669-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="74669-144">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="74669-144">Then select **OK**.</span></span>
5. <span data-ttu-id="74669-145">W obszarze **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy:</span><span class="sxs-lookup"><span data-stu-id="74669-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="74669-146">**Wiersz 1:** w polu **Numer elementu** wybierz wartość **M9200**.</span><span class="sxs-lookup"><span data-stu-id="74669-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="74669-147">W polu **Ilość** wpisz wartość **3**.</span><span class="sxs-lookup"><span data-stu-id="74669-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="74669-148">**Wiersz 2:** w polu **Numer elementu** wybierz wartość **M9201**.</span><span class="sxs-lookup"><span data-stu-id="74669-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="74669-149">W polu **Ilość** wpisz wartość **3**.</span><span class="sxs-lookup"><span data-stu-id="74669-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="74669-150">**Wiersz 3:** w polu **Numer elementu** wybierz wartość **M9202**.</span><span class="sxs-lookup"><span data-stu-id="74669-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="74669-151">W polu **Ilość** wpisz wartość **2**.</span><span class="sxs-lookup"><span data-stu-id="74669-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="74669-152">**Wiersz 4:** w polu **Numer elementu** wybierz wartość **M9200**.</span><span class="sxs-lookup"><span data-stu-id="74669-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="74669-153">W polu **Ilość** wpisz wartość **1**.</span><span class="sxs-lookup"><span data-stu-id="74669-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="74669-154">**Wiersz 5:** w polu **Numer elementu** wybierz wartość **M9200**.</span><span class="sxs-lookup"><span data-stu-id="74669-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="74669-155">W polu **Ilość** wpisz wartość **3**.</span><span class="sxs-lookup"><span data-stu-id="74669-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="74669-156">**Wiersz 6:** w polu **Numer elementu** wybierz wartość **M9202**.</span><span class="sxs-lookup"><span data-stu-id="74669-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="74669-157">W polu **Ilość** wpisz wartość **7**.</span><span class="sxs-lookup"><span data-stu-id="74669-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="74669-158">Poniżej znajduje się podsumowanie całkowitych ilości dla każdego elementu:</span><span class="sxs-lookup"><span data-stu-id="74669-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="74669-159">**Element M9200:** 7 sztuk</span><span class="sxs-lookup"><span data-stu-id="74669-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="74669-160">**Element M9201:** 3 sztuki</span><span class="sxs-lookup"><span data-stu-id="74669-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="74669-161">**Element M9202:** 9 sztuk</span><span class="sxs-lookup"><span data-stu-id="74669-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="74669-162">Przed zwolnieniem zleceń do magazynu należy upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach.</span><span class="sxs-lookup"><span data-stu-id="74669-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="74669-163">Przejrzyj ustawienie **Dyrektywa lokalizacji**, aby określić, które lokalizacje pobrania są używane do pobrania zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="74669-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="74669-164">Zarezerwuj zapasy i zwolnij je do magazynu.</span><span class="sxs-lookup"><span data-stu-id="74669-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="74669-165">Tworzony jest identyfikator pracy, który ma sześć wierszy.</span><span class="sxs-lookup"><span data-stu-id="74669-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="74669-166">Wiersze są sortowane według numeru elementu.</span><span class="sxs-lookup"><span data-stu-id="74669-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="74669-167">Uruchamianie przepływu na urządzeniu przenośnym</span><span class="sxs-lookup"><span data-stu-id="74669-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="74669-168">Na urządzeniu przenośnym wybierz menu, które zawiera nowy element menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="74669-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="74669-169">Wybierz element menu **Pobranie sprzedaży — wiersz grupy** i zainicjuj pobranie.</span><span class="sxs-lookup"><span data-stu-id="74669-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="74669-170">Po wybraniu menu i wprowadzeniu identyfikatora pracy zobaczysz krok pobrania, w którym wszystkie wiersze pobrania dla elementu M9200 są zgrupowane.</span><span class="sxs-lookup"><span data-stu-id="74669-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="74669-171">Otrzymasz instrukcję, aby wybrać 7 sztuk elementu M9200.</span><span class="sxs-lookup"><span data-stu-id="74669-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="74669-172">Potwierdź krok pobrania.</span><span class="sxs-lookup"><span data-stu-id="74669-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="74669-173">Przejdź do ekranu klienta pracy w toku i zwróć uwagę, że wszystkie trzy wiersze pobrania dla elementu M9200 zostały zamknięte jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="74669-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="74669-174">Zostanie wyświetlony wiersz pracy 4.</span><span class="sxs-lookup"><span data-stu-id="74669-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="74669-175">Potwierdź krok pobrania.</span><span class="sxs-lookup"><span data-stu-id="74669-175">Confirm the pick step.</span></span>

    <span data-ttu-id="74669-176">Ostatni krok pobrania na urządzeniu przenośnym agreguje ostatnie dwa wiersze pobrania ze zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="74669-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="74669-177">Ukończ krok pobrania dla 9 sztuk elementu M9202.</span><span class="sxs-lookup"><span data-stu-id="74669-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="74669-178">Potwierdź krok odłożenia i wszelkie dodatkowe pary pobranie/odłożenie, aby ukończyć pracę.</span><span class="sxs-lookup"><span data-stu-id="74669-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="74669-179">Wiersze pracy można grupować tylko wtedy, gdy są ustawione w kolejności.</span><span class="sxs-lookup"><span data-stu-id="74669-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="74669-180">Poniższe funkcje nie są obsługiwane:</span><span class="sxs-lookup"><span data-stu-id="74669-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="74669-181">Towary w ilości efektywnej.</span><span class="sxs-lookup"><span data-stu-id="74669-181">Catch-weight items.</span></span> <span data-ttu-id="74669-182">Jeśli w pracy znajdują się wszystkie dowolne towary w ilości efektywnej, przed rozpoczęciem pobrania zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="74669-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="74669-183">Pobranie sztuk.</span><span class="sxs-lookup"><span data-stu-id="74669-183">Piece picking.</span></span>
>    - <span data-ttu-id="74669-184">Wiersze pracy z niedokończoną pracą uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="74669-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="74669-185">Pobranie nadmiarowe.</span><span class="sxs-lookup"><span data-stu-id="74669-185">Over-picking.</span></span>
>    - <span data-ttu-id="74669-186">Pobieranie w niedomiarze wraz ze zmianą alokacji pozycji</span><span class="sxs-lookup"><span data-stu-id="74669-186">Short picking with item reallocation</span></span>
