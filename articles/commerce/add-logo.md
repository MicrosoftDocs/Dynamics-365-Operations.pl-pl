---
title: Dodawanie logo
description: W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797606"
---
# <a name="add-a-logo"></a><span data-ttu-id="2200e-103">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="2200e-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2200e-104">W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2200e-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2200e-105">Podczas kompilowania witryny jedną z pierwszych rzeczy, którą prawdopodobnie będzie zrobić, będzie dodanie logo firmy lub marki do nagłówka witryny.</span><span class="sxs-lookup"><span data-stu-id="2200e-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="2200e-106">Biblioteka modułów online Dynamics 365 Commerce oferuje moduł, który ułatwia to zadanie.</span><span class="sxs-lookup"><span data-stu-id="2200e-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="2200e-107">Możesz dodać logo bezpośrednio do szablonu, układu lub strony.</span><span class="sxs-lookup"><span data-stu-id="2200e-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="2200e-108">W ten sposób można łatwo zmienić logo, które pojawia się na określonych stronach lub grupach stron.</span><span class="sxs-lookup"><span data-stu-id="2200e-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="2200e-109">W tym temacie omówiono jednak najczęstszy scenariusz dodawania logo do fragmentu nagłówka, który można ponownie wykorzystać na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="2200e-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2200e-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2200e-110">Prerequisites</span></span>

<span data-ttu-id="2200e-111">Aby można było dodać logo do wszystkich stron witryny, należy wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="2200e-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="2200e-112">Przekaż swoją logo do biblioteki multimediów.</span><span class="sxs-lookup"><span data-stu-id="2200e-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="2200e-113">Utwórz fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="2200e-113">Create a header fragment.</span></span> <span data-ttu-id="2200e-114">Aby uzyskać więcej informacji na temat tworzenia i używania fragmentów, zobacz [Praca z fragmentami](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="2200e-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="2200e-115">Dołącz fragment nagłówka w szablonie, którego strony witryny używają do ustawiania opcji układu i modułu.</span><span class="sxs-lookup"><span data-stu-id="2200e-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="2200e-116">Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z szablonami](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="2200e-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="2200e-117">Dodawanie logo do fragmentu nagłówka</span><span class="sxs-lookup"><span data-stu-id="2200e-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="2200e-118">Aby dodać logo do fragmentu nagłówka witryny, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2200e-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="2200e-119">W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="2200e-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="2200e-120">Wybierz utworzony fragment nagłówka, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2200e-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="2200e-121">Rozwiń moduł nagłówka.</span><span class="sxs-lookup"><span data-stu-id="2200e-121">Expand the header module.</span></span>
1. <span data-ttu-id="2200e-122">W okienku właściwości modułu nagłówka wprowadź obraz i łącze do logo.</span><span class="sxs-lookup"><span data-stu-id="2200e-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="2200e-123">Zapisz fragment nagłówka, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="2200e-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="2200e-124">Po opublikowaniu zaktualizowanego fragmentu nagłówka wszystkie strony witryny, które używają szablonu zawierającego fragment nagłówka, będą zawierać Twoje logo.</span><span class="sxs-lookup"><span data-stu-id="2200e-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2200e-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2200e-125">Additional resources</span></span>

[<span data-ttu-id="2200e-126">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="2200e-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="2200e-127">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="2200e-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="2200e-128">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="2200e-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="2200e-129">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="2200e-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="2200e-130">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="2200e-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="2200e-131">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="2200e-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="2200e-132">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="2200e-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
