---
title: Tworzenie rekomendacji z danymi demonstracyjnymi
description: Niniejszy artykuł przedstawia wskazówki dotyczące sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7e3df414b3c16c28b6f5ca04f765d91c1312ada4
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2022
ms.locfileid: "9459976"
---
# <a name="create-recommendations-with-demo-data"></a>Tworzenie rekomendacji z danymi demonstracyjnymi

[!include [banner](includes/banner.md)]

Niniejszy artykuł przedstawia wskazówki dotyczące sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.

Wielokanałowe rekomendacje produktów zapewniają zestaw opracowanych edytorsko lub generowanych programowo list produktów. Listy te mogą być używane w kilku scenariuszach, w zależności od potrzeb biznesowych. Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

Zalecenia dotyczące środowisk Dynamics 365 warstwy 2 i wyższych są obliczane automatycznie na podstawie danych klientów. Korzystanie z pokazów dotyczących produktów dane demonstracyjne nie wyłączają żadnych zaleceń dotyczących produktów już zainicjowanych w środowisku oraz wszelkich kosztów związanych z jego użytkowaniem.

Zalecenia dotyczące produktów w warstwie 1 dotyczą wyłącznie statycznych danych demonstracyjnych przechowywanych w pliku .csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Włączanie demonstracyjnych danych na temat produktów w środowisku
Aby włączyć dane demonstracyjne rekomendacji produktu, użytkownicy muszą wdrożyć Rozszerzenie Dynamics 365 Commerce w wersji podglądu w odpowiednim środowisku. Takie rozwiązanie automatycznie włącza dane demonstracyjne rekomendacji produktu.

## <a name="default-demo-data"></a>Użyj domyślnych danych demonstracyjnych
Każde środowisko typu OneBox zawiera wstępnie załadowany zbiór danych demonstracyjnych rekomendacji dotyczących produktów przechowywanych w pliku rozdzielonym przecinkami „reco_demo_data. csv" znajdującego się w Commerce Scale Unit.

Dane te są uporządkowane według następujących kolumn.

| Nazwa kolumny         | Wymagany          | opis                                                                                                                                 | Możliwe wartości                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | Określony typ listy rekomendacji produktu, który ma zostać wygenerowany dla punktu danych demonstracyjnych.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li><li>RecoPicks</li><li>RecoSimilarVisual</li><li>RecoSimilarTextual</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Numer konkretnej jednostki operacyjnej, w której oczekiwane są rekomendacje produktów.                                        |                                                                              |
| Kategoria            |                    |    Kategoria, dla której należy zwrócić określoną listę. Jeśli nie określono żadnej kategorii, lista jest tylko dla górnej hierarchii nawigacji.    |                                                                              |
| SeedItemId          |                    |    W przypadku list, które wymagają użycia materiału siewnego (RecoPeopleAlsoBuy i RecoCart), produkt zawierający te listy powinien zawierać dodatkowe produkty.            |                                                                              |
| CustomerId          |                    |    Dla list, które wymagają identyfikatora odbiorcy (RecoPicks).  Wartość domyślna „0” dotyczy wszystkich odbiorców.          |                                                                              |
| ItemIds             | :heavy_check_mark: | Jeden lub więcej produktów zwracanych w wyniku, oddzielonych przez ”;”.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Dostosuj dane demonstracyjne
Użytkownicy mogą edytować domyślne dane demonstracyjne z dowolnymi informacjami dotyczącymi produktów i kategorii skonfigurowanymi w HQ. Po zaktualizowaniu pliku CSV zwrócone rekomendacje produktu będą natychmiast odzwierciedlane w tych zmianach.

Rozszerzenie zawiera plik danych o nazwie „RecoMockDataset.csv”, który zezwala użytkownikowi na kontrolowanie zestawu danych używanego do wyłączania wyników rekomendacji przykładowych. Nazwa pliku może być kontrolowana za pośrednictwem konfiguracji rozszerzeń za pomocą ustawienia **ext.Recommendations.DemoFilePath**. Dzięki temu użytkownik może mieć dostęp do wielu zestawów danych, które można łatwo przełączać w konfiguracji.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
