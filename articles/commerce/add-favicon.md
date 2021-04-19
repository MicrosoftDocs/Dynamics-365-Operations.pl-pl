---
title: Dodawanie ikony favicon
description: W tym temacie opisano sposób dodawania ikony favicon do witryny.
author: bicyclingfool
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9268bc74a4131256f5a2e88df833104db271b56a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797726"
---
# <a name="add-a-favicon"></a><span data-ttu-id="37ba8-103">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="37ba8-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="37ba8-104">W tym temacie opisano sposób dodawania ikony favicon do witryny.</span><span class="sxs-lookup"><span data-stu-id="37ba8-104">This topic explains how to add a favicon to your site.</span></span>

<span data-ttu-id="37ba8-105">Favicon jest małym plikiem graficznym wyświetlanym na karcie przeglądarki sieci Web, na pasku adresu, w historii przeglądania oraz w zakładkach lub ulubionych i w innych miejscach.</span><span class="sxs-lookup"><span data-stu-id="37ba8-105">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="37ba8-106">Zaleca się dodanie favicon do witryny, ponieważ reprezentuje ona i wzmacnia daną markę oraz pomaga odróżnić witrynę od innych odwiedzanych przez odbiorców witryn sieci Web.</span><span class="sxs-lookup"><span data-stu-id="37ba8-106">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="37ba8-107">Chociaż do witryny można dodać wiele favicons różnych rozmiarów i typów plików, w tym temacie przedstawiono sposób dodawania jednego favicon.</span><span class="sxs-lookup"><span data-stu-id="37ba8-107">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="37ba8-108">Jednak ten sam proces i lokalizacja są używane do dodawania kolejnych favicons.</span><span class="sxs-lookup"><span data-stu-id="37ba8-108">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="37ba8-109">Przekaż favicon do kolekcji składników majątku w witrynie</span><span class="sxs-lookup"><span data-stu-id="37ba8-109">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="37ba8-110">Aby przekazać favicon do kolekcji składników majątku w witrynie wykonaj procedurę opisaną w następujących krokach:</span><span class="sxs-lookup"><span data-stu-id="37ba8-110">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="37ba8-111">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-111">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="37ba8-112">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-112">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="37ba8-113">W oknie Eksploratora plików przejdź do pliku obrazu favicon, który chcesz przekazać, zaznacz go, a następnie wybierz pozycję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-113">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="37ba8-114">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="37ba8-114">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="37ba8-115">Jeśli chcesz opublikować obraz natychmiast po przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-115">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37ba8-116">Jeśli nie zaznaczysz pola wyboru **Publikuj elementy multimedialne po przekazaniu**, musisz wrócić do strony **Elementy multimedialne** i ręcznie opublikować favicon później.</span><span class="sxs-lookup"><span data-stu-id="37ba8-116">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="37ba8-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-117">Select **OK**.</span></span>
1. <span data-ttu-id="37ba8-118">W okienku właściwości po prawej stronie Skopiuj publiczny adres URL favicon.</span><span class="sxs-lookup"><span data-stu-id="37ba8-118">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="37ba8-119">Ten adres URL będzie używany później.</span><span class="sxs-lookup"><span data-stu-id="37ba8-119">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="37ba8-120">Tworzenie kodu HTML dla pliku favicon</span><span class="sxs-lookup"><span data-stu-id="37ba8-120">Create the HTML for your favicon</span></span>

<span data-ttu-id="37ba8-121">Aby utworzyć kod HTML dla pliku favicon, należy skorzystać z poniższego ciągu kodu HTML.</span><span class="sxs-lookup"><span data-stu-id="37ba8-121">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="37ba8-122">W przypadku atrybutu **href** zamień wartość **Publiczny\_URL\_dla\_ikony\_favicon”** na skopiowany wcześniej, publiczny adres URL.</span><span class="sxs-lookup"><span data-stu-id="37ba8-122">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="37ba8-123">Tworzenie fragmentu zawierającego metatag dla ikony favicon</span><span class="sxs-lookup"><span data-stu-id="37ba8-123">Create a fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="37ba8-124">Aby utworzyć fragment zawierający metatag dla ikony favicon, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="37ba8-124">To create a fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="37ba8-125">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-125">Go to **Fragments**, and select **New**.</span></span>
1. <span data-ttu-id="37ba8-126">W oknie dialogowym **Nowy fragment** wybierz pozycję **Tagi meta** jako moduł, na którym oparty jest fragment strony.</span><span class="sxs-lookup"><span data-stu-id="37ba8-126">In the **New fragment** dialog box, select **Metatags** as the module that the fragment is based on.</span></span>
1. <span data-ttu-id="37ba8-127">Wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-127">Enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="37ba8-128">W drzewie hierarchii fragmentów wybierz element podrzędny **Domyślne tagi meta**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-128">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="37ba8-129">W prawym okienku, w obszarze **Tagi meta**, wybierz pozycję **Dodaj**, a następnie wprowadź ciąg HTML utworzony wcześniej dla ikony favicon.</span><span class="sxs-lookup"><span data-stu-id="37ba8-129">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="37ba8-130">Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować fragment.</span><span class="sxs-lookup"><span data-stu-id="37ba8-130">Select **Finish editing**, and then select **Publish** to publish the fragment.</span></span>

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="37ba8-131">Dodawanie fragmentu metatagów do sekcji nagłówka kodu HTML stron</span><span class="sxs-lookup"><span data-stu-id="37ba8-131">Add the metatag fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="37ba8-132">Aby dodać fragment metatagów do sekcji **nagłówka** kodu HTML stron, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="37ba8-132">To add the metatag fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="37ba8-133">Przejdź do obszaru **Szablony**, otwórz szablon stron, do których chcesz dodać ikonę favicon, a następnie wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-133">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="37ba8-134">W drzewie hierarchii szablonów wybierz przycisk wielokropka (**...**) znajdujący się po prawej stronie kontenera **nagłówek HTML**, a następnie wybierz pozycję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-134">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add fragment**.</span></span>
1. <span data-ttu-id="37ba8-135">W oknie dialogowym **Wybieranie fragmentu** wybierz utworzony wcześniej fragment metatagów, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="37ba8-135">In the **Select fragment** dialog box, select the metatag fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="37ba8-136">Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować szablon.</span><span class="sxs-lookup"><span data-stu-id="37ba8-136">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="37ba8-137">Jeśli witryna używa więcej niż jednego szablonu, musisz dodać fragment metatagów do wszystkich tych szablonów.</span><span class="sxs-lookup"><span data-stu-id="37ba8-137">If your site uses more than one template, you must add the metatags fragment to all of them.</span></span>

<span data-ttu-id="37ba8-138">Podczas wyświetlania podglądu stron opartych na szablonie, do którego dodano fragment metatagów, ikona favicon powinna być teraz widoczna na karcie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="37ba8-138">When you preview pages that are based on the template that you added the metatags fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="37ba8-139">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="37ba8-139">Additional resources</span></span>

[<span data-ttu-id="37ba8-140">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="37ba8-140">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="37ba8-141">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="37ba8-141">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="37ba8-142">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="37ba8-142">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="37ba8-143">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="37ba8-143">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="37ba8-144">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="37ba8-144">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="37ba8-145">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="37ba8-145">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="37ba8-146">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="37ba8-146">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
