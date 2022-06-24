---
title: Skonfiguruj wartości wymiarów produktu, aby były wyświetlane jako próbki
description: W tym artykule opisano, jak skonfigurować wartości wymiarów produktów jako próbki w centrum Microsoft Dynamics 365 Commerce headquarters.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.openlocfilehash: a21e02a8e5aacfa5251b9b7bcbc451fa886d37f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892659"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Skonfiguruj wartości wymiarów produktu, aby były wyświetlane jako próbki

[!include [banner](../../includes/banner.md)]

W tym artykule opisano, jak skonfigurować wartości wymiarów produktów jako próbki w centrum Microsoft Dynamics 365 Commerce headquarters. Aby uzyskać więcej informacji o wymiarach produktu, należy zapoznać się z artykułem [Wymiary produktów](../../supply-chain/pim/product-dimensions.md).

Dynamics 365 Commerce umożliwia używanie wymiarów typu rozmiar, styl i kolor do reprezentowania wariantów produktu. Wymiary produktu mają przyjazne nazwy, które są wyświetlane na stronach szczegółów produktu (PDP), aby można było wybrać warianty produktu. Przykładami tych przyjaznych nazw są „Małe”, „Średnie” i „Duże” dla rozmiarów oraz „Czarny” i „Brązowy” w przypadku kolorów. Jeśli jednak produkt posiada wiele wariantów, do wyświetlenia obrazu dla każdego wariantu wymagane jest wielokrotne wybranie opcji. Dlatego przeglądanie i wybieranie wariantów produktów może być dla klientów powolne i uciążliwe.

Gdy wymiary są pokazywane jako próbki na PDP, klienci otrzymują wizualny podgląd wariantów produktu. Mogą oni z łatwością przeglądać szeroką gamę kolorów, wzorów i faktur, a także szybko zobaczyć różne kombinacje wariantów produktów.

Funkcja wyświetlania wymiarów jako próbek pozwala Commerce używać kodów szesnastkowych (hex) i obrazów do wyświetlania wymiarów jako próbek. Dodatkowo, podobne wymiary, takie jak kolory, mogą być grupowane na stronach z listą produktów. Odbiorca wyszukuje na przykład produkty, które są niebieskie. Jeśli różne wartości wymiaru niebieskiego zostaną pogrupowane razem, na stronie z listą wyników wyszukiwania zostaną wyświetlone produkty, które mają różne odcienie niebieskiego. Grupowanie wymiarów znacząco poprawia doświadczenia związane z wyszukiwaniem produktów i pomaga klientom znaleźć więcej produktów poprzez pojedyncze zapytanie.

> [!NOTE]
> Funkcja wyświetlania wymiarów jako próbek jest dostępna od wersji 10.0.20 Dynamics 365 Commerce.

Na poniższej ilustracji pokazano przykład, w którym kolory są wyświetlane jako próbki w programie Commerce PDP.

![Przykład kolorów pokazanych jako próbki na stronie szczegółów produktu.](../dev-itpro/media/swatch_pdp.png)

Poniższa ilustracja przedstawia przykład, w którym kolory pojawiają się jako próbki na stronie z listą wyników wyszukiwania Commerce.

![Przykład kolorów wyświetlanych jako próbki na stronie z listą wyników wyszukiwania.](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>Włącz funkcję wyświetlania wymiarów jako próbki w centrali Commerce

Aby włączyć funkcję wyświetlania wymiarów jako próbek w centrali Commerce, przejdź do **Obszary robocze \> Zarządzanie funkcjami** i włącz opcję **Włącz mechanizm do reprezentowania wymiarów jako próbek**. Gdy ta flaga jest włączona, dla każdego wymiaru dodawane są trzy nowe pola w odpowiednich tabelach w centrali Commerce: **Kod szesnastkowy**, **URL** (dla obrazów) oraz **GrupaOkreślająca**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Skonfiguruj wartości wymiarów w centrali Commerce

Funkcja wyświetlania wymiarów jako próbek jest obsługiwana dla wymiarów rozmiaru, stylu i koloru. Wartości kodu heksadecymalnego i adresu URL obrazu dla odpowiednich wymiarów mogą być określone w centrali Commerce. Domyślnie, jeśli nie podano wartości kodu heksadecymalnego i adresu URL obrazu dla wymiaru, system wyświetli tekst przyjaznej nazwy wymiaru.

Konfiguracja może być przeprowadzona na każdym z poniższych poziomów:

- **Wymiar** — w centrali Commerce otwórz stronę wymiaru, wyszukując **kolor**, **rozmiar** lub **styl**. Na każdej stronie w siatce są podane wartości wymiarów. Użytkownik może zarządzać kolejnością wyświetlania, kodem szesnastkowym i wartościami adresu URL obrazu. Na poniższej ilustracji pokazano przykład konfiguracji na stronie **Kolory**.

    ![Przykład konfiguracji wymiarów na stronie Kolory.](../dev-itpro/media/swatch_Color.PNG)

- **Grupa wymiarów** — w Dynamics 365 Commerce za jej pomocą można tworzyć grupy wymiarów za pomocą właściwości **GrupaOkreślająca**. Jeśli zdefiniowano grupy wymiarów, otwórz odpowiednią stronę, wyszukując **grupę kolorów**, **grupę rozmiarów** lub **grupę stylów**. Na każdej stronie można zarządzać kodami heksadecymalnymi, adresami URL obrazów i wartościami grup określenia. Na poniższej ilustracji pokazano przykład konfiguracji na stronie **Grupy kolorów**.

    ![Przykład konfiguracji wymiarów na stronie Grupy kolorów.](../dev-itpro/media/swatch_colorGroup.PNG)

- **Wymiar produktu (podczas tworzenia produktu)** — podczas tworzenia nowego produktu można wprowadzić wartości wymiarów za pomocą strony **Wymiary produktu**. W przypadku istniejących produktów mogą już być ustawione pola **kod szesnastkowy**, **URL** (w przypadku obrazów) i **GrupaOkreślająca**. Wartości te można jednak zmieniać według własnych potrzeb. Na poniższej ilustracji pokazano przykład konfiguracji na stronie **Wymiary produktu**.

    ![Przykład konfiguracji wymiarów na stronie Wymiary produktu.](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> Proces zarządzania konfiguracjami kodów heksadecymalnych i adresów URL obrazów przebiega według tego samego schematu, który jest używany do zarządzania kolejnością wyświetlania wymiarów.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Konfiguracja wartości wymiarów za pomocą kodów heksadecymalnych

Dla większości wymiarów kolorów, wartość koloru w kodzie heksadecymalnym powinna być podana na stronach wymiarów w centrali Commerce. Na przykład kolor czarny powinien mieć wartość **#00000**. Kiedy Commerce renderuje stronę, kod heksadecymalny jest reprezentowany przez kolorowy pasek.

Na poniższej ilustracji przedstawiono przykład, w którym wymiary kolorów są konfigurowane za pomocą wartości kodów heksadecymalnych.

![Przykład konfiguracji wymiarów z wykorzystaniem kodów heksadecymalnych.](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Konfiguruj wartości wymiarów za pomocą adresów URL obrazów

Niektóre wymiary kolorów reprezentują wzory, a nie jednolite kolory. Na przykład wymiar koloru może być opisany jako „lamparci”. W takich przypadkach można bardziej efektywnie przedstawić wymiary kolorów, używając opublikowanych obrazów zamiast kodów heksadecymalnych dla próbek.

Musisz załadować każdy obrazek do kreatora stron Commerce i opublikować go. Następnie wprowadź adres URL opublikowanego obrazu na odpowiednich stronach wymiarowych w centrali Commerce. Jeśli wymiar został wybrany do wyświetlenia jako próbka, ale kod heksadecymalny nie został zdefiniowany, Commerce wykona wyszukiwanie obrazu podczas renderowania strony. Jeśli wyszukiwanie obrazu nie powiedzie się, Commerce wyświetli tekst przyjaznej nazwy wymiaru.

Poniższa ilustracja przedstawia przykład, w którym adresy URL obrazów są używane do konfiguracji na stronie **Kolory**.

![Przykład konfiguracji wymiaru wykorzystującej adresy URL obrazów.](../dev-itpro/media/swatch_color_urls.PNG)

Możesz użyć szablonu mediów, aby zdefiniować adresy URL obrazów, tak samo jak w przypadku obrazów produktów i kategorii. Kiedy przesyłasz obrazy do kreatora stron, konwencje nazw plików i ścieżek muszą być spójne.

Na poniższej ilustracji przedstawiono przykład, w którym adresy URL obrazów są używane do konfiguracji szablonu multimediów.

![Przykład konfiguracji szablonu nośnika.](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Konfiguruj wartości wymiarów, używając zarówno kodów heksadecymalnych, jak i adresów URL obrazów

Dla większości wymiarów kolorów można skonfigurować zarówno kody heksadecymalne, jak i adresy URL obrazów. Logika renderowania Commerce będzie automatycznie szukała kodu heksadecymalnego lub adresu URL obrazu, aby pokazać próbkę koloru. Używając zarówno kodów heksadecymalnych, jak i adresów URL obrazów do konfigurowania wymiarów kolorów, upraszczasz zarządzanie obrazami, gdy liczba kolorów jest duża.

Poniższa ilustracja przedstawia przykład, w którym adresy URL obrazów i kody szesnastkowe są używane do konfiguracji na stronie **Kolory**.

![Przykład konfiguracji wymiaru wykorzystującej zarówno kody heksadecymalne, jak i adresy URL obrazów.](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Konfiguracja grup określenia

Kiedy określasz kod heksadecymalny lub adres URL obrazu dla wartości wymiaru, możesz również określić wartość dla pola **GrupOkreślająca**. To pole definiuje wymiar, który powinien być użyty do grupowania podobnych wartości wymiarów w doświadczeniu zawężania.

Jeśli na przykład wartości wymiarów koloru to „niebieski”, „niebieska kratka”, „niebieski sprany” i „ciemnoniebieski”, każda wartość jest mapowana na inny kod heksu lub adres URL obrazu. Dlatego każda wartość będzie wyświetlana jako inny kolor na PDP i kartach produktów dla odpowiednich produktów. Jeśli jednak zmapujesz wszystkie te wartości wymiarów kolorów do **GrupaOkreślająca** o wartości **Niebieski**, wyszukiwanie produktów „niebieskich” wygeneruje wyniki wyszukiwania na stronie listy produktów, które mają wartości wymiarów kolorów „niebieski”, „niebieska kratka”, „niebieski sprany” i „ciemnoniebieski”.

Przykład na poniższej ilustracji przedstawia zależność pomiędzy właściwościami **Kolor** i **GrupaOkreślająca** w centrali Commerce.

![Przykład zarządzania grupą określającą.](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Zarządzanie obrazami w kreatorze stron Commerce

Jeśli dla któregoś z wymiarów używane są adresy URL obrazów, odpowiednie obrazy muszą zostać załadowane do kreatora stron Commerce. Lokalizacja każdego obrazu powinna odpowiadać nazwie pliku i ścieżce do folderu, które zostały zdefiniowane dla obrazu w centrali Commerce. Pliki graficzne muszą być załadowane do odpowiednich lokalizacji kategorii w kreatorze stron. Na przykład, kolorowe zdjęcia muszą być załadowane do folderu kategorii **Kolor**. Aby uzyskać więcej informacji na temat przekazywania obrazów do konstruktora witryn, należy zapoznać się z tematem [Przekazywanie obrazów](../dam-upload-images.md).

Poniższa ilustracja pokazuje przykład, w którym okno dialogowe **Przekaż pliki** jest używane do przesyłania obrazów do biblioteki multimediów kreatora witryny. Podświetla kategorie **Rozmiar**, **Kolor** oraz **Styl**, które są dostępne do wyboru.

![Przykład kategorii plików graficznych podczas wgrywania do biblioteki mediów kreatora strony.](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>Włącz wyświetlanie próbek na stronach witryn e-commerce

Zanim próbki pojawią się na stronach witryny e-commerce, które wymagają wyboru wymiaru, takich jak PDP i strony z listą, musisz skonfigurować ustawienia strony wymiaru w siedzibie Commerce. Aby uzyskać więcej informacji, zobacz temat [Zastosuj ustawienia witryny do wymiarów](../dimension-settings.md).

Dodatkowo należy włączyć właściwość **Uwzględnianie atrybutów produktów w wynikach wyszukiwania** dla modułów wyników wyszukiwania. Jeśli twoja witryna używa niestandardowych stron kategorii, należy zaktualizować moduły wyników wyszukiwania, które są używane na tych stronach, tak aby właściwość **Uwzględniaj atrybuty produktów w wynikach wyszukiwania** była włączona. Aby uzyskać więcej informacji, zajrzyj do [Moduł wyników wyszukiwania](../search-result-module.md).

## <a name="inventory-awareness-on-swatches"></a>Świadomość ekwipunku na próbach

Próbki mają opcjonalną możliwość wyświetlania dostępności zapasów koloru lub wymiaru wariantu produktu. Na przykład produkt jest sprzedawany w wielu rozmiarach, ale niektóre rozmiary są niedostępne. W takim przypadku próbki produktów niedostępnych są renderowane inaczej, aby wskazać, że nie są dostępne. Ta funkcja pomaga zmniejszyć liczbę kliknięć klientów, które są wymagane do określenia dostępności produktu.

Funkcję dostępności zapasów próbek można skonfigurować do użycia zarówno na PDP, jak i na stronach listy wyszukiwania lub kategorii, na których są wyświetlane próbki. Aby go aktywować, należy ustawić właściwość **Aktualizuj nośnik na zaznaczeniu wymiaru** na Wartość **True** w [module galerii multimediów](../media-gallery-module.md). To ustawienie umożliwia aktualizowanie obrazów galerii multimediów po wybraniu wymiarów. 

> [!IMPORTANT]
> Ta funkcja jest dostępna w Commerce od wersji 10.0.21. Wymaga, pakietu biblioteki modułów Commerce w wersji 9.31.

Na poniższej ilustracji przedstawiono przykład świadomości zapasów na próbki rozmiaru PDP.

![Przykład świadomości zapasów na próbach rozmiaru PDP](../dev-itpro/media/swatch_inventory.png)

## <a name="display-swatches-in-pos-and-other-channels"></a>Wyświetlanie próbek w punktach sprzedaży i innych kanałach

Commerce nie posiada obecnie implementacji dostępnej natychmiast, która wspiera wyświetlanie próbek w punktach sprzedaży (POS) i innych kanałach. Można jednak zaimplementować funkcjonalność wyświetlania próbek jako rozszerzenie, które sprawia, że interfejsy API kanału zwracają kody heksadecymalne i adresy URL obrazów, które są wymagane do renderowania próbek.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł wyników wyszukiwania](../search-result-module.md)

[Zastosuj ustawienia witryny do wymiarów](../dimension-settings.md)

[Wymiary produktu](../../supply-chain/pim/product-dimensions.md)

[Przekaż obraz](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
