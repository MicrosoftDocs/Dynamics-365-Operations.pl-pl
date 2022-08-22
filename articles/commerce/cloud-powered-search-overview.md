---
title: Omówienie wyszukiwania w chmurze
description: Ten artykuł zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: ed80ff42ea5c6e6a904ea2855953d006f66aad37
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273674"
---
# <a name="cloud-powered-search-overview"></a>Omówienie wyszukiwania w chmurze

[!include [banner](includes/banner.md)]

Ten artykuł zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.

Wykrywanie produktów pomaga zagwarantować klientom szybkie i łatwe wyszukiwanie produktów poprzez przeglądanie kategorii, wyszukiwanie i filtrowanie. Sprzedawcy detaliczni uważają odkrywanie produktów za podstawowe narzędzie interakcji z klientami w kanałach obsługiwanych przez Cloud Scale Unit (CSU), takich jak e-commerce i punkty sprzedaży (POS).

Klienci są przyzwyczajeni do niemal natychmiastowych czasów reakcji wyszukiwarek internetowych, wyrafinowanych stron e-Commerce, aplikacji społecznościowych, automatycznych sugestii, które pojawiają się podczas wpisywania wyszukiwanych haseł, fasetowanej nawigacji i wyróżniania. Jeśli klienci nie mogą szybko znaleźć produktu, którego szukają w jednym sklepie e-commerce, nie zawahają się przejść do innego sklepu e-commerce.

Możliwość wyszukiwania produktów w chmurze Commerce pomaga sprzedawcom w dalszym zwiększaniu utrzymania klientów i współczynników konwersji w kanałach obsługiwanych przez CSU.

W wyszukiwaniu Commerce ulepszono możliwości pomagające detalistom w osiągnięciu lepszej wykrywalności produktów. Jednocześnie funkcje te zapewniają skalowalność i wydajność, które są wymagane w przypadku ruchu handlu elektronicznego.

## <a name="browse-and-search"></a>Przeglądaj i szukaj

Trafność i wydajność wyszukiwania są kluczowymi czynnikami w doświadczeniu wielokanałowym, ponieważ odkrywanie produktu polega przede wszystkim na funkcji wyszukiwania w zakresie wyszukiwania informacji i nawigacji treści. Skuteczne i wydajne przeglądanie i wyszukiwanie pomaga zwiększyć konwersję.

Na poniższej ilustracji przedstawiono przykład typowej funkcji przeglądania i wyszukiwania.

![Strona docelowa wyszukiwania.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Szlifowana nawigacja i podsumowanie wyboru 

Nawigacja fasetowa pomaga klientom łatwiej przeglądać zawartość, umożliwiając im filtrowanie według rafinerii powiązanych z warunkami w zestawie terminów. Po wybraniu i zastosowaniu rafinerów przez klienta wyświetlane jest podsumowanie wybranych opcji. 

Korzystając z nawigacji fasetowej, możesz skonfigurować różne rafinery dla różnych terminów w zestawie terminów, bez konieczności tworzenia dodatkowych stron. 

Poniższa ilustracja pokazuje przykład, w którym podczas wyszukiwania używana jest nawigacja fasetowa.

![Podsumowanie wyboru.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Immersyjne autosugerowanie

Bieżąca funkcja autosugerowania pokazuje słowa kluczowe, które wyzwalają wyszukanie odpowiedniego słowa kluczowego. Ze względu na nowe ulepszenia w Commerce klienci mogą często wykrywać łącza do produktów, zanim zakończą one wpisywanie.

Commerce obsługuje także funkcje dotyczące słów kluczowych w różnych kategoriach. Dzięki tej funkcji klienci widzą liczbę słów kluczowych w różnych kategoriach i uruchamiają wyszukiwanie słowa kluczowego w innych kategoriach.

Na poniższej ilustracji pokazano przykład, na którym jest używana funkcja automatycznego sugerowania.

![immersyjne autosugerowanie.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Sortuj

Funkcja sortowania umożliwia klientom sortowanie, wyszukiwanie i przeglądanie wyników kategorii oraz doprecyzowanie ich według kryteriów, takich jak cena, nazwa produktu i numer produktu. Włączenie funkcji [rekomendacji produktów](product-recommendations.md) w twoim środowisku umożliwia również klientom sortowanie wyników na podstawie zaawansowanych kryteriów sortowania, takich jak nowe, najpowiedniejsze i trendy.


> [!NOTE]
> Te możliwości wyszukiwania z wykorzystaniem chmury są dostępne począwszy od wersji 10.0.8. Upewnij się, że istnieje wpis dla „ProductSearch.UseAzureSearch” ustawiony na wartość „prawda” w **Parametry handlu > Parametry konfiguracji**. 
![Parametry konfiguracji dla wyszukiwania z wykorzystaniem chmury.](./media/CloudPoweredSearchConfigurationParameters.png)
>Zaawansowane opcje sortowania, takie jak nowe, bestsellery i trendy, są dostępne w wersji Commerce SSK 9.35+ i Dynamics 365 Commerce 10.0.20.  


## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md)

[Zarządzanie metadanymi SEO](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
