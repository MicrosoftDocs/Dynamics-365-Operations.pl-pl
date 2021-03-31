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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a08441f5dffa9c2c65b304d0265dd107a838a685
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206614"
---
# <a name="accordion-module"></a><span data-ttu-id="c1289-103">Moduł typu accordion</span><span class="sxs-lookup"><span data-stu-id="c1289-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c1289-104">W tym temacie opisano moduły harmonijki i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c1289-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c1289-105">Moduły harmonijki to moduły podobne do kontenerów, które służą do organizowania informacji lub modułów na stronie, zapewniając składaną funkcję szuflady.</span><span class="sxs-lookup"><span data-stu-id="c1289-105">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="c1289-106">Na dowolnej stronie można używać modułu harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-106">An accordion module can be used on any page.</span></span>

<span data-ttu-id="c1289-107">W każdym module harmonijki można dodać jeden lub więcej modułów pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-107">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="c1289-108">Każdy moduł pozycji harmonijki reprezentuje szufladę zwijaną.</span><span class="sxs-lookup"><span data-stu-id="c1289-108">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="c1289-109">W każdym module pozycji harmonijki można dodać jeden lub więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="c1289-109">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="c1289-110">Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-110">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="c1289-111">Poniższy obraz przedstawia przykład modułu harmonijki, który jest używany do organizowania informacji na stronie często zadawanych pytań dotyczących sklepu.</span><span class="sxs-lookup"><span data-stu-id="c1289-111">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Przykład modułu harmonijki](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="c1289-113">Właściwości modułu harmonijki</span><span class="sxs-lookup"><span data-stu-id="c1289-113">Accordion module properties</span></span>

| <span data-ttu-id="c1289-114">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="c1289-114">Property name</span></span> | <span data-ttu-id="c1289-115">Wartości</span><span class="sxs-lookup"><span data-stu-id="c1289-115">Values</span></span> | <span data-ttu-id="c1289-116">opis</span><span class="sxs-lookup"><span data-stu-id="c1289-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="c1289-117">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="c1289-117">Heading</span></span> | <span data-ttu-id="c1289-118">Tekst</span><span class="sxs-lookup"><span data-stu-id="c1289-118">Text</span></span> | <span data-ttu-id="c1289-119">Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-119">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="c1289-120">Rozwiń wszystko</span><span class="sxs-lookup"><span data-stu-id="c1289-120">Expand All</span></span> | <span data-ttu-id="c1289-121">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c1289-121">**True** or **False**</span></span> | <span data-ttu-id="c1289-122">Jeśli wartość jest ustawiona na **Prawda**, funkcja Rozwiń/Zwiń jest włączona, co umożliwia rozwijanie i zwijanie wszystkich towarów w module harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-122">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="c1289-123">Styl interakcji</span><span class="sxs-lookup"><span data-stu-id="c1289-123">Interaction Style</span></span> | <span data-ttu-id="c1289-124">**Niezależne** lub **Rozwijaj tylko jeden element**</span><span class="sxs-lookup"><span data-stu-id="c1289-124">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="c1289-125">Ta właściwość definiuje styl interakcji dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="c1289-125">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="c1289-126">Jeśli wartość jest ustawiona jako **Niezależne**, każdy z nich może być rozwinięty lub zwijany niezależnie.</span><span class="sxs-lookup"><span data-stu-id="c1289-126">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="c1289-127">Jeśli wartość jest ustawiona na **Rozwijaj tylko jeden element**, w danym momencie może być rozwinięty tylko jeden towar.</span><span class="sxs-lookup"><span data-stu-id="c1289-127">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="c1289-128">Po rozwinięciu towarów poprzednio rozwinięte elementy są zwijane.</span><span class="sxs-lookup"><span data-stu-id="c1289-128">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="c1289-129">Właściwości modułu pozycji harmonijki</span><span class="sxs-lookup"><span data-stu-id="c1289-129">Accordion item module properties</span></span>

| <span data-ttu-id="c1289-130">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="c1289-130">Property name</span></span> | <span data-ttu-id="c1289-131">Wartości</span><span class="sxs-lookup"><span data-stu-id="c1289-131">Values</span></span> | <span data-ttu-id="c1289-132">opis</span><span class="sxs-lookup"><span data-stu-id="c1289-132">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="c1289-133">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c1289-133">Title</span></span> | <span data-ttu-id="c1289-134">Tekst</span><span class="sxs-lookup"><span data-stu-id="c1289-134">Text</span></span> | <span data-ttu-id="c1289-135">Ta właściwość określa tekst tytułu dla modułu pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-135">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="c1289-136">Wybierając region tytułu, użytkownicy będą mogli rozwijać lub zwijać sekcje.</span><span class="sxs-lookup"><span data-stu-id="c1289-136">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="c1289-137">Rozwiń domyślnie</span><span class="sxs-lookup"><span data-stu-id="c1289-137">Expand by default</span></span> | <span data-ttu-id="c1289-138">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c1289-138">**True** or **False**</span></span> | <span data-ttu-id="c1289-139">Jeśli wartość jest ustawiona na **Prawda**, podczas wczytywania strony domyślnie jest rozwinięta pozycja harmonijki.</span><span class="sxs-lookup"><span data-stu-id="c1289-139">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="c1289-140">Dodawanie modułu harmonijki do strony Często zadawanych pytań</span><span class="sxs-lookup"><span data-stu-id="c1289-140">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="c1289-141">Aby dodać moduł harmonijki do strony Często zadawanych pytań i ustawić wymagane właściwości w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c1289-141">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="c1289-142">Przejdź do **Strony** i użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Często zadawane pytania o sklepie**.</span><span class="sxs-lookup"><span data-stu-id="c1289-142">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="c1289-143">W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c1289-143">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1289-144">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1289-144">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1289-145">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c1289-145">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1289-146">W oknie dialogowym **Dodaj moduł** wybierz moduł **Harmonijka** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1289-146">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1289-147">W okienku właściwości modułu harmonijki wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="c1289-147">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="c1289-148">W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź **Często zadawane pytania**.</span><span class="sxs-lookup"><span data-stu-id="c1289-148">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="c1289-149">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1289-149">Then select **OK**.</span></span>
1. <span data-ttu-id="c1289-150">W okienku właściwości modułu harmonijka zaznacz pole wyboru **Pokaż wszystkie rozwinięte**, a następnie w polu **Styl interakcji** wybierz opcję **Niezależne**.</span><span class="sxs-lookup"><span data-stu-id="c1289-150">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="c1289-151">W gnieździe **Harmonijka** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c1289-151">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1289-152">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element harmonijki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1289-152">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1289-153">W okienku właściwości modułu pozycji harmonijki w obszarze **Tytuł** wprowadź tekst tytułu (np. **Jak działają zwroty?**).</span><span class="sxs-lookup"><span data-stu-id="c1289-153">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="c1289-154">W gnieździe **Pozycja harmonijki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c1289-154">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1289-155">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1289-155">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1289-156">W okienku właściwości modułu blok tekstu wprowadź akapit tekstu (na przykład **Zwroty muszą być przetwarzane za pośrednictwem biura obsługi. Numer kontaktowy 1-800-FABRIKAM w sprawie zwrotów. Produkty mają 30-dniowe zasady dotyczące zwrotów. Zwroty muszą być inicjowane w tym przedziale czasu.**).</span><span class="sxs-lookup"><span data-stu-id="c1289-156">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="c1289-157">W gnieździe **Harmonijka** dodaj kilka więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="c1289-157">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="c1289-158">W każdym module pozycji harmonijki należy dodać moduł bloku tekstu z zawartością.</span><span class="sxs-lookup"><span data-stu-id="c1289-158">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="c1289-159">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="c1289-159">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="c1289-160">Na stronie zostanie wyświetlony moduł harmonijki z dodaną zawartością.</span><span class="sxs-lookup"><span data-stu-id="c1289-160">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="c1289-161">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="c1289-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1289-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1289-162">Additional resources</span></span>

[<span data-ttu-id="c1289-163">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="c1289-163">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c1289-164">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="c1289-164">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c1289-165">Moduł tabularny</span><span class="sxs-lookup"><span data-stu-id="c1289-165">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="c1289-166">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="c1289-166">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]