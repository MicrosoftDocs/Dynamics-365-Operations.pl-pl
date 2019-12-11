---
title: Moduł funkcji
description: W tym temacie opisano moduły funkcji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785313"
---
# <a name="feature-module"></a><span data-ttu-id="c3401-103">Moduł funkcji</span><span class="sxs-lookup"><span data-stu-id="c3401-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c3401-104">W tym temacie opisano moduły funkcji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3401-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c3401-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c3401-105">Overview</span></span>

<span data-ttu-id="c3401-106">Moduł funkcji jest używany do marketingowych produktów lub promocji przy użyciu kombinacji obrazów i tekstu.</span><span class="sxs-lookup"><span data-stu-id="c3401-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="c3401-107">Na przykład sprzedawca może dodać moduł funkcji do strony Szczegóły produktu, aby wyróżnić funkcje produktu.</span><span class="sxs-lookup"><span data-stu-id="c3401-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="c3401-108">Moduł funkcji jest sterowany przez dane z systemu zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="c3401-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="c3401-109">Jest to samodzielny moduł, który nie zależy od innych modułów na stronie.</span><span class="sxs-lookup"><span data-stu-id="c3401-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="c3401-110">Moduł funkcji można umieścić na dowolnej stronie witryny, w której detalista chce dokonać obrotu lub promować coś (na przykład produktów, sprzedaży lub funkcji).</span><span class="sxs-lookup"><span data-stu-id="c3401-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="c3401-111">Przykłady modułów funkcji w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="c3401-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="c3401-112">Moduł funkcji może być używany na następujących stronach:</span><span class="sxs-lookup"><span data-stu-id="c3401-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="c3401-113">Strona szczegóły produktu, w celu zaprezentowania funkcji produktu</span><span class="sxs-lookup"><span data-stu-id="c3401-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="c3401-114">Strona główna, aby promować produkty</span><span class="sxs-lookup"><span data-stu-id="c3401-114">The home page, to promote products</span></span>
- <span data-ttu-id="c3401-115">Strona kategorii w celu wyróżnienia kategorii produktów</span><span class="sxs-lookup"><span data-stu-id="c3401-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="c3401-116">Właściwości modułu funkcji</span><span class="sxs-lookup"><span data-stu-id="c3401-116">Feature module properties</span></span>

| <span data-ttu-id="c3401-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="c3401-117">Property name</span></span>     | <span data-ttu-id="c3401-118">Wartości</span><span class="sxs-lookup"><span data-stu-id="c3401-118">Values</span></span> | <span data-ttu-id="c3401-119">Opis</span><span class="sxs-lookup"><span data-stu-id="c3401-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="c3401-120">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="c3401-120">Image</span></span>             | <span data-ttu-id="c3401-121">Plik obrazu</span><span class="sxs-lookup"><span data-stu-id="c3401-121">Image file</span></span> | <span data-ttu-id="c3401-122">Obraz może służyć do reklamy produktu lub promocji.</span><span class="sxs-lookup"><span data-stu-id="c3401-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="c3401-123">Obraz można przekazać do galerii obrazów lub można użyć istniejącego obrazu.</span><span class="sxs-lookup"><span data-stu-id="c3401-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="c3401-124">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="c3401-124">Heading</span></span>           | <span data-ttu-id="c3401-125">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="c3401-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="c3401-126">Każdy moduł funkcji może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="c3401-126">Every feature module can have a heading.</span></span> <span data-ttu-id="c3401-127">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="c3401-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="c3401-128">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="c3401-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="c3401-129">Akapit</span><span class="sxs-lookup"><span data-stu-id="c3401-129">Paragraph</span></span>         | <span data-ttu-id="c3401-130">Tekst akapitu</span><span class="sxs-lookup"><span data-stu-id="c3401-130">Paragraph text</span></span> | <span data-ttu-id="c3401-131">Moduły funkcji obsługują tekst akapitu w formacie RTF.</span><span class="sxs-lookup"><span data-stu-id="c3401-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="c3401-132">Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony, kursywa i hiperłącza.</span><span class="sxs-lookup"><span data-stu-id="c3401-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="c3401-133">Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu.</span><span class="sxs-lookup"><span data-stu-id="c3401-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="c3401-134">Link</span><span class="sxs-lookup"><span data-stu-id="c3401-134">Link</span></span>              | <span data-ttu-id="c3401-135">Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) **i Otwórz łącze na nowej karcie**</span><span class="sxs-lookup"><span data-stu-id="c3401-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="c3401-136">Moduły funkcji obsługują łącza do jednego lub wielu „wywołań akcji”.</span><span class="sxs-lookup"><span data-stu-id="c3401-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="c3401-137">Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane.</span><span class="sxs-lookup"><span data-stu-id="c3401-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="c3401-138">Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu.</span><span class="sxs-lookup"><span data-stu-id="c3401-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="c3401-139">Łącza można tak skonfigurować, aby były otwierane na nowej karcie.</span><span class="sxs-lookup"><span data-stu-id="c3401-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="c3401-140">Umiejscowienie obrazu</span><span class="sxs-lookup"><span data-stu-id="c3401-140">Image placement</span></span>   | <span data-ttu-id="c3401-141">**Prawy**, **lewy**, **górny** lub **dolny**</span><span class="sxs-lookup"><span data-stu-id="c3401-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="c3401-142">Właściwość ta określa pozycję obrazu w odniesieniu do tekstu.</span><span class="sxs-lookup"><span data-stu-id="c3401-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="c3401-143">Jeśli na przykład zaznaczona jest opcja po **prawej** stronie, obraz pojawi się po prawej stronie tekstu.</span><span class="sxs-lookup"><span data-stu-id="c3401-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="c3401-144">Rozmiar kolumny obrazu</span><span class="sxs-lookup"><span data-stu-id="c3401-144">Image column size</span></span> | <span data-ttu-id="c3401-145">Wartość z zakresu od **1** do **12**</span><span class="sxs-lookup"><span data-stu-id="c3401-145">A value from **1** through **12**</span></span> | <span data-ttu-id="c3401-146">Właściwość ta określa wielkość obrazu w odniesieniu do tekstu.</span><span class="sxs-lookup"><span data-stu-id="c3401-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="c3401-147">Rozmiar jest wyrażony jako liczba kolumn na stronie.</span><span class="sxs-lookup"><span data-stu-id="c3401-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="c3401-148">Na stronie znajduje się 12 kolumn.</span><span class="sxs-lookup"><span data-stu-id="c3401-148">There are 12 columns on a page.</span></span> <span data-ttu-id="c3401-149">Domyślnie obraz i tekst mają równy rozmiar (co sześć kolumn).</span><span class="sxs-lookup"><span data-stu-id="c3401-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="c3401-150">Jednak rozmiar można skorygować w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="c3401-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="c3401-151">Dodawanie modułu funkcji do nowej strony</span><span class="sxs-lookup"><span data-stu-id="c3401-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="c3401-152">Aby dodać moduł funkcji do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c3401-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c3401-153">Przejdź do **Szablonów**i utwórz szablon strony o nazwie **szablon funkcji**.</span><span class="sxs-lookup"><span data-stu-id="c3401-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="c3401-154">W **Głównym** gnieździe na stronie domyślnej dodaj moduł funkcji.</span><span class="sxs-lookup"><span data-stu-id="c3401-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="c3401-155">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="c3401-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="c3401-156">Za pomocą utworzonego właśnie szblonu funkcji utwórz stronę o nazwie **strona funkcji**.</span><span class="sxs-lookup"><span data-stu-id="c3401-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="c3401-157">Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c3401-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c3401-158">W oknie dialogowym **Dodawanie modułu** w obszarze **Wybierz moduły** wybierz moduł funkcji i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3401-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="c3401-159">W drzewie konspektu po lewej wybierz moduł funkcji.</span><span class="sxs-lookup"><span data-stu-id="c3401-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="c3401-160">W panelu właściwości po prawej wybierz **Dodaj obraz**.</span><span class="sxs-lookup"><span data-stu-id="c3401-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="c3401-161">Następnie należy wybrać istniejący obraz lub przekazać nowy obraz.</span><span class="sxs-lookup"><span data-stu-id="c3401-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="c3401-162">Wybierz **Nagłówek**.</span><span class="sxs-lookup"><span data-stu-id="c3401-162">Select **Heading**.</span></span>
1. <span data-ttu-id="c3401-163">W oknie dialogowym **nagłówek** dodaj tekst nagłówka, wybierz poziom nagłówka, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3401-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="c3401-164">W obszarze **tekst sformatowany**,dodaj tekst w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="c3401-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="c3401-165">Wybierz **łącze dodaj akcję**.</span><span class="sxs-lookup"><span data-stu-id="c3401-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="c3401-166">W oknie dialogowym **łącze akcji** dodaj tekst łącza, adres URL łącza oraz etykietę Aria dla łącza, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3401-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="c3401-167">Zapisz stronę i wyświetl podgląd zmian.</span><span class="sxs-lookup"><span data-stu-id="c3401-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="c3401-168">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="c3401-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3401-169">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c3401-169">Additional resources</span></span>

[<span data-ttu-id="c3401-170">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="c3401-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c3401-171">Moduł alertów</span><span class="sxs-lookup"><span data-stu-id="c3401-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="c3401-172">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="c3401-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="c3401-173">Moduł zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="c3401-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="c3401-174">Moduł umieszczania zawartości</span><span class="sxs-lookup"><span data-stu-id="c3401-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="c3401-175">Moduł bohatera</span><span class="sxs-lookup"><span data-stu-id="c3401-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="c3401-176">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="c3401-176">Video player module</span></span>](add-video-player.md)
