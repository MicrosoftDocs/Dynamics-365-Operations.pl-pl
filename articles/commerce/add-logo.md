---
title: Dodawanie logo
description: W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: f15680deb0eab763ba68f2897139c915d1f8a6a3
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817337"
---
# <a name="add-a-logo"></a><span data-ttu-id="b5860-103">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="b5860-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b5860-104">W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b5860-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b5860-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b5860-105">Overview</span></span>

<span data-ttu-id="b5860-106">Podczas kompilowania witryny jedną z pierwszych rzeczy, którą prawdopodobnie będzie zrobić, będzie dodanie logo firmy lub marki do nagłówka witryny.</span><span class="sxs-lookup"><span data-stu-id="b5860-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="b5860-107">Biblioteka modułów online Dynamics 365 Commerce oferuje moduł, który ułatwia to zadanie.</span><span class="sxs-lookup"><span data-stu-id="b5860-107">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="b5860-108">Możesz dodać logo bezpośrednio do szablonu, układu lub strony.</span><span class="sxs-lookup"><span data-stu-id="b5860-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="b5860-109">W ten sposób można łatwo zmienić logo, które pojawia się na określonych stronach lub grupach stron.</span><span class="sxs-lookup"><span data-stu-id="b5860-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="b5860-110">W tym temacie omówiono jednak najczęstszy scenariusz dodawania logo do fragmentu nagłówka, który można ponownie wykorzystać na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="b5860-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5860-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b5860-111">Prerequisites</span></span>

<span data-ttu-id="b5860-112">Aby można było dodać logo do wszystkich stron witryny, należy wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="b5860-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="b5860-113">Przekaż swoją logo do biblioteki multimediów.</span><span class="sxs-lookup"><span data-stu-id="b5860-113">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="b5860-114">Utwórz fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="b5860-114">Create a header fragment.</span></span> <span data-ttu-id="b5860-115">Aby uzyskać więcej informacji na temat tworzenia i używania fragmentów, zobacz [Praca z fragmentami](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="b5860-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="b5860-116">Dołącz fragment nagłówka w szablonie, którego strony witryny używają do ustawiania opcji układu i modułu.</span><span class="sxs-lookup"><span data-stu-id="b5860-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="b5860-117">Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z szablonami](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b5860-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="b5860-118">Dodawanie logo do fragmentu nagłówka</span><span class="sxs-lookup"><span data-stu-id="b5860-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="b5860-119">Aby dodać logo do fragmentu nagłówka witryny, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b5860-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="b5860-120">W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="b5860-120">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="b5860-121">Wybierz utworzony fragment nagłówka, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b5860-121">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="b5860-122">Rozwiń moduł nagłówka.</span><span class="sxs-lookup"><span data-stu-id="b5860-122">Expand the header module.</span></span>
1. <span data-ttu-id="b5860-123">W okienku właściwości modułu nagłówka wprowadź obraz i łącze do logo.</span><span class="sxs-lookup"><span data-stu-id="b5860-123">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="b5860-124">Zapisz fragment nagłówka, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="b5860-124">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="b5860-125">Po opublikowaniu zaktualizowanego fragmentu nagłówka wszystkie strony witryny, które używają szablonu zawierającego fragment nagłówka, będą zawierać Twoje logo.</span><span class="sxs-lookup"><span data-stu-id="b5860-125">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5860-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b5860-126">Additional resources</span></span>

[<span data-ttu-id="b5860-127">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="b5860-127">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="b5860-128">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="b5860-128">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="b5860-129">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="b5860-129">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="b5860-130">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="b5860-130">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="b5860-131">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="b5860-131">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="b5860-132">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="b5860-132">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="b5860-133">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="b5860-133">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

