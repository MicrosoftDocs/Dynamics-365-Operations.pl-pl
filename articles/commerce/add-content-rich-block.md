---
title: Moduł bloku zaawansowanej zawartości
description: W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7dbeb8785641960cc2680335436aea10775759d3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797774"
---
# <a name="text-block-module"></a><span data-ttu-id="3736f-103">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="3736f-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3736f-104">W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3736f-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3736f-105">Moduł bloku tekstu to moduł służący do dodawania zawartości tekstowej.</span><span class="sxs-lookup"><span data-stu-id="3736f-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="3736f-106">Ta zawartość może mieć wartość informacyjną lub promocyjną.</span><span class="sxs-lookup"><span data-stu-id="3736f-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="3736f-107">Moduły bloku zaawansowanej zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="3736f-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="3736f-108">Są to moduły autonomiczne, które nie są zależne od kontekstu strony ani innych modułów.</span><span class="sxs-lookup"><span data-stu-id="3736f-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="3736f-109">Przykłady modułów bloku zaawansowanej zawartości w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="3736f-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="3736f-110">Moduły bloku zaawansowanej zawartości mogą być używane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="3736f-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="3736f-111">W celu zaprezentowania funkcji produktu na stronie Szczegóły produktu.</span><span class="sxs-lookup"><span data-stu-id="3736f-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="3736f-112">Do celów informacyjnych na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="3736f-112">For informational purposes on any page.</span></span> <span data-ttu-id="3736f-113">Można na przykład wyjaśnić zalety programów lojalnościowych, opisać zasady wysyłki i zwrotów, odpowiedzi na często zadawane pytania lub dostarczyć zawartość „o nas”.</span><span class="sxs-lookup"><span data-stu-id="3736f-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="3736f-114">, Aby dodać niestandardowe komunikaty na stronie szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="3736f-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="3736f-115">(na przykład „bezpłatna wysyłka zamówień o wartości ponad $50”).</span><span class="sxs-lookup"><span data-stu-id="3736f-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="3736f-116">Dla roszczeń i szczegółów dotyczących kontaktu na stronach szczegółów produktu, na stronach koszyka, na stronach do realizacji transakcji oraz na innych stronach (np. „Wysyłka i zwroty podlegają zasadom sklepu”).</span><span class="sxs-lookup"><span data-stu-id="3736f-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="3736f-117">Poniższy obraz pokazuje przykład modułu bloku tekstu, który jest używany na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="3736f-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Przykład modułu bloku tekstu](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="3736f-119">Właściwości modułu bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="3736f-119">Text block module properties</span></span>

| <span data-ttu-id="3736f-120">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="3736f-120">Property name</span></span>     | <span data-ttu-id="3736f-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="3736f-121">Value</span></span>                                            | <span data-ttu-id="3736f-122">opis</span><span class="sxs-lookup"><span data-stu-id="3736f-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="3736f-123">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="3736f-123">Rich text</span></span>         | <span data-ttu-id="3736f-124">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="3736f-124">Rich text</span></span>                                        | <span data-ttu-id="3736f-125">Tekst akapitu.</span><span class="sxs-lookup"><span data-stu-id="3736f-125">Paragraph text.</span></span> <span data-ttu-id="3736f-126">Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa.</span><span class="sxs-lookup"><span data-stu-id="3736f-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="3736f-127">Niestandardowa nazwa klasy</span><span class="sxs-lookup"><span data-stu-id="3736f-127">Custom class name</span></span> | <span data-ttu-id="3736f-128">Nazwa klasy arkuszy stylów kaskadowych (CSS)</span><span class="sxs-lookup"><span data-stu-id="3736f-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="3736f-129">Nazwa niestandardowej klasy CSS, którą projektant chce sformatować w tym module.</span><span class="sxs-lookup"><span data-stu-id="3736f-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="3736f-130">Nazwa klasy powinna być zdefiniowana w pakiecie kompozycji.</span><span class="sxs-lookup"><span data-stu-id="3736f-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="3736f-131">Rozmiar czcionki</span><span class="sxs-lookup"><span data-stu-id="3736f-131">Font size</span></span>         | <span data-ttu-id="3736f-132">**Małe**, **średnie**, **duże** lub **XL**</span><span class="sxs-lookup"><span data-stu-id="3736f-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="3736f-133">Wybierz rozmiar czcionki treści.</span><span class="sxs-lookup"><span data-stu-id="3736f-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="3736f-134">Dodawanie bloku zaawansowanej zawartości do nowej strony</span><span class="sxs-lookup"><span data-stu-id="3736f-134">Add a text block module to a page</span></span>

<span data-ttu-id="3736f-135">Aby dodać moduł blokuzaawansowanej zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3736f-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3736f-136">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="3736f-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="3736f-137">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** przejdź do **Szablon zawartości**.</span><span class="sxs-lookup"><span data-stu-id="3736f-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="3736f-138">W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="3736f-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3736f-139">W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3736f-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3736f-140">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="3736f-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3736f-141">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="3736f-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="3736f-142">W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon zawartości**.</span><span class="sxs-lookup"><span data-stu-id="3736f-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="3736f-143">W sekcji **Nazwa strony** przejdź do **Strona zawartości**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3736f-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="3736f-144">Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="3736f-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3736f-145">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3736f-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3736f-146">W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="3736f-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="3736f-147">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="3736f-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3736f-148">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3736f-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="3736f-149">W okienku właściwości modułu blok tekstu Dodaj tekst do pola **Tekst sformatowany**.</span><span class="sxs-lookup"><span data-stu-id="3736f-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="3736f-150">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="3736f-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="3736f-151">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="3736f-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3736f-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3736f-152">Additional resources</span></span>

[<span data-ttu-id="3736f-153">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="3736f-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3736f-154">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="3736f-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="3736f-155">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="3736f-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="3736f-156">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="3736f-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="3736f-157">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="3736f-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]