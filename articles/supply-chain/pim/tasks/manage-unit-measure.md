---
title: Zarządzanie jednostkami miary
description: W tym temacie opisano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921348"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="d8e7f-103">Zarządzanie jednostkami miary</span><span class="sxs-lookup"><span data-stu-id="d8e7f-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d8e7f-104">W tym temacie opisano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="d8e7f-105">Otwieranie strony Jednostki</span><span class="sxs-lookup"><span data-stu-id="d8e7f-105">Open the Units page</span></span>

<span data-ttu-id="d8e7f-106">Aby utworzyć jednostki miary dostępne w systemie i pracować z nich, przejdź do **Administrowanie organizacją \> Konfiguracja \> Jednostki \> Jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="d8e7f-107">Pozostałe sekcje tego tematu zawierają opis tego, co można zrobić na stronie **Jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="d8e7f-108">Tworzenie standardowych jednostek i konwersji</span><span class="sxs-lookup"><span data-stu-id="d8e7f-108">Create standard units and conversions</span></span>

<span data-ttu-id="d8e7f-109">Jeśli w systemie nie są jeszcze najczęściej używane jednostki miary w systemie metrycznym i/lub amerykańskim systemie niestandardowym (USCS), kreator konfiguracji jednostek pomoże szybko skonfigurować podstawowe definicje jednostek i konwersje.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="d8e7f-110">Aby wykonać kreator, wybierz opcję **Kreator tworzenia jednostek** w okienku akcji, a następnie postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="d8e7f-111">Tworzenie lub edytowanie jednostki miary</span><span class="sxs-lookup"><span data-stu-id="d8e7f-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="d8e7f-112">Aby utworzyć lub edytować jednostkę miary, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="d8e7f-113">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="d8e7f-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="d8e7f-114">Aby zmodyfikować istniejącą jednostkę, zaznacz ją w okienku listy.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="d8e7f-115">Aby utworzyć nową jednostkę, wybierz **Nowa** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="d8e7f-116">W nagłówku rekordu określ następujące pola:</span><span class="sxs-lookup"><span data-stu-id="d8e7f-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="d8e7f-117">**Jednostka** — umożliwia wprowadzenie identyfikatora lub symbolu odwołującego się do jednostki w wersji językowej systemu.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="d8e7f-118">Ten identyfikator lub symbol jest zazwyczaj wspólnym skrótem jednostki, takim jak *szt* jako sztuka lub *cm* jako centymetr.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="d8e7f-119">**Opis** — Wprowadź opisową nazwę jednostki w wersji językowej systemu.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="d8e7f-120">Jest to zazwyczaj pełna nazwa jednostki, np. *Sztuka* lub *Centymetr*.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="d8e7f-121">Na skróconej karcie **Ogólne** ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="d8e7f-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="d8e7f-122">**Klasa jednostek** — umożliwia wybór właściwości miary jednostki (np. długość, obszar, masa lub ilość).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="d8e7f-123">**System jednostek** — umożliwia wybór systemu miar, do którego należy jednostka (*jednostki metryczne* lub *tradycyjne jednostki w Stanach Zjednoczonych*).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="d8e7f-124">**Jednostka podstawowa** — ta opcja ma wartość *Tak*, jeśli bieżąca jednostka ma być jednostką podstawową w klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="d8e7f-125">W takim przypadku wystarczy określić współczynnik konwersji między jednostką podstawową a każdą dodatkową jednostką w klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="d8e7f-126">System może następnie konwertować między wszystkimi jednostkami w tej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="d8e7f-127">Wtedy ustawianie konwersji jest łatwiejsze.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="d8e7f-128">Jeśli na przykład galon jest jednostką podstawową dla klasy jednostek *objętości*, należy skonfigurować tylko współczynniki konwersji z litrów na galon oraz z pinty na galon.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="d8e7f-129">System może następnie konwertować z litra na pintę.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="d8e7f-130">Można mieć tylko jedną jednostkę podstawową w danej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="d8e7f-131">**Jednostka systemowa** — ta opcja ma wartość *Tak*, jeśli bieżąca jednostka ma być domyślną jednostką wszystkich miar bez określenia jednostki w danej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="d8e7f-132">Jeśli na przykład pole używane do wprowadzania ilości nie zezwala na podanie jednostki (lub gdy użytkownik nie wybierze jednostki), system użyje jednostki ustawionej jako jednostka systemowa dla klasy jednostek *Ilość*.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="d8e7f-133">Można mieć tylko jedną jednostkę systemową w danej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="d8e7f-134">**Dokładność dziesiętna** — umożliwia określenie liczby miejsc dziesiętnych, do których powinny być zaokrąglane wartości określone w bieżącej jednostce lub przeliczone na nią.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="d8e7f-135">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="d8e7f-136">Definiowanie tłumaczeń jednostek</span><span class="sxs-lookup"><span data-stu-id="d8e7f-136">Define unit translations</span></span>

<span data-ttu-id="d8e7f-137">Aby zdefiniować tłumaczenia identyfikatora lub symbolu oraz opisu jednostki miary, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="d8e7f-138">Utwórz lub wybierz jednostkę, której tłumaczenia chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="d8e7f-139">W okienku akcji wybierz opcję **Teksty jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="d8e7f-140">Zostanie wyświetlona strona **Teksty jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="d8e7f-141">Ta strona służy do definiowania tłumaczeń identyfikatora lub symbolu wybranej jednostki.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="d8e7f-142">Tłumaczenia te mogą być następnie używane w dokumentach zewnętrznych w językach specyficznych dla odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="d8e7f-143">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d8e7f-144">W polu **Język** wybierz język, na który będzie przetłumaczony identyfikator lub symbol jednostki.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="d8e7f-145">W polu **Tekst** wprowadź tłumaczenie identyfikatora lub symbolu jednostki na wybrany język.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="d8e7f-146">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="d8e7f-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-147">Close the page.</span></span>
1. <span data-ttu-id="d8e7f-148">W **okienku akcji** kliknij pozycję **Przetłumaczone opisy jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="d8e7f-149">Zostanie wyświetlona strona **Przetłumaczone opisy jednostki**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="d8e7f-150">Ta strona służy do definiowania opisów w określonym języku dla wybranej jednostki.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="d8e7f-151">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d8e7f-152">W polu **Język** wybierz język, na który będzie przetłumaczony opis jednostki.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="d8e7f-153">W polu **Opis** wprowadź tłumaczenie opisu jednostki na wybrany język.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="d8e7f-154">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="d8e7f-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="d8e7f-156">Definiowanie reguł konwersji jednostek</span><span class="sxs-lookup"><span data-stu-id="d8e7f-156">Define unit conversion rules</span></span>

<span data-ttu-id="d8e7f-157">Aby zdefiniować reguły konwersji między jednostkami miary, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="d8e7f-158">Utwórz lub wybierz jednostkę, której reguły konwersji definiujesz.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="d8e7f-159">W okienku akcji wybierz opcję **Konwersje jednostek**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="d8e7f-160">Zostanie otwarta strona **Konwersje jednostek**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="d8e7f-161">Na tej stronie możesz zdefiniować reguły konwersji wybranej jednostki na i z innych jednostek w tej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="d8e7f-162">W zależności od typu konwersji, którą chcesz skonfigurować, wybierz jedną z następujących kart:</span><span class="sxs-lookup"><span data-stu-id="d8e7f-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="d8e7f-163">**Standardowe konwersje** – Konfigurowanie standardowych reguł konwersji dla wszystkich produktów.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="d8e7f-164">**Konwersje wewnątrz klasy** – Konfigurowanie specyficznych dla produktu reguł konwersji jednostek w tej samej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="d8e7f-165">**Konwersje między klasami** – Konfigurowanie specyficznych dla produktu reguł konwersji jednostek między klasami jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="d8e7f-166">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="d8e7f-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="d8e7f-167">Aby utworzyć nową konwersję, wybierz **Nowa** na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="d8e7f-168">Aby edytować istniejącą konwersję, zaznacz konwersję w siatce, a następnie wybierz pozycję **Edytuj** na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="d8e7f-169">W wyświetlonym oknie dialogowym listy rozwijanej można ustawić następujące pola:</span><span class="sxs-lookup"><span data-stu-id="d8e7f-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="d8e7f-170">**Produkt** — wybierz określony produkt, do którego odnosi się konwersja.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="d8e7f-171">To pole jest dostępne tylko w przypadku konwersji wewnątrz klasy i między klasami.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="d8e7f-172">**Układ formuły** – Aby określić prostą konwersję z jednym współczynnikiem, należy pozostawić wartość *Prosta* w tym polu.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="d8e7f-173">Ustaw w nim wartość *Zaawansowane*, jeśli chcesz skonfigurować bardziej złożone równanie.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="d8e7f-174">Format równań zaawansowanych zmienia się w zależności od klasy jednostek.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="d8e7f-175">**Z jednostki** — w tym polu jest wyświetlana wybrana jednostka.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="d8e7f-176">Zwykle nie należy zmieniać tej wartości.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-176">Usually, you should not change the value.</span></span> <span data-ttu-id="d8e7f-177">(W przypadku zmiany tej wartości należy otworzyć stronę **Konwersje jednostek** dla wybranej jednostki, aby wyświetlić nową konwersję po jej zapisaniu).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="d8e7f-178">**Na jednostkę** — wybierz jednostkę docelową konwersji.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="d8e7f-179">**Zaokrąglanie** — umożliwia wybór sposobu zaokrąglania ułamków na podstawie wartości **dokładności dziesiętnej** wybranej jednostki (*Do najbliższej*, *W górę* lub *W dół*).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="d8e7f-180">**Formuła konwersji** — Pozostałe pola w górnej części okna dialogowego służą do określenia formuły konwersji między tymi dwiema jednostkami.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="d8e7f-181">Dostępne pola różnią się w zależności od wybranej klasy jednostki i wybranego układu formuły.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="d8e7f-182">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-182">Select **OK**.</span></span>
1. <span data-ttu-id="d8e7f-183">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="d8e7f-184">Można także skonfigurować konwersje jednostek zależnie od wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="d8e7f-185">Więcej informacji zawiera temat [Przeliczanie jednostki miary dla wariantów produktów](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
