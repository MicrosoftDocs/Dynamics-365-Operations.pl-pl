---
title: Jeśli nie jest włączone rozwiązanie ocen i recenzji, na stronach wyników wyszukiwania i kategorii wyświetlana jest funkcja poprawiania ocen
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów w przypadku ukrywania funkcji poprawiania ocen na stronach wyników wyszukiwania i kategorii, gdy rozwiązanie w zakresie ocen i recenzji aplikacji Microsoft Dynamics 365 Commerce nie jest włączone w witrynie e-commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ff413e04d7e60da76cd83ecd720c3589b65e93d5
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407643"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>Jeśli nie jest włączone rozwiązanie ocen i recenzji, na stronach wyników wyszukiwania i kategorii wyświetlana jest funkcja poprawiania ocen

[!include [banner](../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów w przypadku ukrywania funkcji poprawiania ocen na stronach wyników wyszukiwania i kategorii, gdy rozwiązanie w zakresie ocen i recenzji aplikacji Microsoft Dynamics 365 Commerce nie jest włączone w witrynie e-commerce.

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
