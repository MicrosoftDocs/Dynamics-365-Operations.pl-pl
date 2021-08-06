---
title: Zastosuj ustawienia wyświetlania dla wymiarów produktu
description: W tym temacie omówiono ustawienia wyświetlania wymiarów produktów i opisano sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 43f402c62cd7c9aab184152820e4fac9499c6f20
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638176"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Zastosuj ustawienia wyświetlania dla wymiarów produktu

[!include [banner](includes/banner.md)]


W tym temacie omówiono ustawienia wyświetlania wymiarów produktów i opisano sposób ich stosowania w Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce umożliwia używanie wymiarów typu rozmiar, styl i kolor do rozróżniania wariantów produktu. Wymiary są zwykle wyświetlane jako wartości tekstowe, takie jak „Mały”, „Średni” i „Duży” dla rozmiarów, oraz „Czarna” i „Brązowy” w przypadku kolorów. Jeśli jednak produkt posiada wiele wariantów, ich przeglądanie może być trudne, ponieważ do wyświetlenia obrazu dla każdego wariantu wymagane jest wielokrotne wybranie opcji. Aby ułatwić przeglądanie wariantów produktów, wersja 10.0.20 Commerce może używać obrazów i kodów szesnastkowych (hex), aby pokazać wymiary jako próbki.

W konstruktorze witryn. Commerce ustawienia wymiarów są definiowane w **Ustawienia witryny \> Rozszerzenia \> Zarządzanie zapasami**. Poniższa ilustracja pokazuje przykład ustawień wymiarów w programie do budowania witryn.

![Przykład ustawień witryny w kreatorze witryn Commerce.](./dev-itpro/media/swatch_site_settings.PNG)

Dostępne są dwa ustawienia wymiarów:

- **Wymiary wyświetlane jako obrazy** — Określeni, które wymiary powinny być wyświetlane jako próbki na stronach witryny e-commerce, takich jak strony szczegółów produktu (PDP) i strony z listą wyników wyszukiwania. Każda kombinacja kolorów, rozmiarów i stylów może być pokazana jako próbka. Jeśli wymiar zostanie wybrany do wyświetlenia jako próbka, moduł Commerce będzie szukał dostępnej konfiguracji próbki z kodem heksadecymalnym. Jeśli nie skonfigurowano kodu heksadecymalnego, logika systemu będzie szukać konfiguracji wzorca URL obrazu. Jeśli nie skonfigurowano ani kodu heksadecymalnego, ani adresu URL obrazu, zostanie wyświetlony tekst.

    Poniższa ilustracja przedstawia przykład, w którym PDP na stronie e-commerce zawiera próbki kolorów i rozmiarów. W tym przykładzie kod heksadecymalny jest skonfigurowany dla wymiaru koloru. W związku z tym próbki są wyświetlane jako kolory. Jednak ani kod heksadecymalny, ani adres URL obrazu nie są skonfigurowane dla wymiaru wielkości. W związku z tym jest wyświetlany tekst.

    ![Przykład wymiarów kolorów pokazanych jako próbki na stronie szczegółów produktu handlu elektronicznego.](./dev-itpro/media/swatch_pdp.png)

- **Wymiary wyświetlane na karcie produktu** — umożliwia określenie, które wymiary powinny być wyświetlane na kartach produktów widocznych na listach i na stronach list. Aby wymiar mógł pojawić się na karcie produktu, ustawienie to musi być włączone dla tego wymiaru. Należy również włączyć ustawienie **Wymiary wyświetlane jako obraz**. Zachowanie przy wyborze próbek na kartach produktów jest zoptymalizowane dla wymiaru kolorów. W przypadku innych wymiarów może być wymagane rozszerzenie widoku, aby dostosować zachowanie wyboru wzorca.

    Poniższa ilustracja przedstawia przykład, w którym strona z listą w witrynie e-commerce zawiera karty produktów zawierające próbki kolorów.

    ![Przykład wymiarów kolorów pokazanych jako próbki na listy produktu handlu elektronicznego.](./dev-itpro/media/swatch_searchresults.PNG)

Aby uzyskać więcej informacji na temat konfigurowania wymiarów produktów w taki sposób, aby były one wyświetlane jako próbki na stronach witryny, patrz [Konfigurowanie wartości wymiarów produktów, aby były wyświetlane jako próbki](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł wyników wyszukiwania](search-result-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Skonfiguruj wartości wymiarów produktu, aby były wyświetlane jako próbki](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
