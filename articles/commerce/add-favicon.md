---
title: Dodawanie ikony favicon
description: W tym temacie opisano sposób dodawania ikony favicon do witryny.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 18e12cbe46650fcf024a56b6de9a8cb2903d2bf8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914588"
---
# <a name="add-a-favicon"></a><span data-ttu-id="6f180-103">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="6f180-103">Add a favicon</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6f180-104">W tym temacie opisano sposób dodawania ikony favicon do witryny.</span><span class="sxs-lookup"><span data-stu-id="6f180-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="6f180-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6f180-105">Overview</span></span>

<span data-ttu-id="6f180-106">Favicon jest małym plikiem graficznym wyświetlanym na karcie przeglądarki sieci Web, na pasku adresu, w historii przeglądania oraz w zakładkach lub ulubionych i w innych miejscach.</span><span class="sxs-lookup"><span data-stu-id="6f180-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="6f180-107">Zaleca się dodanie favicon do witryny, ponieważ reprezentuje ona i wzmacnia daną markę oraz pomaga odróżnić witrynę od innych odwiedzanych przez odbiorców witryn sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6f180-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="6f180-108">Chociaż do witryny można dodać wiele favicons różnych rozmiarów i typów plików, w tym temacie przedstawiono sposób dodawania jednego favicon.</span><span class="sxs-lookup"><span data-stu-id="6f180-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="6f180-109">Jednak ten sam proces i lokalizacja są używane do dodawania kolejnych favicons.</span><span class="sxs-lookup"><span data-stu-id="6f180-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="6f180-110">Przekaż favicon do kolekcji składników majątku w witrynie</span><span class="sxs-lookup"><span data-stu-id="6f180-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="6f180-111">Aby przekazać favicon do kolekcji składników majątku w witrynie wykonaj procedurę opisaną w następujących krokach:</span><span class="sxs-lookup"><span data-stu-id="6f180-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="6f180-112">Przejdź do **Składniki majątku \> Przekaż \> Przekaż składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="6f180-112">Go to **Assets \> Upload \> Upload assets**.</span></span>
1. <span data-ttu-id="6f180-113">Znajdź i wybierz favicon w lokalnym systemie plików.</span><span class="sxs-lookup"><span data-stu-id="6f180-113">Find and select the favicon on your local file system.</span></span>
1. <span data-ttu-id="6f180-114">Wprowadź tytuł, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f180-114">Enter a title, and then select **OK**.</span></span> 
1. <span data-ttu-id="6f180-115">W okienku właściwości po prawej stronie Skopiuj publiczny adres URL favicon.</span><span class="sxs-lookup"><span data-stu-id="6f180-115">In the property pane on the right, copy the public URL of the favicon.</span></span>

> [!NOTE]
> <span data-ttu-id="6f180-116">Jeśli nie zaznaczysz opcji **Publikuj zasoby po przekazaniu**, musisz wrócić do strony **Składniki majątku** i ręcznie opublikować favicon później.</span><span class="sxs-lookup"><span data-stu-id="6f180-116">If you don't select the **Publish assets after upload** option, you must return to **Assets** page and manually publish the favicon later.</span></span>

## <a name="create-the-html-for-the-favicon"></a><span data-ttu-id="6f180-117">Utwórz kod HTML dla favicon</span><span class="sxs-lookup"><span data-stu-id="6f180-117">Create the HTML for the favicon</span></span>

<span data-ttu-id="6f180-118">Aby utworzyć kod HTML dla favicon, należy skorzystać z poniższego urywka kodu HTML.</span><span class="sxs-lookup"><span data-stu-id="6f180-118">To create the HTML for the favicon, use the following HTML snippet.</span></span> <span data-ttu-id="6f180-119">W przypadku atrybutu **href** zamień wartość **„Publiczny\_URL\_dla\_twojej\_favicon”** na publiczny adres URL, który został wcześniej skopiowany.</span><span class="sxs-lookup"><span data-stu-id="6f180-119">For the **href** attribute, replace **"Public\_URL\_for\_your\_favicon"** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a><span data-ttu-id="6f180-120">Dodaj kod HTML favicon do elementu stron \<head\>.</span><span class="sxs-lookup"><span data-stu-id="6f180-120">Add the HTML for the favicon to the \<head\> element of your pages</span></span>

<span data-ttu-id="6f180-121">Aby dodać favicon do witryny, należy użyć tej samej procedury, która służy do dodawania dowolnego typu kodu HTML lub skryptu do elementu **\<head\>** stron witryny.</span><span class="sxs-lookup"><span data-stu-id="6f180-121">To add a favicon to your site, use the same procedure that is used to add any type of HTML or script to the **\<head\>** element of your site pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f180-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6f180-122">Additional resources</span></span>

[<span data-ttu-id="6f180-123">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="6f180-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="6f180-124">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="6f180-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="6f180-125">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="6f180-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="6f180-126">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="6f180-126">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="6f180-127">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="6f180-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="6f180-128">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="6f180-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="6f180-129">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="6f180-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

