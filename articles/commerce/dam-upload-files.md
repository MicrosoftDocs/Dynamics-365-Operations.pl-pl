---
title: Przekaż pliki inne niż obrazy i wideo
description: W tym temacie opisano sposób przekazywania plików binarnych innych niż obrazy i wideo w kreatorze witryn rozwiązania Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
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
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799260"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="1e398-103">Przekazanie plików innych niż obrazy i wideo</span><span class="sxs-lookup"><span data-stu-id="1e398-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1e398-104">W tym temacie opisano sposób przekazywania plików innych niż obrazy i wideo w kreatorze witryn rozwiązania Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1e398-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="1e398-105">Biblioteka medialna kreatora witryn Commerce obsługuje przekazywanie składników binarnych innych niż obrazy i wideo.</span><span class="sxs-lookup"><span data-stu-id="1e398-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="1e398-106">Może to być na przykład przekazanie plików programów Microsoft Excel, Microsoft Word, Microsoft PowerPoint lub PDF.</span><span class="sxs-lookup"><span data-stu-id="1e398-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="1e398-107">Następujące typy dokumentów są obsługiwane:</span><span class="sxs-lookup"><span data-stu-id="1e398-107">The following document types are supported:</span></span>
- <span data-ttu-id="1e398-108">7Z</span><span class="sxs-lookup"><span data-stu-id="1e398-108">7Z</span></span>
- <span data-ttu-id="1e398-109">AVI</span><span class="sxs-lookup"><span data-stu-id="1e398-109">AVI</span></span>
- <span data-ttu-id="1e398-110">CS</span><span class="sxs-lookup"><span data-stu-id="1e398-110">CS</span></span>
- <span data-ttu-id="1e398-111">CSS</span><span class="sxs-lookup"><span data-stu-id="1e398-111">CSS</span></span>
- <span data-ttu-id="1e398-112">DOC</span><span class="sxs-lookup"><span data-stu-id="1e398-112">DOC</span></span>
- <span data-ttu-id="1e398-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="1e398-113">DOCX</span></span>
- <span data-ttu-id="1e398-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="1e398-114">EPUB</span></span>
- <span data-ttu-id="1e398-115">GIF</span><span class="sxs-lookup"><span data-stu-id="1e398-115">GIF</span></span>
- <span data-ttu-id="1e398-116">INDD</span><span class="sxs-lookup"><span data-stu-id="1e398-116">INDD</span></span>
- <span data-ttu-id="1e398-117">JAR</span><span class="sxs-lookup"><span data-stu-id="1e398-117">JAR</span></span>
- <span data-ttu-id="1e398-118">JPG</span><span class="sxs-lookup"><span data-stu-id="1e398-118">JPG</span></span>
- <span data-ttu-id="1e398-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="1e398-119">JPEG</span></span>
- <span data-ttu-id="1e398-120">JS</span><span class="sxs-lookup"><span data-stu-id="1e398-120">JS</span></span>
- <span data-ttu-id="1e398-121">MP3</span><span class="sxs-lookup"><span data-stu-id="1e398-121">MP3</span></span>
- <span data-ttu-id="1e398-122">MP4</span><span class="sxs-lookup"><span data-stu-id="1e398-122">MP4</span></span>
- <span data-ttu-id="1e398-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="1e398-123">MPEG</span></span>
- <span data-ttu-id="1e398-124">MPG</span><span class="sxs-lookup"><span data-stu-id="1e398-124">MPG</span></span>
- <span data-ttu-id="1e398-125">ODP</span><span class="sxs-lookup"><span data-stu-id="1e398-125">ODP</span></span>
- <span data-ttu-id="1e398-126">ODS</span><span class="sxs-lookup"><span data-stu-id="1e398-126">ODS</span></span>
- <span data-ttu-id="1e398-127">ODT</span><span class="sxs-lookup"><span data-stu-id="1e398-127">ODT</span></span>
- <span data-ttu-id="1e398-128">PDF</span><span class="sxs-lookup"><span data-stu-id="1e398-128">PDF</span></span>
- <span data-ttu-id="1e398-129">PNG</span><span class="sxs-lookup"><span data-stu-id="1e398-129">PNG</span></span>
- <span data-ttu-id="1e398-130">PPT</span><span class="sxs-lookup"><span data-stu-id="1e398-130">PPT</span></span>
- <span data-ttu-id="1e398-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="1e398-131">PPTX</span></span>
- <span data-ttu-id="1e398-132">PS</span><span class="sxs-lookup"><span data-stu-id="1e398-132">PS</span></span>
- <span data-ttu-id="1e398-133">QXP</span><span class="sxs-lookup"><span data-stu-id="1e398-133">QXP</span></span>
- <span data-ttu-id="1e398-134">RAR</span><span class="sxs-lookup"><span data-stu-id="1e398-134">RAR</span></span>
- <span data-ttu-id="1e398-135">RTF</span><span class="sxs-lookup"><span data-stu-id="1e398-135">RTF</span></span>
- <span data-ttu-id="1e398-136">SVG</span><span class="sxs-lookup"><span data-stu-id="1e398-136">SVG</span></span>
- <span data-ttu-id="1e398-137">TAR</span><span class="sxs-lookup"><span data-stu-id="1e398-137">TAR</span></span>
- <span data-ttu-id="1e398-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="1e398-138">TGZ</span></span>
- <span data-ttu-id="1e398-139">TXT</span><span class="sxs-lookup"><span data-stu-id="1e398-139">TXT</span></span>
- <span data-ttu-id="1e398-140">WMV</span><span class="sxs-lookup"><span data-stu-id="1e398-140">WMV</span></span>
- <span data-ttu-id="1e398-141">XLS</span><span class="sxs-lookup"><span data-stu-id="1e398-141">XLS</span></span>
- <span data-ttu-id="1e398-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="1e398-142">XLSX</span></span>
- <span data-ttu-id="1e398-143">Plik XML</span><span class="sxs-lookup"><span data-stu-id="1e398-143">XML</span></span>
- <span data-ttu-id="1e398-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="1e398-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="1e398-145">Przekaż plik</span><span class="sxs-lookup"><span data-stu-id="1e398-145">Upload a file</span></span>

<span data-ttu-id="1e398-146">Aby przekazać plik do kreatora witryny w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1e398-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e398-147">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="1e398-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="1e398-148">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="1e398-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="1e398-149">W Eksploratorze plików wybierz jeden lub więcej plików, a następnie wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="1e398-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="1e398-150">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź odpowiednio tytuł, opis i metadane słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="1e398-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="1e398-151">Jeśli chcesz opublikować pliki po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="1e398-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="1e398-152">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e398-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e398-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1e398-153">Additional resources</span></span>

[<span data-ttu-id="1e398-154">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="1e398-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="1e398-155">Przekazanie obrazów</span><span class="sxs-lookup"><span data-stu-id="1e398-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="1e398-156">Przekazanie wideo</span><span class="sxs-lookup"><span data-stu-id="1e398-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="1e398-157">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="1e398-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="1e398-158">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="1e398-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="1e398-159">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="1e398-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
