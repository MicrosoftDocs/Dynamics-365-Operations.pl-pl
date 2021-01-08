---
title: Tworzenie rekomendacji z danymi demonstracyjnymi
description: Niniejszy temat przedstawia wskazówki dotyczące sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cca6913375eec2565852676f3c1da5a67f71e14f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414813"
---
# <a name="create-recommendations-with-demo-data"></a><span data-ttu-id="3237f-103">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="3237f-103">Create recommendations with demo data</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3237f-104">Niniejszy temat przedstawia wskazówki dotyczące sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="3237f-104">This topic provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="3237f-105">Wielokanałowe rekomendacje produktów zapewniają zestaw opracowanych edytorsko lub generowanych programowo list produktów.</span><span class="sxs-lookup"><span data-stu-id="3237f-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="3237f-106">Listy te mogą być używane w kilku scenariuszach, w zależności od potrzeb biznesowych.</span><span class="sxs-lookup"><span data-stu-id="3237f-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="3237f-107">Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="3237f-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="3237f-108">Zalecenia dotyczące środowisk Dynamics 365 warstwy 2 i wyższych są obliczane automatycznie na podstawie danych klientów.</span><span class="sxs-lookup"><span data-stu-id="3237f-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="3237f-109">Korzystanie z pokazów dotyczących produktów dane demonstracyjne nie wyłączają żadnych zaleceń dotyczących produktów już zainicjowanych w środowisku oraz wszelkich kosztów związanych z jego użytkowaniem.</span><span class="sxs-lookup"><span data-stu-id="3237f-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="3237f-110">Zalecenia dotyczące produktów w warstwie 1 dotyczą wyłącznie statycznych danych demonstracyjnych przechowywanych w pliku .csv.</span><span class="sxs-lookup"><span data-stu-id="3237f-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="3237f-111">Włączanie demonstracyjnych danych na temat produktów w środowisku</span><span class="sxs-lookup"><span data-stu-id="3237f-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="3237f-112">Aby włączyć dane demonstracyjne rekomendacji produktu, użytkownicy muszą wdrożyć Rozszerzenie Dynamics 365 Commerce w wersji podglądu w odpowiednim środowisku.</span><span class="sxs-lookup"><span data-stu-id="3237f-112">To enable product recommendations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="3237f-113">Takie rozwiązanie automatycznie włącza dane demonstracyjne rekomendacji produktu.</span><span class="sxs-lookup"><span data-stu-id="3237f-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="3237f-114">Użyj domyślnych danych demonstracyjnych</span><span class="sxs-lookup"><span data-stu-id="3237f-114">Default demo data</span></span>
<span data-ttu-id="3237f-115">Każde środowisko typu OneBox zawiera wstępnie załadowany zbiór danych demonstracyjnych rekomendacji dotyczących produktów przechowywanych w pliku rozdzielonym przecinkami „reco_demo_data. csv" znajdującego się w Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="3237f-115">Each OneBox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated 'reco_demo_data.csv' file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="3237f-116">Dane te są uporządkowane według następujących kolumn.</span><span class="sxs-lookup"><span data-stu-id="3237f-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="3237f-117">Nazwa kolumny</span><span class="sxs-lookup"><span data-stu-id="3237f-117">Column name</span></span>         | <span data-ttu-id="3237f-118">Wymagany</span><span class="sxs-lookup"><span data-stu-id="3237f-118">Mandatory</span></span>          | <span data-ttu-id="3237f-119">opis</span><span class="sxs-lookup"><span data-stu-id="3237f-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="3237f-120">Możliwe wartości</span><span class="sxs-lookup"><span data-stu-id="3237f-120">Possible values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="3237f-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="3237f-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="3237f-123">Określony typ listy rekomendacji produktu, który ma zostać wygenerowany dla punktu danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="3237f-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="3237f-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="3237f-124">RecoBestSelling</span></span></li><li><span data-ttu-id="3237f-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="3237f-125">RecoNew</span></span></li><li><span data-ttu-id="3237f-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="3237f-126">RecoTrending</span></span></li><li><span data-ttu-id="3237f-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="3237f-127">RecoCart</span></span></li><li><span data-ttu-id="3237f-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="3237f-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="3237f-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="3237f-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="3237f-131">Numer konkretnej jednostki operacyjnej, w której oczekiwane są rekomendacje produktów.</span><span class="sxs-lookup"><span data-stu-id="3237f-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="3237f-132">Kategoria</span><span class="sxs-lookup"><span data-stu-id="3237f-132">Category</span></span>            |                    |    <span data-ttu-id="3237f-133">Kategoria, dla której należy zwrócić określoną listę.</span><span class="sxs-lookup"><span data-stu-id="3237f-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="3237f-134">Jeśli nie określono żadnej kategorii, lista jest tylko dla górnej hierarchii nawigacji.</span><span class="sxs-lookup"><span data-stu-id="3237f-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="3237f-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="3237f-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="3237f-136">W przypadku list, które wymagają użycia materiału siewnego (RecoPeopleAlsoBuy i RecoCart), produkt zawierający te listy powinien zawierać dodatkowe produkty.</span><span class="sxs-lookup"><span data-stu-id="3237f-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="3237f-137">CustomerId</span><span class="sxs-lookup"><span data-stu-id="3237f-137">CustomerId</span></span>          |                    |    <span data-ttu-id="3237f-138">Dla list, które wymagają identyfikatora odbiorcy (RecoPicks).</span><span class="sxs-lookup"><span data-stu-id="3237f-138">For lists that require a customer identifier (RecoPicks).</span></span>  <span data-ttu-id="3237f-139">Wartość domyślna „0” dotyczy wszystkich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="3237f-139">The default value '0' applies to all customers.</span></span>          |                                                                              |
| <span data-ttu-id="3237f-140">ItemIds</span><span class="sxs-lookup"><span data-stu-id="3237f-140">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="3237f-142">Jeden lub więcej produktów zwracanych w wyniku, oddzielonych przez ”;”.</span><span class="sxs-lookup"><span data-stu-id="3237f-142">One or more products to be returned as the result, separated by ';'.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="3237f-143">Dostosuj dane demonstracyjne</span><span class="sxs-lookup"><span data-stu-id="3237f-143">Customize demo data</span></span>
<span data-ttu-id="3237f-144">Użytkownicy mogą edytować domyślne dane demonstracyjne z dowolnymi informacjami dotyczącymi produktów i kategorii skonfigurowanymi w HQ.</span><span class="sxs-lookup"><span data-stu-id="3237f-144">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="3237f-145">Po zaktualizowaniu pliku CSV zwrócone rekomendacje produktu będą natychmiast odzwierciedlane w tych zmianach.</span><span class="sxs-lookup"><span data-stu-id="3237f-145">After you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="3237f-146">Rozszerzenie zawiera plik danych o nazwie „RecoMockDataset.csv”, który zezwala użytkownikowi na kontrolowanie zestawu danych używanego do wyłączania wyników rekomendacji przykładowych.</span><span class="sxs-lookup"><span data-stu-id="3237f-146">The extension contains a datafile called 'RecoMockDataset.csv', which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="3237f-147">Nazwa pliku może być kontrolowana za pośrednictwem konfiguracji rozszerzeń za pomocą ustawienia **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="3237f-147">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="3237f-148">Dzięki temu użytkownik może mieć dostęp do wielu zestawów danych, które można łatwo przełączać w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="3237f-148">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="3237f-149">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3237f-149">Additional resources</span></span>

[<span data-ttu-id="3237f-150">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="3237f-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="3237f-151">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3237f-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="3237f-152">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="3237f-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="3237f-153">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="3237f-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="3237f-154">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="3237f-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="3237f-155">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="3237f-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="3237f-156">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3237f-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="3237f-157">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="3237f-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="3237f-158">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="3237f-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="3237f-159">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="3237f-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="3237f-160">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="3237f-160">Product recommendations FAQ</span></span>](faq-recommendations.md)
