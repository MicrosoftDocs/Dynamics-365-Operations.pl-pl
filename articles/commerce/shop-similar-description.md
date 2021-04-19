---
title: Włączanie rekomendacji dotyczących „kupowania podobnie opisanych produktów”
description: W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bsokolov
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ce01ef1d4b916d955685b4d01dafd3d54d6fcebd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795412"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="73f7c-103">Włączanie rekomendacji dotyczących „kupowania produktów z podobnym opisem”</span><span class="sxs-lookup"><span data-stu-id="73f7c-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73f7c-104">W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="73f7c-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="73f7c-105">Funkcja rekomendacji „kup podobne” w Dynamics 365 Commerce wykorzystuje sztuczną inteligencję i uczenie maszynowe (AI-ML) do dostarczania rekomendacji dla produktów, które mają opisy podobne do tego, czego szuka klient.</span><span class="sxs-lookup"><span data-stu-id="73f7c-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="73f7c-106">Udostępniając rekomendacje „kupuj o podobnym opisie” dla wszystkich kanałów sprzedaży detalicznej w usłudze Commerce, sprzedawcy pomóc klientom łatwo znaleźć to, czego szukają.</span><span class="sxs-lookup"><span data-stu-id="73f7c-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="73f7c-107">Funkcjonalność rekomendacji „kupuj podobny opis” wykorzystuje nazwę produktu i opis produktów nasiennych, aby znaleźć i polecić podobne produkty w katalogu produktów sprzedawcy.</span><span class="sxs-lookup"><span data-stu-id="73f7c-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="73f7c-108">Rekomendacje „Kup podobnie opisane” są dostępne zarówno w punktach sprzedaży (POS), jak i w rozwiązań handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="73f7c-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="73f7c-109">Przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="73f7c-109">Example scenarios</span></span>

<span data-ttu-id="73f7c-110">W poniższych przykładach przedstawiono typy rekomendacji, które może dostarczać funkcja „kupuj podobne”:</span><span class="sxs-lookup"><span data-stu-id="73f7c-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="73f7c-111">Klient ogląda parę okularów w rogowej oprawie w stylu retro i otrzymuje zestaw zaleceń dotyczących innych okularów o podobnym wyglądzie w kontekście branży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="73f7c-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="73f7c-112">Klient korzysta z zaleceń „kupuj podobne”, aby odkryć aromaty kawy, które są podobne do smaku, który wcześniej kupił od sprzedawcy.</span><span class="sxs-lookup"><span data-stu-id="73f7c-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="73f7c-113">Włączanie rekomendacji dotyczących „kupowania podobnie opisanych produktów”</span><span class="sxs-lookup"><span data-stu-id="73f7c-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="73f7c-114">Zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników Commerce, którzy przeprowadzili migrację magazynu do Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="73f7c-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="73f7c-115">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="73f7c-115">Prerequisites</span></span>

<span data-ttu-id="73f7c-116">Zanim rekomendacje „kupuj podobne” będą mogły być wyświetlane klientom, musisz spełnić następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="73f7c-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="73f7c-117">[Włącz rekomendacje produktów](enable-product-recommendations.md) w Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="73f7c-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="73f7c-118">Upewnij się, że serwer multimediów obsługuje połączenia HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73f7c-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="73f7c-119">Włącz funkcję rekomendacji „kupowania podobnie opisanych produktów”</span><span class="sxs-lookup"><span data-stu-id="73f7c-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="73f7c-120">Aby włączyć funkcję rekomendacji „Kup podobne” w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="73f7c-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="73f7c-121">W obszarze roboczym **Zarządzanie funkcjami** z listy dostępnych funkcji wyszukaj i wybierz pozycję **Kup podobnie opisane**.</span><span class="sxs-lookup"><span data-stu-id="73f7c-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="73f7c-122">W okienku po prawej stronie włącz pozycję **Włączanie**.</span><span class="sxs-lookup"><span data-stu-id="73f7c-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="73f7c-123">Po włączeniu tej funkcji system zaczyna generować listy rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="73f7c-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="73f7c-124">Może minąć nawet jeden dzień, zanim listy te staną się dostępne i widoczne w Internecie i na terminalach POS.</span><span class="sxs-lookup"><span data-stu-id="73f7c-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="73f7c-125">Wyłączenie tej funkcji nie wpływa na inne typy rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="73f7c-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="73f7c-126">Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="73f7c-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="73f7c-127">Dodawanie przycisku Opis sklepu podobnego do stron szczegółów produktu</span><span class="sxs-lookup"><span data-stu-id="73f7c-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="73f7c-128">Po włączeniu funkcji rekomendacji „kupuj podobne” w centrali Commerce możesz dodać przycisk **Kupuj podobne** do pola zakupu na dowolnej stronie szczegółów produktu (PDP).</span><span class="sxs-lookup"><span data-stu-id="73f7c-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="73f7c-129">Klient, który wybierze ten przycisk, zostaje przeniesiony na specjalną stronę **Kup podobnie opisane**, która zwraca wizualnie podobne produkty.</span><span class="sxs-lookup"><span data-stu-id="73f7c-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="73f7c-130">W tym celu odbiorca może wykorzystać selektory do dalszego filtrowania produktów.</span><span class="sxs-lookup"><span data-stu-id="73f7c-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="73f7c-131">Aby dodać przycisk **Kup podobnie opisane** do stron PDP za pomocą narzędzia do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="73f7c-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="73f7c-132">Otwórz istniejącą stronę konstruktora witryn zawierającą moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="73f7c-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="73f7c-133">W okienku nawigacji po lewej stronie zaznacz moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="73f7c-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="73f7c-134">W prawym okienku nawigacji zaznacz pole wyboru **Włącz łącze kup podobnie opisane**.</span><span class="sxs-lookup"><span data-stu-id="73f7c-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="73f7c-135">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73f7c-135">Select **Save**.</span></span>
1. <span data-ttu-id="73f7c-136">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="73f7c-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="73f7c-137">Po opublikowaniu strony PDP będzie zawierała przycisk **Kup podobnie opisane**.</span><span class="sxs-lookup"><span data-stu-id="73f7c-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="73f7c-138">Na poniższej ilustracji przedstawiono pole wyboru **Włącz łącze kup podobnie opisane** i **Kup podobnie opisane** na przykładowej PDP w konstruktorze witryn.</span><span class="sxs-lookup"><span data-stu-id="73f7c-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![Włącz pole wyboru Link do podobnego opisu sklepu i przycisk Kup podobny opis na PDP w narzędziu do tworzenia witryn](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="73f7c-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="73f7c-140">Additional resources</span></span>

[<span data-ttu-id="73f7c-141">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="73f7c-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="73f7c-142">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="73f7c-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="73f7c-143">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="73f7c-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="73f7c-144">Włączanie rekomendacji dotyczących „kupowania podobnie wyglądających produktów”</span><span class="sxs-lookup"><span data-stu-id="73f7c-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="73f7c-145">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="73f7c-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="73f7c-146">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="73f7c-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="73f7c-147">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="73f7c-147">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]