---
title: Dane demonstracyjne dotyczące produktu w kanale rozproszonego
description: Niniejszy dokument ma na celu zapewnienie wskazówek dotyczących sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872333"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="31b06-103">Dane demonstracyjne dotyczące produktu w kanale rozproszonego</span><span class="sxs-lookup"><span data-stu-id="31b06-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="31b06-104">Niniejszy dokument ma na celu zapewnienie wskazówek dotyczących sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="31b06-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="31b06-105">Zalecenia dotyczące produktu w kanale rozproszonym stanowią zbiór zamówionej listy produktów z redakcją lub programowo.</span><span class="sxs-lookup"><span data-stu-id="31b06-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="31b06-106">Listy te mogą być używane w kilku scenariuszach, w zależności od potrzeb biznesowych.</span><span class="sxs-lookup"><span data-stu-id="31b06-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="31b06-107">Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [przeglądem rekomendacji produktu.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="31b06-107">For more information about product recommendation lists, see [Product recommendations overview.](../commerce/product-recommendations.md)</span></span>

<span data-ttu-id="31b06-108">Zalecenia dotyczące systemu środowiskowego warstwy 2 i większej są obliczane automatycznie na podstawie danych klientów.</span><span class="sxs-lookup"><span data-stu-id="31b06-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="31b06-109">Korzystanie z pokazów dotyczących produktów dane demonstracyjne nie wyłączają żadnych zaleceń dotyczących produktów już zainicjowanych w środowisku oraz wszelkich kosztów związanych z jego użytkowaniem.</span><span class="sxs-lookup"><span data-stu-id="31b06-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="31b06-110">Zalecenia dotyczące produktów w warstwie 1 dotyczą wyłącznie statycznych danych demonstracyjnych przechowywanych w pliku CSV.</span><span class="sxs-lookup"><span data-stu-id="31b06-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="31b06-111">Włączanie demonstracyjnych danych na temat produktów w środowisku</span><span class="sxs-lookup"><span data-stu-id="31b06-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="31b06-112">Klienci muszą wdrożyć **Rozszerzenie Dynamics 365 Commerce podglądu** w odpowiednim środowisku, które automatycznie włącza dane demonstracyjne dotyczące produktu.</span><span class="sxs-lookup"><span data-stu-id="31b06-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="31b06-113">Użyj domyślnych danych demonstracyjnych</span><span class="sxs-lookup"><span data-stu-id="31b06-113">Default demo data</span></span>
<span data-ttu-id="31b06-114">Każde środowisko typu Onebox zawiera wstępnie załadowany zbiór danych demonstracyjnych rekomendacji dotyczących produktów przechowywanych w pliku Coma rozdzielonego **„reco_demo_data. csv"** znajdującego się w tym samym folderze, co ten dokument na serwerze Retail.</span><span class="sxs-lookup"><span data-stu-id="31b06-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="31b06-115">Dane te są uporządkowane według następujących kolumn</span><span class="sxs-lookup"><span data-stu-id="31b06-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="31b06-116">Nazwa kolumny</span><span class="sxs-lookup"><span data-stu-id="31b06-116">Column name</span></span>         | <span data-ttu-id="31b06-117">Wymagany</span><span class="sxs-lookup"><span data-stu-id="31b06-117">Mandatory</span></span>          | <span data-ttu-id="31b06-118">Opis</span><span class="sxs-lookup"><span data-stu-id="31b06-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="31b06-119">Możliwe wartości</span><span class="sxs-lookup"><span data-stu-id="31b06-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="31b06-120">RecoList</span><span class="sxs-lookup"><span data-stu-id="31b06-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="31b06-122">Określony typ listy zaleceń dla produktu, który ma zostać wygenerowany dla demonstracyjnego punktu danych.</span><span class="sxs-lookup"><span data-stu-id="31b06-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="31b06-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="31b06-123">RecoBestSelling</span></span></li><li><span data-ttu-id="31b06-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="31b06-124">RecoNew</span></span></li><li><span data-ttu-id="31b06-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="31b06-125">RecoTrending</span></span></li><li><span data-ttu-id="31b06-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="31b06-126">RecoCart</span></span></li><li><span data-ttu-id="31b06-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="31b06-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="31b06-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="31b06-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="31b06-130">Numer konkretnej jednostki operacyjnej, w której oczekiwane są rekomendacje produktów.</span><span class="sxs-lookup"><span data-stu-id="31b06-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="31b06-131">Kategoria</span><span class="sxs-lookup"><span data-stu-id="31b06-131">Category</span></span>            |                    |    <span data-ttu-id="31b06-132">Kategoria, dla której należy zwrócić określoną listę.</span><span class="sxs-lookup"><span data-stu-id="31b06-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="31b06-133">Jeśli nie określono żadnej kategorii, lista jest tylko dla górnej hierarchii nawigacji.</span><span class="sxs-lookup"><span data-stu-id="31b06-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="31b06-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="31b06-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="31b06-135">W przypadku list, które wymagają użycia materiału siewnego (RecoPeopleAlsoBuy i RecoCart), produkt zawierający te listy powinien zawierać dodatkowe produkty.</span><span class="sxs-lookup"><span data-stu-id="31b06-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="31b06-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="31b06-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="31b06-138">Jeden lub więcej produktów zwracanych w wyniku, oddzielonych przez **”;”**.</span><span class="sxs-lookup"><span data-stu-id="31b06-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="31b06-139">Dostosuj dane demonstracyjne</span><span class="sxs-lookup"><span data-stu-id="31b06-139">Customize demo data</span></span>
<span data-ttu-id="31b06-140">Użytkownicy mogą edytować domyślne dane demonstracyjne z dowolnymi informacjami dotyczącymi produktów i kategorii skonfigurowanymi w HQ.</span><span class="sxs-lookup"><span data-stu-id="31b06-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="31b06-141">Po zaktualizowaniu pliku CSV zasugerowane przez produkt rekomendacje będą natychmiast odzwierciedlane w tych zmianach.</span><span class="sxs-lookup"><span data-stu-id="31b06-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="31b06-142">Rozszerzenie zawiera plik danych o nazwie RecoMockDataset. csv, który zezwala klientowi na kontrolowanie zestawu danych używanego do wyłączania wyników rekomendacji dotyczących makiety.</span><span class="sxs-lookup"><span data-stu-id="31b06-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="31b06-143">Nazwa pliku może być kontrolowana za pośrednictwem konfiguracji rozszerzeń za pomocą ustawienia **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="31b06-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="31b06-144">Dzięki temu klienci mogą mieć dostęp do wielu zestawów danych, które można łatwo przełączać w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="31b06-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="31b06-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="31b06-145">Additional resources</span></span>

[<span data-ttu-id="31b06-146">Przegląd rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="31b06-146">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="31b06-147">Planowanie środowiska</span><span class="sxs-lookup"><span data-stu-id="31b06-147">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
