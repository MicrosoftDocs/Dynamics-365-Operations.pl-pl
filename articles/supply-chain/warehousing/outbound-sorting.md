---
title: Sortowanie towarów wychodzących
description: Ten temat zawiera informacje o sortowaniu towarów wychodzących. Ta funkcjonalność ułatwia obsługę małych pojemników i pomaga pracownikom magazynu lepiej planować i organizować pojemność palet w ciężarówce.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 2b0049269b69c0777420b3ecd9b1f649c4a1ab11
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963417"
---
# <a name="outbound-sorting"></a><span data-ttu-id="de933-104">Sortowanie towarów wychodzących</span><span class="sxs-lookup"><span data-stu-id="de933-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de933-105">Ta funkcjonalność ułatwia obsługę małych pojemników i pomaga pracownikom magazynu lepiej planować i organizować pojemność palet w ciężarówce.</span><span class="sxs-lookup"><span data-stu-id="de933-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="de933-106">W przypadku korzystania z sortowania wychodzącego można posortować spakowane kontenery na właściwej palecie, która znajduje się w stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="de933-107">Można również zbudować hierarchię pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="de933-108">Ta funkcja umożliwia tworzenie palet z kontenerów, które zostały zapakowane w ramach funkcji pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="de933-109">Kontener nie jest wysyłany do końcowej lokalizacji wysyłki, ponieważ znajduje się w oryginalnym przepływie pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="de933-110">Pracownicy mogą natomiast zamknąć kontener i przenieść go do lokalizacji typu sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="de933-111">Następnie mogą sortować kontenery według pozycji, z których każda ma numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="de933-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="de933-112">Po posortowaniu kontenerów można pracować w celu wysłania całego numeru identyfikacyjnego do ostatecznej lokalizacji doku wysyłkowego lub na scenę, w ulotce o dyrektywy lokalizacyjne lub własne wymagania.</span><span class="sxs-lookup"><span data-stu-id="de933-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="de933-113">Ponadto akcja zamknięcia pozycji sortowania może natychmiast przenieść zapasy do ostatecznej lokalizacji wysyłki i odebrać je do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="de933-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="de933-114">Włącz funkcję sortowania wychodzącego</span><span class="sxs-lookup"><span data-stu-id="de933-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="de933-115">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="de933-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="de933-116">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="de933-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="de933-117">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="de933-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="de933-118">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="de933-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="de933-119">**Nazwa funkcji:** *Sortowanie wychodzące*</span><span class="sxs-lookup"><span data-stu-id="de933-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="de933-120">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="de933-120">Setup</span></span>

<span data-ttu-id="de933-121">W tym scenariuszu należy stosować standardowe dane demonstracyjne **USMF** oraz magazyn *62*.</span><span class="sxs-lookup"><span data-stu-id="de933-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="de933-122">Należy również ukończyć konfigurację opisaną w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="de933-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="de933-123">Konfigurowanie szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="de933-123">Set up a wave template</span></span>

<span data-ttu-id="de933-124">Ta konfiguracja automatycznie przetwarza grupę czynności i tworzy pracę po zwolnieniu wiersza do magazynu.</span><span class="sxs-lookup"><span data-stu-id="de933-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="de933-125">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="de933-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="de933-126">Na liście szablonów wybierz **Magazyn 62**.</span><span class="sxs-lookup"><span data-stu-id="de933-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="de933-127">Na skróconej karcie **Ogólne** należy upewnić się, że opcja **Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu** jest ustawiona na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="de933-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="de933-128">Konfigurowanie pracownika</span><span class="sxs-lookup"><span data-stu-id="de933-128">Set up a worker</span></span>

<span data-ttu-id="de933-129">Stacja pakowania jest traktowana jako lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="de933-129">The packing station is considered a location.</span></span> <span data-ttu-id="de933-130">Pracownicy magazynowi, którzy logują się w stacji pakowania, widzą i pracują tylko w wysyłkach i kontenerach planowanych w danej lokalizacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="de933-131">Użytkownik, który zarejestruje się w Microsoft Dynamics 365, musi być skonfigurowany jako pracownik w zarządzaniu magazynem.</span><span class="sxs-lookup"><span data-stu-id="de933-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="de933-132">Jeśli na liście użytkowników pracy nie ma nazwy użytkownika, należy ją dodać, wykonując następującą procedurę:</span><span class="sxs-lookup"><span data-stu-id="de933-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="de933-133">W tych krokach przyjęto, że użytkownik już istnieje w systemie i jest skojarzony jako pracownik lub pracownik w module **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="de933-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="de933-134">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="de933-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="de933-135">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-135">Select **New**.</span></span>
1. <span data-ttu-id="de933-136">W polu **Pracownik** wybierz użytkownika docelowego z listy pracowników.</span><span class="sxs-lookup"><span data-stu-id="de933-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="de933-137">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="de933-137">Select **Select**.</span></span>
1. <span data-ttu-id="de933-138">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="de933-139">Na skróconej karcie **Użytkownicy** wybierz opcję **Nowy**, aby utworzyć konto urządzenia przenośnego, i określ dla niego następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="de933-140">**Identyfikator użytkownika:** wprowadź unikatowy identyfikator.</span><span class="sxs-lookup"><span data-stu-id="de933-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="de933-141">**Nazwa użytkownika:** wprowadź nazwę identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="de933-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="de933-142">**Magazyn domyślny:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-143">**Nazwa menu:** *Główne*</span><span class="sxs-lookup"><span data-stu-id="de933-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="de933-144">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="de933-145">Pojawi się okno dialogowe **Ustaw hasło**, w którym można utworzyć proste hasło, za pomocą którego użytkownik może zalogować w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="de933-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="de933-146">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-146">Set the following values:</span></span>

    - <span data-ttu-id="de933-147">**Hasło:** wprowadź proste hasło.</span><span class="sxs-lookup"><span data-stu-id="de933-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="de933-148">**Potwierdź hasło:** Wprowadź ponownie to samo hasło.</span><span class="sxs-lookup"><span data-stu-id="de933-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="de933-149">Wybierz opcję **Ustaw hasło**.</span><span class="sxs-lookup"><span data-stu-id="de933-149">Select **Set password**.</span></span>

    <span data-ttu-id="de933-150">Powiadomienie w centrum akcji informuje o ustawieniu hasła dla utworzonego przez niego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="de933-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="de933-151">Tworzenie typu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="de933-151">Create a location type</span></span>

1. <span data-ttu-id="de933-152">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Typy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="de933-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="de933-153">W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ lokalizacji, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="de933-154">**Typ lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="de933-155">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="de933-156">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="de933-157">Konfigurowanie parametrów zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="de933-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="de933-158">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="de933-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="de933-159">Na karcie **Ogólne**, na skróconej karcie **Typy lokalizacji** ustaw pole **Typ lokalizacji sortowania** na *Sortowanie*.</span><span class="sxs-lookup"><span data-stu-id="de933-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="de933-160">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="de933-161">Ustaw profil lokalizacji</span><span class="sxs-lookup"><span data-stu-id="de933-161">Set up a location profile</span></span>

1. <span data-ttu-id="de933-162">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="de933-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="de933-163">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-164">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="de933-165">**Identyfikator profilu lokalizacji:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="de933-166">**Nazwa:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="de933-167">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-168">**Format lokalizacji:** *ASRB* (korytarz— regał—półka—pojemnik)</span><span class="sxs-lookup"><span data-stu-id="de933-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="de933-169">**Typ lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="de933-170">**Używaj śledzenia numeru identyfikacyjnego:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="de933-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="de933-171">**Zezwalaj na towary mieszane:** *Tak* (Po ustawieniu tej opcji na wartość *Tak* opcja **Zezwalaj na mieszane partie zapasów** jest automatycznie ustawiana na wartość *Tak* i nie może być zmieniana niezależnie.)</span><span class="sxs-lookup"><span data-stu-id="de933-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="de933-172">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="de933-173">Ustaw lokalizację</span><span class="sxs-lookup"><span data-stu-id="de933-173">Set up a location</span></span>

1. <span data-ttu-id="de933-174">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="de933-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="de933-175">W nagłówku wyczyść pole wyboru **Generuj cyfry kontroli dla lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="de933-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="de933-176">W okienku akcji wybierz opcję **Nowy**, aby utworzyć lokalizację, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="de933-177">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-178">**Lokalizacja:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="de933-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="de933-179">**Identyfikator profilu lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="de933-180">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="de933-181">Ustaw szablon sortowania towarów wychodzących</span><span class="sxs-lookup"><span data-stu-id="de933-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="de933-182">Szablon sortowania towarów wychodzących określa, czy praca jest tworzona poza lokalizacją sortowania oraz czy sortowanie jest wykonywane ręcznie czy automatycznie.</span><span class="sxs-lookup"><span data-stu-id="de933-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="de933-183">W tym scenariuszu zostanie utworzony szablon sortowania towarów wychodzących w celu zbudowania palet po stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="de933-184">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Pakowanie \> Szablon sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="de933-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="de933-185">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-186">W nagłówku nowego szablonu określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="de933-187">**Identyfikator szablonu sortowania towarów wychodzących:** *Autopraca*</span><span class="sxs-lookup"><span data-stu-id="de933-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="de933-188">**Opis:** *Automatyczne tworzenie pracy*</span><span class="sxs-lookup"><span data-stu-id="de933-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="de933-189">**Typ szablonu sortowania towarów wychodzących:** *Kontener*</span><span class="sxs-lookup"><span data-stu-id="de933-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="de933-190">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-191">**Lokalizacja:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="de933-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="de933-192">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-193">**Typ weryfikacji sortowania:** *Skan pozycji*</span><span class="sxs-lookup"><span data-stu-id="de933-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="de933-194">**Utwórz pracę przy zamknięciu stanowiska:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="de933-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="de933-195">Jeśli opcja jest ustawiona na *Tak*, po zamknięciu stanowiska zostanie utworzona praca, aby przenieść zapasy do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="de933-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="de933-196">Jeśli opcja jest ustawiona na *Nie*, zapasy będą natychmiast pobierane dla zamówienia w momencie zamknięcia stanowiska.</span><span class="sxs-lookup"><span data-stu-id="de933-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="de933-197">**Przypisanie stanowiska:** *Automatyczne*</span><span class="sxs-lookup"><span data-stu-id="de933-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="de933-198">W przypadku ustawienia tego pola na *Ręcznie* użytkownik musi zawsze wskazać, do którego stanowiska należy sortować zapasy.</span><span class="sxs-lookup"><span data-stu-id="de933-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="de933-199">W przypadku ustawienia pola na *Automatycznie* system w miarę możliwości automatycznie poprowadzi zapasy do stanowiska na podstawie podziałów w szablonie sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="de933-200">Wybierz **Zapisz**, aby udostępnić opcję **Edytuj kwerendę** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="de933-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="de933-201">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="de933-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="de933-202">W edytorze zapytań na karcie **Sortowanie** dodaj wiersz o następujących wartościach:</span><span class="sxs-lookup"><span data-stu-id="de933-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="de933-203">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="de933-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="de933-204">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="de933-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="de933-205">**Pole:** *Usługa przewozowa*</span><span class="sxs-lookup"><span data-stu-id="de933-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="de933-206">Po wybraniu tej wartości może zostać wyświetlony następujący komunikat: „Usługa przewoźnika nie jest polem indeksu.</span><span class="sxs-lookup"><span data-stu-id="de933-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="de933-207">Czy na pewno chcesz dodać sortowanie według tego kryterium?”</span><span class="sxs-lookup"><span data-stu-id="de933-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="de933-208">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="de933-208">Select **Yes**.</span></span>

    - <span data-ttu-id="de933-209">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="de933-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="de933-210">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-210">Select **OK**.</span></span>
1. <span data-ttu-id="de933-211">Może zostać wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="de933-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="de933-212">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="de933-212">Select **Yes**.</span></span>

    <span data-ttu-id="de933-213">W okienku akcji zostanie udostępniony przycisk **Podziały szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="de933-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="de933-214">W okienku akcji wybierz pozycję **Podziały szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="de933-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="de933-215">W wyświetlonym oknie dialogowym **Kryteria sortowania towarów wychodzących** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="de933-216">**Nazwa tabeli odwołania:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="de933-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="de933-217">**Nazwa pola odwołania:** *Usługa przewoźnika*</span><span class="sxs-lookup"><span data-stu-id="de933-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="de933-218">**Grupuj według pola:** Należy zaznaczyć to pole wyboru, aby pogrupować wysyłki według usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="de933-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="de933-219">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.</span><span class="sxs-lookup"><span data-stu-id="de933-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="de933-220">Ustawianie zasad pakowania kontenerów</span><span class="sxs-lookup"><span data-stu-id="de933-220">Set up container packing policies</span></span>

1. <span data-ttu-id="de933-221">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Zasady pakowania kontenera**.</span><span class="sxs-lookup"><span data-stu-id="de933-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="de933-222">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-223">W nagłówku nowej zasady określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="de933-224">**Zasady pakowania kontenerów:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="de933-225">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="de933-226">Na skróconej karcie **Omówienie** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-227">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-228">**Domyślna lokalizacja do sortowania:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="de933-229">**Jednostka wagi:** *kg*</span><span class="sxs-lookup"><span data-stu-id="de933-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="de933-230">**Zasada zamykania kontenera:** *Automatyczne zwalnianie*</span><span class="sxs-lookup"><span data-stu-id="de933-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="de933-231">**Zasady zwalniania kontenerów:** *Przypisz kontener do pozycji sortowania towarów wyjściowych*</span><span class="sxs-lookup"><span data-stu-id="de933-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="de933-232">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="de933-233">Konfigurowanie profili pakowania</span><span class="sxs-lookup"><span data-stu-id="de933-233">Set up packing profiles</span></span>

<span data-ttu-id="de933-234">Utwórz nowy profil pakowania, który będzie używany razem z funkcją sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="de933-235">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.</span><span class="sxs-lookup"><span data-stu-id="de933-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="de933-236">W okienku akcji wybierz opcję **Nowy**, aby utworzyć linię, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="de933-237">**Identyfikator profilu pakowania:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="de933-238">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="de933-239">**Zasady pakowania kontenerów:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="de933-240">**Tryb identyfikatora kontenera:** *Automatyczny*</span><span class="sxs-lookup"><span data-stu-id="de933-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="de933-241">**Typ kontenera:** *Pudełko-duże*</span><span class="sxs-lookup"><span data-stu-id="de933-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="de933-242">**Automatycznie utwórz kontener przy zamknięciu kontenera:** Wyczyszczone (= *Nie*)</span><span class="sxs-lookup"><span data-stu-id="de933-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="de933-243">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="de933-244">Ustaw klasy pracy</span><span class="sxs-lookup"><span data-stu-id="de933-244">Set up work classes</span></span>

<span data-ttu-id="de933-245">Umożliwia skonfigurowanie klasy pracy, która będzie używana razem z sortowaniem.</span><span class="sxs-lookup"><span data-stu-id="de933-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="de933-246">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="de933-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="de933-247">W okienku akcji wybierz opcję **Nowy**, aby utworzyć klasę pracy dla sortowania, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="de933-248">**Identyfikator klasy roboczej:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="de933-249">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="de933-250">**Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*</span><span class="sxs-lookup"><span data-stu-id="de933-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="de933-251">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="de933-252">Konfigurowanie elementów menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="de933-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="de933-253">Konfigurowanie elementu menu nowej palety</span><span class="sxs-lookup"><span data-stu-id="de933-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="de933-254">Umożliwia utworzenie elementu menu urządzenia przenośnego w celu zbudowania palet podczas sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="de933-255">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="de933-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="de933-256">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-257">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="de933-258">**Nazwa elementu menu:** *kompilacja palety*</span><span class="sxs-lookup"><span data-stu-id="de933-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="de933-259">**Tytuł:** *kompilacja palety*</span><span class="sxs-lookup"><span data-stu-id="de933-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="de933-260">**Tryb:** *Pośrednie*</span><span class="sxs-lookup"><span data-stu-id="de933-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="de933-261">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="de933-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="de933-262">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-263">**Kod działania:** *Sortowanie towarów wychodzących*</span><span class="sxs-lookup"><span data-stu-id="de933-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="de933-264">Jeśli to pole jest ustawione na wartość *Sortowanie towarów wychodzących*, wyświetlane jest pole **Identyfikator szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="de933-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="de933-265">**Użyj przewodnika procesu:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="de933-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="de933-266">Jeśli w polu **Kod działania** wybrano opcję *Sortowanie towarów wychodzących*, ta opcja jest automatycznie ustawiana na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="de933-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="de933-267">**Identyfikator szablonu sortowania towarów wychodzących:** *Autopraca*</span><span class="sxs-lookup"><span data-stu-id="de933-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="de933-268">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="de933-269">Konfigurowanie elementu menu nowego ładowania</span><span class="sxs-lookup"><span data-stu-id="de933-269">Set up a new loading menu item</span></span>

<span data-ttu-id="de933-270">Następnie Utwórz element menu, który pozwoli użytkownikom przenieść posortowane towary magazynowe do lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="de933-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="de933-271">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="de933-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="de933-272">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-273">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="de933-274">**Nazwa elementu menu:** *ładowanie z sortowania*</span><span class="sxs-lookup"><span data-stu-id="de933-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="de933-275">**Tytuł:** *ładowanie z sortowania*</span><span class="sxs-lookup"><span data-stu-id="de933-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="de933-276">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="de933-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="de933-277">**Używanie istniejącej pracy:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="de933-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="de933-278">Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Sterowane przez użytkownika*.</span><span class="sxs-lookup"><span data-stu-id="de933-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="de933-279">Na skróconej karcie **Klasy pracy** wybierz opcję **Nowy**, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="de933-280">I **dentyfikator klasy pracy:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="de933-281">**Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*</span><span class="sxs-lookup"><span data-stu-id="de933-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="de933-282">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="de933-283">Konfigurowanie menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="de933-283">Set up the mobile device menu</span></span>

<span data-ttu-id="de933-284">Teraz musisz dodać nowe elementy menu do menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="de933-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="de933-285">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="de933-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="de933-286">Wybierz menu **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="de933-287">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="de933-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="de933-288">W kolumnie **Dostępne menu i elementy menu** znajdź i zaznacz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="de933-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="de933-289">Wybierz strzałkę w prawo, aby przenieść **Kompilacja palety** do kolumny **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="de933-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="de933-290">Za pomocą przycisków Strzałka w górę i Strzałka w dół można umieścić element menu **Kompiluj paletę** w wybranym miejscu w menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="de933-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="de933-291">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-291">Select **Save**.</span></span>
1. <span data-ttu-id="de933-292">Powtórz tę procedurę, aby dodać element menu **Ładowanie z sortowania** do menu **Towary wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="de933-293">Ustaw dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="de933-293">Set up location directives</span></span>

<span data-ttu-id="de933-294">*Dyrektywy lokalizacji* to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego.</span><span class="sxs-lookup"><span data-stu-id="de933-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="de933-295">Teraz musisz utworzyć regułę, aby zarządzać pracą sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="de933-296">Konfigurowanie pojedyńczej dyrektywy SKU</span><span class="sxs-lookup"><span data-stu-id="de933-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="de933-297">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="de933-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="de933-298">W lewym okienku zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="de933-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="de933-299">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-300">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="de933-301">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="de933-302">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="de933-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="de933-303">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-304">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="de933-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="de933-305">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="de933-305">**Site:** *6*</span></span>
    - <span data-ttu-id="de933-306">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-307">**Wiele jednostek SKU:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="de933-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="de933-308">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Wiersze** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="de933-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="de933-309">Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="de933-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="de933-310">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="de933-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="de933-311">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="de933-312">**Od:** *0*</span><span class="sxs-lookup"><span data-stu-id="de933-312">**From:** *0*</span></span>
    - <span data-ttu-id="de933-313">**Do:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="de933-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="de933-314">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Dyrektywy akcji lokalizacji** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="de933-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="de933-315">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="de933-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="de933-316">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="de933-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="de933-317">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="de933-318">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="de933-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="de933-319">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-319">Select **Save**.</span></span>
1. <span data-ttu-id="de933-320">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="de933-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="de933-321">W edytorze zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="de933-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="de933-322">Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="de933-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="de933-323">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="de933-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="de933-324">Konfigurowanie wielu dyrektyw SKU</span><span class="sxs-lookup"><span data-stu-id="de933-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="de933-325">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="de933-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="de933-326">W lewym okienku zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="de933-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="de933-327">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-328">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="de933-329">**Sekwencja:** *2*</span><span class="sxs-lookup"><span data-stu-id="de933-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="de933-330">**Nazwa:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="de933-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="de933-331">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-332">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="de933-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="de933-333">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="de933-333">**Site:** *6*</span></span>
    - <span data-ttu-id="de933-334">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-335">**Wiele SKU:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="de933-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="de933-336">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Wiersze** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="de933-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="de933-337">Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="de933-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="de933-338">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="de933-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="de933-339">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="de933-340">**Od:** *0*</span><span class="sxs-lookup"><span data-stu-id="de933-340">**From:** *0*</span></span>
    - <span data-ttu-id="de933-341">**Do:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="de933-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="de933-342">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Dyrektywy akcji lokalizacji** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="de933-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="de933-343">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="de933-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="de933-344">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="de933-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="de933-345">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="de933-346">**Nazwa:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="de933-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="de933-347">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-347">Select **Save**.</span></span>
1. <span data-ttu-id="de933-348">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="de933-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="de933-349">W edytorze zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="de933-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="de933-350">Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="de933-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="de933-351">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="de933-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="de933-352">Ustaw szablony pracy</span><span class="sxs-lookup"><span data-stu-id="de933-352">Set up work templates</span></span>

1. <span data-ttu-id="de933-353">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="de933-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="de933-354">Zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="de933-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="de933-355">W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.</span><span class="sxs-lookup"><span data-stu-id="de933-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="de933-356">Na karcie **Omówienie** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="de933-357">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="de933-358">**Szablon pracy:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="de933-359">**Opis szablonu pracy:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="de933-360">Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="de933-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="de933-361">Na skróconej karcie **Szczegóły szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz, a następnie określ dla niego następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="de933-362">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="de933-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="de933-363">I **dentyfikator klasy pracy:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="de933-364">Wybierz znowu **Nowe** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="de933-365">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="de933-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="de933-366">I **dentyfikator klasy pracy:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="de933-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="de933-367">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de933-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="de933-368">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="de933-368">Scenario</span></span>

<span data-ttu-id="de933-369">Ten scenariusz symuluje sytuację, w której spakowane kontenery powinny być automatycznie sortowane według różnych stanowisk (palet) po stanowisku pakowania, w zależności od usługi firmy przewozowej.</span><span class="sxs-lookup"><span data-stu-id="de933-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="de933-370">Po zapełnieniu wszystkich towarów z ładunku i posortowaniu ich według adresu paleta zostanie przeniesiona do bramy dokowej.</span><span class="sxs-lookup"><span data-stu-id="de933-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="de933-371">Tworzenie zlecenia pracy i pobierania zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="de933-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="de933-372">Utwórz zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="de933-372">Create sales order 1</span></span>

1. <span data-ttu-id="de933-373">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="de933-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="de933-374">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-375">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="de933-376">**Konto odbiorcy:** *US-005*</span><span class="sxs-lookup"><span data-stu-id="de933-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="de933-377">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="de933-378">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="de933-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="de933-379">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="de933-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="de933-380">Przełącz do widoku **nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="de933-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="de933-381">Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="de933-382">**Przewoźnik:** *Transport lotniczy*</span><span class="sxs-lookup"><span data-stu-id="de933-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="de933-383">**Usługa przewozowa:** *Lotnicza*</span><span class="sxs-lookup"><span data-stu-id="de933-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="de933-384">Przełącz się do widoku **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="de933-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="de933-385">Jeśli nowy wiersz nie został dodany automatycznie do siatki na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać.</span><span class="sxs-lookup"><span data-stu-id="de933-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="de933-386">Dla nowego wiersza zamówienia należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="de933-387">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="de933-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="de933-388">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="de933-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="de933-389">Gdy nowy wiersz zamówienia jest wciąż wybrany na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="de933-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="de933-390">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="de933-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="de933-391">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="de933-392">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="de933-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="de933-393">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="de933-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="de933-394">Zanotuj identyfikator grupy czynności i numery identyfikacyjne przesyłki.</span><span class="sxs-lookup"><span data-stu-id="de933-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="de933-395">Zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="de933-395">Sales order 2</span></span>

1. <span data-ttu-id="de933-396">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="de933-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="de933-397">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de933-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="de933-398">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="de933-399">**Konto odbiorcy:** *US-006*</span><span class="sxs-lookup"><span data-stu-id="de933-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="de933-400">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="de933-401">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="de933-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="de933-402">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="de933-402">The new sales order is opened.</span></span> <span data-ttu-id="de933-403">Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="de933-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="de933-404">Ustaw następujące wartości w tym wierszu zamówienia:</span><span class="sxs-lookup"><span data-stu-id="de933-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="de933-405">**Pozycja:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="de933-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="de933-406">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="de933-407">Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy określić wartość w polu **Metoda dostawy** na *Flowe-STD*.</span><span class="sxs-lookup"><span data-stu-id="de933-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="de933-408">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, a następnie określ następujące wartości w drugim wierszu:</span><span class="sxs-lookup"><span data-stu-id="de933-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="de933-409">**Pozycja:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="de933-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="de933-410">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="de933-411">Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy zmienić wartość w polu **Metoda dostawy** na *Air C-Air*.</span><span class="sxs-lookup"><span data-stu-id="de933-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="de933-412">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz pierwszy wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="de933-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="de933-413">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="de933-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="de933-414">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="de933-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="de933-415">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="de933-416">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz drugi wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="de933-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="de933-417">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="de933-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="de933-418">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="de933-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="de933-419">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="de933-420">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="de933-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="de933-421">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="de933-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="de933-422">Zwróć uwagę, że utworzono dwa numery identyfikacyjne grupy czynności i dwa numery identyfikacyjne przesyłki, po jednym dla każdego trybu dostawy dla wierszy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="de933-423">Pobierz identyfikatory pracy z szczegółów pracy</span><span class="sxs-lookup"><span data-stu-id="de933-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="de933-424">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="de933-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="de933-425">Na stronie są wyświetlane identyfikatory pracy, które zostały utworzone na podstawie zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="de933-426">Identyfikatory grupy czynności i identyfikatory wysyłki można stosować w utworzonych zamówieniach sprzedaży w celu znalezienia identyfikatora pracy dla każdej grupy czynności i wysyłki.</span><span class="sxs-lookup"><span data-stu-id="de933-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="de933-427">Zapisz identyfikatory pracy, ponieważ są one potrzebne w następnych krokach.</span><span class="sxs-lookup"><span data-stu-id="de933-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="de933-428">Zwróć uwagę, że utworzono dwa identyfikatory pracy dla drugiego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="de933-429">Jeśli różne towary są pobierane z różnych lokalizacji, generowane są oddzielne identyfikatory słowne.</span><span class="sxs-lookup"><span data-stu-id="de933-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="de933-430">Wybierz towary dla zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="de933-430">Pick items for the sales orders</span></span>

<span data-ttu-id="de933-431">Zakończ utworzoną pracę, korzystając z urządzenia przenośnego, aby przenieść elementy do stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="de933-432">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="de933-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="de933-433">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="de933-434">W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="de933-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="de933-435">W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="de933-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="de933-436">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-436">Select **OK**.</span></span>
1. <span data-ttu-id="de933-437">Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny, który został utworzony dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="de933-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="de933-438">Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-001*), pozycja (*A0001*) oraz ilość (*2 sztuki*).</span><span class="sxs-lookup"><span data-stu-id="de933-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="de933-439">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-439">Select **OK**.</span></span>
1. <span data-ttu-id="de933-440">Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="de933-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="de933-441">Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.</span><span class="sxs-lookup"><span data-stu-id="de933-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="de933-442">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-442">Select **OK**.</span></span>

    <span data-ttu-id="de933-443">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”, który wskazuje, że identyfikator pracy z zamówienia sprzedaży 1 został zakończony.</span><span class="sxs-lookup"><span data-stu-id="de933-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="de933-444">Teraz zostanie pobrane zamówienie sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="de933-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="de933-445">W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 2, gdzie wiersz 1 ma element *A0001*.</span><span class="sxs-lookup"><span data-stu-id="de933-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="de933-446">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-446">Select **OK**.</span></span>
1. <span data-ttu-id="de933-447">Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="de933-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="de933-448">Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-001*), pozycja (*A0001*) oraz ilość (*1 sztuki*).</span><span class="sxs-lookup"><span data-stu-id="de933-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="de933-449">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-449">Select **OK**.</span></span>
1. <span data-ttu-id="de933-450">Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="de933-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="de933-451">Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.</span><span class="sxs-lookup"><span data-stu-id="de933-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="de933-452">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-452">Select **OK**.</span></span>

    <span data-ttu-id="de933-453">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="de933-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="de933-454">Ten komunikat wskazuje, że wykonano identyfikator pracy z wiersza 1 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="de933-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="de933-455">W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 2, gdzie wiersz 2 ma element *A0002*.</span><span class="sxs-lookup"><span data-stu-id="de933-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="de933-456">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-456">Select **OK**.</span></span>
1. <span data-ttu-id="de933-457">Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="de933-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="de933-458">Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-002*), pozycja (*A0001*) oraz ilość (*1 sztuki*).</span><span class="sxs-lookup"><span data-stu-id="de933-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="de933-459">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-459">Select **OK**.</span></span>
1. <span data-ttu-id="de933-460">Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="de933-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="de933-461">Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.</span><span class="sxs-lookup"><span data-stu-id="de933-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="de933-462">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-462">Select **OK**.</span></span>

    <span data-ttu-id="de933-463">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="de933-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="de933-464">Ten komunikat wskazuje, że wykonano identyfikator pracy z wiersza 2 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="de933-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="de933-465">Pakowanie zamówień sprzedaży do kontenerów</span><span class="sxs-lookup"><span data-stu-id="de933-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="de933-466">Pakowanie zamówienia 1 sprzedaży do kontenerów</span><span class="sxs-lookup"><span data-stu-id="de933-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="de933-467">Przejdź do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Pakunek**.</span><span class="sxs-lookup"><span data-stu-id="de933-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="de933-468">Wyświetli się okno dialogowe **Wybierz stację pakowania**.</span><span class="sxs-lookup"><span data-stu-id="de933-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="de933-469">Domyślnie pole **Pracownik** powinno mieć ustawioną nazwę pracownika skonfigurowanego wcześniej.</span><span class="sxs-lookup"><span data-stu-id="de933-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="de933-470">Poniższe wartości umożliwiają wyświetlanie i pracę z wysyłkami i kontenerami planowanymi w określonej lokalizacji pakowania:</span><span class="sxs-lookup"><span data-stu-id="de933-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="de933-471">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="de933-471">**Site:** *6*</span></span>
    - <span data-ttu-id="de933-472">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="de933-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="de933-473">**Lokalizacja:** *Pakiet*</span><span class="sxs-lookup"><span data-stu-id="de933-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="de933-474">**Identyfikator profilu pakowania:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="de933-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="de933-475">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="de933-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="de933-476">Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="de933-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="de933-477">Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.</span><span class="sxs-lookup"><span data-stu-id="de933-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="de933-478">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="de933-479">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="de933-480">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="de933-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="de933-481">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-482">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="de933-483">**Identyfikator:** pozycja *A0001*</span><span class="sxs-lookup"><span data-stu-id="de933-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="de933-484">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="de933-485">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="de933-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="de933-486">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-486">Select **OK**.</span></span> <span data-ttu-id="de933-487">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="de933-488">Utwórz drugi kontener, aby dodać drugi towar z numeru identyfikacyjnego dla zamówienia sprzedaży 1 do nowego kontenera.</span><span class="sxs-lookup"><span data-stu-id="de933-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="de933-489">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="de933-490">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="de933-491">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="de933-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="de933-492">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-493">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="de933-494">**Identyfikator:** pozycja *A0001*</span><span class="sxs-lookup"><span data-stu-id="de933-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="de933-495">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="de933-496">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="de933-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="de933-497">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-497">Select **OK**.</span></span> <span data-ttu-id="de933-498">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="de933-499">Pakowanie zamówienia 2 sprzedaży do kontenerów</span><span class="sxs-lookup"><span data-stu-id="de933-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="de933-500">Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla wiersza 1 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="de933-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="de933-501">Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.</span><span class="sxs-lookup"><span data-stu-id="de933-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="de933-502">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="de933-503">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="de933-504">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="de933-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="de933-505">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-506">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="de933-507">**Identyfikator:** pozycja *A0001*</span><span class="sxs-lookup"><span data-stu-id="de933-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="de933-508">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="de933-509">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="de933-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="de933-510">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-510">Select **OK**.</span></span> <span data-ttu-id="de933-511">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="de933-512">Wpolu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla wiersza 2 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="de933-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="de933-513">Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.</span><span class="sxs-lookup"><span data-stu-id="de933-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="de933-514">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="de933-515">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="de933-516">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="de933-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="de933-517">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="de933-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="de933-518">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="de933-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="de933-519">**Pole identyfikatora:** pozycja *A0002*</span><span class="sxs-lookup"><span data-stu-id="de933-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="de933-520">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="de933-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="de933-521">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="de933-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="de933-522">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-522">Select **OK**.</span></span> <span data-ttu-id="de933-523">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="de933-524">Aby wyświetlić szczegóły kontenera, należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Kontenery** oraz wyszukać identyfikatory kontenerów, które zostały utworzone podczas pakowania.</span><span class="sxs-lookup"><span data-stu-id="de933-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="de933-525">Sortowanie kontenerów</span><span class="sxs-lookup"><span data-stu-id="de933-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de933-526">Po dostępie do elementu menu **Kompilacja palety** w aplikacji mobilnej do sortowania wychodzącego wyświetlany jest przycisk z etykietą **Pełna**.</span><span class="sxs-lookup"><span data-stu-id="de933-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="de933-527">*Nie używaj przycisku **Pełne** do sortowania lub zamykania stanowiska.*</span><span class="sxs-lookup"><span data-stu-id="de933-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="de933-528">Przycisk **Pełny** jest domyślnie dostępny i nie można go wyłączyć ani usunąć ze strony.</span><span class="sxs-lookup"><span data-stu-id="de933-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="de933-529">Nie jest używany dla funkcji *Sortowanie towarów wychodzących*.</span><span class="sxs-lookup"><span data-stu-id="de933-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="de933-530">Sortuj pierwszy kontener</span><span class="sxs-lookup"><span data-stu-id="de933-530">Sort the first container</span></span>

1. <span data-ttu-id="de933-531">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="de933-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="de933-532">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="de933-533">W menu **Wychodzące** wybierz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="de933-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="de933-534">W polu **LP/Con** wprowadź pierwszy identyfikator kontenera skojarzony z zamówieniem sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="de933-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="de933-535">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-535">Select **OK**.</span></span>
1. <span data-ttu-id="de933-536">Ponieważ nie istnieją obecnie pozycje sortowania, należy je określić.</span><span class="sxs-lookup"><span data-stu-id="de933-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="de933-537">W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="de933-538">Ponieważ żaden numer identyfikacyjny nie jest aktualnie skojarzony z pozycją sortowania *SP01*, należy określić jeden z nich.</span><span class="sxs-lookup"><span data-stu-id="de933-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="de933-539">W polu **Numer identyfikacyjny** wprowadź *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="de933-540">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-540">Select **OK**.</span></span>
1. <span data-ttu-id="de933-541">Ponieważ sprawdzanie poprawności pozycji sortowania jest włączone, należy ponownie wprowadzić identyfikator pozycji sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="de933-542">W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="de933-543">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-543">Select **OK**.</span></span>

    <span data-ttu-id="de933-544">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="de933-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="de933-545">Aby wyświetlić pozycję sortowania i numer identyfikacyjny w tym celu należy przejść do pola pakowanie w **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="de933-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="de933-546">Na stronie **Przypisania stanowisk sortowania towarów wychodzących** wyświetlane są wszystkie stanowiska, które są obecnie aktywne.</span><span class="sxs-lookup"><span data-stu-id="de933-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="de933-547">W polu **Transakcja na stanowisku sortowania** wyświetlany jest numer numer identyfikacyjny skojarzony z poszczególnymi pozycjami sortowania oraz kontenery znajdujące się na położeniu sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="de933-548">Zauważ, że jedna pozycja sortowania już istnieje, a skrócona karta **Kryteria stanowiska sortowania** przedstawia kryterium **Wysyłka - usługa przewoźnika - powietrze**.</span><span class="sxs-lookup"><span data-stu-id="de933-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="de933-549">Posortuj pozostałe pojemniki</span><span class="sxs-lookup"><span data-stu-id="de933-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="de933-550">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="de933-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="de933-551">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="de933-552">W menu **Wychodzące** wybierz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="de933-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="de933-553">W polu **LP/Con** wprowadź drugi identyfikator kontenera skojarzony z zamówieniem sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="de933-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="de933-554">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-554">Select **OK**.</span></span> <span data-ttu-id="de933-555">Ponieważ szablon sortowania jest skonfigurowany do automatycznego sortowania, a pozycja sortowania, która ma kryteria dopasowywania, już istnieje, jest automatycznie kierowana do właściwej pozycji sortowania.</span><span class="sxs-lookup"><span data-stu-id="de933-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="de933-556">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-556">Select **OK**.</span></span>
1. <span data-ttu-id="de933-557">Potwierdź identyfikator stanowiska sortowania, aby wskazać, że ilość zapasów znajduje się w odpowiednim miejscu.</span><span class="sxs-lookup"><span data-stu-id="de933-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="de933-558">W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="de933-559">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-559">Select **OK**.</span></span>

    <span data-ttu-id="de933-560">Praca została zakończona dla drugiego kontenera z zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="de933-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="de933-561">Teraz zostaną posortowane pozostałe kontenery z zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="de933-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="de933-562">W polu **LP/Con** wprowadź identyfikator kontenera z zamówienia sprzedaży 2, który zawiera pozycję *A0001*.</span><span class="sxs-lookup"><span data-stu-id="de933-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="de933-563">Ponieważ usługa przewoźnika jest inna, system wyświetli monit o wprowadzenie nowej pozycji sortowania i przypisanie do tego stanowiska obiektu numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="de933-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="de933-564">Należy skorzystać z pozycji sortowania *SP02* i numer identyfikacyjny *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="de933-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="de933-565">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-565">Select **OK**.</span></span>
1. <span data-ttu-id="de933-566">Potwierdź pozycję sortowania, wprowadzając *SP02* w polu **Identyfikator pozycji sortowania**.</span><span class="sxs-lookup"><span data-stu-id="de933-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="de933-567">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-567">Select **OK**.</span></span>

    <span data-ttu-id="de933-568">Praca w kontenerze została zakończona.</span><span class="sxs-lookup"><span data-stu-id="de933-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="de933-569">W polu **LP/Con** wprowadź identyfikator ostatniego kontenera z zamówienia sprzedaży 2, który zawiera pozycję *A0002*.</span><span class="sxs-lookup"><span data-stu-id="de933-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="de933-570">Ponieważ usługa przewoźnika jest taka sama jak usługa przewoźnika dla zamówienia sprzedaży 1, system pokazuje istniejącą pozycję sortowania, która ma kryteria dopasowywania.</span><span class="sxs-lookup"><span data-stu-id="de933-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="de933-571">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-571">Select **OK**.</span></span>
1. <span data-ttu-id="de933-572">Potwierdź pozycję sortowania, wprowadzając *SP01* w polu **Identyfikator pozycji sortowania**.</span><span class="sxs-lookup"><span data-stu-id="de933-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="de933-573">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-573">Select **OK**.</span></span>

    <span data-ttu-id="de933-574">Praca w kontenerze została zakończona.</span><span class="sxs-lookup"><span data-stu-id="de933-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="de933-575">Zamknij wychodzące pozycje sortowania</span><span class="sxs-lookup"><span data-stu-id="de933-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="de933-576">Po posortowaniu wszystkich zapasów należy zamknąć to stanowisko, aby można było utworzyć pracę.</span><span class="sxs-lookup"><span data-stu-id="de933-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="de933-577">Zostaną utworzone posortowane prace związane z pobieraniem zapasów, aby przenieść je do bramy dokowej.</span><span class="sxs-lookup"><span data-stu-id="de933-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="de933-578">Zamykanie stanowiska z urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="de933-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="de933-579">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="de933-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="de933-580">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="de933-581">W menu **Wychodzące** wybierz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="de933-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="de933-582">W polu **LP/Con** wprowadź identyfikator kontenera, który został posortowany w celu posortowania pozycji *SP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="de933-583">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-583">Select **OK**.</span></span>
1. <span data-ttu-id="de933-584">Pojawi się następujący komunikat: „Kontener jest już posortowany do stanowiska SP01.</span><span class="sxs-lookup"><span data-stu-id="de933-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="de933-585">Zamknąć to stanowisko?”</span><span class="sxs-lookup"><span data-stu-id="de933-585">Close the position?"</span></span> <span data-ttu-id="de933-586">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="de933-586">Select **Close**.</span></span>

    <span data-ttu-id="de933-587">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="de933-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="de933-588">Zamykanie stanowiska z przypisań pozycji sortowania wychodzącego</span><span class="sxs-lookup"><span data-stu-id="de933-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="de933-589">Należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="de933-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="de933-590">W lewej kolumnie wybierz **SP02**.</span><span class="sxs-lookup"><span data-stu-id="de933-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="de933-591">Ten wiersz określający pozycję sortowania dla zapasów wychodzących jest tym, który zostanie zamknięty.</span><span class="sxs-lookup"><span data-stu-id="de933-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="de933-592">W okienku akcji wybierz opcję **Zamknij stanowisko**.</span><span class="sxs-lookup"><span data-stu-id="de933-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="de933-593">Rekord stanowiska sortowania jest zamknięty i nie jest już wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="de933-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="de933-594">Aby wyświetlić wszystkie rekordy zamkniętych stanowisk, zaznacz pole wyboru **Wyświetl zamknięte**.</span><span class="sxs-lookup"><span data-stu-id="de933-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="de933-595">Pobranie z posortowanych zapasów</span><span class="sxs-lookup"><span data-stu-id="de933-595">Sorted inventory picking</span></span>

<span data-ttu-id="de933-596">Należy wykonać posortowaną pracę pobrania z magazynu.</span><span class="sxs-lookup"><span data-stu-id="de933-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="de933-597">Po zakończeniu Inwentaryzacja zostanie pobrana do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="de933-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="de933-598">W tym momencie obowiązują wszystkie inne procesy magazynowe.</span><span class="sxs-lookup"><span data-stu-id="de933-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="de933-599">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="de933-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="de933-600">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="de933-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="de933-601">W menu **Wychodzące** wybierz opcję **Ładowanie z sortowania**.</span><span class="sxs-lookup"><span data-stu-id="de933-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="de933-602">Wprowadź identyfikator docelowego z pierwszej pozycji sortowania, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="de933-603">Ustaw wartość w polu **Identyfikator** na *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="de933-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="de933-604">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-604">Select **OK**.</span></span>
1. <span data-ttu-id="de933-605">Strona **Odbieranie sortowanych zapasów: Odbiór** zawiera listę prac pobrań, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="de933-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="de933-606">Pobranie z lokalizacji *SORTOWANIE* i docelowego numeru identyfikacyjnego *PLP01*, który ma wiele towarów i ilość *3*.</span><span class="sxs-lookup"><span data-stu-id="de933-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="de933-607">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-607">Select **OK**.</span></span>
1. <span data-ttu-id="de933-608">Strona **Odbieranie sortowanych zapasów: Odłożenie** zawiera listę prac odkładania, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="de933-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="de933-609">Odkładanie z lokalizacji *Baydoor* i docelowego numeru identyfikacyjnego *PLP01*, który ma wiele towarów i ilość *3*.</span><span class="sxs-lookup"><span data-stu-id="de933-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="de933-610">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-610">Select **OK**.</span></span>

    <span data-ttu-id="de933-611">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="de933-611">Work is completed.</span></span>

1. <span data-ttu-id="de933-612">Wprowadź docelowy numer identyfikacyjny z drugie pozycji sortowania, *SP02*.</span><span class="sxs-lookup"><span data-stu-id="de933-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="de933-613">Ustaw wartość w polu **Identyfikator** na *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="de933-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="de933-614">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-614">Select **OK**.</span></span>
1. <span data-ttu-id="de933-615">Strona **Odbieranie sortowanych zapasów: Odbiór** zawiera listę prac pobrań, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="de933-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="de933-616">Pobranie z lokalizacji *SORTOWANIE* i docelowego numeru identyfikacyjnego *PLP02*, który ma wiele towarów i ilość *1*.</span><span class="sxs-lookup"><span data-stu-id="de933-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="de933-617">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-617">Select **OK**.</span></span>
1. <span data-ttu-id="de933-618">Strona **Odbieranie sortowanych zapasów: Odłożenie** zawiera listę prac odkładania, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="de933-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="de933-619">Odkładanie z lokalizacji *Baydoor* i docelowego numeru identyfikacyjnego *PLP02*, który ma wiele towarów i ilość *1*.</span><span class="sxs-lookup"><span data-stu-id="de933-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="de933-620">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de933-620">Select **OK**.</span></span>

    <span data-ttu-id="de933-621">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="de933-621">Work is completed.</span></span>

<span data-ttu-id="de933-622">Od tego momentu obowiązują wszystkie inne procesy magazynowe.</span><span class="sxs-lookup"><span data-stu-id="de933-622">From this point forward, all other warehouse processes apply.</span></span>
