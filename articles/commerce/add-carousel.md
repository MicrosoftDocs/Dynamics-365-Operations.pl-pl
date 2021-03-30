---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5333ecd7a1fe4f60684fa5f5bb3ac9f98efde6d7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206518"
---
# <a name="carousel-module"></a><span data-ttu-id="d39fe-103">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="d39fe-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d39fe-104">W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d39fe-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d39fe-105">Moduł karuzeli służy do umieszczania wielu elementów promocyjnych (w tym obrazów) w obracającej się karuzeli banerów, które mogą być przeglądane przez klientów.</span><span class="sxs-lookup"><span data-stu-id="d39fe-105">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="d39fe-106">Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.</span><span class="sxs-lookup"><span data-stu-id="d39fe-106">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="d39fe-107">Moduły główne i bloku zawartości można dodawać w module karuzeli.</span><span class="sxs-lookup"><span data-stu-id="d39fe-107">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="d39fe-108">Właściwości modułu karuzeli definiują sposób renderowania tych modułów.</span><span class="sxs-lookup"><span data-stu-id="d39fe-108">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="d39fe-109">Przykłady modułów karuzeli w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="d39fe-109">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="d39fe-110">Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="d39fe-110">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="d39fe-111">Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="d39fe-111">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="d39fe-112">Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.</span><span class="sxs-lookup"><span data-stu-id="d39fe-112">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="d39fe-113">Poniższy obraz pokazuje przykład modułu karuzeli, który jest używany na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="d39fe-113">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="d39fe-114">Ten moduł karuzeli zawiera wiele elementów bloków zawartości.</span><span class="sxs-lookup"><span data-stu-id="d39fe-114">This carousel module contains multiple content block items.</span></span>

![Przykład modułu karuzeli](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="d39fe-116">Właściwości modułu karuzeli</span><span class="sxs-lookup"><span data-stu-id="d39fe-116">Carousel module properties</span></span>

| <span data-ttu-id="d39fe-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="d39fe-117">Property name</span></span>             | <span data-ttu-id="d39fe-118">Wartość</span><span class="sxs-lookup"><span data-stu-id="d39fe-118">Value</span></span>                 | <span data-ttu-id="d39fe-119">opis</span><span class="sxs-lookup"><span data-stu-id="d39fe-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="d39fe-120">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="d39fe-120">Autoplay</span></span>                  | <span data-ttu-id="d39fe-121">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="d39fe-121">**True** or **False**</span></span> | <span data-ttu-id="d39fe-122">Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie.</span><span class="sxs-lookup"><span data-stu-id="d39fe-122">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="d39fe-123">Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego.</span><span class="sxs-lookup"><span data-stu-id="d39fe-123">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="d39fe-124">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="d39fe-124">Slide transition interval</span></span> | <span data-ttu-id="d39fe-125">Wartość w sekundach</span><span class="sxs-lookup"><span data-stu-id="d39fe-125">A value in seconds</span></span>    | <span data-ttu-id="d39fe-126">Interwał przejść między elementami.</span><span class="sxs-lookup"><span data-stu-id="d39fe-126">The interval for transitions between items.</span></span> |
| <span data-ttu-id="d39fe-127">Typ zmiany stanu</span><span class="sxs-lookup"><span data-stu-id="d39fe-127">Transition type</span></span>           | <span data-ttu-id="d39fe-128">**Slajd** lub **efekt zanikania**</span><span class="sxs-lookup"><span data-stu-id="d39fe-128">**Slide** or **Fade**</span></span> | <span data-ttu-id="d39fe-129">Efekt przejścia między elementami.</span><span class="sxs-lookup"><span data-stu-id="d39fe-129">The transition effect between items.</span></span> |
| <span data-ttu-id="d39fe-130">Ukryj ramię karuzeli</span><span class="sxs-lookup"><span data-stu-id="d39fe-130">Hide carousel flipper</span></span>     | <span data-ttu-id="d39fe-131">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="d39fe-131">**True** or **False**</span></span> | <span data-ttu-id="d39fe-132">Jeśli wartość jest ustawiona na **Prawda**, ramiona karuzeli i wskaźnik sekwencji są ukryte.</span><span class="sxs-lookup"><span data-stu-id="d39fe-132">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="d39fe-133">Zezwalaj na odrzucanie karuzeli</span><span class="sxs-lookup"><span data-stu-id="d39fe-133">Allow carousel dismiss</span></span>    | <span data-ttu-id="d39fe-134">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="d39fe-134">**True** or **False**</span></span> | <span data-ttu-id="d39fe-135">Jeśli wartość jest ustawiona na **Prawda**, użytkownicy mogą anulować karuzelę.</span><span class="sxs-lookup"><span data-stu-id="d39fe-135">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="d39fe-136">Dodawanie modułu karuzeli do strony</span><span class="sxs-lookup"><span data-stu-id="d39fe-136">Add a carousel module to a page</span></span>

<span data-ttu-id="d39fe-137">Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d39fe-137">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="d39fe-138">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="d39fe-138">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="d39fe-139">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon karuzeli**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="d39fe-139">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="d39fe-140">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="d39fe-140">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="d39fe-141">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="d39fe-141">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="d39fe-142">Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **Strona karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="d39fe-142">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="d39fe-143">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="d39fe-143">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="d39fe-144">W okienku po prawej stronie określ wartość **Szerokości** jako **ekran wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="d39fe-144">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="d39fe-145">W obszarze **Konspekt strony** dodaj moduł karuzeli do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="d39fe-145">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="d39fe-146">W module kontenera dodaj moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="d39fe-146">Add a content block module to the carousel module.</span></span> <span data-ttu-id="d39fe-147">Umożliwia ustawienie właściwości modułu blok zawartości przez udostępnienie **nagłówka**, **łącza**, **układu** i innych właściwości.</span><span class="sxs-lookup"><span data-stu-id="d39fe-147">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="d39fe-148">Dodaj i skonfiguruj inny moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="d39fe-148">Add and configure another content block module.</span></span>
1. <span data-ttu-id="d39fe-149">W razie potrzeby skonfiguruj dodatkowe właściwości dla modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="d39fe-149">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="d39fe-150">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="d39fe-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="d39fe-151">Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji).</span><span class="sxs-lookup"><span data-stu-id="d39fe-151">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="d39fe-152">Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.</span><span class="sxs-lookup"><span data-stu-id="d39fe-152">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="d39fe-153">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="d39fe-153">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d39fe-154">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d39fe-154">Additional resources</span></span>

[<span data-ttu-id="d39fe-155">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="d39fe-155">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d39fe-156">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="d39fe-156">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="d39fe-157">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="d39fe-157">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="d39fe-158">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="d39fe-158">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="d39fe-159">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="d39fe-159">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]