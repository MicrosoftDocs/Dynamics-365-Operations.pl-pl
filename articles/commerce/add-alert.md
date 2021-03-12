---
title: Moduł baneru promocyjnego
description: W tym temacie opisano moduł baneru promocyjnego i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a77196be69bb71d917bf84c633199a3af3fbf478
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986036"
---
# <a name="promo-banner-module"></a><span data-ttu-id="b3c72-103">Moduł baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="b3c72-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3c72-104">W tym temacie opisano moduł baneru promocyjnego i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3c72-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b3c72-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b3c72-105">Overview</span></span>

<span data-ttu-id="b3c72-106">Moduły baneru promocyjnego służą do wyświetlania wbudowanych komunikatów informacyjnych na stronie.</span><span class="sxs-lookup"><span data-stu-id="b3c72-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="b3c72-107">Można ich używać do wyświetlania promocji na poziomie całej witryny wyświetlanych na wszystkich stronach witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3c72-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="b3c72-108">Moduły baneru promocyjnego obsługują wiadomość SMS i łącze.</span><span class="sxs-lookup"><span data-stu-id="b3c72-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="b3c72-109">Jeśli do modułu baneru promocyjnego jest dodawanych wiele wiadomości, staje się on wiodącym banerem karuzeli, który pozwoli klientom przechodzić między wszystkimi wiadomościami.</span><span class="sxs-lookup"><span data-stu-id="b3c72-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="b3c72-110">Moduły baneru promocyjnego są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="b3c72-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="b3c72-111">Przykłady użycia banerów promocyjnych w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="b3c72-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="b3c72-112">W nagłówku witryny można używać banerów promocyjnych do wyświetlania promocji lub komunikatów w całej witrynie, tak jak w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="b3c72-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="b3c72-113">„Roczna wyprzedaż kończy się za 10 dni”</span><span class="sxs-lookup"><span data-stu-id="b3c72-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="b3c72-114">„Zaoszczędź na zakupach do szkoły.</span><span class="sxs-lookup"><span data-stu-id="b3c72-114">"Save big with back to school sale.</span></span> <span data-ttu-id="b3c72-115">Kup teraz.”</span><span class="sxs-lookup"><span data-stu-id="b3c72-115">Shop Now."</span></span>

<span data-ttu-id="b3c72-116">„Wyprzedaż na Święto Dziękczynienia!”</span><span class="sxs-lookup"><span data-stu-id="b3c72-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="b3c72-117">Poniższy obraz przedstawia przykład baneru promocyjnego.</span><span class="sxs-lookup"><span data-stu-id="b3c72-117">The following image shows an example of a promo banner.</span></span>

![Przykład modułu baneru promocyjnego](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="b3c72-119">Właściwości modułu baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="b3c72-119">Promo banner module properties</span></span>

| <span data-ttu-id="b3c72-120">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="b3c72-120">Property name</span></span>             | <span data-ttu-id="b3c72-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="b3c72-121">Value</span></span>                              | <span data-ttu-id="b3c72-122">opis</span><span class="sxs-lookup"><span data-stu-id="b3c72-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="b3c72-123">Wiadomości transparentu</span><span class="sxs-lookup"><span data-stu-id="b3c72-123">Banner messages</span></span>           | <span data-ttu-id="b3c72-124">Tekst i łącza</span><span class="sxs-lookup"><span data-stu-id="b3c72-124">Text and links</span></span>                     | <span data-ttu-id="b3c72-125">Szeroki wybór tekstu i łączy.</span><span class="sxs-lookup"><span data-stu-id="b3c72-125">An array of text and links.</span></span> |
| <span data-ttu-id="b3c72-126">Autoodtwarzanie</span><span class="sxs-lookup"><span data-stu-id="b3c72-126">Autoplay</span></span>                  | <span data-ttu-id="b3c72-127">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b3c72-127">**True** or **False**</span></span>              | <span data-ttu-id="b3c72-128">Wartość wskazująca, czy komunikaty są automatycznie przetwarzane, jeśli skonfigurowano wiele wiadomości.</span><span class="sxs-lookup"><span data-stu-id="b3c72-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="b3c72-129">Interwał przejścia slajdu</span><span class="sxs-lookup"><span data-stu-id="b3c72-129">Slide transition interval</span></span> | <span data-ttu-id="b3c72-130">Liczba milisekund (ms)</span><span class="sxs-lookup"><span data-stu-id="b3c72-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="b3c72-131">Interwał używany do cyklicznego przechodzenia między wiadomościami.</span><span class="sxs-lookup"><span data-stu-id="b3c72-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="b3c72-132">Zezwól na odrzucanie</span><span class="sxs-lookup"><span data-stu-id="b3c72-132">Allow dismiss</span></span>             | <span data-ttu-id="b3c72-133">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b3c72-133">**True** or **False**</span></span>              | <span data-ttu-id="b3c72-134">Jeśli wartość jest ustawiona na **Prawda**, odbiorcy mogą anulować alert.</span><span class="sxs-lookup"><span data-stu-id="b3c72-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="b3c72-135">Pokazuj flipper karuzeli</span><span class="sxs-lookup"><span data-stu-id="b3c72-135">Show carousel flipper</span></span>     | <span data-ttu-id="b3c72-136">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b3c72-136">**True** or **False**</span></span>              | <span data-ttu-id="b3c72-137">Wartość wskazująca, czy mają być pokazywane flippery karuzeli, dzięki czemu odbiorcy mogą ręcznie przechodzić między różnymi elementami baneru.</span><span class="sxs-lookup"><span data-stu-id="b3c72-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="b3c72-138">Wyrównanie tekstu</span><span class="sxs-lookup"><span data-stu-id="b3c72-138">Text alignment</span></span>            | <span data-ttu-id="b3c72-139">**Prawo**, **Lewo** lub **Środek**</span><span class="sxs-lookup"><span data-stu-id="b3c72-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="b3c72-140">Wyrównanie tekstu w module baner promocyjny.</span><span class="sxs-lookup"><span data-stu-id="b3c72-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="b3c72-141">Link</span><span class="sxs-lookup"><span data-stu-id="b3c72-141">Link</span></span>                      | <span data-ttu-id="b3c72-142">Adres URL</span><span class="sxs-lookup"><span data-stu-id="b3c72-142">A URL</span></span>                              | <span data-ttu-id="b3c72-143">Adres URL opcjonalnego linku.</span><span class="sxs-lookup"><span data-stu-id="b3c72-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="b3c72-144">Dodawanie modułu baneru promocyjnego do nowej strony</span><span class="sxs-lookup"><span data-stu-id="b3c72-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="b3c72-145">Aby dodać moduł baneru promocyjnego do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b3c72-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b3c72-146">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="b3c72-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="b3c72-147">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon baneru promocyjnego**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3c72-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="b3c72-148">W obszarze **Konspekt strony** dodaj moduł **Domyślna strona** do gniazda **Treść**.</span><span class="sxs-lookup"><span data-stu-id="b3c72-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="b3c72-149">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="b3c72-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="b3c72-150">Za pomocą utworzonego właśnie szblonu alertu utwórz stronę o nazwie **Strona baneru promocyjnego**.</span><span class="sxs-lookup"><span data-stu-id="b3c72-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="b3c72-151">W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="b3c72-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="b3c72-152">W okienku po prawej stronie określ wartość **Szerokości** jako **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="b3c72-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="b3c72-153">W obszarze **Konspekt strony** dodaj moduł baneru promocyjnego do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="b3c72-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="b3c72-154">W ustawieniach modułu banery promocyjnego dodaj co najmniej jedną wiadomość baneru.</span><span class="sxs-lookup"><span data-stu-id="b3c72-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="b3c72-155">Każda wiadomość może zawierać tekst razem z łączem.</span><span class="sxs-lookup"><span data-stu-id="b3c72-155">Each message can have text together with a link.</span></span> <span data-ttu-id="b3c72-156">Inne właściwości można edytować, jeśli moduł ma być dostosowany dalej.</span><span class="sxs-lookup"><span data-stu-id="b3c72-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="b3c72-157">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="b3c72-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="b3c72-158">W górnej części strony powinien pojawić się alert z dodanym tekstem.</span><span class="sxs-lookup"><span data-stu-id="b3c72-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="b3c72-159">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="b3c72-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c72-160">Baner jest zazwyczaj używany w gnieździe nagłówka strony lub w gnieździe podnagłówków.</span><span class="sxs-lookup"><span data-stu-id="b3c72-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="b3c72-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b3c72-161">Additional resources</span></span>

[<span data-ttu-id="b3c72-162">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="b3c72-162">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b3c72-163">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="b3c72-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="b3c72-164">Moduł bloku tekstu</span><span class="sxs-lookup"><span data-stu-id="b3c72-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="b3c72-165">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="b3c72-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="b3c72-166">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="b3c72-166">Video player module</span></span>](add-video-player.md)
