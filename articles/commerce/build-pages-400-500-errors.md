---
title: Tworzenie niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx/5xx
description: W tym temacie opisano sposób tworzenia niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx i 5xx przy użyciu narzędzi autorskich Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001149"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="d63c5-103">Tworzenie niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="d63c5-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d63c5-104">W tym temacie opisano sposób tworzenia niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx i 5xx przy użyciu narzędzi autorskich Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d63c5-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d63c5-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d63c5-105">Overview</span></span>

<span data-ttu-id="d63c5-106">Jeśli żądanie nie powiodło się, serwer wystawia odpowiedzi na błędy kodów stanu HTTP.</span><span class="sxs-lookup"><span data-stu-id="d63c5-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="d63c5-107">Kod stanu 404 jest przechwytywany i zwracany, jeśli nie odnaleziono strony, a kod stanu 500 jest przechwytywany i zwracany w przypadku wystąpienia błędu serwera.</span><span class="sxs-lookup"><span data-stu-id="d63c5-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="d63c5-108">W Dynamics 365 Commerce Użytkownicy aplikacji mogą budować niestandardowe strony odpowiedzi na kod błędu, które są pokazywane użytkownikom w odpowiedzi na te błędy.</span><span class="sxs-lookup"><span data-stu-id="d63c5-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="d63c5-109">Utwórz stronę odpowiedzi na błędy kodu stanu</span><span class="sxs-lookup"><span data-stu-id="d63c5-109">Build a status code error response page</span></span>

<span data-ttu-id="d63c5-110">Aby rozpocząć tworzenie strony odpowiedzi na błędy kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d63c5-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="d63c5-111">W preferowanej przeglądarce sieci Web zaloguj się do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d63c5-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="d63c5-112">Wybierz oddział, dla którego chcesz utworzyć stronę odpowiedzi na błędy kodu stanu 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="d63c5-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="d63c5-113">Zbuduj szablon</span><span class="sxs-lookup"><span data-stu-id="d63c5-113">Build the template</span></span>

<span data-ttu-id="d63c5-114">Aby zbudować szablon strony odpowiedzi na błąd kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d63c5-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="d63c5-115">Przejdź do **Szablony \> Nowy szablon**.</span><span class="sxs-lookup"><span data-stu-id="d63c5-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="d63c5-116">Nazwij nowy szablon</span><span class="sxs-lookup"><span data-stu-id="d63c5-116">Name the new template.</span></span>
1. <span data-ttu-id="d63c5-117">Utwórz szablon na podstawie struktury, która ma być stroną odpowiedzi na błędy kodu stanu.</span><span class="sxs-lookup"><span data-stu-id="d63c5-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="d63c5-118">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="d63c5-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="d63c5-119">Utwórz stronę odpowiedzi na błędy kodu stanu</span><span class="sxs-lookup"><span data-stu-id="d63c5-119">Build the status code error response page</span></span>

<span data-ttu-id="d63c5-120">Aby utworzyć strony odpowiedzi na błędy kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d63c5-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="d63c5-121">Przejdź do **Strony \> Nowa strona**.</span><span class="sxs-lookup"><span data-stu-id="d63c5-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="d63c5-122">Umożliwia określenie nazwy strony odpowiedzi na błędy kodu stanu, ale **nie** ustawienie pola adresu **URL**.</span><span class="sxs-lookup"><span data-stu-id="d63c5-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="d63c5-123">Zbuduj stronę.</span><span class="sxs-lookup"><span data-stu-id="d63c5-123">Build the page.</span></span>
1. <span data-ttu-id="d63c5-124">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="d63c5-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="d63c5-125">Istnieje możliwość utworzenia oddzielnej strony odpowiedzi o błędy kodów stanu dla błędów kodu stanu 4xx i 5xx.</span><span class="sxs-lookup"><span data-stu-id="d63c5-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="d63c5-126">Alternatywnie można skorzystać z tej samej strony odpowiedzi o błędzie o tym samym ogólnym kodzie stanu dla obu kategorii błędów.</span><span class="sxs-lookup"><span data-stu-id="d63c5-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="d63c5-127">Ustawianie przekierowywania dla strony odpowiedzi na błędy kodu stanu</span><span class="sxs-lookup"><span data-stu-id="d63c5-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="d63c5-128">Aby skonfigurować przekierowanie dla strony odpowiedzi na błąd kodu stanu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d63c5-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="d63c5-129">Przejdź do **Adresy URL \> Nowy \> Nowy alias**, a następnie wybierz stronę odpowiedzi na błędy kodu stanu, która została utworzona wcześniej.</span><span class="sxs-lookup"><span data-stu-id="d63c5-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="d63c5-130">W polu **Alias** wprowadź wartość **domyślna-4xx** lub **domyślne-5xx**, zależnie od strony odpowiedzi na błędy kodu stanu, na której konfigurujesz przekierowanie.</span><span class="sxs-lookup"><span data-stu-id="d63c5-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="d63c5-131">Te aliasy muszą zostać opublikowane.</span><span class="sxs-lookup"><span data-stu-id="d63c5-131">These aliases must be published.</span></span> <span data-ttu-id="d63c5-132">W przeciwnym razie przekierowanie nie będzie działać.</span><span class="sxs-lookup"><span data-stu-id="d63c5-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="d63c5-133">Wybierz przycisk **OK**, aby potwierdzić połączenie.</span><span class="sxs-lookup"><span data-stu-id="d63c5-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="d63c5-134">Jeśli w obu kategoriach błędów jest używana jedna strona odpowiedzi o błędzie kodu stanu, powtórz tę procedurę, aby połączyć alias z inną kategorią błędu na tej samej stronie.</span><span class="sxs-lookup"><span data-stu-id="d63c5-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d63c5-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d63c5-135">Additional resources</span></span>

[<span data-ttu-id="d63c5-136">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="d63c5-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="d63c5-137">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="d63c5-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="d63c5-138">Tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="d63c5-138">Create a page URL</span></span>](create-page-url.md)
