---
title: Omówienie wyszukiwania w chmurze
description: Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5a9cb82053640b7abdba420e087d0707208979de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997657"
---
# <a name="cloud-powered-search-overview"></a><span data-ttu-id="f5c80-103">Omówienie wyszukiwania w chmurze</span><span class="sxs-lookup"><span data-stu-id="f5c80-103">Cloud-powered search overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f5c80-104">Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f5c80-104">This topic gives an overview of cloud-powered search in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f5c80-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f5c80-105">Overview</span></span>

<span data-ttu-id="f5c80-106">Wykrywanie produktów pomaga zagwarantować klientom szybkie i łatwe wyszukiwanie produktów poprzez przeglądanie kategorii, wyszukiwanie i filtrowanie.</span><span class="sxs-lookup"><span data-stu-id="f5c80-106">Product discoverability helps guarantee that customers can quickly and easily find products by browsing categories, searching, and filtering.</span></span> <span data-ttu-id="f5c80-107">Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami we wszystkich kanałach.</span><span class="sxs-lookup"><span data-stu-id="f5c80-107">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span>

<span data-ttu-id="f5c80-108">Klienci są przyzwyczajeni do niemal natychmiastowych czasów reakcji wyszukiwarek internetowych, wyrafinowanych stron e-Commerce, aplikacji społecznościowych, automatycznych sugestii, które pojawiają się podczas wpisywania wyszukiwanych haseł, fasetowanej nawigacji i wyróżniania.</span><span class="sxs-lookup"><span data-stu-id="f5c80-108">Customers are accustomed to the nearly instantaneous response times of web search engines, sophisticated e-Commerce websites, social apps, automatic suggestions that appear as they type search terms, faceted navigation, and highlighting.</span></span> <span data-ttu-id="f5c80-109">Jeśli klienci nie mogą znaleźć produktu, którego szukają wystarczająco szybko w jednym sklepie e-Commerce, nie zawahają się pójść do innego sklepu e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="f5c80-109">If customers can't find the product that they are looking for quickly enough in one e-Commerce store, they won't hesitate to go to a different e-Commerce store.</span></span>

<span data-ttu-id="f5c80-110">Możliwość wykrywania produktów w chmurze w Dynamics 365 Commerce ułatwia detalistom dalsze zwiększenie częstotliwości przechowywania i kursów wymiany między wszystkimi kanałami, zarówno kanałami e-Commerce i kanałami punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="f5c80-110">The cloud-powered product discoverability in Dynamics 365 Commerce helps retailers continue to increase consumer retention and conversion rates across all channels, both e-Commerce channels and point of sale (POS) channels.</span></span>

<span data-ttu-id="f5c80-111">W wyszukiwaniu Dynamics 365 Commerce ulepszono możliwości pomagające detalistom w osiągnięciu lepszej wykrywalności produktów.</span><span class="sxs-lookup"><span data-stu-id="f5c80-111">The Dynamics 365 Commerce search experience has improved capabilities to help retailers achieve better product discoverability.</span></span> <span data-ttu-id="f5c80-112">Jednocześnie funkcje te zapewniają skalowalność i wydajność, które są wymagane w przypadku ruchu w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="f5c80-112">At the same time, these capabilities deliver the scalability and performance that are required for e-Commerce traffic.</span></span>

## <a name="browse-and-search"></a><span data-ttu-id="f5c80-113">Przeglądaj i szukaj</span><span class="sxs-lookup"><span data-stu-id="f5c80-113">Browse and search</span></span>

<span data-ttu-id="f5c80-114">Trafność i wydajność wyszukiwania są kluczowymi czynnikami w doświadczeniu wielokanałowym, ponieważ odkrywanie produktu polega przede wszystkim na funkcji wyszukiwania w zakresie wyszukiwania informacji i nawigacji treści.</span><span class="sxs-lookup"><span data-stu-id="f5c80-114">Search relevance and performance are key factors in the omnichannel experience, because product discovery relies primarily on search functionality for information retrieval and content navigation.</span></span> <span data-ttu-id="f5c80-115">Skuteczne i wydajne przeglądanie i wyszukiwanie pomaga zwiększyć konwersję.</span><span class="sxs-lookup"><span data-stu-id="f5c80-115">An effective and efficient browse and search experience helps increase conversion.</span></span>

<span data-ttu-id="f5c80-116">Na poniższej ilustracji przedstawiono przykład typowej funkcji przeglądania i wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="f5c80-116">The following illustration shows an example of typical browse and search functionality.</span></span>

![Stona docelowa wyszukiwania](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a><span data-ttu-id="f5c80-118">Szlifowana nawigacja i podsumowanie wyboru</span><span class="sxs-lookup"><span data-stu-id="f5c80-118">Faceted navigation and choice summary</span></span> 

<span data-ttu-id="f5c80-119">Nawigacja fasetowa pomaga klientom łatwiej przeglądać zawartość, umożliwiając im filtrowanie według rafinerii powiązanych z warunkami w zestawie terminów.</span><span class="sxs-lookup"><span data-stu-id="f5c80-119">Faceted navigation helps customers more easily browse for content by letting them filter on refiners that are linked to terms in a term set.</span></span> <span data-ttu-id="f5c80-120">Po wybraniu i zastosowaniu rafinerów przez klienta wyświetlane jest podsumowanie wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="f5c80-120">After a customer has selected and applied refiners, a summary of the choices is shown.</span></span> 

<span data-ttu-id="f5c80-121">Korzystając z nawigacji fasetowej, możesz skonfigurować różne rafinery dla różnych terminów w zestawie terminów, bez konieczności tworzenia dodatkowych stron.</span><span class="sxs-lookup"><span data-stu-id="f5c80-121">By using faceted navigation, you can configure different refiners for different terms in a term set, without having to create additional pages.</span></span> 

<span data-ttu-id="f5c80-122">Poniższa ilustracja pokazuje przykład, w którym podczas wyszukiwania używana jest nawigacja fasetowa.</span><span class="sxs-lookup"><span data-stu-id="f5c80-122">The following illustration shows an example where faceted navigation is used in a search.</span></span>

![Podsumowanie wyboru](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a><span data-ttu-id="f5c80-124">Immersyjne autosugerowanie</span><span class="sxs-lookup"><span data-stu-id="f5c80-124">Immersive autosuggest</span></span>

<span data-ttu-id="f5c80-125">Bieżąca funkcja autosugerowania pokazuje słowa kluczowe, które wyzwalają wyszukanie odpowiedniego słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="f5c80-125">Current autosuggest functionality just shows keywords that trigger a search for the matching keyword.</span></span> <span data-ttu-id="f5c80-126">Ze względu na nowe ulepszenia w Dynamics 365 Commerce klienci mogą często wykrywać łącza do produktów, zanim zakończą one wpisywanie.</span><span class="sxs-lookup"><span data-stu-id="f5c80-126">Because of new enhancements in Dynamics 365 Commerce, customers can often discover links to products before they have finished typing.</span></span>

<span data-ttu-id="f5c80-127">Dynamics 365 Commerce obsługuje także funkcje dotyczące słów kluczowych w różnych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="f5c80-127">Dynamics 365 Commerce also supports functionality for keyword matches in various categories.</span></span> <span data-ttu-id="f5c80-128">Dzięki tej funkcji klienci widzą liczbę słów kluczowych w różnych kategoriach i uruchamiają wyszukiwanie słowa kluczowego w innych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="f5c80-128">This functionality lets customers see the number of matching keywords across categories and trigger a search for a keyword in other categories.</span></span>

<span data-ttu-id="f5c80-129">Na poniższej ilustracji pokazano przykład, na którym jest używana funkcja automatycznego sugerowania.</span><span class="sxs-lookup"><span data-stu-id="f5c80-129">The following illustration shows an example where immersive autosuggest is being used.</span></span>

![immersyjne autosugerowanie](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a><span data-ttu-id="f5c80-131">Sortuj</span><span class="sxs-lookup"><span data-stu-id="f5c80-131">Sort</span></span>

<span data-ttu-id="f5c80-132">Ulepszone sortowanie w Dynamics 365 Commerce umożliwia odbiorcom sortowanie, wyszukiwanie i przeglądanie wyników wyszukiwania oraz modyfikowanie ich według kryteriów, takich jak cena, nazwa produktu i numer produktu.</span><span class="sxs-lookup"><span data-stu-id="f5c80-132">Enhanced sorting in Dynamics 365 Commerce lets customers sort, search, and browse search results, and refine them by criteria such as price, product name, and product number.</span></span> <span data-ttu-id="f5c80-133">Wyniki mogą również posłużyć do sortowania produktów w zależności od tego, czy produkt jest nowością, bestsellerem czy został niedawno dodany.</span><span class="sxs-lookup"><span data-stu-id="f5c80-133">Customers can also sort results based on whether a product is new, top-selling, or recently added.</span></span>

>[!NOTE]
><span data-ttu-id="f5c80-134">Te możliwości wyszukiwania z wykorzystaniem chmury są dostępne począwszy od wersji 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="f5c80-134">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="f5c80-135">Upewnij się, że w menu **Parametry Commerce > Konfigurowanie parametrów** istnieje wpis o wartości „true” dla parametru „ProductSearch.UseAzureSearch”.</span><span class="sxs-lookup"><span data-stu-id="f5c80-135">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="f5c80-136">![Parametry konfiguracji dla wyszukiwania z wykorzystaniem chmury](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="f5c80-136">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5c80-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f5c80-137">Additional resources</span></span>

[<span data-ttu-id="f5c80-138">Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie</span><span class="sxs-lookup"><span data-stu-id="f5c80-138">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="f5c80-139">Zarządzanie metadanymi SEO</span><span class="sxs-lookup"><span data-stu-id="f5c80-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)
