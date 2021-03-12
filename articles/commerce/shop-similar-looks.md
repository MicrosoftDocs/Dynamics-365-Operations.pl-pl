---
title: Włącz rekomendacje „Kup podobne”
description: W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 95e4246d6c5f9ac5bc86b626be0d971f756c5130
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985618"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="7a72f-103">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="7a72f-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7a72f-104">W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7a72f-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7a72f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="7a72f-105">Overview</span></span>

<span data-ttu-id="7a72f-106">Funkcja rekomendacji „kup podobne” w Dynamics 365 Commerce wykorzystuje moc sztucznej inteligencji i uczenia maszynowego (AI-ML) do dostarczania klientom rekomendacji dotyczących wizualnie podobnych produktów.</span><span class="sxs-lookup"><span data-stu-id="7a72f-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="7a72f-107">Udostępniając rekomendacje „kupuj podobne” dla wszystkich kanałów sprzedaży detalicznej w usłudze Commerce, sprzedawcy mogą zwiększyć satysfakcję klientów, pomagając klientom łatwo znaleźć to, czego szukają.</span><span class="sxs-lookup"><span data-stu-id="7a72f-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="7a72f-108">Funkcja rekomendacji „kup podobne” wykorzystuje zdjęcia produktów wariantów produktów nasiennych, aby znaleźć i polecić wizualnie podobne produkty w katalogu produktów sprzedawcy.</span><span class="sxs-lookup"><span data-stu-id="7a72f-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="7a72f-109">Rekomendacje „Kup podobne” są dostępne zarówno w punktach sprzedaży (POS), jak i w rozwiązań handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="7a72f-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="7a72f-110">Przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="7a72f-110">Example scenarios</span></span>

- <span data-ttu-id="7a72f-111">Klient ogląda czarny sweter w paski i otrzymuje rekomendację dotyczącą podobnego swetra w kolorze czerwonym.</span><span class="sxs-lookup"><span data-stu-id="7a72f-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="7a72f-112">Klient wybiera rekomendowany produkt zamiast pierwotnie oglądanego produktu, a następnie otrzymuje rekomendacje podobnych produktów w kolorze czerwonym.</span><span class="sxs-lookup"><span data-stu-id="7a72f-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="7a72f-113">Klient korzysta z zaleceń „Kup podobne”, aby odkryć kolczyki pasujące do pierścionka, którymi jest zainteresowany kupujący.</span><span class="sxs-lookup"><span data-stu-id="7a72f-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="7a72f-114">Włącz rekomendacje „Kup podobne” w Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="7a72f-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="7a72f-115">Zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników Commerce, którzy przeprowadzili migrację magazynu do Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="7a72f-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7a72f-116">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7a72f-116">Prerequisites</span></span>

<span data-ttu-id="7a72f-117">Zanim sprzedawcy zaczną wyświetlać klientom rekomendacje „kupuj podobny wygląd”, musisz wykonać dwa wstępne kroki:</span><span class="sxs-lookup"><span data-stu-id="7a72f-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="7a72f-118">[Włącz rekomendacje produktów](enable-product-recommendations.md) w Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="7a72f-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="7a72f-119">Upewnij się, że serwer multimediów obsługuje połączenia HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7a72f-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="7a72f-120">Aby aparat zaleceń mógł uzyskać dostęp do obrazów produktu, detaliści muszą wygenerować adresy URL produktów.</span><span class="sxs-lookup"><span data-stu-id="7a72f-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="7a72f-121">Aby wygenerować adresy URL produktów w centrali Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7a72f-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="7a72f-122">Przejdź do **Obrazy produktu**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="7a72f-123">W okienku akcji wybierz opcję **Definiuj szablon multimediów**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="7a72f-124">W okienku właściowości **Definiuj szablon multimediów** w obszarze **Adresy URL multimediów** wybierz opcję **Generuj adresy URL**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="7a72f-125">Po włączeniu funkcji rekomendacji „kup podobne” rozpoczyna się proces generowania list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="7a72f-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="7a72f-126">Może minąć nawet jeden dzień, zanim listy te będą dostępne i widoczne w Internecie i na terminalach POS.</span><span class="sxs-lookup"><span data-stu-id="7a72f-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="7a72f-127">Aby włączyć funkcję rekomendacji „Kup podobne” w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7a72f-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="7a72f-128">Przejdź do obszaru **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="7a72f-129">Na liście dostępnych funkcji wyszukaj i wybierz pozycję **Kup podobne**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="7a72f-130">W prawym okienku wybierz opcję **Włącz**, aby włączyć usługę.</span><span class="sxs-lookup"><span data-stu-id="7a72f-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="7a72f-131">Na poniższej ilustracji przedstawiono funkcję **Kup podobne** na stronie **Zarządzanie funkcjami** w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="7a72f-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![Funkcja Sklep podobny wygląda na stronie zarządzania funkcjami w siedzibie Commerce](./media/enableshopsimilarlooks.png)

<span data-ttu-id="7a72f-133">Po zakończeniu powyższych zadań terminale POS są automatycznie rozszerzane za pomocą panelu **Kup podobne produkty**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="7a72f-134">Po wybraniu opcji **Zobacz więcej**, użytkownicy terminalu w punkcie sprzedaży mogą zostać uwzględnieni w dedykowanej stronie „kup podobne”, którą można później przefiltrować.</span><span class="sxs-lookup"><span data-stu-id="7a72f-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="7a72f-135">Jeśli wyłączysz funkcję rekomendacji „Kup podobne”, nie ma to wpływu na inne typy rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="7a72f-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="7a72f-136">Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="7a72f-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="7a72f-137">Dodaj przycisk „Kup podobne” do stron szczegółów produktu za pomocą narzędzia do tworzenia witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="7a72f-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="7a72f-138">Po włączeniu funkcji rekomendacji „kup podobny wygląd” w centrali Commerce, opcja w narzędziu do tworzenia witryn Commerce umożliwia sprzedawcom detalicznym dodanie przycisku **Kup podobne** do pola zakupu na dowolnej stronie szczegółów produktu (PDP).</span><span class="sxs-lookup"><span data-stu-id="7a72f-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="7a72f-139">Klient, który wybierze ten przycisk, zostaje przeniesiony na specjalną stronę „Kup podobne produkty”, która zwraca wizualnie podobne produkty.</span><span class="sxs-lookup"><span data-stu-id="7a72f-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="7a72f-140">W tym celu odbiorca może wykorzystać selektory do dalszego filtrowania produktów.</span><span class="sxs-lookup"><span data-stu-id="7a72f-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="7a72f-141">Aby dodać przycisk **Kup podobne** do stron PDP za pomocą narzędzia do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7a72f-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="7a72f-142">Otwórz istniejącą stronę konstruktora witryn zawierającą moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="7a72f-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="7a72f-143">W okienku nawigacji po lewej stronie zaznacz moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="7a72f-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="7a72f-144">W prawym okienku nawigacji zaznacz pole wyboru **Włącz łącze zakup podobne**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="7a72f-145">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="7a72f-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="7a72f-146">Po opublikowaniu strony PDP będzie zawierała przycisk **Kup podobne**.</span><span class="sxs-lookup"><span data-stu-id="7a72f-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="7a72f-147">Na poniższej ilustracji przedstawiono pole wyboru **Włącz łącze zakup podobne** i **Kup podobne** na przykładowej PDP w konstruktorze witryn.</span><span class="sxs-lookup"><span data-stu-id="7a72f-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Włącz pole wyboru Kupuj podobne i przycisk Kupuj podobne na PDP w narzędziu do tworzenia witryn](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="7a72f-149">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7a72f-149">Additional resources</span></span>

[<span data-ttu-id="7a72f-150">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="7a72f-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="7a72f-151">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7a72f-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="7a72f-152">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="7a72f-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="7a72f-153">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="7a72f-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="7a72f-154">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7a72f-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="7a72f-155">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="7a72f-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="7a72f-156">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="7a72f-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="7a72f-157">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="7a72f-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="7a72f-158">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="7a72f-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="7a72f-159">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="7a72f-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
