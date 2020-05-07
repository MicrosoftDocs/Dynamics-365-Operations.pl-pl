---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: f399e4c5618b65b781fdd3ec835e841614579313
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269735"
---
# <a name="carousel-module"></a><span data-ttu-id="1671b-103">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="1671b-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="1671b-104">W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1671b-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1671b-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="1671b-105">Overview</span></span>

<span data-ttu-id="1671b-106">Moduł karuzeli służy do umieszczania wielu elementów promocyjnych (w tym obrazów) w obracającej się karuzeli banerów, które mogą być przeglądane przez klientów.</span><span class="sxs-lookup"><span data-stu-id="1671b-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="1671b-107">Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.</span><span class="sxs-lookup"><span data-stu-id="1671b-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="1671b-108">Moduły główne i bloku zawartości można dodawać w module karuzeli.</span><span class="sxs-lookup"><span data-stu-id="1671b-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="1671b-109">Właściwości modułu karuzeli definiują sposób renderowania tych modułów.</span><span class="sxs-lookup"><span data-stu-id="1671b-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="1671b-110">Przykłady modułów karuzeli w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="1671b-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="1671b-111">Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="1671b-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="1671b-112">Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="1671b-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="1671b-113">Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.</span><span class="sxs-lookup"><span data-stu-id="1671b-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="1671b-114">Właściwości modułu karuzeli</span><span class="sxs-lookup"><span data-stu-id="1671b-114">Carousel module properties</span></span>

| <span data-ttu-id="1671b-115">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1671b-115">Property name</span></span>             | <span data-ttu-id="1671b-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="1671b-116">Value</span></span>                 | <span data-ttu-id="1671b-117">Opis</span><span class="sxs-lookup"><span data-stu-id="1671b-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="1671b-118">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="1671b-118">Autoplay</span></span>                  | <span data-ttu-id="1671b-119">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="1671b-119">**True** or **False**</span></span> | <span data-ttu-id="1671b-120">Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie.</span><span class="sxs-lookup"><span data-stu-id="1671b-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="1671b-121">Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego.</span><span class="sxs-lookup"><span data-stu-id="1671b-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="1671b-122">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="1671b-122">Slide transition interval</span></span> | <span data-ttu-id="1671b-123">Wartość w sekundach</span><span class="sxs-lookup"><span data-stu-id="1671b-123">A value in seconds</span></span>    | <span data-ttu-id="1671b-124">Interwał przejść między elementami.</span><span class="sxs-lookup"><span data-stu-id="1671b-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="1671b-125">Typ zmiany stanu</span><span class="sxs-lookup"><span data-stu-id="1671b-125">Transition type</span></span>           | <span data-ttu-id="1671b-126">**Slajd** lub **efekt zanikania**</span><span class="sxs-lookup"><span data-stu-id="1671b-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="1671b-127">Efekt przejścia między elementami.</span><span class="sxs-lookup"><span data-stu-id="1671b-127">The transition effect between items.</span></span> |
| <span data-ttu-id="1671b-128">Ukryj ramię karuzeli</span><span class="sxs-lookup"><span data-stu-id="1671b-128">Hide carousel flipper</span></span>     | <span data-ttu-id="1671b-129">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="1671b-129">**True** or **False**</span></span> | <span data-ttu-id="1671b-130">Jeśli wartość jest ustawiona na **Prawda**, ramiona karuzeli i wskaźnik sekwencji są ukryte.</span><span class="sxs-lookup"><span data-stu-id="1671b-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="1671b-131">Zezwalaj na odrzucanie karuzeli</span><span class="sxs-lookup"><span data-stu-id="1671b-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="1671b-132">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="1671b-132">**True** or **False**</span></span> | <span data-ttu-id="1671b-133">Jeśli wartość jest ustawiona na **Prawda**, użytkownicy mogą anulować karuzelę.</span><span class="sxs-lookup"><span data-stu-id="1671b-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="1671b-134">Dodawanie modułu karuzeli do strony</span><span class="sxs-lookup"><span data-stu-id="1671b-134">Add a carousel module to a page</span></span>

<span data-ttu-id="1671b-135">Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1671b-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="1671b-136">Wybierz pozycję **Nowy**, aby utworzyć nowy szablon strony.</span><span class="sxs-lookup"><span data-stu-id="1671b-136">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="1671b-137">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon karuzeli**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1671b-137">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="1671b-138">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="1671b-138">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="1671b-139">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1671b-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="1671b-140">Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **Strona karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="1671b-140">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="1671b-141">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="1671b-141">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="1671b-142">W okienku po prawej stronie określ wartość **Szerokości** jako **ekran wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="1671b-142">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="1671b-143">W obszarze **Konspekt strony** dodaj moduł karuzeli do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="1671b-143">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="1671b-144">W module kontenera dodaj moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="1671b-144">Add a content block module to the carousel module.</span></span> <span data-ttu-id="1671b-145">Umożliwia ustawienie właściwości modułu blok zawartości przez udostępnienie **nagłówka**, **łącza**, **układu** i innych właściwości.</span><span class="sxs-lookup"><span data-stu-id="1671b-145">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="1671b-146">Dodaj i skonfiguruj inny moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="1671b-146">Add and configure another content block module.</span></span>
1. <span data-ttu-id="1671b-147">W razie potrzeby skonfiguruj dodatkowe właściwości dla modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="1671b-147">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="1671b-148">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="1671b-148">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="1671b-149">Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji).</span><span class="sxs-lookup"><span data-stu-id="1671b-149">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="1671b-150">Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.</span><span class="sxs-lookup"><span data-stu-id="1671b-150">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="1671b-151">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1671b-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1671b-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1671b-152">Additional resources</span></span>

[<span data-ttu-id="1671b-153">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="1671b-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1671b-154">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="1671b-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="1671b-155">Moduł bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="1671b-155">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="1671b-156">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="1671b-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="1671b-157">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="1671b-157">Video player module</span></span>](add-video-player.md)
