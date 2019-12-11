---
title: Moduł bohatera
description: W tym temacie opisano moduły bohatera i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785404"
---
# <a name="hero-module"></a><span data-ttu-id="f7629-103">Moduł bohatera</span><span class="sxs-lookup"><span data-stu-id="f7629-103">Hero module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f7629-104">W tym temacie opisano moduły bohatera i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7629-104">This topic covers hero modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f7629-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f7629-105">Overview</span></span>

<span data-ttu-id="f7629-106">Moduł bohatera jest używany do marketingowych produktów lub promocji przy użyciu kombinacji obrazów i tekstu.</span><span class="sxs-lookup"><span data-stu-id="f7629-106">A hero module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="f7629-107">Na przykład sprzedawca może dodać moduł bohatera do strony głównej witryny e-Commerce, aby promować nowy produkt i zwrócić uwagę odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f7629-107">For example, a retailer can add a hero module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="f7629-108">Moduł bohatera jest sterowany przez dane z systemu zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="f7629-108">A hero module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="f7629-109">Jest to samodzielny moduł, który nie zależy od innych modułów na stronie.</span><span class="sxs-lookup"><span data-stu-id="f7629-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="f7629-110">Moduł Hero można umieścić na dowolnej stronie witryny, w której detalista chce dokonać obrotu lub promować coś (na przykład produktów, sprzedaży lub funkcji).</span><span class="sxs-lookup"><span data-stu-id="f7629-110">A hero module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-hero-module-in-e-commerce"></a><span data-ttu-id="f7629-111">Przykłady modułów bohatera w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="f7629-111">Examples of hero module in e-Commerce</span></span>

- <span data-ttu-id="f7629-112">Moduł bohatera może być używany na stronie głównej witryny e-Commerce w celu wyróżnienia promocji i nowych produktów.</span><span class="sxs-lookup"><span data-stu-id="f7629-112">A hero module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="f7629-113">Moduł bohatera może być używany na stronie Szczegóły produktu w celu zaprezentowania informacji o produkcie.</span><span class="sxs-lookup"><span data-stu-id="f7629-113">A hero module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="f7629-114">W module bohatera można umieścić wiele modułów bohatera w celu wyróżnienia wielu produktów lub promocji.</span><span class="sxs-lookup"><span data-stu-id="f7629-114">Multiple hero modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="hero-module-properties"></a><span data-ttu-id="f7629-115">Właściwości modułu bohatera</span><span class="sxs-lookup"><span data-stu-id="f7629-115">Hero module properties</span></span>

| <span data-ttu-id="f7629-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="f7629-116">Property name</span></span>  | <span data-ttu-id="f7629-117">Wartości</span><span class="sxs-lookup"><span data-stu-id="f7629-117">Values</span></span> | <span data-ttu-id="f7629-118">Opis</span><span class="sxs-lookup"><span data-stu-id="f7629-118">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="f7629-119">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="f7629-119">Image</span></span>          | <span data-ttu-id="f7629-120">Plik obrazu</span><span class="sxs-lookup"><span data-stu-id="f7629-120">Image file</span></span> | <span data-ttu-id="f7629-121">Obraz może służyć do pokazania produktu lub promocji.</span><span class="sxs-lookup"><span data-stu-id="f7629-121">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="f7629-122">Obraz można przekazać do galerii obrazów lub można użyć istniejącego obrazu.</span><span class="sxs-lookup"><span data-stu-id="f7629-122">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="f7629-123">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="f7629-123">Heading</span></span>        | <span data-ttu-id="f7629-124">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="f7629-124">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="f7629-125">Każdy moduł bohatera może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="f7629-125">Every hero module can have a heading.</span></span> <span data-ttu-id="f7629-126">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="f7629-126">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="f7629-127">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="f7629-127">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="f7629-128">Akapit</span><span class="sxs-lookup"><span data-stu-id="f7629-128">Paragraph</span></span>      | <span data-ttu-id="f7629-129">Tekst akapitu</span><span class="sxs-lookup"><span data-stu-id="f7629-129">Paragraph text</span></span> | <span data-ttu-id="f7629-130">Moduły bohatera obsługują tekst akapitu w formacie RTF.</span><span class="sxs-lookup"><span data-stu-id="f7629-130">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="f7629-131">Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony, kursywa i hiperłącza.</span><span class="sxs-lookup"><span data-stu-id="f7629-131">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="f7629-132">Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu.</span><span class="sxs-lookup"><span data-stu-id="f7629-132">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="f7629-133">Link</span><span class="sxs-lookup"><span data-stu-id="f7629-133">Link</span></span>           | <span data-ttu-id="f7629-134">Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) **i Otwórz łącze na nowej karcie**</span><span class="sxs-lookup"><span data-stu-id="f7629-134">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="f7629-135">Moduły bohatera obsługują łącza do jednego lub wielu „wywołań akcji”.</span><span class="sxs-lookup"><span data-stu-id="f7629-135">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="f7629-136">Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane.</span><span class="sxs-lookup"><span data-stu-id="f7629-136">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="f7629-137">Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu.</span><span class="sxs-lookup"><span data-stu-id="f7629-137">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="f7629-138">Łącza można tak skonfigurować, aby były otwierane na nowej karcie.</span><span class="sxs-lookup"><span data-stu-id="f7629-138">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="f7629-139">Umiejscowienie tekstu</span><span class="sxs-lookup"><span data-stu-id="f7629-139">Text placement</span></span> | <span data-ttu-id="f7629-140">**Lewy górny**, **prawy górny**, **górny środkowy**, **lewy dolny**, **dolny prawy**, **dolny środkowy**, **lewy środkowy**, **prawy środkowy** lub **środkowy**</span><span class="sxs-lookup"><span data-stu-id="f7629-140">**Top Left**, **Top Right**, **Top Center**, **Bottom Left**, **Bottom Right**, **Bottom Center**, **Center Left**, **Center Right**, or **Center Center**</span></span> | <span data-ttu-id="f7629-141">Właściwość ta określa pozycję obrazu w odniesieniu do tekstu.</span><span class="sxs-lookup"><span data-stu-id="f7629-141">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="f7629-142">Jeśli na przykład zaznaczona jest opcja po **prawej** stronie, obraz pojawi się po prawej stronie tekstu.</span><span class="sxs-lookup"><span data-stu-id="f7629-142">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="f7629-143">Motyw tekstu</span><span class="sxs-lookup"><span data-stu-id="f7629-143">Text theme</span></span>     | <span data-ttu-id="f7629-144">**Jasny** lub **ciemny**</span><span class="sxs-lookup"><span data-stu-id="f7629-144">**Light** or **Dark**</span></span> | <span data-ttu-id="f7629-145">Schemat kolorów może zostać zdefiniowany dla tekstu na podstawie obrazu tła.</span><span class="sxs-lookup"><span data-stu-id="f7629-145">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="f7629-146">Na przykład, jeśli obraz ma ciemne tło, można zastosować motyw jasny, aby tekst był bardziej widoczny i spełniał proporcje kolorów dla celów ułatwień dostępu.</span><span class="sxs-lookup"><span data-stu-id="f7629-146">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> |
| <span data-ttu-id="f7629-147">Gradient</span><span class="sxs-lookup"><span data-stu-id="f7629-147">Gradient</span></span>       | <span data-ttu-id="f7629-148">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="f7629-148">**True** or **False**</span></span> | <span data-ttu-id="f7629-149">Gradient można zastosować do obrazu w celu spełnienia współczynnika kontrastu kolorów w celach ułatwień dostępu.</span><span class="sxs-lookup"><span data-stu-id="f7629-149">A gradient can be applied to the image to meet color contrast ratios for accessibility purposes.</span></span> |

## <a name="add-a-hero-module-to-a-new-page"></a><span data-ttu-id="f7629-150">Dodawanie modułu bohatera do nowej strony</span><span class="sxs-lookup"><span data-stu-id="f7629-150">Add a hero module to a new page</span></span>

<span data-ttu-id="f7629-151">Aby dodać moduł bohatera do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f7629-151">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="f7629-152">Przejdź do **Szablonów**i utwórz szablon strony o nazwie **szablon bohatera**.</span><span class="sxs-lookup"><span data-stu-id="f7629-152">Go to **Templates**, and create a page template that is named **hero template**.</span></span>
1. <span data-ttu-id="f7629-153">W **Głównym** gnieździe na stronie domyślnej dodaj moduł bohatera.</span><span class="sxs-lookup"><span data-stu-id="f7629-153">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="f7629-154">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="f7629-154">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="f7629-155">Za pomocą utworzonego właśnie szblonu bohatera utwórz stronę o nazwie **strona bohatera**.</span><span class="sxs-lookup"><span data-stu-id="f7629-155">Use the hero template that you just created to create a page that is named **hero page**.</span></span>
1. <span data-ttu-id="f7629-156">Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="f7629-156">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7629-157">W oknie dialogowym **Dodawanie modułu** w obszarze **Wybierz moduły** wybierz moduł bohatera i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7629-157">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7629-158">W drzewie konspektu po lewej wybierz moduł bohatera.</span><span class="sxs-lookup"><span data-stu-id="f7629-158">In the outline tree on the left, select the hero module.</span></span>
1. <span data-ttu-id="f7629-159">W panelu właściwości po prawej wybierz **Dodaj obraz**.</span><span class="sxs-lookup"><span data-stu-id="f7629-159">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="f7629-160">Następnie należy wybrać istniejący obraz lub przekazać nowy obraz.</span><span class="sxs-lookup"><span data-stu-id="f7629-160">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="f7629-161">Wybierz **Nagłówek**.</span><span class="sxs-lookup"><span data-stu-id="f7629-161">Select **Heading**.</span></span>
1. <span data-ttu-id="f7629-162">W oknie dialogowym **nagłówek** dodaj tekst nagłówka, wybierz poziom nagłówka, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7629-162">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="f7629-163">W obszarze **tekst sformatowany**,dodaj tekst w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="f7629-163">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="f7629-164">Wybierz **łącze dodaj akcję**.</span><span class="sxs-lookup"><span data-stu-id="f7629-164">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="f7629-165">W oknie dialogowym **łącze akcji** dodaj tekst łącza, adres URL łącza oraz etykietę Aria dla łącza, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7629-165">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="f7629-166">Zapisz stronę i wyświetl podgląd zmian.</span><span class="sxs-lookup"><span data-stu-id="f7629-166">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="f7629-167">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="f7629-167">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7629-168">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f7629-168">Additional resources</span></span>

[<span data-ttu-id="f7629-169">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="f7629-169">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f7629-170">Moduł alertów</span><span class="sxs-lookup"><span data-stu-id="f7629-170">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="f7629-171">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="f7629-171">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="f7629-172">Moduł zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="f7629-172">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="f7629-173">Moduł umieszczania zawartości</span><span class="sxs-lookup"><span data-stu-id="f7629-173">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="f7629-174">Moduł funkcji</span><span class="sxs-lookup"><span data-stu-id="f7629-174">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="f7629-175">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="f7629-175">Video player module</span></span>](add-video-player.md)
