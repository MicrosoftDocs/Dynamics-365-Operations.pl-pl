---
title: Przekaż pliki wideo
description: W tym temacie opisano, jak przekazać pliki wideo do kreatora witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8dd9e710f9a6ea593a0673e7902fadf84ca05cff
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594315"
---
# <a name="upload-videos"></a><span data-ttu-id="9d064-103">Przekaż pliki wideo</span><span class="sxs-lookup"><span data-stu-id="9d064-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9d064-104">W tym temacie opisano, jak przekazać pliki wideo do kreatora witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d064-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="9d064-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9d064-105">Overview</span></span>

<span data-ttu-id="9d064-106">Biblioteka mediów kreatora witryny Commerce umożliwia przekazywanie plików wideo.</span><span class="sxs-lookup"><span data-stu-id="9d064-106">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="9d064-107">Należy zawsze przekazywać wersję klipu wideo z największą szybkością transmisji bitów, ponieważ film wideo zostanie automatycznie przekonwertowany na odpowiedni dla różnych wzierników i punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="9d064-107">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="9d064-108">Informacje o wideo określone podczas przekazywania</span><span class="sxs-lookup"><span data-stu-id="9d064-108">Video information specified during upload</span></span>

<span data-ttu-id="9d064-109">Podczas przekazywania wideo można określić następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="9d064-109">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="9d064-110">**Tytuł, opis, słowa kluczowe**: metadane klipu wideo.</span><span class="sxs-lookup"><span data-stu-id="9d064-110">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="9d064-111">**Automatycznie Generuj podpisy kodowane**: określa, czy dla danego klipu wideo powinny być automatycznie generowane podpisy kodowane.</span><span class="sxs-lookup"><span data-stu-id="9d064-111">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="9d064-112">**Podpis kodowany**: określa podpisy kodowane, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="9d064-112">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="9d064-113">**Zwykły dźwięk**: określa normalną ścieżkę audio, która ma być użyta.</span><span class="sxs-lookup"><span data-stu-id="9d064-113">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="9d064-114">**Miniatura**: określa miniaturę klipu wideo.</span><span class="sxs-lookup"><span data-stu-id="9d064-114">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="9d064-115">Jeśli nie zostały określone, będą one generowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="9d064-115">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="9d064-116">**Opisowy dźwięk**: określa opisową ścieżkę audio, która ma być użyta.</span><span class="sxs-lookup"><span data-stu-id="9d064-116">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="9d064-117">Przekaż plik wideo</span><span class="sxs-lookup"><span data-stu-id="9d064-117">Upload a video</span></span>

<span data-ttu-id="9d064-118">Aby przekazać wideo w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="9d064-118">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="9d064-119">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="9d064-119">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="9d064-120">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="9d064-120">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="9d064-121">W oknie Eksploratora plików przejdź do jednego lub więcej plików wideo do przekazania i wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="9d064-121">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="9d064-122">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="9d064-122">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="9d064-123">Wprowadź opcjonalny opis i słowa kluczowe, a w razie potrzeby wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="9d064-123">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="9d064-124">Jeśli chcesz opublikować obrazy po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**</span><span class="sxs-lookup"><span data-stu-id="9d064-124">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="9d064-125">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d064-125">Select **OK**.</span></span>

<span data-ttu-id="9d064-126">Jeśli wiele typów zasobów jest przekazywanych jednocześnie (na przykład obrazy i pliki wideo), w oknie dialogowym **przekazywanie elementu multimedialnego** można określać tylko słowa kluczowe, niezależnie od tego, czy pliki powinny być publikowane natychmiast po przekazaniu, czy mają być automatycznie generowane podpisy kodowane dla plików wideo.</span><span class="sxs-lookup"><span data-stu-id="9d064-126">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="9d064-127">Wszystkie składniki majątku mają takie same słowa kluczowe.</span><span class="sxs-lookup"><span data-stu-id="9d064-127">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d064-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9d064-128">Additional resources</span></span>

[<span data-ttu-id="9d064-129">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="9d064-129">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="9d064-130">Przekazanie obrazów</span><span class="sxs-lookup"><span data-stu-id="9d064-130">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="9d064-131">Przekaż pliki</span><span class="sxs-lookup"><span data-stu-id="9d064-131">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="9d064-132">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="9d064-132">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="9d064-133">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="9d064-133">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="9d064-134">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="9d064-134">Upload and serve static files</span></span>](upload-serve-static-files.md)
