---
title: Omówienie wyszukiwania w chmurze
description: Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 015f308640117b1354868c9f37e4b8df9cac6f2a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697206"
---
# <a name="cloud-powered-search-overview"></a><span data-ttu-id="7c82d-103">Omówienie wyszukiwania w chmurze</span><span class="sxs-lookup"><span data-stu-id="7c82d-103">Cloud-powered search overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="7c82d-104">Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7c82d-104">This topic gives an overview of cloud-powered search in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7c82d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="7c82d-105">Overview</span></span>

<span data-ttu-id="7c82d-106">Wykrywanie produktów pomaga zagwarantować klientom szybkie i łatwe wyszukiwanie produktów poprzez przeglądanie kategorii, wyszukiwanie i filtrowanie.</span><span class="sxs-lookup"><span data-stu-id="7c82d-106">Product discoverability helps guarantee that customers can quickly and easily find products by browsing categories, searching, and filtering.</span></span> <span data-ttu-id="7c82d-107">Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami w całym kanale sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="7c82d-107">Retailers consider product discovery a primary tool for customer interaction across all retail channels.</span></span>

<span data-ttu-id="7c82d-108">Klienci są przyzwyczajeni do niemal natychmiastowych czasów reakcji wyszukiwarek internetowych, wyrafinowanych stron e-Commerce, aplikacji społecznościowych, automatycznych sugestii, które pojawiają się podczas wpisywania wyszukiwanych haseł, fasetowanej nawigacji i wyróżniania.</span><span class="sxs-lookup"><span data-stu-id="7c82d-108">Customers are accustomed to the nearly instantaneous response times of web search engines, sophisticated e-Commerce websites, social apps, automatic suggestions that appear as they type search terms, faceted navigation, and highlighting.</span></span> <span data-ttu-id="7c82d-109">Jeśli klienci nie mogą znaleźć produktu, którego szukają wystarczająco szybko w jednym sklepie e-Commerce, nie zawahają się pójść do innego sklepu e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="7c82d-109">If customers can't find the product that they are looking for quickly enough in one e-Commerce store, they won't hesitate to go to a different e-Commerce store.</span></span>

<span data-ttu-id="7c82d-110">Możliwość wykrywania produktów w chmurze w Dynamics 365 Commerce ułatwia detalistom dalsze zwiększenie częstotliwości przechowywania i kursów wymiany między wszystkimi kanałami, zarówno kanałami e-Commerce i kanałami punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="7c82d-110">The cloud-powered product discoverability in Dynamics 365 Commerce helps retailers continue to increase consumer retention and conversion rates across all channels, both e-Commerce channels and point of sale (POS) channels.</span></span>

<span data-ttu-id="7c82d-111">W wyszukiwaniu Dynamics 365 Commerce ulepszono możliwości pomagające detalistom w osiągnięciu lepszej wykrywalności produktów.</span><span class="sxs-lookup"><span data-stu-id="7c82d-111">The Dynamics 365 Commerce search experience has improved capabilities to help retailers achieve better product discoverability.</span></span> <span data-ttu-id="7c82d-112">Jednocześnie funkcje te zapewniają skalowalność i wydajność, które są wymagane w przypadku ruchu w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="7c82d-112">At the same time, these capabilities deliver the scalability and performance that are required for e-Commerce traffic.</span></span>

## <a name="browse-and-search"></a><span data-ttu-id="7c82d-113">Przeglądaj i szukaj</span><span class="sxs-lookup"><span data-stu-id="7c82d-113">Browse and search</span></span>

<span data-ttu-id="7c82d-114">Trafność i wydajność wyszukiwania są kluczowymi czynnikami w doświadczeniu wielokanałowym, ponieważ odkrywanie produktu polega przede wszystkim na funkcji wyszukiwania w zakresie wyszukiwania informacji i nawigacji treści.</span><span class="sxs-lookup"><span data-stu-id="7c82d-114">Search relevance and performance are key factors in the omnichannel experience, because product discovery relies primarily on search functionality for information retrieval and content navigation.</span></span> <span data-ttu-id="7c82d-115">Skuteczne i wydajne przeglądanie i wyszukiwanie pomaga zwiększyć konwersję.</span><span class="sxs-lookup"><span data-stu-id="7c82d-115">An effective and efficient browse and search experience helps increase conversion.</span></span>

<span data-ttu-id="7c82d-116">Na poniższej ilustracji przedstawiono przykład typowej funkcji przeglądania i wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="7c82d-116">The following illustration shows an example of typical browse and search functionality.</span></span>

![Stona docelowa wyszukiwania](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a><span data-ttu-id="7c82d-118">Szlifowana nawigacja i podsumowanie wyboru</span><span class="sxs-lookup"><span data-stu-id="7c82d-118">Faceted navigation and choice summary</span></span> 

<span data-ttu-id="7c82d-119">Nawigacja fasetowa pomaga klientom łatwiej przeglądać zawartość, umożliwiając im filtrowanie według rafinerii powiązanych z warunkami w zestawie terminów.</span><span class="sxs-lookup"><span data-stu-id="7c82d-119">Faceted navigation helps customers more easily browse for content by letting them filter on refiners that are linked to terms in a term set.</span></span> <span data-ttu-id="7c82d-120">Po wybraniu i zastosowaniu rafinerów przez klienta wyświetlane jest podsumowanie wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="7c82d-120">After a customer has selected and applied refiners, a summary of the choices is shown.</span></span> 

<span data-ttu-id="7c82d-121">Korzystając z nawigacji fasetowej, możesz skonfigurować różne rafinery dla różnych terminów w zestawie terminów, bez konieczności tworzenia dodatkowych stron.</span><span class="sxs-lookup"><span data-stu-id="7c82d-121">By using faceted navigation, you can configure different refiners for different terms in a term set, without having to create additional pages.</span></span> 

<span data-ttu-id="7c82d-122">Poniższa ilustracja pokazuje przykład, w którym podczas wyszukiwania używana jest nawigacja fasetowa.</span><span class="sxs-lookup"><span data-stu-id="7c82d-122">The following illustration shows an example where faceted navigation is used in a search.</span></span>

![Podsumowanie wyboru](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a><span data-ttu-id="7c82d-124">Immersyjne autosugerowanie</span><span class="sxs-lookup"><span data-stu-id="7c82d-124">Immersive autosuggest</span></span>

<span data-ttu-id="7c82d-125">Bieżąca funkcja autosugerowania pokazuje słowa kluczowe, które wyzwalają wyszukanie odpowiedniego słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="7c82d-125">Current autosuggest functionality just shows keywords that trigger a search for the matching keyword.</span></span> <span data-ttu-id="7c82d-126">Ze względu na nowe ulepszenia w Dynamics 365 Commerce klienci mogą często wykrywać łącza do produktów, zanim zakończą one wpisywanie.</span><span class="sxs-lookup"><span data-stu-id="7c82d-126">Because of new enhancements in Dynamics 365 Commerce, customers can often discover links to products before they have finished typing.</span></span>

<span data-ttu-id="7c82d-127">Dynamics 365 Commerce obsługuje także funkcje dotyczące słów kluczowych w różnych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="7c82d-127">Dynamics 365 Commerce also supports functionality for keyword matches in various categories.</span></span> <span data-ttu-id="7c82d-128">Dzięki tej funkcji klienci widzą liczbę słów kluczowych w różnych kategoriach i uruchamiają wyszukiwanie słowa kluczowego w innych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="7c82d-128">This functionality lets customers see the number of matching keywords across categories and trigger a search for a keyword in other categories.</span></span>

<span data-ttu-id="7c82d-129">Na poniższej ilustracji pokazano przykład, na którym jest używana funkcja automatycznego sugerowania.</span><span class="sxs-lookup"><span data-stu-id="7c82d-129">The following illustration shows an example where immersive autosuggest is being used.</span></span>

![immersyjne autosugerowanie](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a><span data-ttu-id="7c82d-131">Sortuj</span><span class="sxs-lookup"><span data-stu-id="7c82d-131">Sort</span></span>

<span data-ttu-id="7c82d-132">Ulepszone sortowanie w Dynamics 365 Commerce umożliwia odbiorcom sortowanie, wyszukiwanie i przeglądanie wyników wyszukiwania oraz modyfikowanie ich według kryteriów, takich jak cena, nazwa produktu i numer produktu.</span><span class="sxs-lookup"><span data-stu-id="7c82d-132">Enhanced sorting in Dynamics 365 Commerce lets customers sort, search, and browse search results, and refine them by criteria such as price, product name, and product number.</span></span> <span data-ttu-id="7c82d-133">Wyniki mogą również posłużyć do sortowania produktów w zależności od tego, czy produkt jest nowością, bestsellerem czy został niedawno dodany.</span><span class="sxs-lookup"><span data-stu-id="7c82d-133">Customers can also sort results based on whether a product is new, top-selling, or recently added.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c82d-134">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7c82d-134">Additional resources</span></span>

[<span data-ttu-id="7c82d-135">Domyślna strona docelowa kategorii i strona wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="7c82d-135">Default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="7c82d-136">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="7c82d-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)
