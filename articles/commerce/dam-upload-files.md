---
title: Przekaż pliki inne niż obrazy i wideo
description: W tym temacie opisano sposób przekazywania plików binarnych innych niż obrazy i wideo w kreatorze witryn rozwiązania Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3392f5f36d04e8cb0a9d6e6b7db31ff62c987649
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995777"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="8e606-103">Przekaż pliki inne niż obrazy i wideo</span><span class="sxs-lookup"><span data-stu-id="8e606-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8e606-104">W tym temacie opisano sposób przekazywania plików innych niż obrazy i wideo w kreatorze witryn rozwiązania Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8e606-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="8e606-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="8e606-105">Overview</span></span>

<span data-ttu-id="8e606-106">Biblioteka medialna kreatora witryn Commerce obsługuje przekazywanie składników binarnych innych niż obrazy i wideo.</span><span class="sxs-lookup"><span data-stu-id="8e606-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="8e606-107">Może to być na przykład przekazanie plików programów Microsoft Excel, Microsoft Word, Microsoft PowerPoint lub PDF.</span><span class="sxs-lookup"><span data-stu-id="8e606-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="8e606-108">Następujące typy dokumentów są obsługiwane:</span><span class="sxs-lookup"><span data-stu-id="8e606-108">The following document types are supported:</span></span>
- <span data-ttu-id="8e606-109">7Z</span><span class="sxs-lookup"><span data-stu-id="8e606-109">7Z</span></span>
- <span data-ttu-id="8e606-110">AVI</span><span class="sxs-lookup"><span data-stu-id="8e606-110">AVI</span></span>
- <span data-ttu-id="8e606-111">CS</span><span class="sxs-lookup"><span data-stu-id="8e606-111">CS</span></span>
- <span data-ttu-id="8e606-112">CSS</span><span class="sxs-lookup"><span data-stu-id="8e606-112">CSS</span></span>
- <span data-ttu-id="8e606-113">DOC</span><span class="sxs-lookup"><span data-stu-id="8e606-113">DOC</span></span>
- <span data-ttu-id="8e606-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="8e606-114">DOCX</span></span>
- <span data-ttu-id="8e606-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="8e606-115">EPUB</span></span>
- <span data-ttu-id="8e606-116">GIF</span><span class="sxs-lookup"><span data-stu-id="8e606-116">GIF</span></span>
- <span data-ttu-id="8e606-117">INDD</span><span class="sxs-lookup"><span data-stu-id="8e606-117">INDD</span></span>
- <span data-ttu-id="8e606-118">JAR</span><span class="sxs-lookup"><span data-stu-id="8e606-118">JAR</span></span>
- <span data-ttu-id="8e606-119">JPG</span><span class="sxs-lookup"><span data-stu-id="8e606-119">JPG</span></span>
- <span data-ttu-id="8e606-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="8e606-120">JPEG</span></span>
- <span data-ttu-id="8e606-121">JS</span><span class="sxs-lookup"><span data-stu-id="8e606-121">JS</span></span>
- <span data-ttu-id="8e606-122">MP3</span><span class="sxs-lookup"><span data-stu-id="8e606-122">MP3</span></span>
- <span data-ttu-id="8e606-123">MP4</span><span class="sxs-lookup"><span data-stu-id="8e606-123">MP4</span></span>
- <span data-ttu-id="8e606-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="8e606-124">MPEG</span></span>
- <span data-ttu-id="8e606-125">MPG</span><span class="sxs-lookup"><span data-stu-id="8e606-125">MPG</span></span>
- <span data-ttu-id="8e606-126">ODP</span><span class="sxs-lookup"><span data-stu-id="8e606-126">ODP</span></span>
- <span data-ttu-id="8e606-127">ODS</span><span class="sxs-lookup"><span data-stu-id="8e606-127">ODS</span></span>
- <span data-ttu-id="8e606-128">ODT</span><span class="sxs-lookup"><span data-stu-id="8e606-128">ODT</span></span>
- <span data-ttu-id="8e606-129">PDF</span><span class="sxs-lookup"><span data-stu-id="8e606-129">PDF</span></span>
- <span data-ttu-id="8e606-130">PNG</span><span class="sxs-lookup"><span data-stu-id="8e606-130">PNG</span></span>
- <span data-ttu-id="8e606-131">PPT</span><span class="sxs-lookup"><span data-stu-id="8e606-131">PPT</span></span>
- <span data-ttu-id="8e606-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="8e606-132">PPTX</span></span>
- <span data-ttu-id="8e606-133">PS</span><span class="sxs-lookup"><span data-stu-id="8e606-133">PS</span></span>
- <span data-ttu-id="8e606-134">QXP</span><span class="sxs-lookup"><span data-stu-id="8e606-134">QXP</span></span>
- <span data-ttu-id="8e606-135">RAR</span><span class="sxs-lookup"><span data-stu-id="8e606-135">RAR</span></span>
- <span data-ttu-id="8e606-136">RTF</span><span class="sxs-lookup"><span data-stu-id="8e606-136">RTF</span></span>
- <span data-ttu-id="8e606-137">SVG</span><span class="sxs-lookup"><span data-stu-id="8e606-137">SVG</span></span>
- <span data-ttu-id="8e606-138">TAR</span><span class="sxs-lookup"><span data-stu-id="8e606-138">TAR</span></span>
- <span data-ttu-id="8e606-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="8e606-139">TGZ</span></span>
- <span data-ttu-id="8e606-140">TXT</span><span class="sxs-lookup"><span data-stu-id="8e606-140">TXT</span></span>
- <span data-ttu-id="8e606-141">WMV</span><span class="sxs-lookup"><span data-stu-id="8e606-141">WMV</span></span>
- <span data-ttu-id="8e606-142">XLS</span><span class="sxs-lookup"><span data-stu-id="8e606-142">XLS</span></span>
- <span data-ttu-id="8e606-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="8e606-143">XLSX</span></span>
- <span data-ttu-id="8e606-144">Plik XML</span><span class="sxs-lookup"><span data-stu-id="8e606-144">XML</span></span>
- <span data-ttu-id="8e606-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="8e606-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="8e606-146">Przekaż plik</span><span class="sxs-lookup"><span data-stu-id="8e606-146">Upload a file</span></span>

<span data-ttu-id="8e606-147">Aby przekazać plik do kreatora witryny w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8e606-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8e606-148">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="8e606-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="8e606-149">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="8e606-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="8e606-150">W Eksploratorze plików wybierz jeden lub więcej plików, a następnie wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="8e606-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="8e606-151">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź odpowiednio tytuł, opis i metadane słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="8e606-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="8e606-152">Jeśli chcesz opublikować pliki po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="8e606-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="8e606-153">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e606-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8e606-154">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8e606-154">Additional resources</span></span>

[<span data-ttu-id="8e606-155">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="8e606-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="8e606-156">Przekazanie obrazów</span><span class="sxs-lookup"><span data-stu-id="8e606-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="8e606-157">Przekazanie wideo</span><span class="sxs-lookup"><span data-stu-id="8e606-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="8e606-158">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="8e606-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="8e606-159">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="8e606-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="8e606-160">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="8e606-160">Upload and serve static files</span></span>](upload-serve-static-files.md)
