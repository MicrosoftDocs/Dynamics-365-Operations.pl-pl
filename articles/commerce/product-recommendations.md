---
title: Omówienie rekomendacji produktów
description: Ten temat zawiera ogólne informacje o rekomendacjach produktu. Rekomendacje produktów umożliwiają łatwe i szybkie znajdowanie produktów, które są potrzebne, a nawet produktów, których klient nie zamierzał pierwotnie kupić.
author: Moonma
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
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770054"
---
# <a name="product-recommendations-overview"></a>Omówienie rekomendacji produktów

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce może posłużyć do pokazywania zaleceń dotyczących produktów w witrynie e-Commerce i urządzeniach punktu sprzedaży (POS). Rekomendacje produktów to przedmioty, które mogą być interesujące dla odbiorcy. Rekomendacje są oparte na trendach zakupu innych odbiorców w sklepach internetowych oraz w sklepach tradycyjnych.

Zalecenia dotyczące produktów pozwalają klientom łatwo i szybko znaleźć produkty, których chcą, mając doświadczenie, które im dobrze służy. Można nawet użyć sprzedaży powiązanej i oferowanie droższego produktu, aby ułatwić klientom znalezienie dodatkowych produktów niż pierwotnie zamierzone. Kiedy rekomendacje są pomocne w odkrywaniu produktów, mogą stworzyć więcej możliwości konwersji, pomóc zwiększyć przychody ze sprzedaży, a nawet pomóc zwiększyć satysfakcję i utrzymanie klientów.

W Commerce rekomendacje produktów są oparte na technologiach uczenia maszynowego rekomendacji Microsoft na dużą skalę.


## <a name="scenarios"></a>Scenariusze

Rekomendacje produktów są dostępne w opisanych niżej scenariuszach:

- **Na dowolnej stronie sklepu lub stronie magazynowej w e-Commerce:** Jeśli klient lub sprzedawca odwiedza stronę sklepu, aparat rekomendacji może sugerować produkty na listach **Nowości**, **Bestsellery** i **Trendy**.
- **Na stronie Szczegóły produktu:** Jeśli klienci lub sprzedawcy odwiedzają stronę **Szczegóły produktu**, aparat rekomendacji sugeruje dodatkowe towary, które również prawdopodobnie zostaną nabyte. Pozycje te pojawiają się również na liście osoby **Klientom podoba się również**.
- **Na stronie transakcja lub stronie realizacja transakcji:** aparat rekomendacji sugeruje pozycje na podstawie całej listy towarów w koszyku. Te pozycje są wyświetlane na liście **Często kupowane razem**.

## <a name="recommendation-service"></a>Usługa rekomendacji

Zalecenia dotyczące produktu wykorzystują technologie uczenia maszynowego Rekomendacji w następujący sposób:

- Dane w formacie wymaganym przez usługę rekomendacji są pobierane z operacyjnej bazy danych Commerce i wysyłane do magazynu jednostek.
- Usługa rekomendacji korzysta z danych w celu wytrenowania modeli rekomendacji dla list **Klientom podoba się również**, **Często kupowane razem**, **Nowości**, **Bestsellery** i **Trendy**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Włączanie rekomendacji produktów](enable-product-recommendations.md)

[Tworzenie list zaleceń dotyczących produktów pod opieką](create-editorial-recommendation-lists.md)

[Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md)

[Dodawanie list rekomendacji produktów do stron](add-reco-list-to-page.md)
