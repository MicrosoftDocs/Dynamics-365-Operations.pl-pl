---
title: Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML
description: W tym temacie wyjaśniono sposób dostosowywania wyników propozycji produktów na podstawie sztucznej inteligencji dotyczącej wywiadu (AI-ML) w firmie.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5da77f71fb2569adc011bb9ee9c8c795d85545f8
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025009"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="30859-103">Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML</span><span class="sxs-lookup"><span data-stu-id="30859-103">Manage AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="30859-104">W tym temacie wyjaśniono sposób dostosowywania wyników propozycji produktów na podstawie sztucznej inteligencji dotyczącej wywiadu (AI-ML) w firmie.</span><span class="sxs-lookup"><span data-stu-id="30859-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="30859-105">Po włączeniu zaleceń dotyczących produktu ustawienia domyślne zaczną obowiązywać; te parametry mogą działać dla wielu potrzeb.</span><span class="sxs-lookup"><span data-stu-id="30859-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="30859-106">Najlepiej zaplanować poświęcenie pewnego czasu oceny, czy wyniki są zgodne ze sprzedażą produktów.</span><span class="sxs-lookup"><span data-stu-id="30859-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="30859-107">Sugerujemy ocenę wyników przez kilka dni przed zmianą parametrów w razie potrzeby przed ponownym rozpoczęciem testowania.</span><span class="sxs-lookup"><span data-stu-id="30859-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="30859-108">Zrozumienie parametrów listy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="30859-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="30859-109">Przed zmianą parametrów Dowiedz się, jak będą one wpływać na wyniki poniżej.</span><span class="sxs-lookup"><span data-stu-id="30859-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="30859-110">Lista „popularnych” produktów</span><span class="sxs-lookup"><span data-stu-id="30859-110">"Trending" product list</span></span>

<span data-ttu-id="30859-111">Lista „popularnych” produktów zawiera dwa parametry, który można zmienić:</span><span class="sxs-lookup"><span data-stu-id="30859-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Przykładowy domyślny parametr listy „popularnych” produktów](./media/exampletrendingparameters.png)

1. <span data-ttu-id="30859-113">**Uwzględnij nowe produkty z ostatnich X dni** — produkty dodane w ciągu określonej liczby dni przed bieżącą datą można użyć do wybrania kandydatów produktów.</span><span class="sxs-lookup"><span data-stu-id="30859-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="30859-114">Wartość domyślna na obrazie sugeruje, że produkty starsze niż 180 dni mogą być używane na liście produktów trendu.</span><span class="sxs-lookup"><span data-stu-id="30859-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="30859-115">**Obejmuje sprzedaż z ostatnich X dni** - Transakcje sprzedaży, które miały miejsce w ciągu określonej liczby dni przed bieżącą datą, można wykorzystać do zamówienia produktów.</span><span class="sxs-lookup"><span data-stu-id="30859-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="30859-116">Wartość domyślna powyżej sugeruje, że wszystkie zakupy produktu w ciągu ostatnich 30 dni zostałyby użyte w celu ustalenia położenia produktu na liście produktów trendu.</span><span class="sxs-lookup"><span data-stu-id="30859-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="30859-117">Lista „bestsellerów”</span><span class="sxs-lookup"><span data-stu-id="30859-117">"Best selling" product list</span></span>

<span data-ttu-id="30859-118">W zależności od prowadzonej działalności „bestsellery” mogą mieć różne wyniki niż trendy, nawet jeśli używają one danych transakcji do zamawiania produktów.</span><span class="sxs-lookup"><span data-stu-id="30859-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="30859-119">Ponieważ lista bestsellerów nie ma odcięcia na podstawie daty asortymentu, bestsellery nadal mogą być wyróżnione jako bardzo popularne, starsze produkty, które mogły zostać usunięte z listy trendów.</span><span class="sxs-lookup"><span data-stu-id="30859-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="30859-120">Lista „bestsellery” zawiera jeden parametr, który można zmienić:</span><span class="sxs-lookup"><span data-stu-id="30859-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Przykładowy domyślny parametr listy bestsellerów](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="30859-122">**Obejmuje sprzedaż z ostatnich X dni** - Transakcje sprzedaży, które miały miejsce w ciągu określonej liczby dni przed bieżącą datą, można wykorzystać do zamówienia produktów.</span><span class="sxs-lookup"><span data-stu-id="30859-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="30859-123">Wartość domyślna powyżej sugeruje, że wszystkie zakupy produktu w ciągu ostatnich 30 dni zostałyby użyte w celu ustalenia położenia produktu na liście produktów bestsellerów.</span><span class="sxs-lookup"><span data-stu-id="30859-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="30859-124">Ręczne dodawanie lub usuwanie produktów z list rekomendacji</span><span class="sxs-lookup"><span data-stu-id="30859-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="30859-125">W przypadku list „nowości”, „trendów” lub „bestsellerów”</span><span class="sxs-lookup"><span data-stu-id="30859-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="30859-126">Przejdź do **Handel detaliczny i komercyjny** > **Rekomendacje produktów** > **Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="30859-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="30859-127">Na liście udostępnionych parametrów sieci sprzedaży wybierz **listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="30859-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="30859-128">Wybierz listę dodaj lub usuń produkty.</span><span class="sxs-lookup"><span data-stu-id="30859-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="30859-129">Aby dodać produkty do tabeli, wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="30859-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="30859-130">W kolumnie produkt Wyszukaj produkt według jego **nazwy** lub **numeru produktu**.</span><span class="sxs-lookup"><span data-stu-id="30859-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Przykład wyszukiwania produktu na liście nowych produktów](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="30859-132">W kolumnie Typ wiersza wybierz jedną z dwóch opcji:</span><span class="sxs-lookup"><span data-stu-id="30859-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="30859-133">**Uwzględnij** — wymusza wymuszenie produktu z przodu listy</span><span class="sxs-lookup"><span data-stu-id="30859-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="30859-134">**Wyklucz** — usuwa produkt z listy</span><span class="sxs-lookup"><span data-stu-id="30859-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Przykład uwzględniania lub wykluczania produktu z listy nowych produktów](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="30859-136">Zmiana **kolejności wyświetlania** zmieni kolejność, gdy produkty oznaczone jako **uwzględnione** zostaną wyświetlone na liście.</span><span class="sxs-lookup"><span data-stu-id="30859-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="30859-137">Jeśli dwa produkty mają taką samą wartość **kolejności wyświetlania**, ostateczna kolejność tych dwóch wyników może się różnić od biura zaplecza.</span><span class="sxs-lookup"><span data-stu-id="30859-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="30859-138">Aby usunąć produkty z tabeli: zaznacz wiersz do usunięcia i wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="30859-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="30859-139">Dla list „Inni często lubią” lub „często kupowane razem”</span><span class="sxs-lookup"><span data-stu-id="30859-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="30859-140">W kontekście list „Często kupowane razem” lub „Klientom podoba się również”, uczenie maszynowe służy do analizy wzorców zakupów konsumenckich w celu rekomendowania powiązanych produktów, które są wspólnie kupowane dla unikalnego produktu początkowego.</span><span class="sxs-lookup"><span data-stu-id="30859-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="30859-141">*Produkt początkowy* to produkt, dla którego mają być generowane wyniki.</span><span class="sxs-lookup"><span data-stu-id="30859-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="30859-142">W kontekście ręcznego dostosowywania list rekomendacji są dodawane lub usuwane wyniki dla tego produktu.</span><span class="sxs-lookup"><span data-stu-id="30859-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="30859-143">Aby ręcznie dodać lub usunąć wyniki dla produktu początkowego, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="30859-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="30859-144">Wybierz **Produkt początkowy**.</span><span class="sxs-lookup"><span data-stu-id="30859-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="30859-145">W kolumnie **produkt** wyszukaj produkt według jego **nazwy** lub **numeru produktu.**
![Przykład wyszukiwania produktu na nowej liście produktów najczęściej kupowanych razem](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="30859-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="30859-146">W kolumnie **Typ wiersza** wybierz jedną z dwóch opcji:</span><span class="sxs-lookup"><span data-stu-id="30859-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="30859-147">**Uwzględnij** — wymusza wymuszenie produktu z przodu listy</span><span class="sxs-lookup"><span data-stu-id="30859-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="30859-148">**Wyklucz** — usuwa produkt z listy</span><span class="sxs-lookup"><span data-stu-id="30859-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="30859-149">![Przykład uwzględniania lub wyłączania produktu na liście produktów najczęściej kupowanych razem](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="30859-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="30859-150">Aby usunąć produkty z tabeli: zaznacz wiersz do usunięcia i wybierz opcję Usuń.</span><span class="sxs-lookup"><span data-stu-id="30859-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="30859-151">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="30859-151">Additional resources</span></span>

[<span data-ttu-id="30859-152">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="30859-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="30859-153">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="30859-153">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="30859-154">Włącz spersonalizowane rekomendacje</span><span class="sxs-lookup"><span data-stu-id="30859-154">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="30859-155">Dodawanie list rekomendacji produktów do stron</span><span class="sxs-lookup"><span data-stu-id="30859-155">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="30859-156">Omówienie modułu kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="30859-156">Product collection module overview</span></span>](product-collection-module-overview.md)
