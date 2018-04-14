---
title: "Atrybuty i grupy atrybutów oraz ich powiązania z różnymi jednostkami aplikacji Retail w programie Finance and Operations"
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 53af4335146be6c163a6d84b60155e1a741c0be4
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="attributes-attribute-groups-and-their-associations-with-various-retail-entities-in-finance-and-operations"></a>Atrybuty i grupy atrybutów oraz ich powiązania z różnymi jednostkami aplikacji Retail w programie Finance and Operations

[!INCLUDE [banner](includes/banner.md)]

*Atrybuty* umożliwiają dokładniejsze opisanie produktu i jego właściwości za pomocą pól zdefiniowanych przez użytkownika (takich jak **Rozmiar pamięci**, **Pojemność dysku twardego**, **Zgodność z normą Energy Star** i tak dalej). W programie Microsoft Dynamics 365 for Finance and Operations atrybuty można skojarzyć z różnymi jednostkami modułu Retail, takimi jak kategorie produktów i kanały sprzedaży detalicznej, oraz ustawić im wartości domyślne. Wtedy produkty dziedziczą atrybuty i wartości domyślne, gdy zostaną powiązane z kategoriami produktów lub kanałami sprzedaży detalicznej. Wartości domyślne można zastąpić na poziomie poszczególnych produktów, na poziomie kanału sprzedaży detalicznej lub w katalogu sieci sprzedaży.
 
Na przykład typowy produkt w postaci telewizora może mieć następujące atrybuty.

| Kategoria   | Atrybut                | Możliwe wartości          | Wartość domyślna |
|------------|--------------------------|-----------------------------|---------------|
| Telewizja i wideo | Marka                    | Dowolna prawidłowa nazwa marki       | None          |
| TELEWIZJA         | Rozmiar ekranu              | 20–80 cali                | None          |
|            | Rozdzielczość w pionie      | 480i, 720p, 1080i, lub 1080p | 1080p         |
|            | Częstotliwość odświeżania ekranu      | 60hz, 120hz, lub 240hz       | 60hz          |
|            | Wejścia HDMI              | 0–10                        | 3             |
|            | Wejścia DVI               | 0–10                        | 1             |
|            | Wejście kompozytowe         | 0–10                        | 2             |
|            | Wejścia komponentów         | 0–10                        | 1             |
| LCD        | 3D Ready                 | Tak lub Nie                   | Tak           |
|            | Obsługa 3D               | Tak lub Nie                   | Nr            |
| Plazmowy     | Minimalna temperatura      | 32–110 stopni              | 32            |
|            | Maksymalna temperatura        | 32–110 stopni              | 100           |
| Projekcyjny | Gwarancja na lampę kineskopową | 6, 12 lub 18 miesięcy         | 12            |
|            | liczba lamp kineskopowych    | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Atrybuty i typy atrybutów

Atrybuty są oparte na *typach atrybutów*. Typ atrybutu określa typ danych, które można wprowadzić dla określonego atrybutu. Obecnie program Finance and Operations obsługuje następujące typy atrybutów:

- **Waluta** — ten typ obsługuje wartości waluty. Może być ograniczony (czyli obsługuje zakres wartości) lub może pozostać otwarty.
- **Data i godzina** — ten typ obsługuje wartości daty i godziny. Może być ograniczony lub pozostać otwarty.
- **Dziesiętna** — ten typ obsługuje wartości liczbowe, które zawierają miejsca dziesiętne. Obsługuje również jednostki miary. Może być ograniczony lub pozostać otwarty.
- **Całkowita** — ten typ obsługuje wartości liczbowe. Obsługuje również jednostki miary. Może być ograniczony lub pozostać otwarty.
- **Tekst** — ten typ obsługuje wartości tekstowe. Obsługuje również wstępnie zdefiniowany zestaw możliwych wartości (tzn. *elementy stałotekstowe*).
- **Logiczna** — ten typ obsługuje wartości binarne (**prawda** lub **fałsz**).
- **Odwołanie** — ten typ odwołuje się do innych atrybutów.

### <a name="set-up-attribute-types-in-finance-and-operations"></a>Konfigurowanie typów atrybutów w programie Finance and Operations

1. Zaloguj się na kliencie narzędzi zaplecza programu Finance and Operations jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Kategorie i atrybuty** &gt; **Typy atrybutów**.
3. Utwórz dwa typy atrybutów o typie **Tekst**, w opcji **Stała lista** zaznacz wartość **Tak**, a następnie dodaj listę wartości:

    - Nazwij jeden typ atrybutu **Kształt soczewek** i dodaj następujące wartości: **Owal**, **Kwadrat** i **Prostokąt**.
    - Nazwij drugi typ atrybutu **Marka okularów przeciwsłonecznych** i dodaj następujące wartości: **Ray ban**, **Aviator** i **Oakley**.

![Typy atrybutów](media/AttributeType.png)

### <a name="set-up-an-attribute-in-finance-and-operations"></a>Konfigurowanie atrybutu w programie Finance and Operations

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Kategorie i atrybuty** &gt; **Atrybuty**.
3. Utwórz atrybut o nazwie **Soczewki**.
4. W polu **Typ atrybutu** ustaw wartość **Kształt soczewek**.

![Atrybuty](media/Attribute.png)

## <a name="attribute-metadata"></a>Metadane atrybutu

*Metadane atrybutów* umożliwiają wybranie opcji określających, jak mają się zachować atrybuty każdego produktu. Można na przykład wskazać, czy atrybuty są wymagane, czy mogą być używana w wyszukiwaniach i czy można ich używać jako filtrów.

Dla produktów sieci sprzedaży ustawienia metadanych atrybutów mogą być zastępowane na poziomie kanału. Ta funkcjonalność zostanie omówiona w dalszej części tego tematu.

Jak można zauważyć, strona **Atrybuty** zawiera opcje powiązane z metadanymi atrybutów. W obszarze **Metadane atrybutów aplikacji POS** opcja o nazwie **Może być doprecyzowany** wpływa na zachowanie wartości atrybutów w aplikacji Retail POS oraz na sposób obsługi tych wartości atrybutów przez system. Tylko atrybuty, dla których w opcji **Może być doprecyzowany** można ustawić wartość **Tak**, będą wyświetlane w aplikacji Retail POS dla operacji doprecyzowywania i filtrowania produktów.

Poniżej przedstawiono pozostałe opcje metadanych atrybutów dostępne na stronie **Atrybuty**:

- Z możliwością wyszukiwania
- Z możliwością pobierania
- Może być przedmiotem kwerendy
- Z możliwością sortowania
- Zezwalaj na wiele wartości
- Ignorowanie wielkości liter i formatu
- Pełne dopasowanie

Te opcje były pierwotnie przeznaczone do poprawy funkcji wyszukiwania w sklepach internetowych. Co prawda program Finance and Operations nie zawiera w standardzie funkcjonalności sklepu internetowego, ale obejmuje zestaw SDK do publikowania dla handlu elektronicznego. Odbiorcy mogą używać tego zestawu SDK do wprowadzania produktów do dowolnych indeksów wyszukiwania. Mimo iż dane produktów są importowane, odbiorcy nadal powinni być w stanie odróżniać dane, które można przeszukiwać, na których można wykonywać zapytania itd. W ten sposób mogą zbudować optymalny indeks obejmujący tylko atrybuty, które *w ich opinii* powinny być indeksowane.

Aby uzyskać więcej informacje o przeznaczeniu tych pozostałych opcji, zobacz [Omówienie schematu wyszukiwania w programie SharePoint Server 2013](https://technet.microsoft.com/en-us/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Ustawienia filtrów atrybutów

Ustawienia filtrów atrybutów pozwalają określić sposób wyświetlania filtrów atrybutów w aplikacji Retail POS. Aby uzyskać dostęp do ustawień filtrów atrybutów, w programie Finance and Operations na stronie **Atrybuty** zaznacz atrybut, a następnie w okienku akcji wybierz opcję **Ustawienia filtra**.

Strona **Preferencje wyświetlania filtra** zawiera następujące pola:

- **Nazwa** — to pole jest domyślnie ustawione na nazwę atrybutu. Można jednak zmienić jego wartość.
- **Opcja wyświetlania** — dostępne są następujące opcje:

    - **Jedna wartość** — ta opcja jest dostępna dla następujących typów atrybutów: **Logiczna**, **Waluta**, **Dziesiętna**, **Całkowita** i **Tekst**. Ta opcja umożliwia wybór jednej wartości dla tych atrybutów na kliencie w celu doprecyzowania.
    - **Wiele wartości** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna**, **Całkowita** i **Tekst**. Ta opcja umożliwia wybór wielu wartości dla tego atrybutu na kliencie w celu doprecyzowania.

- **Sterowanie wyświetlaniem** — dostępne są następujące opcje:

    - **Lista** — ta opcja jest dostępna dla wszystkich typów atrybutów.
    - **Zakres** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna** i **Całkowita**. 
    - **Suwak** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna** i **Całkowita**.
    - **Suwak z paskami** — ta opcja jest dostępna dla następujących typów atrybutów: **Waluta**, **Dziesiętna** i **Całkowita**.

- **Wartość progowa** — to ustawienie jest wymagane, jeśli jako typ sterowania wyświetlaniem wybrano opcję **Zakres**. W celu zdefiniowania wartości można użyć średnika (;) jako separatora.

    Na przykład dla filtra takiego jak **Objętości worka** pole wartości progowej może zawierać wartości **10; 20; 50; 100; 200; 500; 1000; 5000**. W tym przypadku w aplikacji Retail POS będą wyświetlane następujące zakresy. Wszystkie zakresy, które w zbiorze wyników nie mają żadnych produktów, będą wyświetlane jako wygaszone.

    - Mniej niż 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - Ponad 500

![Ustawienia filtrów atrybutów](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Grupy atrybutów

Po zdefiniowaniu atrybutów można je przypisać do grup atrybutów. *Grupa atrybutów* jest używana do grupowania indywidualnych atrybutów składnika lub podskładnika w modelu konfiguracji produktu. Ten sam atrybut można dołączyć do więcej niż jednej grupy atrybutów. Grupy atrybutów mogą pomóc użytkownikom konfigurować produkty, ponieważ różne opcje wyboru są rozmieszczane w określonym kontekście. Grupy atrybutów można przypisywać do kategorii sieci sprzedaży i kanałów sprzedaży detalicznej.

Można również ustawić domyślne wartości dla atrybutów dołączonych do grupy atrybutów. Na przykład do grupy atrybutów można dodać atrybut koloru oraz wybrać **Niebieski** jako domyślną wartość atrybutu. W takim przypadku po dodaniu grupy atrybutów do produktu sieci sprzedaży zawierającego kolor jako jeden z atrybutów wartość **Niebieski** będzie wyświetlana jako domyślny kolor tego produktu.

![Grupy atrybutów](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Tworzenie grup atrybutów

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Kategorie i atrybuty** &gt; **Grupy atrybutów**.
3. Utwórz grupę atrybutów o nazwie **Modne okulary przeciwsłoneczne**.
4. Dodaj następujące atrybuty: **Kształt soczewek** i **Marka okularów przeciwsłonecznych**.

### <a name="assign-attribute-groups-to-retail-categories"></a>Przypisywanie grup atrybutów do kategorii sieci sprzedaży

Jedną lub więcej grup atrybutów można skojarzyć z węzłami kategorii w następujących typach hierarchii kategorii sieci sprzedaży: Hierarchia produktów sieci sprzedaży, Hierarchia kategorii nawigacji w kanale i Hierarchia uzupełniających kategorii produktów. Wtedy gdy produkty będą kategoryzowane, odziedziczą atrybuty włączone do grup atrybutów.

![Hierarchia produktów sieci sprzedaży — grupy atrybutów produktów](media/AGRetailProdHierarchy.PNG)

Wykonaj następujące kroki, aby przypisać grupy atrybutów do kategorii w hierarchii produktów sieci sprzedaży.

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Handel detaliczny** &gt; **Zarządzanie kategoriami i produktami** &gt; **Hierarchia produktów sieci sprzedaży**.
3. Wybierz opcję **Hierarchia nawigacji Moda**.
4. W obszarze **Odzież męska** wybierz kategorię **Spodnie**, a następnie na skróconej karcie **Grupy atrybutów produktu** dodaj grupę atrybutów o nazwie **Pasek męski**.
5. Zaznacz kategorię **Modne okulary przeciwsłoneczne** i zweryfikuj nowe atrybuty w grupie atrybutów **Modne okulary przeciwsłoneczne**, wybierając opcję **Wyświetlenie atrybutów**.

    W grupie atrybutów powinny być teraz widoczne nowe atrybuty **Kształt soczewek** i **Marka okularów przeciwsłonecznych**.

6. W obszarze **Odzież męska** wybierz kategorię **Spodnie** i zweryfikuj atrybuty w grupie atrybutów **Pasek męski**, wybierając opcję **Wyświetlenie atrybutów**.

    W grupie atrybutów powinny być teraz widoczne atrybuty **Marka pasków męskich**, **Tkanina paska** i **Rozmiar paska**.

> [!NOTE]
> Tej procedury można również użyć w celu przypisania grup atrybutów do kategorii w hierarchiach Hierarchia kategorii nawigacji w kanale i Hierarchia uzupełniających kategorii produktów. W kroku 2 użyj następujących ścieżek nawigacji:
>
> - **Handel detaliczny** &gt; **Zarządzanie kategoriami i produktami** &gt; **Kategorie nawigacji kanału**
> - **Handel detaliczny** &gt; **Zarządzanie kategoriami i produktami** &gt; **Uzupełniające kategorie produktów**

### <a name="assign-attribute-groups-to-retail-stores"></a>Przypisywanie grup atrybutów do kategorii sklepów sieci sprzedaży

Można skojarzyć jedną lub kilka grup atrybutów z jednym lub więcej sklepami sieci sprzedaży w hierarchii sklepów sieci sprzedaży. Wtedy gdy produkty zostaną uwzględnione w określonych sklepach sieci sprzedaży, odziedziczą atrybuty włączone do grup atrybutów.

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Kategorie kanału sprzedaży i atrybuty produktów**.
3. Przypisz grupy atrybutów do kanału Houston:

    1. Wybierz kanał **Houston**.
    2. Na skróconej karcie **Grupy atrybutów** wybierz opcję **Dodaj**, a następnie w polu **Nazwa** zaznacz pozycję **SharePointProvisionedProductAttributeGroup**.
    3. Wybierz ponownie przycisk **Dodaj**, a następnie w polu **Nazwa** zaznacz wartość **Pasek męski**.
    4. Wybierz ponownie przycisk **Dodaj**, a następnie w polu **Nazwa** zaznacz wartość **Modne okulary przeciwsłoneczne**.

        > [!NOTE]
        > Opcja pozwala określić, że ten kanał powinien dziedziczyć grupy atrybutów ze swojego kanału nadrzędnego w hierarchii. Jeśli w opcji **Dziedzicz** ustawisz wartość **Tak**, węzeł kanału podrzędnego odziedziczy wszystkie grupy atrybutów oraz wszystkie znajdujące się w nich atrybuty.

4. Włącz atrybuty, tak aby były dostępne w kanale Houston:

    1. W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.
    2. Wybierz węzeł kategorii **Moda**, a następnie na skróconej karcie **Atrybuty produktu kanału** dla każdego atrybutu wybierz opcję **Uwzględnienie atrybutu**.
    3. Wybierz węzeł kategorii **Akcesoria modowe**, zaznacz kategorię **Modne okulary przeciwsłoneczne**, a następnie na skróconej karcie **Atrybuty produktu kanału** dla każdego atrybutu wybierz opcję **Uwzględnienie atrybutu**.
    4. Wybierz węzeł kategorii **Odzież męska**, zaznacz kategorię **Spodnie**, a następnie na skróconej karcie **Atrybuty produktu kanału** dla każdego atrybutu wybierz opcję **Uwzględnienie atrybutu**.

![Kategorie kanału sprzedaży i atrybuty produktów — grupy atrybutów](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Zastępowanie wartości atrybutów

Wartości domyślne atrybutów można zastąpić dla poszczególnych produktów na poziomie produktu. Dla poszczególnych produktów można również zastąpić domyślne wartości atrybutów w określonych katalogach kierowanych do konkretnych kanałów sprzedaży detalicznej.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Zastępowanie wartości atrybutów w poszczególnych produktach

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Handel detaliczny** &gt; **Zarządzanie kategoriami i produktami** &gt; **Zwolnione produkty według kategorii**.
3. Wybierz kolejno opcje **Moda** &gt; **Akcesoria modowe** &gt; węzeł kategorii **Modne okulary przeciwsłoneczne**.
4. Wybierz żądany produkt w siatce. Następnie w okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz opcję **Atrybuty produktu**.
5. Zaznacz atrybut w lewym okienku, a następnie zaktualizuj jego wartość w prawym okienku.

![Strona Szczegóły produktu — grupy atrybutów produktów](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>Zastępowanie wartości atrybutów produktów w katalogu

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Handel detaliczny** &gt; **Zarządzanie katalogami** &gt; **Wszystkie katalogi**.
3. Wybierz katalog **Fabrikam Base Catalog**.
4. Wybierz kolejno opcje **Moda** &gt; **Akcesoria modowe** &gt; węzeł kategorii **Modne okulary przeciwsłoneczne**.
5. Na skróconej karcie **Produkty** wybierz wymagany produkt, a następnie nad siatką produktów wybierz opcję **Atrybuty**.
6. Na następnej skróconej karcie zaktualizuj wartości wymaganych atrybutów:

   - Udostępnione media produktu
   - Udostępnione atrybuty produktu
   - Kanał medialny
   - Atrybuty produktu kanału

     > [!NOTE]
     > Jeśli w programie Finance and Operations utworzono współużytkowane multimedia produktów i współużytkowane atrybuty produktów, dotyczą one wszystkich produktów sieci sprzedaży.

![Grupy atrybutów produktów z katalogu](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>Zastępowanie wartości atrybutów produktów w kanale

1. Zaloguj się na kliencie narzędzi zaplecza jako kierownik ds. merchandisingu.
2. Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Kategorie kanału sprzedaży i atrybuty produktów**.
3. Wybierz kanał **Houston**.
4. Na skróconej karcie **Produkty** wybierz wymagany produkt, a następnie nad siatką produktów wybierz opcję **Atrybuty**.

    > [!NOTE]
    > Jeżeli nie są dostępne żadne produkty, dodaj produkty, wybierając opcję **Dodaj** na skróconej karcie **Produkty**, a następnie wybierając żądane produkty w oknie dialogowym **Dodaj produkty**.

5. Na następnej skróconej karcie zaktualizuj wartości wymaganych atrybutów:

   - Udostępnione media produktu
   - Udostępnione atrybuty produktu
   - Kanał medialny
   - Atrybuty produktu kanału

     > [!NOTE]
     > Jeśli w programie Finance and Operations utworzono współużytkowane multimedia produktów i współużytkowane atrybuty produktów, dotyczą one wszystkich produktów sieci sprzedaży.

