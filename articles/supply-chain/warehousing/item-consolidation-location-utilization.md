---
title: Konsolidacja pozycji — wykorzystanie lokalizacji
description: Ten temat zawiera informacje o funkcjach ułatwiających menedżerom magazynów wyświetlanie i filtrowanie objętościowe wykorzystania lokalizacji w magazynie. Menedżerowie mogą wybierać lokalizacje i tworzyć pracę przesunięcia zapasów bezpośrednio na stronie konsolidacji towaru w celu konsolidowania towarów, a w ten sposób lepiej korzystać z przestrzeni magazynowej.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6edabc51981d8935672b44e53b453cfbaca9031b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004659"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="48dda-104">Konsolidacja pozycji — wykorzystanie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48dda-105">Ten temat zawiera informacje o funkcjach ułatwiających menedżerom magazynów wyświetlanie i filtrowanie objętościowe wykorzystania lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="48dda-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="48dda-106">Menedżerowie mogą wybierać lokalizacje i tworzyć pracę przesunięcia zapasów bezpośrednio na stronie **Konsolidacji towaru** w celu konsolidowania towarów, a w ten sposób lepiej korzystać z przestrzeni magazynowej.</span><span class="sxs-lookup"><span data-stu-id="48dda-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="48dda-107">Włączanie funkcji</span><span class="sxs-lookup"><span data-stu-id="48dda-107">Turn on the features</span></span>

<span data-ttu-id="48dda-108">Aby można było skorzystać z funkcji opisanych w tym temacie, należy je włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="48dda-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="48dda-109">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="48dda-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="48dda-110">Włącz obie następujące funkcje w kolejności, w jakiej są wymienione w systemie.</span><span class="sxs-lookup"><span data-stu-id="48dda-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="48dda-111">(Obie funkcje dotyczą modułu **Zarządzania magazynem**.)</span><span class="sxs-lookup"><span data-stu-id="48dda-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="48dda-112">Stan lokalizacji w magazynie</span><span class="sxs-lookup"><span data-stu-id="48dda-112">Warehouse location status</span></span>
2. <span data-ttu-id="48dda-113">Wykorzystanie lokalizacji konsolidacji pozycji</span><span class="sxs-lookup"><span data-stu-id="48dda-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="48dda-114">Stan lokalizacji w magazynie</span><span class="sxs-lookup"><span data-stu-id="48dda-114">Warehouse location status</span></span>

<span data-ttu-id="48dda-115">Funkcja *Stan lokalizacji w magazynie* dodaje cztery nowe pola do strony **Lokalizacje** w celu śledzenia dodatkowych informacji o bieżącym stanie lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="48dda-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="48dda-116">**Kod towaru** – pozycja aktualnie w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="48dda-117">Jeśli lokalizacja zawiera wiele towarów, pole będzie puste.</span><span class="sxs-lookup"><span data-stu-id="48dda-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="48dda-118">**Data i godzina ostatniego działania** – sygnatura czasowa ostatniej transakcji magazynowej, która została wykonana w odniesieniu do tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="48dda-119">**Data wieku** – Data, kiedy zapasy w lokalizacji zostały wprowadzone do magazynu.</span><span class="sxs-lookup"><span data-stu-id="48dda-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="48dda-120">Ta data jest obliczana na podstawie daty wiekowania numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="48dda-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="48dda-121">Ta data dokładna w przypadku lokalizacji, w których numer identyfikacyjny jest śledzony, ale może być niedokładna w przypadku lokalizacji, dla których nie jest śledzony numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="48dda-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="48dda-122">**Stan lokalizacji** – stan lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="48dda-123">Cztery dostępne wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-123">Four values are available:</span></span>

    - <span data-ttu-id="48dda-124">**Nieokreślony** – Profil lokalizacji nie śledzi stanu.</span><span class="sxs-lookup"><span data-stu-id="48dda-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="48dda-125">W związku z tym bieżący stan jest nieznany.</span><span class="sxs-lookup"><span data-stu-id="48dda-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="48dda-126">**Puste** – W tej lokalizacji nie ma obecnie żadnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="48dda-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="48dda-127">**Pobieranie** – transakcje wychodzące zostały wykonane w odniesieniu do lokalizacji po jej opróżnieniu.</span><span class="sxs-lookup"><span data-stu-id="48dda-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="48dda-128">**Magazyn** – Tylko transakcje przychodzące zostały wykonane od kiedy lokalizacja była pusta.</span><span class="sxs-lookup"><span data-stu-id="48dda-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="48dda-129">Te pola umożliwiają kierownikom magazynu lepszy przegląd stanu lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="48dda-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="48dda-130">Umożliwiają także bardziej zaawansowane raportowanie i filtrowanie.</span><span class="sxs-lookup"><span data-stu-id="48dda-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="48dda-131">Ustawianie konsolidacja pozycji i wykorzystanie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="48dda-132">W tej sekcji opisano sposób przygotowania systemu do użycia konsolidacji pozycji i wykorzystania lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="48dda-133">W procedurach są używane przykładowe wartości z standardowych danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="48dda-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="48dda-134">Jeśli planujesz pracę z przykładowym scenariuszem przedstawionym w dalszej części tego tematu, wybierz firmę **USMF** (zawierającą standardowe dane demonstracyjne) i utwórz każdy rekord opisany w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="48dda-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="48dda-135">Jeśli nie planujesz pracy za pomocą scenariusza przykładowego, podane tu wartości można traktować jako przykłady typów konfiguracji, które należy wykonać w celu użycia tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="48dda-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="48dda-136">Zwolniony produkt</span><span class="sxs-lookup"><span data-stu-id="48dda-136">Released product</span></span>

1. <span data-ttu-id="48dda-137">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="48dda-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="48dda-138">W polu **Identyfikator pozycji** wybierz opcję *M9201*, a następnie otwórz stronę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="48dda-138">In the **Item number** field, select *M9201*, and open the details page.</span></span>
1. <span data-ttu-id="48dda-139">W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Magazyn** wybierz **Wymiary fizyczne**.</span><span class="sxs-lookup"><span data-stu-id="48dda-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="48dda-140">Na stronie **Wymiary fizyczne** w okienku akcji wybierz **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="48dda-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="48dda-141">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="48dda-141">A new line is added to the grid.</span></span> <span data-ttu-id="48dda-142">Pole **Identyfikator pozycji** jest wstępnie ustawione.</span><span class="sxs-lookup"><span data-stu-id="48dda-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="48dda-143">W polu **Jednostka** zaznacz opcję *każdy*.</span><span class="sxs-lookup"><span data-stu-id="48dda-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="48dda-144">Pozostałe pola w wierszu są ustawiane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="48dda-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="48dda-145">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48dda-145">Select **Save**, and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="48dda-146">Profil lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-146">Location profile</span></span>

1. <span data-ttu-id="48dda-147">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="48dda-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="48dda-148">Z listy profilów lokalizacji wybierz opcję **PIĘTRO-05**.</span><span class="sxs-lookup"><span data-stu-id="48dda-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="48dda-149">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="48dda-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="48dda-150">Na skróconej karcie **Ogólne** upewnij się, że obie następujące opcje są ustawione na wartość *Tak*:</span><span class="sxs-lookup"><span data-stu-id="48dda-150">On the **General** FastTab, make sure that both the following options are set to *Yes*:</span></span>

    - <span data-ttu-id="48dda-151">Włącz obsługę towaru w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-151">Enable item in location</span></span>
    - <span data-ttu-id="48dda-152">Włącz obsługę stanu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-152">Enable location status</span></span>

1. <span data-ttu-id="48dda-153">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48dda-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="48dda-154">Jeśli dla opcji **Włącz przedmiot w lokalizacji** i **Włącz stan lokalizacji** została już ustawiona wartość *Tak*, przejdź na instrukcje dotyczące konfigurowania karty skróconej **Wymiary** w kroku 10.</span><span class="sxs-lookup"><span data-stu-id="48dda-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes*, skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="48dda-155">Jeśli opcje nie zostały jeszcze ustawione na wartość *Tak*, należy uruchomić sprawdzanie spójności modułu **Zarządzania magazynem** po ich ręcznym ustawieniu.</span><span class="sxs-lookup"><span data-stu-id="48dda-155">If the options weren't already set to *Yes*, you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="48dda-156">W takim przypadku przejdź do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="48dda-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="48dda-157">Aby uruchomić sprawdzanie spójności, należy przejść do okna **Administracja systemu \> Okresowe zadania \> Baza danych \> Sprawdzania spójności**.</span><span class="sxs-lookup"><span data-stu-id="48dda-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="48dda-158">W wyświetlonym oknie dialogowym **Sprawdzanie spójności** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="48dda-159">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="48dda-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="48dda-160">**Sprawdź/napraw:** *Sprawdź*</span><span class="sxs-lookup"><span data-stu-id="48dda-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="48dda-161">**Od daty:** Zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="48dda-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="48dda-162">**Sprawdzanie spójności stanu lokalizacji w magazynie:** Zaznacz to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="48dda-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="48dda-163">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="48dda-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="48dda-164">Po zakończeniu sprawdzania spójności otrzymasz powiadomienie.</span><span class="sxs-lookup"><span data-stu-id="48dda-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="48dda-165">Otwórz [Centrum akcji](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) w celu wyświetlenia wiadomości.</span><span class="sxs-lookup"><span data-stu-id="48dda-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="48dda-166">Kliknij przycisk **Szczegóły komunikatu**, aby wyświetlić szczegóły.</span><span class="sxs-lookup"><span data-stu-id="48dda-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="48dda-167">Jeśli komunikat dotyczący kontroli spójności brzmi: „Znaleziono nieprawidłowe informacje o statusie lokalizacji dla lokalizacji XXXX w magazynie XX”, należy ponownie przeprowadzić kontrolę spójności.</span><span class="sxs-lookup"><span data-stu-id="48dda-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="48dda-168">W tym momencie należy zaznaczyć pole **Sprawdź/napraw**, aby *Naprawić błąd*.</span><span class="sxs-lookup"><span data-stu-id="48dda-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="48dda-169">Wyświetl komunikaty, aby upewnić się, że nie znaleziono błędów.</span><span class="sxs-lookup"><span data-stu-id="48dda-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="48dda-170">Należy teraz zakończyć konfigurowanie profilu lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="48dda-171">Wróć do **Zarządzanie magazynem \> Konfiguracja \> Magazyn \> Profile lokalizacji**, wybierz profil lokalizacji **PIĘTRO-05**, a następnie w okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="48dda-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles**, select location profile **FLOOR-05**, and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="48dda-172">Na skróconej karcie **Wymiary** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="48dda-173">**Procent wykorzystania objętości:** *100*</span><span class="sxs-lookup"><span data-stu-id="48dda-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="48dda-174">**Metoda pomiarowa używana w lokalizacji zapasów:** *Użyj woluminu lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="48dda-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="48dda-175">**Rzeczywista wysokość lokalizacji:** *10*</span><span class="sxs-lookup"><span data-stu-id="48dda-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="48dda-176">**Rzeczywista szerokość lokalizacji:** *10*</span><span class="sxs-lookup"><span data-stu-id="48dda-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="48dda-177">**Rzeczywista głębokość lokalizacji:** *10*</span><span class="sxs-lookup"><span data-stu-id="48dda-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="48dda-178">**Maksymalna waga:** *100*</span><span class="sxs-lookup"><span data-stu-id="48dda-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="48dda-179">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48dda-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="48dda-180">Elementy menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="48dda-180">Mobile device menu items</span></span>

1. <span data-ttu-id="48dda-181">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="48dda-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="48dda-182">W okienku akcji wybierz opcję **Nowy**, aby utworzyć element menu do sortowania.</span><span class="sxs-lookup"><span data-stu-id="48dda-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="48dda-183">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="48dda-184">**Nazwa elementu menu:** *Dostosuj w*</span><span class="sxs-lookup"><span data-stu-id="48dda-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="48dda-185">**Tytuł:** *Dostosuj w*</span><span class="sxs-lookup"><span data-stu-id="48dda-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="48dda-186">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="48dda-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="48dda-187">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="48dda-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="48dda-188">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="48dda-189">**Proces tworzenia pracy:** *Korekta w*</span><span class="sxs-lookup"><span data-stu-id="48dda-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="48dda-190">**Typy korekt zapasów:** *Korekta w*</span><span class="sxs-lookup"><span data-stu-id="48dda-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="48dda-191">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48dda-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="48dda-192">Menu urządzeń przenośnych</span><span class="sxs-lookup"><span data-stu-id="48dda-192">Mobile device menu</span></span>

1. <span data-ttu-id="48dda-193">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="48dda-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="48dda-194">Z listy menu wybierz opcję **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="48dda-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="48dda-195">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="48dda-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="48dda-196">Na liście **Dostępne menu i elementy menu** znajdź i zaznacz element menu **Dostosuj w**.</span><span class="sxs-lookup"><span data-stu-id="48dda-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="48dda-197">Wybierz strzałkę w prawo, aby przenieść **Dostosuj w** do listy **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="48dda-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="48dda-198">W ten sposób dodasz nowy element menu do wybranego menu.</span><span class="sxs-lookup"><span data-stu-id="48dda-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="48dda-199">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48dda-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="48dda-200">Typy przeniesienia</span><span class="sxs-lookup"><span data-stu-id="48dda-200">Movement types</span></span>

1. <span data-ttu-id="48dda-201">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Typy przesunięcia**.</span><span class="sxs-lookup"><span data-stu-id="48dda-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="48dda-202">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-202">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="48dda-203">**Kod typu przesunięcia:** *KONSOLIDOWANIE*</span><span class="sxs-lookup"><span data-stu-id="48dda-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="48dda-204">**Opis:** *Konsoliduj lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="48dda-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="48dda-205">**Identyfikator klasy roboczej:** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="48dda-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="48dda-206">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48dda-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="48dda-207">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="48dda-207">Example scenario</span></span>

<span data-ttu-id="48dda-208">W poniższym scenariuszu używana jest aplikacja magazynowa na urządzeniu przenośnym do tworzenia *korekt w* zapasów w dwóch lokalizacjach w magazynie.</span><span class="sxs-lookup"><span data-stu-id="48dda-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="48dda-209">Dodaj zapasy do lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-209">Add inventory to locations</span></span>

1. <span data-ttu-id="48dda-210">Zaloguj się do urządzenia mobilnego jako użytkownik skonfigurowany dla magazynu *51*.</span><span class="sxs-lookup"><span data-stu-id="48dda-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="48dda-211">Przejdź do **Zapasy \> Dostosuj w**.</span><span class="sxs-lookup"><span data-stu-id="48dda-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="48dda-212">Teraz będzie można wprowadzić pierwszą korektę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="48dda-213">W zadaniu **Korekta w** wybierz lokalizację, dla której ma zostać dokonana korekta zapasów.</span><span class="sxs-lookup"><span data-stu-id="48dda-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="48dda-214">W polu **LOC** wybierz wartość *LP-001*.</span><span class="sxs-lookup"><span data-stu-id="48dda-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="48dda-215">Potwierdź lokalizację.</span><span class="sxs-lookup"><span data-stu-id="48dda-215">Confirm the location.</span></span>
1. <span data-ttu-id="48dda-216">Utwórz identyfikator numeru identyfikacyjnego dla pozycji, która zostanie dodana do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="48dda-217">W polu **Numer identyfikacyjny** wprowadź *LP00101*.</span><span class="sxs-lookup"><span data-stu-id="48dda-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="48dda-218">Potwierdź numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="48dda-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="48dda-219">Wprowadź towar, który zostanie dodany do numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="48dda-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="48dda-220">W polu **ITEM** wprowadź *M9201*.</span><span class="sxs-lookup"><span data-stu-id="48dda-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="48dda-221">Potwierdź pozycję.</span><span class="sxs-lookup"><span data-stu-id="48dda-221">Confirm the item.</span></span>
1. <span data-ttu-id="48dda-222">Wprowadź ilość pozycji, która zostanie dodana.</span><span class="sxs-lookup"><span data-stu-id="48dda-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="48dda-223">W polu **ILOŚĆ** wprowadź *10*.</span><span class="sxs-lookup"><span data-stu-id="48dda-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="48dda-224">Potwierdź ilość.</span><span class="sxs-lookup"><span data-stu-id="48dda-224">Confirm the quantity.</span></span>

    <span data-ttu-id="48dda-225">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="48dda-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="48dda-226">Teraz będzie można wprowadzić drugą korektę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="48dda-227">W zadaniu **Korekta w** wybierz lokalizację, dla której ma zostać dokonana korekta zapasów.</span><span class="sxs-lookup"><span data-stu-id="48dda-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="48dda-228">W polu **LOC** wybierz wartość *LP-002*.</span><span class="sxs-lookup"><span data-stu-id="48dda-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="48dda-229">Potwierdź lokalizację.</span><span class="sxs-lookup"><span data-stu-id="48dda-229">Confirm the location.</span></span>
1. <span data-ttu-id="48dda-230">Utwórz identyfikator numeru identyfikacyjnego dla pozycji, która zostanie dodana do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="48dda-231">W polu **Numer identyfikacyjny** wprowadź *LP00201*.</span><span class="sxs-lookup"><span data-stu-id="48dda-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="48dda-232">Potwierdź numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="48dda-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="48dda-233">Wprowadź towar, który zostanie dodany do numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="48dda-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="48dda-234">W polu **ITEM** wprowadź *M9201*.</span><span class="sxs-lookup"><span data-stu-id="48dda-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="48dda-235">Potwierdź pozycję.</span><span class="sxs-lookup"><span data-stu-id="48dda-235">Confirm the item.</span></span>
1. <span data-ttu-id="48dda-236">Wprowadź ilość pozycji, która zostanie dodana.</span><span class="sxs-lookup"><span data-stu-id="48dda-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="48dda-237">W polu **ILOŚĆ** wprowadź *15*.</span><span class="sxs-lookup"><span data-stu-id="48dda-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="48dda-238">Potwierdź ilość.</span><span class="sxs-lookup"><span data-stu-id="48dda-238">Confirm the quantity.</span></span>

    <span data-ttu-id="48dda-239">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="48dda-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="48dda-240">Wybierz przycisk menu (czasami nazywany przyciskiem Hamburger lub Hamburger), a następnie wybierz opcję **Anuluj**, aby zamknąć zadanie **Korekta w**.</span><span class="sxs-lookup"><span data-stu-id="48dda-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="48dda-241">Konsolidowanie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="48dda-241">Consolidate locations</span></span>

1. <span data-ttu-id="48dda-242">Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Konsolidacja pozycji**.</span><span class="sxs-lookup"><span data-stu-id="48dda-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="48dda-243">W nagłówku wybierz magazyn, dla którego ma być wykonana konsolidacja.</span><span class="sxs-lookup"><span data-stu-id="48dda-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="48dda-244">W polu **Magazyn** wprowadź *51*.</span><span class="sxs-lookup"><span data-stu-id="48dda-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="48dda-245">Rekord jest wyświetlany dla każdej lokalizacji, w której skorygowano pozycję *M9201*.</span><span class="sxs-lookup"><span data-stu-id="48dda-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="48dda-246">Kolumna **Procent wykorzystania** wskazuje objętościowe wykorzystanie poszczególnych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="48dda-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="48dda-247">Aby skonsolidować zapasy, zaznacz wszystkie lokalizacje, które muszą zostać skonsolidowane, a następnie w okienku akcji wybierz opcję **Konsoliduj zapasy**.</span><span class="sxs-lookup"><span data-stu-id="48dda-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="48dda-248">W oknie dialogowym **Konsolidowanie zapasów** określ lokalizację i typ ruchu, który ma być używany do tworzenia pracy na potrzeby przesunięcia zapasów.</span><span class="sxs-lookup"><span data-stu-id="48dda-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="48dda-249">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="48dda-249">Set the following values:</span></span>

    - <span data-ttu-id="48dda-250">**Lokalizacja:** *LP-001*</span><span class="sxs-lookup"><span data-stu-id="48dda-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="48dda-251">**Kod typu przesunięcia:** *KONSOLIDOWANIE*</span><span class="sxs-lookup"><span data-stu-id="48dda-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="48dda-252">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="48dda-252">Select **OK**.</span></span>
1. <span data-ttu-id="48dda-253">Użytkownik otrzymuje komunikat informacyjny, który pokazuje utworzoną pracę przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="48dda-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="48dda-254">Zanotuj identyfikator pracy przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="48dda-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="48dda-255">Wyświetlanie pracy przeniesienia</span><span class="sxs-lookup"><span data-stu-id="48dda-255">View movement work</span></span>

1. <span data-ttu-id="48dda-256">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="48dda-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="48dda-257">Umożliwia wyświetlenie utworzonej pracy.</span><span class="sxs-lookup"><span data-stu-id="48dda-257">View the work that was created.</span></span> <span data-ttu-id="48dda-258">Identyfikator pracy przepływu należy wykorzystać z konsolidacji zapasów w celu filtrowania lub wyszukiwania siatki pracy.</span><span class="sxs-lookup"><span data-stu-id="48dda-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="48dda-259">W tym scenariuszu istniejąca lokalizacja, w której były zapasy, została użyta jako lokalizacja konsolidacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="48dda-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="48dda-260">W związku z tym utworzono tylko jeden identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="48dda-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="48dda-261">System tworzy jeden identyfikator pracy dla każdego przeniesienia, które musi zostać ukończone.</span><span class="sxs-lookup"><span data-stu-id="48dda-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="48dda-262">Jeśli zostanie określona lokalizacja, która już zawiera zapasy, zostanie utworzony tylko jeden identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="48dda-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="48dda-263">W przypadku określenia nowej lokalizacji tworzone są dwa identyfikatory pracy.</span><span class="sxs-lookup"><span data-stu-id="48dda-263">If you specify a new location, two work IDs are created.</span></span>
