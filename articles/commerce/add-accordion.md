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
ms.openlocfilehash: 28cb9d2e450ff1c05d4faa5cac343e03ef051437
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986111"
---
# <a name="accordion-module"></a><span data-ttu-id="4ebd6-103">Moduł harmonijki</span><span class="sxs-lookup"><span data-stu-id="4ebd6-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4ebd6-104">W tym temacie opisano moduły harmonijki i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4ebd6-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="4ebd6-105">Overview</span></span>

<span data-ttu-id="4ebd6-106">Moduły harmonijki to moduły podobne do kontenerów, które służą do organizowania informacji lub modułów na stronie, zapewniając składaną funkcję szuflady.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-106">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="4ebd6-107">Na dowolnej stronie można używać modułu harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-107">An accordion module can be used on any page.</span></span>

<span data-ttu-id="4ebd6-108">W każdym module harmonijki można dodać jeden lub więcej modułów pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-108">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="4ebd6-109">Każdy moduł pozycji harmonijki reprezentuje szufladę zwijaną.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-109">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="4ebd6-110">W każdym module pozycji harmonijki można dodać jeden lub więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-110">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="4ebd6-111">Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-111">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="4ebd6-112">Poniższy obraz przedstawia przykład modułu harmonijki, który jest używany do organizowania informacji na stronie często zadawanych pytań dotyczących sklepu.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-112">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Przykład modułu harmonijki](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="4ebd6-114">Właściwości modułu harmonijki</span><span class="sxs-lookup"><span data-stu-id="4ebd6-114">Accordion module properties</span></span>

| <span data-ttu-id="4ebd6-115">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="4ebd6-115">Property name</span></span> | <span data-ttu-id="4ebd6-116">Wartości</span><span class="sxs-lookup"><span data-stu-id="4ebd6-116">Values</span></span> | <span data-ttu-id="4ebd6-117">opis</span><span class="sxs-lookup"><span data-stu-id="4ebd6-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="4ebd6-118">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="4ebd6-118">Heading</span></span> | <span data-ttu-id="4ebd6-119">Tekst</span><span class="sxs-lookup"><span data-stu-id="4ebd6-119">Text</span></span> | <span data-ttu-id="4ebd6-120">Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-120">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="4ebd6-121">Rozwiń wszystko</span><span class="sxs-lookup"><span data-stu-id="4ebd6-121">Expand All</span></span> | <span data-ttu-id="4ebd6-122">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="4ebd6-122">**True** or **False**</span></span> | <span data-ttu-id="4ebd6-123">Jeśli wartość jest ustawiona na **Prawda**, funkcja Rozwiń/Zwiń jest włączona, co umożliwia rozwijanie i zwijanie wszystkich towarów w module harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-123">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="4ebd6-124">Styl interakcji</span><span class="sxs-lookup"><span data-stu-id="4ebd6-124">Interaction Style</span></span> | <span data-ttu-id="4ebd6-125">**Niezależne** lub **Rozwijaj tylko jeden element**</span><span class="sxs-lookup"><span data-stu-id="4ebd6-125">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="4ebd6-126">Ta właściwość definiuje styl interakcji dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-126">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="4ebd6-127">Jeśli wartość jest ustawiona jako **Niezależne**, każdy z nich może być rozwinięty lub zwijany niezależnie.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-127">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="4ebd6-128">Jeśli wartość jest ustawiona na **Rozwijaj tylko jeden element**, w danym momencie może być rozwinięty tylko jeden towar.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-128">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="4ebd6-129">Po rozwinięciu towarów poprzednio rozwinięte elementy są zwijane.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-129">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="4ebd6-130">Właściwości modułu pozycji harmonijki</span><span class="sxs-lookup"><span data-stu-id="4ebd6-130">Accordion item module properties</span></span>

| <span data-ttu-id="4ebd6-131">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="4ebd6-131">Property name</span></span> | <span data-ttu-id="4ebd6-132">Wartości</span><span class="sxs-lookup"><span data-stu-id="4ebd6-132">Values</span></span> | <span data-ttu-id="4ebd6-133">opis</span><span class="sxs-lookup"><span data-stu-id="4ebd6-133">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="4ebd6-134">Nazwa</span><span class="sxs-lookup"><span data-stu-id="4ebd6-134">Title</span></span> | <span data-ttu-id="4ebd6-135">Tekst</span><span class="sxs-lookup"><span data-stu-id="4ebd6-135">Text</span></span> | <span data-ttu-id="4ebd6-136">Ta właściwość określa tekst tytułu dla modułu pozycji harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-136">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="4ebd6-137">Wybierając region tytułu, użytkownicy będą mogli rozwijać lub zwijać sekcje.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-137">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="4ebd6-138">Rozwiń domyślnie</span><span class="sxs-lookup"><span data-stu-id="4ebd6-138">Expand by default</span></span> | <span data-ttu-id="4ebd6-139">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="4ebd6-139">**True** or **False**</span></span> | <span data-ttu-id="4ebd6-140">Jeśli wartość jest ustawiona na **Prawda**, podczas wczytywania strony domyślnie jest rozwinięta pozycja harmonijki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-140">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="4ebd6-141">Dodawanie modułu harmonijki do strony Często zadawanych pytań</span><span class="sxs-lookup"><span data-stu-id="4ebd6-141">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="4ebd6-142">Aby dodać moduł harmonijki do strony Często zadawanych pytań i ustawić wymagane właściwości w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-142">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="4ebd6-143">Przejdź do **Strony** i użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Często zadawane pytania o sklepie**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-143">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="4ebd6-144">W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-144">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4ebd6-145">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4ebd6-146">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-146">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4ebd6-147">W oknie dialogowym **Dodaj moduł** wybierz moduł **Harmonijka** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-147">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4ebd6-148">W okienku właściwości modułu harmonijki wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-148">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="4ebd6-149">W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź **Często zadawane pytania**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-149">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="4ebd6-150">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-150">Then select **OK**.</span></span>
1. <span data-ttu-id="4ebd6-151">W okienku właściwości modułu harmonijka zaznacz pole wyboru **Pokaż wszystkie rozwinięte**, a następnie w polu **Styl interakcji** wybierz opcję **Niezależne**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-151">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="4ebd6-152">W gnieździe **Harmonijka** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-152">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4ebd6-153">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element harmonijki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-153">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4ebd6-154">W okienku właściwości modułu pozycji harmonijki w obszarze **Tytuł** wprowadź tekst tytułu (np. **Jak działają zwroty?**).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-154">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="4ebd6-155">W gnieździe **Pozycja harmonijki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-155">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4ebd6-156">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-156">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4ebd6-157">W okienku właściwości modułu blok tekstu wprowadź akapit tekstu (na przykład **Zwroty muszą być przetwarzane za pośrednictwem biura obsługi. Numer kontaktowy 1-800-FABRIKAM w sprawie zwrotów. Produkty mają 30-dniowe zasady dotyczące zwrotów. Zwroty muszą być inicjowane w tym przedziale czasu.**).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-157">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="4ebd6-158">W gnieździe **Harmonijka** dodaj kilka więcej modułów.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-158">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="4ebd6-159">W każdym module pozycji harmonijki należy dodać moduł bloku tekstu z zawartością.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-159">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="4ebd6-160">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-160">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="4ebd6-161">Na stronie zostanie wyświetlony moduł harmonijki z dodaną zawartością.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-161">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="4ebd6-162">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-162">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ebd6-163">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4ebd6-163">Additional resources</span></span>

[<span data-ttu-id="4ebd6-164">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="4ebd6-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4ebd6-165">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="4ebd6-165">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="4ebd6-166">Moduł tabularny</span><span class="sxs-lookup"><span data-stu-id="4ebd6-166">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="4ebd6-167">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="4ebd6-167">Text block module</span></span>](add-content-rich-block.md)
