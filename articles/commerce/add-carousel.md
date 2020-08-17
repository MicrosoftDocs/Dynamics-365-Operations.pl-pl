---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 10ff0cd566a1a8d89ccadce9571dafc5a592520b
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "3620993"
---
# <a name="carousel-module"></a><span data-ttu-id="ff398-103">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="ff398-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff398-104">W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff398-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ff398-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="ff398-105">Overview</span></span>

<span data-ttu-id="ff398-106">Moduł karuzeli służy do umieszczania wielu elementów promocyjnych (w tym obrazów) w obracającej się karuzeli banerów, które mogą być przeglądane przez klientów.</span><span class="sxs-lookup"><span data-stu-id="ff398-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="ff398-107">Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.</span><span class="sxs-lookup"><span data-stu-id="ff398-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="ff398-108">Moduły główne i bloku zawartości można dodawać w module karuzeli.</span><span class="sxs-lookup"><span data-stu-id="ff398-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="ff398-109">Właściwości modułu karuzeli definiują sposób renderowania tych modułów.</span><span class="sxs-lookup"><span data-stu-id="ff398-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="ff398-110">Przykłady modułów karuzeli w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="ff398-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="ff398-111">Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="ff398-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="ff398-112">Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="ff398-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="ff398-113">Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.</span><span class="sxs-lookup"><span data-stu-id="ff398-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="ff398-114">Poniższy obraz pokazuje przykład modułu karuzeli, który jest używany na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="ff398-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="ff398-115">Ten moduł karuzeli zawiera wiele elementów bloków zawartości.</span><span class="sxs-lookup"><span data-stu-id="ff398-115">This carousel module contains multiple content block items.</span></span>

![Przykład modułu karuzeli](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="ff398-117">Właściwości modułu karuzeli</span><span class="sxs-lookup"><span data-stu-id="ff398-117">Carousel module properties</span></span>

| <span data-ttu-id="ff398-118">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="ff398-118">Property name</span></span>             | <span data-ttu-id="ff398-119">Wartość</span><span class="sxs-lookup"><span data-stu-id="ff398-119">Value</span></span>                 | <span data-ttu-id="ff398-120">opis</span><span class="sxs-lookup"><span data-stu-id="ff398-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="ff398-121">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="ff398-121">Autoplay</span></span>                  | <span data-ttu-id="ff398-122">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="ff398-122">**True** or **False**</span></span> | <span data-ttu-id="ff398-123">Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie.</span><span class="sxs-lookup"><span data-stu-id="ff398-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="ff398-124">Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego.</span><span class="sxs-lookup"><span data-stu-id="ff398-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="ff398-125">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="ff398-125">Slide transition interval</span></span> | <span data-ttu-id="ff398-126">Wartość w sekundach</span><span class="sxs-lookup"><span data-stu-id="ff398-126">A value in seconds</span></span>    | <span data-ttu-id="ff398-127">Interwał przejść między elementami.</span><span class="sxs-lookup"><span data-stu-id="ff398-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="ff398-128">Typ zmiany stanu</span><span class="sxs-lookup"><span data-stu-id="ff398-128">Transition type</span></span>           | <span data-ttu-id="ff398-129">**Slajd** lub **efekt zanikania**</span><span class="sxs-lookup"><span data-stu-id="ff398-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="ff398-130">Efekt przejścia między elementami.</span><span class="sxs-lookup"><span data-stu-id="ff398-130">The transition effect between items.</span></span> |
| <span data-ttu-id="ff398-131">Ukryj ramię karuzeli</span><span class="sxs-lookup"><span data-stu-id="ff398-131">Hide carousel flipper</span></span>     | <span data-ttu-id="ff398-132">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="ff398-132">**True** or **False**</span></span> | <span data-ttu-id="ff398-133">Jeśli wartość jest ustawiona na **Prawda**, ramiona karuzeli i wskaźnik sekwencji są ukryte.</span><span class="sxs-lookup"><span data-stu-id="ff398-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="ff398-134">Zezwalaj na odrzucanie karuzeli</span><span class="sxs-lookup"><span data-stu-id="ff398-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="ff398-135">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="ff398-135">**True** or **False**</span></span> | <span data-ttu-id="ff398-136">Jeśli wartość jest ustawiona na **Prawda**, użytkownicy mogą anulować karuzelę.</span><span class="sxs-lookup"><span data-stu-id="ff398-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="ff398-137">Dodawanie modułu karuzeli do strony</span><span class="sxs-lookup"><span data-stu-id="ff398-137">Add a carousel module to a page</span></span>

<span data-ttu-id="ff398-138">Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ff398-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ff398-139">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="ff398-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ff398-140">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon karuzeli**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff398-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="ff398-141">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="ff398-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="ff398-142">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="ff398-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="ff398-143">Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **Strona karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="ff398-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="ff398-144">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="ff398-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="ff398-145">W okienku po prawej stronie określ wartość **Szerokości** jako **ekran wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="ff398-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="ff398-146">W obszarze **Konspekt strony** dodaj moduł karuzeli do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="ff398-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="ff398-147">W module kontenera dodaj moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="ff398-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="ff398-148">Umożliwia ustawienie właściwości modułu blok zawartości przez udostępnienie **nagłówka**, **łącza**, **układu** i innych właściwości.</span><span class="sxs-lookup"><span data-stu-id="ff398-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="ff398-149">Dodaj i skonfiguruj inny moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="ff398-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="ff398-150">W razie potrzeby skonfiguruj dodatkowe właściwości dla modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="ff398-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="ff398-151">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="ff398-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="ff398-152">Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji).</span><span class="sxs-lookup"><span data-stu-id="ff398-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="ff398-153">Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.</span><span class="sxs-lookup"><span data-stu-id="ff398-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="ff398-154">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="ff398-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff398-155">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ff398-155">Additional resources</span></span>

[<span data-ttu-id="ff398-156">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="ff398-156">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ff398-157">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="ff398-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="ff398-158">Moduł bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="ff398-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="ff398-159">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="ff398-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="ff398-160">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="ff398-160">Video player module</span></span>](add-video-player.md)
