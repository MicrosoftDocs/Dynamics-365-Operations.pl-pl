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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: fc0490e3532dcbb9c1e91101009b2d4605315416
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097066"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="d533f-103">Przekaż pliki inne niż obrazy i wideo</span><span class="sxs-lookup"><span data-stu-id="d533f-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d533f-104">W tym temacie opisano sposób przekazywania plików innych niż obrazy i wideo w kreatorze witryn rozwiązania Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d533f-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="d533f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d533f-105">Overview</span></span>

<span data-ttu-id="d533f-106">Biblioteka medialna kreatora witryn Commerce obsługuje przekazywanie składników binarnych innych niż obrazy i wideo.</span><span class="sxs-lookup"><span data-stu-id="d533f-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="d533f-107">Może to być na przykład przekazanie plików programów Microsoft Excel, Microsoft Word, Microsoft PowerPoint lub PDF.</span><span class="sxs-lookup"><span data-stu-id="d533f-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="d533f-108">Następujące typy dokumentów są obsługiwane:</span><span class="sxs-lookup"><span data-stu-id="d533f-108">The following document types are supported:</span></span>
- <span data-ttu-id="d533f-109">7Z</span><span class="sxs-lookup"><span data-stu-id="d533f-109">7Z</span></span>
- <span data-ttu-id="d533f-110">AVI</span><span class="sxs-lookup"><span data-stu-id="d533f-110">AVI</span></span>
- <span data-ttu-id="d533f-111">CS</span><span class="sxs-lookup"><span data-stu-id="d533f-111">CS</span></span>
- <span data-ttu-id="d533f-112">CSS</span><span class="sxs-lookup"><span data-stu-id="d533f-112">CSS</span></span>
- <span data-ttu-id="d533f-113">DOC</span><span class="sxs-lookup"><span data-stu-id="d533f-113">DOC</span></span>
- <span data-ttu-id="d533f-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="d533f-114">DOCX</span></span>
- <span data-ttu-id="d533f-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="d533f-115">EPUB</span></span>
- <span data-ttu-id="d533f-116">GIF</span><span class="sxs-lookup"><span data-stu-id="d533f-116">GIF</span></span>
- <span data-ttu-id="d533f-117">INDD</span><span class="sxs-lookup"><span data-stu-id="d533f-117">INDD</span></span>
- <span data-ttu-id="d533f-118">JAR</span><span class="sxs-lookup"><span data-stu-id="d533f-118">JAR</span></span>
- <span data-ttu-id="d533f-119">JPG</span><span class="sxs-lookup"><span data-stu-id="d533f-119">JPG</span></span>
- <span data-ttu-id="d533f-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="d533f-120">JPEG</span></span>
- <span data-ttu-id="d533f-121">JS</span><span class="sxs-lookup"><span data-stu-id="d533f-121">JS</span></span>
- <span data-ttu-id="d533f-122">MP3</span><span class="sxs-lookup"><span data-stu-id="d533f-122">MP3</span></span>
- <span data-ttu-id="d533f-123">MP4</span><span class="sxs-lookup"><span data-stu-id="d533f-123">MP4</span></span>
- <span data-ttu-id="d533f-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="d533f-124">MPEG</span></span>
- <span data-ttu-id="d533f-125">MPG</span><span class="sxs-lookup"><span data-stu-id="d533f-125">MPG</span></span>
- <span data-ttu-id="d533f-126">ODP</span><span class="sxs-lookup"><span data-stu-id="d533f-126">ODP</span></span>
- <span data-ttu-id="d533f-127">ODS</span><span class="sxs-lookup"><span data-stu-id="d533f-127">ODS</span></span>
- <span data-ttu-id="d533f-128">ODT</span><span class="sxs-lookup"><span data-stu-id="d533f-128">ODT</span></span>
- <span data-ttu-id="d533f-129">PDF</span><span class="sxs-lookup"><span data-stu-id="d533f-129">PDF</span></span>
- <span data-ttu-id="d533f-130">PNG</span><span class="sxs-lookup"><span data-stu-id="d533f-130">PNG</span></span>
- <span data-ttu-id="d533f-131">PPT</span><span class="sxs-lookup"><span data-stu-id="d533f-131">PPT</span></span>
- <span data-ttu-id="d533f-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="d533f-132">PPTX</span></span>
- <span data-ttu-id="d533f-133">PS</span><span class="sxs-lookup"><span data-stu-id="d533f-133">PS</span></span>
- <span data-ttu-id="d533f-134">QXP</span><span class="sxs-lookup"><span data-stu-id="d533f-134">QXP</span></span>
- <span data-ttu-id="d533f-135">RAR</span><span class="sxs-lookup"><span data-stu-id="d533f-135">RAR</span></span>
- <span data-ttu-id="d533f-136">RTF</span><span class="sxs-lookup"><span data-stu-id="d533f-136">RTF</span></span>
- <span data-ttu-id="d533f-137">SVG</span><span class="sxs-lookup"><span data-stu-id="d533f-137">SVG</span></span>
- <span data-ttu-id="d533f-138">TAR</span><span class="sxs-lookup"><span data-stu-id="d533f-138">TAR</span></span>
- <span data-ttu-id="d533f-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="d533f-139">TGZ</span></span>
- <span data-ttu-id="d533f-140">TXT</span><span class="sxs-lookup"><span data-stu-id="d533f-140">TXT</span></span>
- <span data-ttu-id="d533f-141">WMV</span><span class="sxs-lookup"><span data-stu-id="d533f-141">WMV</span></span>
- <span data-ttu-id="d533f-142">XLS</span><span class="sxs-lookup"><span data-stu-id="d533f-142">XLS</span></span>
- <span data-ttu-id="d533f-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="d533f-143">XLSX</span></span>
- <span data-ttu-id="d533f-144">Plik XML</span><span class="sxs-lookup"><span data-stu-id="d533f-144">XML</span></span>
- <span data-ttu-id="d533f-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="d533f-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="d533f-146">Przekaż plik</span><span class="sxs-lookup"><span data-stu-id="d533f-146">Upload a file</span></span>

<span data-ttu-id="d533f-147">Aby przekazać plik do kreatora witryny w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d533f-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d533f-148">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="d533f-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="d533f-149">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="d533f-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="d533f-150">W Eksploratorze plików wybierz jeden lub więcej plików, a następnie wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="d533f-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="d533f-151">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź odpowiednio tytuł, opis i metadane słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="d533f-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="d533f-152">Jeśli chcesz opublikować pliki po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="d533f-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="d533f-153">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d533f-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d533f-154">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d533f-154">Additional resources</span></span>

[<span data-ttu-id="d533f-155">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="d533f-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="d533f-156">Przekaż obrazy</span><span class="sxs-lookup"><span data-stu-id="d533f-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="d533f-157">Przekaż plik wideo</span><span class="sxs-lookup"><span data-stu-id="d533f-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="d533f-158">Przytnij obrazy</span><span class="sxs-lookup"><span data-stu-id="d533f-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="d533f-159">Dostosuj punkty ogniskowe obrazu</span><span class="sxs-lookup"><span data-stu-id="d533f-159">Customize image focal points</span></span>](dam-custom-focal-point.md)
