---
title: Zarządzanie atrybutami i grupami atrybutów
description: W tym artykule opisano sposób zarządzania atrybutami i grupami atrybutów w celu opisywania produktów i ich charakterystyk w programie Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386980"
---
# <a name="manage-attributes-and-attribute-groups"></a>Zarządzanie atrybutami i grupami atrybutów

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób zarządzania atrybutami i grupami atrybutów w celu opisywania produktów i ich charakterystyk w programie Microsoft Dynamics 365 Commerce.

*Atrybuty* umożliwiają sposób opisania produktów i ich charakterystykę w polach definiowanych przez użytkownika. Przykłady: rozmiar pamięci, pojemność dysku twardego i zgodność z oceną Energy Star.

Atrybuty można skojarzyć z różnymi jednostkami usługi Commerce, takimi jak kategorie produktu i kanały handlu oraz ustawić ich wartości domyślne. Produkty dziedziczą atrybuty i wartości domyślne, gdy atrybuty te są powiązane z kategoriami produktów lub kanałami. Wartości domyślne atrybutów można zastąpić na poziomie poszczególnych produktów, na poziomie kanału lub w katalogu.

Na przykład typowy produkt w postaci telewizora może mieć następujące atrybuty.

| Kategoria   | Atrybut           | Możliwe wartości                        | Wartość domyślna |
|------------|---------------------|-------------------------------------------|---------------|
| Telewizja i wideo | Marka               | Dowolna prawidłowa nazwa marki                     | Żadne          |
| TV         | Rozmiar ekranu         | 20–85 cali                              | 55 cali     |
|            | Rozdzielczość w pionie | 4K (2160p), Full HD (1080p) lub HD (720p) | 4K (2160p)    |
|            | Częstotliwość odświeżania ekranu | 60hz, 120hz, lub 240hz                     | 60hz          |
|            | Wejścia HDMI         | 0–10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Atrybuty i typy atrybutów

Atrybuty są oparte na *typach atrybutów*. Typ atrybutu określa typ danych, które można wprowadzić dla określonego atrybutu. Następujące typy atrybutów są obsługiwane w rozwiązaniu Commerce:

- **Waluta** — ten typ obsługuje wartości waluty. Może być ograniczony (czyli obsługuje zakres wartości) lub może pozostać otwarty.
- **Data i godzina** — ten typ obsługuje wartości daty i godziny. Może być ograniczony lub pozostać otwarty.
- **Dziesiętna** — ten typ obsługuje wartości liczbowe, które zawierają miejsca dziesiętne. Obsługuje również jednostki miary. Może być ograniczony lub pozostać otwarty.
- **Całkowita** — ten typ obsługuje wartości liczbowe. Obsługuje również jednostki miary. Może być ograniczony lub pozostać otwarty.
- **Tekst** — ten typ obsługuje wartości tekstowe. Obsługuje także wstępnie zdefiniowany zestaw możliwych wartości, gdy jest włączone ustawienie **Stała lista**.
- **Logiczna** — ten typ obsługuje wartości binarne (**prawda** lub **fałsz**).
- **Odwołanie** — ten typ odwołuje się do innych atrybutów.

> [!NOTE]
> Z powodu [ograniczeń indeksu wyszukiwania Azure Search](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search) typ atrybutu **Dziesiętny** nie jest obsługiwany w przypadku wyszukiwania w chmurze. Usługa Azure Cognitive Search nie obsługuje konwersji typów atrybutów **Dzięsiętne** na typy pól indeksu docelowego **Edm.Double**, ponieważ ta konwersja spowoduje zmniejszenie precyzji.

### <a name="set-up-attribute-types"></a>Ustawianie typów atrybutów

Aby skonfigurować typy atrybutów, wykonaj kroki opisane w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Ustawienia \> Kategorie i atrybuty \> Typy atrybutów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa typu atrybutu** wprowadź **Typ torby**.
1. W polu **Typ** zaznacz opcję **Tekst**.
1. Ustaw wartość **Stała lista** na wartość **Tak**.
1. Na skróconej karcie **Wartości** wybierz pozycję **Dodaj**.
1. W nowym wierszu w polu **Wartość** wprowadź **Tornister**.
1. Dodaj pięć wierszy więcej. W każdym polu **Wartość** wprowadź inną wartość: **Kopertówka**, **Torebka**, **Plecak**, **Torba kurierska** lub **Portfel**.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa typu atrybutu** wprowadź **Marka okularów przeciwsłonecznych**.
1. W polu **Typ** zaznacz opcję **Tekst**.
1. Ustaw wartość **Stała lista** na wartość **Tak**.
1. Na skróconej karcie **Wartości** wybierz pozycję **Dodaj**.
1. W nowym wierszu w polu **Wartość** wprowadź **Ray ban**.
1. Dodaj dwa wiersze więcej. W polu **Wartość** każdej z nich wprowadź inną wartość: **Aviator** lub **Oakley**.
1. Na okienku akcji wybierz opcję **Zapisz**.

![Strona typów atrybutów.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Ustawianie atrybutu

Aby skonfigurować atrybut, wykonaj kroki opisane w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Ustawienia \> Kategorie i atrybuty \> Atrybuty**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wpisz **Typ torby**.
1. W polu **Typ atrybutu** zaznacz opcję **Typ torby**.
1. Na okienku akcji wybierz opcję **Zapisz**.

![Strona atrybutów.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Metadane atrybutu

*Metadane atrybutów* umożliwiają wybranie opcji określających, jak mają się zachować atrybuty każdego produktu. Można na przykład wskazać, czy atrybuty są wymagane, czy mogą być używana w wyszukiwaniach i czy można ich używać jako filtrów.

Dla produktów ustawienia metadanych atrybutów mogą być zastępowane na poziomie kanału.

Strona **Atrybuty** atrybutu zawiera kilka opcji powiązanych z metadanymi atrybutów. Na przykład po skonfigurowaniu opcji **Może być doprecyzowane** na **Tak** w **Metadanych atrybutów dla kanałów Commerce**, atrybut ten zostanie pokazany w celu doprecyzowania lub filtrowania produktów w wynikach wyszukiwania i stronach przeglądania kategorii. Aby skonfigurować atrybut jako możliwy do doprecyzowania, należy najpierw wybrać **Ustawienia filtra** w okienku akcji i potwierdzić ustawienia filtra dla atrybutu.

## <a name="filter-settings-for-attributes"></a>Ustawienia filtrów atrybutów

Ustawienia filtrów atrybutów pozwalają określić sposób, w jaki filtry atrybutów są wyświetlane w punkcie sprzedaży. Aby uzyskać dostęp do ustawień filtrów atrybutów, na stronie **Atrybuty** atrybutu w okienku akcji wybierz opcję **Ustawienia filtra**.

Strona **Ustawienia filtra** zawiera następujące pola:

- **Nazwa** — to pole jest domyślnie ustawione na nazwę atrybutu. Można jednak zmienić jego wartość.
- **Opcja wyświetlania** — dostępne są następujące opcje:

    - **Jedna wartość** — ta opcja jest dostępna dla następujących typów atrybutów: **Logiczna**, **Waluta**, **Dziesiętna**, **Całkowita** i **Tekst**. Pozwala ona wybrać tylko jedną wartość do udoskonalenia na stronach list produktów, takich jak przeglądanie kategorii i strony wyników wyszukiwania produktów.
    - **Wiele wartości** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna**, **Całkowita** i **Tekst**. Umożliwia to wybór wielu wartości dla atrybutu na kliencie w celu doprecyzowania.

- **Sterowanie wyświetlaniem** — dostępne są następujące opcje:

    - **Lista** — ta opcja jest dostępna dla wszystkich typów atrybutów.
    - **Zakres** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna** i **Całkowita**.
    - **Suwak** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna** i **Całkowita**.
    - **Suwak z paskami** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna** i **Całkowita**.

- **Wartość progowa** — to ustawienie jest wymagane, jeśli jako typ sterowania wyświetlaniem wybrano opcję **Zakres**. W celu zdefiniowania wartości można użyć średnika (;) jako separatora.

    Na przykład dla atrybutu **Objętość torby**, który ma typ atrybutu **Liczba całkowita**, wartość progowa może być liczbą **10; 20; 50; 100; 200; 500; 1000; 5000**. W tym przypadku w POS będą wyświetlane następujące zakresy. Zakresy, które w zbiorze wyników nie mają żadnych produktów, będą wyświetlane jako wygaszone.

    - Mniej niż 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - Ponad 500

Ustawienia filtru dla atrybutów mają zastosowanie tylko do atrybutów produktu i mogą być używane do ulepszania wyników wyszukiwania produktów i przeglądania kategorii. Nie dotyczą one wyszukiwania klienta ani wyszukiwania zamówień, jednak tych samych atrybutów można użyć w celu wzbogacania informacji o odbiorcy lub zamówieniu.

W domyślnych modułach Commerce nie są od razu dostępne dla ustawienia filtra **Kontrola wyświetlania**, takie jak **Zakres**, **Suwak** i **Suwak z paskami** Ustawienia **Zakres** i **Suwak** nadal są obsługiwane w przypadku rozwiązań w punkcie sprzedaży, podczas gdy ustawienie **Suwak z paskami** jest stosowane do starszych sklepów internetowych SharePoint i nadal jest dostępne w przypadku integracji z innymi firmami i scenariuszy niestandardowych.

Zaleca się, aby atrybuty rozszerzone miały atrybut typu **Tekst**, gdzie jest włączona opcja **Stała lista**, i aby lista była rozsądna (maksymalnie 100–200 unikatowych wartości). Jeśli ulepszanie będzie mieć co najmniej 1000 unikatowych wartości, bardziej odpowiednie jest użycie atrybutu typu **Tekst**, w którym opcja **Stała lista** jest wyłączona.

Tłumaczenia mają krytyczne znaczenie w nazwach atrybutów i ich wartościach. W przypadku atrybutów typu **Tekst** z włączoną opcją **Stała lista** można definiować tłumaczenia wartości atrybutów w obszarze **Typ atrybutu**. Dla każdego innego typu atrybutu można zdefiniować tłumaczenia na stronie, na której definiuje się wartości atrybutów. Na przykład dla atrybutu typu **Tekst** można zdefiniować tłumaczenia wartości domyślnej na stronie **Atrybuty** atrybutu. Jednak w przypadku zastąpienia wartości domyślnej na poziomie produktu można zdefiniować tłumaczenia atrybutu na stronie **Atrybuty produktu**.

Po oznaczeniu atrybutu jako możliwego do doprecyzowania dla kanału, nie należy aktualizować typ atrybutu. W przeciwnym razie będzie to miało wpływ na publikację danych produktów w indeksie wyszukiwania. Zamiast tego zaleca się utworzenie nowego atrybutu dla nowego typu udoskonalenia i wycofanie poprzedniego atrybutu przez usunięcie go z innych grup atrybutów.

Wyszukiwanie według atrybutów jest obsługiwane, ale pobiera wyniki tylko w celu dokładnego dopasowania wyszukiwanych słów. Na przykład atrybut **Tkanina** ma wartość **Kaszmir bawełna**. Jeśli odbiorca wyszukuje „Gotówka”, nie zostaną pobrane żadne produkty z oznaczeniem tkaniny jako **Kaszmir bawełna**. Jednakże jeśli odbiorca wyszukuje „Kaszmir”, „Bawełna” lub „Bawełna kaszmir”, zostaną pobrane produkty z oznaczeniem tkaniny jako **Kaszmir**.

### <a name="additional-attribute-metadata-options"></a>Opcje metadanych dodatkowych atrybutów

> [!NOTE]
> Te opcje metadanych atrybutów mają zastosowanie tylko do starszych integracji sklepu internetowego SharePoint i integracji zewnętrznych. Aby uzyskać więcej informacji o tych opcjach metadanych atrybutów, zobacz [Omówienie schematu wyszukiwania w programie SharePoint Server 2013](/SharePoint/search/search-schema-overview).

Poniższe dodatkowe opcje metadanych atrybutów także dostępne na stronie **Atrybuty**:

- Z możliwością wyszukiwania
- Z możliwością pobierania
- Może być przedmiotem kwerendy
- Z możliwością sortowania
- Ignorowanie wielkości liter i formatu
- Pełne dopasowanie

Te opcje były pierwotnie przeznaczone do poprawy funkcji wyszukiwania w witrynach sklepów internetowych SharePoint w trybie online. Nie muszą one dotyczyć witryn handlu elektronicznego Commerce lub terminali punktów sprzedaży. Integracja bez kierownictwa jest nadal obsługiwana, więc te opcje są dostępne do eksportowania metadanych atrybutów za pomocą zestawu Commerce Software Development Kit (SDK). Zestaw SDK do Commerce umożliwia umieszczanie produktów w niestandardowy, zoptymalizowany indeks wyszukiwania zewnętrznego. W ten sposób można zagwarantować, że indeksowane będą tylko atrybuty, które powinny być indeksowane.

## <a name="attribute-groups"></a>Grupy atrybutów

*Grupa atrybutów* jest używana do grupowania indywidualnych atrybutów składnika lub podskładnika w modelu konfiguracji produktu. Ten sam atrybut można dołączyć do więcej niż jednej grupy atrybutów. Grupy atrybutów mogą pomóc użytkownikom konfigurować produkty, ponieważ różne opcje wyboru są rozmieszczane w określonym kontekście. Grupy atrybutów można przypisywać do kategorii i kanałów. Można również ustawić domyślne wartości dla atrybutów w grupie atrybutów.

![Strona grupy atrybutów.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Tworzenie grup atrybutów

Aby utworzyć grupę atrybutów, wykonaj kroki opisane w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Ustawienia \> Kategorie i atrybuty \> Grupy atrybutów**.
1. Utwórz grupę atrybutów o nazwie **Koszule**.
1. Dodaj następujące atrybuty: **Typ prania**, **Typ kołnierzyka**, **Kolekcja** i **Styl**.

> [!NOTE]
> Wartości kolejności wyświetlania atrybutów w grupie atrybutów nie mają wpływu na kolejność atrybutów w wynikach wyszukiwania i przeglądania kategorii ani do nich stosowane. Są one stosowane tylko do scenariusza „Atrybuty zamówienia”.

### <a name="assign-attribute-groups-to-categories"></a>Przypisywanie grup atrybutów do kategorii

Co najmniej jedna grupa atrybutów może być skojarzona z węzłami kategorii w następujących typach hierarchii kategorii:

- Hierarchia produktów handlowych
- Hierarchia kategorii nawigacji kanału
- Uzupełniająca hierarchia kategorii produktu

Gdy produkty są klasyfikowane w kategoriach skojarzonych z grupami atrybutów, dziedziczą one atrybuty zawarte w tych grupach atrybutów.

![Skrócona karta grup atrybutów produktu na stronie hierarchii produktów w rozwiązaniu Commerce.](media/AGRetailProdHierarchy_2022Series.png)

Aby przypisać grupy atrybutów do kategorii w hierarchii produktów Commerce, wykonaj następujące kroki w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Hierarchia produktów Commerce**.
1. Wybierz hierarchę nawigacji **Moda**.
1. W obszarze **Odzież męska** wybierz kategorię **Spodnie**, a następnie na skróconej karcie **Grupy atrybutów produktu** dodaj grupę atrybutów o nazwie **Pasek męski**.
1. Zaznacz kategorię **Modne okulary przeciwsłoneczne** i zweryfikuj nowe atrybuty w grupie atrybutów **Modne okulary przeciwsłoneczne**, wybierając opcję **Wyświetlenie atrybutów**. W grupie atrybutów powinny być teraz widoczne nowe atrybuty **Kształt soczewek** i **Marka okularów przeciwsłonecznych**.
1. Wybierz kategorię **Spodnie** i zweryfikuj atrybuty w grupie atrybutów **Pasek męski**, wybierając opcję **Wyświetl atrybuty**. W grupie atrybutów powinny być teraz widoczne atrybuty **Marka pasków męskich**, **Tkanina paska** i **Rozmiar paska**.

Tej samej podstawowej procedury można również użyć w celu przypisania grup atrybutów do kategorii w hierarchii kategorii nawigacji w kanale i hierarchii uzupełniających kategorii produktów. Jednak w kroku 2 należy użyć jednej z następujących ścieżek, w zależności od hierarchii, do której mają zostać przypisane grupy atrybutów:

- **Hierarchia kategorii nawigacji kanału:** przejdź do **Retail i Commerce \> Zarządzanie kategorią i produktem \> Kategorie nawigacji kanału**.
- **Uzupełniona hierarchia kategorii produktu:** przejdź do **Retail i Commerce \> Zarządzanie kategorią i produktem \> Uzupełnione kategorie produktu**.

> [!NOTE]
> Upewnij się, by skojarzyć tylko grupy atrybutów w hierarchii kategorii na skróconej karcie **Grupy atrybutów produktu**, a nie na skróconej karcie **Wartości atrybutów kategorii**. Jeśli atrybuty są wyświetlane na skróconej karcie **Wartości atrybutów kategorii**, wybierz pozycję **Edytuj hierarchię kategorii** w okienku akcji. Następnie na skróconej karcie **Grupy atrybutów kategorii** zaznacz węzły kategorii i wybierz pozycję **Usuń**. Brak obsługi pobierania atrybutów według kategorii za pomocą usługi Commerce Scale Unit.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Identyfikowanie dostępnych i rozszerzonych atrybutów kanałów rozwiązania Commerce dla domyślnej kolekcji produktów

Po skojarzeniu różnych grup atrybutów z kategoriami w różnych hierarchiach (hierarchia produktów Commerce lub kategorie nawigacji kanału) i zdefiniowaniu wartości atrybutów dla poszczególnych produktów, na podstawie skojarzenia kategorii należy włączyć flagę **Pokaż atrybut w kanale**, aby te atrybuty były wyświetlane w określonym kanale.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz **Ustaw metadane atrybutu**, a następnie wybierz atrybut w lewym okienku nawigacyjnym.
1. Na skróconej karcie **Atrybuty produktu kanału** (nie na skróconej karcie **Atrybuty kategorii**) ustaw dla opcji **Pokaż atrybut w kanale** wartość **Tak**, aby atrybut był dostępny do wyświetlania.
1. Jeśli atrybut ma również podlegać udoskonaleniu, należy ustawić opcję **Może być doprecyzowane** na wartość **Tak**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>Steruj widocznością udoskonalania opartą na wymiarach, takich jak rozmiar, styl i kolor

Najczęściej używane do doprecyzowania są wymiary produktu, takie jak rozmiar, styl i kolor. Aby udostępnić wymiary produktów jako udoskonalenia, należy skojarzyć grupę atrybutów na poziomie kanału, która zawiera odwołanie do typu atrybutu, który automatycznie dziedziczy wartości z wartości wymiaru produktu.

Można określić, że wymiary produktów można wyświetlać i ulepszać, aktualizując flagi na stronie **Kategorie kanału i atrybuty produktu**. Zaznacz węzeł główny w okienku nawigacji, a następnie na skróconej karcie **Atrybuty produktu kanału** ustaw opcję **Pokaż atrybut w kanale** dla atrybutów **Rozmiar**, **Styl** i **Kolor** na **Tak**. Jeśli chcesz, by te atrybuty można było doprecyzować, należy dla każdego z nich ustawić opcję **Może być doprecyzowane** na wartość **Tak**.

![Ustawianie metadanych atrybutów dla wymiarów doprecyzowania.](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

Aby włączyć atrybuty, tak aby były dostępne w kanale Houston opartym na danych demonstracyjnych, należy wykonać kroki w tej przykładowej procedurze.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz kanał **Houston**.
1. W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.
1. Wybierz węzeł kategorii **Moda**, a następnie na skróconej karcie **Atrybuty produktu kanału** dla każdego atrybutu wybierz opcję **Uwzględnienie atrybutu**.
1. Wybierz węzeł kategorii **Akcesoria modowe**, zaznacz kategorię **Modne okulary przeciwsłoneczne**, a następnie na skróconej karcie **Atrybuty produktu kanału** dla każdego atrybutu wybierz opcję **Uwzględnienie atrybutu**.
1. Wybierz węzeł kategorii **Odzież męska**, zaznacz kategorię **Spodnie**, a następnie na skróconej karcie **Atrybuty produktu kanału** dla każdego atrybutu wybierz opcję **Uwzględnienie atrybutu**.
1. Po zaktualizowaniu metadanych atrybutów dla zamierzonych atrybutów i ulepszeń upewnij się, że zapisać zmiany i uruchomić zadanie **Publikuj aktualizacje kanału**. Następnie po opublikowaniu aktualizacji należy uruchomić następujące zadania: **1070** (**Konfiguracja kanału**), **1040** (**Produkty**) **i 1150** (**Katalog**).

> [!NOTE]
> - Jeśli w firmie jest wymagane, aby produkty w hierarchii nawigacji często dodawać lub usuwać lub wprowadzać zmiany, takie jak aktualizowanie wartości kolejności wyświetlania, dodawanie nowych kategorii i dodawanie nowych grup atrybutów do kategorii, zalecane jest skonfigurowanie zadania **Publikuj aktualizacje kanału** tak, aby było uruchamiane jako częste zadanie wsadowe. Można również ręcznie wyzwolić zadanie **Publikuj aktualizacje kanału**, a następnie poniższe zadania Commerce Data Exchange (CDX): **1070** (**Konfiguracja kanału**), **1040** (**Produkty**) i **1150** (**Katalog**).
> - Opcja **Dziedzicz** pozwala określić, że kanał powinien dziedziczyć grupy atrybutów ze swojego kanału nadrzędnego w hierarchii. Jeśli w opcji **Dziedzicz** ustawisz wartość **Tak**, węzeł kanału podrzędnego odziedziczy wszystkie grupy atrybutów oraz wszystkie znajdujące się w nich atrybuty.
> - Jeśli przycisk **Ustaw metadane atrybutu** w okienku akcji jest niedostępny, upewnij się, że **Hierarchia nawigacji** jest skojarzona z kanałem na skróconej karcie **Ogólne**.
> - Nie można skojarzyć grup atrybutów z wyjątkiem grup atrybutów opartych na wymiarach na poziomie kanału (na przykład w obszarze **Grupy atrybutów** na stronie **Kategorie kanału i atrybuty produktów**).
> - Po wprowadzeniu obsługi dla specyficznych dla klienta katalogów B2B w wersji Commerce 10.0.27 można określić konfiguracje ulepszeń i atrybutów dla poszczególnych katalogów B2B w taki sam sposób, jak opisano w tym artykule.

## <a name="override-attribute-values"></a>Zastąp wartości atrybutów

Wartości domyślne atrybutów można zastąpić dla poszczególnych produktów na poziomie produktu. Dla poszczególnych produktów można również zastąpić je w określonych katalogach kierowanych do konkretnych kanałów.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Zastępowanie wartości atrybutów w poszczególnych produktach

Aby zastąpić wartości atrybutów pojedynczego produktu, wykonaj kroki opisane w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Retail i Commerce \> Zarządzanie kategoriami i produktami \> Zwolnione produkty według kategorii**.
1. Wybierz kolejno **Moda \> Akcesoria modowe \> Modne okulary przeciwsłoneczne**.
1. Wybierz żądany produkt w siatce. Następnie w okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz opcję **Atrybuty produktu**.
1. Zaznacz atrybut w lewym okienku, a następnie zaktualizuj jego wartość w prawym okienku.

![Strona wartości atrybutu produktów.](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Zastępowanie wartości atrybutów wszystkich produktów w katalogu

Aby zastąpić wartości atrybutów wszystkich produktów w katalogu, wykonaj kroki opisane w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Retail i Commerce \> Zarządzanie katalogami \> Wszystkie katalogi**.
1. Wybierz katalog **Fabrikam Base Catalog**.
1. Wybierz kolejno **Moda \> Akcesoria modowe \> Modne okulary przeciwsłoneczne**.
1. Na skróconej karcie **Produkty** wybierz wymagany produkt, a następnie nad siatką produktów wybierz opcję **Atrybuty**.
1. Na następnej skróconej karcie zaktualizuj wartości wymaganych atrybutów:

    - Udostępnione media produktu
    - Udostępnione atrybuty produktu
    - Kanał medialny
    - Atrybuty produktu kanału

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>Zastępowanie wartości atrybutów wszystkich produktów w kanale

Aby zastąpić wartości atrybutów wszystkich produktów w kanale, wykonaj kroki opisane w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz kanał **Houston**.
1. Na skróconej karcie **Produkty** wybierz wymagany produkt, a następnie nad siatką produktów wybierz opcję **Atrybuty**.
1. Jeżeli nie są dostępne żadne produkty, wybierz opcję **Dodaj** na skróconej karcie **Produkty**, a następnie wybierz żądane produkty w oknie dialogowym **Dodaj produkty**.
1. Na następnej skróconej karcie zaktualizuj wartości wymaganych atrybutów:

    - Udostępnione media produktu
    - Udostępnione atrybuty produktu
    - Kanał medialny
    - Atrybuty produktu kanału

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Zdefiniuj wartości atrybutów specyficzne dla wariantów i zdefiniuj wiele wartości dla atrybutów produktu

Aby zdefiniować wartości atrybutów specyficzne dla wariantów oraz zdefiniować wiele wartości atrybutów produktu, wykonaj kroki w tej przykładowej procedurze.

1. Zaloguj się do centrali Commerce headquarters jako menedżer ds. merchandisingu.
1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz kanał **Houston**.
1. Na skróconej karcie **Produkty** wybierz wymagany wariant produktu, a następnie nad siatką produktów wybierz opcję **Atrybuty**.
1. Jeżeli nie są dostępne żadne produkty, wybierz opcję **Dodaj** na skróconej karcie **Produkty**, a następnie wybierz żądane warianty produktów w oknie dialogowym **Dodaj produkty**.
1. Na następnej skróconej karcie zaktualizuj wartości wymaganych atrybutów:

    - Udostępnione media produktu
    - Udostępnione atrybuty produktu
    - Kanał medialny
    - Atrybuty produktu kanału

#### <a name="example-of-variant-specific-attribute-configuration"></a>Przykład konfiguracji atrybutu specyficznej dla wariantu
        
W tym przykładzie produkt **P001-główny** to szerokiego zastosowania but, który ma trzy warianty: **Bieg**, **Spacer** i **Wędrówki**. Dla każdego wariantu chcesz jednoznacznie zdefiniować wartość atrybutu **Działanie**. Na skróconej karcie **Produkty** na stronie **Kategorie kanału oraz atrybuty produktu** dla kanału zdefiniuj wartość atrybutu **Działanie** dla wariantów, tak jak to przedstawiono w poniższej tabeli.

| Wariant     | Wartość atrybutu działania |
|-------------|--------------------------|
| P001-główny | Sporty                   |
| P001-1      | Uruchomione                  |
| P001-2      | Chodzenie                  |
| P001-3      | Wędrówki                 |

Jeśli użytkownik szuka „buta”, w wynikach wyszukiwania pojawi się produkt **P001-Master**. W przypadku skonfigurowania atrybutu **Działanie** jako dostępnego do udoskonalenia,ulepszanie **działań** będzie zawierało tylko wartość **Sporty** jako wartość do doprecyzowania, ponieważ ta wartość została zdefiniowana dla atrybutu **Działanie** na poziomie produktu **P001-główny**.

Domyślnie atrybuty poziomu wariantu mają być używane tylko na stronach szczegółów produktu (PDP). Po wybraniu określonego wariantu produktu w PDP, specyfikacje produktu w PDP są aktualizowane dla tego konkretnego wariantu.

W celu udoskonaleń, które mają ująć wartości atrybutów zdefiniowane na poziomie wariantu produktu, należy zdefiniować atrybut na poziomie produktu głównego, zaznaczyć pole wyboru **Zezwalaj na wiele wartości** i ustawić typ atrybutu na **Tekst**.

Następnie należy określić wszystkie możliwe wartości wariantów produktu. W przypadku atrybutu **Działanie**, który jest używany w tym przykładzie, możliwe wartości mogą obejmować: **Bieg**, **Spacer**, **Wspinaczka**, **Wędrówki**, **Kemping**, **Sporty wodne** i **Sporty zimowe**.

Po określeniu, czym powinny być wartości atrybutów wariantów, można je zdefiniować na poziomie produktu głównego, używając wartości rozdzielanych potokami. W przypadku atrybutu **Działanie** można zdefiniować wartość atrybutu produktu głównego jako **Bieg|Spacer|Wspinaczka|Wędrówki|Kemping|Sporty wodne|Sporty zimowe**.

Następnie dla każdego wariantu można zdefiniować wartości atrybutów, wprowadzając wartości rozdzielane potokami lub pojedyncze wartości. Dla atrybutu **Działanie** można skonfigurować pojedynczy wariant produktu jako **Bieg|Spacer|Wspinaczka**, **Bieg**, **Bieg|Wspinaczki|Sporty wodne** i tak dalej.

Po zdefiniowaniu wartości atrybutów wariantów na stronie **Kategorie kanału i atrybuty produktów** w okienku akcji wybierz opcję **Publikuj aktualizacje kanału**, a następnie uruchom zadania **1150**, **1040** i **1070**.

Po ukończeniu zadań i zaktualizowaniu indeksu wyszukiwania wszystkie oczekiwane wartości powinny pojawiać się w wynikach wyszukiwania i wynikach przeglądania kategorii.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
