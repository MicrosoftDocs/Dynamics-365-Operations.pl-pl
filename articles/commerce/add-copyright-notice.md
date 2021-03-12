---
title: Dodawanie powiadomienia o prawach autorskich
description: W tym temacie opisano, jak dodać informację o prawach autorskich do swojej witryny e-Commerce.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 54d9ccbb56131333159cdf8858dfca23b75b61fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980463"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="ce3eb-103">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="ce3eb-103">Add a copyright notice</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ce3eb-104">W tym temacie opisano, jak dodać informację o prawach autorskich do swojej witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ce3eb-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ce3eb-105">Prerequisites</span></span>

<span data-ttu-id="ce3eb-106">Aby można było dodać do witryny powiadomienie o prawach autorskich, należy dysponować następującymi pozycjami:</span><span class="sxs-lookup"><span data-stu-id="ce3eb-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="ce3eb-107">Szablon zawierający wspólny fragment stopki.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="ce3eb-108">Strona korzystająca z tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="ce3eb-109">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="ce3eb-109">Add a copyright notice</span></span>

<span data-ttu-id="ce3eb-110">Aby dodać powiadomienie o prawach autorskich na końcu każdej strony korzystającej z określonego szablonu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="ce3eb-111">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-111">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="ce3eb-112">W oknie dialogowym **Nowy fragment** wybierz moduł **Stopki** i nazwij fragment.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-112">In the **New fragment** dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="ce3eb-113">Na przykład wprowadź **stopka — prawa autorskie**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="ce3eb-114">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-114">Select **OK**.</span></span>
1. <span data-ttu-id="ce3eb-115">W okienku nawigacji wybierz przycisk wielokropka (**...**) obok **Stopki**, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ce3eb-116">W oknie dialogowym wybierz **Kategoria stopki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="ce3eb-117">W okienku nawigacji wybierz przycisk wielokropka (...) obok **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ce3eb-118">W oknie dialogowym wybierz **Blok zaawansowanej zawartości** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-118">In the dialog box, select **Text block**, and then select **OK**.</span></span>
1. <span data-ttu-id="ce3eb-119">W okienku nawigacji wybierz opcję **Blok aawansowanej zawarości**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-119">In the navigation pane, select **Text block**.</span></span>
1. <span data-ttu-id="ce3eb-120">W okienku właściwości po prawej stronie w polu **Akapit** dodaj wiadomość dotyczącą praw autorskich.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="ce3eb-121">Na przykład wprowadź **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="ce3eb-122">Wybierz opcję **Zapisz**, wybierz opcję **Zakończ edycję**, a następnie wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-122">Select **Save**, select **Finish editing**, and then select **Publish**.</span></span>
1. <span data-ttu-id="ce3eb-123">Przejdź do **Szablony**, wybierz szablon, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-123">Go to **Templates**, select the template, and then select **Edit**.</span></span>
1. <span data-ttu-id="ce3eb-124">W obszarze **Konspekt strony** rozwiń węzeł **Treść**, a następnie rozwiń węzeł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="ce3eb-125">Wybierz przycisk wielokropka obok **Gniazdo nagłówka**, a następnie wybierz opcję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="ce3eb-126">Wybierz utworzony fragment, który utworzono wcześniej, a następnie wybierz opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="ce3eb-127">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-127">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="ce3eb-128">Stopka zawierająca informację o prawach autorskich jest automatycznie wyświetlana u dołu wszystkich stron, w których jest używany wybrany szablon.</span><span class="sxs-lookup"><span data-stu-id="ce3eb-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce3eb-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ce3eb-129">Additional resources</span></span>

[<span data-ttu-id="ce3eb-130">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="ce3eb-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="ce3eb-131">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="ce3eb-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="ce3eb-132">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="ce3eb-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="ce3eb-133">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="ce3eb-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="ce3eb-134">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="ce3eb-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="ce3eb-135">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="ce3eb-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="ce3eb-136">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="ce3eb-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

