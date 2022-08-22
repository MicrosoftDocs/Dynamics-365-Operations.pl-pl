---
title: Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie
description: W tym artykule omówiono domyślną stronę docelową kategorii i stronę wyników wyszukiwania w Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/30/2020
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
ms.openlocfilehash: 1f2e4eb8825dd690f926f7f0bdfc39f1eb5fb83c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276381"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie

[!include [banner](includes/banner.md)]

W tym artykule omówiono domyślną stronę docelową kategorii i stronę wyników wyszukiwania w Microsoft Dynamics 365 Commerce e-Commerce.

## <a name="default-category-landing-page"></a>Domyślna strona docelowa kategorii

Domyślna strona docelowa kategorii to strona, do której zazwyczaj są przyjmowane użytkownicy serwisu www, gdy wybierają kategorię w hierarchii nawigacji. Strona kategorii umożliwia przeglądanie, a także sortowanie i modyfikowanie produktów skategoryzowanych.

![Domyślna strona docelowa kategorii.](./media/SimpleCategoryLandingDressCategory.png)

U góry strony znajduje się nagłówek, który pokazuje wszystkie kategorie produktów i inne strony, które podzielił kierownik sprzedaży. Konfiguracja jest wykonana w ramach konfiguracji hierarchii nawigacji kanału. Na dole strony znajduje się stopka zawierająca szybkie linki do różnych artykułów, które mogą zainteresować kupującego.

Następujące składniki są istotne dla danej kategorii:

- **Kafelki umieszczenia produktu** pokazują produkty, które zostały zdefiniowane przez Menedżera ds. merchandisingu w kategorii jako część konfiguracji hierarchii nawigacji.
- **Elementy uściślające i podsumowanie wyborów** są filtrami, które dostarczają liczników i służą do poprawiania pozycji. Menedżer ds. merchandisingu konfiguruje je jako część konfiguracji metadanych związanych z kategoriami kanału i atrybutami produktu.
- **Opcje sortowania** są używane przez odwiedzających witrynę sieci Web do sortowania produktów. Domyślnie dostępne są następujące opcje sortowania:

    - Cena – od najniższej do najwyższej
    - Cena – od najwyższej do najniższej
    - Nazwa produktu – \[A-Z\]
    - Nazwa produktu – \[Z-A\]
    - Ocena – od najniższej do najwyższej
    - Ocena – od najwyższej do najniższej

- **Zaawansowane opcje sortowania** są używane przez odwiedzających witrynę do sortowania produktów za pomocą inteligentnych kryteriów. Po włączeniu [Rekomendacje produktów](product-recommendations.md) dostępne są następujące opcje sortowania. Aby uzyskać więcej informacji, zobacz artykuł [Typy rekomendacji produktów](product-recommendations.md#types-of-product-recommendations).

    - Nowa
    - Najlepiej sprzedawane
    - Popularne

- **Podział na strony** umożliwia osobom odwiedzającym witrynę przechodzenie z jednej strony skategoryzowanych wyników produktów na inną stronę.
- **Licznik całkowity** podaje całkowitą liczbę produktów zdefiniowanych w kategorii.

## <a name="enrich-a-category-landing-page"></a>Wzbogacanie strony docelowej kategorii

Jeśli chcesz, aby strona docelowa kategorii zawierała bardziej dostosowane doświadczenie w odniesieniu do konkretnej kategorii, możesz „wzbogacić” stronę do tej kategorii. Na przykład można dodać marketingowy materiał wideo i kilka opowieści kategorii, aby uzyskać uwagę klienta. Aby uzyskać więcej informacji, zapoznaj się z tematem [Wzbogacanie strony docelowej kategorii](enrich-category-page.md).

![Wzbogacona strona docelowa kategorii.](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Automatyczne sugerowanie i wyszukiwanie stron wyników

Użytkownicy witryny sieci Web mogą eksplorować witrynę, przechodząc do kategorii z hierarchii nawigacji lub wprowadzając wyszukiwany termin w polu wyszukiwania.

Gdy tylko użytkownicy rozpoczną wpisywanie pola wyszukiwania, będą mieć funkcję automatycznego sugerowania, która sugeruje terminy wyszukiwania.

Oto kilka typów sugestii, które mogą być wyświetlane:

- **Słowa kluczowe** służą do wyszukiwania towarów we wszystkich produktach w danym kanale.
- **Produkty** dostarczają bezpośrednich łączy do strony Szczegóły produktu.
- **Sugestie wyszukiwania kategorii objętej zakresem** mają różne kategorie i umożliwiają użytkownikom wyszukiwanie słów kluczowych w określonych kategoriach.

![immersyjna automatyczna sugestia.](./media/ImmersiveAutoSuggestUX.png)

Gdy użytkownicy wybiorą jedną z propozycji wyszukiwania słowa kluczowego lub kategorii lub gdy nie ma podanych sugestii dla wyszukiwanego hasła, zostają przekierowani na stronę wyników wyszukiwania. Użytkownicy mogą następnie przeglądać, sortować i udoskonalać listę wyników wyszukiwania, aby znaleźć żądany element.

![Strona docelowa wyszukiwania.](./media/SearchLanding.png)

Następujące składniki są istotne dla strony wyników wyszukiwania

- **Kafelki umieszczenia produktu** pokazują produkty dla wyszukiwania użytkownika. Domyślnie te kafelki są sortowane według punktacji Relevancy wyszukiwanej w chmurze dla wyszukiwania użytkownika.
- **Elementy uściślające i podsumowanie wyborów** są filtrami, które dostarczają liczników i służą do poprawiania pozycji. Menedżer ds. merchandisingu konfiguruje je jako część konfiguracji metadanych związanych z „kategoriami kanału i atrybutami produktu”.
- **Standardowe opcje sortowania** są używane przez odwiedzających witrynę sieci Web do sortowania produktów. Domyślnie dostępne są następujące opcje sortowania:

    - Cena – od najniższej do najwyższej
    - Cena – od najwyższej do najniższej
    - Nazwa produktu – \[A-Z\]
    - Nazwa produktu – \[Z-A\]
    - Ocena – od najniższej do najwyższej
    - Ocena – od najwyższej do najniższej
    - Domyślnie 
    
    > [!NOTE]
    > Jeśli dla produktów w hierarchii nawigacji zdefiniowano wartości **Kolejność wyświetlania**, sortowanie domyślnie na stronie kategorii uwzględnia wartości zdefiniowane w **Kolejność wyświetlania**. W przeciwnym razie sortowanie zostanie wykonane według **numeru produktu**)
    
- **Zaawansowane opcje sortowania** są używane przez odwiedzających witrynę do sortowania produktów za pomocą inteligentnych kryteriów. Po włączeniu [Rekomendacje produktów](product-recommendations.md) dostępne są następujące opcje sortowania. Aby uzyskać więcej informacji, zobacz artykuł [Typy rekomendacji produktów](product-recommendations.md#types-of-product-recommendations).

    - Nowa
    - Najlepiej sprzedawane
    - Popularne

- **Podział na strony** umożliwia osobom odwiedzającym witrynę przechodzenie z jednej strony skategoryzowanych wyników produktów na inną stronę.
- **Licznik całkowity** podaje całkowitą liczbę produktów zdefiniowanych w kategorii i wyników pasujących do kryteriów wyszukiwania.

>[!NOTE]
>Te możliwości wyszukiwania z wykorzystaniem chmury są dostępne począwszy od wersji 10.0.8. Upewnij się, że w menu **Parametry Commerce > Konfigurowanie parametrów** istnieje wpis o wartości „true” dla parametru „ProductSearch.UseAzureSearch”. 
![Parametry konfiguracji dla wyszukiwania z wykorzystaniem chmury.](./media/CloudPoweredSearchConfigurationParameters.png)

>Ponadto, aby używać zaawansowanych opcji sortowania, takich jak nowe, najpowiedniejsze i najmodnujące, należy włączyć [Rekomendacje produktów](product-recommendations.md) w swoim środowisku. Zaawansowane opcje sortowania są dostępne wraz z zestawami Commerce SDK w wersji 9.35+ i Commerce w wersji 10.0.20.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie wyszukiwania w chmurze](cloud-powered-search-overview.md)

[Omówienie strony głównej](quick-tour-home-page.md)

[Omówienie stron szczegółów produktów](quick-tour-pdp.md)

[Omówienie stron koszyka i realizacji zamówienia](quick-tour-cart-checkout.md)

[Omówienie stron zarządzania kontem](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
