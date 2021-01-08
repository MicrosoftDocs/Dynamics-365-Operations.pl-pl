---
title: Przekaż obrazy
description: W tym temacie opisano, jak przekazać obrazy do kreatora witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f562d3376fde6a24e6a1e1a3f7f4192cf290ae90
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594291"
---
# <a name="upload-images"></a><span data-ttu-id="93eb9-103">Przekaż obrazy</span><span class="sxs-lookup"><span data-stu-id="93eb9-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="93eb9-104">W tym temacie opisano, jak przekazać obrazy do kreatora witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93eb9-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="93eb9-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="93eb9-105">Overview</span></span>

<span data-ttu-id="93eb9-106">Biblioteka mediów kreatora witryny Commerce umożliwia przekazywanie obrazów, pojedynczo lub razem przy użyciu folderów.</span><span class="sxs-lookup"><span data-stu-id="93eb9-106">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="93eb9-107">Należy zawsze przekazywać wersję obrazu z największą rozdzielczością i jakością, ponieważ element zmiany rozmiaru obrazu automatycznie zoptymalizuje obraz dla różnych wzierników i punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="93eb9-107">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="93eb9-108">Informacje o obrazie określone podczas przekazywania</span><span class="sxs-lookup"><span data-stu-id="93eb9-108">Image information specified during upload</span></span>

<span data-ttu-id="93eb9-109">Podczas przekazywania obrazu można określić następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="93eb9-109">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="93eb9-110">**Tytuł, tekst alternatywny, opis, słowa kluczowe**: metadane obrazu lub obrazów.</span><span class="sxs-lookup"><span data-stu-id="93eb9-110">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="93eb9-111">Tytuł i tekst alternatywny są wymagane.</span><span class="sxs-lookup"><span data-stu-id="93eb9-111">Title and alt text are required values.</span></span>
- <span data-ttu-id="93eb9-112">**Wybierz kategorię**:</span><span class="sxs-lookup"><span data-stu-id="93eb9-112">**Select category**:</span></span>
    - <span data-ttu-id="93eb9-113">**Brak**: używany w przypadku obrazu lub obrazów opowieści w handlu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="93eb9-113">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="93eb9-114">**Produkt, Kategoria, odbiorca, pracownik,katalog**: używany dla obrazów lub obrazów kanału rozproszonego Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93eb9-114">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="93eb9-115">**Publikuj zasoby po przekazaniu**: gdy to pole wyboru jest zaznaczone, obraz lub obrazy są publikowane natychmiast po przekazaniu.</span><span class="sxs-lookup"><span data-stu-id="93eb9-115">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="93eb9-116">Elementy zawartości obrazu z przypisaną kategorią są również automatycznie znakowane za pomocą słowa kluczowego, aby ułatwić wyszukiwanie składników majątku w określonej kategorii.</span><span class="sxs-lookup"><span data-stu-id="93eb9-116">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="93eb9-117">Konwencje nazewnictwa dla obrazów kanału rozproszonego</span><span class="sxs-lookup"><span data-stu-id="93eb9-117">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="93eb9-118">Jeśli biblioteka multimediów została skonfigurowana jako wewnętrzny obraz kanału rozproszonego, można skorzystać z kategorii obrazów w celu wskazania, do której kategorii należy przekazany obraz.</span><span class="sxs-lookup"><span data-stu-id="93eb9-118">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="93eb9-119">Istnieje również Konwencja nazewnictwa, która powinna być stosowana w celu zapewnienia prawidłowego pobierania obrazów przez inne kanały, takie jak punkt sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="93eb9-119">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="93eb9-120">Domyślna konwencja nazewnictwa zmienia się w zależności od kategorii:</span><span class="sxs-lookup"><span data-stu-id="93eb9-120">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="93eb9-121">Obrazy wykazu powinny mieć nazwę „**/katalogi/\{identyfikator_języka\}/\{nazwa_katalogu\}.jpg**”</span><span class="sxs-lookup"><span data-stu-id="93eb9-121">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="93eb9-122">Obrazy kategorii powinny mieć nazwę „**/kategorie/\{nazwa_kategorii\}.png**”</span><span class="sxs-lookup"><span data-stu-id="93eb9-122">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="93eb9-123">Obrazy odbiorców powinny mieć nazwę „**/odbiorcy/\{nuer_odbiorcy\}.jpg**”</span><span class="sxs-lookup"><span data-stu-id="93eb9-123">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="93eb9-124">Obrazy pracowników powinny mieć nazwę „**/pracownicy/\{numer_pracownika\}.jpg**”</span><span class="sxs-lookup"><span data-stu-id="93eb9-124">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="93eb9-125">Obrazy produktów powinny mieć nazwę „**/Produkty/\{numer_Produktu\}_000_001.png**”</span><span class="sxs-lookup"><span data-stu-id="93eb9-125">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="93eb9-126">001 oznacza sekwencję obrazu i może być 001, 002, 003, 004 lub 005</span><span class="sxs-lookup"><span data-stu-id="93eb9-126">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="93eb9-127">Obrazy wariantów produktów powinny mieć nazwę „**/Produkty/\{numer_Produktu\}\_\{Rozmiar\}\_\{Color\}\_\{Styl\}\_000_001.png**”</span><span class="sxs-lookup"><span data-stu-id="93eb9-127">Product variant images should be named "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="93eb9-128">Przekaż obraz</span><span class="sxs-lookup"><span data-stu-id="93eb9-128">Upload an image</span></span>

<span data-ttu-id="93eb9-129">Aby przekazać obraz w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="93eb9-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="93eb9-130">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="93eb9-131">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="93eb9-132">W oknie Eksploratora plików przejdź do jednego lub więcej obrazów do przekazania i wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="93eb9-133">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="93eb9-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="93eb9-134">Wprowadź opcjonalny opis i słowa kluczowe, a w razie potrzeby wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="93eb9-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="93eb9-135">Jeśli chcesz opublikować obrazy po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="93eb9-136">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="93eb9-137">Przekaż folder obrazów</span><span class="sxs-lookup"><span data-stu-id="93eb9-137">Upload a folder of images</span></span>

<span data-ttu-id="93eb9-138">Aby przekazać wiele obrazów w folderze w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="93eb9-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="93eb9-139">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="93eb9-140">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż folder**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="93eb9-141">W oknie Eksploratora plików przejdź i wybierz folder do przekazania, po czym wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="93eb9-142">W oknie dialogowym **przekazywanie elementów multimedialnych** wprowadź opcjonalne słowa kluczowe i w razie potrzeby wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="93eb9-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="93eb9-143">Jeśli chcesz opublikować obrazy w folderze po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="93eb9-144">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="93eb9-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93eb9-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="93eb9-145">Additional resources</span></span>

[<span data-ttu-id="93eb9-146">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="93eb9-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="93eb9-147">Przekazanie wideo</span><span class="sxs-lookup"><span data-stu-id="93eb9-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="93eb9-148">Przekaż pliki</span><span class="sxs-lookup"><span data-stu-id="93eb9-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="93eb9-149">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="93eb9-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="93eb9-150">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="93eb9-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="93eb9-151">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="93eb9-151">Upload and serve static files</span></span>](upload-serve-static-files.md)
