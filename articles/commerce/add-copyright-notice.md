---
title: Dodawanie powiadomienia o prawach autorskich
description: W tym temacie opisano, jak dodać informację o prawach autorskich do swojej witryny e-Commerce.
author: psimolin
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 58c2949057ef777f706d12cee2dd3341d1a3b7e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914585"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="fd7b1-103">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="fd7b1-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="fd7b1-104">W tym temacie opisano, jak dodać informację o prawach autorskich do swojej witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd7b1-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="fd7b1-105">Prerequisites</span></span>

<span data-ttu-id="fd7b1-106">Aby można było dodać do witryny powiadomienie o prawach autorskich, należy dysponować następującymi pozycjami:</span><span class="sxs-lookup"><span data-stu-id="fd7b1-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="fd7b1-107">Szablon zawierający wspólny fragment stopki.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="fd7b1-108">Strona korzystająca z tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="fd7b1-109">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="fd7b1-109">Add a copyright notice</span></span>

<span data-ttu-id="fd7b1-110">Aby dodać powiadomienie o prawach autorskich na końcu każdej strony korzystającej z określonego szablonu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="fd7b1-111">Przejdź do **Fragmentów**, a następnie wybierz opcję **Nowy fragment strony**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="fd7b1-112">W oknie dialogowym wybierz moduł **Stopki** i nazwij ten fragment.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="fd7b1-113">Na przykład wprowadź **stopka — prawa autorskie**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="fd7b1-114">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-114">Select **OK**.</span></span>
1. <span data-ttu-id="fd7b1-115">W okienku nawigacji wybierz przycisk wielokropka (**...**) obok **Stopki**, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="fd7b1-116">W oknie dialogowym wybierz **Kategoria stopki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="fd7b1-117">W okienku nawigacji wybierz przycisk wielokropka (...) obok **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="fd7b1-118">W oknie dialogowym wybierz **Element bloku zawartości sformatowanej** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="fd7b1-119">W okienku nawigacji wybierz opcję **Element bloku zawartości sformatowanej**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="fd7b1-120">W okienku właściwości po prawej stronie w polu **Akapit** dodaj wiadomość dotyczącą praw autorskich.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="fd7b1-121">Na przykład wprowadź **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="fd7b1-122">Wybierz opcję **Zapisz**, wybierz opcję **Zaewidencjonuj**, a następnie wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="fd7b1-123">Przejdź do **Szablony**, wybierz szablon, a następnie wybierz opcję **Wyewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="fd7b1-124">W obszarze **Konspekt strony** rozwiń węzeł **Treść**, a następnie rozwiń węzeł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="fd7b1-125">Wybierz przycisk wielokropka obok **Gniazdo nagłówka**, a następnie wybierz opcję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="fd7b1-126">Wybierz utworzony fragment, który utworzono wcześniej, a następnie wybierz opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="fd7b1-127">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="fd7b1-128">Stopka zawierająca informację o prawach autorskich jest automatycznie wyświetlana u dołu wszystkich stron, w których jest używany wybrany szablon.</span><span class="sxs-lookup"><span data-stu-id="fd7b1-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd7b1-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fd7b1-129">Additional resources</span></span>

[<span data-ttu-id="fd7b1-130">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="fd7b1-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="fd7b1-131">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="fd7b1-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="fd7b1-132">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="fd7b1-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="fd7b1-133">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="fd7b1-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="fd7b1-134">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="fd7b1-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="fd7b1-135">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="fd7b1-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="fd7b1-136">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="fd7b1-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

