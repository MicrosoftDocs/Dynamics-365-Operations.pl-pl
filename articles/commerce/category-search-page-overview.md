---
title: Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie
description: W tym temacie omówiono domyślną stronę docelową kategorii i stronę wyników wyszukiwania w Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e85449c10fa4a768a144ce423a77bd1fc2c94352
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414907"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie

[!include [banner](includes/banner.md)]

W tym temacie omówiono domyślną stronę docelową kategorii i stronę wyników wyszukiwania w Microsoft Dynamics 365 Commerce e-Commerce.

## <a name="default-category-landing-page"></a>Domyślna strona docelowa kategorii

Domyślna strona docelowa kategorii to strona, do której zazwyczaj są przyjmowane użytkownicy serwisu www, gdy wybierają kategorię w hierarchii nawigacji. Strona kategorii umożliwia przeglądanie, a także sortowanie i modyfikowanie produktów skategoryzowanych.

![Domyślna strona docelowa kategorii](./media/SimpleCategoryLandingDressCategory.png)

U góry strony znajduje się nagłówek, który pokazuje wszystkie kategorie produktów i inne strony, które podzielił kierownik sprzedaży. Konfiguracja jest wykonana w ramach konfiguracji hierarchii nawigacji kanału. Na dole strony znajduje się stopka zawierająca szybkie linki do różnych tematów, które mogą zainteresować kupującego.

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

- **Podział na strony** umożliwia osobom odwiedzającym witrynę przechodzenie z jednej strony skategoryzowanych wyników produktów na inną stronę.
- **Licznik całkowity** podaje całkowitą liczbę produktów zdefiniowanych w kategorii.

## <a name="enrich-a-category-landing-page"></a>Wzbogacanie strony docelowej kategorii

Jeśli chcesz, aby strona docelowa kategorii zawierała bardziej dostosowane doświadczenie w odniesieniu do konkretnej kategorii, możesz „wzbogacić” stronę do tej kategorii. Na przykład można dodać marketingowy materiał wideo i kilka opowieści kategorii, aby uzyskać uwagę klienta. Aby uzyskać więcej informacji, zapoznaj się z tematem [Wzbogacanie strony docelowej kategorii](enrich-category-page.md).

![Wzbogacona strona docelowa kategorii](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Automatyczne sugerowanie i wyszukiwanie stron wyników

Użytkownicy witryny sieci Web mogą eksplorować witrynę, przechodząc do kategorii z hierarchii nawigacji lub wprowadzając wyszukiwany termin w polu wyszukiwania.

Gdy tylko użytkownicy rozpoczną wpisywanie pola wyszukiwania, będą mieć funkcję automatycznego sugerowania, która sugeruje terminy wyszukiwania.

Oto kilka typów sugestii, które mogą być wyświetlane:

- **Słowa kluczowe** służą do wyszukiwania towarów we wszystkich produktach w danym kanale.
- **Produkty** dostarczają bezpośrednich łączy do strony Szczegóły produktu.
- **Sugestie wyszukiwania kategorii objętej zakresem** mają różne kategorie i umożliwiają użytkownikom wyszukiwanie słów kluczowych w określonych kategoriach.

![immersyjna automatyczna sugestia](./media/ImmersiveAutoSuggestUX.png)

Gdy użytkownicy wybiorą jedną z propozycji wyszukiwania słowa kluczowego lub kategorii lub gdy nie ma podanych sugestii dla wyszukiwanego hasła, zostają przekierowani na stronę wyników wyszukiwania. Użytkownicy mogą następnie przeglądać, sortować i udoskonalać listę wyników wyszukiwania, aby znaleźć żądany element.

![Stona docelowa wyszukiwania](./media/SearchLanding.png)

Następujące składniki są istotne dla strony wyników wyszukiwania

- **Kafelki umieszczenia produktu** pokazują produkty dla wyszukiwania użytkownika. Domyślnie te kafelki są sortowane według punktacji Relevancy wyszukiwanej w chmurze dla wyszukiwania użytkownika.
- **Elementy uściślające i podsumowanie wyborów** są filtrami, które dostarczają liczników i służą do poprawiania pozycji. Menedżer ds. merchandisingu konfiguruje je jako część konfiguracji metadanych związanych z „kategoriami kanału i atrybutami produktu”.
- **Opcje sortowania** są używane przez odwiedzających witrynę sieci Web do sortowania produktów. Domyślnie dostępne są następujące opcje sortowania:

    - Cena – od najniższej do najwyższej
    - Cena – od najwyższej do najniższej
    - Nazwa produktu – \[A-Z\]
    - Nazwa produktu – \[Z-A\]
    - Ocena – od najniższej do najwyższej
    - Ocena – od najwyższej do najniższej
    - Domyślnie

- **Podział na strony** umożliwia osobom odwiedzającym witrynę przechodzenie z jednej strony skategoryzowanych wyników produktów na inną stronę.
- **Licznik całkowity** podaje całkowitą liczbę produktów zdefiniowanych w kategorii i wyników pasujących do kryteriów wyszukiwania.

>[!NOTE]
>Te możliwości wyszukiwania z wykorzystaniem chmury są dostępne począwszy od wersji 10.0.8. Upewnij się, że w menu **Parametry Commerce > Konfigurowanie parametrów** istnieje wpis o wartości „true” dla parametru „ProductSearch.UseAzureSearch”. 
![Parametry konfiguracji dla wyszukiwania z wykorzystaniem chmury](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie wyszukiwania w chmurze](cloud-powered-search-overview.md)

[Omówienie strony głównej](quick-tour-home-page.md)

[Omówienie stron szczegółów produktów](quick-tour-pdp.md)

[Omówienie stron koszyka i realizacji zamówienia](quick-tour-cart-checkout.md)

[Omówienie stron zarządzania kontem](quick-tour-account-management.md)

