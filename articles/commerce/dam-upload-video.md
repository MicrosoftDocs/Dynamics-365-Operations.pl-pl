---
title: Przekaż pliki wideo
description: W tym temacie opisano, jak przesyłać pliki wideo w kreatorze witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e3579b54c58898b79c84406480a3b58f541c4621
ms.sourcegitcommit: 257437a57e146496a49782bc8aad179c92fbf6e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2021
ms.locfileid: "6224545"
---
# <a name="upload-videos"></a><span data-ttu-id="39f8e-103">Przekaż pliki wideo</span><span class="sxs-lookup"><span data-stu-id="39f8e-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="39f8e-104">W tym temacie opisano, jak przesyłać pliki wideo w kreatorze witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="39f8e-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="39f8e-105">Biblioteka mediów kreatora witryny Commerce umożliwia przekazywanie plików wideo.</span><span class="sxs-lookup"><span data-stu-id="39f8e-105">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="39f8e-106">Należy zawsze przekazywać wersję klipu wideo z największą szybkością transmisji bitów, ponieważ film wideo zostanie automatycznie przekonwertowany na odpowiedni dla różnych wzierników i punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="39f8e-106">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="39f8e-107">Informacje o wideo określone podczas przekazywania</span><span class="sxs-lookup"><span data-stu-id="39f8e-107">Video information specified during upload</span></span>

<span data-ttu-id="39f8e-108">Podczas przekazywania wideo można określić następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="39f8e-108">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="39f8e-109">**Tytuł, opis, słowa kluczowe**: metadane klipu wideo.</span><span class="sxs-lookup"><span data-stu-id="39f8e-109">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="39f8e-110">**Automatycznie Generuj podpisy kodowane**: określa, czy dla danego klipu wideo powinny być automatycznie generowane podpisy kodowane (obsługiwany jest tylko język angielski).</span><span class="sxs-lookup"><span data-stu-id="39f8e-110">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video (only English language is supported).</span></span> 
- <span data-ttu-id="39f8e-111">**Podpis kodowany**: określa podpisy kodowane, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="39f8e-111">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="39f8e-112">**Zwykły dźwięk**: określa normalną ścieżkę audio, która ma być użyta.</span><span class="sxs-lookup"><span data-stu-id="39f8e-112">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="39f8e-113">**Miniatura**: określa miniaturę klipu wideo.</span><span class="sxs-lookup"><span data-stu-id="39f8e-113">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="39f8e-114">Jeśli nie zostały określone, będą one generowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="39f8e-114">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="39f8e-115">**Opisowy dźwięk**: określa opisową ścieżkę audio, która ma być użyta.</span><span class="sxs-lookup"><span data-stu-id="39f8e-115">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="39f8e-116">Przekaż plik wideo</span><span class="sxs-lookup"><span data-stu-id="39f8e-116">Upload a video</span></span>

<span data-ttu-id="39f8e-117">Aby przekazać wideo w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="39f8e-117">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="39f8e-118">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="39f8e-118">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="39f8e-119">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="39f8e-119">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="39f8e-120">W oknie Eksploratora plików przejdź do jednego lub więcej plików wideo do przekazania i wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="39f8e-120">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="39f8e-121">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="39f8e-121">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="39f8e-122">Wprowadź opcjonalny opis i słowa kluczowe, a w razie potrzeby wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="39f8e-122">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="39f8e-123">Jeśli chcesz opublikować obrazy po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**</span><span class="sxs-lookup"><span data-stu-id="39f8e-123">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="39f8e-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="39f8e-124">Select **OK**.</span></span>

<span data-ttu-id="39f8e-125">Jeśli wiele typów zasobów jest przekazywanych jednocześnie (na przykład obrazy i pliki wideo), w oknie dialogowym **przekazywanie elementu multimedialnego** można określać tylko słowa kluczowe, niezależnie od tego, czy pliki powinny być publikowane natychmiast po przekazaniu, czy mają być automatycznie generowane podpisy kodowane dla plików wideo.</span><span class="sxs-lookup"><span data-stu-id="39f8e-125">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="39f8e-126">Wszystkie składniki majątku mają takie same słowa kluczowe.</span><span class="sxs-lookup"><span data-stu-id="39f8e-126">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39f8e-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="39f8e-127">Additional resources</span></span>

[<span data-ttu-id="39f8e-128">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="39f8e-128">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="39f8e-129">Przekazanie obrazów</span><span class="sxs-lookup"><span data-stu-id="39f8e-129">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="39f8e-130">Przekaż pliki</span><span class="sxs-lookup"><span data-stu-id="39f8e-130">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="39f8e-131">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="39f8e-131">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="39f8e-132">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="39f8e-132">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="39f8e-133">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="39f8e-133">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
