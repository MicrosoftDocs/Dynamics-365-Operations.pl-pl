---
title: Tworzenie niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx/5xx
description: W tym temacie opisano sposób tworzenia niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx i 5xx przy użyciu narzędzi autorskich Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d21ce20b2c7ac8c656a718749dabd76f33893da8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991472"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="6d673-103">Tworzenie niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="6d673-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6d673-104">W tym temacie opisano sposób tworzenia niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx i 5xx przy użyciu narzędzi autorskich Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6d673-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6d673-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6d673-105">Overview</span></span>

<span data-ttu-id="6d673-106">Jeśli żądanie nie powiodło się, serwer wystawia odpowiedzi na błędy kodów stanu HTTP.</span><span class="sxs-lookup"><span data-stu-id="6d673-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="6d673-107">Kod stanu 404 jest przechwytywany i zwracany, jeśli nie odnaleziono strony, a kod stanu 500 jest przechwytywany i zwracany w przypadku wystąpienia błędu serwera.</span><span class="sxs-lookup"><span data-stu-id="6d673-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="6d673-108">W Dynamics 365 Commerce Użytkownicy aplikacji mogą budować niestandardowe strony odpowiedzi na kod błędu, które są pokazywane użytkownikom w odpowiedzi na te błędy.</span><span class="sxs-lookup"><span data-stu-id="6d673-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="6d673-109">Utwórz stronę odpowiedzi na błędy kodu stanu</span><span class="sxs-lookup"><span data-stu-id="6d673-109">Build a status code error response page</span></span>

<span data-ttu-id="6d673-110">Aby rozpocząć tworzenie strony odpowiedzi na błędy kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6d673-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6d673-111">W preferowanej przeglądarce sieci Web zaloguj się do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6d673-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="6d673-112">Wybierz oddział, dla którego chcesz utworzyć stronę odpowiedzi na błędy kodu stanu 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="6d673-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="6d673-113">Zbuduj szablon</span><span class="sxs-lookup"><span data-stu-id="6d673-113">Build the template</span></span>

<span data-ttu-id="6d673-114">Aby zbudować szablon strony odpowiedzi na błąd kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6d673-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6d673-115">Przejdź do okna **Szablony**.</span><span class="sxs-lookup"><span data-stu-id="6d673-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="6d673-116">Wybierz pozycję **Nowy**, aby utworzyć nowy szablon strony.</span><span class="sxs-lookup"><span data-stu-id="6d673-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="6d673-117">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź nazwę nowego szablonu, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d673-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="6d673-118">Utwórz szablon na podstawie struktury, która ma być stroną odpowiedzi na błędy kodu stanu.</span><span class="sxs-lookup"><span data-stu-id="6d673-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="6d673-119">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="6d673-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="6d673-120">Utwórz stronę odpowiedzi na błędy kodu stanu</span><span class="sxs-lookup"><span data-stu-id="6d673-120">Build the status code error response page</span></span>

<span data-ttu-id="6d673-121">Aby utworzyć strony odpowiedzi na błędy kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6d673-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6d673-122">Przejdź do **Strony**.</span><span class="sxs-lookup"><span data-stu-id="6d673-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="6d673-123">Wybierz **Nowy**, aby utworzyć stronę.</span><span class="sxs-lookup"><span data-stu-id="6d673-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="6d673-124">W oknie dialogowym **Wybierz szablon** wybierz szablon, a następnie w obszarze **Nazwa strony** wprowadź nazwę strony odpowiedzi na błędy kodu stanu.</span><span class="sxs-lookup"><span data-stu-id="6d673-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="6d673-125">Pole **Adres URL strony** należy pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="6d673-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="6d673-126">Zbuduj stronę.</span><span class="sxs-lookup"><span data-stu-id="6d673-126">Build the page.</span></span>
1. <span data-ttu-id="6d673-127">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="6d673-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="6d673-128">Istnieje możliwość utworzenia oddzielnej strony odpowiedzi o błędy kodów stanu dla błędów kodu stanu 4xx i 5xx.</span><span class="sxs-lookup"><span data-stu-id="6d673-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="6d673-129">Alternatywnie można skorzystać z tej samej strony odpowiedzi o błędzie o tym samym ogólnym kodzie stanu dla obu kategorii błędów.</span><span class="sxs-lookup"><span data-stu-id="6d673-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="6d673-130">Ustawianie przekierowywania dla strony odpowiedzi na błędy kodu stanu</span><span class="sxs-lookup"><span data-stu-id="6d673-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="6d673-131">Aby skonfigurować przekierowanie dla strony odpowiedzi na błąd kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6d673-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6d673-132">Przejdź do **Adresy URL \> Nowy \> Nowy alias**, a następnie wybierz stronę odpowiedzi na błędy kodu stanu, która została utworzona wcześniej.</span><span class="sxs-lookup"><span data-stu-id="6d673-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="6d673-133">W polu **Alias** wprowadź wartość **domyślna-4xx** lub **domyślne-5xx**, zależnie od strony odpowiedzi na błędy kodu stanu, na której konfigurujesz przekierowanie.</span><span class="sxs-lookup"><span data-stu-id="6d673-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="6d673-134">Te aliasy muszą zostać opublikowane.</span><span class="sxs-lookup"><span data-stu-id="6d673-134">These aliases must be published.</span></span> <span data-ttu-id="6d673-135">W przeciwnym razie przekierowanie nie będzie działać.</span><span class="sxs-lookup"><span data-stu-id="6d673-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="6d673-136">Wybierz przycisk **OK**, aby potwierdzić połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d673-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="6d673-137">Jeśli w obu kategoriach błędów jest używana jedna strona odpowiedzi o błędzie kodu stanu, powtórz tę procedurę, aby połączyć alias z inną kategorią błędu na tej samej stronie.</span><span class="sxs-lookup"><span data-stu-id="6d673-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d673-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6d673-138">Additional resources</span></span>

[<span data-ttu-id="6d673-139">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="6d673-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="6d673-140">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="6d673-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="6d673-141">Tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="6d673-141">Create a page URL</span></span>](create-page-url.md)
