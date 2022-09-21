---
title: Dodawanie rekomendacji produktu w punkcie sprzedaży
description: W tym artykule opisano sposób korzystania z rekomendacji dotyczących produktów na urządzeniu punktu sprzedaży (POS).
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460064"
---
# <a name="add-product-recommendations-on-pos"></a>Dodawanie rekomendacji produktu w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Istotnie, rekomendacje produktów są aplikacją zmieniającą biznes obejmującą wszystkie obszary handlu w celu tworzenia bogatych, atrakcyjnych i dostosowanych rozwiązań do wykrywania produktów. Aby zaimplementować tę funkcję w punkcie sprzedaży, należy wykonać kroki [procedury dodawania zaleceń do urządzeń punktu sprzedaży.](add-recommendations-control-pos-screen.md) 

Aby uzyskać więcej informacji na temat zaleceń dotyczących funkcji rekomendacji, zapoznaj się z [przeglądem rekomendacji produktu.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scenariusze

Rekomendacje produktów działają w opisanych niżej scenariuszach w punkcie sprzedaż. Są dostępne dla aplikacji Cloud POS i Modern POS (MPOS).

1. Na stronie **Szczegóły produktu**:

    - Jeśli pracownik sklepu otworzy stronę **Szczegóły produktu** podczas oglądania wcześniejszych transakcji w różnych kanałach, usługa rekomendacji proponuje dodatkowe towary, które inni odbiorcy często kupowali razem z analizowanym produktem. W zależności od dodatków tej usługi sprzedawcy detaliczni mogą wyświetlać rekomendacje **Kupuj podobnie wyglądające rzeczy** i **Kupuj podobnie opisane rzeczy**, a także spersonalizowane rekomendacje dla użytkowników, którzy mają poprzednią historię zakupów.

    [![Rekomendacje na stronie Szczegóły produktu.](./media/proddetails.png)](./media/proddetails.png)

2. Na stronie **Transakcja**:

    - Zalecane jest, aby aparat rekomendacji sugerował pozycje na podstawie całej listy towarów w koszyku, które są często kupowane razem.

    > [!NOTE]
    > Aby rekomendacje były wyświetlane na stronie **Transakcja**, sprzedawca detaliczny musi zaktualizować układ ekranu w programie Dynamics 365 Commerce. Formant **Zalecenia** należy upuścić na stronę **Transakcja**.

    [![Rekomendacje na stronie Transakcja.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Konfigurowanie Commerce do obsługi rekomendacji POS 

Aby skonfigurować rekomendacje produktów, potwierdź, że proces inicjowania obsługi rekomendacji produktów Commerce został ukończony, zgodnie z krokiem [Włączanie rekomendacji produktów](../commerce/enable-product-recommendations.md). Domyślnie rekomendacje są wyświetlane zarówno na stronie **Szczegóły produktu**, jak i na stronie **Szczegółów dotyczące odbiorcy** po ukończeniu kroków inicjowania obsługi i pomyślnym przygotowanie danych. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Dodawanie rekomendacji do ekranu transakcji

1. Aby dodać rekomendacje na ekranie transakcji, wykonaj kroki w temacie [Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md).
1. Aby odzwierciedlić zmiany dokonane w konstruktorze układu ekranu punktu sprzedaży, uruchom zadanie konfiguracji kanału **1070** w programie Commerce Headquarters.

> [!NOTE] 
> Aby włączyć rekomendacje dotyczące aplikacji w punkcie sprzedaży za pomocą pliku RecoMock z wartościami rozdzielanymi przecinkami (CSV), przed skonfigurowaniem menedżera układów należy wdrożyć ten plik CSV w bibliotece elementów zawartości usługi Microsoft Dynamics Lifecycle Services (LCS). W przypadku korzystania z pliku CSV RecoMock nie trzeba włączać rekomendacji. Plik CSV jest dostępny tylko dla celów demonstracyjnych. Jest zalecane dla klientów lub architektów rozwiązań, którzy chcą naśladować wygląd list propozycji dla celów demonstracyjnych bez konieczności zakupu dodatku jednostka magazynowa (SKU)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
