---
title: Moduł odtwarzacza wideo
description: W tym temacie opisano moduły odtwarzacza wideo i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025671"
---
# <a name="video-player-module"></a><span data-ttu-id="c3071-103">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="c3071-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c3071-104">W tym temacie opisano moduły odtwarzacza wideo i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3071-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c3071-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c3071-105">Overview</span></span>

<span data-ttu-id="c3071-106">Moduł odtwarzacza wideo służy do obsługi odtwarzania wideo.</span><span class="sxs-lookup"><span data-stu-id="c3071-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="c3071-107">Można go dodać do dowolnej strony, pod warunkiem, że zawartość wideo jest przekazywana do systemu zarządzania zawartością (CMS) i dostępna w nim.</span><span class="sxs-lookup"><span data-stu-id="c3071-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="c3071-108">Moduł odtwarzacz wideo obsługuje typ multimediów MP4.</span><span class="sxs-lookup"><span data-stu-id="c3071-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="c3071-109">Moduł odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="c3071-109">Video player module</span></span>

<span data-ttu-id="c3071-110">Moduł odtwarzacz wideo może służyć do prezentowania filmów wideo w witrynie e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3071-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="c3071-111">Obsługuje on wszystkie możliwości odtwarzania, takie jak odtwarzanie, wstrzymywanie, tryb pełnego rozmiaru, opisy audio i napisy kodowane.</span><span class="sxs-lookup"><span data-stu-id="c3071-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="c3071-112">Moduł odtwarzacz wideo obsługuje również dostosowywanie napisów kodowanych w celu spełnienia standardów dotyczących ułatwień dostępu firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3071-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="c3071-113">Można na przykład dostosować rozmiar czcionki i kolor tła.</span><span class="sxs-lookup"><span data-stu-id="c3071-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="c3071-114">Moduł odtwarzacza wideo obsługuje również pomocnicze ścieżki audio.</span><span class="sxs-lookup"><span data-stu-id="c3071-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="c3071-115">Po przekazaniu filmu wideo do CMS można również przesłać pomocniczą ścieżkę audio.</span><span class="sxs-lookup"><span data-stu-id="c3071-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="c3071-116">Moduł odtwarzacza wideo może następnie odtwarzać pomocniczą ścieżkę audio, jeśli użytkownik ją wybierze.</span><span class="sxs-lookup"><span data-stu-id="c3071-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="c3071-117">Przykładowe moduły odtwarzacza wideo w e-Commerce</span><span class="sxs-lookup"><span data-stu-id="c3071-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="c3071-118">Instruktażowe filmy wideo na stronach szczegółów produktu lub na stronach marketingowych</span><span class="sxs-lookup"><span data-stu-id="c3071-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="c3071-119">Promocyjne filmy wideo i materiały wideo informacje o zasadach na dowolnej stronie marketingowej</span><span class="sxs-lookup"><span data-stu-id="c3071-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="c3071-120">Marketingowe pliki wideo, które wyróżniają funkcje produktu na stronach szczegółów produktu lub na stronach marketingowych</span><span class="sxs-lookup"><span data-stu-id="c3071-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="c3071-121">Właściwości modułu odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="c3071-121">Video player module properties</span></span>

| <span data-ttu-id="c3071-122">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="c3071-122">Property name</span></span>         | <span data-ttu-id="c3071-123">Wartość</span><span class="sxs-lookup"><span data-stu-id="c3071-123">Value</span></span>                               | <span data-ttu-id="c3071-124">Opis</span><span class="sxs-lookup"><span data-stu-id="c3071-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="c3071-125">Automatyczne odtwarzanie</span><span class="sxs-lookup"><span data-stu-id="c3071-125">Auto play</span></span>             | <span data-ttu-id="c3071-126">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-126">**True** or **False**</span></span>               | <span data-ttu-id="c3071-127">Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest automatycznie odtwarzane.</span><span class="sxs-lookup"><span data-stu-id="c3071-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="c3071-128">Wycisz</span><span class="sxs-lookup"><span data-stu-id="c3071-128">Mute</span></span>                  | <span data-ttu-id="c3071-129">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-129">**True** or **False**</span></span>               | <span data-ttu-id="c3071-130">Jeśli wartość jest ustawiona na **prawda**, audio jest wyciszane.</span><span class="sxs-lookup"><span data-stu-id="c3071-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="c3071-131">Domyślną wartością tego odtwarzacza jest **fałsz**.</span><span class="sxs-lookup"><span data-stu-id="c3071-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="c3071-132">W przeglądarce Chrome klipy wideo autoodtwarzania są domyślnie wyciszone, a dźwięk jest odtwarzany tylko wtedy, gdy użytkownik ręcznie odtworzy wideo.</span><span class="sxs-lookup"><span data-stu-id="c3071-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="c3071-133">Pętla</span><span class="sxs-lookup"><span data-stu-id="c3071-133">Loop</span></span>                  | <span data-ttu-id="c3071-134">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-134">**True** or **False**</span></span>               | <span data-ttu-id="c3071-135">Jeśli wartość jest ustawiona na **prawda**, wideo jest zapętlone.</span><span class="sxs-lookup"><span data-stu-id="c3071-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="c3071-136">Multimedia</span><span class="sxs-lookup"><span data-stu-id="c3071-136">Media</span></span>                 | <span data-ttu-id="c3071-137">Ścieżka pliku wideo i nazwa.</span><span class="sxs-lookup"><span data-stu-id="c3071-137">Video file path and name</span></span> | <span data-ttu-id="c3071-138">Plik wideo odtwarzany w odtwarzaczu wideo.</span><span class="sxs-lookup"><span data-stu-id="c3071-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="c3071-139">Tryb pełnoekranowy</span><span class="sxs-lookup"><span data-stu-id="c3071-139">Play fullscreen</span></span>       | <span data-ttu-id="c3071-140">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-140">**True** or **False**</span></span>               | <span data-ttu-id="c3071-141">Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest odtwarzane na pełnym ekranie.</span><span class="sxs-lookup"><span data-stu-id="c3071-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="c3071-142">Odtwórz wyzwalacz wstrzymania</span><span class="sxs-lookup"><span data-stu-id="c3071-142">Play pause trigger</span></span>    | <span data-ttu-id="c3071-143">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-143">**True** or **False**</span></span>               | <span data-ttu-id="c3071-144">Jeśli wartość jest ustawiona na **prawda**, w pliku wideo jest wyświetlany przycisk Odtwórz/Wstrzymaj.</span><span class="sxs-lookup"><span data-stu-id="c3071-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="c3071-145">Kontrolki odtwarzacza wideo</span><span class="sxs-lookup"><span data-stu-id="c3071-145">Video player controls</span></span> | <span data-ttu-id="c3071-146">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-146">**True** or **False**</span></span>               | <span data-ttu-id="c3071-147">Jeśli wartość jest ustawiona na **prawda**, wyświetlane są kontrolki odtwarzacza wideo.</span><span class="sxs-lookup"><span data-stu-id="c3071-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="c3071-148">Te formanty obejmują przyciski odtwarzania i wstrzymywania, wskaźnik postępu oraz opcje napisów kodowanych.</span><span class="sxs-lookup"><span data-stu-id="c3071-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="c3071-149">Ukryj kadr</span><span class="sxs-lookup"><span data-stu-id="c3071-149">Hide poster image</span></span>     | <span data-ttu-id="c3071-150">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="c3071-150">**True** or **False**</span></span>               | <span data-ttu-id="c3071-151">Film wideo może mieć ramkę plakatu.</span><span class="sxs-lookup"><span data-stu-id="c3071-151">A video can have a poster frame.</span></span> <span data-ttu-id="c3071-152">Jeśli dla wartości tej właściwości jest ustawiona wartość **prawda**, ramka plakatu jest ukryta.</span><span class="sxs-lookup"><span data-stu-id="c3071-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="c3071-153">Poziom maski</span><span class="sxs-lookup"><span data-stu-id="c3071-153">Mask level</span></span>            | <span data-ttu-id="c3071-154">Liczba z zakresu od **0** do **100**</span><span class="sxs-lookup"><span data-stu-id="c3071-154">A number from **0** through **100**</span></span> | <span data-ttu-id="c3071-155">Maska zastosowana do obrazu wideo dla stylów.</span><span class="sxs-lookup"><span data-stu-id="c3071-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="c3071-156">Dodawanie modułu odtwarzacza wideo na stronie</span><span class="sxs-lookup"><span data-stu-id="c3071-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="c3071-157">Przed utworzeniem modułu odtwarzacza wideo należy najpierw przekazać wideo do biblioteki multimediów.</span><span class="sxs-lookup"><span data-stu-id="c3071-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="c3071-158">Aby dodać moduł odtwarzacza wideo do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c3071-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c3071-159">Utwórz szablon strony o nazwie nazwa **szablon odtwarzacza wideo**.</span><span class="sxs-lookup"><span data-stu-id="c3071-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="c3071-160">W **Głównym** gnieździe na stronie domyślnej dodaj moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="c3071-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="c3071-161">W module kontener Dodaj moduły odtwarzaczy wideo i odtwarzacze wideo w otoczeniu.</span><span class="sxs-lookup"><span data-stu-id="c3071-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="c3071-162">Zakończ edytowanie szablonu i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="c3071-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="c3071-163">Za pomocą utworzonego szablonu odtwarzacza wideo utwórz stronę o nazwie **strona odtwarzacza wideo**.</span><span class="sxs-lookup"><span data-stu-id="c3071-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="c3071-164">W **Głównym** gnieździe na nowej stronie dodaj moduł odtwarzacza wideo.</span><span class="sxs-lookup"><span data-stu-id="c3071-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="c3071-165">W okienku właściwości modułu odtwarzacza wideo wybierz opcję **Dodaj klip wideo**.</span><span class="sxs-lookup"><span data-stu-id="c3071-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="c3071-166">W oknie dialogowym **Selektor elementów multimedialnych** wybierz plik wideo, a następnie wybierz opcję **Przekaż nowy element multimedialny**.</span><span class="sxs-lookup"><span data-stu-id="c3071-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="c3071-167">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="c3071-167">Save and preview the page.</span></span> <span data-ttu-id="c3071-168">Na stronie powinny być widoczny moduł wideo.</span><span class="sxs-lookup"><span data-stu-id="c3071-168">You should see the video module on the page.</span></span> <span data-ttu-id="c3071-169">Można zmienić dodatkowe ustawienia, aby dostosować zachowanie modułu.</span><span class="sxs-lookup"><span data-stu-id="c3071-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="c3071-170">Zakończ edytowanie strony i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="c3071-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3071-171">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c3071-171">Additional resources</span></span>

[<span data-ttu-id="c3071-172">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="c3071-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c3071-173">Moduł baneru promocyjnego</span><span class="sxs-lookup"><span data-stu-id="c3071-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="c3071-174">Moduł karuzeli</span><span class="sxs-lookup"><span data-stu-id="c3071-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="c3071-175">Moduł bloku zaawansowanej zawartości</span><span class="sxs-lookup"><span data-stu-id="c3071-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="c3071-176">Moduł bloku zawartości</span><span class="sxs-lookup"><span data-stu-id="c3071-176">Content block module</span></span>](add-hero-module.md)
