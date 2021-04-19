---
title: Omówienie wyszukiwania w chmurze
description: Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b5182df9d45a3b5d2572a5b6b391c924ef23bf9a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800428"
---
# <a name="cloud-powered-search-overview"></a><span data-ttu-id="ace18-103">Omówienie wyszukiwania w chmurze</span><span class="sxs-lookup"><span data-stu-id="ace18-103">Cloud-powered search overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ace18-104">Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ace18-104">This topic gives an overview of cloud-powered search in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ace18-105">Wykrywanie produktów pomaga zagwarantować klientom szybkie i łatwe wyszukiwanie produktów poprzez przeglądanie kategorii, wyszukiwanie i filtrowanie.</span><span class="sxs-lookup"><span data-stu-id="ace18-105">Product discoverability helps guarantee that customers can quickly and easily find products by browsing categories, searching, and filtering.</span></span> <span data-ttu-id="ace18-106">Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami we wszystkich kanałach.</span><span class="sxs-lookup"><span data-stu-id="ace18-106">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span>

<span data-ttu-id="ace18-107">Klienci są przyzwyczajeni do niemal natychmiastowych czasów reakcji wyszukiwarek internetowych, wyrafinowanych stron e-Commerce, aplikacji społecznościowych, automatycznych sugestii, które pojawiają się podczas wpisywania wyszukiwanych haseł, fasetowanej nawigacji i wyróżniania.</span><span class="sxs-lookup"><span data-stu-id="ace18-107">Customers are accustomed to the nearly instantaneous response times of web search engines, sophisticated e-Commerce websites, social apps, automatic suggestions that appear as they type search terms, faceted navigation, and highlighting.</span></span> <span data-ttu-id="ace18-108">Jeśli klienci nie mogą znaleźć produktu, którego szukają wystarczająco szybko w jednym sklepie e-Commerce, nie zawahają się pójść do innego sklepu e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ace18-108">If customers can't find the product that they are looking for quickly enough in one e-Commerce store, they won't hesitate to go to a different e-Commerce store.</span></span>

<span data-ttu-id="ace18-109">Możliwość wykrywania produktów w chmurze w Dynamics 365 Commerce ułatwia detalistom dalsze zwiększenie częstotliwości przechowywania i kursów wymiany między wszystkimi kanałami, zarówno kanałami e-Commerce i kanałami punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="ace18-109">The cloud-powered product discoverability in Dynamics 365 Commerce helps retailers continue to increase consumer retention and conversion rates across all channels, both e-Commerce channels and point of sale (POS) channels.</span></span>

<span data-ttu-id="ace18-110">W wyszukiwaniu Dynamics 365 Commerce ulepszono możliwości pomagające detalistom w osiągnięciu lepszej wykrywalności produktów.</span><span class="sxs-lookup"><span data-stu-id="ace18-110">The Dynamics 365 Commerce search experience has improved capabilities to help retailers achieve better product discoverability.</span></span> <span data-ttu-id="ace18-111">Jednocześnie funkcje te zapewniają skalowalność i wydajność, które są wymagane w przypadku ruchu w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ace18-111">At the same time, these capabilities deliver the scalability and performance that are required for e-Commerce traffic.</span></span>

## <a name="browse-and-search"></a><span data-ttu-id="ace18-112">Przeglądaj i szukaj</span><span class="sxs-lookup"><span data-stu-id="ace18-112">Browse and search</span></span>

<span data-ttu-id="ace18-113">Trafność i wydajność wyszukiwania są kluczowymi czynnikami w doświadczeniu wielokanałowym, ponieważ odkrywanie produktu polega przede wszystkim na funkcji wyszukiwania w zakresie wyszukiwania informacji i nawigacji treści.</span><span class="sxs-lookup"><span data-stu-id="ace18-113">Search relevance and performance are key factors in the omnichannel experience, because product discovery relies primarily on search functionality for information retrieval and content navigation.</span></span> <span data-ttu-id="ace18-114">Skuteczne i wydajne przeglądanie i wyszukiwanie pomaga zwiększyć konwersję.</span><span class="sxs-lookup"><span data-stu-id="ace18-114">An effective and efficient browse and search experience helps increase conversion.</span></span>

<span data-ttu-id="ace18-115">Na poniższej ilustracji przedstawiono przykład typowej funkcji przeglądania i wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ace18-115">The following illustration shows an example of typical browse and search functionality.</span></span>

![Stona docelowa wyszukiwania](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a><span data-ttu-id="ace18-117">Szlifowana nawigacja i podsumowanie wyboru</span><span class="sxs-lookup"><span data-stu-id="ace18-117">Faceted navigation and choice summary</span></span> 

<span data-ttu-id="ace18-118">Nawigacja fasetowa pomaga klientom łatwiej przeglądać zawartość, umożliwiając im filtrowanie według rafinerii powiązanych z warunkami w zestawie terminów.</span><span class="sxs-lookup"><span data-stu-id="ace18-118">Faceted navigation helps customers more easily browse for content by letting them filter on refiners that are linked to terms in a term set.</span></span> <span data-ttu-id="ace18-119">Po wybraniu i zastosowaniu rafinerów przez klienta wyświetlane jest podsumowanie wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="ace18-119">After a customer has selected and applied refiners, a summary of the choices is shown.</span></span> 

<span data-ttu-id="ace18-120">Korzystając z nawigacji fasetowej, możesz skonfigurować różne rafinery dla różnych terminów w zestawie terminów, bez konieczności tworzenia dodatkowych stron.</span><span class="sxs-lookup"><span data-stu-id="ace18-120">By using faceted navigation, you can configure different refiners for different terms in a term set, without having to create additional pages.</span></span> 

<span data-ttu-id="ace18-121">Poniższa ilustracja pokazuje przykład, w którym podczas wyszukiwania używana jest nawigacja fasetowa.</span><span class="sxs-lookup"><span data-stu-id="ace18-121">The following illustration shows an example where faceted navigation is used in a search.</span></span>

![Podsumowanie wyboru](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a><span data-ttu-id="ace18-123">Immersyjne autosugerowanie</span><span class="sxs-lookup"><span data-stu-id="ace18-123">Immersive autosuggest</span></span>

<span data-ttu-id="ace18-124">Bieżąca funkcja autosugerowania pokazuje słowa kluczowe, które wyzwalają wyszukanie odpowiedniego słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="ace18-124">Current autosuggest functionality just shows keywords that trigger a search for the matching keyword.</span></span> <span data-ttu-id="ace18-125">Ze względu na nowe ulepszenia w Dynamics 365 Commerce klienci mogą często wykrywać łącza do produktów, zanim zakończą one wpisywanie.</span><span class="sxs-lookup"><span data-stu-id="ace18-125">Because of new enhancements in Dynamics 365 Commerce, customers can often discover links to products before they have finished typing.</span></span>

<span data-ttu-id="ace18-126">Dynamics 365 Commerce obsługuje także funkcje dotyczące słów kluczowych w różnych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="ace18-126">Dynamics 365 Commerce also supports functionality for keyword matches in various categories.</span></span> <span data-ttu-id="ace18-127">Dzięki tej funkcji klienci widzą liczbę słów kluczowych w różnych kategoriach i uruchamiają wyszukiwanie słowa kluczowego w innych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="ace18-127">This functionality lets customers see the number of matching keywords across categories and trigger a search for a keyword in other categories.</span></span>

<span data-ttu-id="ace18-128">Na poniższej ilustracji pokazano przykład, na którym jest używana funkcja automatycznego sugerowania.</span><span class="sxs-lookup"><span data-stu-id="ace18-128">The following illustration shows an example where immersive autosuggest is being used.</span></span>

![immersyjne autosugerowanie](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a><span data-ttu-id="ace18-130">Sortuj</span><span class="sxs-lookup"><span data-stu-id="ace18-130">Sort</span></span>

<span data-ttu-id="ace18-131">Ulepszone sortowanie w Dynamics 365 Commerce umożliwia odbiorcom sortowanie, wyszukiwanie i przeglądanie wyników wyszukiwania oraz modyfikowanie ich według kryteriów, takich jak cena, nazwa produktu i numer produktu.</span><span class="sxs-lookup"><span data-stu-id="ace18-131">Enhanced sorting in Dynamics 365 Commerce lets customers sort, search, and browse search results, and refine them by criteria such as price, product name, and product number.</span></span> <span data-ttu-id="ace18-132">Wyniki mogą również posłużyć do sortowania produktów w zależności od tego, czy produkt jest nowością, bestsellerem czy został niedawno dodany.</span><span class="sxs-lookup"><span data-stu-id="ace18-132">Customers can also sort results based on whether a product is new, top-selling, or recently added.</span></span>

>[!NOTE]
><span data-ttu-id="ace18-133">Te możliwości wyszukiwania z wykorzystaniem chmury są dostępne począwszy od wersji 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="ace18-133">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="ace18-134">Upewnij się, że w menu **Parametry Commerce > Konfigurowanie parametrów** istnieje wpis o wartości „true” dla parametru „ProductSearch.UseAzureSearch”.</span><span class="sxs-lookup"><span data-stu-id="ace18-134">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="ace18-135">![Parametry konfiguracji dla wyszukiwania z wykorzystaniem chmury](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="ace18-135">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ace18-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ace18-136">Additional resources</span></span>

[<span data-ttu-id="ace18-137">Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie</span><span class="sxs-lookup"><span data-stu-id="ace18-137">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="ace18-138">Zarządzanie metadanymi SEO</span><span class="sxs-lookup"><span data-stu-id="ace18-138">Manage SEO metadata</span></span>](manage-seo-metadata.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
