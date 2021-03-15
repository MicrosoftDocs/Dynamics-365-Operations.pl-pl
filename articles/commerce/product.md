---
title: Dodawanie rekomendacji produktu w punkcie sprzedaży
description: W tym temacie opisano sposób korzystania z rekomendacji dotyczących produktów na urządzeniu punktu sprzedaży (POS).
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 08784385dd1fead13f538b4e856b4bac6651a560
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969933"
---
# <a name="add-product-recommendations-on-pos"></a>Dodawanie rekomendacji produktu w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Istotnie, rekomendacje produktów są aplikacją zmieniającą biznes obejmującą wszystkie obszary handlu w celu tworzenia bogatych, atrakcyjnych i dostosowanych rozwiązań do wykrywania produktów. Aby zaimplementować tę funkcję w punkcie sprzedaży, należy wykonać kroki [procedury dodawania zaleceń do urządzeń punktu sprzedaży.](add-recommendations-control-pos-screen.md) 

Aby uzyskać więcej informacji na temat zaleceń dotyczących funkcji rekomendacji, zapoznaj się z [przeglądem rekomendacji produktu.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scenariusze

Rekomendacje produktów działają w opisanych niżej scenariuszach w punkcie sprzedaż. Są dostępne dla aplikacji Cloud POS i Modern POS (MPOS).

1. Na stronie **Szczegóły produktu**:

    - Jeśli pracownik sklepu otworzy stronę **Szczegóły produktu** podczas oglądania wcześniejszych transakcji w różnych kanałach, usługa rekomendacji proponuje dodatkowe towary, które inni odbiorcy często kupowali razem z analizowanym produktem.

    [![Rekomendacje na stronie Szczegóły produktu](./media/proddetails.png)](./media/proddetails.png)

2. Na stronie **Transakcja**:

    - Zalecane jest, aby aparat rekomendacji sugerował pozycje na podstawie całej listy towarów w koszyku, które są często kupowane razem.

    > [!NOTE]
    > Aby rekomendacje były wyświetlane na stronie **Transakcja**, sprzedawca detaliczny musi zaktualizować układ ekranu w programie Dynamics 365 Commerce. Formant **Zalecenia** należy upuścić na stronę **Transakcja**.

    [![Rekomendacje na stronie Transakcja](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Konfigurowanie Commerce do obsługi rekomendacji POS

Aby skonfigurować rekomendacje produktu, wykonaj następujące czynności:

1. Upewnij się, że usługa została zaktualizowana do **kompilacji 10.0.6.**
2. Postępuj zgodnie z instrukcjami dotyczącymi sposobu [włączania rekomendacji produktu](../commerce/enable-product-recommendations.md) w firmie.
3. Opcjonalnie: Aby wyświetlać rekomendacje na ekranie transakcji, przejdź do okna **Układ ekranu**, wybierz układ ekranu, uruchom narzędzie **Projektant układu ekranu**, a następnie upuść formant **rekomendacji** w żądanym miejscu.
4. Przejdź do okna **Parametry sprzedaży**, wybierz opcję **Uczenie maszynowe** i w ustawieniu **Włącz rekomendacje w punkcie sprzedaży** wybierz wartość **Tak**.
5. Aby rekomendacje były wyświetlane w punkcie sprzedaży, uruchom zadanie konfiguracji globalnej **1110**. Aby pokazywać zmiany wprowadzone w projektancie układu ekranu punktu sprzedaży, uruchom zadanie konfiguracji kanału **1070**.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Rozwiązywanie problemów, jeśli już włączono funkcję Rekomendacje produktów

- Wybierz kolejno opcje **Parametry sprzedaży** \> **Listy rekomendacji** \> **Wyłącz rekomendacje produktów** i uruchom **Żądanie konfiguracji globalnej \[9999\]**. 
- Jeśli za pomocą **Projektanta układu ekranu** dodano **kontrolkę rekomendacji** do ekranu transakcji, usuń również ją.
- Jeśli masz dodatkowe pytania, zapoznaj się z [Rekomendacje produktów - Często zadawane pytania](../commerce/faq-recommendations.md).

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