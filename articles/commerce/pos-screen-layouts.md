---
title: Konfiguracje wizualne interfejsu użytkownika punktu sprzedaży
description: Ten temat zawiera informacje dotyczące układów ekranu w środowiskach POS aplikacji Dynamics 365 Commerce.
author: boycezhu
manager: annbe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 203d12956825286b77a107bb9fd91c451ecfd1e6
ms.sourcegitcommit: dc3deca942864c4a8354096183c9e1b9b88992f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/20/2021
ms.locfileid: "5032940"
---
# <a name="pos-user-interface-visual-configurations"></a>Konfiguracje wizualne interfejsu użytkownika punktu sprzedaży

[!include [banner](includes/banner.md)]


Interfejs użytkownika (UI) punktu sprzedaży Microsoft Dynamics 365 Commerce można konfigurować przy użyciu kombinacji profili graficznych i układów ekranu, które się przypisuje do sklepów, kas i użytkowników. Ten temat zawiera informacje na temat tych opcji konfiguracji.

Poniższa ilustracja pokazuje relacje między różnymi jednostkami, które razem tworzą konfigurowalne aspekty interfejsu użytkownika aplikacji POS.

![Jednostki układu ekranu aplikacji POS](../commerce/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Profil graficzny

Profile graficzne są przypisywane do kas. Określają elementy wizualnych, które są specyficzne dla kas i wspólne dla użytkowników. Każdy użytkownik, który się loguje do kasy, widzi ten sam motyw, układ, kolory i obrazy.

![Ekran powitalny aplikacji POS z jasnym motywem](../commerce/media/POS-Welcome-Screen-with-Light-theme.png)

![Ekran transakcji w aplikacji POS z ciemnym motywem](../commerce/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Numer profilu** — Numer profilu jest unikatowym identyfikatorem profilu graficznego.
- **Opis** — Można wprowadzić znaczącą nazwę, która pomoże identyfikować profil odpowiedni w danej sytuacji.
- **Motyw** — Można wybierać między motywami aplikacji **Jasny** i **Ciemny**. Motyw ma wpływ na kolory czcionki i tła w całej aplikacji.
- **Kolor wiodący** — Kolor wiodący jest używany w całej aplikacji POS do odróżniania lub wyróżniania pewnych elementów wizualnych, takich jak kafelki, przyciski poleceń i hiperłącza. Zazwyczaj te elementy wykonują różne akcje.
- **Kolor nagłówka** — Można skonfigurować kolor nagłówka strony spełniający wymagania identyfikacji wizualnej sprzedawcy detalicznego.
- **Schemat czcionek** — umożliwia wybór między **Standardowymi** i **Dużymi** schematami czcionek. Schemat czcionek ma wpływ na rozmiar czcionki w aplikacji. Ustawieniem domyślnym jest **Standardowa**.
- **Zawsze pokazuj etykiety paska aplikacji** — gdy ta opcja jest włączona, tekst etykiety jest zawsze widoczny pod przyciskami paska aplikacji.
- **Układ** — umożliwia wybór między układami **Środkowymi** i **Prawy**. Układ ma wpływ na wyrównanie pola rejestracji na ekranie logowania. Ustawieniem domyślnym jest **Środkowy**.
- **Wyświetlanie daty/godziny** — gdy ta opcja jest włączona, bieżąca data i godzina są wyświetlane w nagłówku punktu sprzedaży i na ekranie logowania.
- **Klawiatura** — można wybrać opcję między **Domyślną klawiaturą systemu operacyjnego** i **Wyświetlić konsolę numeryczną**, aby określić domyślną klawiaturę używaną do wprowadzania danych na ekranie logowania. Konsola numeryczna jest wirtualną klawiaturą używaną głównie dla urządzeń dotykowych. Domyślnym wyborem jest **Domyślną klawiaturą systemu operacyjnego**.
- **Obraz logo** — można określić obraz logo wyświetlany na ekranie logowania. Zaleca się używanie obrazu, który ma przezroczyste tło. Rozmiar pliku powinien być możliwie jak najmniejszy, ponieważ zachowanie i wydajność aplikacji mogą mieć wpływ na przechowywanie i ładowanie dużych plików.
- **Tło logowania** — Można określić obraz tła dla ekranu logowania. Podobnie jak w przypadku obrazów tła logowania, rozmiar pliku powinien być jak najmniejszy.
- **Tło** — Można określić obraz tła, który będzie używany zamiast jednolitego koloru motywu w całej aplikacji. Podobnie jak w przypadku obrazów tła ekranu logowania, rozmiar pliku powinien być możliwie najmniejszy.

> [!NOTE]
> Wyświetlanie układu **Prawego** i daty/godziny nie jest stosowane do ekranu logowania w widoku kompaktowym.

Aby zsynchronizować najnowsze konfiguracje profilów graficznych z bazą danych kanału, należy uruchomić zadanie harmonogramu dystrybucji **1090** (**Rejestrs**).

## <a name="screen-layouts"></a>Układy ekranu

Konfiguracje układu ekranu decydują o akcjach, zawartości i położeniu formantów interfejsu użytkownika na ekranie **Powitalnym** i ekranie **Transakcja** w aplikacji POS.

![Widok układu ekranu aplikacji POS](../commerce/media/POS-Screen-Layout-View.png)

- **Ekran powitalny** — W większości przypadków ekran powitalny to strona, którą użytkownicy widzą podczas pierwszego logowania do aplikacji POS. Ekran powitalny może zawierać obraz identyfikacyjny marki oraz siatki przycisków umożliwiające dostęp do operacji w punkcie sprzedaży. Zwykle na tym ekranie umieszcza się operacje, które nie są specyficzne dla bieżącej transakcji.

    ![Ekran powitalny aplikacji POS](../commerce/media/POS-Welcome-Screen.png)

- **Ekran transakcji** — Ekran **Transakcja** jest w aplikacji POS głównym ekranem do przetwarzania transakcji i zamówień sprzedaży. Zawartość i układ są skonfigurowane przy użyciu konstruktora układu ekranu.

    ![Ekran transakcji w punkcie sprzedaży](../commerce/media/POS-Transaction-Screen.png)

- **Domyślny ekran startowy** — Niektórzy sprzedawcy detaliczni wolą, aby kasjerzy po zalogowaniu przechodzili bezpośrednio do ekranu **Transakcja**. Ustawienie **Domyślny ekran startowy** umożliwia określenie domyślnego ekranu, który pojawia się po zalogowaniu przy użyciu poszczególnych układów ekranu.

### <a name="assignment"></a>Przypisanie

Układy ekranów można przypisywać na poziomie sklepu, kasy lub użytkownika. Przypisanie użytkownikowi zastępuje przypisania do kasy i sklepu, a przypisanie na poziomie kasy ma priorytet nad przypisaniem do sklepu. W prostym scenariuszu, gdzie wszyscy użytkownicy korzystają z tego samego układu niezależnie od kasy ani roli, układ ekranu można ustawić tylko na poziomie sklepu. W scenariuszach, gdy określone kasy lub użytkownicy wymagają specjalnych układów, można je przypisać.

W zależności od poziomu, na którym są przypisane układy ekranu, należy uruchomić zadania planowania dystrybucji **1070** (**Konfiguracja kanału**), **1090** (**Rejestry**) i/lub **1060** (**Personel**), aby synchronizować najnowsze konfiguracje układu ekranu z bazą danych kanału.

### <a name="layout-sizes"></a>Rozmiary układów

Większość aspektów interfejsu użytkownika aplikacji POS jest elastyczna, a układ automatycznie zmieniany i korygowany w zależności od rozmiaru i orientacji ekranu. Jednak ekran **Transakcja** w aplikacji POS musi być skonfigurowany dla każdej spodziewanej rozdzielczości ekranu.

Podczas uruchamiania aplikacja POS wybiera najbliższy rozmiar układu skonfigurowany dla urządzenia. Układ ekranu może również zawierać konfiguracje dla orientacji poziomej i pionowej oraz urządzeń pełnowymiarowych i kompaktowych. Dlatego użytkowników można przypisać do jednego układu ekranu, który działa w urządzeniach o różnych rozmiarach i typach wykorzystywanych w sklepie.

![Rozmiary układów aplikacji POS](../commerce/media/POS-Screen-Layout-Sizes.png)

- **Nazwa** — Można wprowadzić opisową nazwę identyfikującą rozmiar ekranu.
- **Typ układu** — W aplikacji POS interfejs użytkownika może być wyświetlany w różnych orientacjach, tak aby zapewnić użytkownikowi jak najlepsze środowisko obsługi na konkretnym urządzeniu.

    - **Modern POS - Pełna wersja** — Pełnowymiarowe układy zazwyczaj najlepiej nadają się do większych ekranów, takich jak w monitorach komputerowych i tabletach. Można wskazać elementy interfejsu użytkownika, które mają być zawarte w układzie, określić rozmiar i umieszczenie tych elementów oraz skonfigurować ich szczegółowe właściwości. Układy pełne obsługują konfiguracje poziome i pionowe.
    - **Modern POS - Wersja kompaktowa** — Układy kompaktowe zazwyczaj najlepiej nadają się do telefonów i małych tabletów. Możliwości projektowania dla urządzeń kompaktowych są ograniczone. Można skonfigurować kolumny i pola paneli pokwitowania i sum.

- **Szerokość/Wysokość** — Te wartości reprezentują efektywny rozmiar ekranu (w pikselach), jakiego oczekuje się w układzie. Należy pamiętać, że w niektórych systemach operacyjnych do ekranów o wysokiej rozdzielczości jest stosowane skalowanie.

> [!TIP]
> Informację o rozmiarze układu wymaganym dla ekranu aplikacji POS można uzyskać poprzez wyświetlanie rozdzielczości w aplikacji. Uruchom aplikację POS i wybierz kolejno opcje **Ustawienia \> Informacje o sesji**. Aplikacja POS pokazuje aktualnie załadowany układ ekranu, rozmiar układu i rozdzielczość okna aplikacji.

![Ekran Informacje dot. sesji POS pokazuje aktualnie załadowany układ ekranu, rozmiar układu i rozdzielczość okna aplikacji](../commerce/media/POS-Session-Information.png)

### <a name="button-grids"></a>Siatki przycisków

W każdym rozmiarze układu ekranu można skonfigurować i przypisać siatki przycisków dla ekranów powitalnego i **Transakcja** aplikacji POS. Siatki przycisków ekranu powitalnego są układane automatycznie od lewej do prawej, od numeru najniższego (ekran powitalny 1) do najwyższego.

W pełnowymiarowych układach aplikacji POS położenie siatki przycisków jest określane w projektancie układu ekranu.

W kompaktowych wersjach układów aplikacji POS siatki przycisków są układane automatycznie od góry do dołu, od numeru najniższego (ekran transakcji 1) do najwyższego. Można do nich przejść z menu **Akcje**.

![Siatka przycisków w układzie kompaktowym](../commerce/media/Compact-View-Button-Grids.png)

> [!NOTE]
> Rozmiary przycisków w projektancie będą skalowane w celu dopasowania do rozmiaru okna, dlatego mogą nie odzwierciedlać dokładnie rzeczywistych przycisków renderowanych w punkcie sprzedaży. Aby najlepiej zasymulować układ siatki przycisków, dostosuj okna projektanta do tego samego rozmiaru co POS.

### <a name="images"></a>Obrazy

W każdym rozmiarze układu ekranu można określić obrazy, które mają się znaleźć w interfejsie użytkownika aplikacji POS. W pełnowymiarowych układach aplikacji POS można określić jeden obraz dla ekranu powitalnego. Obraz ten jest wyświetlany jako pierwszy element interfejsu użytkownika po lewej stronie. Na ekranie **Transakcja** obrazy mogą pełnić rolę obrazów kart lub logo. W kompaktowych układach aplikacji POS te obrazy nie są używane.

### <a name="screen-layout-designer"></a>Projektant układu ekranu

W projektancie układu ekranu można skonfigurować różne aspekty ekranu **Transakcja** aplikacji POS dla każdego rozmiaru układu w orientacjach pionowej i poziomej oraz w wersjach pełnej i kompaktowej. Projektant układu ekranu używa technologii wdrażania ClickOnce, która powoduje pobranie, zainstalowanie i uruchomienie najnowszej wersji aplikacji za każdym razem, gdy użytkownicy uzyskują do niej dostęp. Należy koniecznie sprawdzić wymagania technologii ClickOnce w kwestii przeglądarek internetowych. Niektóre przeglądarki, takie jak Google Chrome, wymagają rozszerzeń.

> [!IMPORTANT]
> Należy skonfigurować układu ekranu dla każdego rozmiaru układu zdefiniowanego i używanego w aplikacji POS.

### <a name="full-layout-designer"></a>Projektant układu pełnowymiarowego

W projektancie układu pełnowymiarowego użytkownicy mogą przeciągać formanty interfejsu użytkownika na ekran **Transakcja** aplikacji POS i konfigurować ustawienia tych formantów.

![Projektant układu pełnowymiarowego aplikacji POS (orientacja pozioma)](../commerce/media/POS-Full-Layout-Designer-Landscape.png)

- **Importowanie/eksportowanie układu** — Projekty układów ekranu aplikacji POS można eksportować i importować jako pliki XML, co pozwala je łatwo wykorzystywać i udostępniać w różnych środowiskach. Ważne jest, aby importować projekty układów dla odpowiednich rozmiarów układów. W przeciwnym razie elementy interfejsu użytkownika mogą nie mieścić się prawidłowo na ekranie.
- **Orientacja pozioma/pionowa** — Jeśli urządzenie z aplikacją POS pozwala użytkownikom przełączać się między orientacjami poziomą i pionową, należy zdefiniować układ ekranu dla każdej orientacji. Aplikacja POS automatycznie wykryje obrót ekranu i pokaże poprawny układ.
- **Siatka układu** — W projektancie układu aplikacji POS jest używana siatka 4-pikselowa. Formanty interfejsu użytkownika „przyciągają się” do siatki, aby ułatwić prawidłowe wyrównywanie zawartości.
- **Powiększenie w projektancie** — Widok projektanta można przybliżać i oddalać, aby lepiej widzieć zawartość ekranu aplikacji POS. Ta funkcja jest przydatna, gdy rozdzielczość ekranu w aplikacji POS różni się znacząco od rozdzielczości ekranu używanej w projektancie.
- **Pokazywanie/ukrywanie paska nawigacji** — W pełnowymiarowych układach aplikacji POS można określić, czy lewy pasek nawigacji ma być widoczny na ekranie **Transakcja**. Ta funkcja jest przydatna w monitorach o niższej rozdzielczości. Aby ustawić widoczność, kliknij pasek nawigacji prawym przyciskiem myszy w projektancie i zaznacz lub wyczyść pole wyboru **Zawsze widoczny**. Jeśli pasek nawigacji jest ukryty, użytkownicy aplikacji POS nadal mają do niego dostęp za pomocą menu w lewym górnym rogu.

    ![Pokazywanie/ukrywanie paska nawigacji](../commerce/media/Navigation-Bar.PNG)

- **Formanty aplikacji POS** — Projektant układu aplikacji POS obsługuje formanty wymienione poniżej. Wiele formantów można skonfigurować, klikając prawym przyciskiem myszy i używając menu skrótów.

    ![Formanty interfejsu użytkownika aplikacji POS](../commerce/media/POS-UI-Controls.png)

    - **Klawiatura numeryczna** — Klawiatura numeryczna jest głównym mechanizmem wprowadzania danych przez użytkownika na ekranie **Transakcja** w aplikacji POS. Można tak skonfigurować formant, aby była wyświetlana pełna klawiatura numeryczna. Ta opcja jest idealna dla urządzeń dotykowych. Alternatywnie można ją tak skonfigurować, aby było widoczne tylko pole wejściowe. W takim przypadku do wprowadzania danych jest używana fizyczna klawiatura. Ustawienia klawiatury numerycznej są dostępne tylko w układach pełnowymiarowych. W układach kompaktowych na ekranie **Transakcja** zawsze jest wyświetlana pełna klawiatura numeryczna.
    - **Panel sum** — Panel sum można skonfigurować na jedną lub dwie kolumny pokazujące wartości takie jak liczba wierszy, kwota rabatu, opłaty, suma częściowa i podatek. Układy kompaktowe zawierają tylko jedną kolumnę.
    - **Panel pokwitowań** — Panel pokwitowań zawiera wiersze sprzedaży, wiersze płatności oraz informacje o dostawie produktów i usług przetwarzanych w aplikacji POS. Użytkownik może określać kolumny, szerokości i położenie. W układach kompaktowy można również konfigurować dodatkowe informacje, które będą wyświetlane w wierszu pod wierszem głównym.
    - **Karta odbiorcy** — Karta odbiorcy pokazuje informacje odnoszące się do odbiorcy aktualnie skojarzonego z transakcją. Kartę odbiorcy można skonfigurować tak, aby ukrywała lub pokazywała dodatkowe informacje.
    - **Formant karty** — Do układu ekranu można dodać formant karty, a następnie wewnątrz niego umieścić inne formanty, na przykład klawiatury numerycznej, karty odbiorcy lub siatek przycisków. Formant karty jest kontenerem, który pomaga zmieścić więcej zawartości na ekranie. Formant karty jest dostępny tylko w układach pełnowymiarowych.
    - **Obraz** — Formant obrazu może służyć do wyświetlania logo sklepu lub innego obrazu identyfikacyjnego marki na ekranie **Transakcja**. Formant obrazu jest dostępny tylko w układach pełnowymiarowych.
    - **Rekomendowane produkty** — Jeśli formant rekomendowanych produktów zostanie skonfigurowany dla środowiska, będzie wyświetlał sugestie produktów przy użyciu mechanizmu uczenia maszynowego.
    - **Formant niestandardowy** — Formant niestandardowy pełni rolę symbolu zastępczego w układzie ekranu, pozwalając rezerwować miejsce na niestandardową zawartość. Formant niestandardowy jest dostępny tylko w układach pełnowymiarowych.

### <a name="compact-layout-designer"></a>Projektant układu kompaktowego

Analogicznie do projektanta układu pełnowymiarowego, projektant układu kompaktowego umożliwia konfigurowanie układu ekranu aplikacji dla telefonów i małych tabletów. Jednak w tym wypadku układ jest stały. Formanty w układzie można konfigurować, klikając prawym przyciskiem myszy i używając menu skrótów. Nie można jednak używać operacji przeciągania i upuszczania dla dodatkowej zawartości.

![Projektant układu kompaktowego](../commerce/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Projektant siatki przycisków

Projektant siatki przycisków pozwala konfigurować siatki przycisków, których można używać na ekranach powitalnym i **Transakcja** w aplikacji POS w układach pełnowymiarowych i kompaktowych. Tej samej siatki przycisków można używać w różnych układach i typach układów. Podobnie jak projektant układu ekranu, projektant siatki przycisków używa technologii wdrażania ClickOnce, która powoduje pobranie, zainstalowanie i uruchomienie najnowszej wersji aplikacji za każdym razem, gdy użytkownicy uzyskują do niej dostęp. Należy koniecznie sprawdzić wymagania technologii ClickOnce w kwestii przeglądarek internetowych. Niektóre przeglądarki, takie jak Google Chrome, wymagają rozszerzeń.

![Projektant siatki przycisków](../commerce/media/Button-Grid-Designer.png)

- **Nowy przycisk** — Kliknij, aby dodać nowy przycisk do siatki przycisków. Domyślnie nowe przyciski pojawiają się w lewym górnym rogu siatki. Jednak można inaczej rozmieścić przyciski, przeciągając je w układzie.

    > [!IMPORTANT]
    > Zawartość siatki przycisków może się nakładać. Dlatego podczas rozmieszczania przycisków upewnij się, że nie zakrywają innych przycisków.

- **Nowy projekt** — Kliknięcie tej opcji umożliwia automatyczne skonfigurowanie układu siatki przycisków poprzez określenie liczby przycisków w wierszach i kolumnach.
- **Właściwości przycisku** — Można skonfigurować właściwości przycisku, klikając przycisk prawym przyciskiem myszy i używając menu skrótów.

    > [!IMPORTANT]
    > Niektóre ustawienia siatki przycisków mają zastosowanie tylko do aplikacji Enterprise POS, a nie Modern POS ani Cloud POS.

    ![Właściwości przycisku w siatce przycisków](../commerce/media/Button-grid-button-properties.png)

    - **Akcja** — Na liście operacji aplikacji POS mających zastosowanie wybierz operację, która jest wywoływana po kliknięciu przycisku w aplikacji POS.

        Aby uzyskać listę obsługiwanych operacji aplikacji POS, zobacz [Operacje online i offline w punkcie sprzedaży (POS)](pos-operations.md).

    - **Parametry akcji** — Niektóre operacje w aplikacji POS używają dodatkowych parametrów podczas wywoływania. Na przykład dla operacji Dodaj produkty użytkownicy mogą określić produkt, który ma zostać dodany.
    - **Tekst przycisku** — Wprowadź tekst, który ma być wyświetlany na przycisku w aplikacji POS.
    - **Ukryj tekst przycisku** — To pole wyboru służy do określania, czy tekst przycisku ma być ukryty, czy widoczny. Tekst przycisku jest często ukrywany na małych przyciskach i wtedy widać tylko ikonę.
    - **Etykietka narzędzia** — Wprowadź dodatkowy tekst pomocy, który ma się pojawiać, gdy użytkownik umieści wskaźnik myszy na przycisku.
    - **Rozmiar w kolumnach/Rozmiar w wierszach** — Można określić wysokość i szerokość przycisku.

        ![Rozmiary przycisków w aplikacji POS wyrażone w wierszach i kolumnach](../commerce/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Niestandardowa czcionka** — Po zaznaczeniu pola wyboru **Włącz czcionkę niestandardową dla programu POS** można dla aplikacji POS określić czcionkę inną niż domyślna czcionka systemowa.
    - **Motyw niestandardowy** — Domyślnie przyciski aplikacji POS używają koloru wiodącego z profilu graficznego. Po zaznaczeniu pola wyboru **Użyj motywu niestandardowego** można określić dodatkowe kolory.

        > [!NOTE]
        > W aplikacjach Modern POS i Cloud POS są używane tylko wartości **Kolor tła** i **Kolor czcionki**.

    - **Obraz przycisku** — Przyciski mogą zawierać obrazy lub ikony. Wybierz jeden z dostępnych obrazów podanych w oknie **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Obrazy**.

![Przykład siatki przycisków w aplikacji POS](../commerce/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Instalowanie projektanta układów aplikacji Retail Point of Sale (POS)](install-pos-layout-designer.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]