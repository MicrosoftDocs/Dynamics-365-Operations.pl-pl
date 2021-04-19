---
title: Rekomendacje produktów — często zadawane pytania
description: Ten temat zawiera informacje o procesach i narzędziach, których można wykorzystywać do rozwiązywania problemów związanych z zaleceniami dotyczącymi produktów lub ich wynikami.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fa845f4d41e0bd7725349a216b9e4ee79efee79d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792422"
---
# <a name="product-recommendations-faq"></a><span data-ttu-id="456ae-103">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="456ae-103">Product recommendations FAQ</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="456ae-104">Ten temat zawiera informacje o procesach i narzędziach, których można wykorzystywać do rozwiązywania problemów związanych z [rekomendacjami produktów](product-recommendations.md) lub ich wynikami.</span><span class="sxs-lookup"><span data-stu-id="456ae-104">This topic provides information about processes and tools that you can use to troubleshoot issues that are related to [product recommendations](product-recommendations.md) or their results.</span></span>

## <a name="best-practices"></a><span data-ttu-id="456ae-105">Najlepsze praktyki</span><span class="sxs-lookup"><span data-stu-id="456ae-105">Best practices</span></span>
<span data-ttu-id="456ae-106">Bardzo ważne jest wykorzystanie pojęcia produktów głównych i wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="456ae-106">It's very important to utilize the concept of product masters and variants.</span></span> <span data-ttu-id="456ae-107">Rozsądne grupowanie wariantów dla nadrzędnego produktu głównego pomaga algorytmom list i usłudze w tworzeniu lepszych modeli.</span><span class="sxs-lookup"><span data-stu-id="456ae-107">The sensible grouping of variants to a parent product master helps the list algorithms and service create better models.</span></span> <span data-ttu-id="456ae-108">Ponadto usługa może obsługiwać tylko jedno wystąpienie produktu, a nie wszystkie ściśle powiązane warianty z listy.</span><span class="sxs-lookup"><span data-stu-id="456ae-108">Additionally, the service can serve just one instance of a product instead of putting all closely related variants in a list.</span></span> <span data-ttu-id="456ae-109">Jeśli wszystkie ściśle powiązane warianty są umieszczone na liście, mogą wystąpić błędne lub zduplikowane wyniki.</span><span class="sxs-lookup"><span data-stu-id="456ae-109">When all closely related variants are put in a list, erroneous or duplicate results can occur.</span></span>

## <a name="why-are-products-missing-from-my-recommendation-lists"></a><span data-ttu-id="456ae-110">Dlaczego na moich listach rekomendacji nie ma produktów?</span><span class="sxs-lookup"><span data-stu-id="456ae-110">Why are products missing from my recommendation lists?</span></span>

<span data-ttu-id="456ae-111">Zazwyczaj, jeśli brakuje pozycji z listy rekomendacji produktów, może to być błąd konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="456ae-111">Typically, if an item is missing from a product recommendation list, there might be a product configuration issue.</span></span> <span data-ttu-id="456ae-112">Na przykład może to być niepoprawna data rozpoczęcia lub zakończenia produktu, wymiar może być niepoprawnie skonfigurowany lub produkt może nie znajdować się w poprawnym asortymentzie kanału itp.</span><span class="sxs-lookup"><span data-stu-id="456ae-112">For example, there might be an incorrect product start date or end date, a dimension might be misconfigured, or the product might not be in the correct channel assortment, etc.</span></span>

<span data-ttu-id="456ae-113">Jeśli brakuje pozycji z listy rekomendacji opartej na sztucznej analizie maszyn (AI-ML), pozycja może nie pasować do kryteriów listy rekomendacji lub może nie mieć wystarczającej liczby transakcji zakupu, aby wyświetlić listę rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="456ae-113">If an item is missing from a recommendation list that is based on artificial intelligence-machine learning (AI-ML), the item might not fit the criteria of the recommendation list, or it might not have enough purchase transactions for the recommendation list to show it.</span></span>

<span data-ttu-id="456ae-114">Zalecane jest sprawdzenie następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="456ae-114">We recommend that you check these steps:</span></span>
1. <span data-ttu-id="456ae-115">**Upewnij się, że włączono rekomendacje dotyczące produktu w HQ.**</span><span class="sxs-lookup"><span data-stu-id="456ae-115">**Make sure that product recommendations have been enabled in HQ.**</span></span> <span data-ttu-id="456ae-116">Aby uzyskać informacje o włączaniu tej usłudze, zobacz [Włączanie rekomendacji produktów](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-116">For more information about how to enable this service, see [Enable product recommendations](enable-product-recommendations.md).</span></span>
1. <span data-ttu-id="456ae-117">**Upewnij się, że są ustawione kluczowe właściwości produktu.**</span><span class="sxs-lookup"><span data-stu-id="456ae-117">**Make sure that key product properties are set.**</span></span> <span data-ttu-id="456ae-118">Na przykład asortymenty produktów muszą mieć wartość **Uwzględnij**.</span><span class="sxs-lookup"><span data-stu-id="456ae-118">For example, product assortments must be set to **Include**.</span></span>
1. <span data-ttu-id="456ae-119">**W przypadku nowych produktów w asortymentach może upłynąć nawet do 3 godzin, zanim produkt zostanie uruchomiony na nowej liście.**</span><span class="sxs-lookup"><span data-stu-id="456ae-119">**For newly assorted products, it might take up to 3 hours before the product will start appearing in the new list.**</span></span>
1. <span data-ttu-id="456ae-120">**Jeśli produkt nadal nie jest wyświetlany na liście trendy, bestsellery, klientom podoba się również lub często kupowane razem, może to oznaczać, że ten produkt nie ma wystarczającej liczby transakcji.**</span><span class="sxs-lookup"><span data-stu-id="456ae-120">**If a product is still not appearing in Trending, Best selling, People also like, or Frequently bought together, then that product might not have enough transactions.**</span></span> <span data-ttu-id="456ae-121">W takim przypadku można poczekać na więcej transakcji, zaktualizować domyślne parametry listy rekomendacji lub skorzystać z ręcznej interwencji w celu zmodyfikowania wyników listy produktów rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="456ae-121">In this case, you can either wait for more transactions to occur, update the default recommendation list parameters, or use manual intervention to modify the recommendation product list results.</span></span> <span data-ttu-id="456ae-122">Aby uzyskać więcej informacji o parametrach rekomendacji, zapoznaj się z tematem [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-122">For more information about recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
1. <span data-ttu-id="456ae-123">**Upewnij się, że produkt spełnia kryteria rekomendacji dla listy.**</span><span class="sxs-lookup"><span data-stu-id="456ae-123">**Make sure that the product meets the recommendation criteria for the list.**</span></span> <span data-ttu-id="456ae-124">Aby uzyskać więcej informacji o parametrach rekomendacji produktów, zapoznaj się z tematem [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-124">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a><span data-ttu-id="456ae-125">Jak można zapobiec zwracaniu złych wyników rekomendacji?</span><span class="sxs-lookup"><span data-stu-id="456ae-125">How can I prevent poor recommendation results from being returned?</span></span>

<span data-ttu-id="456ae-126">Listy rekomendacji wymagają dużej ilości transakcji do wygenerowania wyników.</span><span class="sxs-lookup"><span data-stu-id="456ae-126">Recommendation lists require a large volume of transactions to produce results.</span></span> <span data-ttu-id="456ae-127">Dlatego ważne jest, aby użytkownicy dostarczali pełne historyczne dane o transakcjach.</span><span class="sxs-lookup"><span data-stu-id="456ae-127">Therefore, it's important that users provide full historical transaction data.</span></span>

<span data-ttu-id="456ae-128">Ponadto produkty, które nie mają transakcji lub kilku transakcji zwykle nie mają **Klientom podoba się również** lub **często kupowane razem**, a nie pojawiają się na listach **Trendy** lub **Bestsellery**.</span><span class="sxs-lookup"><span data-stu-id="456ae-128">Additionally, products that have no transactions or few transactions typically don't have **People also like** or **Frequently bought together** results, and don't appear in **Trending** or **Best selling** recommendation lists.</span></span> <span data-ttu-id="456ae-129">Taka sytuacja może często występować w przypadku bardzo nowych produktów lub starych produktów, które mają małą liczbę zakupów.</span><span class="sxs-lookup"><span data-stu-id="456ae-129">This situation can often occur for very new products, or for old products that have a small number of purchases.</span></span> <span data-ttu-id="456ae-130">Popularne nowe elementy umożliwią łatwe pokonanie tego zagadnienia.</span><span class="sxs-lookup"><span data-stu-id="456ae-130">Popular new items will easily overcome this issue.</span></span>

<span data-ttu-id="456ae-131">Zalecane jest wykonanie następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="456ae-131">We recommend that you follow these steps:</span></span>
1. <span data-ttu-id="456ae-132">**Upewnij się, że produkt spełnia kryteria rekomendacji dla tej listy.**</span><span class="sxs-lookup"><span data-stu-id="456ae-132">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="456ae-133">Aby uzyskać więcej informacji o parametrach rekomendacji produktów, zapoznaj się z tematem Modyfikuj wyniki rekomendacji produktów na podstawie plików AI-ML.</span><span class="sxs-lookup"><span data-stu-id="456ae-133">For more information about product recommendation parameters, see Modify AI-ML-based product recommendation results.</span></span>
1. <span data-ttu-id="456ae-134">**Jeśli produkt jest nowy, rozważ zmodyfikowanie listy rekomendacji, dopóki produkt nie będzie już miał dalszych transakcji.**</span><span class="sxs-lookup"><span data-stu-id="456ae-134">**If the product is new, consider modifying a recommendation list until the product has more transactions.**</span></span> <span data-ttu-id="456ae-135">Aby uzyskać więcej informacji o modyfikacji wyników list rekomendacji produktów, zapoznaj się z tematem [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-135">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>


- <span data-ttu-id="456ae-136">**Upewnij się, że produkt spełnia kryteria rekomendacji dla tej listy.**</span><span class="sxs-lookup"><span data-stu-id="456ae-136">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="456ae-137">Aby uzyskać więcej informacji o parametrach rekomendacji produktów, zapoznaj się z tematem [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-137">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
- <span data-ttu-id="456ae-138">**Jeśli produkt jest nowy, rozważ zmodyfikowanie listy rekomendacji, dopóki produkt nie będzie już miał dalszych transakcji**.</span><span class="sxs-lookup"><span data-stu-id="456ae-138">**If the product is new, consider modifying a recommendation list until the product has more transactions**.</span></span> <span data-ttu-id="456ae-139">Aby uzyskać więcej informacji o modyfikacji wyników list rekomendacji produktów, zapoznaj się z tematem [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-139">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a><span data-ttu-id="456ae-140">Czy można usunąć produkt, ale nadal jest on widoczny w sklepie?</span><span class="sxs-lookup"><span data-stu-id="456ae-140">Can I remove a product but still see it in the store?</span></span>

<span data-ttu-id="456ae-141">Istnieje możliwość korygowania list algorithmically generowanych w razie potrzeby biznesowego.</span><span class="sxs-lookup"><span data-stu-id="456ae-141">You can adjust lists that are algorithmically generated if a business need arises.</span></span> <span data-ttu-id="456ae-142">Jeśli jednak produkt zostanie usunięty z listy zaleceń, produkt pozostanie wykrywalny w sklepie.</span><span class="sxs-lookup"><span data-stu-id="456ae-142">However, if a product is removed from a recommendation list, the product will remain discoverable in the store.</span></span> <span data-ttu-id="456ae-143">Aby uzyskać więcej informacji o modyfikacji wyników rekomendacji produktów, zapoznaj się z tematem [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-143">For more information about how to modify product recommendation results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

<span data-ttu-id="456ae-144">Jeśli w sklepie ma być zablokowane wykrycie towaru, należy zmienić wartość **Asortymentów towarów** na **Wykluczenie**.</span><span class="sxs-lookup"><span data-stu-id="456ae-144">If you must block an item from being discovered in the store, you must change the **Item assortments** value to **Exclude**.</span></span>

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a><span data-ttu-id="456ae-145">Jak dodać listę do strony e-Commerce?</span><span class="sxs-lookup"><span data-stu-id="456ae-145">How do I add a list to an e-Commerce page?</span></span>

<span data-ttu-id="456ae-146">Aby uzyskać informacje dotyczące sposobu dodawania stron rekomendacji produktów do witryny e-Commerce, zapoznaj się z tematem [Dodawanie list rekomendacji produktów do stron](add-reco-list-to-page.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-146">For information about how to add product recommendation pages to your e-Commerce website, see [Add product recommendation lists to pages](add-reco-list-to-page.md).</span></span>

## <a name="how-do-i-enable-recommendations-on-pos"></a><span data-ttu-id="456ae-147">Jak włączyć rekomendacje w punkcie sprzedaży?</span><span class="sxs-lookup"><span data-stu-id="456ae-147">How do I enable recommendations on POS?</span></span>

<span data-ttu-id="456ae-148">Po włączeniu zaleceń dotyczących produktu należy dodać Panel rekomendacji do ekranu kontrolki punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="456ae-148">After enabling product recommendations, you will need to add the recommendations panel to the control POS screen.</span></span> <span data-ttu-id="456ae-149">Aby uzyskać więcej informacji, patrz [Dodawanie kontrolki rekomendacji do ekranu transakcji na urządzeniach w punkcie sprzedaży](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="456ae-149">For more information, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="456ae-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="456ae-150">Additional resources</span></span>

[<span data-ttu-id="456ae-151">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="456ae-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="456ae-152">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="456ae-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="456ae-153">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="456ae-153">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="456ae-154">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="456ae-154">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="456ae-155">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="456ae-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="456ae-156">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="456ae-156">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="456ae-157">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="456ae-157">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="456ae-158">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="456ae-158">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="456ae-159">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="456ae-159">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="456ae-160">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="456ae-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="456ae-161">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="456ae-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]