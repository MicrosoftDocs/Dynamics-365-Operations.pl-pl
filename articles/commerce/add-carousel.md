---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785244"
---
# <a name="carousel-module"></a><span data-ttu-id="e8794-103">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="e8794-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e8794-104">W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e8794-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e8794-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="e8794-105">Overview</span></span>

<span data-ttu-id="e8794-106">Moduł karuzeli służy do umieszczania wielu elementów promocyjnych w karuzeli, które mogą być przeglądane przez klientów.</span><span class="sxs-lookup"><span data-stu-id="e8794-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="e8794-107">Jest to specjalny moduł kontenera, który obsługuje inne moduły.</span><span class="sxs-lookup"><span data-stu-id="e8794-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="e8794-108">Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.</span><span class="sxs-lookup"><span data-stu-id="e8794-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="e8794-109">Moduły główne i funkcji można dodawać w module karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="e8794-110">Właściwości modułu karuzeli definiują sposób renderowania tych modułów.</span><span class="sxs-lookup"><span data-stu-id="e8794-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="e8794-111">Przykłady modułów karuzeli w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="e8794-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="e8794-112">Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="e8794-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="e8794-113">Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="e8794-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="e8794-114">Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.</span><span class="sxs-lookup"><span data-stu-id="e8794-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="e8794-115">Właściwości modułu karuzeli</span><span class="sxs-lookup"><span data-stu-id="e8794-115">Carousel module properties</span></span>

| <span data-ttu-id="e8794-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="e8794-116">Property name</span></span>             | <span data-ttu-id="e8794-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="e8794-117">Value</span></span>                                | <span data-ttu-id="e8794-118">Opis</span><span class="sxs-lookup"><span data-stu-id="e8794-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="e8794-119">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="e8794-119">Autoplay</span></span>                  | <span data-ttu-id="e8794-120">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="e8794-120">**True** or **False**</span></span>                | <span data-ttu-id="e8794-121">Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie.</span><span class="sxs-lookup"><span data-stu-id="e8794-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="e8794-122">Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego.</span><span class="sxs-lookup"><span data-stu-id="e8794-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="e8794-123">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="e8794-123">Slide transition interval</span></span> | <span data-ttu-id="e8794-124">Wartość w sekundach</span><span class="sxs-lookup"><span data-stu-id="e8794-124">A value in seconds</span></span>                   | <span data-ttu-id="e8794-125">Interwał przejść między elementami.</span><span class="sxs-lookup"><span data-stu-id="e8794-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="e8794-126">Animacja przejścia</span><span class="sxs-lookup"><span data-stu-id="e8794-126">Transition animation</span></span>      | <span data-ttu-id="e8794-127">**Slajd** lub **efekt zanikania**</span><span class="sxs-lookup"><span data-stu-id="e8794-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="e8794-128">Efekt przejścia.</span><span class="sxs-lookup"><span data-stu-id="e8794-128">The transition effect.</span></span> |
| <span data-ttu-id="e8794-129">Szerokość</span><span class="sxs-lookup"><span data-stu-id="e8794-129">Width</span></span>                     | <span data-ttu-id="e8794-130">**Dopasuj do kontenera** lub **ekran wypełnienia**</span><span class="sxs-lookup"><span data-stu-id="e8794-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="e8794-131">Jeśli wartość jest ustawiona na **dopasowana do kontenera**, elementy wewnątrz karuzeli są ograniczone do szerokości karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="e8794-132">Jeśli wartość jest ustawiona na **wypełnienie ekranu**, elementy nie są ograniczone do szerokości karuzeli, ale mogą przechodzić do trybu pełnoekranowego.</span><span class="sxs-lookup"><span data-stu-id="e8794-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="e8794-133">Można zmienić wartość, aby uzyskać odpowiedni układ.</span><span class="sxs-lookup"><span data-stu-id="e8794-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="e8794-134">Dodawanie modułu karuzeli do strony</span><span class="sxs-lookup"><span data-stu-id="e8794-134">Add a carousel module to a page</span></span>

<span data-ttu-id="e8794-135">Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8794-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e8794-136">Utwórz szablon strony o nazwie nazwa **szablon karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="e8794-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="e8794-137">W **Głównym** gnieździe na stronie domyślnej dodaj moduł karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="e8794-138">Dodaj moduł główny do modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="e8794-139">Dodaj moduł funkcji do modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="e8794-140">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="e8794-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="e8794-141">Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **strona karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="e8794-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="e8794-142">W **Głównym** gnieździe na nowej stronie dodaj moduł karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="e8794-143">Umożliwia ustawienie właściwości **szerokość** modułu karuzela na **ekran wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="e8794-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="e8794-144">Umożliwia ustawienie właściwości **animacji przejścia** na **slajd**.</span><span class="sxs-lookup"><span data-stu-id="e8794-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="e8794-145">Dodaj moduł główny do modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="e8794-146">W module głównym dodaj obraz i nagłówek, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8794-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="e8794-147">Dodaj moduł funkcji do modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="e8794-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="e8794-148">Umożliwia dodanie obrazu, nagłówka i akapitu tekstu w module funkcji.</span><span class="sxs-lookup"><span data-stu-id="e8794-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="e8794-149">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="e8794-149">Save and preview the page.</span></span> <span data-ttu-id="e8794-150">Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji).</span><span class="sxs-lookup"><span data-stu-id="e8794-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="e8794-151">Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.</span><span class="sxs-lookup"><span data-stu-id="e8794-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="e8794-152">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="e8794-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8794-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e8794-153">Additional resources</span></span>

[<span data-ttu-id="e8794-154">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="e8794-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e8794-155">Moduł alertów</span><span class="sxs-lookup"><span data-stu-id="e8794-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="e8794-156">Moduł zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="e8794-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="e8794-157">Moduł umieszczania zawartości</span><span class="sxs-lookup"><span data-stu-id="e8794-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="e8794-158">Moduł funkcji</span><span class="sxs-lookup"><span data-stu-id="e8794-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="e8794-159">Moduł bohatera</span><span class="sxs-lookup"><span data-stu-id="e8794-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="e8794-160">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="e8794-160">Video player module</span></span>](add-video-player.md)
