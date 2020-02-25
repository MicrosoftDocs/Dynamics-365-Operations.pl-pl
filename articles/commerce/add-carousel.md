---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025788"
---
# <a name="carousel-module"></a><span data-ttu-id="b0f0f-103">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="b0f0f-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b0f0f-104">W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b0f0f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b0f0f-105">Overview</span></span>

<span data-ttu-id="b0f0f-106">Moduł karuzeli służy do umieszczania wielu elementów promocyjnych (w tym obrazów) w obracającej się karuzeli banerów, które mogą być przeglądane przez klientów.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="b0f0f-107">Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="b0f0f-108">Moduły główne i bloku zawartości można dodawać w module karuzeli.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="b0f0f-109">Właściwości modułu karuzeli definiują sposób renderowania tych modułów.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="b0f0f-110">Przykłady modułów karuzeli w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="b0f0f-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="b0f0f-111">Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="b0f0f-112">Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="b0f0f-113">Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="b0f0f-114">Właściwości modułu karuzeli</span><span class="sxs-lookup"><span data-stu-id="b0f0f-114">Carousel module properties</span></span>

| <span data-ttu-id="b0f0f-115">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="b0f0f-115">Property name</span></span>             | <span data-ttu-id="b0f0f-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="b0f0f-116">Value</span></span>                 | <span data-ttu-id="b0f0f-117">Opis</span><span class="sxs-lookup"><span data-stu-id="b0f0f-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="b0f0f-118">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="b0f0f-118">Autoplay</span></span>                  | <span data-ttu-id="b0f0f-119">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b0f0f-119">**True** or **False**</span></span> | <span data-ttu-id="b0f0f-120">Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="b0f0f-121">Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="b0f0f-122">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="b0f0f-122">Slide transition interval</span></span> | <span data-ttu-id="b0f0f-123">Wartość w sekundach</span><span class="sxs-lookup"><span data-stu-id="b0f0f-123">A value in seconds</span></span>    | <span data-ttu-id="b0f0f-124">Interwał przejść między elementami.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="b0f0f-125">Typ zmiany stanu</span><span class="sxs-lookup"><span data-stu-id="b0f0f-125">Transition type</span></span>           | <span data-ttu-id="b0f0f-126">**Slajd** lub **efekt zanikania**</span><span class="sxs-lookup"><span data-stu-id="b0f0f-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="b0f0f-127">Efekt przejścia między elementami.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-127">The transition effect between items.</span></span> |
| <span data-ttu-id="b0f0f-128">Ukryj ramię karuzeli</span><span class="sxs-lookup"><span data-stu-id="b0f0f-128">Hide carousel flipper</span></span>     | <span data-ttu-id="b0f0f-129">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b0f0f-129">**True** or **False**</span></span> | <span data-ttu-id="b0f0f-130">Jeśli wartość jest ustawiona na **Prawda**, ramiona karuzeli i wskaźnik sekwencji są ukryte.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="b0f0f-131">Zezwalaj na odrzucanie karuzeli</span><span class="sxs-lookup"><span data-stu-id="b0f0f-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="b0f0f-132">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b0f0f-132">**True** or **False**</span></span> | <span data-ttu-id="b0f0f-133">Jeśli wartość jest ustawiona na **Prawda**, użytkownicy mogą anulować karuzelę.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="b0f0f-134">Dodawanie modułu karuzeli do strony</span><span class="sxs-lookup"><span data-stu-id="b0f0f-134">Add a carousel module to a page</span></span>

<span data-ttu-id="b0f0f-135">Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b0f0f-136">Utwórz szablon strony o nazwie nazwa **szablon karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="b0f0f-137">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-137">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="b0f0f-138">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-138">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="b0f0f-139">Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **strona karuzeli**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-139">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="b0f0f-140">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-140">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="b0f0f-141">W okienku po prawej stronie określ wartość **Szerokości** jako **ekran wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-141">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="b0f0f-142">W obszarze **Konspekt strony** dodaj moduł karuzeli do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-142">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="b0f0f-143">W module kontenera dodaj moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-143">Add a content block module to the carousel module.</span></span> <span data-ttu-id="b0f0f-144">Umożliwia ustawienie właściwości modułu blok zawartości przez udostępnienie **nagłówka**, **łącza**, **układu** i innych właściwości.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-144">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="b0f0f-145">Dodaj i skonfiguruj inny moduł bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-145">Add and configure another content block module.</span></span>
1. <span data-ttu-id="b0f0f-146">W razie potrzeby skonfiguruj dodatkowe właściwości dla modułu karuzeli.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-146">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="b0f0f-147">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-147">Save and preview the page.</span></span> <span data-ttu-id="b0f0f-148">Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji).</span><span class="sxs-lookup"><span data-stu-id="b0f0f-148">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="b0f0f-149">Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-149">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="b0f0f-150">Zakończ edytowanie strony i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-150">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0f0f-151">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b0f0f-151">Additional resources</span></span>

[<span data-ttu-id="b0f0f-152">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="b0f0f-152">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b0f0f-153">Moduł baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="b0f0f-153">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="b0f0f-154">Moduł bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="b0f0f-154">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="b0f0f-155">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="b0f0f-155">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="b0f0f-156">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="b0f0f-156">Video player module</span></span>](add-video-player.md)
