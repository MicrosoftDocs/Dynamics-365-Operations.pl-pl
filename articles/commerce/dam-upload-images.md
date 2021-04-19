---
title: Przekazanie obrazów
description: W tym temacie opisano, jak przesyłać obrazy w kreatorze witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799236"
---
# <a name="upload-images"></a><span data-ttu-id="fe791-103">Przekazanie obrazów</span><span class="sxs-lookup"><span data-stu-id="fe791-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe791-104">W tym temacie opisano, jak przesyłać obrazy w kreatorze witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe791-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="fe791-105">Biblioteka mediów kreatora witryny Commerce umożliwia przekazywanie obrazów, pojedynczo lub razem przy użyciu folderów.</span><span class="sxs-lookup"><span data-stu-id="fe791-105">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="fe791-106">Należy zawsze przekazywać wersję obrazu z największą rozdzielczością i jakością, ponieważ element zmiany rozmiaru obrazu automatycznie zoptymalizuje obraz dla różnych wzierników i punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="fe791-106">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="fe791-107">Informacje o obrazie określone podczas przekazywania</span><span class="sxs-lookup"><span data-stu-id="fe791-107">Image information specified during upload</span></span>

<span data-ttu-id="fe791-108">Podczas przekazywania obrazu można określić następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="fe791-108">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="fe791-109">**Tytuł, tekst alternatywny, opis, słowa kluczowe**: metadane obrazu lub obrazów.</span><span class="sxs-lookup"><span data-stu-id="fe791-109">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="fe791-110">Tytuł i tekst alternatywny są wymagane.</span><span class="sxs-lookup"><span data-stu-id="fe791-110">Title and alt text are required values.</span></span>
- <span data-ttu-id="fe791-111">**Wybierz kategorię**:</span><span class="sxs-lookup"><span data-stu-id="fe791-111">**Select category**:</span></span>
    - <span data-ttu-id="fe791-112">**Brak**: używany w przypadku obrazu lub obrazów opowieści w handlu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="fe791-112">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="fe791-113">**Produkt, Kategoria, odbiorca, pracownik,katalog**: używany dla obrazów lub obrazów kanału rozproszonego Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe791-113">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="fe791-114">**Publikuj zasoby po przekazaniu**: gdy to pole wyboru jest zaznaczone, obraz lub obrazy są publikowane natychmiast po przekazaniu.</span><span class="sxs-lookup"><span data-stu-id="fe791-114">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="fe791-115">Elementy zawartości obrazu z przypisaną kategorią są również automatycznie znakowane za pomocą słowa kluczowego, aby ułatwić wyszukiwanie składników majątku w określonej kategorii.</span><span class="sxs-lookup"><span data-stu-id="fe791-115">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="fe791-116">Konwencje nazewnictwa dla obrazów kanału rozproszonego</span><span class="sxs-lookup"><span data-stu-id="fe791-116">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="fe791-117">Jeśli biblioteka multimediów została skonfigurowana jako wewnętrzny obraz kanału rozproszonego, można skorzystać z kategorii obrazów w celu wskazania, do której kategorii należy przekazany obraz.</span><span class="sxs-lookup"><span data-stu-id="fe791-117">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="fe791-118">Istnieje również Konwencja nazewnictwa, która powinna być stosowana w celu zapewnienia prawidłowego pobierania obrazów przez inne kanały, takie jak punkt sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="fe791-118">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="fe791-119">Domyślna konwencja nazewnictwa zmienia się w zależności od kategorii:</span><span class="sxs-lookup"><span data-stu-id="fe791-119">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="fe791-120">Obrazy wykazu powinny mieć nazwę „**/katalogi/\{identyfikator_języka\}/\{nazwa_katalogu\}.jpg**”</span><span class="sxs-lookup"><span data-stu-id="fe791-120">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="fe791-121">Obrazy kategorii powinny mieć nazwę „**/kategorie/\{nazwa_kategorii\}.png**”</span><span class="sxs-lookup"><span data-stu-id="fe791-121">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="fe791-122">Obrazy odbiorców powinny mieć nazwę „**/odbiorcy/\{nuer_odbiorcy\}.jpg**”</span><span class="sxs-lookup"><span data-stu-id="fe791-122">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="fe791-123">Obrazy pracowników powinny mieć nazwę „**/pracownicy/\{numer_pracownika\}.jpg**”</span><span class="sxs-lookup"><span data-stu-id="fe791-123">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="fe791-124">Obrazy produktów powinny mieć nazwę „**/Produkty/\{numer_Produktu\}_000_001.png**”</span><span class="sxs-lookup"><span data-stu-id="fe791-124">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="fe791-125">001 oznacza sekwencję obrazu i może być 001, 002, 003, 004 lub 005</span><span class="sxs-lookup"><span data-stu-id="fe791-125">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="fe791-126">Obrazy wariantów produktów powinny mieć nazwę „**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**”</span><span class="sxs-lookup"><span data-stu-id="fe791-126">Product variant images should be named "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span></span>
    - <span data-ttu-id="fe791-127">Na przykład: 93039 \^ \^ 2 \^ Black \^_000_001.png</span><span class="sxs-lookup"><span data-stu-id="fe791-127">For example: 93039 \^ \^ 2 \^ Black \^_000_001.png</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="fe791-128">Przekaż obraz</span><span class="sxs-lookup"><span data-stu-id="fe791-128">Upload an image</span></span>

<span data-ttu-id="fe791-129">Aby przekazać obraz w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe791-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="fe791-130">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="fe791-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="fe791-131">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="fe791-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="fe791-132">W oknie Eksploratora plików przejdź do jednego lub więcej obrazów do przekazania i wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe791-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="fe791-133">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="fe791-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="fe791-134">Wprowadź opcjonalny opis i słowa kluczowe, a w razie potrzeby wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="fe791-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="fe791-135">Jeśli chcesz opublikować obrazy po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="fe791-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="fe791-136">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe791-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="fe791-137">Przekaż folder obrazów</span><span class="sxs-lookup"><span data-stu-id="fe791-137">Upload a folder of images</span></span>

<span data-ttu-id="fe791-138">Aby przekazać wiele obrazów w folderze w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe791-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="fe791-139">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="fe791-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="fe791-140">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż folder**.</span><span class="sxs-lookup"><span data-stu-id="fe791-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="fe791-141">W oknie Eksploratora plików przejdź i wybierz folder do przekazania, po czym wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe791-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="fe791-142">W oknie dialogowym **przekazywanie elementów multimedialnych** wprowadź opcjonalne słowa kluczowe i w razie potrzeby wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="fe791-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="fe791-143">Jeśli chcesz opublikować obrazy w folderze po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="fe791-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="fe791-144">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe791-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe791-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fe791-145">Additional resources</span></span>

[<span data-ttu-id="fe791-146">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="fe791-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="fe791-147">Przekazanie wideo</span><span class="sxs-lookup"><span data-stu-id="fe791-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="fe791-148">Przekaż pliki</span><span class="sxs-lookup"><span data-stu-id="fe791-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="fe791-149">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="fe791-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="fe791-150">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="fe791-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="fe791-151">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="fe791-151">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
