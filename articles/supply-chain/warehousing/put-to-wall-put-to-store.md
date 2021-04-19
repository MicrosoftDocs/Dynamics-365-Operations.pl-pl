---
title: Umieść na ścianie - odłożenie do sklepu
description: Ten temat zawiera informacje o funkcji Umieść na ścianie - odłóż do sklepu. Ta funkcja umożliwia obsługę scenariuszy, w których trzeba skonsolidować produkt do obszaru tymczasowego na podstawie kryteriów konfigurowalnych. Umożliwia skrócenie czasu pobrania, ponieważ umożliwia pobranie go do jednego docelowego numeru identyfikacyjnego i może spowodować użycie większej liczby stanowisk niż pobranie w klastrze.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cf34a61d0b3f784b5a424473588d05bf8703635c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823294"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="b0c74-105">Umieść na ścianie - odłożenie do sklepu</span><span class="sxs-lookup"><span data-stu-id="b0c74-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0c74-106">Funkcja *Umieść na ścianie - odłożenie do sklepu* umożliwia obsługę scenariuszy, w których trzeba skonsolidować produkt do obszaru tymczasowego na podstawie kryteriów konfigurowalnych.</span><span class="sxs-lookup"><span data-stu-id="b0c74-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="b0c74-107">Ponieważ ta funkcja umożliwia pobranie do jednego docelowego numeru identyfikacyjnego i może korzystać z większej liczby stanowisk niż pobieranie w klastrze, firmy, które mają być przeznaczone do przechowywania lub obsługi małych towarów, będą korzystać ze zmniejszonego czasu pobierania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="b0c74-108">Przepływ pracy dla tej funkcji umożliwia kierowanie pobranego produktu do lokalizacji sortowania w różnych typach kontenerów.</span><span class="sxs-lookup"><span data-stu-id="b0c74-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="b0c74-109">Na ogół każda lokalizacja sortowania zawiera wiele stanowisk sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="b0c74-110">Każda pozycja sortowania jest przypisywana zgodnie z kryteriami określonymi przez proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="b0c74-111">Typowymi kryteriami są ostateczne miejsce docelowe, wysyłka lub obciążenie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="b0c74-112">Po dostarczeniu produktu jest on dystrybuowany do każdego stanowiska sortowania na podstawie ilości skojarzonej z zamówieniem, miejscem docelowym, wysyłką lub obciążeniem.</span><span class="sxs-lookup"><span data-stu-id="b0c74-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="b0c74-113">Gdy kontener jest pełny lub kompletny, jest on przenoszony do lokalizacji przemieszczania lub do lokalizacji wysyłki w celu dalszej obsługi, w zależności od procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="b0c74-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="b0c74-114">Ta funkcja magazynowania jest również nazywana innymi nazwami, takimi jak otwarcie funkcji odłożenie-lekkie i przerwanie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="b0c74-115">Włącz funkcję sortowania wychodzącego</span><span class="sxs-lookup"><span data-stu-id="b0c74-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="b0c74-116">Zanim będzie możliwe użycie funkcji przekazanie *Umieść na ścianie - odłożenie do sklepu*, funkcja *Sortowanie towarów wychodzących* musi być włączona w systemie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="b0c74-117">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="b0c74-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b0c74-118">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="b0c74-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b0c74-119">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="b0c74-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b0c74-120">**Nazwa funkcji:** *Sortowanie wychodzące*</span><span class="sxs-lookup"><span data-stu-id="b0c74-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="b0c74-121">Funkcja *Sortowanie towarów wychodzących* może być używana w połączeniu z funkcją *Kod kroku grupy czynności dotyczący całej organizacji:*, jeśli jest włączona.</span><span class="sxs-lookup"><span data-stu-id="b0c74-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="b0c74-122">Należy również włączyć tę funkcję, jeśli będą używane wstępnie zdefiniowane kody skonfigurowane w kodach kroków grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="b0c74-123">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="b0c74-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="b0c74-124">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="b0c74-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b0c74-125">**Nazwa funkcji:** *Kod kroku grupy czynności dotyczący całej organizacji*</span><span class="sxs-lookup"><span data-stu-id="b0c74-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="b0c74-126">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="b0c74-126">Setup</span></span>

<span data-ttu-id="b0c74-127">W przypadku tego pokazu używane są standardowe dane firmy Contoso i magazyn *62*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="b0c74-128">Używane są również niektóre dodatki, które zostały przedstawione później.</span><span class="sxs-lookup"><span data-stu-id="b0c74-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="b0c74-129">Typ lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b0c74-129">Location type</span></span>

1. <span data-ttu-id="b0c74-130">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Typy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="b0c74-131">W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ lokalizacji służący do sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="b0c74-132">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-132">Set the following values:</span></span>

    - <span data-ttu-id="b0c74-133">**Typ lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="b0c74-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="b0c74-134">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="b0c74-135">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="b0c74-136">Parametry zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="b0c74-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="b0c74-137">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="b0c74-138">Na karcie **Ogólne**, na skróconej karcie **Typy lokalizacji** w polu **Typ lokalizacji sortowania** wpisz *Sortowanie*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="b0c74-139">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="b0c74-140">Profil lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b0c74-140">Location profile</span></span>

1. <span data-ttu-id="b0c74-141">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="b0c74-142">W okienku akcji wybierz opcję **Nowy**, aby utworzyć profil lokalizacji dla lokalizacji sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="b0c74-143">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="b0c74-144">**Identyfikator profilu lokalizacji:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-145">**Nazwa:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="b0c74-146">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="b0c74-147">**Format lokalizacji:** *PACK*</span><span class="sxs-lookup"><span data-stu-id="b0c74-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="b0c74-148">**Typ lokalizacji:** *SORTOWANIE*</span><span class="sxs-lookup"><span data-stu-id="b0c74-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="b0c74-149">**Używaj śledzenia numeru identyfikacyjnego:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b0c74-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="b0c74-150">**Pozwól na mieszane pozycje:** *Yes*</span><span class="sxs-lookup"><span data-stu-id="b0c74-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="b0c74-151">**Zezwalaj na mieszane stany zapasów:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b0c74-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="b0c74-152">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="b0c74-153">Lokalizacje</span><span class="sxs-lookup"><span data-stu-id="b0c74-153">Locations</span></span>

1. <span data-ttu-id="b0c74-154">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="b0c74-155">Wyczyść pole wyboru **Generuj cyfry kontroli dla lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="b0c74-156">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-156">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b0c74-157">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="b0c74-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="b0c74-158">**Lokalizacja:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-159">**Identyfikator profilu lokalizacji:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="b0c74-160">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="b0c74-161">Profile pakowania</span><span class="sxs-lookup"><span data-stu-id="b0c74-161">Packing profiles</span></span>

1. <span data-ttu-id="b0c74-162">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="b0c74-163">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-163">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b0c74-164">**Identyfikator profilu pakowania:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-165">**Opis:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-166">**Zasady pakowania kontenerów:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="b0c74-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="b0c74-167">**Tryb identyfikatora kontenera:** *Automatyczny*</span><span class="sxs-lookup"><span data-stu-id="b0c74-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="b0c74-168">**Typ kontenera:** *PALETA 48X48*</span><span class="sxs-lookup"><span data-stu-id="b0c74-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="b0c74-169">**Utwórz automatycznie kontener przy zamknięciu kontenera:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="b0c74-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="b0c74-170">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="b0c74-171">Kody kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="b0c74-171">Wave step codes</span></span>

<span data-ttu-id="b0c74-172">Po włączeniu funkcji *Kod kroku grupy czynności dotyczący całej organizacji* należy skonfigurować poniższy kod.</span><span class="sxs-lookup"><span data-stu-id="b0c74-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="b0c74-173">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody kroku grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="b0c74-174">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-174">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b0c74-175">**Kod kroku grupy czynności:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-176">**Opis kroku grupy czynności:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-177">**Typ kroku grupy czynności:** *Szablon sortowania*</span><span class="sxs-lookup"><span data-stu-id="b0c74-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="b0c74-178">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="b0c74-179">Szablon sortowania towarów wychodzących</span><span class="sxs-lookup"><span data-stu-id="b0c74-179">Outbound sorting template</span></span>

<span data-ttu-id="b0c74-180">Szablon sortowania określa, czy są tworzone pozycje sortowania, używane kryteria oraz inne atrybuty procesu sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="b0c74-181">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Pakowanie \> Szablon sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="b0c74-182">W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="b0c74-183">W nagłówku nowego szablonu określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="b0c74-184">**Identyfikator szablonu sortowania towarów wychodzących:** *Sortowanie grupy czynności*</span><span class="sxs-lookup"><span data-stu-id="b0c74-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="b0c74-185">**Opis:** *Sortowanie grupy czynności*</span><span class="sxs-lookup"><span data-stu-id="b0c74-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="b0c74-186">**Typ szablonu sortowania:** *Popyt grupy czynności*</span><span class="sxs-lookup"><span data-stu-id="b0c74-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="b0c74-187">To pole definiuje proces, dla którego jest używany szablon sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="b0c74-188">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-188">The following values are available:</span></span>

        - <span data-ttu-id="b0c74-189">**Popyt grupy czynności** — szablon sortowania jest używany w procesie *Odkładania do ściany*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="b0c74-190">Ten typ szablonu służy do ominięcia stacji pakowania i przetwarzania zapasów bezpośrednio poza falą.</span><span class="sxs-lookup"><span data-stu-id="b0c74-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="b0c74-191">Można użyć tego typu, tylko jeśli metoda przetwarzania grupy czynności typu **sortowanie** jest uwzględniona w szablonie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="b0c74-192">**Kontener** — szablon sortowania jest używany do procesu *kompilacji palet po pakowaniu*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="b0c74-193">Ten typ szablonu jest używany do przetwarzania kontenerów, które są zamknięte na stacji pakowania i muszą być sortowane na paletach.</span><span class="sxs-lookup"><span data-stu-id="b0c74-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="b0c74-194">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="b0c74-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="b0c74-195">**Lokalizacja:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="b0c74-196">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="b0c74-197">**Typ weryfikacji sortowania:** *Skan pozycji*</span><span class="sxs-lookup"><span data-stu-id="b0c74-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="b0c74-198">To pole określa weryfikację wymaganą podczas sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="b0c74-199">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-199">The following values are available:</span></span>

        - <span data-ttu-id="b0c74-200">None</span><span class="sxs-lookup"><span data-stu-id="b0c74-200">None</span></span>
        - <span data-ttu-id="b0c74-201">Skan numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="b0c74-201">License plate scan</span></span>
        - <span data-ttu-id="b0c74-202">Skan stanowiska</span><span class="sxs-lookup"><span data-stu-id="b0c74-202">Position scan</span></span>

    - <span data-ttu-id="b0c74-203">**Utwórz pracę przy zamknięciu stanowiska:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b0c74-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="b0c74-204">Jeśli opcja jest ustawiona na *Tak*, po zamknięciu stanowiska zostanie utworzona praca, aby przenieść zapasy do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-204">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="b0c74-205">Jeśli opcja jest ustawiona na *Nie*, zapasy będą natychmiast pobierane dla zamówienia w momencie zamknięcia stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-205">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="b0c74-206">**Przypisanie stanowiska:** *Manual*</span><span class="sxs-lookup"><span data-stu-id="b0c74-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="b0c74-207">To pole określa typ przypisania stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="b0c74-208">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-208">The following values are available:</span></span>

        - <span data-ttu-id="b0c74-209">**Ręczne** – Użytkownik musi zawsze wskazać, do którego stanowiska należy sortować zapasy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="b0c74-210">**Automatycznie** – System w miarę możliwości automatycznie poprowadzi zapasy do stanowiska na podstawie podziałów w szablonie sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="b0c74-211">**Przypisz kryteria stanowiska sortowania:** *Używaj tylko pustego stanowiska*</span><span class="sxs-lookup"><span data-stu-id="b0c74-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="b0c74-212">To pole kontroluje, czy zapasy, które są już obecne na stanowiskach sortowania, są brane pod uwagę podczas przypisywania stanowiska do zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="b0c74-213">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-213">The following values are available:</span></span>

        - <span data-ttu-id="b0c74-214">**Używaj tylko pustego stanowiska** — Uwzględnione zostaną stanowiska, które mają już skojarzone z nimi zapasy</span><span class="sxs-lookup"><span data-stu-id="b0c74-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="b0c74-215">**Przyjmij puste stanowisko** — Wszystkie zapasy znajdujące się już w danym stanowisku zostaną zignorowane podczas przypisywania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="b0c74-216">Zostaną użyte wszystkie dostępne stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-216">All available positions will be used.</span></span>

    - <span data-ttu-id="b0c74-217">**Kod kroku grupy czynności:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="b0c74-218">Jeśli jest włączona funkcja *Kod kroku grupy czynności dotyczący całej organizacji*, kod etapu grupy czynności do *Sortowania* musi być również ustawiony w kodach kroków grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="b0c74-219">**Automatycznie zamknij stanowisko sortowania:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b0c74-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="b0c74-220">Jeśli ta opcja jest ustawiona na *Tak*, stanowisko sortowania zostanie automatycznie zamknięte po zakończeniu całej pracy wchodzącej do jej stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-220">If this option is set to *Yes*, the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="b0c74-221">**Liczba stanowisk sortowania:** *3*</span><span class="sxs-lookup"><span data-stu-id="b0c74-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="b0c74-222">W tym polu jest określana maksymalna liczba stanowisk sortowania tworzonych przez system.</span><span class="sxs-lookup"><span data-stu-id="b0c74-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="b0c74-223">**Prefiks stanowiska sortowania:** *SP-*</span><span class="sxs-lookup"><span data-stu-id="b0c74-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="b0c74-224">To pole definiuje prefiks, który system przypisuje przed numerem stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="b0c74-225">**Automatycznie pakuj stanowisko sortowania:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b0c74-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="b0c74-226">Jeśli ta opcja jest ustawiona na *Tak*, zapasy w pozycji sortowania będą pakowane do kontenera po zamknięciu stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-226">If this option is set to *Yes*, the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="b0c74-227">**Identyfikator profilu pakowania:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="b0c74-228">To pole definiuje profil pakowania, który będzie używany, gdy stanowisko sortowania jest pakowane do kontenera.</span><span class="sxs-lookup"><span data-stu-id="b0c74-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="b0c74-229">W okienku akcji wybierz opcję **Edytuj kwerendę**, aby określić kryteria używane dla tego szablonu sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="b0c74-230">W oknie dialogowym kwerenda, na karcie **Sortowanie** wybierz opcję **Nowy**, aby dodać wiersz, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="b0c74-231">**Tabela:** *Szczegóły ładunku*</span><span class="sxs-lookup"><span data-stu-id="b0c74-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="b0c74-232">**Tabela pochodna:** *Szczegóły ładunku*</span><span class="sxs-lookup"><span data-stu-id="b0c74-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="b0c74-233">**Pole:** *Identyfikator wysyłki*</span><span class="sxs-lookup"><span data-stu-id="b0c74-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="b0c74-234">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="b0c74-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="b0c74-235">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-235">Select **OK**.</span></span>
1. <span data-ttu-id="b0c74-236">Może zostać wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="b0c74-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="b0c74-237">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-237">Select **Yes**.</span></span>

    <span data-ttu-id="b0c74-238">W okienku akcji zostanie udostępniony przycisk **Podziały szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="b0c74-239">W okienku akcji wybierz pozycję **Podziały szablonu sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="b0c74-240">Wybierz **Grupuj według pola**, aby pogrupować wysyłki według identyfikatora wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="b0c74-241">To ustawienie spowoduje utworzenie jednego stanowiska sortowania na przesyłkę będącą kontenerem w grupie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="b0c74-242">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="b0c74-243">Metody przetwarzania grupy czynności</span><span class="sxs-lookup"><span data-stu-id="b0c74-243">Wave process methods</span></span>

1. <span data-ttu-id="b0c74-244">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="b0c74-245">W okienku akcji wybierz pozycję **Ponownie utwórz metody**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="b0c74-246">Metoda **sortowania** jest dodawana do listy dostępnych metod, a dla niego wybrano typ szablonu grupy czynności *Wysyłki*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="b0c74-247">Szablony grupy czynności</span><span class="sxs-lookup"><span data-stu-id="b0c74-247">Wave templates</span></span>

<span data-ttu-id="b0c74-248">Edytuj szablon grupy czynności używany do popytu sortowania na grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="b0c74-249">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="b0c74-250">W **Typ szablonu grupy czynności** wybierz *Wysyłka*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="b0c74-251">Umożliwia wybór istniejącego szablonu **Domyślna wysyłka 62**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="b0c74-252">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="b0c74-253">Na skróconej karcie **Ogólne** wprowadź następujące zmiany:</span><span class="sxs-lookup"><span data-stu-id="b0c74-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="b0c74-254">Ustaw opcję **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** na wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="b0c74-255">Ustaw opcję **Przypisz do otwartych grup czynności** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="b0c74-256">Na skróconej karcie **Metody** należy ustawić metodę **sortowania**:</span><span class="sxs-lookup"><span data-stu-id="b0c74-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="b0c74-257">W siatce **Pozostałe metody** wybierz opcję **Sortowanie**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="b0c74-258">Korzystaj z przycisku Strzałka w prawo, aby przesunąć **sortowanie** na siatkę **Wybrane metody**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="b0c74-259">W siatce **Wybrane metody** wybierz opcję **Sortowanie**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="b0c74-260">W polu **Kod kroku grupy czynności** należy ustawić *Sortowanie*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="b0c74-261">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="b0c74-262">Elementy menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="b0c74-262">Mobile device menu items</span></span>

1. <span data-ttu-id="b0c74-263">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="b0c74-264">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0c74-265">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="b0c74-266">**Nazwa elementu menu:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-267">**Tytuł:** *Sortowanie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="b0c74-268">**Tryb:** *Pośrednie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="b0c74-269">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="b0c74-270">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="b0c74-271">**Kod działania:** *Sortowanie towarów wychodzących*</span><span class="sxs-lookup"><span data-stu-id="b0c74-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="b0c74-272">**Skorzystaj z przewodnika procesu:** *Tak* (wartość domyślna)</span><span class="sxs-lookup"><span data-stu-id="b0c74-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="b0c74-273">**Identyfikator szablonu sortowania towarów wychodzących:** *Sortowanie grupy czynności*</span><span class="sxs-lookup"><span data-stu-id="b0c74-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="b0c74-274">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="b0c74-275">Menu urządzeń przenośnych</span><span class="sxs-lookup"><span data-stu-id="b0c74-275">Mobile device menu</span></span>

1. <span data-ttu-id="b0c74-276">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="b0c74-277">Z listy menu wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="b0c74-278">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="b0c74-279">W siatce **Dostępne menu i elementy menu** znajdź i wybierz element menu **Sortowanie**, który został właśnie utworzony.</span><span class="sxs-lookup"><span data-stu-id="b0c74-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="b0c74-280">Wybierz strzałkę w prawo, aby przenieść **Sortowanie** do siatki **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="b0c74-281">W ten sposób dodasz nowy element menu do menu **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="b0c74-282">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="b0c74-283">Dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b0c74-283">Location directives</span></span>

<span data-ttu-id="b0c74-284">Należy utworzyć dyrektywy lokalizacji, które będą kierować pracą utworzoną po zakończeniu sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="b0c74-285">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b0c74-286">W polu **Typ zlecenia pracy** zaznacz opcję *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="b0c74-287">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0c74-288">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="b0c74-289">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0c74-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="b0c74-290">**Nazwa:** *Odłóż do bramy dokowej*</span><span class="sxs-lookup"><span data-stu-id="b0c74-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="b0c74-291">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="b0c74-292">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b0c74-293">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="b0c74-293">**Site:** *6*</span></span>
    - <span data-ttu-id="b0c74-294">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="b0c74-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="b0c74-295">Pole **Kod dyrektywy:** należy pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="b0c74-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="b0c74-296">**Wiele jednostek SKU:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="b0c74-297">Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="b0c74-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="b0c74-298">Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="b0c74-298">On the **Lines** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="b0c74-299">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="b0c74-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="b0c74-300">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0c74-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b0c74-301">**Od ilości:** *0*</span><span class="sxs-lookup"><span data-stu-id="b0c74-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="b0c74-302">**Do ilości:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="b0c74-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="b0c74-303">Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="b0c74-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="b0c74-304">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="b0c74-304">On the **Location Directive Actions** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="b0c74-305">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="b0c74-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="b0c74-306">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0c74-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b0c74-307">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b0c74-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="b0c74-308">Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na skróconej karcie **Dyrektywy akcji lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="b0c74-309">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="b0c74-310">W oknie dialogowym zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="b0c74-311">Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="b0c74-312">Wybierz przycisk **OK**, aby zatwierdzić zmiany.</span><span class="sxs-lookup"><span data-stu-id="b0c74-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="b0c74-313">Klasy robocze</span><span class="sxs-lookup"><span data-stu-id="b0c74-313">Work classes</span></span>

1. <span data-ttu-id="b0c74-314">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="b0c74-315">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0c74-316">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="b0c74-317">**Identyfikator klasy roboczej:** *Sortowane*</span><span class="sxs-lookup"><span data-stu-id="b0c74-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="b0c74-318">**Opis:** *Sortowane*</span><span class="sxs-lookup"><span data-stu-id="b0c74-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="b0c74-319">**Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*</span><span class="sxs-lookup"><span data-stu-id="b0c74-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="b0c74-320">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="b0c74-321">Szablony pracy</span><span class="sxs-lookup"><span data-stu-id="b0c74-321">Work templates</span></span>

1. <span data-ttu-id="b0c74-322">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b0c74-323">W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="b0c74-324">W siatce wybierz szablon pracy **62 Pobranie do pakowania**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="b0c74-325">W okienku akcji wybierz **Podziały nagłówka pracy**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="b0c74-326">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="b0c74-327">W wierszu, w którym pole **Nazwa pola** ma wartość *Identyfikator wysyłki*, wyczyść pole wyboru **Grupuj według tego pola**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-327">On the line where the **Field name** field is set to *Shipment ID*, clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="b0c74-328">Wybierz opcję **Zapisz**, a następnie zamknij okno dialogowe **Podziały nagłówka pracy**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-328">Select **Save**, and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="b0c74-329">W polu **Typ zlecenia pracy** zaznacz opcję *Pobranie z posortowanych zapasów*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="b0c74-330">Wybierz pozycję **Nowy**, aby utworzyć nowy pracy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="b0c74-331">W sekcji **Omówienie** ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="b0c74-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="b0c74-332">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="b0c74-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="b0c74-333">**Szablon pracy:** *Pobranie z posortowanych*</span><span class="sxs-lookup"><span data-stu-id="b0c74-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="b0c74-334">**Opis szablonu pracy:** *Pobranie z posortowanych*</span><span class="sxs-lookup"><span data-stu-id="b0c74-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="b0c74-335">Wybierz opcję **Zapisz**, aby sekcja **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="b0c74-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="b0c74-336">W sekcji **Szczegóły szablonu pracy** zostaną utworzone dwa wiersze.</span><span class="sxs-lookup"><span data-stu-id="b0c74-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="b0c74-337">Wybierz opcję **Nowe**, a następnie określ następujące wartości dla wiersza 1:</span><span class="sxs-lookup"><span data-stu-id="b0c74-337">Select **New**, and then set the following values for line 1:</span></span>

    - <span data-ttu-id="b0c74-338">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="b0c74-339">**Wymagane:** Wybrane (= *Tak*)</span><span class="sxs-lookup"><span data-stu-id="b0c74-339">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="b0c74-340">**Identyfikator klasy roboczej:** *Sortowane*</span><span class="sxs-lookup"><span data-stu-id="b0c74-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="b0c74-341">Wybierz znowu opcję **Nowe**, a następnie określ następujące wartości dla wiersza 2:</span><span class="sxs-lookup"><span data-stu-id="b0c74-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="b0c74-342">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="b0c74-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b0c74-343">**Wymagane:** Wybrane (= *Tak*)</span><span class="sxs-lookup"><span data-stu-id="b0c74-343">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="b0c74-344">**Identyfikator klasy roboczej:** *Sortowane*</span><span class="sxs-lookup"><span data-stu-id="b0c74-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="b0c74-345">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="b0c74-346">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="b0c74-346">Example scenario</span></span>

<span data-ttu-id="b0c74-347">W tym scenariuszu symulowane są sytuacje, w których magazyn przechowuje małe towary w lokalizacjach i pakuje je do pól przed ich wysłaniem, a funkcjonalność stacji pakowania jest w rzeczywistości odpowiednia.</span><span class="sxs-lookup"><span data-stu-id="b0c74-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="b0c74-348">Pracownicy kompletują zamówienia dla wielu klientów i jednocześnie pod różnymi adresami, aby zwiększyć szybkość kompletacji.</span><span class="sxs-lookup"><span data-stu-id="b0c74-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="b0c74-349">Po zakończeniu pobierania pracownicy docierają do lokalizacji sortowania, gdzie pobrane towary mogą być posortowane w odpowiednim polu na podstawie wymaganych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="b0c74-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="b0c74-350">W tym przykładzie identyfikator wysyłki zostanie użyty do ustalenia prawidłowego pola, ponieważ każda wysyłka ma inny adres.</span><span class="sxs-lookup"><span data-stu-id="b0c74-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="b0c74-351">Po zapełnieniu wszystkich towarów z ładunku i posortowaniu ich według wysyłki pola zostaną przeniesione do obszaru tymczasowego, a ostatecznie załadowane na ciężarówkę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="b0c74-352">Przed rozpoczęciem scenariusza należy upewnić się, że wszystkie funkcje magazynu standardowego są poprawnie skonfigurowane dla danego magazynu.</span><span class="sxs-lookup"><span data-stu-id="b0c74-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="b0c74-353">W tym celu jest używany standardowy magazyn *62* firmy Contoso.</span><span class="sxs-lookup"><span data-stu-id="b0c74-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="b0c74-354">Standardowe konfiguracje nie zostały zmienione, a nie zostały opisane w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="b0c74-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="b0c74-355">Utwórz popyt</span><span class="sxs-lookup"><span data-stu-id="b0c74-355">Create demand</span></span>

<span data-ttu-id="b0c74-356">Aby można było wykazać tę funkcję, trzeba utworzyć pewne zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="b0c74-357">W tym scenariuszu zostaną utworzone trzy zamówienia sprzedaży dla trzech różnych odbiorców w celu symulacji różnych adresów dostawy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="b0c74-358">W ten sposób utworzysz trzy osobne wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="b0c74-359">Przed utworzeniem zamówień sprzedaży i wysyłek upewnij się, że w lokalizacjach pobrania jest wystarczająca ilość zapasów dla wszystkich towarów w zamówieniach.</span><span class="sxs-lookup"><span data-stu-id="b0c74-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="b0c74-360">Przejrzyj ustawienia dyrektywy lokalizacji, aby potwierdzić lokalizacje pobrania używane do pobierania zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b0c74-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="b0c74-361">Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub skorzystać z dowolnego innego przepływu.</span><span class="sxs-lookup"><span data-stu-id="b0c74-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="b0c74-362">Następnie zarezerwuj ekwipunek.</span><span class="sxs-lookup"><span data-stu-id="b0c74-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="b0c74-363">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b0c74-364">Wybierz pozycję **Nowe**, aby utworzyć zamówienie sprzedaży dla zamówienia 1.</span><span class="sxs-lookup"><span data-stu-id="b0c74-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="b0c74-365">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0c74-366">**Odbiorca:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b0c74-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="b0c74-367">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="b0c74-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="b0c74-368">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-368">Select **OK**.</span></span>
1. <span data-ttu-id="b0c74-369">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b0c74-370">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-370">Set the following values:</span></span>

    - <span data-ttu-id="b0c74-371">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b0c74-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b0c74-372">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="b0c74-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="b0c74-373">Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="b0c74-374">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="b0c74-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="b0c74-375">**Ilość:** *10*</span><span class="sxs-lookup"><span data-stu-id="b0c74-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="b0c74-376">Poniższe kroki należy powtórzyć dla każdego wiersza sprzedaży w zamówieniu, aby zarezerwować dla niego zapasy:</span><span class="sxs-lookup"><span data-stu-id="b0c74-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="b0c74-377">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="b0c74-378">Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-378">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="b0c74-379">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-379">Select **Save**.</span></span>

1. <span data-ttu-id="b0c74-380">Wybierz pozycję **Nowe**, aby utworzyć zamówienie sprzedaży dla zamówienia 2.</span><span class="sxs-lookup"><span data-stu-id="b0c74-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="b0c74-381">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0c74-382">**Odbiorca:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="b0c74-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="b0c74-383">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="b0c74-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="b0c74-384">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-384">Select **OK**.</span></span>
1. <span data-ttu-id="b0c74-385">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b0c74-386">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-386">Set the following values:</span></span>

    - <span data-ttu-id="b0c74-387">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b0c74-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b0c74-388">**Ilość:** *7*</span><span class="sxs-lookup"><span data-stu-id="b0c74-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="b0c74-389">Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="b0c74-390">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="b0c74-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="b0c74-391">**Ilość:** *3*</span><span class="sxs-lookup"><span data-stu-id="b0c74-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="b0c74-392">Poniższe kroki należy powtórzyć dla każdego wiersza sprzedaży w zamówieniu, aby zarezerwować dla niego zapasy:</span><span class="sxs-lookup"><span data-stu-id="b0c74-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="b0c74-393">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="b0c74-394">Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-394">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="b0c74-395">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-395">Select **Save**.</span></span>

1. <span data-ttu-id="b0c74-396">Wybierz pozycję **Nowe**, aby utworzyć zamówienie sprzedaży dla zamówienia 3.</span><span class="sxs-lookup"><span data-stu-id="b0c74-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="b0c74-397">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0c74-398">**Odbiorca:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b0c74-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="b0c74-399">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="b0c74-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="b0c74-400">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-400">Select **OK**.</span></span>
1. <span data-ttu-id="b0c74-401">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b0c74-402">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b0c74-402">Set the following values:</span></span>

    - <span data-ttu-id="b0c74-403">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b0c74-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b0c74-404">**Ilość:** *8*</span><span class="sxs-lookup"><span data-stu-id="b0c74-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="b0c74-405">Wykonaj następujące kroki, aby zarezerwować zapasy dla linii sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="b0c74-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="b0c74-406">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="b0c74-407">Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-407">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="b0c74-408">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-408">Select **Save**.</span></span>

<span data-ttu-id="b0c74-409">Aby zwolnić poszczególne zamówienia sprzedaży do magazynu, należy wykonać poniższą procedurę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="b0c74-410">Zostaną utworzone trzy różne wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-410">Three different shipments will be created.</span></span> <span data-ttu-id="b0c74-411">Następnie należy dodać wszystkie trzy wysyłki do jednej nowej grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="b0c74-412">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b0c74-413">W siatce wybierz pierwsze utworzone zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b0c74-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="b0c74-414">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b0c74-415">Użytkownik otrzymuje komunikat informacyjny, który zawiera utworzony identyfikator grupy czynności oraz identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="b0c74-416">Powtórz powyższe kroki, aby zwolnić zamówienia sprzedaży 2 i 3 do magazynu.</span><span class="sxs-lookup"><span data-stu-id="b0c74-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="b0c74-417">Należy zauważyć, że otrzymany komunikat informacyjny wskazuje, że wysyłka została dodana do grupy czynności, która została utworzona podczas zwalniania zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="b0c74-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="b0c74-418">Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="b0c74-419">Wybierz grupę czynności, która została utworzona na podstawie zwolnienia zamówień sprzedaży, aby otworzyć stronę **Grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="b0c74-420">Na tej stronie są wyświetlane szczegóły dotyczące grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-420">This page shows the wave details.</span></span> <span data-ttu-id="b0c74-421">Na skróconej karcie **Wiersze grupy czynności** są wyświetlane wywysyłki, które zostały utworzone.</span><span class="sxs-lookup"><span data-stu-id="b0c74-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="b0c74-422">Teraz należy utworzyć pracę, aby przenieść pozycje z lokalizacji pobrania do lokalizacji sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="b0c74-423">W okienku akcji wybierz pozycję **Przetwarzanie**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="b0c74-424">Podczas przetwarzania grupy czynności metoda sortowania używa szablonu sortowania w celu przypisania zapasów do pozycji do sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="b0c74-425">Po zakończeniu przetwarzania grupy czynności zostanie wyświetlony komunikat informacyjny z informacją, że grupa czynności została opublikowana i została utworzona praca.</span><span class="sxs-lookup"><span data-stu-id="b0c74-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="b0c74-426">W okienku akcji na karcie **Grupa czynności**, w grupie **Informacje pokrewne** wybierz opcję **Praca**, aby wyświetlić utworzoną pracę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="b0c74-427">Zanotuj identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="b0c74-428">Należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="b0c74-429">W lewej kolumnie można wyświetlić wychodzącą pozycję sortowania utworzoną dla każdej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="b0c74-430">Na skróconej karcie **Kryteria stanowiska sortowania** można wyświetlić identyfikator wysyłki dla danego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="b0c74-431">Utworzono jeden identyfikator pracy w celu przeniesienia zapasów z lokalizacji pobrania do lokalizacji sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="b0c74-432">Do zakończenia pracy potrzebny jest identyfikator pracy utworzony podczas przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="b0c74-433">Pobieranie zamówienia sprzedaży do lokalizacji sortowania</span><span class="sxs-lookup"><span data-stu-id="b0c74-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="b0c74-434">Zaloguj się do aplikacji mobilnej jako pracownik w magazynie *62*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="b0c74-435">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="b0c74-436">W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="b0c74-437">Zaznacz pole **Identyfikator**, a następnie wprowadź identyfikator pracy z przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="b0c74-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="b0c74-438">Potwierdź wpis.</span><span class="sxs-lookup"><span data-stu-id="b0c74-438">Confirm your entry.</span></span>

    <span data-ttu-id="b0c74-439">Następnie wyświetlany jest monit o wprowadzenie docelowego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="b0c74-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="b0c74-440">Zwróć uwagę, że wiersz 1 z zamówienia sprzedaży 1 musi zostać pobrany i dodany do docelowego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="b0c74-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="b0c74-441">Wyświetlany jest kod towaru, ilość, opis towaru i lokalizacja pobrania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="b0c74-442">W polu **Docelowy num. id.** wprowadź numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="b0c74-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="b0c74-443">Wszystkie wiersze utworzone z przetworzonej grupy czynności zostaną pobrane na ten sam docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="b0c74-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="b0c74-444">Potwierdź wpis.</span><span class="sxs-lookup"><span data-stu-id="b0c74-444">Confirm your entry.</span></span>

    <span data-ttu-id="b0c74-445">Aplikacja mobilna przedstawia w serii stron **Pobrania**, które wskazują na lokalizację pobrania, oraz na towar i ilość, która musi zostać pobrana.</span><span class="sxs-lookup"><span data-stu-id="b0c74-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="b0c74-446">Po dodaniu pobranego towaru do numeru identyfikacyjnego należy potwierdzić poprawność pobrania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="b0c74-447">Ostatnia strona to praca, która powoduje umieszczenie pobranych towarów w lokalizacji sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="b0c74-448">Potwierdź pierwszą pracę pobrania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="b0c74-449">Zostanie wyświetlona Następna praca pobrania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-449">The next pick work is shown.</span></span> <span data-ttu-id="b0c74-450">Potwierdź pobranie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-450">Confirm the pick.</span></span>
1. <span data-ttu-id="b0c74-451">Kontynuuj, aby potwierdzić pozostałą pracę pobrania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="b0c74-452">Ostatnim krokiem jest zakończenie pracy odłożenia.</span><span class="sxs-lookup"><span data-stu-id="b0c74-452">The last step is to complete the put work.</span></span> <span data-ttu-id="b0c74-453">Potwierdź odłożenie w lokalizacji sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="b0c74-454">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="b0c74-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="b0c74-455">Zakończ **Pobranie sprzedaży** w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="b0c74-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="b0c74-456">Sortowanie/odłożenie na ścianę</span><span class="sxs-lookup"><span data-stu-id="b0c74-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="b0c74-457">Teraz, gdy wszystkie zapasy zostały wprowadzone do lokalizacji sortowania, należy je posortować na prawidłowej pozycji sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="b0c74-458">Logowanie do aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="b0c74-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="b0c74-459">W menu głównym wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="b0c74-460">W menu **Wychodzące** wybierz opcję **Sortowanie**, aby rozpocząć sortowanie towarów.</span><span class="sxs-lookup"><span data-stu-id="b0c74-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="b0c74-461">W polu **Numer identyfikacyjny/Con** wprowadź docelowy numer identyfikacyjny dla pobranej pracy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b0c74-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="b0c74-462">Potwierdź wpis.</span><span class="sxs-lookup"><span data-stu-id="b0c74-462">Confirm your entry.</span></span>
1. <span data-ttu-id="b0c74-463">Umożliwia wprowadzenie kodu towaru, który ma być posortowany jako pierwszy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="b0c74-464">System określa pierwsze stanowisko sortowania, które powinno zostać pokazane.</span><span class="sxs-lookup"><span data-stu-id="b0c74-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="b0c74-465">Potwierdź stanowisko sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="b0c74-466">Zostanie wyświetlony monit o przypisanie numeru identyfikacyjnego do stanowiska sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="b0c74-467">Zaznacz pole **Numer identyfikacyjny**, wprowadź numer identyfikacyjny, a następnie potwierdź wpis.</span><span class="sxs-lookup"><span data-stu-id="b0c74-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="b0c74-468">Ponieważ stanowisko sortowania jest powiązane z identyfikatorem wysyłki, towary te zostaną posortowane w numer identyfikacyjny, który jest właściwy dla wysyłki wychodzącej i zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b0c74-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="b0c74-469">Na następnej stronie jest wyświetlany identyfikator towaru, ilość, identyfikator stanowiska sortowania oraz numer identyfikacyjny „od” (pobranie) oraz „do” (sortowanie) identyfikatorów numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="b0c74-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="b0c74-470">Informacje na tej stronie instruują, aby posortować określoną pozycję i ilości z numeru rejestracyjnego pobrania do numeru identyfikacyjnego sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="b0c74-471">Potwierdź stanowisko sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="b0c74-472">Umożliwia posortowanie elementów na pierwszym stanowisku sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="b0c74-473">Po zakończeniu system kieruje do następnego stanowiska sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="b0c74-474">Powtórz ten proces dla wszystkich pobranych wierszy w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="b0c74-475">Tego procesu należy również używać w przypadku wielu wierszy pobrania o tym samym numerze towaru.</span><span class="sxs-lookup"><span data-stu-id="b0c74-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="b0c74-476">W przypadku powtórzenia tego procesu dla wszystkich towarów system ocenia kryteria z następnego zeskanowanego elementu (wiersz pracy) i określa stanowisko sortowania, do którego ma być wykonane przesunięcie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="b0c74-477">Automatycznie nastąpi przekierowanie w celu odłożenia towaru do właściwego stanowiska sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="b0c74-478">W zależności od konfiguracji potwierdzeń użytkownik jest również kierowany do potwierdzenia tej akcji przez wprowadzenie numeru stanowiska lub numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="b0c74-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0c74-479">Jeśli jest włączone sortowanie automatyczne, ręczna zmiana nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="b0c74-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="b0c74-480">Po zakończeniu w Microsoft Dynamics 365 Supply Chain Management otwórz stronę **Przypisania stanowisk sortowania towarów wychodzących**, aby przejrzeć stan stanowisk.</span><span class="sxs-lookup"><span data-stu-id="b0c74-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="b0c74-481">Jeśli pozycje są zamykane automatycznie, wybierz opcję **Pokaż zamknięte**, aby wyświetlić zamknięte stanowiska.</span><span class="sxs-lookup"><span data-stu-id="b0c74-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="b0c74-482">Zauważ, że są wyświetlane transakcje dotyczące stanowisk sortowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="b0c74-483">Wyświetlany jest towar i ilość przetworzona przez stanowisko.</span><span class="sxs-lookup"><span data-stu-id="b0c74-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="b0c74-484">Podczas konfigurowania szablonu wychodzącego sortowania została ustawiona opcja **Automatycznie zamknij stanowisko sortowania** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="b0c74-485">Z tego względu stanowisko jest automatycznie zamykane po umieszczeniu ostatniego oczekiwanego zapasu.</span><span class="sxs-lookup"><span data-stu-id="b0c74-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="b0c74-486">Pozycje sortowania są w stanie **Zamkniętym** i utworzono pracę w celu przeniesienia posortowanych zapasów do lokalizacji *Bramy dokującej*.</span><span class="sxs-lookup"><span data-stu-id="b0c74-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="b0c74-487">Zakończ posortowaną pracę pobrania dla magazynu, aby przenieść zapasy do lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b0c74-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="b0c74-488">Gdy magazyn jest gotowy, należy go potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="b0c74-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c74-489">W przypadku posortowanej pracy pobierania zapasów, która ma zostać prawidłowo przetworzona, element menu urządzenia przenośnego z identyfikatorem klasy pracy, w którym pole **Typ zlecenia pracy** jest ustawione na *Pobranie z posortowanych zapasów* powinno być używane w procesie przesunięcia i załadunku.</span><span class="sxs-lookup"><span data-stu-id="b0c74-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="b0c74-490">Ręcznie zamknij stanowisko (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="b0c74-490">Manually close a position (optional)</span></span>

<span data-ttu-id="b0c74-491">Jeśli stanowiska sortowania powinny być zamykane ręcznie, opcja **Automatycznie zamknij stanowisko sortowania** dla szablonu wychodzącego sortowania musi mieć wartość *Nie*, a zamknięcie musi być wykonane przed przeniesieniem zapasów do obszaru bramy dokującej.</span><span class="sxs-lookup"><span data-stu-id="b0c74-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No*, and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="b0c74-492">Stanowiska mogą być zamknięte na różne sposoby:</span><span class="sxs-lookup"><span data-stu-id="b0c74-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="b0c74-493">Poprzez aplikację mobilną Warehouse Management:</span><span class="sxs-lookup"><span data-stu-id="b0c74-493">Via the Warehouse Management mobile app:</span></span>

    - <span data-ttu-id="b0c74-494">Użytkownik może skanować jeden z towarów znajdujących się już na stanowisku, a następnie wybrać opcję **Zamknij**, aby zamknąć stanowisko.</span><span class="sxs-lookup"><span data-stu-id="b0c74-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="b0c74-495">Jeśli użytkownik zeskanuje kontener, który został już posortowany, wyświetlany jest komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="b0c74-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="b0c74-496">Użytkownik może jednak nadal zamknąć stanowisko.</span><span class="sxs-lookup"><span data-stu-id="b0c74-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="b0c74-497">Z Microsoft Dynamics 365 Supply Chain Management ze strony **Przypisania stanowisk sortowania towarów wychodzących**:</span><span class="sxs-lookup"><span data-stu-id="b0c74-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="b0c74-498">Użytkownik może wybrać rekord ze stanowiskiem wychodzącego sortowania, a następnie w okienku akcji wybrać **Zamknij stanowisko**.</span><span class="sxs-lookup"><span data-stu-id="b0c74-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="b0c74-499">Porady</span><span class="sxs-lookup"><span data-stu-id="b0c74-499">Tips</span></span>

- <span data-ttu-id="b0c74-500">Nie można przenosić towarów między pozycjami po ich przypisaniu do jednego.</span><span class="sxs-lookup"><span data-stu-id="b0c74-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="b0c74-501">System ocenia, ile elementów powinno zostać przestawionych na określone stanowisko.</span><span class="sxs-lookup"><span data-stu-id="b0c74-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="b0c74-502">Szablon sortowania można skonfigurować do automatycznego tworzenia kontenerów po zamknięciu stanowisk.</span><span class="sxs-lookup"><span data-stu-id="b0c74-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="b0c74-503">Ta metoda spowoduje utworzenie standardowej struktury identyfikatorów kontenerów opartej na określonym profilu pakowania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0c74-504">Po utworzeniu pracy przesunięcia z lokalizacji sortowania nie można anulować pracy.</span><span class="sxs-lookup"><span data-stu-id="b0c74-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="b0c74-505">W przeciwnym razie pozycja i kontenery w niej zostaną usunięte z systemu i nie będą dostępne do dalszego przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="b0c74-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="b0c74-506">Zapasy zostaną również usunięte.</span><span class="sxs-lookup"><span data-stu-id="b0c74-506">The inventory will also be removed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]