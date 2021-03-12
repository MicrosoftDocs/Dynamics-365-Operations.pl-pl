---
title: Dodawanie ikony favicon
description: W tym temacie opisano sposób dodawania ikony favicon do witryny.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f249348fac526fc7814045b1b1b71c898430c0f2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980438"
---
# <a name="add-a-favicon"></a><span data-ttu-id="16277-103">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="16277-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="16277-104">W tym temacie opisano sposób dodawania ikony favicon do witryny.</span><span class="sxs-lookup"><span data-stu-id="16277-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="16277-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="16277-105">Overview</span></span>

<span data-ttu-id="16277-106">Favicon jest małym plikiem graficznym wyświetlanym na karcie przeglądarki sieci Web, na pasku adresu, w historii przeglądania oraz w zakładkach lub ulubionych i w innych miejscach.</span><span class="sxs-lookup"><span data-stu-id="16277-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="16277-107">Zaleca się dodanie favicon do witryny, ponieważ reprezentuje ona i wzmacnia daną markę oraz pomaga odróżnić witrynę od innych odwiedzanych przez odbiorców witryn sieci Web.</span><span class="sxs-lookup"><span data-stu-id="16277-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="16277-108">Chociaż do witryny można dodać wiele favicons różnych rozmiarów i typów plików, w tym temacie przedstawiono sposób dodawania jednego favicon.</span><span class="sxs-lookup"><span data-stu-id="16277-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="16277-109">Jednak ten sam proces i lokalizacja są używane do dodawania kolejnych favicons.</span><span class="sxs-lookup"><span data-stu-id="16277-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="16277-110">Przekaż favicon do kolekcji składników majątku w witrynie</span><span class="sxs-lookup"><span data-stu-id="16277-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="16277-111">Aby przekazać favicon do kolekcji składników majątku w witrynie wykonaj procedurę opisaną w następujących krokach:</span><span class="sxs-lookup"><span data-stu-id="16277-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="16277-112">W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.</span><span class="sxs-lookup"><span data-stu-id="16277-112">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="16277-113">Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.</span><span class="sxs-lookup"><span data-stu-id="16277-113">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="16277-114">W oknie Eksploratora plików przejdź do pliku obrazu favicon, który chcesz przekazać, zaznacz go, a następnie wybierz pozycję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="16277-114">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="16277-115">W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="16277-115">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="16277-116">Jeśli chcesz opublikować obraz natychmiast po przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.</span><span class="sxs-lookup"><span data-stu-id="16277-116">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16277-117">Jeśli nie zaznaczysz pola wyboru **Publikuj elementy multimedialne po przekazaniu**, musisz wrócić do strony **Elementy multimedialne** i ręcznie opublikować favicon później.</span><span class="sxs-lookup"><span data-stu-id="16277-117">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="16277-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="16277-118">Select **OK**.</span></span>
1. <span data-ttu-id="16277-119">W okienku właściwości po prawej stronie Skopiuj publiczny adres URL favicon.</span><span class="sxs-lookup"><span data-stu-id="16277-119">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="16277-120">Ten adres URL będzie używany później.</span><span class="sxs-lookup"><span data-stu-id="16277-120">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="16277-121">Tworzenie kodu HTML dla pliku favicon</span><span class="sxs-lookup"><span data-stu-id="16277-121">Create the HTML for your favicon</span></span>

<span data-ttu-id="16277-122">Aby utworzyć kod HTML dla pliku favicon, należy skorzystać z poniższego ciągu kodu HTML.</span><span class="sxs-lookup"><span data-stu-id="16277-122">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="16277-123">W przypadku atrybutu **href** zamień wartość **Publiczny\_URL\_dla\_ikony\_favicon”** na skopiowany wcześniej, publiczny adres URL.</span><span class="sxs-lookup"><span data-stu-id="16277-123">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="16277-124">Tworzenie fragmentu zawierającego metatag dla ikony favicon</span><span class="sxs-lookup"><span data-stu-id="16277-124">Create a fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="16277-125">Aby utworzyć fragment zawierający metatag dla ikony favicon, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="16277-125">To create a fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="16277-126">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="16277-126">Go to **Fragments**, and select **New**.</span></span>
1. <span data-ttu-id="16277-127">W oknie dialogowym **Nowy fragment** wybierz pozycję **Tagi meta** jako moduł, na którym oparty jest fragment strony.</span><span class="sxs-lookup"><span data-stu-id="16277-127">In the **New fragment** dialog box, select **Metatags** as the module that the fragment is based on.</span></span>
1. <span data-ttu-id="16277-128">Wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="16277-128">Enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="16277-129">W drzewie hierarchii fragmentów wybierz element podrzędny **Domyślne tagi meta**.</span><span class="sxs-lookup"><span data-stu-id="16277-129">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="16277-130">W prawym okienku, w obszarze **Tagi meta**, wybierz pozycję **Dodaj**, a następnie wprowadź ciąg HTML utworzony wcześniej dla ikony favicon.</span><span class="sxs-lookup"><span data-stu-id="16277-130">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="16277-131">Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować fragment.</span><span class="sxs-lookup"><span data-stu-id="16277-131">Select **Finish editing**, and then select **Publish** to publish the fragment.</span></span>

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="16277-132">Dodawanie fragmentu metatagów do sekcji nagłówka kodu HTML stron</span><span class="sxs-lookup"><span data-stu-id="16277-132">Add the metatag fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="16277-133">Aby dodać fragment metatagów do sekcji **nagłówka** kodu HTML stron, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="16277-133">To add the metatag fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="16277-134">Przejdź do obszaru **Szablony**, otwórz szablon stron, do których chcesz dodać ikonę favicon, a następnie wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="16277-134">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="16277-135">W drzewie hierarchii szablonów wybierz przycisk wielokropka (**...**) znajdujący się po prawej stronie kontenera **nagłówek HTML**, a następnie wybierz pozycję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="16277-135">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add fragment**.</span></span>
1. <span data-ttu-id="16277-136">W oknie dialogowym **Wybieranie fragmentu** wybierz utworzony wcześniej fragment metatagów, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="16277-136">In the **Select fragment** dialog box, select the metatag fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="16277-137">Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować szablon.</span><span class="sxs-lookup"><span data-stu-id="16277-137">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="16277-138">Jeśli witryna używa więcej niż jednego szablonu, musisz dodać fragment metatagów do wszystkich tych szablonów.</span><span class="sxs-lookup"><span data-stu-id="16277-138">If your site uses more than one template, you must add the metatags fragment to all of them.</span></span>

<span data-ttu-id="16277-139">Podczas wyświetlania podglądu stron opartych na szablonie, do którego dodano fragment metatagów, ikona favicon powinna być teraz widoczna na karcie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="16277-139">When you preview pages that are based on the template that you added the metatags fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="16277-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="16277-140">Additional resources</span></span>

[<span data-ttu-id="16277-141">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="16277-141">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="16277-142">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="16277-142">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="16277-143">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="16277-143">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="16277-144">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="16277-144">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="16277-145">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="16277-145">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="16277-146">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="16277-146">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="16277-147">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="16277-147">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

