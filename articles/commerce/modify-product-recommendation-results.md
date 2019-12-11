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
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770077"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="69fc9-103">Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML</span><span class="sxs-lookup"><span data-stu-id="69fc9-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="69fc9-104">W tym temacie wyjaśniono sposób dostosowywania wyników propozycji produktów na podstawie sztucznej inteligencji dotyczącej wywiadu (AI-ML) w firmie.</span><span class="sxs-lookup"><span data-stu-id="69fc9-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="69fc9-105">Po włączeniu zaleceń dotyczących produktu ustawienia domyślne zaczną obowiązywać; te parametry mogą działać dla wielu potrzeb.</span><span class="sxs-lookup"><span data-stu-id="69fc9-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="69fc9-106">Najlepiej zaplanować poświęcenie pewnego czasu oceny, czy wyniki są zgodne ze sprzedażą produktów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="69fc9-107">Sugerujemy ocenę wyników przez kilka dni przed zmianą parametrów w razie potrzeby przed ponownym rozpoczęciem testowania.</span><span class="sxs-lookup"><span data-stu-id="69fc9-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="69fc9-108">Zrozumienie parametrów listy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="69fc9-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="69fc9-109">Przed zmianą parametrów Dowiedz się, jak będą one wpływać na wyniki poniżej.</span><span class="sxs-lookup"><span data-stu-id="69fc9-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="69fc9-110">Lista produktów w trendach</span><span class="sxs-lookup"><span data-stu-id="69fc9-110">Trending product list</span></span>

<span data-ttu-id="69fc9-111">Lista produktów **Trendy** ma dwa parametry, które można zmienić: ![Przykład domyślnych parametrów listy trendów](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="69fc9-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="69fc9-112">**Uwzględnij nowe produkty z ostatnich X dni** — produkty dodane w ciągu określonej liczby dni przed bieżącą datą można użyć do wybrania kandydatów produktów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="69fc9-113">Wartość domyślna na obrazie sugeruje, że produkty starsze niż 180 dni mogą być używane na liście produktów trendu.</span><span class="sxs-lookup"><span data-stu-id="69fc9-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="69fc9-114">**Obejmuje sprzedaż z ostatnich X dni** - Transakcje sprzedaży, które miały miejsce w ciągu określonej liczby dni przed bieżącą datą, można wykorzystać do zamówienia produktów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="69fc9-115">Wartość domyślna powyżej sugeruje, że wszystkie zakupy produktu w ciągu ostatnich 30 dni zostałyby użyte w celu ustalenia położenia produktu na liście produktów trendu.</span><span class="sxs-lookup"><span data-stu-id="69fc9-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="69fc9-116">Lista bestsellerów</span><span class="sxs-lookup"><span data-stu-id="69fc9-116">Best selling product list</span></span>

<span data-ttu-id="69fc9-117">W zależności od prowadzonej działalności bestsellery mogą mieć różne wyniki niż trendy, nawet jeśli używają one danych transakcji do zamawiania produktów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="69fc9-118">Ponieważ lista bestsellerów nie ma odcięcia na podstawie daty asortymentu, bestsellery nadal mogą być wyróżnione jako bardzo popularne, starsze produkty, które mogły zostać usunięte z listy trendów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="69fc9-119">Lista **bestsellery** zawiera jeden parametr, który można zmienić:</span><span class="sxs-lookup"><span data-stu-id="69fc9-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Przykładowy domyślny parametr listy bestsellerów](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="69fc9-121">**Obejmuje sprzedaż z ostatnich X dni** - Transakcje sprzedaży, które miały miejsce w ciągu określonej liczby dni przed bieżącą datą, można wykorzystać do zamówienia produktów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="69fc9-122">Wartość domyślna powyżej sugeruje, że wszystkie zakupy produktu w ciągu ostatnich 30 dni zostałyby użyte w celu ustalenia położenia produktu na liście produktów bestsellerów.</span><span class="sxs-lookup"><span data-stu-id="69fc9-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="69fc9-123">Ręczne dodawanie lub usuwanie produktów z list rekomendacji</span><span class="sxs-lookup"><span data-stu-id="69fc9-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="69fc9-124">W przypadku nowości, trendów lub bestsellerów</span><span class="sxs-lookup"><span data-stu-id="69fc9-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="69fc9-125">Przejdź do **Retail** > **Rekomendacje produktów** > **Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="69fc9-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="69fc9-126">Na liście udostępnionych parametrów sieci sprzedaży wybierz **listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="69fc9-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="69fc9-127">Wybierz listę dodaj lub usuń produkty.</span><span class="sxs-lookup"><span data-stu-id="69fc9-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="69fc9-128">Aby dodać produkty do tabeli, wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="69fc9-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="69fc9-129">W kolumnie produkt wyszukaj produkt według jego **nazwy** lub **numeru produktu.**
![Przykład wyszukiwania produktu na nowej liście produktów](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="69fc9-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="69fc9-130">W kolumnie Typ wiersza wybierz jedną z dwóch opcji:</span><span class="sxs-lookup"><span data-stu-id="69fc9-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="69fc9-131">**Uwzględnij** — wymusza wymuszenie produktu z przodu listy</span><span class="sxs-lookup"><span data-stu-id="69fc9-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="69fc9-132">**Wyklucz** — usuwa produkt z listy w ![przykładzie zawierającym lub wykluczającym produkt z nowej listy produktów](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="69fc9-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="69fc9-133">Zmiana **kolejności wyświetlania** zmieni kolejność, gdy produkty oznaczone jako **uwzględnione** zostaną wyświetlone na liście.</span><span class="sxs-lookup"><span data-stu-id="69fc9-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="69fc9-134">Jeśli dwa produkty mają taką samą wartość **kolejności wyświetlania**, ostateczna kolejność tych dwóch wyników może się różnić od biura zaplecza.</span><span class="sxs-lookup"><span data-stu-id="69fc9-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="69fc9-135">Aby usunąć produkty z tabeli: zaznacz wiersz do usunięcia i wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="69fc9-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="69fc9-136">Dla osób podobnych lub często kupowanych list</span><span class="sxs-lookup"><span data-stu-id="69fc9-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="69fc9-137">W kontekście list **Często kupowane razemr** lub **Klientom podoba się również**, uczenie maszynowe służy do analizy wzorców zakupów konsumenckich w celu rekomendowania powiązanych produktów, które są wspólnie kupowane dla unikalnego produktu początkowego.</span><span class="sxs-lookup"><span data-stu-id="69fc9-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="69fc9-138">**Produkt początkowy** to produkt, dla którego mają być generowane wyniki.</span><span class="sxs-lookup"><span data-stu-id="69fc9-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="69fc9-139">W kontekście ręcznego dostosowywania list rekomendacji są dodawane lub usuwane wyniki dla tego produktu.</span><span class="sxs-lookup"><span data-stu-id="69fc9-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="69fc9-140">Aby ręcznie dodać lub usunąć wyniki dla produktu początkowego, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="69fc9-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="69fc9-141">Wybierz **Produkt początkowy**.</span><span class="sxs-lookup"><span data-stu-id="69fc9-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="69fc9-142">W kolumnie **produkt** wyszukaj produkt według jego **nazwy** lub **numeru produktu.**
![Przykład wyszukiwania produktu na nowej liście produktów najczęściej kupowanych razem](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="69fc9-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="69fc9-143">W kolumnie **Typ wiersza** wybierz jedną z dwóch opcji:</span><span class="sxs-lookup"><span data-stu-id="69fc9-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="69fc9-144">**Uwzględnij** — wymusza wymuszenie produktu z przodu listy</span><span class="sxs-lookup"><span data-stu-id="69fc9-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="69fc9-145">**Wyklucz** — usuwa produkt z listy</span><span class="sxs-lookup"><span data-stu-id="69fc9-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="69fc9-146">![Przykład uwzględniania lub wyłączania produktu na liście produktów najczęściej kupowanych razem](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="69fc9-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="69fc9-147">Aby usunąć produkty z tabeli: zaznacz wiersz do usunięcia i wybierz opcję Usuń.</span><span class="sxs-lookup"><span data-stu-id="69fc9-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="69fc9-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="69fc9-148">Additional resources</span></span>

[<span data-ttu-id="69fc9-149">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="69fc9-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="69fc9-150">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="69fc9-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="69fc9-151">Dodawanie list rekomendacji produktów do stron</span><span class="sxs-lookup"><span data-stu-id="69fc9-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
