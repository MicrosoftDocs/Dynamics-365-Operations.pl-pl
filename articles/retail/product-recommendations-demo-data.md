---
title: Dane demonstracyjne dotyczące produktu w kanale rozproszonego
description: Niniejszy dokument ma na celu zapewnienie wskazówek dotyczących sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: 81af4c1bb7828c9b346a3ef514d8657e853dcefb
ms.sourcegitcommit: c526cfd1f823df1ff33ded95e599a72f0a15cc5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2226323"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Dane demonstracyjne dotyczące produktu w kanale rozproszonego

Niniejszy dokument ma na celu zapewnienie wskazówek dotyczących sposobu korzystania z zaleceń dotyczących produktu kanału rozproszonego w środowiskach z jedną ramką w warstwie 1 przy użyciu wstępnie wypełnionych, dostosowywanych danych demonstracyjnych.

Zalecenia dotyczące produktu w kanale rozproszonym stanowią zbiór zamówionej listy produktów z redakcją lub programowo. Listy te mogą być używane w kilku scenariuszach, w zależności od potrzeb biznesowych. Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [przeglądem rekomendacji produktu.](product-recommendaitons-overview.md)

Zalecenia dotyczące systemu środowiskowego warstwy 2 i większej są obliczane automatycznie na podstawie danych klientów.
Korzystanie z pokazów dotyczących produktów dane demonstracyjne nie wyłączają żadnych zaleceń dotyczących produktów już zainicjowanych w środowisku oraz wszelkich kosztów związanych z jego użytkowaniem.

Zalecenia dotyczące produktów w warstwie 1 dotyczą wyłącznie statycznych danych demonstracyjnych przechowywanych w pliku CSV.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Włączanie demonstracyjnych danych na temat produktów w środowisku

Klienci muszą wdrożyć **Rozszerzenie Dynamics 365 Commerce podglądu** w odpowiednim środowisku, które automatycznie włącza dane demonstracyjne dotyczące produktu.

## <a name="default-demo-data"></a>Użyj domyślnych danych demonstracyjnych
Każde środowisko typu Onebox zawiera wstępnie załadowany zbiór danych demonstracyjnych rekomendacji dotyczących produktów przechowywanych w pliku Coma rozdzielonego **„reco_demo_data. csv"** znajdującego się w tym samym folderze, co ten dokument na serwerze Retail.

Dane te są uporządkowane według następujących kolumn

| Nazwa kolumny         | Wymagany          | Opis                                                                                                                                 | Możliwe wartości                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | Określony typ listy zaleceń dla produktu, który ma zostać wygenerowany dla demonstracyjnego punktu danych.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Numer konkretnej jednostki operacyjnej, w której oczekiwane są rekomendacje produktów.                                        |                                                                              |
| Kategoria            |                    |    Kategoria, dla której należy zwrócić określoną listę. Jeśli nie określono żadnej kategorii, lista jest tylko dla górnej hierarchii nawigacji.    |                                                                              |
| SeedItemId          |                    |    W przypadku list, które wymagają użycia materiału siewnego (RecoPeopleAlsoBuy i RecoCart), produkt zawierający te listy powinien zawierać dodatkowe produkty.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Jeden lub więcej produktów zwracanych w wyniku, oddzielonych przez **”;”**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Dostosuj dane demonstracyjne
Użytkownicy mogą edytować domyślne dane demonstracyjne z dowolnymi informacjami dotyczącymi produktów i kategorii skonfigurowanymi w HQ. Po zaktualizowaniu pliku CSV zasugerowane przez produkt rekomendacje będą natychmiast odzwierciedlane w tych zmianach.

Rozszerzenie zawiera plik danych o nazwie RecoMockDataset. csv, który zezwala klientowi na kontrolowanie zestawu danych używanego do wyłączania wyników rekomendacji dotyczących makiety. Nazwa pliku może być kontrolowana za pośrednictwem konfiguracji rozszerzeń za pomocą ustawienia **ext.Recommendations.DemoFilePath**. Dzięki temu klienci mogą mieć dostęp do wielu zestawów danych, które można łatwo przełączać w konfiguracji.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd rekomendacji produktów](product-recommendations-overview.md)

[Planowanie środowiska](environment-planning.md)
