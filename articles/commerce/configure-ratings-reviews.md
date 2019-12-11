---
title: Konfigurowanie ocen i recenzji
description: W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770488"
---
# <a name="configure-ratings-and-reviews"></a>Konfigurowanie ocen i recenzji

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Oceny i Recenzje w witrynach e-Commerce umożliwiają klientom zapoznanie się z produktami przed podjęciem decyzji o zakupie, kierując ich uwagę na te produkty. W przypadku witryn e-Commerce, oceny i recenzje są również mechanizmami zbierania opinii klientów dotyczących produktów. 

Oceny są wyświetlane na stronach list produktów, na stronach list kategorii, na stronach wyników wyszukiwania oraz na innych stronach witryny. Histogramy ocen i recenzje produktów są wyświetlane na stronach szczegółów produktów (stronach PDP). Przez naciśnięcie przycisku **Napisz recenzję** klienci mogą przesyłać oceny i recenzje produktu.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Moduły ocen i recenzji na stronach PDP 

Na stronach PDP w trzech modułach są wyświetlane podsumowania ocen i recenzji:

- Napisz moduł recenzji
- Moduł listy recenzji produktów
- Moduł histogramu ocen
 
Na poniższej ilustracji przedstawiono jak moduły ocen i recenzji wyglądają na stronach PDP.

![Moduły ocen i recenzji na stronach PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Aby uzyskać informacje na temat optymalizowania szablonów i układów PDP, tak aby można było udostępniać konfiguracje dla modułów ocen i recenzji na wielu stronach PDP w witrynie e-Commerce, należy zapoznać się z [Omówienie szablonów i układów](templates-layouts-overview.md).

Na poniższej ilustracji pokazano, jak w oknie dialogowym **Dodaj moduł** są prezentowane moduły ocen i recenzji w Dynamics 365 Commerce.

![Dodaj moduł okna dialogowego](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Napisz moduł recenzji

Moduł zapisu recenzji zawiera przycisk **Napisz recenzję**, który pozwala użytkownikom zalogować się, przypisać ocenę i napisać recenzję produktu. Moduł ten pozwala również edytować wcześniej przesłane oceny lub recenzje. Ten moduł zazwyczaj pojawia się nad histogramem ocen i modułami listy recenzji produktów na PDP.

Poniższa ilustracja pokazuje okno dialogowe **Napisz recenzję**, które pojawia się, gdy klient wybierze **Napisz recenzję**. Odbiorca może użyć tego okna dialogowego do przesłania ocen i recenzji.

![Napisz okno dialogowe recenzji](media/rnr-eCommerce-write-review-module.png)

W poniższej tabeli przedstawiono właściwość modułu recenzji zapisu, którą należy skonfigurować w narzędziu do tworzenia treści.

| Nazwa właściwości | Wartość        | Opis właściwości                 |
|---------------|--------------|--------------------------------------|
| Nazwisko          | Napisz recenzję | Nazwa modułu pisania recenzji. |

### <a name="ratings-histogram-module"></a>Moduł histogramu ocen

W module histogramu ocen jest wyświetlany histogram klasyfikacji. Ten moduł zwykle pojawia się między modułem recenzji zapisu a modułem listy recenzji produktów na PDP.

Moduł histogramu ocen nie wymaga konfiguracji. Wystarczy dodać moduł do szablonu PDP. 

Poniższe ilustracje pokazują, jak wygląda szablon PDP w Dynamics 365 Commerce, gdy moduły ocen i recenzji są skonfigurowane do wyświetlania na PDP.

![Szablon PDP, gdy oceny i recenzje są skonfigurowane do wyświetlania na PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Moduł listy recenzji produktów

Moduł listy recenzji produktów pokazuje listę recenzji produktów wraz z opcjami sortowania, filtrowania i paginacji. Ten moduł zazwyczaj znajduje się po module histogramu ocen na PDP.

Poniższa tabela pokazuje właściwości modułu listy recenzji produktów, które należy skonfigurować w narzędziu do tworzenia treści.

| Nazwa właściwości              | Wartość | Opis właściwości |
|----------------------------|-------| ---------------------|
| Recenzje pokazywane na każdej stronie | 10    | Liczba recenzji, które powinny być pokazywane jednocześnie na PDP. Przyciski **Następne** i **Poprzednie** są dołączone, dzięki czemu użytkownicy mogą poruszać się po stronach recenzji. |

#### <a name="ratings-histogram--summary-view"></a>Histogram ocen — Widok podsumowania

Moduł listy recenzji produktów zawiera miejsce, w którym można dodać moduł histogramu ocen. Poniższa ilustracja pokazuje, jak można dodać moduł histogramu ocen w module listy recenzji produktów w Dynamics 365 Commerce.

![Dodawanie modułu histogramu ocen w module listy recenzji produktów](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Skonfiguruj witrynę, aby wyświetlała oceny i recenzje

Wartości konfiguracji ocen i recenzji, takie jak identyfikator dzierżawcy, długość tekstu recenzji i długość tytułu recenzji, są konfigurowane na poziomie witryny. 

Aby skonfigurować witrynę do wyświetlania ocen i recenzji, wykonaj następujące kroki. 

1. Przejdź do **Widok główny \> Strony**.
1. Wybierz nazwę swojej witryny. 
1. Przejdź do **Zarządzanie witryną \> Możliwości rozszerzania**. 
1. W polu **Maksymalna długość tekstu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tekst recenzji (na przykład **1000**). 
1. W polu **Maksymalna długość tytułu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tytuł recenzji (na przykład **55**). 
1. Wybierz **Zapisz i opublikuj**. 

Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.

![Konfigurowanie witryny, aby wyświetlała oceny i recenzje](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Łączenie oceny produktu z sekcją recenzji w PDP

Ocena produktu jest wyświetlana pod tytułem produktu u góry PDP. Ocenę produktu można skonfigurować tak, aby była połączona z sekcją **Recenzje** tej samej strony PDP. 

Aby połączyć ocenę produktu z sekcją **Recenzje** PDP, należy wykonać następujące kroki.

1. Otwórz szablon PDP. 
1. Przejdź do **Ustawienia modułu kontenera pola zakupu**.
1. W **Polu zakupu** wybierz opcję **Oceny produktów**, a następnie zaznacz pole wyboru **Połącz kliknięcie z modułem pełnych ocen**.

Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.

![Łączenie oceny produktu z sekcją recenzji w PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Konfiguruj łącze do strony prywatność i zasady

Aby skonfigurować link do strony prywatności i zasad, wykonaj następujące kroki.

1. Przejdź do **Widok główny \> Strony**.
1. Wybierz nazwę swojej witryny. 
1. Przejdź do **Zarządzanie witryną \> Możliwości rozszerzania**
1. Na karcie **Marszruty** w obszarze **RNR prywatność i zasady** wybierz opcję **Dodaj łącze**. Jeśli łącze zostało już wprowadzone i ma zostać zamienione, należy zaznaczyć łącze. 
1. W oknie dialogowym **Dodawj łącze** wybierz łącze do strony prywatność i zasady, a następnie kliknij przycisk **OK**. 
1. Wybierz **Zapisz i opublikuj**. 

Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.

![Konfiguracja łącza do strony prywatność i zasady](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail](sync-product-ratings.md)
