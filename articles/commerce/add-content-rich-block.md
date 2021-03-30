---
title: Moduł bloku zaawansowanej zawartości
description: W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3926f23e4e762a49ef94ef0c8f3291e7e9a4a6a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206398"
---
# <a name="text-block-module"></a><span data-ttu-id="abbe5-103">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="abbe5-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="abbe5-104">W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="abbe5-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="abbe5-105">Moduł bloku tekstu to moduł służący do dodawania zawartości tekstowej.</span><span class="sxs-lookup"><span data-stu-id="abbe5-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="abbe5-106">Ta zawartość może mieć wartość informacyjną lub promocyjną.</span><span class="sxs-lookup"><span data-stu-id="abbe5-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="abbe5-107">Moduły bloku zaawansowanej zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="abbe5-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="abbe5-108">Są to moduły autonomiczne, które nie są zależne od kontekstu strony ani innych modułów.</span><span class="sxs-lookup"><span data-stu-id="abbe5-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="abbe5-109">Przykłady modułów bloku zaawansowanej zawartości w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="abbe5-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="abbe5-110">Moduły bloku zaawansowanej zawartości mogą być używane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="abbe5-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="abbe5-111">W celu zaprezentowania funkcji produktu na stronie Szczegóły produktu.</span><span class="sxs-lookup"><span data-stu-id="abbe5-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="abbe5-112">Do celów informacyjnych na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="abbe5-112">For informational purposes on any page.</span></span> <span data-ttu-id="abbe5-113">Można na przykład wyjaśnić zalety programów lojalnościowych, opisać zasady wysyłki i zwrotów, odpowiedzi na często zadawane pytania lub dostarczyć zawartość „o nas”.</span><span class="sxs-lookup"><span data-stu-id="abbe5-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="abbe5-114">, Aby dodać niestandardowe komunikaty na stronie szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="abbe5-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="abbe5-115">(na przykład „bezpłatna wysyłka zamówień o wartości ponad $50”).</span><span class="sxs-lookup"><span data-stu-id="abbe5-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="abbe5-116">Dla roszczeń i szczegółów dotyczących kontaktu na stronach szczegółów produktu, na stronach koszyka, na stronach do realizacji transakcji oraz na innych stronach (np. „Wysyłka i zwroty podlegają zasadom sklepu”).</span><span class="sxs-lookup"><span data-stu-id="abbe5-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="abbe5-117">Poniższy obraz pokazuje przykład modułu bloku tekstu, który jest używany na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="abbe5-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Przykład modułu bloku tekstu](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="abbe5-119">Właściwości modułu bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="abbe5-119">Text block module properties</span></span>

| <span data-ttu-id="abbe5-120">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="abbe5-120">Property name</span></span>     | <span data-ttu-id="abbe5-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="abbe5-121">Value</span></span>                                            | <span data-ttu-id="abbe5-122">opis</span><span class="sxs-lookup"><span data-stu-id="abbe5-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="abbe5-123">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="abbe5-123">Rich text</span></span>         | <span data-ttu-id="abbe5-124">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="abbe5-124">Rich text</span></span>                                        | <span data-ttu-id="abbe5-125">Tekst akapitu.</span><span class="sxs-lookup"><span data-stu-id="abbe5-125">Paragraph text.</span></span> <span data-ttu-id="abbe5-126">Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa.</span><span class="sxs-lookup"><span data-stu-id="abbe5-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="abbe5-127">Niestandardowa nazwa klasy</span><span class="sxs-lookup"><span data-stu-id="abbe5-127">Custom class name</span></span> | <span data-ttu-id="abbe5-128">Nazwa klasy arkuszy stylów kaskadowych (CSS)</span><span class="sxs-lookup"><span data-stu-id="abbe5-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="abbe5-129">Nazwa niestandardowej klasy CSS, którą projektant chce sformatować w tym module.</span><span class="sxs-lookup"><span data-stu-id="abbe5-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="abbe5-130">Nazwa klasy powinna być zdefiniowana w pakiecie kompozycji.</span><span class="sxs-lookup"><span data-stu-id="abbe5-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="abbe5-131">Rozmiar czcionki</span><span class="sxs-lookup"><span data-stu-id="abbe5-131">Font size</span></span>         | <span data-ttu-id="abbe5-132">**Małe**, **średnie**, **duże** lub **XL**</span><span class="sxs-lookup"><span data-stu-id="abbe5-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="abbe5-133">Wybierz rozmiar czcionki treści.</span><span class="sxs-lookup"><span data-stu-id="abbe5-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="abbe5-134">Dodawanie bloku zaawansowanej zawartości do nowej strony</span><span class="sxs-lookup"><span data-stu-id="abbe5-134">Add a text block module to a page</span></span>

<span data-ttu-id="abbe5-135">Aby dodać moduł blokuzaawansowanej zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="abbe5-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="abbe5-136">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="abbe5-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="abbe5-137">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** przejdź do **Szablon zawartości**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="abbe5-138">W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="abbe5-139">W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="abbe5-140">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="abbe5-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="abbe5-141">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="abbe5-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="abbe5-142">W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon zawartości**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="abbe5-143">W sekcji **Nazwa strony** przejdź do **Strona zawartości**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="abbe5-144">Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="abbe5-145">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="abbe5-146">W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="abbe5-147">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="abbe5-148">W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="abbe5-149">W okienku właściwości modułu blok tekstu Dodaj tekst do pola **Tekst sformatowany**.</span><span class="sxs-lookup"><span data-stu-id="abbe5-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="abbe5-150">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="abbe5-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="abbe5-151">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="abbe5-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="abbe5-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="abbe5-152">Additional resources</span></span>

[<span data-ttu-id="abbe5-153">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="abbe5-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="abbe5-154">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="abbe5-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="abbe5-155">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="abbe5-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="abbe5-156">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="abbe5-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="abbe5-157">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="abbe5-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]