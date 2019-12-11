---
title: Moduł zaawansowanego bloku zawartości
description: W tym temacie opisano moduły zaawansowanego bloku zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785428"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="6be26-103">Moduł zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="6be26-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6be26-104">W tym temacie opisano moduły zaawansowanego bloku zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6be26-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6be26-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6be26-105">Overview</span></span>

<span data-ttu-id="6be26-106">Moduł zaawansowanego bloku zawartości jest specjalnym kontenerem, w którym można umieścić co najmniej jeden element zaawansowanego bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="6be26-107">Dla zawartości tekstowej na stronie używany jest moduł zaawansowanego bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="6be26-108">Ta zawartość może mieć wartość informacyjną lub promocyjną.</span><span class="sxs-lookup"><span data-stu-id="6be26-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="6be26-109">Moduły zaawansowanego bloku zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="6be26-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="6be26-110">Są to moduły autonomiczne, które nie są zależne od kontekstu strony ani innych modułów.</span><span class="sxs-lookup"><span data-stu-id="6be26-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="6be26-111">Przykłady modułów zaawansowanego bloku zawartości w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="6be26-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="6be26-112">Moduły zaawansowanego bloku zawartości mogą być używane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6be26-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="6be26-113">W celu zaprezentowania funkcji produktu na stronie Szczegóły produktu.</span><span class="sxs-lookup"><span data-stu-id="6be26-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="6be26-114">Do celów informacyjnych na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="6be26-114">For informational purposes on any page.</span></span> <span data-ttu-id="6be26-115">Można na przykład wyjaśnić zalety programów lojalnościowych, opisać zasady wysyłki i zwrotów, odpowiedzi na często zadawane pytania lub dostarczyć zawartość „o nas”.</span><span class="sxs-lookup"><span data-stu-id="6be26-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="6be26-116">, Aby dodać niestandardowe komunikaty na stronie szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="6be26-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="6be26-117">(na przykład „bezpłatna wysyłka zamówień o wartości ponad $50”).</span><span class="sxs-lookup"><span data-stu-id="6be26-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="6be26-118">Dla roszczeń i szczegółów dotyczących kontaktu na stronach szczegółów produktu, na stronach koszyka, na stronach do realizacji transakcji oraz na innych stronach (np. „Wysyłka i zwroty podlegają zasadom sklepu”).</span><span class="sxs-lookup"><span data-stu-id="6be26-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="6be26-119">Właściwości modułu zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="6be26-119">Content rich block module properties</span></span>

| <span data-ttu-id="6be26-120">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="6be26-120">Property name</span></span>     | <span data-ttu-id="6be26-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="6be26-121">Value</span></span>                                 | <span data-ttu-id="6be26-122">Właściwość</span><span class="sxs-lookup"><span data-stu-id="6be26-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="6be26-123">Liczba kolumn</span><span class="sxs-lookup"><span data-stu-id="6be26-123">Number of columns</span></span> | <span data-ttu-id="6be26-124">Liczba z zakresu od **1** do **4**</span><span class="sxs-lookup"><span data-stu-id="6be26-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="6be26-125">Liczba kolumn w bloku bogatym zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="6be26-126">Może zawierać do czterech kolumn.</span><span class="sxs-lookup"><span data-stu-id="6be26-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="6be26-127">Szerokość</span><span class="sxs-lookup"><span data-stu-id="6be26-127">Width</span></span>             | <span data-ttu-id="6be26-128">**Wypełnij kontener** lub **ekran wypełnienia**</span><span class="sxs-lookup"><span data-stu-id="6be26-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="6be26-129">Jeśli wartość jest ustawiona na **Wypełnij kontener**, elementy wewnątrz kontenera są ograniczone do szerokości kontenera.</span><span class="sxs-lookup"><span data-stu-id="6be26-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="6be26-130">Jeśli wartość jest ustawiona na **wypełnienie ekranu**, elementy nie są ograniczone do szerokości kontenera, ale mogą przechodzić do trybu pełnoekranowego.</span><span class="sxs-lookup"><span data-stu-id="6be26-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="6be26-131">Można zmienić wartość, aby uzyskać odpowiedni układ.</span><span class="sxs-lookup"><span data-stu-id="6be26-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="6be26-132">Właściwości modułu elementu zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="6be26-132">Content rich block item module properties</span></span>

| <span data-ttu-id="6be26-133">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="6be26-133">Property name</span></span> | <span data-ttu-id="6be26-134">Wartość</span><span class="sxs-lookup"><span data-stu-id="6be26-134">Value</span></span>          | <span data-ttu-id="6be26-135">Opis</span><span class="sxs-lookup"><span data-stu-id="6be26-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="6be26-136">Akapit</span><span class="sxs-lookup"><span data-stu-id="6be26-136">Paragraph</span></span>     | <span data-ttu-id="6be26-137">Tekst akapitu</span><span class="sxs-lookup"><span data-stu-id="6be26-137">Paragraph text</span></span> | <span data-ttu-id="6be26-138">Tekst towarzyszący każdego elementu zaawansowanego bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="6be26-139">Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa.</span><span class="sxs-lookup"><span data-stu-id="6be26-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="6be26-140">Dodawanie modułu zaawansowanego bloku zawartości do strony</span><span class="sxs-lookup"><span data-stu-id="6be26-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="6be26-141">Aby dodać moduł zaawansowanego bloku zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6be26-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="6be26-142">Utwórz szablon strony o nazwie nazwa **szablon zawartości**.</span><span class="sxs-lookup"><span data-stu-id="6be26-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="6be26-143">W **Głównym** gnieździe na stronie domyślnej dodaj moduł zaawansowanego bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="6be26-144">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="6be26-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="6be26-145">Za pomocą utworzonego właśnie szblonu zawartości utwórz stronę o nazwie **strona zawartości**.</span><span class="sxs-lookup"><span data-stu-id="6be26-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="6be26-146">W **Głównym** gnieździe na nowej stronie dodaj moduł zaawansowanego bloku zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="6be26-147">W właściwościach modułu zaawansowanego bloku zawartości określ liczbę kolumn równą **2**.</span><span class="sxs-lookup"><span data-stu-id="6be26-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="6be26-148">W module zaawansowanego bloku zawartości wybierz opcję **Dodaj moduł** i dodaj element zaawansowanego bloku zawartości (na przykład **Element1**).</span><span class="sxs-lookup"><span data-stu-id="6be26-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="6be26-149">W nowym elemencie zaawansowanego bloku zawartości dodaj tekst akapitu.</span><span class="sxs-lookup"><span data-stu-id="6be26-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="6be26-150">W module zaawansowanego bloku zawartości wybierz opcję **Dodaj moduł** i dodaj element zaawansowanego bloku zawartości (na przykład **Element2**).</span><span class="sxs-lookup"><span data-stu-id="6be26-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="6be26-151">W nowym elemencie zaawansowanego bloku zawartości dodaj tekst akapitu.</span><span class="sxs-lookup"><span data-stu-id="6be26-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="6be26-152">Zapisz stronę i wyświetl podgląd zmian.</span><span class="sxs-lookup"><span data-stu-id="6be26-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="6be26-153">W widoku dwóch kolumn powinny być widoczne dwa bloki zaawansowanej zawartości.</span><span class="sxs-lookup"><span data-stu-id="6be26-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="6be26-154">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="6be26-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="6be26-155">Jeśli zostanie dodany element trzeciego bloku zaawansowanej zawartości, zostanie on umieszczony w stosie poniżej dwóch wcześniej dodanych elementów.</span><span class="sxs-lookup"><span data-stu-id="6be26-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="6be26-156">Zmieniając liczbę kolumn i elementów w kontenerze, można uzyskać różne układy dla zawartości tekstowej.</span><span class="sxs-lookup"><span data-stu-id="6be26-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6be26-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6be26-157">Additional resources</span></span>

[<span data-ttu-id="6be26-158">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="6be26-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6be26-159">Moduł alertów</span><span class="sxs-lookup"><span data-stu-id="6be26-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="6be26-160">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="6be26-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="6be26-161">Moduł umieszczania zawartości</span><span class="sxs-lookup"><span data-stu-id="6be26-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="6be26-162">Moduł funkcji</span><span class="sxs-lookup"><span data-stu-id="6be26-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="6be26-163">Moduł bohatera</span><span class="sxs-lookup"><span data-stu-id="6be26-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="6be26-164">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="6be26-164">Video player module</span></span>](add-video-player.md)

