---
title: Moduł alertów
description: W tym temacie opisano moduły alertów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785359"
---
# <a name="alert-module"></a><span data-ttu-id="276c3-103">Moduł alertów</span><span class="sxs-lookup"><span data-stu-id="276c3-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="276c3-104">W tym temacie opisano moduły alertów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="276c3-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="276c3-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="276c3-105">Overview</span></span>

<span data-ttu-id="276c3-106">Moduł alertów służy do wyświetlania wbudowanych komunikatów informacyjnych na stronie.</span><span class="sxs-lookup"><span data-stu-id="276c3-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="276c3-107">Moduły alertów obsługują wiadomość SMS i łącze.</span><span class="sxs-lookup"><span data-stu-id="276c3-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="276c3-108">Można ich używać do wyświetlania promocji na poziomie całej witryny wyświetlanych na wszystkich stronach witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="276c3-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="276c3-109">Moduły alertów są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="276c3-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="276c3-110">Przykłady modułów alertów w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="276c3-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="276c3-111">Moduły alertów mogą być używane w nagłówku witryny w celu pokazania promocji lub komunikatów na poziomie całej witryny.</span><span class="sxs-lookup"><span data-stu-id="276c3-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="276c3-112">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="276c3-112">Here are some examples:</span></span>

<span data-ttu-id="276c3-113">„Roczna wyprzedaż kończy się za 10 dni”</span><span class="sxs-lookup"><span data-stu-id="276c3-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="276c3-114">„Zaoszczędź na zakupach do szkoły.</span><span class="sxs-lookup"><span data-stu-id="276c3-114">"Save big with back to school sale.</span></span> <span data-ttu-id="276c3-115">Kup teraz.”</span><span class="sxs-lookup"><span data-stu-id="276c3-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="276c3-116">Właściwości modułu alertów</span><span class="sxs-lookup"><span data-stu-id="276c3-116">Alert module properties</span></span>

| <span data-ttu-id="276c3-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="276c3-117">Property name</span></span>  | <span data-ttu-id="276c3-118">Wartość</span><span class="sxs-lookup"><span data-stu-id="276c3-118">Value</span></span>                              | <span data-ttu-id="276c3-119">Opis</span><span class="sxs-lookup"><span data-stu-id="276c3-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="276c3-120">Tekst</span><span class="sxs-lookup"><span data-stu-id="276c3-120">Text</span></span>           | <span data-ttu-id="276c3-121">Tekst</span><span class="sxs-lookup"><span data-stu-id="276c3-121">Text</span></span>                               | <span data-ttu-id="276c3-122">Komunikat tekstowy wyświetlany w module alertu.</span><span class="sxs-lookup"><span data-stu-id="276c3-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="276c3-123">Wyrównanie tekstu</span><span class="sxs-lookup"><span data-stu-id="276c3-123">Text alignment</span></span> | <span data-ttu-id="276c3-124">**Prawo**, **Lewo** lub **Środek**</span><span class="sxs-lookup"><span data-stu-id="276c3-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="276c3-125">Wartość określająca sposób wyrównania tekstu w module alertów.</span><span class="sxs-lookup"><span data-stu-id="276c3-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="276c3-126">Pomiń alert</span><span class="sxs-lookup"><span data-stu-id="276c3-126">Dismiss alert</span></span>  | <span data-ttu-id="276c3-127">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="276c3-127">**True** or **False**</span></span>              | <span data-ttu-id="276c3-128">Jeśli wartość jest ustawiona na **Prawda**, odbiorca może anulować alert.</span><span class="sxs-lookup"><span data-stu-id="276c3-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="276c3-129">Link</span><span class="sxs-lookup"><span data-stu-id="276c3-129">Link</span></span>           | <span data-ttu-id="276c3-130">Adres URL</span><span class="sxs-lookup"><span data-stu-id="276c3-130">URL</span></span>                                | <span data-ttu-id="276c3-131">Adres URL opcjonalnego linku.</span><span class="sxs-lookup"><span data-stu-id="276c3-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="276c3-132">Dodawanie modułu alertów do strony</span><span class="sxs-lookup"><span data-stu-id="276c3-132">Add an alert module to a page</span></span> 

<span data-ttu-id="276c3-133">Aby dodać moduł alertów do strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="276c3-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="276c3-134">Utwórz szablon strony o nazwie nazwa **szablon alertu**.</span><span class="sxs-lookup"><span data-stu-id="276c3-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="276c3-135">W **Głównym** gnieździe na stronie domyślnej dodaj moduł alertów.</span><span class="sxs-lookup"><span data-stu-id="276c3-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="276c3-136">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="276c3-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="276c3-137">Za pomocą utworzonego właśnie szblonu alertu utwórz stronę o nazwie **strona alertu**.</span><span class="sxs-lookup"><span data-stu-id="276c3-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="276c3-138">W **Głównym** gnieździe na nowej stronie dodaj moduł alertów.</span><span class="sxs-lookup"><span data-stu-id="276c3-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="276c3-139">W ustawieniach modułu alertów wprowadź tekst alertu.</span><span class="sxs-lookup"><span data-stu-id="276c3-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="276c3-140">Inne właściwości można edytować, jeśli moduł alertów ma być dostosowany dalej.</span><span class="sxs-lookup"><span data-stu-id="276c3-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="276c3-141">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="276c3-141">Save and preview the page.</span></span> <span data-ttu-id="276c3-142">W górnej części strony powinien pojawić się alert z dodanym tekstem.</span><span class="sxs-lookup"><span data-stu-id="276c3-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="276c3-143">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="276c3-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="276c3-144">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="276c3-144">Additional resources</span></span>

[<span data-ttu-id="276c3-145">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="276c3-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="276c3-146">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="276c3-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="276c3-147">Moduł zaawansowanego bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="276c3-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="276c3-148">Moduł umieszczania zawartości</span><span class="sxs-lookup"><span data-stu-id="276c3-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="276c3-149">Moduł funkcji</span><span class="sxs-lookup"><span data-stu-id="276c3-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="276c3-150">Moduł bohatera</span><span class="sxs-lookup"><span data-stu-id="276c3-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="276c3-151">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="276c3-151">Video player module</span></span>](add-video-player.md)
