---
title: Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji
description: Funkcja Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji pozwala sprawdzić, gdzie w lokalizacji wielopaletowej znajduje się dany numer identyfikacyjny, np. gdy w lokalizacji używane są szafki na palety o podwójnej głębokości.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: e5fd7a9a9703f9ab6802def0aac096e29aa04f1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831393"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="a6a8d-103">Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6a8d-104">Funkcja Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji pozwala sprawdzić, gdzie w lokalizacji wielopaletowej znajduje się dany numer identyfikacyjny, np. gdy w lokalizacji używane są szafki na palety o podwójnej głębokości.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="a6a8d-105">Ta funkcja dodaje numer sekwencyjny do każdego numeru identyfikacyjnego, który jest umieszczany w lokalizacji przechowywania.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="a6a8d-106">Ten numer sekwencyjny służy do porządkowania numerów identyfikacyjnych w lokalizacji magazynu.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="a6a8d-107">Z tego względu funkcja ta inteligentnie obsługuje scenariusze, w których klienci korzystają z systemu stojaków i muszą znać, do celów pobrania, który numer identyfikacyjny jest zwrócony do przodu.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="a6a8d-108">W tym temacie przedstawiono scenariusz, który pokazuje sposób konfigurowania i korzystania z funkcji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="a6a8d-109">Włączenie funkcji Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="a6a8d-110">Aby móc używać funkcji Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="a6a8d-111">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a6a8d-112">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a6a8d-113">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a6a8d-114">**Nazwa funkcji:** *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="a6a8d-115">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="a6a8d-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="a6a8d-116">Udostępnianie danych pokazowych</span><span class="sxs-lookup"><span data-stu-id="a6a8d-116">Make sample data available</span></span>

<span data-ttu-id="a6a8d-117">Aby przejść przez ten scenariusz przy użyciu określonych zaprezentowanych przykładowych danych i wartości, należy korzystać z systemu, w którym są zainstalowane standardowe dane przykładowe.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="a6a8d-118">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="a6a8d-119">Skonfiguruj funkcję dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="a6a8d-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="a6a8d-120">Wykonaj poniższe procedury, aby skonfigurować funkcję *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji* dla scenariusza przedstawionego w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="a6a8d-121">Profile lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-121">Location profiles</span></span>

<span data-ttu-id="a6a8d-122">Funkcja musi być włączona w profilu lokalizacji dla każdej lokalizacji, w której będzie używana.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="a6a8d-123">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="a6a8d-124">Z listy profilów lokalizacji w lewym okienku wybierz opcję **BULK-06**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="a6a8d-125">Na skróconej karcie **Ogólne** zostały dodane dwie nowe opcje przez tą funkcję.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="a6a8d-126">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-126">Set the following values:</span></span>

    - <span data-ttu-id="a6a8d-127">**Włącz funkcję Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="a6a8d-128">Jeśli ta opcja jest ustawiona na wartość *Tak*, pozycja numeru identyfikacyjnego będzie utrzymywana dla numerów identyfikacyjnych w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="a6a8d-129">**Wyświetl pozycję num. id. urządzenia przenośnego:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="a6a8d-130">Jeśli ta opcja jest ustawiona na *Tak*, użytkownicy urządzeń przenośnych będą mogli wyświetlić pozycję numeru identyfikacyjnego w trakcie korekty i inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="a6a8d-131">Ustawienie tej opcji można zmienić tylko w przypadku, gdy funkcja jest włączona.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="a6a8d-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="a6a8d-133">Dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-133">Location directives</span></span>

1. <span data-ttu-id="a6a8d-134">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a6a8d-135">W lewym okienku upewnij się, że pole **Typ zlecenia produkcyjnego** ma wartość *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="a6a8d-136">Z listy dyrektyw lokalizacji wybierz pozycję **61 Zlecenie pobrania zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="a6a8d-137">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a6a8d-138">Na skróconej karcie **Wiersze** wybierz wiersz mający wartość **Numeru sekwencyjnego** równą *2*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="a6a8d-139">Na skróconej karcie **Akcji dyrektywy lokalizacji** wybierz wiersz, który ma wartość **Nazwa** równą *Pobierz mniej niż paleta* (powinien to być jedyny wiersz), a następnie zmień **Wartość jego sekwencji** na *2*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="a6a8d-140">Powyżej siatki wybierz **Nowe**, aby dodać nowy wiersz dla dyrektywy akcji lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="a6a8d-141">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a6a8d-142">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="a6a8d-143">**Nazwa:** *Pozycja pobrania 1*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="a6a8d-144">Gdy nowy wiersz jest wciąż zaznaczony, wybierz polecenie **Edytuj kwerendę** powyżej siatki.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="a6a8d-145">W edytorze zapytań wybierz kartę **Sprzężenia**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="a6a8d-146">Rozwiń opcję **Lokalizacje** na tabeli sprzężęnia, aby wyświetlić sprzężenie do tabeli **Wymiarów magazynowych**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="a6a8d-147">Rozwiń opcję **Wymiary magazynowe** na tabeli sprzężęnia, aby wyświetlić sprzężenie tabeli **Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="a6a8d-148">Wybierz **Wymiary magazynowe**, a następnie wybierz opcję **Dodaj sprzężenie tabeli**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="a6a8d-149">Z listy tabel, które pojawiają się w kolumnie **Relacja**, wybierz **Numer identyfikacyjny (numer identyfikacyjny)**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="a6a8d-150">Następnie wybierz opcję **Wybierz**, aby dodać **Numer identyfikacyjny** do sprzężenia tabeli **Wymiarów magazynowych**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="a6a8d-151">Póki **Numer identyfikacyjny** jest wciąż zaznaczony, wybierz opcję **Dodaj sprzężenie tabeli**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="a6a8d-152">Z listy tabel, które pojawiają się w kolumnie **Relacja**, wybierz **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji (numer identyfikacyjny)**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="a6a8d-153">Następnie wybierz opcję **Wybierz**, aby dodać **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji** do sprzężenia tabeli **Wymiarów magazynowych**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="a6a8d-154">![Sprzężenia tabeli](media/LpTableJoin.png "Sprzężenia tabeli")</span><span class="sxs-lookup"><span data-stu-id="a6a8d-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="a6a8d-155">Wybierz przycisk **OK**, aby potwierdzić zaktualizowane tabele sprzężone i zamknąć Edytor kwerend.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="a6a8d-156">Na karcie skróconej **Akcje dyrektywy lokalizacji** ponownie kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="a6a8d-157">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="a6a8d-158">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a6a8d-159">**Tabela:** *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="a6a8d-160">**Tabela pochodna:** *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="a6a8d-161">**Pole:** *Stanowisko Num. id.*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="a6a8d-162">**Kryteria:** *1*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="a6a8d-163">![Nowy zakres](media/LpPositionCriteria.png "Nowy zakres")</span><span class="sxs-lookup"><span data-stu-id="a6a8d-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="a6a8d-164">Wybierz przycisk **OK**, aby potwierdzić zmiany i zamknąć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="a6a8d-165">Skonfiguruj przykładowe dane dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="a6a8d-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="a6a8d-166">W tym scenariuszu użytkownik musi zalogować się do mobilnej aplikacji magazynowej, używając pracownika skonfigurowanego dla magazynu *61* w celu przeprowadzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="a6a8d-167">Użytkownik musi również wykonać transakcje.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-167">The user must also complete transactions.</span></span>

<span data-ttu-id="a6a8d-168">Ponieważ funkcja *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji* dodaje nowy identyfikator dla położenia numeru identyfikacyjnego w lokalizacji, należy najpierw utworzyć pewne dane, które będą obsługiwały ten scenariusz.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="a6a8d-169">Inwentaryzacja punktowa w pierwszej lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-169">Spot-count the first location</span></span>

1. <span data-ttu-id="a6a8d-170">Otwórz do mobilną aplikację magazynowania i zaloguj się jako użytkownik w magazynie *61*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="a6a8d-171">Przejdź do **Zapasy \> Inwentaryzacja punktowa**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="a6a8d-172">Na stronie **Inwentaryzacja punktowa**, w polu **Lokalizacja** określ wartość *01A01R1S1B*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="a6a8d-173">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-173">Select **OK**.</span></span>

    <span data-ttu-id="a6a8d-174">Na stronie zostanie wyświetlona wprowadzona lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-174">The page shows the location that you entered.</span></span> <span data-ttu-id="a6a8d-175">Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”</span><span class="sxs-lookup"><span data-stu-id="a6a8d-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="a6a8d-176">Wybierz opcję **Odśwież**, aby dodać licznik do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="a6a8d-177">W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję**, zaznacz pole **Pozycja**, a następnie wprowadź wartość *A0001*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="a6a8d-178">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-178">Select **OK**.</span></span>
1. <span data-ttu-id="a6a8d-179">W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję** wybierz pole **Num. id.**, a następnie wprowadź wartość *LP1001* (lub dowolny inny numer identyfikacyjny).</span><span class="sxs-lookup"><span data-stu-id="a6a8d-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="a6a8d-180">Strona **Licznik cykli: Dodaj nowy num. id. lub pozycję** pokazuje **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji 1**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="a6a8d-181">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-181">Select **OK**.</span></span>

    <span data-ttu-id="a6a8d-182">Teraz należy określić ilość towaru, która znajduje się na numerze identyfikacyjnym.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="a6a8d-183">Ustaw wartość w polu **Ilość** na *10*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="a6a8d-184">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-184">Select **OK**.</span></span>

    <span data-ttu-id="a6a8d-185">Na stronie zostanie wyświetlona wprowadzona lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-185">The page shows the location that you entered.</span></span> <span data-ttu-id="a6a8d-186">Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”</span><span class="sxs-lookup"><span data-stu-id="a6a8d-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="a6a8d-187">Wybierz opcję **Odśwież**, aby dodać kolejny licznik do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="a6a8d-188">W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję**, zaznacz pole **Pozycja**, a następnie wprowadź wartość *A0002*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="a6a8d-189">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-189">Select **OK**.</span></span>
1. <span data-ttu-id="a6a8d-190">W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję** wybierz **Num. id.**, a następnie wprowadź wartość *LP1002* (lub dowolny inny numer identyfikacyjny, pod warunkiem, że różni się on od numeru podanego wcześniej).</span><span class="sxs-lookup"><span data-stu-id="a6a8d-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="a6a8d-191">Zmień pozycję numeru identyfikacyjnego, ustawiając wartość pola **Pozycja num. id.** na *2*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="a6a8d-192">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-192">Select **OK**.</span></span>
1. <span data-ttu-id="a6a8d-193">Określ ilość towaru, która jest zliczana na podstawie numeru identyfikacyjnego, ustawiając wartość **Ilość** na *10*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="a6a8d-194">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-194">Select **OK**.</span></span>

    <span data-ttu-id="a6a8d-195">Na stronie zostanie wyświetlona wprowadzona lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-195">The page shows the location that you entered.</span></span> <span data-ttu-id="a6a8d-196">Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”</span><span class="sxs-lookup"><span data-stu-id="a6a8d-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="a6a8d-197">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-197">Select **OK**.</span></span>

<span data-ttu-id="a6a8d-198">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="a6a8d-199">Inwentaryzacja punktowa w drugiej lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-199">Spot-count the second location</span></span>

1. <span data-ttu-id="a6a8d-200">Na stronie **Inwentaryzacja punktowa**, w polu **Lokalizacja** określ wartość *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="a6a8d-201">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-201">Select **OK**.</span></span>

    <span data-ttu-id="a6a8d-202">Na stronie zostanie wyświetlona wprowadzona lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-202">The page shows the location that you entered.</span></span> <span data-ttu-id="a6a8d-203">Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”</span><span class="sxs-lookup"><span data-stu-id="a6a8d-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="a6a8d-204">Wybierz opcję **Odśwież**, aby dodać licznik do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="a6a8d-205">W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję**, zaznacz pole **Pozycja**, a następnie wprowadź wartość *A0002*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="a6a8d-206">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-206">Select **OK**.</span></span>
1. <span data-ttu-id="a6a8d-207">W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję** wybierz **Num. id.**, a następnie wprowadź wartość *LP1003* (lub dowolny inny numer identyfikacyjny, pod warunkiem, że różni się on od numerów podanych we wcześniejszej procedurze).</span><span class="sxs-lookup"><span data-stu-id="a6a8d-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="a6a8d-208">Strona **Licznik cykli: Dodaj nowy num. id. lub pozycję** pokazuje **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji 1**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="a6a8d-209">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-209">Select **OK**.</span></span>
1. <span data-ttu-id="a6a8d-210">Określ ilość towaru, która jest zliczana na podstawie numeru identyfikacyjnego, ustawiając wartość **Ilość** na *10*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="a6a8d-211">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-211">Select **OK**.</span></span>

    <span data-ttu-id="a6a8d-212">Na stronie zostanie wyświetlona wprowadzona lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-212">The page shows the location that you entered.</span></span> <span data-ttu-id="a6a8d-213">Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”</span><span class="sxs-lookup"><span data-stu-id="a6a8d-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="a6a8d-214">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-214">Select **OK**.</span></span>

<span data-ttu-id="a6a8d-215">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="a6a8d-216">Szczegóły pracy</span><span class="sxs-lookup"><span data-stu-id="a6a8d-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="a6a8d-217">Inwentaryzacje punktowe z poziomu aplikacji mobilnej tworzą plan inwentaryzacji ciągłej w Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="a6a8d-218">Praca wymaga przyjęcia tych inwentaryzacji przed zaksięgowaniem ich w magazynie.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="a6a8d-219">Zaloguj się w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="a6a8d-220">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="a6a8d-221">Na karcie **Przegląd** odszukaj wiersze, które mają następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="a6a8d-222">**Typ zlecenia pracy:** *Inwentaryzacja ciągła*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="a6a8d-223">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="a6a8d-224">**Stan pracy:** *Oczekiwanie na przegląd*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="a6a8d-225">Dla tych wierszy powinny były zostać utworzone dwa identyfikatory pracy.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="a6a8d-226">Należy zaakceptować te zliczenia dla obu tych identyfikatorów pracy.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="a6a8d-227">W siatce wybierz pierwszy identyfikator pracy dla zlecenia pracy *Inwentaryzacji ciągłej*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="a6a8d-228">W okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Inwentaryzacja ciągła**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="a6a8d-229">Wyświetlane są dwa wiersze, po jednym dla każdego towaru i numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="a6a8d-230">Wartości w polach **Ilość zliczona**, **Lokalizacja**, **Numer identyfikacyjny** i **Pozycja** powinny odpowiadać wpisom zliczania utworzonym na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="a6a8d-231">Jeśli którekolwiek z tych pól nie są widoczne, wybierz opcję **Wyświetl wymiary** w okienku akcji, aby dodać je do siatki.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="a6a8d-232">Wybierz oba wiersze.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-232">Select both lines.</span></span>
1. <span data-ttu-id="a6a8d-233">W okienku akcji wybierz pozycję **Potwierdź zliczanie**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="a6a8d-234">Zostanie wyświetlony komunikat „Księgowanie arkusza”.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="a6a8d-235">Wybierz opcję **Szczegóły komunikatu**, aby wyświetlić numer zaksięgowanego arkusza.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="a6a8d-236">Zamknij szczegóły komunikatu.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-236">Close the message details.</span></span>
1. <span data-ttu-id="a6a8d-237">Odśwież stronę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="a6a8d-238">Pierwszy identyfikator pracy został zamknięty i nie jest już wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="a6a8d-239">Aby wyświetlić zamkniętą pracę, zaznacz pole wyboru **Pokaż zamknięte**, znajdujące się nad siatką.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="a6a8d-240">Teraz będziesz akceptować pracę dla numeru identyfikacyjnego w lokalizacji *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="a6a8d-241">W zakładce **Przegląd** wybierz drugi identyfikator pracy dla zlecenia pracy *Inwentaryzacji ciągłej*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="a6a8d-242">W okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Inwentaryzacja ciągła**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="a6a8d-243">Jest wyświetlany jeden wiersz dla pozycji i numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="a6a8d-244">Wartości w polach **Ilość zliczona**, **Lokalizacja**, **Numer identyfikacyjny** i **Pozycja** powinny odpowiadać wpisom zliczania utworzonym na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="a6a8d-245">Wybierz wiersz.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-245">Select the line.</span></span>
1. <span data-ttu-id="a6a8d-246">W okienku akcji wybierz pozycję **Potwierdź zliczanie**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="a6a8d-247">Zostanie wyświetlony komunikat „Księgowanie arkusza”.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="a6a8d-248">Wybierz opcję **Szczegóły komunikatu**, aby wyświetlić numer zaksięgowanego arkusza.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="a6a8d-249">Zamknij szczegóły komunikatu.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-249">Close the message details.</span></span>
1. <span data-ttu-id="a6a8d-250">Odśwież stronę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="a6a8d-251">Drugi identyfikator pracy został zamknięty i nie jest już wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="a6a8d-252">Aby wyświetlić zamkniętą pracę, zaznacz pole wyboru **Pokaż zamknięte**, znajdujące się nad siatką.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="a6a8d-253">Dostępne zapasy według lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a6a8d-253">On-hand by location</span></span>

1. <span data-ttu-id="a6a8d-254">Wybierz kolejno opcje **Zarządzanie magazynem \> Zapytania i raporty \> Dostępne zapasy według lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="a6a8d-255">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-255">Set the following values:</span></span>

    - <span data-ttu-id="a6a8d-256">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-256">**Site:** *6*</span></span>
    - <span data-ttu-id="a6a8d-257">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="a6a8d-258">**Odśwież we wszystkich lokalizacjach:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="a6a8d-259">Należy zauważyć, że lokalizacja *01A01R1S1B* zawiera dwa numery identyfikacyjne:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="a6a8d-260">**A0001**, gdzie pole **Pozycja num. id.** ma wartość *1*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="a6a8d-261">**A0002**, gdzie pole **Pozycja num. id.** ma wartość *2*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="a6a8d-262">Należy zauważyć, że lokalizacja *01A01R1S2B* zawiera jeden numer identyfikacyjny:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="a6a8d-263">**A0002**, gdzie pole **Pozycja num. id.** ma wartość *1*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="a6a8d-264">Kryteria zamówień sprzedaży – scenariusz</span><span class="sxs-lookup"><span data-stu-id="a6a8d-264">Sales order scenario</span></span>

<span data-ttu-id="a6a8d-265">Teraz, gdy funkcja *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji* została skonfigurowana, a zapas został przemieszczony, należy utworzyć zamówienie sprzedaży w celu wygenerowania pracy pobrania, która będzie kierowała pracownika magazynu do pobrania *A0002* z lokalizacji magazynu, w której identyfikator palety znajduje się na pozycji *1*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="a6a8d-266">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a6a8d-267">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a6a8d-268">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a6a8d-269">**Konto odbiorcy:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="a6a8d-270">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="a6a8d-271">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-271">Select **OK**.</span></span>
1. <span data-ttu-id="a6a8d-272">Nowy wiersz zostanie dodany do siatki na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a6a8d-273">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a6a8d-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="a6a8d-274">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="a6a8d-275">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="a6a8d-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="a6a8d-276">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a6a8d-277">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy dla wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="a6a8d-278">Zamknij stronę **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="a6a8d-279">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="a6a8d-280">Użytkownik otrzymuje komunikat informacyjny, które zawiera identyfikator grupy czynności oraz identyfikatory wysyłki utworzone dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="a6a8d-281">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Magazyn** ponad siatką wybierz **Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="a6a8d-282">Zostanie wyświetlona strona **Praca**, która została utworzona dla danego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="a6a8d-283">Zanotuj pokazany identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="a6a8d-284">Scenariusz pobrania sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a6a8d-284">Sales picking scenario</span></span>

1. <span data-ttu-id="a6a8d-285">Otwórz mobilną aplikację magazynowania i zaloguj się jako użytkownik w magazynie *61*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="a6a8d-286">Przejdź do **Wychodzące \> Pobieranie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="a6a8d-287">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego**, zaznacz pole **Identyfikator**, a następnie wprowadź identyfikator pracy z wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="a6a8d-288">Należy zauważyć, że praca pobrania kieruje się do pobrania *A0002* z lokalizacji *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="a6a8d-289">Zostanie wyświetlona ta instrukcja, ponieważ *A0002* znajduje się na numerze identyfikacyjnym znajdującym się w pozycji *1* w tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="a6a8d-290">![Lokalizacja stanowiska 1](media/LocationLicensePlatePositioning.png "Lokalizacja stanowiska 1")</span><span class="sxs-lookup"><span data-stu-id="a6a8d-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="a6a8d-291">Wprowadź identyfikator numeru identyfikacyjnego, który został utworzony dla danej lokalizacji, a następnie postępuj zgodnie z instrukcjami, aby pobrać zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]