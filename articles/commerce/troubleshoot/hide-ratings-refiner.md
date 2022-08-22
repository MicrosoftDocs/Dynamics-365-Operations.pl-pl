---
title: Jeśli nie jest włączone rozwiązanie ocen i recenzji, na stronach wyników wyszukiwania i kategorii wyświetlana jest funkcja poprawiania ocen
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów w przypadku ukrywania funkcji poprawiania ocen na stronach wyników wyszukiwania i kategorii, gdy rozwiązanie w zakresie ocen i recenzji aplikacji Microsoft Dynamics 365 Commerce nie jest włączone w witrynie e-commerce.
author: gvrmohanreddy
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
manager: annbe
ms.openlocfilehash: 28a3cefd6aab81f5e7907bda457763f2306e5a1d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267385"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>Jeśli nie jest włączone rozwiązanie ocen i recenzji, na stronach wyników wyszukiwania i kategorii wyświetlana jest funkcja poprawiania ocen

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów w przypadku ukrywania funkcji poprawiania ocen na stronach wyników wyszukiwania i kategorii, gdy rozwiązanie w zakresie ocen i recenzji aplikacji Microsoft Dynamics 365 Commerce nie jest włączone w witrynie e-commerce.

## <a name="description"></a>opis

Funkcja poprawiania ocen jest wyświetlana na stronach wyników wyszukiwania i kategorii w kanale e-commerce, który nie używa rozwiązania do obsługi ocen i recenzji.

## <a name="resolution"></a>Rozwiązanie

### <a name="enable-the-hide-rating-setting-in-commerce-site-builder"></a>Włączanie ustawienia Ukryj ocenę w konstruktorze witryn portalu Commerce

Aby włączyć ustawienie **Ukryj oceny** w konstruktorze witryn portalu Commerce, tak aby funkcja ulepszania ocen była ukryte na stronach wyników wyszukiwania i kategorii, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. W obszarze **Oceny i recenzje** zaznacz pole wyboru **Ukryj ocenę**.
1. Wybierz **Zapisz i opublikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](../ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](../opt-in-ratings-reviews.md)
