---
title: Dodawanie logo
description: W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914631"
---
# <a name="add-a-logo"></a><span data-ttu-id="78ac6-103">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="78ac6-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="78ac6-104">W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="78ac6-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="78ac6-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="78ac6-105">Overview</span></span>

<span data-ttu-id="78ac6-106">Podczas kompilowania witryny jedną z pierwszych rzeczy, którą prawdopodobnie będzie zrobić, będzie dodanie logo firmy lub marki do nagłówka witryny.</span><span class="sxs-lookup"><span data-stu-id="78ac6-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="78ac6-107">Zestaw startowy online Dynamics 365 Commerce oferuje moduł, który ułatwia to zadanie.</span><span class="sxs-lookup"><span data-stu-id="78ac6-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="78ac6-108">Możesz dodać logo bezpośrednio do szablonu, układu lub strony.</span><span class="sxs-lookup"><span data-stu-id="78ac6-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="78ac6-109">W ten sposób można łatwo zmienić logo, które pojawia się na określonych stronach lub grupach stron.</span><span class="sxs-lookup"><span data-stu-id="78ac6-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="78ac6-110">W tym temacie omówiono jednak najczęstszy scenariusz dodawania logo do fragmentu nagłówka, który można ponownie wykorzystać na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="78ac6-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78ac6-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="78ac6-111">Prerequisites</span></span>

<span data-ttu-id="78ac6-112">Aby można było dodać logo do wszystkich stron witryny, należy wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="78ac6-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="78ac6-113">Przekaż logo do menedżera cyfrowych elementów zawartości, do którego możesz uzyskać dostęp ze strony **Elementy zawartości**.</span><span class="sxs-lookup"><span data-stu-id="78ac6-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="78ac6-114">Utwórz fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="78ac6-114">Create a header fragment.</span></span> <span data-ttu-id="78ac6-115">Aby uzyskać więcej informacji na temat tworzenia i używania fragmentów, zobacz [Praca z fragmentami](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="78ac6-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="78ac6-116">Dołącz fragment nagłówka w szablonie, którego strony witryny używają do ustawiania opcji układu i modułu.</span><span class="sxs-lookup"><span data-stu-id="78ac6-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="78ac6-117">Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z szablonami](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="78ac6-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="78ac6-118">Dodawanie logo do fragmentu nagłówka</span><span class="sxs-lookup"><span data-stu-id="78ac6-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="78ac6-119">Aby dodać logo do fragmentu nagłówka witryny, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="78ac6-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="78ac6-120">W okienku nawigacji po lewej stronie wybierz pozycję **Fragmenty**, a następnie wybierz utworzony fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="78ac6-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="78ac6-121">Wybierz **Wyewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="78ac6-121">Select **Check out**.</span></span>
3. <span data-ttu-id="78ac6-122">Rozwiń gniazdo **Nagłówek** i gniazdo **Logo**.</span><span class="sxs-lookup"><span data-stu-id="78ac6-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="78ac6-123">Wybierz przycisk wielokropka (**...**) dla gniazda **Logo**, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="78ac6-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="78ac6-124">Wybierz moduł logo.</span><span class="sxs-lookup"><span data-stu-id="78ac6-124">Select the logo module.</span></span>
6. <span data-ttu-id="78ac6-125">W okienku właściwości po prawej stronie skonfiguruj moduł logo, aby zostało ono wyświetlone.</span><span class="sxs-lookup"><span data-stu-id="78ac6-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="78ac6-126">Zapisz fragment nagłówka, zaewidencjonuj go i opublikuj.</span><span class="sxs-lookup"><span data-stu-id="78ac6-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="78ac6-127">Po opublikowaniu zaktualizowanego fragmentu nagłówka wszystkie strony witryny, które używają szablonu zawierającego fragment nagłówka, będą zawierać Twoje logo.</span><span class="sxs-lookup"><span data-stu-id="78ac6-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78ac6-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="78ac6-128">Additional resources</span></span>

[<span data-ttu-id="78ac6-129">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="78ac6-129">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="78ac6-130">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="78ac6-130">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="78ac6-131">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="78ac6-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="78ac6-132">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="78ac6-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="78ac6-133">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="78ac6-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="78ac6-134">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="78ac6-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="78ac6-135">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="78ac6-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

