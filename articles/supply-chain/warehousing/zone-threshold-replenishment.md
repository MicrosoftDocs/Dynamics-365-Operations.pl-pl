---
title: Uzupełnianie zapasów na podstawie progu w strefie
description: W przypadku zapasów uzupełniających dla strefy używana jest minimalna/maksymalna (min./maks.) strategia uzupełniania zapasów, ale system ocenia całe strefy magazynowe, a nie tylko poszczególne lokalizacje. Dzięki temu kierownik magazynu może szybko rozpoznać, kiedy w strefie pobrania są wymagane dodatkowe zapasy.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6aaa139fb206c035b25b7056e681d086fde6447f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245065"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="43c24-104">Uzupełnianie zapasów na podstawie progu w strefie</span><span class="sxs-lookup"><span data-stu-id="43c24-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43c24-105">W przypadku zapasów uzupełnianych dla strefy używana jest minimalna/maksymalna (min./maks.) strategia [uzupełniania](replenishment.md) zapasów, ale system ocenia całe strefy magazynowe, a nie tylko poszczególne lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="43c24-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="43c24-106">Dzięki temu kierownik magazynu może szybko rozpoznać, kiedy w strefie pobrania są wymagane dodatkowe zapasy.</span><span class="sxs-lookup"><span data-stu-id="43c24-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="43c24-107">Ustawienia tej funkcji są podobne do ustawień uzupełniania w oparciu o lokalizację.</span><span class="sxs-lookup"><span data-stu-id="43c24-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="43c24-108">Jednak podczas konfigurowania szablonu dla minimalnego/maksymalnego uzupełnienia zapasów można również określić, czy próg ma być oceniany według lokalizacji, czy dla każdej strefy.</span><span class="sxs-lookup"><span data-stu-id="43c24-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="43c24-109">W przypadku skonfigurowania oceny opartej na strefach należy dodać określone strefy do zapytania wyboru strefy.</span><span class="sxs-lookup"><span data-stu-id="43c24-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="43c24-110">Podobnie jak w przypadku minimalnych/maksymalnych uzupełnień na podstawie lokalizacji, minimalne/maksymalne uzupełnienie w strefie jest oparte na konfiguracji minimalnego progu zapasów, który wyzwala tworzenie zlecenia pracy uzupełniania dla wybranych towarów.</span><span class="sxs-lookup"><span data-stu-id="43c24-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="43c24-111">Ta praca uzupełnienia zapasów spowoduje zwiększenie ilości zapasów do określonego progu maksymalnego dla strefy.</span><span class="sxs-lookup"><span data-stu-id="43c24-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="43c24-112">Proces uzupełniania zapasów strefy dla wariantów produktów nie jest obsługiwany w bieżącej wersji.</span><span class="sxs-lookup"><span data-stu-id="43c24-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="43c24-113">W przeciwieństwie do minimalnych/maksymalnych uzupełnień na podstawie lokalizacji, wartość minimalna/maksymalna dla uzupełniania zapasów w strefie nie wymaga ustalonych lokalizacji, aby ocenić, czy lokalizacje powinny przechowywać określony towar.</span><span class="sxs-lookup"><span data-stu-id="43c24-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="43c24-114">W związku z tym zapasy uzupełniające strefy umożliwiają korzystanie z minimalnych/maksymalnych uzupełnień, nawet jeśli nie utworzono żadnych stałych lokalizacji dla każdego wariantu towaru lub towaru w magazynie.</span><span class="sxs-lookup"><span data-stu-id="43c24-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="43c24-115">Jeśli ilość w strefie spadnie poniżej określonego progu minimalnego, tworzone jest zlecenie pracy uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="43c24-116">Dyrektywy lokalizacji określają lokalizację, do której należy wprowadzić zapasy.</span><span class="sxs-lookup"><span data-stu-id="43c24-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="43c24-117">Włącz funkcję Uzupełnianie zapasów na podstawie progu w strefie</span><span class="sxs-lookup"><span data-stu-id="43c24-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="43c24-118">Aby móc używać funkcji *Uzupełniania zapasów na podstawie progu w strefie*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="43c24-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="43c24-119">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="43c24-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="43c24-120">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="43c24-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="43c24-121">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="43c24-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="43c24-122">**Nazwa funkcji:** *Uzupełnianie zapasów na podstawie progu w strefie*</span><span class="sxs-lookup"><span data-stu-id="43c24-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="43c24-123">Konfigurowanie uzupełniania zapasów w strefie</span><span class="sxs-lookup"><span data-stu-id="43c24-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="43c24-124">Aby skonfigurować uzupełniania zapasów w strefie, należy skonfigurować kilka części systemu.</span><span class="sxs-lookup"><span data-stu-id="43c24-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="43c24-125">W tej sekcji przedstawiono różne ustawienia oraz dostępne wartości danych demonstracyjnych, które można wprowadzić, aby wykonać czynności wykonywane w scenariuszu na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="43c24-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="43c24-126">Konfigurowanie kodów dyrektyw</span><span class="sxs-lookup"><span data-stu-id="43c24-126">Set up directive codes</span></span>

<span data-ttu-id="43c24-127">[Kody dyrektyw](control-warehouse-location-directives.md) pozwalają na dokładniejsze określenie szablonu lokalizacji, który jest używany w szablonie pracy.</span><span class="sxs-lookup"><span data-stu-id="43c24-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="43c24-128">Każdy kod określa wspólną wartość, do której można się odwoływać podczas konfigurowania każdego typu szablonu.</span><span class="sxs-lookup"><span data-stu-id="43c24-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="43c24-129">Wyświetlanie i edytowanie kodów dyrektyw</span><span class="sxs-lookup"><span data-stu-id="43c24-129">View and edit directive codes</span></span>

<span data-ttu-id="43c24-130">Aby wyświetlić lub edytować kody dyrektyw, przejdź do **Zarządzanie magazynem \> Konfiguracja \> Kody dyrektyw**.</span><span class="sxs-lookup"><span data-stu-id="43c24-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="43c24-131">Przygotowywanie kodów dyrektyw w danych demonstracyjnych</span><span class="sxs-lookup"><span data-stu-id="43c24-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="43c24-132">W tym przykładzie przedstawiono sposób przygotowania kodu dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="43c24-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="43c24-133">Jeśli planowane jest korzystanie z scenariusza na końcu tego tematu, należy skorzystać z przedstawionych tu wartości danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="43c24-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="43c24-134">W przeciwnym razie należy skorzystać z własnych wartości.</span><span class="sxs-lookup"><span data-stu-id="43c24-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="43c24-135">Wybierz firmę **USMF** do pracy z danymi demonstracyjnymi.</span><span class="sxs-lookup"><span data-stu-id="43c24-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="43c24-136">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kody dyrektyw**.</span><span class="sxs-lookup"><span data-stu-id="43c24-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="43c24-137">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-138">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-139">**Kod dyrektywy:** _Uzupeł. stref._</span><span class="sxs-lookup"><span data-stu-id="43c24-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="43c24-140">**Opis dyrektywy:** _Uzupełnienie zapasów strefy_</span><span class="sxs-lookup"><span data-stu-id="43c24-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="43c24-141">Wybierz **Zapisz**, aby zapisać nowy kod.</span><span class="sxs-lookup"><span data-stu-id="43c24-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="43c24-142">Ustaw szablony uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="43c24-142">Set up replenishment templates</span></span>

<span data-ttu-id="43c24-143">[Szablony uzupełniania zapasów według ilości min./maks.](tasks/set-up-min-max-replenishment-process.md) są podstawowym mechanizmem utrzymywania optymalnego poziomu zapasów w lokalizacjach pobrania.</span><span class="sxs-lookup"><span data-stu-id="43c24-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="43c24-144">W tych szablonach należy skonfigurować reguły, które będą używane do uzupełniania zapasów w magazynie.</span><span class="sxs-lookup"><span data-stu-id="43c24-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="43c24-145">Uzupełnienie, do którego mogą być używane szablony, w tym uzupełnienie w oparciu o strefy.</span><span class="sxs-lookup"><span data-stu-id="43c24-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="43c24-146">Umożliwia wyświetlanie i edytowanie szablonów uzupełniania</span><span class="sxs-lookup"><span data-stu-id="43c24-146">View and edit replenishment templates</span></span>

<span data-ttu-id="43c24-147">Szablon uzupełniania zapasów jest zestawem reguł, które sterują tym, kiedy i jak zapasy są uzupełniane w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="43c24-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="43c24-148">Wybranie szablonu umożliwia kontrolowanie czasu i sposobu uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="43c24-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="43c24-149">Aby oglądać lub edytować szablony uzupełniania zapasów, wybierz **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="43c24-150">Przygotowywanie demonstracyjnego szablonu uzupełniania danych</span><span class="sxs-lookup"><span data-stu-id="43c24-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="43c24-151">W tym przykładzie przedstawiono sposób przygotowania szablonu uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="43c24-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="43c24-152">Jeśli planowane jest korzystanie z scenariusza na końcu tego tematu, należy skorzystać z przedstawionych tu wartości danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="43c24-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="43c24-153">W przeciwnym razie należy skorzystać z własnych wartości.</span><span class="sxs-lookup"><span data-stu-id="43c24-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="43c24-154">Wybierz firmę **USMF** do pracy z danymi demonstracyjnymi.</span><span class="sxs-lookup"><span data-stu-id="43c24-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="43c24-155">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="43c24-156">Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.</span><span class="sxs-lookup"><span data-stu-id="43c24-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="43c24-157">W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać nowy wiersz do siatki **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="43c24-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="43c24-158">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="43c24-158">In the new row, set the following values.</span></span> <span data-ttu-id="43c24-159">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="43c24-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="43c24-160">**Szablon uzupełnienia:** _strefa min./maks. uzupeł_</span><span class="sxs-lookup"><span data-stu-id="43c24-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="43c24-161">**Opis::** _Uzupełnienie zapasów strefy min./maks._</span><span class="sxs-lookup"><span data-stu-id="43c24-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="43c24-162">**Typ uzupełnienia:** _minimum lub maksimum_</span><span class="sxs-lookup"><span data-stu-id="43c24-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="43c24-163">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="43c24-163">Select **Save**.</span></span>
1. <span data-ttu-id="43c24-164">Gdy nowy wiersz jest nadal zaznaczony w siatce **Przeglądu**, wybierz opcję **Nowy** nad siatką **Szczegóły szablonu uzupełnienia**, aby dodać wiersz skojarzony z właśnie utworzonym szablonem uzupełnienia zapasów *strefy min./maks.*</span><span class="sxs-lookup"><span data-stu-id="43c24-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="43c24-165">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-166">**Numer sekwencyjny:** Wpisz _1_.</span><span class="sxs-lookup"><span data-stu-id="43c24-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="43c24-167">**Opis:** Wpisz _Wybierz uzupełnienie strefy_.</span><span class="sxs-lookup"><span data-stu-id="43c24-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="43c24-168">**Jednostka uzupełnienia:** Wybierz pozycję _ea_.</span><span class="sxs-lookup"><span data-stu-id="43c24-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="43c24-169">**Typ żądania:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="43c24-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="43c24-170">**Kod dyrektywy:** To pole łączy się z szablonem uzupełniania zapasów za pomocą dyrektywy lokalizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="43c24-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="43c24-171">Wybierz wcześniej utworzony demonstracyjny kod dyrektywy danych (_strefa uzupeł_).</span><span class="sxs-lookup"><span data-stu-id="43c24-171">Select the demo data directive code that you created earlier (_Zone replen_).</span></span>
    - <span data-ttu-id="43c24-172">**Szablon pracy:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="43c24-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="43c24-173">**Ilość minimalna:** W tym polu jest ustawiana ilość, jaka będzie wyzwalać uzupełnianie zapasów.</span><span class="sxs-lookup"><span data-stu-id="43c24-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="43c24-174">Wprowadź _50_.</span><span class="sxs-lookup"><span data-stu-id="43c24-174">Enter _50_.</span></span>
    - <span data-ttu-id="43c24-175">**Maksymalna ilość:** W tym polu jest ustawiana maksymalna ilość towaru, która może być obecna w strefie.</span><span class="sxs-lookup"><span data-stu-id="43c24-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="43c24-176">Wytworzona praca uzupełniająca spowoduje zwiększenie zapasów do tej ilości.</span><span class="sxs-lookup"><span data-stu-id="43c24-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="43c24-177">Wprowadź _150_.</span><span class="sxs-lookup"><span data-stu-id="43c24-177">Enter _150_.</span></span>
    - <span data-ttu-id="43c24-178">**Jednostka:** W tym polu jest ustawiana jednostka dla wartości minimalnej i maksymalnej.</span><span class="sxs-lookup"><span data-stu-id="43c24-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="43c24-179">Wybierz _ea_.</span><span class="sxs-lookup"><span data-stu-id="43c24-179">Select _ea_.</span></span>
    - <span data-ttu-id="43c24-180">**Przyrost popytu:** Wybierz opcję _Zaokrąglaj w górę_.</span><span class="sxs-lookup"><span data-stu-id="43c24-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="43c24-181">Zaznacz pole wyboru **Uzupełnij zapasy w pustych stałych lokalizacjach**.</span><span class="sxs-lookup"><span data-stu-id="43c24-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="43c24-182">Zaznacz pole wyboru **Uzupełniaj tylko stałe lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="43c24-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-183">**Tryb zapytania o produkt:** Wybierz _Zapytanie o produkt_.</span><span class="sxs-lookup"><span data-stu-id="43c24-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="43c24-184">**Zakres progu uzupełnienia zapasów:** to pole określa, czy szablon powinien oceniać według strefy, czy według konkretnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="43c24-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="43c24-185">Wybierz opcję _Strefa_.</span><span class="sxs-lookup"><span data-stu-id="43c24-185">Select _Zone_.</span></span>
    - <span data-ttu-id="43c24-186">**Magazyn:** Wybierz _61_.</span><span class="sxs-lookup"><span data-stu-id="43c24-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="43c24-187">Wybierz opcję **Wybierz produkty** powyżej siatki **Szczegóły szablonu uzupełnienia zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="43c24-188">W polu dialogowym **Zapytanie dot. produktu**, na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-189">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-190">**Tabela:** _pozycje_</span><span class="sxs-lookup"><span data-stu-id="43c24-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="43c24-191">**Tabela pochodna:** _pozycje_</span><span class="sxs-lookup"><span data-stu-id="43c24-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="43c24-192">**Pole:** _numer pozycji_</span><span class="sxs-lookup"><span data-stu-id="43c24-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="43c24-193">**Kryteria:** _A0001_</span><span class="sxs-lookup"><span data-stu-id="43c24-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="43c24-194">Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="43c24-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="43c24-195">Wybierz opcję **Wybierz strefy do uzupełnienia** powyżej siatki **Szczegóły szablonu uzupełnienia zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="43c24-196">W polu dialogowym **Zapytanie dot. strefy**, na karcie **Zakres**, dodaj wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-197">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-198">**Tabela:** _strefa magazynowa_</span><span class="sxs-lookup"><span data-stu-id="43c24-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="43c24-199">**Tabela pochodna:** _strefa magazynowa_</span><span class="sxs-lookup"><span data-stu-id="43c24-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="43c24-200">**Pole:** _Identyfikator strefy_</span><span class="sxs-lookup"><span data-stu-id="43c24-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="43c24-201">**Kryteria:** _FLOOR_</span><span class="sxs-lookup"><span data-stu-id="43c24-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="43c24-202">Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="43c24-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="43c24-203">Ustaw dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="43c24-203">Set up location directives</span></span>

<span data-ttu-id="43c24-204">W przeciwieństwie do minimalnych/maksymalnych uzupełnień na podstawie lokalizacji, min./maks. uzupełnienie strefy wymaga skonfigurowania dyrektyw lokalizacji pobrania i lokalizacji odłożenia, ponieważ system ocenia całą strefę, a nie tylko lokalizację pobrania dla pracy wychodzącej.</span><span class="sxs-lookup"><span data-stu-id="43c24-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="43c24-205">Przeglądanie i edytowanie dyrektyw lokalizacji</span><span class="sxs-lookup"><span data-stu-id="43c24-205">View and edit location directives</span></span>

<span data-ttu-id="43c24-206">Aby wyświetlić lub edytować dyrektywy lokalizacji, przejdź do **Zarządzania magazynem \> Konfiguracja \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="43c24-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="43c24-207">Aby zapoznać się z przykładami, w których można skorzystać z ustawień w celu utworzenia wymaganej dyrektywy dotyczącej pobrania i dyrektyw lokalizacji, należy zapoznać się z następną sekcją.</span><span class="sxs-lookup"><span data-stu-id="43c24-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="43c24-208">Przygotowywanie danych demonstracyjnych dyrektyw lokalizacji</span><span class="sxs-lookup"><span data-stu-id="43c24-208">Prepare demo data location directives</span></span>

<span data-ttu-id="43c24-209">Aby przygotować dane demonstracyjne do użycia w scenariuszu na końcu tego tematu, należy utworzyć dwie dyrektywy lokalizacji: jedną do pobrania i jedną do umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="43c24-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="43c24-210">Tworzenie dyrektywy pobierania uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="43c24-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="43c24-211">Wybierz firmę **USMF** do pracy z danymi demonstracyjnymi.</span><span class="sxs-lookup"><span data-stu-id="43c24-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="43c24-212">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="43c24-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="43c24-213">W lewym okienku w polu **Typ zlecenia produkcyjnego** ustaw wartość na _uzupełnienie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="43c24-214">W okienku akcji wybierz opcję **Nowa**, aby utworzyć nową dyrektywę.</span><span class="sxs-lookup"><span data-stu-id="43c24-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="43c24-215">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-215">Set the following values:</span></span>

    - <span data-ttu-id="43c24-216">**Numer sekwencyjny:** Zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="43c24-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="43c24-217">**Nazwa:** Wprowadź _pobranie w strefie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="43c24-218">**Typ pracy:** Wybierz _Pobranie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="43c24-219">**Placówka:** Wybierz _6_.</span><span class="sxs-lookup"><span data-stu-id="43c24-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="43c24-220">**Magazyn:** Wybierz _61_.</span><span class="sxs-lookup"><span data-stu-id="43c24-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="43c24-221">Pole **Kod dyrektywy:** należy pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="43c24-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="43c24-222">**Wiele jednostek SKU:** ustaw tą wartość na _Nie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="43c24-223">Wybierz opcję **Zapisz**, aby utworzyć dyrektywę, w której skonfigurowano dotychczasowe ustawienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="43c24-224">Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="43c24-225">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="43c24-226">**Numer sekwencyjny:** Wpisz _1_.</span><span class="sxs-lookup"><span data-stu-id="43c24-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="43c24-227">**Ilość od:** Podaj _0_.</span><span class="sxs-lookup"><span data-stu-id="43c24-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="43c24-228">**Ilość do:** Podaj _10000000_.</span><span class="sxs-lookup"><span data-stu-id="43c24-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="43c24-229">**Jednostka:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="43c24-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="43c24-230">**Znajdź ilość:** Wybierz opcję _Brak_.</span><span class="sxs-lookup"><span data-stu-id="43c24-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="43c24-231">Zaznacz lub wyczyść pole wyboru **Ogranicz według jednostki:**.</span><span class="sxs-lookup"><span data-stu-id="43c24-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-232">**Zaokrąglaj w górę do jednostki:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-233">**Znajdź ilość opakowań:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-234">Zaznacz pole wyboru **Zezwalaj na podział:**.</span><span class="sxs-lookup"><span data-stu-id="43c24-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="43c24-235">Wybierz **Zapisz**, aby zapisać nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="43c24-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="43c24-236">Gdy nowy wiersz jest wciąż zaznaczony w siatce **Wiersze**, wybierz opcję **Nowy** w skróconej karcie **Działania dyrektywy lokalizacji**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-237">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-238">**Numer sekwencyjny:** Wpisz _1_.</span><span class="sxs-lookup"><span data-stu-id="43c24-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="43c24-239">**Nazwa:** Wprowadź _pobranie z partii_.</span><span class="sxs-lookup"><span data-stu-id="43c24-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="43c24-240">**Stałe użycie lokalizacji:** Wybierz _Stałe i niestałe lokalizacje_.</span><span class="sxs-lookup"><span data-stu-id="43c24-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="43c24-241">**Zezwalaj na ujemne zapasy:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-242">**Partia włączona:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-243">**Strategia:** Wybierz opcję _Brak_.</span><span class="sxs-lookup"><span data-stu-id="43c24-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="43c24-244">Wybierz **Zapisz**, aby zapisać nowe działanie.</span><span class="sxs-lookup"><span data-stu-id="43c24-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="43c24-245">Podczas gdy nowa akcja jest wciąż zaznaczona, wybierz polecenie **Edytuj zapytanie** powyżej siatki **Działania dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="43c24-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="43c24-246">Zostanie wyświetlone okno dialogowe zapytania, w którym można wybrać lokalizacje, z których będą wykonywane uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="43c24-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="43c24-247">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-248">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-249">**Tabela:** _Lokalizacje_</span><span class="sxs-lookup"><span data-stu-id="43c24-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="43c24-250">**Tabela pochodna:** _Lokalizacje_</span><span class="sxs-lookup"><span data-stu-id="43c24-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="43c24-251">**Pole:** _Identyfikator strefy_</span><span class="sxs-lookup"><span data-stu-id="43c24-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="43c24-252">**Kryteria:** _BULK_</span><span class="sxs-lookup"><span data-stu-id="43c24-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="43c24-253">Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="43c24-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="43c24-254">Wybierz **Zapisz**, by zapisać dyrektywę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="43c24-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="43c24-255">Tworzenie dyrektywy odkładania uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="43c24-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="43c24-256">Na stronie **Dyrektywy lokalizacji** w lewym okienku upewnij się, że pole **Typ zlecenia pracy** jest nadal ustawiony na _uzupełnienie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="43c24-257">W okienku akcji wybierz opcję **Nowa**, aby utworzyć kolejną dyrektywę.</span><span class="sxs-lookup"><span data-stu-id="43c24-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="43c24-258">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-258">Set the following values:</span></span>

    - <span data-ttu-id="43c24-259">**Numer sekwencyjny:** Zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="43c24-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="43c24-260">**Nazwa:** Wprowadź _oddanie w strefie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="43c24-261">**Typ zlecenia pracy:** Wybierz opcję _Odłóż_.</span><span class="sxs-lookup"><span data-stu-id="43c24-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="43c24-262">**Placówka:** Wybierz _6_.</span><span class="sxs-lookup"><span data-stu-id="43c24-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="43c24-263">**Magazyn:** Wybierz _61_.</span><span class="sxs-lookup"><span data-stu-id="43c24-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="43c24-264">**Kod dyrektywy:** Wybierz _strefa uzupełnień_, aby połączyć tę dyrektywę lokalizacji z szablonem uzupełnienia, który został utworzony wcześniej, przy użyciu utworzonego wcześniej kodu.</span><span class="sxs-lookup"><span data-stu-id="43c24-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="43c24-265">**Wiele jednostek SKU:** ustaw tą wartość na _Nie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="43c24-266">Wybierz opcję **Zapisz**, aby utworzyć dyrektywę, w której skonfigurowano dotychczasowe ustawienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="43c24-267">Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="43c24-268">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="43c24-269">**Numer sekwencyjny:** Wpisz _1_.</span><span class="sxs-lookup"><span data-stu-id="43c24-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="43c24-270">**Ilość od:** Podaj _0_.</span><span class="sxs-lookup"><span data-stu-id="43c24-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="43c24-271">**Ilość do:** Podaj _10000000_.</span><span class="sxs-lookup"><span data-stu-id="43c24-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="43c24-272">**Jednostka:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="43c24-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="43c24-273">**Znajdź ilość:** Wybierz opcję _Brak_.</span><span class="sxs-lookup"><span data-stu-id="43c24-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="43c24-274">Zaznacz lub wyczyść pole wyboru **Ogranicz według jednostki:**.</span><span class="sxs-lookup"><span data-stu-id="43c24-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-275">**Zaokrąglaj w górę do jednostki:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-276">**Znajdź ilość opakowań:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-277">Zaznacz pole wyboru **Zezwalaj na podział:**.</span><span class="sxs-lookup"><span data-stu-id="43c24-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="43c24-278">Wybierz **Zapisz**, aby zapisać nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="43c24-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="43c24-279">Gdy nowy wiersz jest wciąż zaznaczony w siatce **Wiersze**, wybierz opcję **Nowy** w skróconej karcie **Działania dyrektywy lokalizacji**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-280">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-281">**Numer sekwencyjny:** Wpisz _1_.</span><span class="sxs-lookup"><span data-stu-id="43c24-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="43c24-282">**Nazwa:** Wprowadź _oddanie w strefie_.</span><span class="sxs-lookup"><span data-stu-id="43c24-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="43c24-283">**Stałe użycie lokalizacji:** Wybierz _Stałe i niestałe lokalizacje_.</span><span class="sxs-lookup"><span data-stu-id="43c24-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="43c24-284">**Zezwalaj na ujemne zapasy:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-285">**Partia włączona:** Wyczyść to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="43c24-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="43c24-286">**Strategia:** Wybierz _Konsolidacja_.</span><span class="sxs-lookup"><span data-stu-id="43c24-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="43c24-287">Wybierz **Zapisz**, aby zapisać nowe działanie.</span><span class="sxs-lookup"><span data-stu-id="43c24-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="43c24-288">Podczas gdy nowa akcja jest wciąż zaznaczona, wybierz polecenie **Edytuj zapytanie** powyżej siatki **Działania dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="43c24-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="43c24-289">Zostanie wyświetlone okno dialogowe zapytania, w którym można wybrać lokalizację do uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="43c24-290">To powinna być ta sama strefa, która jest określona w szablonie uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="43c24-291">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="43c24-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="43c24-292">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="43c24-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="43c24-293">**Tabela:** _Lokalizacje_</span><span class="sxs-lookup"><span data-stu-id="43c24-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="43c24-294">**Tabela pochodna:** _Lokalizacje_</span><span class="sxs-lookup"><span data-stu-id="43c24-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="43c24-295">**Pole:** _Identyfikator strefy_</span><span class="sxs-lookup"><span data-stu-id="43c24-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="43c24-296">**Kryteria:** _FLOOR_</span><span class="sxs-lookup"><span data-stu-id="43c24-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="43c24-297">Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="43c24-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="43c24-298">Wybierz **Zapisz**, by zapisać dyrektywę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="43c24-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="43c24-299">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="43c24-299">Scenario</span></span>

<span data-ttu-id="43c24-300">Ta sekcja zawiera przykładowy scenariusz przedstawiający sposób pracy z tą funkcją.</span><span class="sxs-lookup"><span data-stu-id="43c24-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="43c24-301">Przygotuj przykładowe dane wymagane dla scenariusza z przykładu</span><span class="sxs-lookup"><span data-stu-id="43c24-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="43c24-302">Przed rozpoczęciem pracy nad scenariuszem należy aktywować przykładowe dane i skonfigurować funkcję zgodnie z opisem w tej sekcji i w poprzednich sekcjach tego tematu.</span><span class="sxs-lookup"><span data-stu-id="43c24-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="43c24-303">Użyj firmy USMF</span><span class="sxs-lookup"><span data-stu-id="43c24-303">Use the USMF legal entity</span></span>

<span data-ttu-id="43c24-304">Aby pracować z tymi scenariuszami przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="43c24-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="43c24-305">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="43c24-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="43c24-306">Przygotowywanie dodatkowych przykładowych danych</span><span class="sxs-lookup"><span data-stu-id="43c24-306">Prepare additional sample data</span></span>

<span data-ttu-id="43c24-307">Po wybraniu firmy **USMF** dodaj dodatkowe przykładowe dane, które są wymagane, zgodnie z opisem w sekcji [konfiguracji uzupełnienia w strefie](#setup), opisanej wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="43c24-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="43c24-308">Sprawdzanie dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="43c24-308">Check your on-hand inventory</span></span>

<span data-ttu-id="43c24-309">Należy wykonać poniższe kroki, aby upewnić się, że w systemie znajduje się wystarczająca ilość zapasów do obsługi scenariusza przykładowego.</span><span class="sxs-lookup"><span data-stu-id="43c24-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="43c24-310">Upewnij się, że istnieją dostępne zapasy dla pozycji *A0001* w dwóch różnych lokalizacjach w strefie pobrania (*FLOOR*), które są określone w szablonie uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="43c24-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone (*FLOOR*) that is specified in the replenishment template.</span></span> <span data-ttu-id="43c24-311">Jednak suma zapasów powinna być mniejsza niż wymagana ilość minimalna (*50*), która jest określona w szablonie uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-311">However, the total inventory should be less than the required minimum quantity (*50*) that is specified on the replenishment template.</span></span> <span data-ttu-id="43c24-312">W ten sposób można symulować sposób obliczania w całej strefie, a nie tylko dla jednej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="43c24-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="43c24-313">**Korzystaj z dowolnego procesu magazynowego, aby skorygować zapasy**.</span><span class="sxs-lookup"><span data-stu-id="43c24-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="43c24-314">Upewnij się, że istnieje wystarczająca ilość zapasów dla pozycji *A0001* w lokalizacji zbiorczej określonej w dyrektywie pobrania strefy, w której praca uzupełniająca powinna pobierać towary ze strefy o identyfikatorze *BULK*.</span><span class="sxs-lookup"><span data-stu-id="43c24-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="43c24-315">Suma zapasów powinna być większa niż wymagana ilość maksymalna (*150*), która jest określona w szablonie uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="43c24-315">The total inventory must be more than the required maximum quantity (*150*) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="43c24-316">Opcjonalne, ale zalecane: Aby utworzyć arkusz korekt zapasów, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="43c24-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="43c24-317">Kliknij kolejno opcje **Zarządzanie zapasami \> Wpisy w arkuszu \> Towary \> Korekta zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="43c24-318">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="43c24-318">Select **New**.</span></span>
    1. <span data-ttu-id="43c24-319">W oknie dialogowym **Tworzenie arkusza magazynowego** w polu **Magazyn** wybierz pozycję *61*.</span><span class="sxs-lookup"><span data-stu-id="43c24-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="43c24-320">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43c24-320">Select **OK**.</span></span>
    1. <span data-ttu-id="43c24-321">Na skróconej karcie **Wiersze arkusza** użyj przycisku **Nowe**, aby dodać trzy wiersze do siatki, należy określić następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="43c24-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="43c24-322">Po zakończeniu konfigurowania każdego wiersza wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="43c24-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="43c24-323">**Wiersz 1:**</span><span class="sxs-lookup"><span data-stu-id="43c24-323">**Line 1:**</span></span>

            - <span data-ttu-id="43c24-324">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="43c24-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="43c24-325">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="43c24-325">**Site:** *6*</span></span>
            - <span data-ttu-id="43c24-326">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="43c24-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="43c24-327">**Lokalizacja:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="43c24-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="43c24-328">**Numer identyfikacyjny:** Wybierz istniejący numer identyfikacyjny na liście lub Utwórz nowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="43c24-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="43c24-329">**Ilość:** *1000*</span><span class="sxs-lookup"><span data-stu-id="43c24-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="43c24-330">**Wiersz 2:**</span><span class="sxs-lookup"><span data-stu-id="43c24-330">**Line 2:**</span></span>

            - <span data-ttu-id="43c24-331">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="43c24-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="43c24-332">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="43c24-332">**Site:** *6*</span></span>
            - <span data-ttu-id="43c24-333">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="43c24-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="43c24-334">**Lokalizacja:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="43c24-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="43c24-335">**Numer identyfikacyjny:** Wybierz istniejący numer identyfikacyjny na liście lub Utwórz nowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="43c24-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="43c24-336">**Ilość:** *15*</span><span class="sxs-lookup"><span data-stu-id="43c24-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="43c24-337">**Wiersz 3:**</span><span class="sxs-lookup"><span data-stu-id="43c24-337">**Line 3:**</span></span>

            - <span data-ttu-id="43c24-338">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="43c24-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="43c24-339">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="43c24-339">**Site:** *6*</span></span>
            - <span data-ttu-id="43c24-340">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="43c24-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="43c24-341">**Lokalizacja:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="43c24-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="43c24-342">**Numer identyfikacyjny:** Wybierz istniejący numer identyfikacyjny na liście lub Utwórz nowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="43c24-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="43c24-343">**Ilość:** *10*</span><span class="sxs-lookup"><span data-stu-id="43c24-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="43c24-344">W okienku akcji wybierz pozycję **Weryfikacja**.</span><span class="sxs-lookup"><span data-stu-id="43c24-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="43c24-345">Rozwiąż wszelkie znalezione błędy przed przejściem do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="43c24-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="43c24-346">W okienku akcji wybierz opcję **Księguj**, aby zaksięgować zapasy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="43c24-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="43c24-347">Przykładowy scenariusz: Uruchom min./maks. uzupełnienie na podstawie strefy</span><span class="sxs-lookup"><span data-stu-id="43c24-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="43c24-348">Po ustawieniu wszystkich przykładowych danych dotyczących wymagań wstępnych można uruchomić uzupełnianie, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="43c24-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="43c24-349">Wybierz kolejno opcje **Zarządzanie magazynem \> Uzupełnienie \> Uzupełnienia zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="43c24-350">W oknie dialogowym **Uzupełnianie** w skróconej karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="43c24-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="43c24-351">W oknie dialogowym **Informacje** na karcie **Zakres** dokonaj edycji domyślnego wiersza tabeli w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="43c24-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="43c24-352">**Tabela:** Wybierz _Szablony uzupełniania zapasów_.</span><span class="sxs-lookup"><span data-stu-id="43c24-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="43c24-353">**Tabela pochodna:** Wybierz _Szablony uzupełniania zapasów_.</span><span class="sxs-lookup"><span data-stu-id="43c24-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="43c24-354">**Pole:** Wybierz _Szablon uzupełniania zapasów_.</span><span class="sxs-lookup"><span data-stu-id="43c24-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="43c24-355">**Kryteria:** Wybierz _min./maks. wartość strefy uzupeł_.</span><span class="sxs-lookup"><span data-stu-id="43c24-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="43c24-356">Ten szablon uzupełnienia zapasów jest szablonem utworzonym podczas przygotowywania danych demonstracyjnych tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="43c24-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="43c24-357">Wybierz **OK**, zapisać zapytanie i cofnąć się do oka dialogowego **Uzupełnianie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="43c24-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="43c24-358">Wybierz **OK**, aby uruchomić szablon uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="43c24-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="43c24-359">Zlecenie uzupełniania zapasów jest teraz tworzone, aby pobierać zapasy ze strefy *BULK* i odnawiać je w strefie *FLOOR*.</span><span class="sxs-lookup"><span data-stu-id="43c24-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="43c24-360">Notatki i porady</span><span class="sxs-lookup"><span data-stu-id="43c24-360">Notes and tips</span></span>

<span data-ttu-id="43c24-361">Oto kilka uwag i porad dotyczących pracy z tą funkcją:</span><span class="sxs-lookup"><span data-stu-id="43c24-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="43c24-362">Aby skonfigurować pracę uzupełniania zapasów, która przechodzi do żądanej strefy, można połączyć wiersze szablonu uzupełnienia i dyrektywy lokalizacji, korzystając z jednej z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="43c24-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="43c24-363">Edytowanie kwerendy nagłówka dyrektywy lokalizacji i filtrowanie wybranych wierszy szablonu uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="43c24-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="43c24-364">Użycia kodu dyrektywy w wierszu szablonu uzupełniania zapasów oraz sparowania go z dyrektywą lokalizacji odłożenia.</span><span class="sxs-lookup"><span data-stu-id="43c24-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="43c24-365">Jeśli są używane lokalizacje dynamiczne, praca uzupełniająca zostanie utworzona dla pierwszej dostępnej lokalizacji lub dla lokalizacji, która już zawiera zapasy, jeśli dla akcji dyrektywy lokalizacji skonfigurowano stosowanie strategii **Konsolidacja**.</span><span class="sxs-lookup"><span data-stu-id="43c24-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="43c24-366">Jeśli są używane stałe lokalizacje, a nie strefy, należy użyć [standardowego minimalnego/maksymalnego uzupełnienia zapasów](tasks/set-up-min-max-replenishment-process.md).</span><span class="sxs-lookup"><span data-stu-id="43c24-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]