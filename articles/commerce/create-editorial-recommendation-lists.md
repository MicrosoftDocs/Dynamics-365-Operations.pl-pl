---
title: Ręczne tworzenie zaleceń pod opieką
description: W tym artykule wyjaśniono, w jaki sposób merchandizers mogą tworzyć i zarządzać ręcznymi listami produktów dla odbiorców Microsoft Dynamics 365 Commerce.
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
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e1a1b402165c5cb35696cf1cf6630770ad07508a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892685"
---
# <a name="manually-create-curated-recommendations"></a>Ręczne tworzenie zaleceń pod opieką

[!include [banner](includes/banner.md)]

W tym artykule wyjaśniono, jak handlowcy mogą ręcznie tworzyć listy rekomendacji produktów dla klientów Microsoft Dynamics 365 Commerce.

Wyselekcjonowane listy to zbiory indywidualnych, treści tworzone i dostosowywane przez ludzi.  

## <a name="create-a-new-list"></a>Utwórz nową listę

Aby utworzyć wyselekcjonowaną listę rekomendacji produktów, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce &gt; Rekomendacje produktów &gt; Listy rekomendacji**.
1. Wybierz pozycję **Nowy**.
1. Wprowadź wartość w polu **Identyfikator listy**.
1. Wprowadź wartość w polu **Nazwa listy**.
    - **Nazwa listy** jest tytułem listy, który pojawi się w sekcji list wyselekcjonowanych w module **kolekcja produktów**.
1. Aby dodać produkty do listy, wybierz **Dodaj produkty**.
1. Aby zmienić kolejność produktów z listy, należy wprowadzić wartość w kolumnie **Kolejność wyświetlania**.
    - Jeśli dwa produkty mają taką samą wartość zamówienia wyświetlania, ostateczna kolejność tych dwóch wyników może się różnić od biura zaplecza.
1. Wybierz **Zapisz**, aby zapisać listę.

## <a name="example-list"></a>Przykładowa lista

![Przykładowa wyselekcjonowana lista w biurze zaplecza.](./media/examplecuratedrecolist.png)

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

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]