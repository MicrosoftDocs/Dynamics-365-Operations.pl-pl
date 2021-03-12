---
title: Moduł karty
description: W tym temacie opisano moduły karty i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 42c3cd99897627dbcdbdec91cfdb03d5743f7388
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980189"
---
# <a name="tab-module"></a><span data-ttu-id="00265-103">Moduł karty</span><span class="sxs-lookup"><span data-stu-id="00265-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="00265-104">W tym temacie opisano moduły karty i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="00265-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="00265-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="00265-105">Overview</span></span>

<span data-ttu-id="00265-106">Moduły kart są modułami przypominającymi kontenery, które służą do organizowania informacji na stronie witryny na kartach.</span><span class="sxs-lookup"><span data-stu-id="00265-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="00265-107">Można ich używać na dowolnej stronie, na której należy przedstawić informacje na kartach.</span><span class="sxs-lookup"><span data-stu-id="00265-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="00265-108">W każdym module karty można dodać jeden lub więcej modułów pozycji karty.</span><span class="sxs-lookup"><span data-stu-id="00265-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="00265-109">Każdy moduł karty reprezentuje pojedynczą kartę. W każdym module pozycji karty można dodać jeden lub więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="00265-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="00265-110">Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji karty.</span><span class="sxs-lookup"><span data-stu-id="00265-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="00265-111">Poniższy obraz pokazuje przykład modułu karty na stronie witryny.</span><span class="sxs-lookup"><span data-stu-id="00265-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="00265-112">W tym przykładzie wybrano kartę **Wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="00265-112">In this example, the **Shipping** tab selected.</span></span>

![Przykład modułu karty](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="00265-114">Właściwości modułu karty</span><span class="sxs-lookup"><span data-stu-id="00265-114">Tab module properties</span></span>

| <span data-ttu-id="00265-115">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="00265-115">Property name</span></span> | <span data-ttu-id="00265-116">Wartości</span><span class="sxs-lookup"><span data-stu-id="00265-116">Values</span></span> | <span data-ttu-id="00265-117">opis</span><span class="sxs-lookup"><span data-stu-id="00265-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="00265-118">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="00265-118">Heading</span></span> | <span data-ttu-id="00265-119">Tekst</span><span class="sxs-lookup"><span data-stu-id="00265-119">Text</span></span> | <span data-ttu-id="00265-120">Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu kart.</span><span class="sxs-lookup"><span data-stu-id="00265-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="00265-121">Aktywny indeks karty</span><span class="sxs-lookup"><span data-stu-id="00265-121">Active Tab Index</span></span> | <span data-ttu-id="00265-122">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="00265-122">Number</span></span> | <span data-ttu-id="00265-123">Właściwość ta określa kartę, która powinna być domyślnie aktywna podczas ładowania strony.</span><span class="sxs-lookup"><span data-stu-id="00265-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="00265-124">Jeśli nie zostanie podana żadna wartość, domyślnie jest aktywna pierwsza pozycja karty.</span><span class="sxs-lookup"><span data-stu-id="00265-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="00265-125">Właściwości modułu pozycji karty</span><span class="sxs-lookup"><span data-stu-id="00265-125">Tab item module properties</span></span>

| <span data-ttu-id="00265-126">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="00265-126">Property name</span></span> | <span data-ttu-id="00265-127">Wartości</span><span class="sxs-lookup"><span data-stu-id="00265-127">Values</span></span> | <span data-ttu-id="00265-128">opis</span><span class="sxs-lookup"><span data-stu-id="00265-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="00265-129">Nazwa</span><span class="sxs-lookup"><span data-stu-id="00265-129">Title</span></span> | <span data-ttu-id="00265-130">Tekst</span><span class="sxs-lookup"><span data-stu-id="00265-130">Text</span></span> | <span data-ttu-id="00265-131">Ta właściwość określa tekst tytułu dla modułu pozycji karty.</span><span class="sxs-lookup"><span data-stu-id="00265-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="00265-132">Dodawanie modułu karty do strony</span><span class="sxs-lookup"><span data-stu-id="00265-132">Add a tab module to a page</span></span>

<span data-ttu-id="00265-133">Aby dodać moduł karty do strony i ustawić właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="00265-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="00265-134">Użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Strona zasad sklepu**.</span><span class="sxs-lookup"><span data-stu-id="00265-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="00265-135">W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="00265-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="00265-136">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="00265-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="00265-137">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="00265-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="00265-138">W oknie dialogowym **Dodaj moduł** wybierz moduł **Karta** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="00265-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="00265-139">W okienku właściwości modułu kart wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="00265-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="00265-140">W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź tekst nagłówka (np. **Zasady**).</span><span class="sxs-lookup"><span data-stu-id="00265-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="00265-141">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="00265-141">Then select **OK**.</span></span>
1. <span data-ttu-id="00265-142">W gnieździe **Karta** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="00265-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="00265-143">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Pozycja karty** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="00265-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="00265-144">W okienku właściwości modułu pozycji kart w obszarze **Tytuł** wprowadź tekst tytułu (np. **Dostawa**).</span><span class="sxs-lookup"><span data-stu-id="00265-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="00265-145">W gnieździe **Pozycja karty** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="00265-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="00265-146">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="00265-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="00265-147">W okienku właściwości modułu blok tekstu pod **Tekst sformatowany** wprowadzić akapit tekstu..</span><span class="sxs-lookup"><span data-stu-id="00265-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="00265-148">W gnieździe **Karta** dodaj kilka dodatkowych modułów z kartami z tytułami.</span><span class="sxs-lookup"><span data-stu-id="00265-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="00265-149">W każdym module pozycji karty należy dodać moduł bloku tekstu z zawartością.</span><span class="sxs-lookup"><span data-stu-id="00265-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="00265-150">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="00265-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="00265-151">Na stronie zostanie wyświetlona karta zawierająca moduły pozycji karty, która zawiera dodaną zawartość.</span><span class="sxs-lookup"><span data-stu-id="00265-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="00265-152">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="00265-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="00265-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="00265-153">Additional resources</span></span>

[<span data-ttu-id="00265-154">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="00265-154">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="00265-155">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="00265-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="00265-156">Moduł typu accordion</span><span class="sxs-lookup"><span data-stu-id="00265-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="00265-157">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="00265-157">Text block module</span></span>](add-content-rich-block.md)
