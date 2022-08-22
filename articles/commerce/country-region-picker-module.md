---
title: Moduł wyboru kraju/regionu
description: W tym artykule omówiono moduł wyboru kraju/regionu i opisano, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 203a8e17e075f15b7ae3cceb98d24ced75539a01
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270299"
---
# <a name="countryregion-picker-module"></a>Moduł wyboru kraju/regionu

[!include [banner](includes/banner.md)]

W tym artykule omówiono moduł wyboru kraju/regionu i opisano, jak go skonfigurować w Microsoft Dynamics 365 Commerce.

Moduł wyboru kraju/regionu używa funkcji [wykrywania i przekierowywania geograficznego](geo-detection-redirection.md) w aplikacji Dynamics 365 Commerce do zalecanych adresów stron klientom, którzy wnioskują o adres URL witryny e-commerce, która nie jest skojarzona z ich krajem lub regionem.

Na przykład klient z Kanady żąda adresu URL witryny, który jest związany z innym krajem niż Kanada. W takim przypadku moduł wyboru kraju/regionu pokazuje okno dialogowe z zalecanymi adresami URL witryn skojarzonymi z Kanadą. 

## <a name="how-it-works"></a>Jak działa

Gdy dla witryny włączone jest wykrywanie geograficzne i przekierowanie, a klient zażąda adresu URL witryny, kraj, który został wykryty dla klienta, oraz żądany przez niego adres URL są wykorzystywane do określenia, czy ten adres URL jest odwzorowany na kraj, w którym znajduje się klient. Mapowanie między adresami URL i krajami jest definiowane na stronie **Kanały** w **ustawieniach witryny** w Konstruktorze witryn commerce. 

Jeśli adres URL żądania nie pasuje do żadnego adresu URL, który jest odwzorowany na kraj klienta, w odpowiedzi zwracana jest lista jednego lub więcej adresów URL, które są odwzorowane na ten kraj. Selektor krajów/regionów porównuje każdy adres URL z tej listy z adresami URL, które zostały skonfigurowane w module krajów/regionów. Dla każdego znalezionego dokładnego dopasowania selektor kraju/regionu renderuje nagłówek, podnagłówek i obrazek dla tego adresu URL oraz tworzy hiperłącza do tych elementów za pomocą adresu URL.

Gdy klient wybierze opcję w oknie wyboru kraju/regionu, zostanie przeniesiony do hiperłącza z adresem URL. Ten adres URL jest zapisywany w pliku cookie **\_msdyn365\_\_\_site\_**, aby można go było wykorzystać jako preferencje witryny klienta. Następnie, gdy następnym razem klient zażąda adresu URL, który nie jest powiązany z jego krajem lub regionem, zostanie automatycznie przekierowany do preferowanego kraju. Dlatego zalecamy korzystanie [z modułu wyboru witryn](site-selector.md) w witrynie e-commerce, aby odbiorcy mieli możliwość zastępowania lub aktualizowania preferencji w witrynie. 

Jeśli klient zamknie okno dialogowe wyboru kraju/regionu, plik cookie nie jest zapisywany, a klient pozostaje na bieżącej stronie. 

Poniższa ilustracja zawiera przykładowe okno dialogowe wyboru kraju/regionu.

![Przykład okna dialogowego wyboru kraju/regionu na stronie głównej.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Właściwości modułu wyboru kraju/regionu

| Nazwa właściwości              | Wartość       | opis                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Nagłówek                    | Tekst        | Nagłówek wyświetlany w górnej części okna dialogowego.       |
| Nagłówek podrzędny                 | Tekst        | Nagłówek podrzędny wyświetlany pod nagłówkiem.               |
| Kraj: ciąg wyświetlany    | Tekst        | Nazwa wyświetlana opcji adresu URL (na przykład „Kanada”).   |
| Kraj: wyświetlany ciąg podrzędny | Tekst        | Opcjonalny wyświetlany ciąg podrzędny dla opcji adresu URL (na przykład „Angielski” lub „Francuski”). |
| Kraj: obraz kraju     | Zasób multimedialny | Opcjonalny obraz skojarzony z opcją adresu URL (na przykład obraz flagi kanadyjskiej). |
| Kraj: adres URL kraju       | Tekst        | Adres URL witryny dla konfigurowanego kraju/regionu. Ten adres URL musi dokładnie odpowiadać adresowi URL określonego dla tego kraju/regionu na stronie **Kanały** w obszarze **Ustawienia witryny** w Konstruktorze witryn Commerce. Dodatkowo domena w adresie URL musi być domeną własną, która została określona w polu **Dopasuj domenę** na stronie **Kanały** , a nie adresem roboczym strony, który Commerce podaje podczas tworzenia środowiska e-commerce (np. URL `https://<yourcompany>.commerce.dynamics.com/`). |
| Link akcji                | Link akcji | Opcjonalny link wyświetlany u dołu okna dialogowego. Ten link może na przykład wskazać stronę wewnętrzną, na przykład z listą wszystkich krajów i regionów, które obsługuje ta witryna. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Dodawanie modułu wyboru kraju/regionu do strony

Moduł wyboru kraju/regionu można dodać do modułu nagłówka bezpośrednio lub za pośrednictwem udostępnionego fragmentu. Aby uzyskać więcej informacji o modułach nagłówka, skorzystaj z tematu [Moduł nagłówka](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Konfigurowanie modułu wyboru kraju/regionu w konstruktorze witryn rozwiązania Commerce

> [!NOTE]
> Adresy URL polecane klientom muszą być skonfigurowane jako obiekty krajów w module wyboru kraju/regionu.

W przypadku każdego adresu URL strony, który ma być pokazywany i polecany klientom, wykonaj poniższe kroki w konstruktorze witryn rozwiązania Commerce.

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
