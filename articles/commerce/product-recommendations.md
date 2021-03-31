---
title: Omówienie rekomendacji produktów
description: Ten temat zawiera ogólne informacje o rekomendacjach produktu. Rekomendacje produktów umożliwiają łatwe i szybkie znajdowanie produktów, które są potrzebne, a nawet produktów, których klient nie zamierzał pierwotnie kupić.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb64cd05ac8580c3ddcd719d62544f1edbdbef0b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231039"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="cf637-104">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="cf637-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cf637-105">Microsoft Dynamics 365 Commerce może posłużyć do pokazywania zaleceń dotyczących produktów w witrynie e-Commerce i urządzeniach punktu sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="cf637-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="cf637-106">Rekomendacje produktów to przedmioty, które mogą być interesujące dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="cf637-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="cf637-107">Rekomendacje są oparte na trendach zakupu innych odbiorców w sklepach internetowych oraz w sklepach tradycyjnych.</span><span class="sxs-lookup"><span data-stu-id="cf637-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="cf637-108">Zalecenia dotyczące produktów pozwalają klientom łatwo i szybko znaleźć produkty, których chcą, mając doświadczenie, które im dobrze służy.</span><span class="sxs-lookup"><span data-stu-id="cf637-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="cf637-109">Można nawet użyć sprzedaży powiązanej i oferowanie droższego produktu, aby pomóc klientom znalezienie dodatkowych produktów niż pierwotnie zamierzone.</span><span class="sxs-lookup"><span data-stu-id="cf637-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="cf637-110">Kiedy rekomendacje są pomocne w odkrywaniu produktów, mogą stworzyć więcej możliwości konwersji, pomóc zwiększyć przychody ze sprzedaży, a nawet pomóc zwiększyć satysfakcję i utrzymanie klientów.</span><span class="sxs-lookup"><span data-stu-id="cf637-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="cf637-111">W handlu elektronicznym rekomendacje produktów są oparte na technologiach uczenia maszynowego rekomendacji Microsoft na dużą skalę.</span><span class="sxs-lookup"><span data-stu-id="cf637-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="cf637-112">Usługa rekomendacji</span><span class="sxs-lookup"><span data-stu-id="cf637-112">Recommendation service</span></span>

<span data-ttu-id="cf637-113">Usługa rekomendacji produktów korzysta z sztucznych technologii wywiadu i nauki maszyn (AI) w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="cf637-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="cf637-114">Dane w formacie wymaganym przez usługę rekomendacji są pobierane z operacyjnej bazy danych Commerce i wysyłane do Azure Data Lake Storage lub magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="cf637-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure Data Lake Storage or Entity store.</span></span>
- <span data-ttu-id="cf637-115">Usługa rekomendacji korzysta z przechowywanych danych w celu wytrenowania modeli rekomendacji dla list **Klientom podoba się również**, **Często kupowane razem**, **Nowości**, **Bestsellery** i **Trendy**.</span><span class="sxs-lookup"><span data-stu-id="cf637-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="cf637-116">Scenariusze</span><span class="sxs-lookup"><span data-stu-id="cf637-116">Scenarios</span></span>

<span data-ttu-id="cf637-117">Rekomendacje produktów są dostępne w opisanych niżej scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="cf637-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="cf637-118">**Na dowolnej stronie sklepu lub stronie magazynowej w e-Commerce:** Jeśli klient lub sprzedawca odwiedza stronę sklepu, aparat rekomendacji może sugerować produkty na listach **Nowości**, **Bestsellery** i **Trendy**.</span><span class="sxs-lookup"><span data-stu-id="cf637-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="cf637-119">**Na stronie Szczegóły produktu:** Jeśli klienci lub sprzedawcy odwiedzają stronę **Szczegóły produktu**, aparat rekomendacji sugeruje dodatkowe towary, które również prawdopodobnie zostaną nabyte.</span><span class="sxs-lookup"><span data-stu-id="cf637-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="cf637-120">Pozycje te pojawiają się również na liście osoby **Klientom podoba się również**.</span><span class="sxs-lookup"><span data-stu-id="cf637-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="cf637-121">**Na stronie transakcja lub stronie realizacja transakcji:** aparat rekomendacji sugeruje pozycje na podstawie całej listy towarów w koszyku.</span><span class="sxs-lookup"><span data-stu-id="cf637-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="cf637-122">Te pozycje są wyświetlane na liście **Często kupowane razem**.</span><span class="sxs-lookup"><span data-stu-id="cf637-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="cf637-123">**Spersonalizowane rekomendacje:** Sprzedacy mogą dostarczać zalogowanym odbiorcom listę **Wybrane dla Ciebie** w dodatku do nowych funkcji, które pozwalają na spersonalizowanie istniejących scenariuszy list na podstawie tego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="cf637-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="cf637-124">Aby dowiedzieć się więcej, patrz [Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="cf637-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="cf637-125">Typy rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="cf637-125">Types of product recommendations</span></span>

<span data-ttu-id="cf637-126">W poniższej tabeli opisano różne typy automatycznych rekomendacji dotyczących produktów dostępnych dla detalistów, które można zaimplementować w rozwiązaniu Dynamics 365 Commerce za pośrednictwem [modułu zbierania produktów](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cf637-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="cf637-127">Detaliści mogą także wyświetlać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję.</span><span class="sxs-lookup"><span data-stu-id="cf637-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="cf637-128">Moduł kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="cf637-128">Product collection module</span></span>  | <span data-ttu-id="cf637-129">Typ</span><span class="sxs-lookup"><span data-stu-id="cf637-129">Type</span></span> | <span data-ttu-id="cf637-130">opis</span><span class="sxs-lookup"><span data-stu-id="cf637-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="cf637-131">Nowy element</span><span class="sxs-lookup"><span data-stu-id="cf637-131">New</span></span>                        | <span data-ttu-id="cf637-132">Algorytmy</span><span class="sxs-lookup"><span data-stu-id="cf637-132">Algorithmic</span></span> | <span data-ttu-id="cf637-133">Ten moduł pokazuje listę najnowszych produktów w najnowszych asortymentach do kanałów i katalogów.</span><span class="sxs-lookup"><span data-stu-id="cf637-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="cf637-134">Bestsellery</span><span class="sxs-lookup"><span data-stu-id="cf637-134">Best selling</span></span>               | <span data-ttu-id="cf637-135">Algorytmy</span><span class="sxs-lookup"><span data-stu-id="cf637-135">Algorithmic</span></span> | <span data-ttu-id="cf637-136">Ten moduł pokazuje listę produktów sklasyfikowanych według najwyższej liczby sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cf637-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="cf637-137">Popularne</span><span class="sxs-lookup"><span data-stu-id="cf637-137">Trending</span></span>                   | <span data-ttu-id="cf637-138">Algorytmy</span><span class="sxs-lookup"><span data-stu-id="cf637-138">Algorithmic</span></span> | <span data-ttu-id="cf637-139">Ten moduł listę produktów najwyższej wydajności w danym okresie, sklasyfikowanych według najwyższej liczby sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cf637-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="cf637-140">Często kupowane razem</span><span class="sxs-lookup"><span data-stu-id="cf637-140">Frequently bought together</span></span> | <span data-ttu-id="cf637-141">AI-ML</span><span class="sxs-lookup"><span data-stu-id="cf637-141">AI-ML</span></span> | <span data-ttu-id="cf637-142">W tym module zaleca listę produktów, które są często kupowane razem z zawartością bieżącego koszyka konsumentów.</span><span class="sxs-lookup"><span data-stu-id="cf637-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="cf637-143">Klienci także lubią</span><span class="sxs-lookup"><span data-stu-id="cf637-143">People also like</span></span>           | <span data-ttu-id="cf637-144">AI-ML</span><span class="sxs-lookup"><span data-stu-id="cf637-144">AI-ML</span></span> | <span data-ttu-id="cf637-145">Ten moduł zaleca produkty dla danego inicjatora na podstawie wzorców zakupów odbiorców.</span><span class="sxs-lookup"><span data-stu-id="cf637-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="cf637-146">Wybrane dla Ciebie</span><span class="sxs-lookup"><span data-stu-id="cf637-146">Picks for you</span></span>              | <span data-ttu-id="cf637-147">AI-ML</span><span class="sxs-lookup"><span data-stu-id="cf637-147">AI-ML</span></span> | <span data-ttu-id="cf637-148">Ten moduł zaleca spersonalizowaną listę produktów na podstawie wzorców zakupów zalogowanego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="cf637-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="cf637-149">W przypadku użytkownika gościa ta lista zostanie zwinięta.</span><span class="sxs-lookup"><span data-stu-id="cf637-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="cf637-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cf637-150">Additional resources</span></span>

[<span data-ttu-id="cf637-151">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cf637-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="cf637-152">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="cf637-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="cf637-153">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="cf637-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="cf637-154">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="cf637-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="cf637-155">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="cf637-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="cf637-156">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="cf637-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="cf637-157">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="cf637-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="cf637-158">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="cf637-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="cf637-159">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="cf637-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="cf637-160">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="cf637-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="cf637-161">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="cf637-161">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]