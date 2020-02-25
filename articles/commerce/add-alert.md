---
title: Moduł baneru promocyjnego
description: W tym temacie opisano moduł baneru promocyjnego i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025627"
---
# <a name="promo-banner-module"></a><span data-ttu-id="f4d1a-103">Moduł baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="f4d1a-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f4d1a-104">W tym temacie opisano moduł baneru promocyjnego i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f4d1a-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f4d1a-105">Overview</span></span>

<span data-ttu-id="f4d1a-106">Moduły baneru promocyjnego służą do wyświetlania wbudowanych komunikatów informacyjnych na stronie.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="f4d1a-107">Można ich używać do wyświetlania promocji na poziomie całej witryny wyświetlanych na wszystkich stronach witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="f4d1a-108">Moduły baneru promocyjnego obsługują wiadomość SMS i łącze.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="f4d1a-109">Jeśli do modułu baneru promocyjnego jest dodawanych wiele wiadomości, staje się on wiodącym banerem karuzeli, który pozwoli klientom przechodzić między wszystkimi wiadomościami.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="f4d1a-110">Moduły baneru promocyjnego są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="f4d1a-111">Przykłady użycia banerów promocyjnych w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="f4d1a-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="f4d1a-112">W nagłówku witryny można używać banerów promocyjnych do wyświetlania promocji lub komunikatów w całej witrynie, tak jak w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="f4d1a-113">„Roczna wyprzedaż kończy się za 10 dni”</span><span class="sxs-lookup"><span data-stu-id="f4d1a-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="f4d1a-114">„Zaoszczędź na zakupach do szkoły.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-114">"Save big with back to school sale.</span></span> <span data-ttu-id="f4d1a-115">Kup teraz.”</span><span class="sxs-lookup"><span data-stu-id="f4d1a-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="f4d1a-116">Właściwości modułu baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="f4d1a-116">Promo banner module properties</span></span>

| <span data-ttu-id="f4d1a-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="f4d1a-117">Property name</span></span>             | <span data-ttu-id="f4d1a-118">Value</span><span class="sxs-lookup"><span data-stu-id="f4d1a-118">Value</span></span>                              | <span data-ttu-id="f4d1a-119">Opis</span><span class="sxs-lookup"><span data-stu-id="f4d1a-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="f4d1a-120">Wiadomości transparentu</span><span class="sxs-lookup"><span data-stu-id="f4d1a-120">Banner messages</span></span>           | <span data-ttu-id="f4d1a-121">Tekst i łącza</span><span class="sxs-lookup"><span data-stu-id="f4d1a-121">Text and links</span></span>                     | <span data-ttu-id="f4d1a-122">Szeroki wybór tekstu i łączy.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-122">An array of text and links.</span></span> |
| <span data-ttu-id="f4d1a-123">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="f4d1a-123">Autoplay</span></span>                  | <span data-ttu-id="f4d1a-124">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="f4d1a-124">**True** or **False**</span></span>              | <span data-ttu-id="f4d1a-125">Wartość wskazująca, czy komunikaty są automatycznie przetwarzane, jeśli skonfigurowano wiele wiadomości.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="f4d1a-126">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="f4d1a-126">Slide transition interval</span></span> | <span data-ttu-id="f4d1a-127">Liczba milisekund (ms)</span><span class="sxs-lookup"><span data-stu-id="f4d1a-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="f4d1a-128">Interwał używany do cyklicznego przechodzenia między wiadomościami.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="f4d1a-129">Zezwól na odrzucanie</span><span class="sxs-lookup"><span data-stu-id="f4d1a-129">Allow dismiss</span></span>             | <span data-ttu-id="f4d1a-130">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="f4d1a-130">**True** or **False**</span></span>              | <span data-ttu-id="f4d1a-131">Jeśli wartość jest ustawiona na **Prawda**, odbiorcy mogą anulować alert.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="f4d1a-132">Pokazuj flipper karuzeli</span><span class="sxs-lookup"><span data-stu-id="f4d1a-132">Show carousel flipper</span></span>     | <span data-ttu-id="f4d1a-133">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="f4d1a-133">**True** or **False**</span></span>              | <span data-ttu-id="f4d1a-134">Wartość wskazująca, czy mają być pokazywane flippery karuzeli, dzięki czemu odbiorcy mogą ręcznie przechodzić między różnymi elementami baneru.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="f4d1a-135">Wyrównanie tekstu</span><span class="sxs-lookup"><span data-stu-id="f4d1a-135">Text alignment</span></span>            | <span data-ttu-id="f4d1a-136">**Prawo**, **Lewo** lub **Środek**</span><span class="sxs-lookup"><span data-stu-id="f4d1a-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="f4d1a-137">Wyrównanie tekstu w module baner promocyjny.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="f4d1a-138">Link</span><span class="sxs-lookup"><span data-stu-id="f4d1a-138">Link</span></span>                      | <span data-ttu-id="f4d1a-139">Adres URL</span><span class="sxs-lookup"><span data-stu-id="f4d1a-139">A URL</span></span>                              | <span data-ttu-id="f4d1a-140">Adres URL opcjonalnego linku.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="f4d1a-141">Dodawanie modułu baneru promocyjnego do nowej strony</span><span class="sxs-lookup"><span data-stu-id="f4d1a-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="f4d1a-142">Aby dodać moduł baneru promocyjnego do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="f4d1a-143">Utwórz szablon strony o nazwie nazwa **Szablon baneru promocyjnego**.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-143">Create a page template that is named **Promo banner template**.</span></span>
1. <span data-ttu-id="f4d1a-144">W obszarze **Konspekt strony** dodaj moduł **Domyślna strona** do gniazda **Treść**.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-144">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="f4d1a-145">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-145">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="f4d1a-146">Za pomocą utworzonego właśnie szblonu alertu utwórz stronę o nazwie **Strona baneru promocyjnego**.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-146">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="f4d1a-147">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-147">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="f4d1a-148">W okienku po prawej stronie określ wartość **Szerokości** jako **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-148">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="f4d1a-149">W obszarze **Konspekt strony** dodaj moduł baneru promocyjnego do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-149">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="f4d1a-150">W ustawieniach modułu banery promocyjnego dodaj co najmniej jedną wiadomość baneru.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-150">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="f4d1a-151">Każda wiadomość może zawierać tekst razem z łączem.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-151">Each message can have text together with a link.</span></span> <span data-ttu-id="f4d1a-152">Inne właściwości można edytować, jeśli moduł ma być dostosowany dalej.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-152">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="f4d1a-153">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-153">Save and preview the page.</span></span> <span data-ttu-id="f4d1a-154">W górnej części strony powinien pojawić się alert z dodanym tekstem.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-154">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="f4d1a-155">Zakończ edytowanie strony i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-155">Finish editing the page, and publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="f4d1a-156">Baner jest zazwyczaj używany w gnieździe nagłówka strony lub w gnieździe podnagłówków.</span><span class="sxs-lookup"><span data-stu-id="f4d1a-156">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="f4d1a-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f4d1a-157">Additional resources</span></span>

[<span data-ttu-id="f4d1a-158">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="f4d1a-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f4d1a-159">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="f4d1a-159">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="f4d1a-160">Moduł bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="f4d1a-160">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="f4d1a-161">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="f4d1a-161">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="f4d1a-162">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="f4d1a-162">Video player module</span></span>](add-video-player.md)
