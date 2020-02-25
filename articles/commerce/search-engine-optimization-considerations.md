---
title: Zagadnienia optymalizacji wyszukiwarki dla witryny
description: Ten temat obejmuje zagadnienia optymalizacji aparatu wyszukiwania (SEO), które nie zostały rozbudowane do produkcji.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c7afed8e4620d5fe49ead47eb6c17d97d7492ad
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002816"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a><span data-ttu-id="b9a63-103">Zagadnienia optymalizacji wyszukiwarki dla witryny</span><span class="sxs-lookup"><span data-stu-id="b9a63-103">Search engine optimization (SEO) considerations for your site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b9a63-104">Ten temat obejmuje zagadnienia optymalizacji aparatu wyszukiwania (SEO), które nie zostały rozbudowane do produkcji.</span><span class="sxs-lookup"><span data-stu-id="b9a63-104">This topic covers earch engine optimization (SEO) considerations for your site from development to production.</span></span>

## <a name="a-site-that-is-under-development"></a><span data-ttu-id="b9a63-105">Witryna w trakcie opracowywania</span><span class="sxs-lookup"><span data-stu-id="b9a63-105">A site that is under development</span></span>

<span data-ttu-id="b9a63-106">Podczas tworzenia witryny wszystkie strony witryny powinny mieć metatagi **NOINDEX** i **NOFOLLOW**, aby wyszukiwarki nie indeksowały stron i nie zapisywały wersji programistycznych witryny w pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="b9a63-106">While a site is under development, all site pages should have the **NOINDEX** and **NOFOLLOW** meta tags, so that search engines don't index the pages and store development versions of your site in their cache.</span></span> <span data-ttu-id="b9a63-107">Aby wykonać tę konfigurację, musisz dodać domyślny moduł metatagów do szablonu strony serwisu.</span><span class="sxs-lookup"><span data-stu-id="b9a63-107">To do this configuration, you must add the default meta tags module to the site page template.</span></span> <span data-ttu-id="b9a63-108">Domyślne właściwości metatagów będą wówczas dostępne w sekcji właściwości SEO w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="b9a63-108">The default meta tags properties will then be available in the SEO properties section in the page editor.</span></span> <span data-ttu-id="b9a63-109">Te właściwości służą do zarządzania metatagami.</span><span class="sxs-lookup"><span data-stu-id="b9a63-109">You can use these properties to manage the meta tags.</span></span>

## <a name="soft-launch-of-a-site"></a><span data-ttu-id="b9a63-110">Wstępne uruchamianie witryny</span><span class="sxs-lookup"><span data-stu-id="b9a63-110">Soft launch of a site</span></span>

<span data-ttu-id="b9a63-111">Podczas „uruchamiania wstępnego” witryna sieci Web jest udostępniana do ograniczonej grupy odbiorców lub rynku przed wykonaniem pełnego uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="b9a63-111">During a "soft launch," a website is made available to a limited audience or market before the full launch occurs.</span></span> <span data-ttu-id="b9a63-112">W przypadku miękkiego uruchomienia witryny należy rozważyć pozostawienie metatagów **NOINDEX**.</span><span class="sxs-lookup"><span data-stu-id="b9a63-112">If you do a soft launch of your website, you should consider leaving the **NOINDEX** meta tags in place.</span></span> <span data-ttu-id="b9a63-113">W ten sposób pomagasz zagwarantować, że wstępne uruchomienie pozostanie ograniczone do ograniczonej grupy odbiorców, do której chcesz dotrzeć.</span><span class="sxs-lookup"><span data-stu-id="b9a63-113">In this way, you help guarantee that the soft launch remains restricted to the limited audience that you want to reach.</span></span>

## <a name="a-site-that-is-in-production"></a><span data-ttu-id="b9a63-114">Witryna w produkcji</span><span class="sxs-lookup"><span data-stu-id="b9a63-114">A site that is in production</span></span>

<span data-ttu-id="b9a63-115">Jeśli witryna jest w produkcji, należy upewnić się, że wszystkie strony witryny są poprawnie oznakowane.</span><span class="sxs-lookup"><span data-stu-id="b9a63-115">When a site is in production, you should make sure that all site pages are correctly tagged.</span></span> <span data-ttu-id="b9a63-116">Microsoft Dynamics 365 Commerce używa informacji wprowadzonych na stronie w celu renderowania wszystkich informacji dotyczących SEO na tej stronie</span><span class="sxs-lookup"><span data-stu-id="b9a63-116">Microsoft Dynamics 365 Commerce uses the information that is entered for a page to render all the SEO information on that page.</span></span> <span data-ttu-id="b9a63-117">Następujące moduły zapewniają tę funkcjonalność: podsumowanie strony kategorii, podsumowanie strony listy i podsumowanie strony produktu.</span><span class="sxs-lookup"><span data-stu-id="b9a63-117">The following modules provide this functionality: category page summary, list page summary, and product page summary.</span></span>

<span data-ttu-id="b9a63-118">Aby zoptymalizować indeksowanie wyszukiwarek, struktura renderowania wykorzystuje obie informacje z właściwości SEO, które są skonfigurowane w Dynamics 365 Commerce i w informacjach dotyczących modułu.</span><span class="sxs-lookup"><span data-stu-id="b9a63-118">To optimize search engine indexing, the rendering framework uses both information from the SEO properties that are configured in Dynamics 365 Commerce and module-specific information.</span></span> <span data-ttu-id="b9a63-119">W przypadku witryny, która jest produkowana, należy upewnić się, że plik robots.txt pozwala na indeksowanie całej witryny oraz że zawiera linki do opublikowanego dokumentu mapy witryny.</span><span class="sxs-lookup"><span data-stu-id="b9a63-119">For a site that is in production, you should make sure that the robots.txt file allows for indexing of your whole site, and that it contains links to your published site map document.</span></span> <span data-ttu-id="b9a63-120">Należy włączyć funkcję generowania mapy witryny w **Ustawienia witryny \> Mapy witryny włączone**.</span><span class="sxs-lookup"><span data-stu-id="b9a63-120">You should turn on the site map generation functionality at **Site Settings \> Site maps enabled**.</span></span>

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a><span data-ttu-id="b9a63-121">Ustawienia SEO strony dla wewnętrznego podglądu, ograniczonej liczby odbiorców i wszystkich odbiorców</span><span class="sxs-lookup"><span data-stu-id="b9a63-121">Page SEO settings for internal preview, limited audiences, and all audiences</span></span>

<span data-ttu-id="b9a63-122">Ponieważ Dynamics 365 Commerce działa według zasady „to co widzisz, jest tym co dostajesz” (WYSIWYG), autorzy mogą przygotować zawartość strony bez konieczności obaw, że informacje staną się widoczne dla osób odwiedzających witrynę.</span><span class="sxs-lookup"><span data-stu-id="b9a63-122">Because Dynamics 365 Commerce supports "what you see is what you get" (WYSIWYG) authenticated previews, authors can prepare their page content without having to worry that the information will become visible to site visitors.</span></span> <span data-ttu-id="b9a63-123">Jeśli strona musi zostać opublikowana, ale jej ekspozycja musi być ograniczona, powinna mieć metatag **NOINDEX**, aby nie był indeksowany przez wyszukiwarki.</span><span class="sxs-lookup"><span data-stu-id="b9a63-123">If a page must be published, but its exposure must be limited, it should have the **NOINDEX** meta tag, so that it won't be indexed by search engines.</span></span> <span data-ttu-id="b9a63-124">Następnie, gdy strona jest gotowa dla wszystkich odbiorców, wszystkie podstawowe metadane SEO powinny być obecne, aby zmaksymalizować skuteczność indeksowania wyszukiwarek.</span><span class="sxs-lookup"><span data-stu-id="b9a63-124">Then, when the page is ready for all audiences, all the basic SEO metadata should be present, to maximize the efficiency of search engine indexing.</span></span> <span data-ttu-id="b9a63-125">Ponadto należy usunąć metatag **NOLIMIT**.</span><span class="sxs-lookup"><span data-stu-id="b9a63-125">Additionally, the **NOLIMIT** meta tag should be removed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b9a63-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b9a63-126">Additional resources</span></span>

[<span data-ttu-id="b9a63-127">Zarządzanie użytkownikami i rolami e-Commerce</span><span class="sxs-lookup"><span data-stu-id="b9a63-127">Manage e-Commerce users and roles</span></span>](manage-ecommerce-users-roles.md)

[<span data-ttu-id="b9a63-128">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="b9a63-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="b9a63-129">Zarządzanie zasadami zabezpieczeń zawartości (CSP)</span><span class="sxs-lookup"><span data-stu-id="b9a63-129">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
