---
title: Uzupełnianie zapasów ponad pojemność lokalizacji
description: Ten temat zawiera informacje dotyczące funkcji uzupełniania zapasów pojemności lokalizacji. Ta funkcja umożliwia utworzenie wszystkich prac związanych z uzupełnianiem zapasów, które będą wymagane w danym dniu, i zarządza dostępnością tych prac, aby zapewnić, że w lokalizacji pobrania nie zabraknie zapasów ani nie przekroczą pojemności.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8e9ae16fea892d1d6b6a6b5d06137576623e7f5b
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435613"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="aee6c-104">Uzupełnianie zapasów ponad pojemność lokalizacji</span><span class="sxs-lookup"><span data-stu-id="aee6c-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aee6c-105">Niektóre magazyny o dużym poziomie wolumenu lub przestrzeni muszą wysyłać większą ilość towaru w ciągu dnia, który nie mieści się w lokalizacji pobrania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="aee6c-106">Funkcja *Uzupełnianie zapasów ponad pojemność lokalizacji* umożliwia utworzenie wszystkich prac związanych z uzupełnianiem zapasów, które będą wymagane w danym dniu, i zarządza dostępnością tych prac, aby zapewnić, że w lokalizacji pobrania nie zabraknie zapasów ani nie przekroczą pojemności.</span><span class="sxs-lookup"><span data-stu-id="aee6c-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="aee6c-107">Funkcja umożliwia tworzenie większej ilości pracy uzupełniania, która nie mieści się w lokalizacji i blokuje pracę uzupełniania zapasów w przypadku zapełnienia lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="aee6c-108">Jeśli zapasy w lokalizacji pobrania są porzucane poniżej progu konfigurowalnego, dostępna jest większa ilość pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="aee6c-109">Włączanie funkcji Uzupełnianie zapasów ponad pojemność lokalizacji</span><span class="sxs-lookup"><span data-stu-id="aee6c-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="aee6c-110">Aby ta funkcja była dostępna, włącz następujące funkcje w module [zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności):</span><span class="sxs-lookup"><span data-stu-id="aee6c-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="aee6c-111">Blokowanie pracy na poziomie organizacji</span><span class="sxs-lookup"><span data-stu-id="aee6c-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="aee6c-112">Uzupełnianie zapasów ponad pojemność lokalizacji</span><span class="sxs-lookup"><span data-stu-id="aee6c-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="aee6c-113">Skonfiguruj funkcję dla tego scenariusza przykładowego</span><span class="sxs-lookup"><span data-stu-id="aee6c-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="aee6c-114">Ta sekcja zawiera wskazówki oraz przykład, w jaki sposób należy skonfigurować funkcję i przygotować przykładowe dane do scenariusza przykładowego, który opisano w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="aee6c-115">Włącz dane przykładowe</span><span class="sxs-lookup"><span data-stu-id="aee6c-115">Enable sample data</span></span>

<span data-ttu-id="aee6c-116">Aby pracować z tymi [przykładowymi scenariuszami](#example-scenario) przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aee6c-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="aee6c-117">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="aee6c-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="aee6c-118">Profil lokalizacji</span><span class="sxs-lookup"><span data-stu-id="aee6c-118">Location profile</span></span>

<span data-ttu-id="aee6c-119">Włącz funkcję uzupełniania nadmiaru pojemności w profilu lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="aee6c-120">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="aee6c-121">W lewym okienku wybierz **PICK-06**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="aee6c-122">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="aee6c-123">Na skróconej karcie **Uzupełnianie zapasów** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="aee6c-124">**Przekraczanie pojemności lokalizacji:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="aee6c-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="aee6c-125">Po włączeniu tej opcji maksymalna pojemność lokalizacji będzie mogła być przekraczana przez pracę uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="aee6c-126">Umożliwia także korzystanie z innych pól na skróconej karcie **Uzupełnienie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="aee6c-127">**Typ progu dostępności pracy:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="aee6c-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="aee6c-128">To pole określa metodę używaną do określenia, kiedy ma być zwalniana większa praca.</span><span class="sxs-lookup"><span data-stu-id="aee6c-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="aee6c-129">Możesz zwolnić według ilości lub procentu:</span><span class="sxs-lookup"><span data-stu-id="aee6c-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="aee6c-130">*Procent* — tę opcję należy wybrać, aby zastosować procentową zdolność produkcyjną opartą na limitach składowania lub miarach.</span><span class="sxs-lookup"><span data-stu-id="aee6c-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="aee6c-131">Zaznaczenie tej opcji włącza pole **Procent przepełnienia** i wyłącza dwie powiązane pola ilości, **Ilość przepełnienia** i **Jednostkę przepełnienia**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="aee6c-132">Opcji tej można skorzystać, jeśli lokalizacje pobrania używają miar.</span><span class="sxs-lookup"><span data-stu-id="aee6c-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="aee6c-133">Jeśli ta opcja jest zaznaczona, pole **Procent przepełnienia** jest ustawiane na wartość procentową, przy której będzie udostępniana większa ilość pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="aee6c-134">*Ilość* — tę opcję należy wybrać, aby zastosować określoną wartość ilości.</span><span class="sxs-lookup"><span data-stu-id="aee6c-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="aee6c-135">Zaznaczenie tej opcji wyłącza pole **Procent przepełnienia** i włącza dwie powiązane pola **Ilość przepełnienia** i **Jednostkę przepełnienia**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="aee6c-136">Tej opcji należy użyć w przypadku, gdy nie są używane objętości w odniesieniu do lokalizacji, które są uzupełniane, lub gdy istnieją spójne ilości, na których ma zostać przeprowadzona większa ilość zapasów w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="aee6c-137">Jeśli ta opcja jest zaznaczona, wartości pól **Ilość przepełnienia** i **Jednostka przepełnienia** należy określić w odniesieniu do ilości i jednostki, w których będzie dostępna większa ilość pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="aee6c-138">**Ilość przepełnienia:** *0,65*</span><span class="sxs-lookup"><span data-stu-id="aee6c-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="aee6c-139">To pole służy do definiowania ilości przepełnienia lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="aee6c-140">Praca będzie dostępna zawsze, gdy suma ilości dostępnej w lokalizacji i ilości pracy spadnie poniżej tej wartości.</span><span class="sxs-lookup"><span data-stu-id="aee6c-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="aee6c-141">Dowolna ilość pracy uzupełniania zapasów powyżej tej wartości zostanie zablokowana i musi być odblokowana ręcznie.</span><span class="sxs-lookup"><span data-stu-id="aee6c-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="aee6c-142">Limity składowania są brane pod uwagę podczas obliczania ilości pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="aee6c-143">**Jednostka przepełnienia:** *PL*</span><span class="sxs-lookup"><span data-stu-id="aee6c-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="aee6c-144">To pole określa jednostkę, która jest skojarzona z ilością przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="aee6c-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="aee6c-145">W takim przypadku więcej pracy uzupełniania zapasów zostanie udostępniona, gdy lokalizacja odniesie się do 0,65 palety (PL).</span><span class="sxs-lookup"><span data-stu-id="aee6c-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="aee6c-146">**Procent przepełnienia**</span><span class="sxs-lookup"><span data-stu-id="aee6c-146">**Overflow percentage**</span></span>

        <span data-ttu-id="aee6c-147">To pole służy do definiowania procentu przepełnienia lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="aee6c-148">Praca będzie dostępna zawsze, gdy suma ilości dostępnej w lokalizacji i ilości pracy spadnie poniżej tego procentu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="aee6c-149">Dowolna wartość procentowa ilości pracy uzupełniania zapasów powyżej tej wartości zostanie zablokowana i musi być odblokowana ręcznie.</span><span class="sxs-lookup"><span data-stu-id="aee6c-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="aee6c-150">Limity składowania są brane pod uwagę podczas obliczania procentu ilości pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="aee6c-151">Jeśli nie zdefiniowano żadnych limitów magazynowych, procent ilości pracy jest obliczany na podstawie objętości, jeśli w profilu lokalizacji są zdefiniowane ograniczenia dotyczące wolumenu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aee6c-152">Jeśli użytkownik korzysta z danych demonstracyjnych dla firmy **USMF** i uprzednio włączył funkcję *Pozycjonowania numeru identyfikacyjnego danej lokalizacji*, musi wyłączyć ustawienie **Włącz pozycjonowanie numeru identyfikacyjnego** dla profilu lokalizacji **BULK-06**, aby zakończyć etapy mobilne w scenariuszu przykładowym.</span><span class="sxs-lookup"><span data-stu-id="aee6c-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="aee6c-153">Kod kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="aee6c-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="aee6c-154">Aby można było skonfigurować kod kroku grupy czynności w sposób opisany w tym miejscu, należy najpierw skorzystać z [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby włączyć funkcję o nazwie *Kod kroku grupy czynności dotyczący całej organizacji:*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="aee6c-155">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody kroku grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="aee6c-156">Wybierz opcję **Nowe** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="aee6c-157">**Kod kroku grupy czynności:** *Uzupełnienie*</span><span class="sxs-lookup"><span data-stu-id="aee6c-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="aee6c-158">**Opis kroku grupy czynności:** *Uzupełnienie*</span><span class="sxs-lookup"><span data-stu-id="aee6c-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="aee6c-159">**Typ kroku grupy czynności:** *Uzupełnienie*</span><span class="sxs-lookup"><span data-stu-id="aee6c-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="aee6c-160">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="aee6c-161">Szablon uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="aee6c-161">Replenishment template</span></span>

<span data-ttu-id="aee6c-162">Szablony uzupełniania zapasów są zestawem reguł, które sterują tym, kiedy i jak zapasy są uzupełniane w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="aee6c-163">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="aee6c-164">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="aee6c-165">W sekcji **Przegląd** wybierz wiersz, w którym w polu **Szablon uzupełnienia** zaznaczono wartość *Uzupełnienie zapotrzebowania*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="aee6c-166">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-166">Set the following values:</span></span>

    - <span data-ttu-id="aee6c-167">**Kod kroku grupy czynności:** *Uzupełnienie*</span><span class="sxs-lookup"><span data-stu-id="aee6c-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="aee6c-168">**Zezwalaj, aby żądania w ramach grupy czynności korzystały z niezarezerwowanych ilości:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="aee6c-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="aee6c-169">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="aee6c-170">Szablon grupy czynności</span><span class="sxs-lookup"><span data-stu-id="aee6c-170">Wave template</span></span>

1. <span data-ttu-id="aee6c-171">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="aee6c-172">W lewym okienku w polu **Typ szablonu grupy czynności** ustaw wartość na *Wysyłka*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="aee6c-173">Wybierz szablon **61 Wysyłka** na liście.</span><span class="sxs-lookup"><span data-stu-id="aee6c-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="aee6c-174">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="aee6c-175">W karcie **Ogólne** ustaw **Automatyczne zwalnianie pracy uzupełniania zapasów** jako *Tak*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="aee6c-176">Ustaw opcję na *Tak*, aby tworzyć pracę uzupełnienia opartą na żądaniu, i zwalniać ją automatycznie.</span><span class="sxs-lookup"><span data-stu-id="aee6c-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="aee6c-177">Należy dodać do szablonu grupy czynności metodę grupy czynności uzupełnienia i utworzyć szablon uzupełnienia typu **Popyt grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="aee6c-178">Konfigurowanie szablonu uzupełniania zapasów znajdujących się na stronie **Szablony uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="aee6c-179">Aby skonfigurować szablon uzupełniania zapasów, należy dodać metodę uzupełnienia do szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="aee6c-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="aee6c-180">Na skróconej karcie **Metody** w kolumnie **Wybrane metody** znajdź następujący wiersz:</span><span class="sxs-lookup"><span data-stu-id="aee6c-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="aee6c-181">**Nazwa metody:** *replenish*</span><span class="sxs-lookup"><span data-stu-id="aee6c-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="aee6c-182">**Nazwa:** *Uzupełnienie*</span><span class="sxs-lookup"><span data-stu-id="aee6c-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="aee6c-183">Umożliwia ustawienie pola **Koda kroku grupy czynności** dla tego wiersza na *Replen*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="aee6c-184">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="aee6c-185">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="aee6c-185">Example scenario</span></span>

<span data-ttu-id="aee6c-186">Po wykonaniu wszystkich poprzednio opisanych przykładowych danych i ich skonfigurowania można korzystać z tego scenariusza, aby wypróbować funkcję *Uzupełnianie zapasów ponad pojemność lokalizacji*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="aee6c-187">Wartości przedstawione w tym scenariuszu zakładają, że pracujesz ze standardowymi danymi demonstracyjnymi, które zostały wybrane firmę **USMF**, oraz że zostały przygotowane przykładowe rekordy opisane wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="aee6c-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="aee6c-188">Ten scenariusz służy także jako przykład, który pokazuje, w jaki sposób funkcja może być używana w ustawieniu produkcji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="aee6c-189">Utwórz pracę uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="aee6c-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="aee6c-190">Utwórz zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="aee6c-190">Create sales order 1</span></span>

1. <span data-ttu-id="aee6c-191">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="aee6c-192">Wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe do tworzenia nowego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="aee6c-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="aee6c-193">W oknie dialogowym ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="aee6c-194">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="aee6c-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="aee6c-195">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="aee6c-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="aee6c-196">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="aee6c-197">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="aee6c-197">The new sales order is opened.</span></span> <span data-ttu-id="aee6c-198">Zawiera nowy, pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="aee6c-199">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="aee6c-200">**Numer pozycji:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="aee6c-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="aee6c-201">**Ilość:** *40*</span><span class="sxs-lookup"><span data-stu-id="aee6c-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="aee6c-202">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="aee6c-203">Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="aee6c-204">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aee6c-204">Close the page.</span></span>
1. <span data-ttu-id="aee6c-205">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="aee6c-206">Otrzymujesz komunikaty informacyjne, które zawierają utworzone identyfikatory grupy czynności i przesyłki.</span><span class="sxs-lookup"><span data-stu-id="aee6c-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="aee6c-207">Tworzona jest również grupa czynności uzupełnień.</span><span class="sxs-lookup"><span data-stu-id="aee6c-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="aee6c-208">Otrzymujesz również komunikat ostrzegawczy z informacją, że „Identyfikator pracy XXXX nie może zostać odblokowany, ponieważ zawiera niedokończone prace uzupełniające”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="aee6c-209">Utwórz zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="aee6c-209">Create sales order 2</span></span>

1. <span data-ttu-id="aee6c-210">Na stronie **Wszystkie zamówienia sprzedaży** wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe do tworzenia nowego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="aee6c-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="aee6c-211">W oknie dialogowym ustaw następującą wartość:</span><span class="sxs-lookup"><span data-stu-id="aee6c-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="aee6c-212">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="aee6c-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="aee6c-213">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="aee6c-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="aee6c-214">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="aee6c-215">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="aee6c-215">The new sales order is opened.</span></span> <span data-ttu-id="aee6c-216">Zawiera nowy, pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="aee6c-217">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="aee6c-218">**Numer pozycji:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="aee6c-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="aee6c-219">**Ilość:** *60*</span><span class="sxs-lookup"><span data-stu-id="aee6c-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="aee6c-220">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="aee6c-221">Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="aee6c-222">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aee6c-222">Close the page.</span></span>
1. <span data-ttu-id="aee6c-223">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="aee6c-224">Otrzymujesz komunikaty informacyjne, które zawierają utworzone identyfikatory grupy czynności i przesyłki.</span><span class="sxs-lookup"><span data-stu-id="aee6c-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="aee6c-225">Tworzona jest również grupa czynności uzupełnień.</span><span class="sxs-lookup"><span data-stu-id="aee6c-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="aee6c-226">Otrzymujesz również komunikat ostrzegawczy z informacją, że „Identyfikator pracy XXXX nie może zostać odblokowany, ponieważ zawiera niedokończone prace uzupełniające”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="aee6c-227">Utwórz zamówienie sprzedaży 3</span><span class="sxs-lookup"><span data-stu-id="aee6c-227">Create sales order 3</span></span>

1. <span data-ttu-id="aee6c-228">Na stronie **Wszystkie zamówienia sprzedaży** wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe do tworzenia nowego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="aee6c-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="aee6c-229">W oknie dialogowym ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="aee6c-230">**Konto odbiorcy:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="aee6c-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="aee6c-231">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="aee6c-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="aee6c-232">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="aee6c-233">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="aee6c-233">The new sales order is opened.</span></span> <span data-ttu-id="aee6c-234">Zawiera nowy, pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="aee6c-235">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="aee6c-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="aee6c-236">**Numer pozycji:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="aee6c-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="aee6c-237">**Ilość:** *30*</span><span class="sxs-lookup"><span data-stu-id="aee6c-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="aee6c-238">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="aee6c-239">Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="aee6c-240">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aee6c-240">Close the page.</span></span>
1. <span data-ttu-id="aee6c-241">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="aee6c-242">Otrzymujesz komunikaty informacyjne, które zawierają utworzone identyfikatory grupy czynności i przesyłki.</span><span class="sxs-lookup"><span data-stu-id="aee6c-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="aee6c-243">Tworzona jest również grupa czynności uzupełnień.</span><span class="sxs-lookup"><span data-stu-id="aee6c-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="aee6c-244">Otrzymujesz również komunikat ostrzegawczy z informacją, że „Identyfikator pracy XXXX nie może zostać odblokowany, ponieważ zawiera niedokończone prace uzupełniające”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="aee6c-245">Wyświetlanie szczegółów pracy</span><span class="sxs-lookup"><span data-stu-id="aee6c-245">View work details</span></span>

1. <span data-ttu-id="aee6c-246">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="aee6c-247">W sekcji **Przegląd** odfiltruj kolumnę **Magazyn** dla magazynu *61*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="aee6c-248">Należy sprawdzić, czy dla trzech zamówień sprzedaży na żądanie zostały utworzone siedem identyfikatorów pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="aee6c-249">Trzy z siedmiu identyfikatorów pracy mają w **Typu zlecenia pracy** wartość *Uzupełnienie*, a cztery mają w **Typ zlecenia pracy** wartość *Zamówienie sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="aee6c-250">Wszystkie trzy identyfikatory pracy, dla których wartość **Typu zlecenia pracy** to *Uzupełnienie*, mają te same lokalizacje *Pobrania* i *Odłożenia* w sekcji **Wiersze**:</span><span class="sxs-lookup"><span data-stu-id="aee6c-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="aee6c-251">**Odbierz:** *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="aee6c-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="aee6c-252">**Odłóz:** *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="aee6c-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="aee6c-253">Utworzono dwa identyfikatory pracy dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="aee6c-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="aee6c-254">Zapisz identyfikatory pracy dla zamówienń sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="aee6c-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="aee6c-255">W zależności od ilości dostępnych ilości pracy mogą być nieco niezmienne.</span><span class="sxs-lookup"><span data-stu-id="aee6c-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="aee6c-256">Jednak ogólnie utworzone nagłówki pracy powinny pasować do tego przykładu scenariusza.</span><span class="sxs-lookup"><span data-stu-id="aee6c-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="aee6c-257">Identyfikator numeru identyfikacyjnego dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="aee6c-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="aee6c-258">W dalszej części tego scenariusza będzie używana aplikacja magazynu (lub emulator), gdzie należy zidentyfikować numer identyfikacyjny w celu ukończenia scenariuszy pobierania i uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-258">Later in this scenario, you will use the warehouse app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="aee6c-259">Aby znaleźć identyfikatory numerów identyfikacyjnych, które będą potrzebne później, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="aee6c-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="aee6c-260">Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="aee6c-261">Wybierz przycisk **Pokaż filtry**, aby otworzyć okienko filtru.</span><span class="sxs-lookup"><span data-stu-id="aee6c-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="aee6c-262">Wprowadź poniższe kryteria filtrowania, aby uzyskać tablice rejestracyjne dla scenariusza.</span><span class="sxs-lookup"><span data-stu-id="aee6c-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="aee6c-263">Należy skorzystać z filtru *zaczyna się od*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="aee6c-264">**Numer pozycji:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="aee6c-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="aee6c-265">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="aee6c-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="aee6c-266">Wybierz opcję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-266">Select **Apply**.</span></span>
1. <span data-ttu-id="aee6c-267">W Okienku akcji kliknij pozycję **Wymiary**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="aee6c-268">W oknie dialogowym **Wyświetlanie wymiarów** w sekcji **Wymiary magazynowe** wybierz wszystkie wartości.</span><span class="sxs-lookup"><span data-stu-id="aee6c-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="aee6c-269">W sekcji **Transakcje** wybierz **Numer pozycji** i **Ilość \<\> 0**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="aee6c-270">Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="aee6c-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="aee6c-271">Na siatce **Dostępne** są wyświetlane numery numerów identyfikacyjnych dla pozycji *T0100* w każdej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="aee6c-272">Zanotuj numer identyfikacyjny znajdujący się w każdej lokalizacji, ponieważ informacje te będą potrzebne później.</span><span class="sxs-lookup"><span data-stu-id="aee6c-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="aee6c-273">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aee6c-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="aee6c-274">Kroki procesu</span><span class="sxs-lookup"><span data-stu-id="aee6c-274">Process steps</span></span>

<span data-ttu-id="aee6c-275">Uzupełnianie lokalizacji w magazynie jest wykonywane dla pierwszych dwóch identyfikatorów pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="aee6c-276">Praca nad trzecią pracą uzupełniania zapasów zostanie zablokowana do momentu, gdy poziom zapasów w lokalizacji pobrania spadnie poniżej progu.</span><span class="sxs-lookup"><span data-stu-id="aee6c-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="aee6c-277">Uzupełnianie zapasów</span><span class="sxs-lookup"><span data-stu-id="aee6c-277">Replenishment</span></span>

1. <span data-ttu-id="aee6c-278">Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *61*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-278">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="aee6c-279">(Wprowadź *61* jako identyfikator użytkownika i *1* jako hasło.)</span><span class="sxs-lookup"><span data-stu-id="aee6c-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="aee6c-280">Przejdź do **Zapasy \> Uzupełnienie**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="aee6c-281">Zostanie wyświetlony monit o wykonanie pierwszej pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="aee6c-282">Wyświetlany jest numer pozycji, ilość i lokalizacja do pobrania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="aee6c-283">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="aee6c-284">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="aee6c-285">System generuje numer identyfikacyjny docelowy dla nowego numeru identyfikacyjnego pobranego towaru.</span><span class="sxs-lookup"><span data-stu-id="aee6c-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="aee6c-286">Wybierz przycisk **OK**, aby zatwierdzić wartość.</span><span class="sxs-lookup"><span data-stu-id="aee6c-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="aee6c-287">Wyświetlana jest pokazana praca, która nakazuje użytkownikowi umieszczenie docelowego numeru identyfikacyjnego w lokalizacji uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="aee6c-288">Lokalizacja *Odłożenia* powinna być **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="aee6c-289">Potwierdź szczegóły umieszczania i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="aee6c-290">Otrzymasz komunikat „Praca zakończona” i zostaną wyświetlone szczegóły następnego zadania pobrania uzupełnienia: numer pozycji, ilość i lokalizacja do pobrania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="aee6c-291">Lokalizacja pobrania będzie taka sama jak pierwsza lokalizacja uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="aee6c-292">W związku z tym numer identyfikacyjny ma ten sam identyfikator, który był używany dla pierwszego zadania pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="aee6c-293">Powtórz powyższe kroki, aby ukończyć pracę uzupełniania zapasów dla drugiego zadania pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="aee6c-294">Ilość i docelowy numer identyfikacyjny różnią się od ilości i docelowego numeru identyfikacyjnego dla pierwszego zadania pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="aee6c-295">Po zakończeniu drugiej pracy uzupełniania zapasów wyświetlany jest komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="aee6c-296">Urządzenie przenośne informuje również o tym, że nie ma dostępnej pracy, nawet jeśli pozostała część pracy uzupełniającej.</span><span class="sxs-lookup"><span data-stu-id="aee6c-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="aee6c-297">Takie zachowanie występuje, ponieważ praca uzupełniania zapasów ma stan dostępności *Wstrzymany* i dlatego oznaczono jako **Zablokowana**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="aee6c-298">Stan *Wstrzymany* został wyzwolony, ponieważ profil lokalizacji dla lokalizacji pobrania, do której jest przypisana praca, ma wartość **Ilości przepełnienia** równą *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="aee6c-299">Dwa poprzednie zadania związane z uzupełnianiem zapasów wypełnione lokalizacją prawie do limitu przepełnienia dla pozycji *T0100*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="aee6c-300">(Przeliczenie jednostek towaru wynosi *1 PL = 100 każdy*.) W związku z tym pozostała praca uzupełniania zapasów spowodowałaby przekroczenie limitu przepełnienia w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="aee6c-301">Dopóki w lokalizacji nie zostanie pobrana wystarczająca ilość zapasów w celu przeniesienia jej poniżej progu zwolnienia pracy w menu urządzenia przenośnego, ta praca uzupełniania pozostanie zablokowana.</span><span class="sxs-lookup"><span data-stu-id="aee6c-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="aee6c-302">Odbiór zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="aee6c-302">Sales order pick</span></span>

<span data-ttu-id="aee6c-303">Aby można było ukończyć pozostałe zadanie uzupełniania zapasów, lokalizacja pobrania musi zostać wyczerpana z zapasów do poziomu, w którym może zostać odblokowana pozostała praca uzupełniająca.</span><span class="sxs-lookup"><span data-stu-id="aee6c-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="aee6c-304">Innymi słowy, suma ilości dostępnych zapasów w lokalizacji i ilości uzupełniania nie może przekroczyć wartości **Ilości przepełnienia**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="aee6c-305">Gdy ta suma jest mniejsza niż ilość przepełnienia, zostanie odblokowana pozostała praca uzupełniająca.</span><span class="sxs-lookup"><span data-stu-id="aee6c-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="aee6c-306">Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *61*.</span><span class="sxs-lookup"><span data-stu-id="aee6c-306">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="aee6c-307">(Wprowadź *61* jako identyfikator użytkownika i *1* jako hasło.)</span><span class="sxs-lookup"><span data-stu-id="aee6c-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="aee6c-308">Przejdź do **Wychodzące \> Pobieranie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="aee6c-309">Wprowadź pierwszy identyfikator pracy dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="aee6c-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="aee6c-310">Zapoznaj się z identyfikatorami roboczymi dla zamówień sprzedaży, które zostały wykonane wcześniej, na stronie **Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="aee6c-311">Wprowadzony tutaj identyfikator pracy będzie generował pracę pobrania dla ilości 10 każdy z dwóch odrębnych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="aee6c-312">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-312">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-313">Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, które można pobrać z pierwszej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="aee6c-314">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="aee6c-315">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="aee6c-316">Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, które można pobrać z następnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="aee6c-317">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="aee6c-318">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="aee6c-319">Strona **Zamówień sprzedaży: Pobranie** zawiera instrukcje, aby odłożyć obie kompletacje do lokalizacji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="aee6c-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="aee6c-320">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-320">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-321">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="aee6c-322">Wprowadź drugi identyfikator pracy dla zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="aee6c-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="aee6c-323">Istnieje tylko jedno zadanie pobrania dla tego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="aee6c-324">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-324">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-325">Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, z której można pobrać.</span><span class="sxs-lookup"><span data-stu-id="aee6c-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="aee6c-326">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="aee6c-327">Określony numer identyfikacyjny będzie jednym z wygenerowanych przez system numerów identyfikacyjnych na podstawie zadań związanych z pracą uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="aee6c-328">Aby mieć pewność, że jest przechwytywany poprawny identyfikator numeru identyfikacyjnego, należy sprawdzić, czy na stronie **Lista dostępnych** znajduje się pozycja zapasy, lokalizacja i ilość.</span><span class="sxs-lookup"><span data-stu-id="aee6c-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="aee6c-329">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="aee6c-330">Potwierdź instrukcje dotyczące zadania wysyłania do wychodzącej lokalizacji przemieszczania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="aee6c-331">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-331">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-332">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="aee6c-333">Zamówienie sprzedaży 2 jest zablokowane przed pobraniem, ponieważ zadanie uzupełniania zapasów, z którym jest połączony, nie zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="aee6c-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="aee6c-334">Obecnie w lokalizacji pobrania występuje wciąż liczba 30 każdy, a ilość uzupełnienia zapasów dla zamówienia sprzedaży 2 wynosi 60 każdy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="aee6c-335">Suma dostępnych zapasów i zapasów uzupełniających (90 każdy) przekracza ilość przepełnienia 0,65 PL (lub 65 każdy).</span><span class="sxs-lookup"><span data-stu-id="aee6c-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="aee6c-336">Aby można było ukończyć pracę uzupełniania zapasów, należy pobrać zamówienie sprzedaży 3.</span><span class="sxs-lookup"><span data-stu-id="aee6c-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="aee6c-337">Wprowadź identyfikator pracy dla zamówienia sprzedaży 3.</span><span class="sxs-lookup"><span data-stu-id="aee6c-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="aee6c-338">Istnieje tylko jedno zadanie pobrania dla tego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="aee6c-339">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-339">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-340">Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, z której można pobrać.</span><span class="sxs-lookup"><span data-stu-id="aee6c-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="aee6c-341">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="aee6c-342">Określony numer identyfikacyjny będzie jednym z wygenerowanych przez system numerów identyfikacyjnych na podstawie zadań związanych z pracą uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="aee6c-343">Aby mieć pewność, że jest przechwytywany poprawny identyfikator numeru identyfikacyjnego, należy sprawdzić, czy na stronie **Lista dostępnych** znajduje się pozycja zapasy, lokalizacja i ilość.</span><span class="sxs-lookup"><span data-stu-id="aee6c-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="aee6c-344">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="aee6c-345">Potwierdź instrukcje dotyczące zadania wysyłania do wychodzącej lokalizacji przemieszczania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="aee6c-346">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-346">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-347">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="aee6c-348">Gdy tylko suma ilości na stanie w miejscu pobrania i ilości do uzupełnienia spadnie poniżej progu, będzie można przetworzyć pozostałą pracę uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="aee6c-349">Wróć do strony **Szczegóły pracy** i zwróć uwagę, że dostępność prac uzupełniających dla ostatniej części uzupełnienia (dla zamówienia sprzedaży 2) to *Otwarte*, ponieważ w tej lokalizacji jest teraz wystarczająco dużo miejsca, aby przyjąć uzupełnienie.</span><span class="sxs-lookup"><span data-stu-id="aee6c-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="aee6c-350">Teraz można przetwarzać tę pracę uzupełniania zapasów za pośrednictwem urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="aee6c-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="aee6c-351">Przejdź do **Zapasy \> Uzupełnienie**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="aee6c-352">Zostanie wyświetlony monit o wykonanie resztę pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="aee6c-353">Wyświetlany jest numer pozycji, ilość i lokalizacja do pobrania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="aee6c-354">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="aee6c-355">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="aee6c-356">System generuje numer identyfikacyjny docelowy dla nowego numeru identyfikacyjnego pobranego towaru.</span><span class="sxs-lookup"><span data-stu-id="aee6c-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="aee6c-357">Wybierz przycisk **OK**, aby zatwierdzić wartość.</span><span class="sxs-lookup"><span data-stu-id="aee6c-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="aee6c-358">Wyświetlana jest pokazana praca, która nakazuje użytkownikowi umieszczenie docelowego numeru identyfikacyjnego w lokalizacji uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="aee6c-359">Lokalizacja *Odłożenia* powinna być **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="aee6c-360">Potwierdź szczegóły umieszczania i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="aee6c-361">Otrzymujesz komunikaty „Praca zakończona” i „Brak dostępnej pracy”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="aee6c-362">Teraz może być pobrane zamówienie sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="aee6c-362">You can now pick sales order 2.</span></span> <span data-ttu-id="aee6c-363">Po zakończeniu pracy uzupełniania zapasów połączonej z zamówieniem sprzedaży jego praca została odblokowana.</span><span class="sxs-lookup"><span data-stu-id="aee6c-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="aee6c-364">Wprowadź identyfikator pracy dla zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="aee6c-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="aee6c-365">Istnieje tylko jedno zadanie pobrania dla tego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="aee6c-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="aee6c-366">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-366">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-367">Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, z której można pobrać.</span><span class="sxs-lookup"><span data-stu-id="aee6c-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="aee6c-368">W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="aee6c-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="aee6c-369">Określony numer identyfikacyjny będzie wygenerowanych przez system numerem identyfikacyjnym na podstawie zadania związanego z pracą uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="aee6c-370">Aby mieć pewność, że jest przechwytywany poprawny identyfikator numeru identyfikacyjnego, należy sprawdzić, czy na stronie **Lista dostępnych** znajduje się pozycja zapasy, lokalizacja i ilość.</span><span class="sxs-lookup"><span data-stu-id="aee6c-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="aee6c-371">Wybierz przycisk **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="aee6c-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="aee6c-372">Potwierdź instrukcje dotyczące zadania wysyłania do wychodzącej lokalizacji przemieszczania.</span><span class="sxs-lookup"><span data-stu-id="aee6c-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="aee6c-373">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-373">Select **OK**.</span></span>

    <span data-ttu-id="aee6c-374">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="aee6c-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="aee6c-375">Notatki i porady</span><span class="sxs-lookup"><span data-stu-id="aee6c-375">Notes and tips</span></span>

- <span data-ttu-id="aee6c-376">Ta funkcja działa ze wszystkimi typami uzupełniania: zapotrzebowaniem na falę, min./maks., zapotrzebowaniem na obciążenie i szczelinami.</span><span class="sxs-lookup"><span data-stu-id="aee6c-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="aee6c-377">Można ręcznie zastępować dostępność pracy uzupełniania zapasów dla każdego nagłówka pracy na stronie **Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="aee6c-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="aee6c-378">Jeśli system ustawi dostępność pracy uzupełniania zapasów, będzie ona uwzględniać zapasy znajdujące się już w lokalizacji przed ukończeniem pracy</span><span class="sxs-lookup"><span data-stu-id="aee6c-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="aee6c-379">Każda część pracy z zamówieniem sprzedaży jest połączona z określoną pracą uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="aee6c-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="aee6c-380">Nie ma odpowiedniej funkcji dostępności pracy w sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="aee6c-380">There is no corresponding sales work availability functionality.</span></span>
