---
title: Moduł harmonijki
description: W tym temacie opisano moduły harmonijki i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2bb18539f610e5af05f8d9a20a0ba9f34db5c94f
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817141"
---
# <a name="accordion-module"></a><span data-ttu-id="57e1a-103">Moduł harmonijki</span><span class="sxs-lookup"><span data-stu-id="57e1a-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="57e1a-104">W tym temacie opisano moduły harmonijki i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="57e1a-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="57e1a-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="57e1a-105">Overview</span></span>

<span data-ttu-id="57e1a-106">Moduły harmonijki to moduły podobne do kontenerów, które służą do organizowania informacji lub modułów na stronie, zapewniając składaną funkcję szuflady.</span><span class="sxs-lookup"><span data-stu-id="57e1a-106">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="57e1a-107">Na dowolnej stronie można używać modułu harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-107">An accordion module can be used on any page.</span></span>

<span data-ttu-id="57e1a-108">W każdym module harmonijki można dodać jeden lub więcej modułów pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-108">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="57e1a-109">Każdy moduł pozycji harmonijki reprezentuje szufladę zwijaną.</span><span class="sxs-lookup"><span data-stu-id="57e1a-109">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="57e1a-110">W każdym module pozycji harmonijki można dodać jeden lub więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="57e1a-110">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="57e1a-111">Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-111">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="57e1a-112">Poniższy obraz przedstawia przykład modułu harmonijki, który jest używany do organizowania informacji na stronie często zadawanych pytań dotyczących sklepu.</span><span class="sxs-lookup"><span data-stu-id="57e1a-112">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Przykład modułu harmonijki](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="57e1a-114">Właściwości modułu harmonijki</span><span class="sxs-lookup"><span data-stu-id="57e1a-114">Accordion module properties</span></span>

| <span data-ttu-id="57e1a-115">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="57e1a-115">Property name</span></span> | <span data-ttu-id="57e1a-116">Wartości</span><span class="sxs-lookup"><span data-stu-id="57e1a-116">Values</span></span> | <span data-ttu-id="57e1a-117">opis</span><span class="sxs-lookup"><span data-stu-id="57e1a-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="57e1a-118">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="57e1a-118">Heading</span></span> | <span data-ttu-id="57e1a-119">Tekst</span><span class="sxs-lookup"><span data-stu-id="57e1a-119">Text</span></span> | <span data-ttu-id="57e1a-120">Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-120">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="57e1a-121">Rozwiń wszystko</span><span class="sxs-lookup"><span data-stu-id="57e1a-121">Expand All</span></span> | <span data-ttu-id="57e1a-122">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="57e1a-122">**True** or **False**</span></span> | <span data-ttu-id="57e1a-123">Jeśli wartość jest ustawiona na **Prawda**, funkcja Rozwiń/Zwiń jest włączona, co umożliwia rozwijanie i zwijanie wszystkich towarów w module harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-123">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="57e1a-124">Styl interakcji</span><span class="sxs-lookup"><span data-stu-id="57e1a-124">Interaction Style</span></span> | <span data-ttu-id="57e1a-125">**Niezależne** lub **Rozwijaj tylko jeden element**</span><span class="sxs-lookup"><span data-stu-id="57e1a-125">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="57e1a-126">Ta właściwość definiuje styl interakcji dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="57e1a-126">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="57e1a-127">Jeśli wartość jest ustawiona jako **Niezależne**, każdy z nich może być rozwinięty lub zwijany niezależnie.</span><span class="sxs-lookup"><span data-stu-id="57e1a-127">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="57e1a-128">Jeśli wartość jest ustawiona na **Rozwijaj tylko jeden element**, w danym momencie może być rozwinięty tylko jeden towar.</span><span class="sxs-lookup"><span data-stu-id="57e1a-128">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="57e1a-129">Po rozwinięciu towarów poprzednio rozwinięte elementy są zwijane.</span><span class="sxs-lookup"><span data-stu-id="57e1a-129">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="57e1a-130">Właściwości modułu pozycji harmonijki</span><span class="sxs-lookup"><span data-stu-id="57e1a-130">Accordion item module properties</span></span>

| <span data-ttu-id="57e1a-131">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="57e1a-131">Property name</span></span> | <span data-ttu-id="57e1a-132">Wartości</span><span class="sxs-lookup"><span data-stu-id="57e1a-132">Values</span></span> | <span data-ttu-id="57e1a-133">opis</span><span class="sxs-lookup"><span data-stu-id="57e1a-133">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="57e1a-134">Nazwa</span><span class="sxs-lookup"><span data-stu-id="57e1a-134">Title</span></span> | <span data-ttu-id="57e1a-135">Tekst</span><span class="sxs-lookup"><span data-stu-id="57e1a-135">Text</span></span> | <span data-ttu-id="57e1a-136">Ta właściwość określa tekst tytułu dla modułu pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-136">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="57e1a-137">Wybierając region tytułu, użytkownicy będą mogli rozwijać lub zwijać sekcje.</span><span class="sxs-lookup"><span data-stu-id="57e1a-137">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="57e1a-138">Rozwiń domyślnie</span><span class="sxs-lookup"><span data-stu-id="57e1a-138">Expand by default</span></span> | <span data-ttu-id="57e1a-139">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="57e1a-139">**True** or **False**</span></span> | <span data-ttu-id="57e1a-140">Jeśli wartość jest ustawiona na **Prawda**, podczas wczytywania strony domyślnie jest rozwinięta pozycja harmonijki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-140">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="57e1a-141">Dodawanie modułu harmonijki do strony Często zadawanych pytań</span><span class="sxs-lookup"><span data-stu-id="57e1a-141">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="57e1a-142">Aby dodać moduł harmonijki do strony Często zadawanych pytań i ustawić wymagane właściwości w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="57e1a-142">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="57e1a-143">Przejdź do **Strony** i użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Często zadawane pytania o sklepie**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-143">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="57e1a-144">W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-144">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="57e1a-145">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="57e1a-146">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-146">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="57e1a-147">W oknie dialogowym **Dodaj moduł** wybierz moduł **Harmonijka** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-147">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="57e1a-148">W okienku właściwości modułu harmonijki wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="57e1a-148">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="57e1a-149">W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź **Często zadawane pytania**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-149">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="57e1a-150">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-150">Then select **OK**.</span></span>
1. <span data-ttu-id="57e1a-151">W okienku właściwości modułu harmonijka zaznacz pole wyboru **Pokaż wszystkie rozwinięte**, a następnie w polu **Styl interakcji** wybierz opcję **Niezależne**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-151">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="57e1a-152">W gnieździe **Harmonijka** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-152">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="57e1a-153">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element harmonijki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-153">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="57e1a-154">W okienku właściwości modułu pozycji harmonijki w obszarze **Tytuł** wprowadź tekst tytułu (np. **Jak działają zwroty?**).</span><span class="sxs-lookup"><span data-stu-id="57e1a-154">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="57e1a-155">W gnieździe **Pozycja harmonijki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-155">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="57e1a-156">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e1a-156">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="57e1a-157">W okienku właściwości modułu blok tekstu wprowadź akapit tekstu (na przykład **Zwroty muszą być przetwarzane za pośrednictwem biura obsługi. Numer kontaktowy 1-800-FABRIKAM w sprawie zwrotów. Produkty mają 30-dniowe zasady dotyczące zwrotów. Zwroty muszą być inicjowane w tym przedziale czasu.**).</span><span class="sxs-lookup"><span data-stu-id="57e1a-157">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="57e1a-158">W gnieździe **Harmonijka** dodaj kilka więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="57e1a-158">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="57e1a-159">W każdym module pozycji harmonijki należy dodać moduł bloku tekstu z zawartością.</span><span class="sxs-lookup"><span data-stu-id="57e1a-159">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="57e1a-160">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="57e1a-160">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="57e1a-161">Na stronie zostanie wyświetlony moduł harmonijki z dodaną zawartością.</span><span class="sxs-lookup"><span data-stu-id="57e1a-161">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="57e1a-162">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="57e1a-162">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57e1a-163">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="57e1a-163">Additional resources</span></span>

[<span data-ttu-id="57e1a-164">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="57e1a-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="57e1a-165">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="57e1a-165">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="57e1a-166">Moduł tabularny</span><span class="sxs-lookup"><span data-stu-id="57e1a-166">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="57e1a-167">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="57e1a-167">Text block module</span></span>](add-content-rich-block.md)
