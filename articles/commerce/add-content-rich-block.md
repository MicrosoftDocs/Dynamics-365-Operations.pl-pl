---
title: Moduł bloku zaawansowanej zawartości
description: W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025604"
---
# <a name="text-block-module"></a><span data-ttu-id="69386-103">Moduł bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="69386-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="69386-104">W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="69386-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="69386-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="69386-105">Overview</span></span>

<span data-ttu-id="69386-106">Moduł bloku tekstu to moduł służący do dodawania zawartości tekstowej.</span><span class="sxs-lookup"><span data-stu-id="69386-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="69386-107">Ta zawartość może mieć wartość informacyjną lub promocyjną.</span><span class="sxs-lookup"><span data-stu-id="69386-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="69386-108">Moduły bloku zaawansowanej zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="69386-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="69386-109">Są to moduły autonomiczne, które nie są zależne od kontekstu strony ani innych modułów.</span><span class="sxs-lookup"><span data-stu-id="69386-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="69386-110">Przykłady modułów bloku zaawansowanej zawartości w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="69386-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="69386-111">Moduły bloku zaawansowanej zawartości mogą być używane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="69386-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="69386-112">W celu zaprezentowania funkcji produktu na stronie Szczegóły produktu.</span><span class="sxs-lookup"><span data-stu-id="69386-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="69386-113">Do celów informacyjnych na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="69386-113">For informational purposes on any page.</span></span> <span data-ttu-id="69386-114">Można na przykład wyjaśnić zalety programów lojalnościowych, opisać zasady wysyłki i zwrotów, odpowiedzi na często zadawane pytania lub dostarczyć zawartość „o nas”.</span><span class="sxs-lookup"><span data-stu-id="69386-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="69386-115">, Aby dodać niestandardowe komunikaty na stronie szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="69386-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="69386-116">(na przykład „bezpłatna wysyłka zamówień o wartości ponad $50”).</span><span class="sxs-lookup"><span data-stu-id="69386-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="69386-117">Dla roszczeń i szczegółów dotyczących kontaktu na stronach szczegółów produktu, na stronach koszyka, na stronach do realizacji transakcji oraz na innych stronach (np. „Wysyłka i zwroty podlegają zasadom sklepu”).</span><span class="sxs-lookup"><span data-stu-id="69386-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="69386-118">Właściwości modułu bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="69386-118">Text block module properties</span></span>

| <span data-ttu-id="69386-119">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="69386-119">Property name</span></span>     | <span data-ttu-id="69386-120">Value</span><span class="sxs-lookup"><span data-stu-id="69386-120">Value</span></span>                                            | <span data-ttu-id="69386-121">Opis</span><span class="sxs-lookup"><span data-stu-id="69386-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="69386-122">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="69386-122">Rich text</span></span>         | <span data-ttu-id="69386-123">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="69386-123">Rich text</span></span>                                        | <span data-ttu-id="69386-124">Tekst akapitu.</span><span class="sxs-lookup"><span data-stu-id="69386-124">Paragraph text.</span></span> <span data-ttu-id="69386-125">Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa.</span><span class="sxs-lookup"><span data-stu-id="69386-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="69386-126">Niestandardowa nazwa klasy</span><span class="sxs-lookup"><span data-stu-id="69386-126">Custom class name</span></span> | <span data-ttu-id="69386-127">Nazwa klasy arkuszy stylów kaskadowych (CSS)</span><span class="sxs-lookup"><span data-stu-id="69386-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="69386-128">Nazwa niestandardowej klasy CSS, którą projektant chce sformatować w tym module.</span><span class="sxs-lookup"><span data-stu-id="69386-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="69386-129">Nazwa klasy powinna być zdefiniowana w pakiecie kompozycji.</span><span class="sxs-lookup"><span data-stu-id="69386-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="69386-130">Rozmiar czcionki</span><span class="sxs-lookup"><span data-stu-id="69386-130">Font size</span></span>         | <span data-ttu-id="69386-131">**Małe**, **średnie**, **duże** lub **XL**</span><span class="sxs-lookup"><span data-stu-id="69386-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="69386-132">Wybierz rozmiar czcionki treści.</span><span class="sxs-lookup"><span data-stu-id="69386-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="69386-133">Dodawanie bloku zaawansowanej zawartości do nowej strony</span><span class="sxs-lookup"><span data-stu-id="69386-133">Add a text block module to a page</span></span>

<span data-ttu-id="69386-134">Aby dodać moduł blokuzaawansowanej zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="69386-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="69386-135">Utwórz szablon strony o nazwie nazwa **szablon zawartości**.</span><span class="sxs-lookup"><span data-stu-id="69386-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="69386-136">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="69386-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="69386-137">Zakończ edytowanie szablonu i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="69386-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="69386-138">Za pomocą utworzonego właśnie szblonu zawartości utwórz stronę o nazwie **strona zawartości**.</span><span class="sxs-lookup"><span data-stu-id="69386-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="69386-139">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="69386-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="69386-140">W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="69386-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="69386-141">W module bloku zaawansowanej zawartości dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="69386-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="69386-142">W okienku właściwości modułu blok tekstu Dodaj tekst do pola **Tekst sformatowany**.</span><span class="sxs-lookup"><span data-stu-id="69386-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="69386-143">Zakończ edytowanie strony i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="69386-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69386-144">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="69386-144">Additional resources</span></span>

[<span data-ttu-id="69386-145">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="69386-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="69386-146">Moduł baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="69386-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="69386-147">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="69386-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="69386-148">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="69386-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="69386-149">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="69386-149">Video player module</span></span>](add-video-player.md)

