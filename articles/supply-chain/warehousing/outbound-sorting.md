---
title: Sortowanie towarów wychodzących
description: Ten temat zawiera informacje o sortowaniu towarów wychodzących. Ta funkcjonalność ułatwia obsługę małych pojemników i pomaga pracownikom magazynu lepiej planować i organizować pojemność palet w ciężarówce.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3c576209a86f776ac424f7fb9f2b606bea774a67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828401"
---
# <a name="outbound-sorting"></a><span data-ttu-id="f3c29-104">Sortowanie towarów wychodzących</span><span class="sxs-lookup"><span data-stu-id="f3c29-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3c29-105">Ta funkcjonalność ułatwia obsługę małych pojemników i pomaga pracownikom magazynu lepiej planować i organizować pojemność palet w ciężarówce.</span><span class="sxs-lookup"><span data-stu-id="f3c29-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="f3c29-106">W przypadku korzystania z sortowania wychodzącego można posortować spakowane kontenery na właściwej palecie, która znajduje się w stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="f3c29-107">Można również zbudować hierarchię pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="f3c29-108">Ta funkcja umożliwia tworzenie palet z kontenerów, które zostały zapakowane w ramach funkcji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="f3c29-109">Kontener nie jest wysyłany do końcowej lokalizacji wysyłki, ponieważ znajduje się w oryginalnym przepływie pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="f3c29-110">Pracownicy mogą natomiast zamknąć kontener i przenieść go do lokalizacji typu sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="f3c29-111">Następnie mogą sortować kontenery według pozycji, z których każda ma numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="f3c29-112">Po posortowaniu kontenerów można pracować w celu wysłania całego numeru identyfikacyjnego do ostatecznej lokalizacji doku wysyłkowego lub na scenę, w ulotce o dyrektywy lokalizacyjne lub własne wymagania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="f3c29-113">Ponadto akcja zamknięcia pozycji sortowania może natychmiast przenieść zapasy do ostatecznej lokalizacji wysyłki i odebrać je do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f3c29-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="f3c29-114">Włącz funkcję sortowania wychodzącego</span><span class="sxs-lookup"><span data-stu-id="f3c29-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="f3c29-115">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="f3c29-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="f3c29-116">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="f3c29-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f3c29-117">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f3c29-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f3c29-118">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="f3c29-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f3c29-119">**Nazwa funkcji:** *Sortowanie wychodzące*</span><span class="sxs-lookup"><span data-stu-id="f3c29-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="f3c29-120">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="f3c29-120">Setup</span></span>

<span data-ttu-id="f3c29-121">W tym scenariuszu należy stosować standardowe dane demonstracyjne **USMF** oraz magazyn *62*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="f3c29-122">Należy również ukończyć konfigurację opisaną w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="f3c29-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="f3c29-123">Konfigurowanie szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="f3c29-123">Set up a wave template</span></span>

<span data-ttu-id="f3c29-124">Ta konfiguracja automatycznie przetwarza grupę czynności i tworzy pracę po zwolnieniu wiersza do magazynu.</span><span class="sxs-lookup"><span data-stu-id="f3c29-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="f3c29-125">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="f3c29-126">Na liście szablonów wybierz **Magazyn 62**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="f3c29-127">Na skróconej karcie **Ogólne** należy upewnić się, że opcja **Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu** jest ustawiona na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="f3c29-128">Konfigurowanie pracownika</span><span class="sxs-lookup"><span data-stu-id="f3c29-128">Set up a worker</span></span>

<span data-ttu-id="f3c29-129">Stacja pakowania jest traktowana jako lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="f3c29-129">The packing station is considered a location.</span></span> <span data-ttu-id="f3c29-130">Pracownicy magazynowi, którzy logują się w stacji pakowania, widzą i pracują tylko w wysyłkach i kontenerach planowanych w danej lokalizacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="f3c29-131">Użytkownik, który zarejestruje się w Microsoft Dynamics 365, musi być skonfigurowany jako pracownik w zarządzaniu magazynem.</span><span class="sxs-lookup"><span data-stu-id="f3c29-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="f3c29-132">Jeśli na liście użytkowników pracy nie ma nazwy użytkownika, należy ją dodać, wykonując następującą procedurę:</span><span class="sxs-lookup"><span data-stu-id="f3c29-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="f3c29-133">W tych krokach przyjęto, że użytkownik już istnieje w systemie i jest skojarzony jako pracownik lub pracownik w module **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="f3c29-134">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="f3c29-135">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-135">Select **New**.</span></span>
1. <span data-ttu-id="f3c29-136">W polu **Pracownik** wybierz użytkownika docelowego z listy pracowników.</span><span class="sxs-lookup"><span data-stu-id="f3c29-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="f3c29-137">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-137">Select **Select**.</span></span>
1. <span data-ttu-id="f3c29-138">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f3c29-139">Na skróconej karcie **Użytkownicy** wybierz opcję **Nowy**, aby utworzyć konto urządzenia przenośnego, i określ dla niego następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-140">**Identyfikator użytkownika:** wprowadź unikatowy identyfikator.</span><span class="sxs-lookup"><span data-stu-id="f3c29-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="f3c29-141">**Nazwa użytkownika:** wprowadź nazwę identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="f3c29-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="f3c29-142">**Magazyn domyślny:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-143">**Nazwa menu:** *Główne*</span><span class="sxs-lookup"><span data-stu-id="f3c29-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="f3c29-144">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f3c29-145">Pojawi się okno dialogowe **Ustaw hasło**, w którym można utworzyć proste hasło, za pomocą którego użytkownik może zalogować w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="f3c29-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="f3c29-146">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-146">Set the following values:</span></span>

    - <span data-ttu-id="f3c29-147">**Hasło:** wprowadź proste hasło.</span><span class="sxs-lookup"><span data-stu-id="f3c29-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="f3c29-148">**Potwierdź hasło:** Wprowadź ponownie to samo hasło.</span><span class="sxs-lookup"><span data-stu-id="f3c29-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="f3c29-149">Wybierz opcję **Ustaw hasło**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-149">Select **Set password**.</span></span>

    <span data-ttu-id="f3c29-150">Powiadomienie w centrum akcji informuje o ustawieniu hasła dla utworzonego przez niego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f3c29-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="f3c29-151">Tworzenie typu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="f3c29-151">Create a location type</span></span>

1. <span data-ttu-id="f3c29-152">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Typy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="f3c29-153">W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ lokalizacji, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-154">**Typ lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="f3c29-155">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="f3c29-156">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="f3c29-157">Konfigurowanie parametrów zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="f3c29-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="f3c29-158">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="f3c29-159">Na karcie **Ogólne**, na skróconej karcie **Typy lokalizacji** ustaw pole **Typ lokalizacji sortowania** na *Sortowanie*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="f3c29-160">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="f3c29-161">Ustaw profil lokalizacji</span><span class="sxs-lookup"><span data-stu-id="f3c29-161">Set up a location profile</span></span>

1. <span data-ttu-id="f3c29-162">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="f3c29-163">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-164">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="f3c29-165">**Identyfikator profilu lokalizacji:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="f3c29-166">**Nazwa:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="f3c29-167">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-168">**Format lokalizacji:** *ASRB* (korytarz— regał—półka—pojemnik)</span><span class="sxs-lookup"><span data-stu-id="f3c29-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="f3c29-169">**Typ lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="f3c29-170">**Używaj śledzenia numeru identyfikacyjnego:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f3c29-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="f3c29-171">**Zezwalaj na towary mieszane:** *Tak* (Po ustawieniu tej opcji na wartość *Tak* opcja **Zezwalaj na mieszane partie zapasów** jest automatycznie ustawiana na wartość *Tak* i nie może być zmieniana niezależnie.)</span><span class="sxs-lookup"><span data-stu-id="f3c29-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="f3c29-172">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="f3c29-173">Ustaw lokalizację</span><span class="sxs-lookup"><span data-stu-id="f3c29-173">Set up a location</span></span>

1. <span data-ttu-id="f3c29-174">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="f3c29-175">W nagłówku wyczyść pole wyboru **Generuj cyfry kontroli dla lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="f3c29-176">W okienku akcji wybierz opcję **Nowy**, aby utworzyć lokalizację, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-177">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-178">**Lokalizacja:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="f3c29-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="f3c29-179">**Identyfikator profilu lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="f3c29-180">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="f3c29-181">Ustaw szablon sortowania towarów wychodzących</span><span class="sxs-lookup"><span data-stu-id="f3c29-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="f3c29-182">Szablon sortowania towarów wychodzących określa, czy praca jest tworzona poza lokalizacją sortowania oraz czy sortowanie jest wykonywane ręcznie czy automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f3c29-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="f3c29-183">W tym scenariuszu zostanie utworzony szablon sortowania towarów wychodzących w celu zbudowania palet po stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="f3c29-184">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Pakowanie \> Szablon sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="f3c29-185">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-186">W nagłówku nowego szablonu określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="f3c29-187">**Identyfikator szablonu sortowania towarów wychodzących:** *Autopraca*</span><span class="sxs-lookup"><span data-stu-id="f3c29-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="f3c29-188">**Opis:** *Automatyczne tworzenie pracy*</span><span class="sxs-lookup"><span data-stu-id="f3c29-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="f3c29-189">**Typ szablonu sortowania towarów wychodzących:** *Kontener*</span><span class="sxs-lookup"><span data-stu-id="f3c29-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="f3c29-190">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-191">**Lokalizacja:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="f3c29-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="f3c29-192">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-193">**Typ weryfikacji sortowania:** *Skan pozycji*</span><span class="sxs-lookup"><span data-stu-id="f3c29-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="f3c29-194">**Utwórz pracę przy zamknięciu stanowiska:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f3c29-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="f3c29-195">Jeśli opcja jest ustawiona na *Tak*, po zamknięciu stanowiska zostanie utworzona praca, aby przenieść zapasy do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f3c29-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="f3c29-196">Jeśli opcja jest ustawiona na *Nie*, zapasy będą natychmiast pobierane dla zamówienia w momencie zamknięcia stanowiska.</span><span class="sxs-lookup"><span data-stu-id="f3c29-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="f3c29-197">**Przypisanie stanowiska:** *Automatyczne*</span><span class="sxs-lookup"><span data-stu-id="f3c29-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="f3c29-198">W przypadku ustawienia tego pola na *Ręcznie* użytkownik musi zawsze wskazać, do którego stanowiska należy sortować zapasy.</span><span class="sxs-lookup"><span data-stu-id="f3c29-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="f3c29-199">W przypadku ustawienia pola na *Automatycznie* system w miarę możliwości automatycznie poprowadzi zapasy do stanowiska na podstawie podziałów w szablonie sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="f3c29-200">Wybierz **Zapisz**, aby udostępnić opcję **Edytuj kwerendę** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="f3c29-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="f3c29-201">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="f3c29-202">W edytorze zapytań na karcie **Sortowanie** dodaj wiersz o następujących wartościach:</span><span class="sxs-lookup"><span data-stu-id="f3c29-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="f3c29-203">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="f3c29-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="f3c29-204">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="f3c29-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="f3c29-205">**Pole:** *Usługa przewozowa*</span><span class="sxs-lookup"><span data-stu-id="f3c29-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="f3c29-206">Po wybraniu tej wartości może zostać wyświetlony następujący komunikat: „Usługa przewoźnika nie jest polem indeksu.</span><span class="sxs-lookup"><span data-stu-id="f3c29-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="f3c29-207">Czy na pewno chcesz dodać sortowanie według tego kryterium?”</span><span class="sxs-lookup"><span data-stu-id="f3c29-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="f3c29-208">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-208">Select **Yes**.</span></span>

    - <span data-ttu-id="f3c29-209">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="f3c29-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="f3c29-210">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-210">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-211">Może zostać wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="f3c29-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="f3c29-212">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-212">Select **Yes**.</span></span>

    <span data-ttu-id="f3c29-213">W okienku akcji zostanie udostępniony przycisk **Podziały szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="f3c29-214">W okienku akcji wybierz pozycję **Podziały szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="f3c29-215">W wyświetlonym oknie dialogowym **Kryteria sortowania towarów wychodzących** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="f3c29-216">**Nazwa tabeli odwołania:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="f3c29-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="f3c29-217">**Nazwa pola odwołania:** *Usługa przewoźnika*</span><span class="sxs-lookup"><span data-stu-id="f3c29-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="f3c29-218">**Grupuj według pola:** Należy zaznaczyć to pole wyboru, aby pogrupować wysyłki według usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="f3c29-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="f3c29-219">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f3c29-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="f3c29-220">Ustawianie zasad pakowania kontenerów</span><span class="sxs-lookup"><span data-stu-id="f3c29-220">Set up container packing policies</span></span>

1. <span data-ttu-id="f3c29-221">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Zasady pakowania kontenera**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="f3c29-222">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-223">W nagłówku nowej zasady określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="f3c29-224">**Zasady pakowania kontenerów:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-225">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="f3c29-226">Na skróconej karcie **Omówienie** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-227">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-228">**Domyślna lokalizacja do sortowania:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="f3c29-229">**Jednostka wagi:** *kg*</span><span class="sxs-lookup"><span data-stu-id="f3c29-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="f3c29-230">**Zasada zamykania kontenera:** *Automatyczne zwalnianie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="f3c29-231">**Zasady zwalniania kontenerów:** *Przypisz kontener do pozycji sortowania towarów wyjściowych*</span><span class="sxs-lookup"><span data-stu-id="f3c29-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="f3c29-232">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="f3c29-233">Konfigurowanie profili pakowania</span><span class="sxs-lookup"><span data-stu-id="f3c29-233">Set up packing profiles</span></span>

<span data-ttu-id="f3c29-234">Utwórz nowy profil pakowania, który będzie używany razem z funkcją sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="f3c29-235">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="f3c29-236">W okienku akcji wybierz opcję **Nowy**, aby utworzyć linię, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-237">**Identyfikator profilu pakowania:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-238">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-239">**Zasady pakowania kontenerów:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-240">**Tryb identyfikatora kontenera:** *Automatyczny*</span><span class="sxs-lookup"><span data-stu-id="f3c29-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="f3c29-241">**Typ kontenera:** *Pudełko-duże*</span><span class="sxs-lookup"><span data-stu-id="f3c29-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="f3c29-242">**Automatycznie utwórz kontener przy zamknięciu kontenera:** Wyczyszczone (= *Nie*)</span><span class="sxs-lookup"><span data-stu-id="f3c29-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="f3c29-243">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="f3c29-244">Ustaw klasy pracy</span><span class="sxs-lookup"><span data-stu-id="f3c29-244">Set up work classes</span></span>

<span data-ttu-id="f3c29-245">Umożliwia skonfigurowanie klasy pracy, która będzie używana razem z sortowaniem.</span><span class="sxs-lookup"><span data-stu-id="f3c29-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="f3c29-246">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="f3c29-247">W okienku akcji wybierz opcję **Nowy**, aby utworzyć klasę pracy dla sortowania, i określ dla niej następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-248">**Identyfikator klasy roboczej:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-249">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-250">**Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*</span><span class="sxs-lookup"><span data-stu-id="f3c29-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="f3c29-251">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="f3c29-252">Konfigurowanie elementów menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="f3c29-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="f3c29-253">Konfigurowanie elementu menu nowej palety</span><span class="sxs-lookup"><span data-stu-id="f3c29-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="f3c29-254">Umożliwia utworzenie elementu menu urządzenia przenośnego w celu zbudowania palet podczas sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="f3c29-255">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="f3c29-256">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-257">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="f3c29-258">**Nazwa elementu menu:** *kompilacja palety*</span><span class="sxs-lookup"><span data-stu-id="f3c29-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="f3c29-259">**Tytuł:** *kompilacja palety*</span><span class="sxs-lookup"><span data-stu-id="f3c29-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="f3c29-260">**Tryb:** *Pośrednie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="f3c29-261">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="f3c29-262">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-263">**Kod działania:** *Sortowanie towarów wychodzących*</span><span class="sxs-lookup"><span data-stu-id="f3c29-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="f3c29-264">Jeśli to pole jest ustawione na wartość *Sortowanie towarów wychodzących*, wyświetlane jest pole **Identyfikator szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="f3c29-265">**Użyj przewodnika procesu:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f3c29-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="f3c29-266">Jeśli w polu **Kod działania** wybrano opcję *Sortowanie towarów wychodzących*, ta opcja jest automatycznie ustawiana na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="f3c29-267">**Identyfikator szablonu sortowania towarów wychodzących:** *Autopraca*</span><span class="sxs-lookup"><span data-stu-id="f3c29-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="f3c29-268">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="f3c29-269">Konfigurowanie elementu menu nowego ładowania</span><span class="sxs-lookup"><span data-stu-id="f3c29-269">Set up a new loading menu item</span></span>

<span data-ttu-id="f3c29-270">Następnie Utwórz element menu, który pozwoli użytkownikom przenieść posortowane towary magazynowe do lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f3c29-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="f3c29-271">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="f3c29-272">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-273">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="f3c29-274">**Nazwa elementu menu:** *ładowanie z sortowania*</span><span class="sxs-lookup"><span data-stu-id="f3c29-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="f3c29-275">**Tytuł:** *ładowanie z sortowania*</span><span class="sxs-lookup"><span data-stu-id="f3c29-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="f3c29-276">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="f3c29-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="f3c29-277">**Używanie istniejącej pracy:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f3c29-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="f3c29-278">Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Sterowane przez użytkownika*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="f3c29-279">Na skróconej karcie **Klasy pracy** wybierz opcję **Nowy**, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="f3c29-280">I **dentyfikator klasy pracy:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="f3c29-281">**Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*</span><span class="sxs-lookup"><span data-stu-id="f3c29-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="f3c29-282">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="f3c29-283">Konfigurowanie menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="f3c29-283">Set up the mobile device menu</span></span>

<span data-ttu-id="f3c29-284">Teraz musisz dodać nowe elementy menu do menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="f3c29-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="f3c29-285">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="f3c29-286">Wybierz menu **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="f3c29-287">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="f3c29-288">W kolumnie **Dostępne menu i elementy menu** znajdź i zaznacz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="f3c29-289">Wybierz strzałkę w prawo, aby przenieść **Kompilacja palety** do kolumny **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="f3c29-290">Za pomocą przycisków Strzałka w górę i Strzałka w dół można umieścić element menu **Kompiluj paletę** w wybranym miejscu w menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="f3c29-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="f3c29-291">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-291">Select **Save**.</span></span>
1. <span data-ttu-id="f3c29-292">Powtórz tę procedurę, aby dodać element menu **Ładowanie z sortowania** do menu **Towary wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="f3c29-293">Ustaw dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="f3c29-293">Set up location directives</span></span>

<span data-ttu-id="f3c29-294">*Dyrektywy lokalizacji* to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego.</span><span class="sxs-lookup"><span data-stu-id="f3c29-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="f3c29-295">Teraz musisz utworzyć regułę, aby zarządzać pracą sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="f3c29-296">Konfigurowanie pojedyńczej dyrektywy SKU</span><span class="sxs-lookup"><span data-stu-id="f3c29-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="f3c29-297">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="f3c29-298">W lewym okienku zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="f3c29-299">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-300">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="f3c29-301">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="f3c29-302">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="f3c29-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="f3c29-303">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-304">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="f3c29-305">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="f3c29-305">**Site:** *6*</span></span>
    - <span data-ttu-id="f3c29-306">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-307">**Wiele jednostek SKU:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="f3c29-308">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Wiersze** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="f3c29-309">Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="f3c29-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="f3c29-310">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="f3c29-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="f3c29-311">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="f3c29-312">**Od:** *0*</span><span class="sxs-lookup"><span data-stu-id="f3c29-312">**From:** *0*</span></span>
    - <span data-ttu-id="f3c29-313">**Do:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="f3c29-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="f3c29-314">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Dyrektywy akcji lokalizacji** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="f3c29-315">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="f3c29-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="f3c29-316">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="f3c29-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="f3c29-317">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="f3c29-318">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="f3c29-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="f3c29-319">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-319">Select **Save**.</span></span>
1. <span data-ttu-id="f3c29-320">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="f3c29-321">W edytorze zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="f3c29-322">Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="f3c29-323">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="f3c29-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="f3c29-324">Konfigurowanie wielu dyrektyw SKU</span><span class="sxs-lookup"><span data-stu-id="f3c29-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="f3c29-325">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="f3c29-326">W lewym okienku zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="f3c29-327">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-328">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="f3c29-329">**Sekwencja:** *2*</span><span class="sxs-lookup"><span data-stu-id="f3c29-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="f3c29-330">**Nazwa:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="f3c29-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="f3c29-331">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-332">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="f3c29-333">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="f3c29-333">**Site:** *6*</span></span>
    - <span data-ttu-id="f3c29-334">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-335">**Wiele SKU:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f3c29-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="f3c29-336">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Wiersze** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="f3c29-337">Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="f3c29-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="f3c29-338">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="f3c29-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="f3c29-339">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="f3c29-340">**Od:** *0*</span><span class="sxs-lookup"><span data-stu-id="f3c29-340">**From:** *0*</span></span>
    - <span data-ttu-id="f3c29-341">**Do:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="f3c29-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="f3c29-342">Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Dyrektywy akcji lokalizacji** stał się dostępny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="f3c29-343">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu:</span><span class="sxs-lookup"><span data-stu-id="f3c29-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="f3c29-344">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="f3c29-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="f3c29-345">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="f3c29-346">**Nazwa:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="f3c29-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="f3c29-347">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-347">Select **Save**.</span></span>
1. <span data-ttu-id="f3c29-348">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="f3c29-349">W edytorze zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="f3c29-350">Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="f3c29-351">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="f3c29-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="f3c29-352">Ustaw szablony pracy</span><span class="sxs-lookup"><span data-stu-id="f3c29-352">Set up work templates</span></span>

1. <span data-ttu-id="f3c29-353">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="f3c29-354">Zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="f3c29-355">W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.</span><span class="sxs-lookup"><span data-stu-id="f3c29-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="f3c29-356">Na karcie **Omówienie** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-357">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="f3c29-358">**Szablon pracy:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="f3c29-359">**Opis szablonu pracy:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="f3c29-360">Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="f3c29-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="f3c29-361">Na skróconej karcie **Szczegóły szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz, a następnie określ dla niego następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-362">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="f3c29-363">I **dentyfikator klasy pracy:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="f3c29-364">Wybierz znowu **Nowe** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="f3c29-365">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="f3c29-366">I **dentyfikator klasy pracy:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="f3c29-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="f3c29-367">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="f3c29-368">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="f3c29-368">Scenario</span></span>

<span data-ttu-id="f3c29-369">Ten scenariusz symuluje sytuację, w której spakowane kontenery powinny być automatycznie sortowane według różnych stanowisk (palet) po stanowisku pakowania, w zależności od usługi firmy przewozowej.</span><span class="sxs-lookup"><span data-stu-id="f3c29-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="f3c29-370">Po zapełnieniu wszystkich towarów z ładunku i posortowaniu ich według adresu paleta zostanie przeniesiona do bramy dokowej.</span><span class="sxs-lookup"><span data-stu-id="f3c29-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="f3c29-371">Tworzenie zlecenia pracy i pobierania zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="f3c29-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="f3c29-372">Utwórz zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="f3c29-372">Create sales order 1</span></span>

1. <span data-ttu-id="f3c29-373">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="f3c29-374">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-375">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="f3c29-376">**Konto odbiorcy:** *US-005*</span><span class="sxs-lookup"><span data-stu-id="f3c29-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="f3c29-377">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f3c29-378">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f3c29-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="f3c29-379">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="f3c29-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="f3c29-380">Przełącz do widoku **nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="f3c29-381">Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="f3c29-382">**Przewoźnik:** *Transport lotniczy*</span><span class="sxs-lookup"><span data-stu-id="f3c29-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="f3c29-383">**Usługa przewozowa:** *Lotnicza*</span><span class="sxs-lookup"><span data-stu-id="f3c29-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="f3c29-384">Przełącz się do widoku **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="f3c29-385">Jeśli nowy wiersz nie został dodany automatycznie do siatki na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać.</span><span class="sxs-lookup"><span data-stu-id="f3c29-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="f3c29-386">Dla nowego wiersza zamówienia należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="f3c29-387">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f3c29-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="f3c29-388">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="f3c29-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="f3c29-389">Gdy nowy wiersz zamówienia jest wciąż wybrany na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="f3c29-390">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="f3c29-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="f3c29-391">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="f3c29-392">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="f3c29-393">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f3c29-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="f3c29-394">Zanotuj identyfikator grupy czynności i numery identyfikacyjne przesyłki.</span><span class="sxs-lookup"><span data-stu-id="f3c29-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="f3c29-395">Zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="f3c29-395">Sales order 2</span></span>

1. <span data-ttu-id="f3c29-396">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="f3c29-397">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f3c29-398">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="f3c29-399">**Konto odbiorcy:** *US-006*</span><span class="sxs-lookup"><span data-stu-id="f3c29-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="f3c29-400">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f3c29-401">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f3c29-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="f3c29-402">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="f3c29-402">The new sales order is opened.</span></span> <span data-ttu-id="f3c29-403">Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="f3c29-404">Ustaw następujące wartości w tym wierszu zamówienia:</span><span class="sxs-lookup"><span data-stu-id="f3c29-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="f3c29-405">**Pozycja:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f3c29-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="f3c29-406">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="f3c29-407">Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy określić wartość w polu **Metoda dostawy** na *Flowe-STD*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="f3c29-408">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, a następnie określ następujące wartości w drugim wierszu:</span><span class="sxs-lookup"><span data-stu-id="f3c29-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="f3c29-409">**Pozycja:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f3c29-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="f3c29-410">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="f3c29-411">Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy zmienić wartość w polu **Metoda dostawy** na *Air C-Air*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="f3c29-412">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz pierwszy wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f3c29-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="f3c29-413">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="f3c29-414">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="f3c29-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="f3c29-415">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="f3c29-416">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz drugi wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f3c29-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="f3c29-417">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="f3c29-418">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="f3c29-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="f3c29-419">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="f3c29-420">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="f3c29-421">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f3c29-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="f3c29-422">Zwróć uwagę, że utworzono dwa numery identyfikacyjne grupy czynności i dwa numery identyfikacyjne przesyłki, po jednym dla każdego trybu dostawy dla wierszy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="f3c29-423">Pobierz identyfikatory pracy z szczegółów pracy</span><span class="sxs-lookup"><span data-stu-id="f3c29-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="f3c29-424">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="f3c29-425">Na stronie są wyświetlane identyfikatory pracy, które zostały utworzone na podstawie zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="f3c29-426">Identyfikatory grupy czynności i identyfikatory wysyłki można stosować w utworzonych zamówieniach sprzedaży w celu znalezienia identyfikatora pracy dla każdej grupy czynności i wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f3c29-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="f3c29-427">Zapisz identyfikatory pracy, ponieważ są one potrzebne w następnych krokach.</span><span class="sxs-lookup"><span data-stu-id="f3c29-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="f3c29-428">Zwróć uwagę, że utworzono dwa identyfikatory pracy dla drugiego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="f3c29-429">Jeśli różne towary są pobierane z różnych lokalizacji, generowane są oddzielne identyfikatory słowne.</span><span class="sxs-lookup"><span data-stu-id="f3c29-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="f3c29-430">Wybierz towary dla zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="f3c29-430">Pick items for the sales orders</span></span>

<span data-ttu-id="f3c29-431">Zakończ utworzoną pracę, korzystając z urządzenia przenośnego, aby przenieść elementy do stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="f3c29-432">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="f3c29-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="f3c29-433">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="f3c29-434">W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="f3c29-435">W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="f3c29-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="f3c29-436">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-436">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-437">Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny, który został utworzony dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="f3c29-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="f3c29-438">Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-001*), pozycja (*A0001*) oraz ilość (*2 sztuki*).</span><span class="sxs-lookup"><span data-stu-id="f3c29-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="f3c29-439">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-439">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-440">Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="f3c29-441">Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="f3c29-442">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-442">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-443">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”, który wskazuje, że identyfikator pracy z zamówienia sprzedaży 1 został zakończony.</span><span class="sxs-lookup"><span data-stu-id="f3c29-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="f3c29-444">Teraz zostanie pobrane zamówienie sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="f3c29-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="f3c29-445">W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 2, gdzie wiersz 1 ma element *A0001*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="f3c29-446">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-446">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-447">Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="f3c29-448">Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-001*), pozycja (*A0001*) oraz ilość (*1 sztuki*).</span><span class="sxs-lookup"><span data-stu-id="f3c29-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="f3c29-449">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-449">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-450">Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="f3c29-451">Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="f3c29-452">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-452">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-453">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="f3c29-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="f3c29-454">Ten komunikat wskazuje, że wykonano identyfikator pracy z wiersza 1 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="f3c29-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="f3c29-455">W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 2, gdzie wiersz 2 ma element *A0002*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="f3c29-456">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-456">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-457">Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="f3c29-458">Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-002*), pozycja (*A0001*) oraz ilość (*1 sztuki*).</span><span class="sxs-lookup"><span data-stu-id="f3c29-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="f3c29-459">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-459">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-460">Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="f3c29-461">Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="f3c29-462">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-462">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-463">Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="f3c29-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="f3c29-464">Ten komunikat wskazuje, że wykonano identyfikator pracy z wiersza 2 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="f3c29-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="f3c29-465">Pakowanie zamówień sprzedaży do kontenerów</span><span class="sxs-lookup"><span data-stu-id="f3c29-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="f3c29-466">Pakowanie zamówienia 1 sprzedaży do kontenerów</span><span class="sxs-lookup"><span data-stu-id="f3c29-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="f3c29-467">Przejdź do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Pakunek**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="f3c29-468">Wyświetli się okno dialogowe **Wybierz stację pakowania**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="f3c29-469">Domyślnie pole **Pracownik** powinno mieć ustawioną nazwę pracownika skonfigurowanego wcześniej.</span><span class="sxs-lookup"><span data-stu-id="f3c29-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="f3c29-470">Poniższe wartości umożliwiają wyświetlanie i pracę z wysyłkami i kontenerami planowanymi w określonej lokalizacji pakowania:</span><span class="sxs-lookup"><span data-stu-id="f3c29-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="f3c29-471">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="f3c29-471">**Site:** *6*</span></span>
    - <span data-ttu-id="f3c29-472">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f3c29-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f3c29-473">**Lokalizacja:** *Pakiet*</span><span class="sxs-lookup"><span data-stu-id="f3c29-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="f3c29-474">**Identyfikator profilu pakowania:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="f3c29-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="f3c29-475">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f3c29-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="f3c29-476">Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="f3c29-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="f3c29-477">Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.</span><span class="sxs-lookup"><span data-stu-id="f3c29-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="f3c29-478">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="f3c29-479">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="f3c29-480">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3c29-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="f3c29-481">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-482">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="f3c29-483">**Identyfikator:** pozycja *A0001*</span><span class="sxs-lookup"><span data-stu-id="f3c29-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="f3c29-484">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="f3c29-485">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="f3c29-486">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-486">Select **OK**.</span></span> <span data-ttu-id="f3c29-487">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="f3c29-488">Utwórz drugi kontener, aby dodać drugi towar z numeru identyfikacyjnego dla zamówienia sprzedaży 1 do nowego kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3c29-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="f3c29-489">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="f3c29-490">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="f3c29-491">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3c29-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="f3c29-492">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-493">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="f3c29-494">**Identyfikator:** pozycja *A0001*</span><span class="sxs-lookup"><span data-stu-id="f3c29-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="f3c29-495">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="f3c29-496">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="f3c29-497">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-497">Select **OK**.</span></span> <span data-ttu-id="f3c29-498">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="f3c29-499">Pakowanie zamówienia 2 sprzedaży do kontenerów</span><span class="sxs-lookup"><span data-stu-id="f3c29-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="f3c29-500">Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla wiersza 1 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="f3c29-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="f3c29-501">Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.</span><span class="sxs-lookup"><span data-stu-id="f3c29-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="f3c29-502">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="f3c29-503">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="f3c29-504">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3c29-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="f3c29-505">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-506">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="f3c29-507">**Identyfikator:** pozycja *A0001*</span><span class="sxs-lookup"><span data-stu-id="f3c29-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="f3c29-508">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="f3c29-509">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="f3c29-510">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-510">Select **OK**.</span></span> <span data-ttu-id="f3c29-511">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="f3c29-512">Wpolu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla wiersza 2 zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="f3c29-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="f3c29-513">Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.</span><span class="sxs-lookup"><span data-stu-id="f3c29-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="f3c29-514">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="f3c29-515">Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="f3c29-516">Zanotuj identyfikator kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3c29-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="f3c29-517">Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f3c29-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f3c29-518">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f3c29-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="f3c29-519">**Pole identyfikatora:** pozycja *A0002*</span><span class="sxs-lookup"><span data-stu-id="f3c29-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="f3c29-520">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="f3c29-521">W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="f3c29-522">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-522">Select **OK**.</span></span> <span data-ttu-id="f3c29-523">Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="f3c29-524">Aby wyświetlić szczegóły kontenera, należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Kontenery** oraz wyszukać identyfikatory kontenerów, które zostały utworzone podczas pakowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="f3c29-525">Sortowanie kontenerów</span><span class="sxs-lookup"><span data-stu-id="f3c29-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3c29-526">Po dostępie do elementu menu **Kompilacja palety** w aplikacji mobilnej do sortowania wychodzącego wyświetlany jest przycisk z etykietą **Pełna**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="f3c29-527">*Nie używaj przycisku **Pełne** do sortowania lub zamykania stanowiska.*</span><span class="sxs-lookup"><span data-stu-id="f3c29-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="f3c29-528">Przycisk **Pełny** jest domyślnie dostępny i nie można go wyłączyć ani usunąć ze strony.</span><span class="sxs-lookup"><span data-stu-id="f3c29-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="f3c29-529">Nie jest używany dla funkcji *Sortowanie towarów wychodzących*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="f3c29-530">Sortuj pierwszy kontener</span><span class="sxs-lookup"><span data-stu-id="f3c29-530">Sort the first container</span></span>

1. <span data-ttu-id="f3c29-531">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="f3c29-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="f3c29-532">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="f3c29-533">W menu **Wychodzące** wybierz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="f3c29-534">W polu **LP/Con** wprowadź pierwszy identyfikator kontenera skojarzony z zamówieniem sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="f3c29-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="f3c29-535">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-535">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-536">Ponieważ nie istnieją obecnie pozycje sortowania, należy je określić.</span><span class="sxs-lookup"><span data-stu-id="f3c29-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="f3c29-537">W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="f3c29-538">Ponieważ żaden numer identyfikacyjny nie jest aktualnie skojarzony z pozycją sortowania *SP01*, należy określić jeden z nich.</span><span class="sxs-lookup"><span data-stu-id="f3c29-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="f3c29-539">W polu **Numer identyfikacyjny** wprowadź *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="f3c29-540">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-540">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-541">Ponieważ sprawdzanie poprawności pozycji sortowania jest włączone, należy ponownie wprowadzić identyfikator pozycji sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="f3c29-542">W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="f3c29-543">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-543">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-544">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="f3c29-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="f3c29-545">Aby wyświetlić pozycję sortowania i numer identyfikacyjny w tym celu należy przejść do pola pakowanie w **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="f3c29-546">Na stronie **Przypisania stanowisk sortowania towarów wychodzących** wyświetlane są wszystkie stanowiska, które są obecnie aktywne.</span><span class="sxs-lookup"><span data-stu-id="f3c29-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="f3c29-547">W polu **Transakcja na stanowisku sortowania** wyświetlany jest numer numer identyfikacyjny skojarzony z poszczególnymi pozycjami sortowania oraz kontenery znajdujące się na położeniu sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="f3c29-548">Zauważ, że jedna pozycja sortowania już istnieje, a skrócona karta **Kryteria stanowiska sortowania** przedstawia kryterium **Wysyłka - usługa przewoźnika - powietrze**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="f3c29-549">Posortuj pozostałe pojemniki</span><span class="sxs-lookup"><span data-stu-id="f3c29-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="f3c29-550">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="f3c29-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="f3c29-551">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="f3c29-552">W menu **Wychodzące** wybierz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="f3c29-553">W polu **LP/Con** wprowadź drugi identyfikator kontenera skojarzony z zamówieniem sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="f3c29-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="f3c29-554">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-554">Select **OK**.</span></span> <span data-ttu-id="f3c29-555">Ponieważ szablon sortowania jest skonfigurowany do automatycznego sortowania, a pozycja sortowania, która ma kryteria dopasowywania, już istnieje, jest automatycznie kierowana do właściwej pozycji sortowania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="f3c29-556">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-556">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-557">Potwierdź identyfikator stanowiska sortowania, aby wskazać, że ilość zapasów znajduje się w odpowiednim miejscu.</span><span class="sxs-lookup"><span data-stu-id="f3c29-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="f3c29-558">W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="f3c29-559">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-559">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-560">Praca została zakończona dla drugiego kontenera z zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="f3c29-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="f3c29-561">Teraz zostaną posortowane pozostałe kontenery z zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="f3c29-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="f3c29-562">W polu **LP/Con** wprowadź identyfikator kontenera z zamówienia sprzedaży 2, który zawiera pozycję *A0001*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="f3c29-563">Ponieważ usługa przewoźnika jest inna, system wyświetli monit o wprowadzenie nowej pozycji sortowania i przypisanie do tego stanowiska obiektu numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="f3c29-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="f3c29-564">Należy skorzystać z pozycji sortowania *SP02* i numer identyfikacyjny *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="f3c29-565">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-565">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-566">Potwierdź pozycję sortowania, wprowadzając *SP02* w polu **Identyfikator pozycji sortowania**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="f3c29-567">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-567">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-568">Praca w kontenerze została zakończona.</span><span class="sxs-lookup"><span data-stu-id="f3c29-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="f3c29-569">W polu **LP/Con** wprowadź identyfikator ostatniego kontenera z zamówienia sprzedaży 2, który zawiera pozycję *A0002*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="f3c29-570">Ponieważ usługa przewoźnika jest taka sama jak usługa przewoźnika dla zamówienia sprzedaży 1, system pokazuje istniejącą pozycję sortowania, która ma kryteria dopasowywania.</span><span class="sxs-lookup"><span data-stu-id="f3c29-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="f3c29-571">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-571">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-572">Potwierdź pozycję sortowania, wprowadzając *SP01* w polu **Identyfikator pozycji sortowania**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="f3c29-573">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-573">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-574">Praca w kontenerze została zakończona.</span><span class="sxs-lookup"><span data-stu-id="f3c29-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="f3c29-575">Zamknij wychodzące pozycje sortowania</span><span class="sxs-lookup"><span data-stu-id="f3c29-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="f3c29-576">Po posortowaniu wszystkich zapasów należy zamknąć to stanowisko, aby można było utworzyć pracę.</span><span class="sxs-lookup"><span data-stu-id="f3c29-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="f3c29-577">Zostaną utworzone posortowane prace związane z pobieraniem zapasów, aby przenieść je do bramy dokowej.</span><span class="sxs-lookup"><span data-stu-id="f3c29-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="f3c29-578">Zamykanie stanowiska z urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="f3c29-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="f3c29-579">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="f3c29-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="f3c29-580">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="f3c29-581">W menu **Wychodzące** wybierz opcję **Kompilacja palety**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="f3c29-582">W polu **LP/Con** wprowadź identyfikator kontenera, który został posortowany w celu posortowania pozycji *SP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="f3c29-583">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-583">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-584">Pojawi się następujący komunikat: „Kontener jest już posortowany do stanowiska SP01.</span><span class="sxs-lookup"><span data-stu-id="f3c29-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="f3c29-585">Zamknąć to stanowisko?”</span><span class="sxs-lookup"><span data-stu-id="f3c29-585">Close the position?"</span></span> <span data-ttu-id="f3c29-586">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-586">Select **Close**.</span></span>

    <span data-ttu-id="f3c29-587">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="f3c29-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="f3c29-588">Zamykanie stanowiska z przypisań pozycji sortowania wychodzącego</span><span class="sxs-lookup"><span data-stu-id="f3c29-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="f3c29-589">Należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="f3c29-590">W lewej kolumnie wybierz **SP02**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="f3c29-591">Ten wiersz określający pozycję sortowania dla zapasów wychodzących jest tym, który zostanie zamknięty.</span><span class="sxs-lookup"><span data-stu-id="f3c29-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="f3c29-592">W okienku akcji wybierz opcję **Zamknij stanowisko**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="f3c29-593">Rekord stanowiska sortowania jest zamknięty i nie jest już wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="f3c29-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="f3c29-594">Aby wyświetlić wszystkie rekordy zamkniętych stanowisk, zaznacz pole wyboru **Wyświetl zamknięte**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="f3c29-595">Pobranie z posortowanych zapasów</span><span class="sxs-lookup"><span data-stu-id="f3c29-595">Sorted inventory picking</span></span>

<span data-ttu-id="f3c29-596">Należy wykonać posortowaną pracę pobrania z magazynu.</span><span class="sxs-lookup"><span data-stu-id="f3c29-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="f3c29-597">Po zakończeniu Inwentaryzacja zostanie pobrana do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3c29-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="f3c29-598">W tym momencie obowiązują wszystkie inne procesy magazynowe.</span><span class="sxs-lookup"><span data-stu-id="f3c29-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="f3c29-599">Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).</span><span class="sxs-lookup"><span data-stu-id="f3c29-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="f3c29-600">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="f3c29-601">W menu **Wychodzące** wybierz opcję **Ładowanie z sortowania**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="f3c29-602">Wprowadź identyfikator docelowego z pierwszej pozycji sortowania, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="f3c29-603">Ustaw wartość w polu **Identyfikator** na *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="f3c29-604">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-604">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-605">Strona **Odbieranie sortowanych zapasów: Odbiór** zawiera listę prac pobrań, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="f3c29-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="f3c29-606">Pobranie z lokalizacji *SORTOWANIE* i docelowego numeru identyfikacyjnego *PLP01*, który ma wiele towarów i ilość *3*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="f3c29-607">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-607">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-608">Strona **Odbieranie sortowanych zapasów: Odłożenie** zawiera listę prac odkładania, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="f3c29-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="f3c29-609">Odkładanie z lokalizacji *Baydoor* i docelowego numeru identyfikacyjnego *PLP01*, który ma wiele towarów i ilość *3*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="f3c29-610">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-610">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-611">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="f3c29-611">Work is completed.</span></span>

1. <span data-ttu-id="f3c29-612">Wprowadź docelowy numer identyfikacyjny z drugie pozycji sortowania, *SP02*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="f3c29-613">Ustaw wartość w polu **Identyfikator** na *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="f3c29-614">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-614">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-615">Strona **Odbieranie sortowanych zapasów: Odbiór** zawiera listę prac pobrań, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="f3c29-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="f3c29-616">Pobranie z lokalizacji *SORTOWANIE* i docelowego numeru identyfikacyjnego *PLP02*, który ma wiele towarów i ilość *1*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="f3c29-617">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-617">Select **OK**.</span></span>
1. <span data-ttu-id="f3c29-618">Strona **Odbieranie sortowanych zapasów: Odłożenie** zawiera listę prac odkładania, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="f3c29-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="f3c29-619">Odkładanie z lokalizacji *Baydoor* i docelowego numeru identyfikacyjnego *PLP02*, który ma wiele towarów i ilość *1*.</span><span class="sxs-lookup"><span data-stu-id="f3c29-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="f3c29-620">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c29-620">Select **OK**.</span></span>

    <span data-ttu-id="f3c29-621">Praca została zakończona.</span><span class="sxs-lookup"><span data-stu-id="f3c29-621">Work is completed.</span></span>

<span data-ttu-id="f3c29-622">Od tego momentu obowiązują wszystkie inne procesy magazynowe.</span><span class="sxs-lookup"><span data-stu-id="f3c29-622">From this point forward, all other warehouse processes apply.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]