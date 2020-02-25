---
title: Praca z układami predefiniowanymi
description: W tym temacie opisano, jak pracować z układami predefiniowanymi w Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c8149c6e443c77dabfa641a698c931176bedbc98
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002643"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="a5e70-103">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="a5e70-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a5e70-104">W tym temacie opisano, jak pracować z układami predefiniowanymi w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5e70-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a5e70-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a5e70-105">Overview</span></span>

<span data-ttu-id="a5e70-106">Przed wykonaniem procedur opisanych w tym temacie należy koniecznie przeczytać [Układ predefiniowany i niestandardowy](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="a5e70-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="a5e70-107">Aby zapoznać się z ogólnym omówieniem, zajrzyj do [Omówienie szablonów i układów](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5e70-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="a5e70-108">Tworzenie nowego układu predefiniowanego</span><span class="sxs-lookup"><span data-stu-id="a5e70-108">Create a new preset layout</span></span>

<span data-ttu-id="a5e70-109">Są dwie metody tworzenia predefiniowanego układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="a5e70-110">Istniejący układ niestandardowy można zapisać jako nowy układ predefiniowany lub można utworzyć predefiniowany układ od podstaw.</span><span class="sxs-lookup"><span data-stu-id="a5e70-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="a5e70-111">Tworzenie predefiniowanego układu na podstawie istniejącego układu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="a5e70-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="a5e70-112">Aby utworzyć układ predefiniowany z istniejącego układu niestandardowego, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5e70-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="a5e70-113">Umożliwia otwarcie istniejącej strony, w której obecnie nie jest używany układ predefiniowany, a także strukturę modułu, której użytkownik chce użyć do ponownego użycia w odniesieniu do innych stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="a5e70-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="a5e70-114">Wybierz **Wyewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-114">Select **Check out**.</span></span>
1. <span data-ttu-id="a5e70-115">Wybierz **Zapisz jako nowy układ**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-115">Select **Save as new layout**.</span></span> <span data-ttu-id="a5e70-116">Zostanie wyświetlone okno dialogowe **Zapisz jako nowy układ**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="a5e70-117">Wprowadź nazwę i opis predefiniowanego układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="a5e70-118">Wprowadzone wartości będą widoczne dla innych autorów, tworząc nowe strony z układu lub przełączając do niego.</span><span class="sxs-lookup"><span data-stu-id="a5e70-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="a5e70-119">Dlatego należy wprowadzić wartości, które będą przydatne autorom stron.</span><span class="sxs-lookup"><span data-stu-id="a5e70-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="a5e70-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-120">Select **OK**.</span></span>

<span data-ttu-id="a5e70-121">Układ predefiniowany będzie teraz dostępny w przypadku tworzenia nowych stron lub wybrania innego układu strony w tej samej hierarchii szablonów.</span><span class="sxs-lookup"><span data-stu-id="a5e70-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="a5e70-122">Aby szybko sprawdzić, czy konkretna strona jest aktualnie powiązana z ustawionym układem, wybierz stronę w widoku listy stron i sprawdź metadane układu w panelu właściwości po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="a5e70-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="a5e70-123">Tworzenie nowego układu predefiniowanego</span><span class="sxs-lookup"><span data-stu-id="a5e70-123">Create a new preset layout</span></span>

<span data-ttu-id="a5e70-124">Aby utworzyć układ predefiniowany od zera, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5e70-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="a5e70-125">W okienku nawigacji po lewej stronie zaznacz **Układy**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="a5e70-126">Wybierz **Nowy układ**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-126">Select **New Layout**.</span></span> <span data-ttu-id="a5e70-127">Zostanie wyświetlone okno dialogowe **Nowy układ**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="a5e70-128">Wybierz szablon, który ma być używany w układzie predefiniowanym.</span><span class="sxs-lookup"><span data-stu-id="a5e70-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="a5e70-129">Wprowadź nazwę i opis predefiniowanego układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="a5e70-130">Wprowadzone wartości będą widoczne dla innych autorów, tworząc nowe strony z układu lub przełączając do niego.</span><span class="sxs-lookup"><span data-stu-id="a5e70-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="a5e70-131">Dlatego należy wprowadzić wartości, które będą przydatne autorom stron.</span><span class="sxs-lookup"><span data-stu-id="a5e70-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="a5e70-132">Wybierz przycisk **OK**, aby utworzyć nowy układ predefiniowany i otworzyć edytor układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="a5e70-133">W edytorze układu dodaj i skonfiguruj moduły, korzystając z drzewa konspektu po lewej stronie i okienka właściwości po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="a5e70-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="a5e70-134">(Proces ten przypomina proces dodawania i konfigurowania modułów szablonu w edytorze szablonów.) Układ modułów i wszelkie zablokowane ustawienia domyślne stają się scentralizowaną konfiguracją modułu dla stron używających tego układu predefiniowanego.</span><span class="sxs-lookup"><span data-stu-id="a5e70-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="a5e70-135">Modyfikowanie predefiniowanego układu</span><span class="sxs-lookup"><span data-stu-id="a5e70-135">Modify a preset layout</span></span>

<span data-ttu-id="a5e70-136">Aby modyfikować układ predefiniowany, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5e70-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="a5e70-137">W okienku nawigacji po lewej stronie zaznacz **Układy**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="a5e70-138">W edytorze układu, w drzewie konspektu z lewej strony, wybierz moduł do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="a5e70-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="a5e70-139">Następnie wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="a5e70-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="a5e70-140">Aby przenieść moduł w górę lub w dół wewnątrz jego elementu nadrzędnego, wybierz przycisk wielokropeka (**...**) dla modułu, a następnie wybierz opcję **Przenieś w górę** lub **Przenieś w dół**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="a5e70-141">Aby zmienić domyślne ustawienia modułu, należy w okienku właściwości wprowadzić wartości domyślne i opcjonalnie je zablokować dla wszystkich podrzędnych stron.</span><span class="sxs-lookup"><span data-stu-id="a5e70-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="a5e70-142">Aby dodać nowe moduły lub fragmenty do modułów kontenerów, wybierz przycisk wielokropeka, a następnie wybierz opcję **Dodaj moduł** lub **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="a5e70-143">Aby usunąć moduł z układu, wybierz przycisk wielokropek, a następnie wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="a5e70-144">Zmienianie wstępnie ustawionego motywu układu</span><span class="sxs-lookup"><span data-stu-id="a5e70-144">Change a preset layout theme</span></span>

<span data-ttu-id="a5e70-145">Typową praktyką jest ustawienie domyślnego motywu dla wszystkich stron używających predefiniowanego układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="a5e70-146">Aby ustawić lub zmienić motyw dla wszystkich stron podrzędnych korzystających z układu predefiniowanego, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5e70-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="a5e70-147">W edytorze układu, w drzewie konspektu z lewej strony, wybierz moduł kontenera strony.</span><span class="sxs-lookup"><span data-stu-id="a5e70-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="a5e70-148">(Zazwyczaj ten moduł jest drugim węzłem i ma nazwę **Strona domyślna**.)</span><span class="sxs-lookup"><span data-stu-id="a5e70-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="a5e70-149">W okienku właściwości po prawej stronie w polu **motyw** wybierz motyw.</span><span class="sxs-lookup"><span data-stu-id="a5e70-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="a5e70-150">Zapisywanie, zaewidencjonuj, przejrzyj i opublikuj predefiniowany układ</span><span class="sxs-lookup"><span data-stu-id="a5e70-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="a5e70-151">Aby zapisać i zewidencjonować predefiniowany układ, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5e70-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="a5e70-152">Wybierz opcję **Zapisz** u góry edytora układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="a5e70-153">Zapisane zmiany nie wpływają na strony podrzędne, dopóki nie zostaną zaewidencjonowane.</span><span class="sxs-lookup"><span data-stu-id="a5e70-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="a5e70-154">Wybierz **Zaewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-154">Select **Check In**.</span></span> <span data-ttu-id="a5e70-155">Twoje zmiany są teraz wykrywalne dla podrzędnych przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="a5e70-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="a5e70-156">Aby wyświetlić podgląd zmian, należy otworzyć istniejącą stronę, która używa tego predefiniowanego układu, lub utworzyć nową stronę na podstawie tego układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="a5e70-157">Po przejrzeniu zmian w predefiniowanym szablonie należy wykonać jedną z następujących czynności, aby opublikować układ w witrynie na żywo:</span><span class="sxs-lookup"><span data-stu-id="a5e70-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="a5e70-158">Przejdź do **Układy**, wybierz układ, a następnie wybierz opcję **Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="a5e70-159">W edytorze układu wybierz opcję **Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="a5e70-159">In the layout editor, select **Publish**.</span></span>
* <span data-ttu-id="a5e70-160">Umożliwia opublikowanie strony, która odwołuje się do nieopublikowanego układu.</span><span class="sxs-lookup"><span data-stu-id="a5e70-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="a5e70-161">Układ zostanie automatycznie opublikowany.</span><span class="sxs-lookup"><span data-stu-id="a5e70-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="a5e70-162">Do dostępnych układów mogą odwoływać się wiele stron.</span><span class="sxs-lookup"><span data-stu-id="a5e70-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="a5e70-163">Publikując predefiniowany układ, należy pamiętać, że może on mieć wpływ na układ wielu stron.</span><span class="sxs-lookup"><span data-stu-id="a5e70-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5e70-164">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a5e70-164">Additional resources</span></span>

[<span data-ttu-id="a5e70-165">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="a5e70-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="a5e70-166">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="a5e70-166">Work with templates</span></span>](work-with-templates.md)
