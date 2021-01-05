---
title: Interfejs Projektanta raportów
description: Ten artykuł wyjaśnia, jak się poruszać w Projektancie raportów i jak używać różnych opcji do własnych potrzeb.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f0fb8052948b2d1b9297d30d6c5da186f8898bfc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687477"
---
# <a name="report-designer-interface"></a>Interfejs Projektanta raportów

[!include [banner](../includes/banner.md)]

Ten artykuł wyjaśnia, jak się poruszać w Projektancie raportów i jak używać różnych opcji do własnych potrzeb.

## <a name="report-designer-menu-commands"></a>Polecenia menu Projektanta raportów

W poniższych tabelach opisano polecenia menu i opcje, których można używać podczas projektowania sprawozdań finansowych. Niektóre polecenia menu i opcje są dostępne tylko w określonych warunkach. Na przykład polecenia promocji i obniżanie poziomu jednostek raportowania są dostępne tylko podczas modyfikowania definicji drzewa raportowania.

### <a name="file-menu"></a>Menu Plik

Menu **Pliku** jest dostępne dla wszystkich użytkowników i obejmuje następujące polecenia.

| Polecenie                           | Opis |
|-----------------------------------|-------------|
| Nowy                               | Tworzenie nowej definicji raportu, definicji wiersza, definicji kolumny, definicji drzewa raportowania, definicji grupy raportów lub folderu. Dodatkowe opcje są dostępne, w zależności od roli użytkownika. |
| Otwarto                              | Otwieranie istniejącej definicji wiersza, definicji kolumny, definicji drzewa raportowania lub definicji raportu. |
| Zamknij                             | Zamykanie bieżącego bloku konstrukcyjnego. |
| Zamknij wszystko                         | Zamykanie wszystkich bloków konstrukcyjnych. |
| Zapisz                              | Zapisywanie bieżącej definicji wiersza, definicji kolumny, definicji drzewa raportowania lub definicji raportu. |
| Zapisz jako                           | Zapisywanie bieżącej definicji wiersza, definicji kolumny, definicji drzewa raportowania lub definicji raportu pod nową nazwą. |
| Właściwości                        | Otwieranie okna dialogowego **Właściwości**, w którym można zmienić nazwę i opis raportu. |
| Generuj                          | Generowanie bieżącego raportu. To polecenie jest dostępne z definicji raportu. |
| Wyświetl raport                       | Otwieranie najnowszej wersji wygenerowanego raportu. To polecenie jest dostępne z definicji raportu po wygenerowaniu co najmniej jednego raportu. |
| Ostatnie definicje raportów         | Umożliwia wyświetlenie listy raportów, które zostały ostatnio utworzone lub zmodyfikowane. Następnie można wybrać raport z listy. |
| Ostatnie definicje wierszy            | Umożliwia wyświetlenie listy definicji wierszy, które zostały ostatnio utworzone lub zmodyfikowane. Następnie można wybrać definicję wiersza z listy. |
| Ostatnie definicje kolumn         | Umożliwia wyświetlenie listy definicji kolumn, które zostały ostatnio utworzone lub zmodyfikowane. Następnie można wybrać definicję kolumny z listy. |
| Ostatnie definicje drzew raportowania | Umożliwia wyświetlenie listy definicji drzew raportowania, które zostały ostatnio utworzone lub zmodyfikowane. Następnie można wybrać definicję drzewa raportowania z listy. |
| Zakończ                              | Zamykanie projektanta raportów. |

### <a name="edit-menu"></a>Menu Edycja

Menu **Edycja** jest dostępne dla użytkowników, którzy mają role **Konstruktor** lub **Administrator**. Obejmuje ono następujące polecenia:

| Polecenie                                | Opis |
|----------------------------------------|-------------|
| Cofnij                                   | Cofnięcie ostatniego działania. |
| Wykonaj ponownie                                   | Cofnięcie ostatniego cofnięcia. |
| Wytnij                                    | Usuwanie zaznaczonego tekstu i kopiowanie go do schowka. |
| Kopiuj                                   | Kopiowanie zaznaczonego tekstu do schowka. |
| Wklej                                  | Wstawienie ostatnio wyciętego lub skopiowanego tekstu ze schowka. |
| Wyczyść                                  | Usuwanie zawartości zaznaczonej komórki bloku konstrukcyjnego. |
| Znajdź                                   | Otwieranie okna dialogowego **Znajdź i zastąp**, które umożliwia wyszukiwanie tekstu w okienku widoku. |
| Zamień                                | Otwieranie okna dialogowego **Znajdź i zastąp**, które umożliwia wyszukiwanie i zastępowanie tekstu w okienku widoku. |
| Wstaw wiersze z wymiarów            | Otwieranie okna dialogowego **Wstawianie wierszy z wymiarów**, w którym można wybrać wartości wymiaru do uwzględnienia w definicji wiersza. To polecenie jest dostępne z definicji wiersza. |
| Ponowne numerowanie wierszy                          | Ponowne numerowanie wszystkich kodów wiersza. To polecenie jest dostępne z definicji wiersza. |
| Łącza wiersza                              | Otwieranie okna dialogowego **Łącza wiersza**, w którym można określić źródła dla łącza danych w definicje wierszy i raportowania drzewa. To polecenie jest dostępne z definicji wiersza. |
| Korygowanie zaokrągleń                    | Otwieranie okna dialogowego **Korygowanie zaokrągleń**, w którym można określić parametry zaokrąglania. To polecenie jest dostępne z definicji wiersza. |
| Zarządzanie zestawami wymiarów                  | Otwieranie okna dialogowego **Zestawy wymiarów**, w którym można tworzyć i modyfikować zestawy wymiarów. To polecenie jest dostępne z definicji wiersza lub definicji drzewa raportowania. |
| Wstaw wiersz                             | Wstawianie pustego wiersza na w definicji wiersza lub pustego wiersza nagłówka w definicji kolumny. To polecenie jest dostępne z definicji wiersza lub definicji kolumny. |
| Usuń wiersz                             | Usuwanie zaznaczonego wiersza z definicji wiersza lub zaznaczonego wiersza nagłówka z definicji kolumny. To polecenie jest dostępne z definicji wiersza lub definicji kolumny. |
| Wstaw kolumnę                          | Wstawianie pustej kolumny w definicji kolumny. To polecenie jest dostępne z definicji kolumny. |
| Usuń kolumnę                          | Usuwanie zaznaczonej kolumny z definicji kolumny. To polecenie jest dostępne z definicji kolumny. |
| Wstawianie jednostek raportowania z wymiarów | Otwieranie okna dialogowego **Wstawianie jednostek raportowania z wymiarów**, w którym można wybrać wartości wymiaru do uwzględnienia w definicji drzewa raportowania. To polecenie jest dostępne z definicji drzewa raportowania. |
| Importuj hierarchię zestawu wymiarów         | Otwieranie okna dialogowego **Hierarchia zestawu wymiarów**, w których można importować hierarchię zestawu wymiarów z danych finansowych. To polecenie jest dostępne z definicji drzewa raportowania dla systemu opartego na ..\\wymiarach finansowych\\wymiarach. |
| Wstaw jednostkę raportowania                  | Umożliwia wstawienie pustego wiersza do definicji drzewa raportowania. To polecenie jest dostępne z definicji drzewa raportowania. |
| Usuń jednostkę raportowania                  | Usuwanie zaznaczonego wiersza jednostki raportowania z definicji drzewa raportowania. To polecenie jest dostępne w definicji drzewa raportowania. |

### <a name="view-menu"></a>Menu Widok

Menu **Widok** jest dostępne dla wszystkich użytkowników i obejmuje następujące polecenia.

| Polecenie         | Opis                                                            |
|-----------------|------------------------------------------------------------------------|
| Okienko nawigacji | Wyświetlanie lub ukrywanie okienka nawigacji.                                      |
| Paski narzędzi        | Wybieranie widocznych pasków narzędzi.                                  |
| Pasek stanu      | Wyświetlanie lub ukrywanie informacji o stanie w oknie **Projektant raportów**. |
| Strona powitalna    | Umożliwia otwarcie strony **Witamy**.                                             |

### <a name="format-menu"></a>Menu Format

Menu **Format** jest dostępne dla użytkowników, którzy mają role **Konstruktor** lub **Administrator**. Obejmuje ono następujące polecenia:

| Polecenie               | Opis |
|-----------------------|-------------|
| Style i formatowanie | Otwieranie okna dialogowego **Style i formatowanie**, w którym można tworzyć i modyfikować style tekstu w definicje wierszy oraz kolumn. To polecenie jest dostępne z definicji wiersza lub definicji kolumny. |
| Szerokość kolumny          | Otwieranie okna dialogowego **Szerokość kolumny**, w którym można ustawić szerokość wybranej kolumny. To polecenie jest dostępne z definicji wiersza, definicji kolumny lub definicji drzewa raportowania. |
| Ukryj                  | Ukrywanie zaznaczonej kolumny. To polecenie jest dostępne z definicji wiersza, definicji kolumny lub definicji drzewa raportowania. |
| Odkryj                | Wyświetlanie kolumn ukrytych między zaznaczonymi kolumnami. To polecenie jest dostępne z definicji wiersza, definicji kolumny lub definicji drzewa raportowania. |

### <a name="company-menu"></a>Menu Firma

Menu **Firma** jest dostępne dla użytkowników, którzy mają role **Konstruktor** lub **Administrator**. Obejmuje ono następujące polecenia:

| Polecenie               | Opis                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Firmy             | Otwieranie okna dialogowego **Firmy**, w którym można tworzyć i modyfikować firmy.                                          |
| Grupy bloków konstrukcyjnych | Otwieranie okna dialogowego **Grupa bloków konstrukcyjnych**, gdzie można tworzyć, modyfikować, importować i eksportować grupy bloków konstrukcyjnych. |

### <a name="go-menu"></a>Menu Przejdź

Menu **Przejdź** jest dostępne dla wszystkich użytkowników i zawiera następujące polecenia.

> [!NOTE]
> Skutków zastosowania tych poleceń nie widać, jeśli okienko nawigacji jest niewidoczne.

| Polecenia                   | Opis                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Definicje raportu         | Umożliwia wyświetlanie definicji raportu w okienku nawigacji.                                    |
| Definicje wierszy            | Umożliwia wyświetlanie definicji wiersza w okienku nawigacji.                                       |
| Definicje kolumn         | Umożliwia wyświetlanie definicji kolumny w okienku nawigacji.                                    |
| Definicje drzew raportowania | Umożliwia wyświetlanie definicji drzew raportowania w okienku nawigacji.                            |
| Zabezpieczenia                   | Umożliwia wyświetlenie informacji o zabezpieczeniach dla użytkowników, grup i firm w okienku nawigacji. |

### <a name="tools-menu"></a>Menu Narzędzia

Menu **Narzędzia** jest dostępne dla wszystkich użytkowników, ale niektóre polecenia ograniczonej dostępności. Obejmuje ono następujące polecenia:

| Polecenie                       | Opis |
|-------------------------------|-------------|
| Ochrona                       | Umożliwia zabezpieczenie bieżącego bloku konstrukcyjnego hasłem. To polecenie jest dostępne dla użytkowników, którzy mają rolę **Projektant** lub **Administrator**. |
| Stan kolejki raportów           | Pozwala otworzyć okno dialogowe **Stan kolejki raportów** okno dialogowe, w którym widoczne są wszystkie niedawno generowane raporty i szczegółów dla każdego raportu. |
| Informacje o systemie źródłowym     | Umożliwia wyświetlenie ustawień dla systemu Microsoft Dynamics ERP. To polecenie jest dostępne dla użytkowników, którzy mają rolę **Projektant** lub **Administrator**. |
| Elementy wyewidencjonowane             | Umożliwia wyświetlenie definicji wierszy, definicji kolumn, definicje drzew raportowania i definicje raportów, które są aktualnie otwarte. To polecenie jest dostępne dla użytkowników, którzy mają rolę **Projektant** lub **Administrator**. |
| Odśwież dane finansowe w pamięci podręcznej | Pozwala zaktualizować dane w kolumnie wymiary finansowe. |
| Opcje                       | Otwórz okno dialogowe **Opcje**, w którym można zmodyfikować preferencje użytkownika dla Projektanta raportów. |

### <a name="window-menu"></a>Menu Okno

Menu **Okno** jest dostępne dla wszystkich użytkowników i obejmuje następujące polecenia.

| Polecenie              | Opis |
|----------------------|-------------|
| Sąsiadująco w poziomie    | Pokaż wszystkie otwarte okna obok siebie. |
| Sąsiadująco w pionie      | Pokaż wszystkie otwarte okna jedno na drugim. |
| Kaskadowo              | Ułóż wszystkie otwarte okna tak aby pasek tytułu każdego okna był widoczny. |
| Zablokuj w poziomie    | Zablokuj wybrany wiersz, aby podczas przewijania ten wiersz był nadal widoczny w oknie. To polecenie jest dostępne dla użytkowników, którzy mają rolę **Projektant** lub **Administrator**. |
| Zablokuj w pionie      | Zablokuj wybraną kolumnę, aby podczas przewijania ta kolumna była nadal widoczna w oknie. To polecenie jest dostępne dla użytkowników, którzy mają rolę **Projektant** lub **Administrator**. |
| Lista otwartych okien | Pokaż listę otwartych okien. Wybierz okno, aby przenieść je na pierwszy plan. |

### <a name="help-menu"></a>Menu Pomoc

Menu **Pomoc** jest dostępne dla wszystkich użytkowników i obejmuje następujące polecenia.

| Command | Opis                                                              |
|---------|--------------------------------------------------------------------------|
| Pomoc    | Otwieranie tematu pomocy dotyczącego sprawozdawczości finansowej. |
|         |                                                                          |

## <a name="report-designer-toolbar-buttons"></a>Przyciski paska narzędzi Projektanta raportów
W poniższych tabelach opisano przyciski paska narzędzi, których można używać podczas projektowania raportów. Niektóre przyciski paska narzędzi są dostępne tylko w określonych warunkach. Na przykład przyciski promocji i obniżanie poziomu jednostek raportowania są dostępne tylko podczas modyfikowania definicji drzewa raportowania.

### <a name="standard-toolbar"></a>Standardowy pasek narzędzi

Standardowy pasek narzędzi zapewnia szybki dostęp do plików i poleceń edycji. Ten pasek narzędzi zawiera następujące przyciski.

| Przycisk                                                                                       | Opis |
|----------------------------------------------------------------------------------------------|-------------|
| [![Przycisk Nowy](./media/rowc130389.png)](./media/rowc130389.png)                              | Utwórz nową (pustą) definicję raportu, definicję wiersza, definicję kolumny lub definicję drzewa raportowania. |
| [![Przycisk Otwórz](./media/openfolderc130389.png)](./media/openfolderc130389.png)               | Otwieranie istniejącej definicji wiersza, definicji kolumny, definicji drzewa raportowania lub definicji raportu. |
| [![Przycisk Zapisz](./media/savec130389.png)](./media/savec130389.png)                           | Zapisywanie bieżącej definicji wiersza, definicji kolumny, definicji drzewa raportowania lub definicji raportu. |
| [![Przycisk Kopiuj](./media/copyc130389.png)](./media/copyc130389.png)                           | Kopiowanie zaznaczonego tekstu do schowka. |
| [![Przycisk Wytnij](./media/cutc130389.png)](./media/cutc130389.png)                              | Usuwanie zaznaczonego tekstu i kopiowanie go do schowka. |
| [![Przycisk Wklej](./media/pastec130389.png)](./media/pastec130389.png)                        | Wstaw tekst ze schowka. |
| [![Przycisk Cofnij](./media/undoc130389.png)](./media/undoc130389.png)                           | Cofnięcie ostatniego działania. |
| [![Przycisk Ponów](./media/redoc130389.png)](./media/redoc130389.png)                           | Cofnięcie ostatniego cofnięcia. |
| [![Przycisk Znajdź](./media/findc130389.png)](./media/findc130389.png)                           | Otwieranie okna dialogowego **Znajdź i zastąp**, które umożliwia wyszukiwanie i zastępowanie tekstu w aktywnym oknie. |
| [![Przycisk Wstaw wiersz](./media/insertrowc130389.png)](./media/insertrowc130389.png)           | Wstawianie pustego wiersza na w definicji wiersza lub pustego wiersza nagłówka w definicji kolumny. Ten przycisk jest dostępny z definicji wiersza lub definicji kolumny. |
| [![Przycisk Wstaw kolumnę](./media/insertcolumnc130389.png)](./media/insertcolumnc130389.png)  | Wstawianie pustej kolumny w definicji kolumny. Ten przycisk jest dostępny z definicji kolumny. |
| [![Przycisk Zablokuj](./media/lockc130389.png)](./media/lockc130389.png)                           | Umożliwia zabezpieczenie bieżącego bloku konstrukcyjnego hasłem. Ten przycisk jest dostępny dla użytkowników, którzy mają role **Projektant** lub **Administrator**. |
| [![Przycisk Łącze wiersza](./media/rowlinkc130389.png)](./media/rowlinkc130389.png)                 | Otwieranie okna dialogowego **Łącza wiersza**, w którym można określić źródła dla łącza danych w definicje wierszy i raportowania drzewa. Ten przycisk jest dostępny z definicji wiersza. |
| [![Przycisk Podwyższ poziom](./media/promotec130389.png)](./media/promotec130389.png)                  | Podnieś poziom jednostki w definicji drzewa raportowania. Po wybraniu jednostki podrzędnej i kliknięciu przycisku **Podnieś poziom** jednostka podrzędna jest przenoszona na ten sam poziom co jednostka nadrzędna. |
| [![Przycisk Obniż poziom](./media/demotec130389.png)](./media/demotec130389.png)                     | Obliż poziom jednostki raportowania drzewa definicji. Po wybraniu jednostki i kliknięciu przycisku **Obniż poziom** jednostka staje się podrzędna względem jednostka która jest przed nią. |
| [![Przycisk Rozwiń](./media/expandtreebuttonc130389.png)](./media/expandtreebuttonc130389.png) | Rozwiń wszystkie jednostki definicji drzewa raportowania na poziomie wybranej jednostki. |
| [![Przycisk Zwiń](./media/collapsec130389.png)](./media/collapsec130389.png)               | Zwiń drzewo raportowania. |
| [![Przycisk Pomoc](./media/helpc130389.png)](./media/helpc130389.png)                           | Otwieranie Pomocy. |

### <a name="formatting-toolbar"></a>Pasek narzędzi Formatowanie

Pasek narzędzi formatowania zapewnia łatwy dostęp do poleceń stylów. Ten pasek narzędzi zawiera następujące przyciski.

| Przycisk                                                                                                       | Opis                                             |
|--------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| [![Przycisk Styl czcionki](./media/formattingc130389.png)](./media/formattingc130389.png)                         | Zastosuj wybrany styl czcionki do bieżącego tekstu.      |
| [![Przycisk Czcionka](./media/fonttype.png)](./media/fonttype.png)                                                 | Zastosuj wybraną czcionkę w bieżącym tekście.              |
| [![Przycisk Rozmiar czcionki](./media/fontsize.png)](./media/fontsize.png)                                            | Ustaw wybraną czcionkę w bieżącym tekście (w punktach). |
| [![Przycisk Pogrubienie](./media/boldc130389.png)](./media/boldc130389.png)                                           | Zastosuj pogrubienie do bieżącego tekstu.                             |
| [![Przycisk Kursywa](./media/italicsc130389.png)](./media/italicsc130389.png)                                   | Zastosuj kursywę do bieżącego tekstu.                           |
| [![Przycisk Podkreślenie](./media/underlinec130389.png)](./media/underlinec130389.png)                            | Podkreśl bieżący tekst.                             |
| [![Przycisk Zmniejsz wcięcie](./media/outdentlsc130389.png)](./media/outdentlsc130389.png)                      | Zmniejszenie wcięcia bieżącego tekstu.                |
| [![Przycisk Zwiększ wcięcie](./media/indentlsc130389.png)](./media/indentlsc130389.png)                        | Zwiększenie wcięcia bieżącego tekstu.                |
| [![Przycisk Kolor tła](./media/fillbackgroundcolorc130389.png)](./media/fillbackgroundcolorc130389.png) | Zmiana koloru tła bieżącej komórki.        |
| [![Przycisk Kolor czcionki](./media/fontcolorc130389.png)](./media/fontcolorc130389.png)                           | Zmiana koloru bieżącego tekstu.                   |

### <a name="report-designer-toolbar"></a>Pasek narzędzi projektanta raportów

Pasek narzędzi projektanta raportów oferuje szybki dostęp do poleceń nawigowania wewnątrz projektanta raportów. Ten pasek narzędzi zawiera następujące przyciski.

| Przycisk                                                                                              | Opis |
|-----------------------------------------------------------------------------------------------------|-------------|
| [![Przycisk Definicja raportu](./media/reportc130389.png)](./media/reportc130389.png)                 | Wyświetlanie definicji raportu, która jest wyświetlana w menu **Okno**. |
| [![Przycisk Definicja wiersza](./media/rowc130389.png)](./media/rowc130389.png)                          | Umożliwia wyświetlenie definicji wiersza, która jest przypisana do definicji aktywnego raportu. |
| [![Przycisk Definicja kolumny](./media/columnc130389.png)](./media/columnc130389.png)                 | Umożliwia wyświetlenie definicji kolumny, która jest przypisana do definicji aktywnego raportu. |
| [![Przycisk Definicja drzewa raportowania](./media/treec130389.png)](./media/treec130389.png)             | Umożliwia wyświetlenie definicji drzewa raportowania, która jest przypisana do definicji aktywnego raportu. |
| [![Przycisk Report Viewer](./media/reportviewerc130389.png)](./media/reportviewerc130389.png)         | Uruchom Report Viewer i pokaż najnowszą wersję generowanego raportu. Ten przycisk jest dostępny z definicji raportu po wygenerowaniu co najmniej jednego raportu. |
| [![Przycisk Generuj raport](./media/generate-to-ddvc130389.png)](./media/generate-to-ddvc130389.png) | Generowanie raportu na podstawie aktywnej definicji raportu. Ten przycisk jest dostępny w oknie definicji raportu. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie finansowe](financial-reporting-intro.md)

[Generowanie raportów finansowych](generate-financial-report.md)
