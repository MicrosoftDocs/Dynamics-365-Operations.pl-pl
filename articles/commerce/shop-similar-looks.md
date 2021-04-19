---
title: Włącz rekomendacje „Kup podobne”
description: W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 06b5721c423330b8840bb546bdb144c3189c25bb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795388"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="905f8-103">Włączanie rekomendacji dotyczących „kupowania podobnie wyglądających produktów”</span><span class="sxs-lookup"><span data-stu-id="905f8-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="905f8-104">W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="905f8-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="905f8-105">Funkcja rekomendacji „kup podobne” w Dynamics 365 Commerce wykorzystuje moc sztucznej inteligencji i uczenia maszynowego (AI-ML) do dostarczania klientom rekomendacji dotyczących wizualnie podobnych produktów.</span><span class="sxs-lookup"><span data-stu-id="905f8-105">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="905f8-106">Udostępniając rekomendacje „kupuj podobne” dla wszystkich kanałów sprzedaży detalicznej w usłudze Commerce, sprzedawcy mogą zwiększyć satysfakcję klientów, pomagając klientom łatwo znaleźć to, czego szukają.</span><span class="sxs-lookup"><span data-stu-id="905f8-106">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="905f8-107">Funkcja rekomendacji „kup podobne” wykorzystuje zdjęcia produktów wariantów produktów nasiennych, aby znaleźć i polecić wizualnie podobne produkty w katalogu produktów sprzedawcy.</span><span class="sxs-lookup"><span data-stu-id="905f8-107">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="905f8-108">Rekomendacje „Kup podobne” są dostępne zarówno w punktach sprzedaży (POS), jak i w rozwiązań handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="905f8-108">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="905f8-109">Przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="905f8-109">Example scenarios</span></span>

- <span data-ttu-id="905f8-110">Klient ogląda czarny sweter w paski i otrzymuje rekomendację dotyczącą podobnego swetra w kolorze czerwonym.</span><span class="sxs-lookup"><span data-stu-id="905f8-110">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="905f8-111">Klient wybiera rekomendowany produkt zamiast pierwotnie oglądanego produktu, a następnie otrzymuje rekomendacje podobnych produktów w kolorze czerwonym.</span><span class="sxs-lookup"><span data-stu-id="905f8-111">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="905f8-112">Klient korzysta z zaleceń „Kup podobne”, aby odkryć kolczyki pasujące do pierścionka, którymi jest zainteresowany kupujący.</span><span class="sxs-lookup"><span data-stu-id="905f8-112">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="905f8-113">Włącz rekomendacje „Kup podobne” w Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="905f8-113">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="905f8-114">Zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników Commerce, którzy przeprowadzili migrację magazynu do Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="905f8-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="905f8-115">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="905f8-115">Prerequisites</span></span>

<span data-ttu-id="905f8-116">Zanim sprzedawcy zaczną wyświetlać klientom rekomendacje „kupuj podobny wygląd”, musisz wykonać dwa wstępne kroki:</span><span class="sxs-lookup"><span data-stu-id="905f8-116">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="905f8-117">[Włącz rekomendacje produktów](enable-product-recommendations.md) w Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="905f8-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="905f8-118">Upewnij się, że serwer multimediów obsługuje połączenia HTTPS.</span><span class="sxs-lookup"><span data-stu-id="905f8-118">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="905f8-119">Aby aparat zaleceń mógł uzyskać dostęp do obrazów produktu, detaliści muszą wygenerować adresy URL produktów.</span><span class="sxs-lookup"><span data-stu-id="905f8-119">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="905f8-120">Aby wygenerować adresy URL produktów w centrali Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="905f8-120">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="905f8-121">Przejdź do **Obrazy produktu**.</span><span class="sxs-lookup"><span data-stu-id="905f8-121">Go to **Product images**.</span></span>
1. <span data-ttu-id="905f8-122">W okienku akcji wybierz opcję **Definiuj szablon multimediów**.</span><span class="sxs-lookup"><span data-stu-id="905f8-122">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="905f8-123">W okienku właściowości **Definiuj szablon multimediów** w obszarze **Adresy URL multimediów** wybierz opcję **Generuj adresy URL**.</span><span class="sxs-lookup"><span data-stu-id="905f8-123">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="905f8-124">Po włączeniu funkcji rekomendacji „kup podobne” rozpoczyna się proces generowania list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="905f8-124">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="905f8-125">Może minąć nawet jeden dzień, zanim listy te będą dostępne i widoczne w Internecie i na terminalach POS.</span><span class="sxs-lookup"><span data-stu-id="905f8-125">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="905f8-126">Aby włączyć funkcję rekomendacji „Kup podobne” w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="905f8-126">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="905f8-127">Przejdź do obszaru **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="905f8-127">Go to **Feature management**.</span></span>
1. <span data-ttu-id="905f8-128">Na liście dostępnych funkcji wyszukaj i wybierz pozycję **Kup podobne**.</span><span class="sxs-lookup"><span data-stu-id="905f8-128">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="905f8-129">W prawym okienku wybierz opcję **Włącz**, aby włączyć usługę.</span><span class="sxs-lookup"><span data-stu-id="905f8-129">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="905f8-130">Na poniższej ilustracji przedstawiono funkcję **Kup podobne** na stronie **Zarządzanie funkcjami** w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="905f8-130">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![Funkcja Sklep podobny wygląda na stronie zarządzania funkcjami w siedzibie Commerce](./media/enableshopsimilarlooks.png)

<span data-ttu-id="905f8-132">Po zakończeniu powyższych zadań terminale POS są automatycznie rozszerzane za pomocą panelu **Kup podobne produkty**.</span><span class="sxs-lookup"><span data-stu-id="905f8-132">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="905f8-133">Po wybraniu opcji **Zobacz więcej**, użytkownicy terminalu w punkcie sprzedaży mogą zostać uwzględnieni w dedykowanej stronie „kup podobne”, którą można później przefiltrować.</span><span class="sxs-lookup"><span data-stu-id="905f8-133">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="905f8-134">Jeśli wyłączysz funkcję rekomendacji „Kup podobne”, nie ma to wpływu na inne typy rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="905f8-134">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="905f8-135">Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="905f8-135">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="905f8-136">Dodaj przycisk „Kup podobne” do stron szczegółów produktu za pomocą narzędzia do tworzenia witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="905f8-136">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="905f8-137">Po włączeniu funkcji rekomendacji „kup podobny wygląd” w centrali Commerce, opcja w narzędziu do tworzenia witryn Commerce umożliwia sprzedawcom detalicznym dodanie przycisku **Kup podobne** do pola zakupu na dowolnej stronie szczegółów produktu (PDP).</span><span class="sxs-lookup"><span data-stu-id="905f8-137">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="905f8-138">Klient, który wybierze ten przycisk, zostaje przeniesiony na specjalną stronę „Kup podobne produkty”, która zwraca wizualnie podobne produkty.</span><span class="sxs-lookup"><span data-stu-id="905f8-138">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="905f8-139">W tym celu odbiorca może wykorzystać selektory do dalszego filtrowania produktów.</span><span class="sxs-lookup"><span data-stu-id="905f8-139">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="905f8-140">Aby dodać przycisk **Kup podobne** do stron PDP za pomocą narzędzia do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="905f8-140">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="905f8-141">Otwórz istniejącą stronę konstruktora witryn zawierającą moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="905f8-141">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="905f8-142">W okienku nawigacji po lewej stronie zaznacz moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="905f8-142">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="905f8-143">W prawym okienku nawigacji zaznacz pole wyboru **Włącz łącze zakup podobne**.</span><span class="sxs-lookup"><span data-stu-id="905f8-143">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="905f8-144">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="905f8-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="905f8-145">Po opublikowaniu strony PDP będzie zawierała przycisk **Kup podobne**.</span><span class="sxs-lookup"><span data-stu-id="905f8-145">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="905f8-146">Na poniższej ilustracji przedstawiono pole wyboru **Włącz łącze zakup podobne** i **Kup podobne** na przykładowej PDP w konstruktorze witryn.</span><span class="sxs-lookup"><span data-stu-id="905f8-146">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Włącz pole wyboru Kupuj podobne i przycisk Kupuj podobne na PDP w narzędziu do tworzenia witryn](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="905f8-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="905f8-148">Additional resources</span></span>

[<span data-ttu-id="905f8-149">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="905f8-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="905f8-150">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="905f8-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="905f8-151">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="905f8-151">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="905f8-152">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="905f8-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="905f8-153">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="905f8-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="905f8-154">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="905f8-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="905f8-155">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="905f8-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="905f8-156">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="905f8-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="905f8-157">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="905f8-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="905f8-158">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="905f8-158">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
