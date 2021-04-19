---
title: Moduł karty
description: W tym temacie opisano moduły karty i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c865d5e055e3fadf2dda225b49f13a163974768f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797462"
---
# <a name="tab-module"></a><span data-ttu-id="1099e-103">Moduł tabularny</span><span class="sxs-lookup"><span data-stu-id="1099e-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1099e-104">W tym temacie opisano moduły karty i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1099e-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1099e-105">Moduły kart są modułami przypominającymi kontenery, które służą do organizowania informacji na stronie witryny na kartach.</span><span class="sxs-lookup"><span data-stu-id="1099e-105">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="1099e-106">Można ich używać na dowolnej stronie, na której należy przedstawić informacje na kartach.</span><span class="sxs-lookup"><span data-stu-id="1099e-106">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="1099e-107">W każdym module karty można dodać jeden lub więcej modułów pozycji karty.</span><span class="sxs-lookup"><span data-stu-id="1099e-107">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="1099e-108">Każdy moduł karty reprezentuje pojedynczą kartę. W każdym module pozycji karty można dodać jeden lub więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="1099e-108">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="1099e-109">Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji karty.</span><span class="sxs-lookup"><span data-stu-id="1099e-109">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="1099e-110">Poniższy obraz pokazuje przykład modułu karty na stronie witryny.</span><span class="sxs-lookup"><span data-stu-id="1099e-110">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="1099e-111">W tym przykładzie wybrano kartę **Wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="1099e-111">In this example, the **Shipping** tab selected.</span></span>

![Przykład modułu karty](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="1099e-113">Właściwości modułu karty</span><span class="sxs-lookup"><span data-stu-id="1099e-113">Tab module properties</span></span>

| <span data-ttu-id="1099e-114">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1099e-114">Property name</span></span> | <span data-ttu-id="1099e-115">Wartości</span><span class="sxs-lookup"><span data-stu-id="1099e-115">Values</span></span> | <span data-ttu-id="1099e-116">opis</span><span class="sxs-lookup"><span data-stu-id="1099e-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="1099e-117">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="1099e-117">Heading</span></span> | <span data-ttu-id="1099e-118">Tekst</span><span class="sxs-lookup"><span data-stu-id="1099e-118">Text</span></span> | <span data-ttu-id="1099e-119">Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu kart.</span><span class="sxs-lookup"><span data-stu-id="1099e-119">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="1099e-120">Aktywny indeks karty</span><span class="sxs-lookup"><span data-stu-id="1099e-120">Active Tab Index</span></span> | <span data-ttu-id="1099e-121">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="1099e-121">Number</span></span> | <span data-ttu-id="1099e-122">Właściwość ta określa kartę, która powinna być domyślnie aktywna podczas ładowania strony.</span><span class="sxs-lookup"><span data-stu-id="1099e-122">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="1099e-123">Jeśli nie zostanie podana żadna wartość, domyślnie jest aktywna pierwsza pozycja karty.</span><span class="sxs-lookup"><span data-stu-id="1099e-123">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="1099e-124">Właściwości modułu pozycji karty</span><span class="sxs-lookup"><span data-stu-id="1099e-124">Tab item module properties</span></span>

| <span data-ttu-id="1099e-125">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1099e-125">Property name</span></span> | <span data-ttu-id="1099e-126">Wartości</span><span class="sxs-lookup"><span data-stu-id="1099e-126">Values</span></span> | <span data-ttu-id="1099e-127">opis</span><span class="sxs-lookup"><span data-stu-id="1099e-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="1099e-128">Nazwa</span><span class="sxs-lookup"><span data-stu-id="1099e-128">Title</span></span> | <span data-ttu-id="1099e-129">Tekst</span><span class="sxs-lookup"><span data-stu-id="1099e-129">Text</span></span> | <span data-ttu-id="1099e-130">Ta właściwość określa tekst tytułu dla modułu pozycji karty.</span><span class="sxs-lookup"><span data-stu-id="1099e-130">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="1099e-131">Dodawanie modułu karty do strony</span><span class="sxs-lookup"><span data-stu-id="1099e-131">Add a tab module to a page</span></span>

<span data-ttu-id="1099e-132">Aby dodać moduł karty do strony i ustawić właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1099e-132">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="1099e-133">Użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Strona zasad sklepu**.</span><span class="sxs-lookup"><span data-stu-id="1099e-133">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="1099e-134">W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1099e-134">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1099e-135">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1099e-135">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1099e-136">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1099e-136">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1099e-137">W oknie dialogowym **Dodaj moduł** wybierz moduł **Karta** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1099e-137">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1099e-138">W okienku właściwości modułu kart wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="1099e-138">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="1099e-139">W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź tekst nagłówka (np. **Zasady**).</span><span class="sxs-lookup"><span data-stu-id="1099e-139">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="1099e-140">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="1099e-140">Then select **OK**.</span></span>
1. <span data-ttu-id="1099e-141">W gnieździe **Karta** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1099e-141">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1099e-142">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Pozycja karty** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1099e-142">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1099e-143">W okienku właściwości modułu pozycji kart w obszarze **Tytuł** wprowadź tekst tytułu (np. **Dostawa**).</span><span class="sxs-lookup"><span data-stu-id="1099e-143">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="1099e-144">W gnieździe **Pozycja karty** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1099e-144">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1099e-145">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1099e-145">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1099e-146">W okienku właściwości modułu blok tekstu pod **Tekst sformatowany** wprowadzić akapit tekstu..</span><span class="sxs-lookup"><span data-stu-id="1099e-146">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="1099e-147">W gnieździe **Karta** dodaj kilka dodatkowych modułów z kartami z tytułami.</span><span class="sxs-lookup"><span data-stu-id="1099e-147">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="1099e-148">W każdym module pozycji karty należy dodać moduł bloku tekstu z zawartością.</span><span class="sxs-lookup"><span data-stu-id="1099e-148">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="1099e-149">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="1099e-149">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="1099e-150">Na stronie zostanie wyświetlona karta zawierająca moduły pozycji karty, która zawiera dodaną zawartość.</span><span class="sxs-lookup"><span data-stu-id="1099e-150">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="1099e-151">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1099e-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1099e-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1099e-152">Additional resources</span></span>

[<span data-ttu-id="1099e-153">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="1099e-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1099e-154">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="1099e-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="1099e-155">Moduł typu accordion</span><span class="sxs-lookup"><span data-stu-id="1099e-155">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="1099e-156">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="1099e-156">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]