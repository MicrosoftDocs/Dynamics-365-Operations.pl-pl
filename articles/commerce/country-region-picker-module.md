---
title: Moduł wyboru kraju/regionu
description: W tym temacie omówiono moduł wyboru kraju/regionu i opisano, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 1a8eebb589372051272573895a0ae5b4203eef62
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109788"
---
# <a name="countryregion-picker-module"></a>Moduł wyboru kraju/regionu

[!include [banner](includes/banner.md)]

W tym temacie omówiono moduł wyboru kraju/regionu i opisano, jak go skonfigurować w Microsoft Dynamics 365 Commerce.

Moduł wyboru kraju/regionu używa funkcji [wykrywania i przekierowywania geograficznego](geo-detection-redirection.md) w aplikacji Dynamics 365 Commerce do zalecanych adresów URL klientom, którzy wnioskują o adres URL witryny e-commerce, która nie jest skojarzona z ich krajem lub regionem.

Na przykład odbiorca z Kanady prosi o adres URL witryny, który nie jest skojarzony z Kanadą. W takim przypadku moduł wyboru kraju/regionu pokazuje okno dialogowe z zalecanymi adresami URL witryn skojarzonymi z Kanadą. Poniższa ilustracja zawiera przykładowe okno dialogowe wyboru kraju/regionu.

![Przykład okna dialogowego wyboru kraju/regionu na stronie głównej.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Właściwości modułu wyboru kraju/regionu

| Nazwa właściwości              | Wartość       | opis |
| -------------------------- | ----------- | ----------- |
| Nagłówek                    | Tekst        | Nagłówek wyświetlany w górnej części okna dialogowego. |
| Nagłówek podrzędny                 | Tekst        | Nagłówek podrzędny wyświetlany pod nagłówkiem. |
| Kraj: ciąg wyświetlany    | Tekst        | Nazwa wyświetlana opcji adresu URL (na przykład „Kanada”). |
| Kraj: wyświetlany ciąg podrzędny | Tekst        | Opcjonalny wyświetlany ciąg podrzędny dla opcji adresu URL (na przykład „Angielski” lub „Francuski”). |
| Kraj: obraz kraju     | Zasób multimedialny | Opcjonalny obraz skojarzony z opcją adresu URL (na przykład obraz flagi kanadyjskiej). |
| Kraj: adres URL kraju       | Tekst        | Adres URL odpowiadający kanałowi i ustawieniom regionalnym skonfigurowanym dla kraju lub regionu na stronie **Kanały** w konstruktorze witryn Commerce (**Ustawienia witryny \> Kanały**). Ten adres URL musi dokładnie odpowiadać adresowi URL skonfigurowanemu na stronie **Kanały**. |
| Link akcji                | Link akcji | Opcjonalny link wyświetlany u dołu okna dialogowego. Ten link może na przykład wskazać stronę wewnętrzną, na przykład z listą wszystkich krajów i regionów, które obsługuje ta witryna. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Dodawanie modułu wyboru kraju/regionu do strony

Moduł wyboru kraju/regionu można dodać do modułu nagłówka bezpośrednio lub za pośrednictwem udostępnionego fragmentu. Aby uzyskać więcej informacji o modułach nagłówka, skorzystaj z tematu [Moduł nagłówka](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Konfigurowanie modułu wyboru kraju/regionu w konstruktorze witryn rozwiązania Commerce

> [!NOTE]
> Adresy URL polecane klientom muszą być skonfigurowane jako obiekty krajów w module wyboru kraju/regionu.

W przypadku każdego adresu URL, który ma być pokazywany i polecany klientom, wykonaj poniższe kroki w konstruktorze witryn rozwiązania Commerce.

1. Wybierz miejsce na moduł wyboru kraju/regionu.
1. W okienku właściwości w obszarze **Lista krajów** wybierz pozycję **Dodaj kraj**.
1. Zaznacz nowe pole **Kraj**.
1. W polu **Wyświetlany ciąg** wprowadź nazwę wyświetlaną (na przykład **Kanada**).
1. Opcjonalnie: w polu **Wyświetlany podciąg** wprowadź wyświetlany podciąg (na przykład **Francuski** lub **fr-ca**).
1. Opcjonalnie: wybierz obraz z biblioteki multimediów.
1. W polu **Adres URL kraju** wprowadź adres URL. Ten adres URL musi dokładnie odpowiadać adresowi URL wyświetlanego na stronie **Kanały** i jest mapowany na kanał, w tym ustawienia lokalne skojarzone z danym krajem lub regionem.
1. Kliknij przycisk **OK**.
1. Powtórz te kroki dla wszystkich innych adresów URL krajów, które mają być wyświetlane w module wyboru kraju/regionu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie wykrywania i przekierowywania lokalizacji geograficznej](geo-detection-redirection.md)

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł nagłówka](author-header-module.md)

[Moduł selektora witryn](site-selector.md)

[Moduł szlaków nawigacyjnych](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
