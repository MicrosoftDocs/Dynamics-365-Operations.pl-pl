---
title: Aby pobrać dane z wielu tabel aplikacji, należy zastosować SPRĘŻENIE źródeł danych w mapowaniach modeli ER
description: W tym temacie wyjaśniono, jak można używać SPRĘŻENIA źródeł danych wielu firm w Raportowaniu elektronicznym (ER).
author: NickSelin
ms.date: 04/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: c9a06c048e98676e30a6652cad6634c2e13531d4ebc6d35f325f4c7153cd82ae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723220"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Aby pobrać dane z wielu tabel aplikacji, należy zastosować SPRĘŻENIE źródeł danych w mapowaniach modeli Raportowania elektronicznego (ER)

[!include[banner](../includes/banner.md)]

Konfigurując mapowania lub formaty modeli raportowania elektronicznego (ER), można [dodać](#review) wymagane źródła danych typu **sprzężenia**. W czasie projektowania źródło danych **sprzężenia** jest konfigurowane jako zbiór kilku źródeł danych, z których każdy zwraca listę rekordów. Dla każdego źródła danych z wyjątkiem pierwszego należy zdefiniować niezbędne warunki, aby dołączyć rekordy bieżącego i poprzedniego źródła danych. W czasie wykonywania, skonfigurowane źródło danych typu **sprężenia** [zwraca](#executeERformat) pojedynczą połączoną listę rekordów zawierającą pola z rekordów zagnieżdżonych źródeł danych.

Obecnie obsługiwane są następujące typy sprzężeń:

- Sprzężenie zewnętrzne (lewe):
    - Dołącz wszystkie rekordy w pierwszym (najbardziej do lewej) źródle danych, a następnie wszelkie uzgodnienia zgodnie z skonfigurowanymi rekordami warunków drugiego (najbardziej do prawej) źródła danych.
- Sprzężenie zewnętrzne (prawe):
    - Dołącz tylko rekordy w pierwszym (najbardziej do lewej) źródle danych, a następnie wszelkie uzgodnienia zgodnie z skonfigurowanymi rekordami warunków tylko drugiego (najbardziej do prawej) źródła danych.

W skonfigurowanym źródle danych **sprężenia**, gdy wszystkie źródła danych są typu **Rekordy tabeli**, wykonanie źródła danych sprzężenia można [wykonać na poziomie bazy danych](#analyze) przy użyciu pojedynczej instrukcji SQL. Ta instrukcja zmniejsza liczbę wywołań bazy danych, zwiększając wydajność mapowania modeli. W przeciwnym razie wykonanie źródła **Danych sprzężenia** jest wykonywane w pamięci.

> [!NOTE]
> Użycie funkcji **VALUEIN** w wyrażeniach ER określających warunki dołączania rekordów w źródłach danych typu sprzężenia nie jest jeszcze obsługiwane. Odwiedź stronę [Projektant formuł w module Raportowanie elektroniczne (ER)](general-electronic-reporting-formula-designer.md), aby uzyskać szczegółowe informacje na temat tej funkcji.

Wykonaj przykład z tego tematu, aby dowiedzieć się więcej na temat tej funkcji.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Przykład: używanie źródeł danych SPRZĘŻENIA w mapowaniach modelu ER

Poniższe kroki wyjaśniają, jak administrator systemu lub projektant raportu elektronicznego może skonfigurować mapowanie modelu Raportowania elektronicznego (ER) w celu pobrania danych z wielu tabel aplikacji jednocześnie, używając źródeł danych typu **Sprzężenia** do poprawy wydajności dostępu do danych. Te kroki można wykonać dla dowolnej firmy należącej do Dynamics 365 Finance lub Regulatory Configuration Services (RCS).

### <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym temacie, należy mieć dostęp do jednej z następujących czynności, w zależności od tego, jaka usługa jest używana do konkurowania następujących kroków:

**Dostęp do Finance w jednej z następujących ról:**

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

**Dostęp do RCS w jednej z następujących ról:**

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Musisz najpierw wykonać kroki procedury [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Należy również wcześniej pobrać i zapisać następujące przykładowe pliki konfiguracji ER:

| **Opis zawartości**  | **Nazwa pliku**   |
|--------------------------|-----------------|
| Przykładowy plik konfiguracji **modelu danych ER**, który jest używany jako źródło danych przykładów.| [Model do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml](https://download.microsoft.com/download/5/c/1/5c1d8a57-6ebd-425b-bc5d-c71dde92c6af/ModeltolearnJOINdatasources.version.1.xml) |
| Przykładowy plik konfiguracji **modelu mapowania ER**, który wprowadza model danych ER dla przykładów. | [Mapowanie do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml](https://download.microsoft.com/download/9/2/f/92f339ca-41fc-4f5e-b458-6983c957d3dd/MappingtolearnJOINdatasources.version.1.1.xml)|
| Przykładowa konfiguracja pliku **formatu ER**. Ten plik opisuje dane, które zapełnią składnik formatu ER dla przykładów. | [Format do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml.](https://download.microsoft.com/download/f/f/8/ff8f1b48-14d0-4c73-9145-bcdf8b5265bc/FormattolearnJOINdatasources.version.1.1.xml) |

### <a name="activate-a-configurations-provider"></a>Aktywuj dostawcę konfiguracji

1. W pierwszej sesji przeglądarki sieci Web należy uzyskać dostęp do Finance lub RCS.
2. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.
3. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** sprawdź, czy dostawca konfiguracji dla przykładowej firmy [Litware, Inc.](http://www.litware.com) jest wymieniony na liście i czy jest oznaczony jako **Aktywny**. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki w procedurze [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Obszar roboczy raportowania elektronicznego.](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Importuj przykładową konfigurację pliku formatu ER.

1. Wybierz **Raportowanie konfiguracji**.
2. Zaimportuj plik konfiguracji modelu danych ER.
    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Wybierz przycisk **Przeglądaj**, aby znaleźć plik **Model do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml**.
    4. Kliknij przycisk **OK**.
3. Zaimportuj plik mapowania modelu danych ER.
    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Wybierz przycisk **Przeglądaj**, aby znaleźć plik **Mapowanie do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml**.
    4. Kliknij przycisk **OK**.
4. Importuj plik konfiguracji formatu ER.
    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Wybierz przycisk **Przeglądaj**, aby znaleźć plik **Format do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml**.
    4. Kliknij przycisk **OK**.
5. W drzewie konfiguracji rozwiń **Model do nauczenia SPRĘŻENIA źródeł danych**, a także inne elementy modelu (jeśli są dostępne).
6. Zaobserwuj listę konfiguracji modelu ER w drzewie, jak również szczegóły wersji na karcie skróconej **Wersje** — będą one używane jako źródło danych dla przykładowego raportu.

    ![Strona konfiguracji raportowania elektronicznego.](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Włącz opcje śledzenia wykonania

1. Wybierz **KONFIGURACJE**.
2. Wybierz **Parametry użytkownika**.
3. Określ parametry śledzenia wykonania, tak jak pokazano na poniższym zrzucie ekranu.

    ![Strona parametrów użytkownika raportowania elektronicznego.](./media/GER-JoinDS-Parameters.PNG)

    Jeśli te parametry są włączone, dla każdego wykonania importowanego pliku formatu ER zostanie wygenerowana funkcja śledzenia wykonania. Korzystając ze szczegółowych informacji o generowanym śledzeniu wykonania, można analizować wykonywanie formatów ER i składników mapowania modelu ER. Aby dowiedziec się więcej na temat funkcji śledzenia wykonywania ER, odwiedź stronę [Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md).

### <a name="review-er-model-mapping-part-1"></a>Przegląd mapowania modelu ER (część 1)

Przejrzyj ustawienia składnika mapowania modelu ER. Składnik jest skonfigurowany pod kątem dostępu do informacji na temat wersji konfiguracji systemu ER, szczegółów konfiguracji i dostawców konfiguracji bez użycia źródeł danych typu **Sprzężenia**.

1. Wybierz konfigurację **Mapowanie do nauczenia SPRĘŻENIA źródeł danych**.
2. Wybierz opcję **Projektant**, aby otworzyć listę mapowań.
3. Wybierz opcję **Projektant**, aby przejrzeć szczegóły mapowania.
4. Wybierz **Pokaż szczegóły**.
5. W drzewie konfiguracje rozwiń pozycję elementy modelu danych **Set1** i **Set1.Details**:

    1. Powiązanie **Szczegóły powiązania: Lista rekordów = wersje** wskazuje, że pozycja **Set1.Details** jest związana z **Wersjami** źródła danych zwracającymi rekordy tabeli **ERSolutionVersionTable**. Każdy rekord tej tabeli reprezentuje jedną wersję konfiguracji ER. Zawartość tej tabeli jest prezentowana na karcie skróconej **Wersje** na stronie **Konfiguracje**.
    2. Powiązanie **ConfigurationVersion: String = @.PublicVersionNumber** oznacza, że wartość publicznej wersji każdej konfiguracji jest pobierana z pola **PublicVersionNumber** tabeli **ERSolutionVersionTable** i umieszczana na elemencie **ConfigurationVersion**.
    3. Powiązanie **ConfigurationTitle: String = @.'>Relations'.Solution.Name** wskazuje, że nazwa konfiguracji ER odnoszącej się do obiektu jest pobierana z pola **Nazwa** tabeli **ERSolutionTable** oceniając przy użyciu relacji wiele-do-jednego (**'>Relacje'**) między tabelami **ERSolutionVersionTable** i **ERSolutionTable**. Nazwy konfiguracji ER dla bieżącego wystąpienia aplikacji są wyświetlane w drzewie konfiguracje na stronie **Konfiguracje**.
    4. Powiązanie **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** oznacza, że nazwa dostawcy konfiguracji, który posiada obecną konfigurację jest pobierana z pola **Nazwa** tabeli **ERVendorTable** oceniając przy użyciu relacji wiele-do-jednegomiędzy tabelami **ERSolutionTable** i **ERVendorTable**. Nazwy dostawców konfiguracji ER dla bieżącego wystąpienia aplikacji są wyświetlane w drzewie konfiguracje na stronie **Konfiguracje** na nagłówku dla każdej konfiguracji osobno. Całą listę dostawców konfiguracji modelu encja-relacja można znaleźć na stronie **Administrowanie organizacją \> Raportowanie elektroniczne \> Dostawca konfiguracji**.

    ![Strona Projektant mapowania modelu ER, lista powiązanych pozycji modelu danych.](./media/GER-JoinDS-Set1Review.PNG)

6. W drzewie konfiguracje rozwiń pozycję modelu danych **Set1.Summary**:

    1. Powiązanie **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** wskazuje, że element **Set1.Summary.VersionsNumber** jest powiązany z polem agregacji **VersionsNumber** w polu **VersionsSummary** źródło danych typu **GroupBy**, które zostało skonfigurowane do zwracania liczby rekordów tabeli **ERSolutionVersionTable** za pośrednictwem **Wersji** źródła danych.

    ![Edytuj stronę parametrów „Grupuj według”.](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Zamknij stronę.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> Przegląd mapowania modelu ER (część 2)

Przejrzyj ustawienia składnika mapowania modelu ER. Składnik jest skonfigurowany pod kątem dostępu do informacji na temat wersji konfiguracji systemu ER, szczegółów konfiguracji i dostawców konfiguracji z użyciem źródeł danych typu **Sprzężenia**.

1. W drzewie konfiguracje rozwiń pozycję elementy modelu danych **Set2** i **Set2.Details**: Powiązanie **Details: Record list = Details** wskazuje, że element **Set2.Details** jest powiązany ze źródłem danych **Szczegóły** skonfigurowanym jako źródło danych typu **Sprzężenie**.

    ![Strona Projektant mapowania modelu ER pokazująca rozwinięte pozycje modelu danych Set2:Record.](./media/GER-JoinDS-Set2Review.PNG)

    Źródło danych **sprzężenia** można dodać, wybierając **Functions\Join** źródło danych:

    ![Strona Projektant mapowania modelu ER, typ źródła danych sprzężenia.](./media/GER-JoinDS-AddJoinDS.PNG)

2. Wybierz źródło danych **szczegółów**.
3. Wybierz opcję **Edytuj** w okienku **Źródła danych**.
4. Wybierz opcję **Edycja sprężenia**.
5. Wybierz **Pokaż szczegóły**.

    ![Strona parametrów źródła danych SPRĘŻENIA.](./media/GER-JoinDS-JoinDSEditor.PNG)

    Ta strona służy do projektowania wymaganego źródła danych **typu sprzężenia**. W czasie wykonywania to źródło danych utworzy jedną przyłączoną listę rekordów ze źródeł danych w siatce **Połączonej listy**. Dołączenie rekordów zostanie rozpoczęte ze źródła danych **ConfigurationProviders**, które znajduje się w siatce jako pierwsza (dla niego jest pusta kolumna **Typ**). Rekordy z każdego innego źródła danych będą przyłączane w związku z rekordami nadrzędnego źródła danych na podstawie jego zamówienia w tej siatce. Każde dołączenie źródła danych musi być skonfigurowane jako źródło danych zagnieżdżone w docelowym źródle danych (źródło danych `1Versions` jest zagnieżdżone w `1Configurations`; źródło danych `1Configurations` jest zagnieżdżone w **ConfigurationProviders**). Każde skonfigurowane źródło danych musi zawierać warunki dla sprzężenia. W źródle danych dla tego konkretnego **Sprzężenia** zdefiniowano następujące sprzężenia:

    - Każdy rekord źródła danych **ConfigurationProviders** (odwołujący się do tabeli **ERVendorTable**) jest połączony tylko z rekordami **1Configurations** (określonymi w tabeli **ERSolutionTable**) o tej samej wartości w polach **SolutionVendor** i **RecId**. Typ **Sprzężenia wewnętrznego** jest używany dla tego sprzężenia, a także następujące warunki dotyczące dopasowywania rekordów:

    FILTROWANIE (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Każdy rekord źródła danych **1Configurations** (odwołujący się do tabeli **ERSolutionTable**) jest połączony tylko z rekordami **1Versions** (określonymi w tabeli **ERSolutionVersionTable**) o tej samej wartości w polach **Solution** i **RecId**. Typ **Sprzężenia wewnętrznego** jest używany dla tego sprzężenia, a także następujące warunki dotyczące dopasowywania rekordów:

    FILTROWANIE (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - Opcja **Wykonaj** jest skonfigurowana jako **Kwerenda**, co oznacza, że to źródło danych sprzężenia zostanie wykonane w czasie wykonywania na poziomie bazy danych jako bezpośrednie wywołanie SQL.

    W przypadku dołączania rekordów źródeł danych reprezentujących tabele aplikacji można określać warunki sprzężenia za pomocą par pól innych niż te, które opisują istniejące relacje drzewa obiektów aplikacji (AOT) między tymi tabelami. Ten typ sprzężenia można skonfigurować do wykonywania również na poziomie bazy danych.

6. Zamknij stronę.
7. Wybierz **Anuluj**.
8. W drzewie konfiguracje rozwiń pozycję modelu danych **Set2.Summary**:

    - Powiązanie **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** wskazuje, że element **Set2.Summary.VersionsNumber** jest powiązany z polem agregacji **VersionsNumber** w polu **DetailsSummary** źródło danych typu **GroupBy**, które zostało skonfigurowane do zwracania liczby połączonych rekordów źródła danych **Szczegóły** typu **Sprężenia**.
    - Opcja lokalizacji **Wykonaj** jest skonfigurowana jako **Zapytanie**, co oznacza, że to źródło danych typu **GroupBy** będzie uruchamiane w czasie wykonywania na poziomie bazy danych jako bezpośrednie wywołanie SQL. To zachowanie jest możliwe, ponieważ podstawowe źródło danych **Szczegóły** o typie **Sprzężenie** jest skonfigurowane jako wykonywane na poziomie bazy danych.

    ![Strona parametrów źródła danych GROUPBY.](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Zamknij stronę.
10. Wybierz **Anuluj**.

### <a name="execute-er-format"></a><a name="executeERformat"></a> Wykonaj format ER

1. Dostęp do Finance lub RCS w drugiej sesji przeglądarki sieci Web przy użyciu tych samych poświadczeń i firmy, co w pierwszej sesji.
2. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
3. Rozwiń konfigurację **Model do nauczenia SPRĘŻENIA źródeł danych**.
4. Wybierz konfigurację **Format do nauczenia SPRĘŻENIA źródeł danych**.
5. Wybierz opcję **Konstruktor**.
6. Wybierz **Pokaż szczegóły**.
7. Wybierz **Mapowanie**.
8. Wybierz **Rozwiń/zwiń**.

    Ten format jest przeznaczony do wypełnienia wygenerowanego pliku tekstowego nowym wierszem dla każdej wersji konfiguracji ER (sekwencja **Wersja**). Każdy wygenerowany wiersz będzie zawierał nazwę dostawcy konfiguracji, który jest właścicielem bieżącej konfiguracji, nazwę konfiguracji i wersję konfiguracji rozdzielone średnikiem. Ostatni wiersz wygenerowanego pliku będzie zawierał liczbę odnalezionych wersji konfiguracji programu ER (sekwencja **Podsumowania**).

    ![Strona Projektant formatu ER, karta Format.](./media/GER-JoinDS-FormatReview.PNG)

    Źródła danych **Dane** i **Podsumowanie** służą do wypełniania szczegółów wersji konfiguracji do wygenerowanego pliku:

    - Informacje z modelu danych **Set1** są używane po wybraniu opcji **Nie** dla źródła danych **selektora** w czasie wykonywania na stronie dialogowym użytkownika podczas uruchamiania formatu ER.
    - Informacje z modelu danych **Set2** są używane po wybraniu opcji **Tak** dla źródła danych **Selektora** w czasie wykonywania na stronie dialogowym użytkownika.

    ![Strona Projektant formatu ER, karta Mapowanie.](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Wybierz opcję **Uruchom**.
10. Na stronie okna dialogowego wybierz opcję **Nie** w polu **Użyj SPRĘŻENIA źródeł danych**.
11. Kliknij przycisk **OK**.
12. Przeglądnij wygenerowany plik.

    ![Wygenerowany plik parametrów raportu elektronicznego bez źródła danych sprzężenia.](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analizowanie śledzenia wykonania operacji na formacie ER

1. W pierwszej sesji finansów lub RCS wybierz opcję **Projektant**.
2. Wybierz **Śledzenie wydajności**.
3. W siatce **Śledzenie wydajności** wybierz najwyższy rekord na najnowszym śledzeniu wydajności dla formatu ER, który używa bieżącego składnika mapowania modelu.
4. Kliknij przycisk **OK**.

    Statystyki wykonania informują o zduplikowanych wywołaniach tabel aplikacji:

    - **ERSolutionTable** zostało wywołane tyle razy, ile jest rekordów wersji konfiguracji w tabeli **ERSolutionVersionTable**, podczas gdy liczba takich wywołań mogłaby zostać zmniejszona w czasie w celu zwiększenia wydajności.
    - **ERVendorTable** zostało wywołane dwa razy dla każdej wersji konfiguracji, która została odkryta w tabeli **ERSolutionVersionTable**, podczas gdy liczba takich wywołań mogłaby również zostać zmniejszona.

    ![Statystyki wykonania na stronie projektanta mapowania modelu ER.](./media/GER-JoinDS-Set1Run2.PNG)

5. Zamknij stronę.

### <a name="execute-er-format"></a>Wykonaj format ER

1. Przełącz się na kartę przeglądarki sieci Web przy użyciu drugiej sesji Finance lub RCS.
2. Wybierz opcję **Uruchom**.
3. Na stronie okna dialogowego wybierz opcję **Tak** w polu **Użyj SPRĘŻENIA źródeł danych**.
4. Kliknij przycisk **OK**.
5. Przeglądnij wygenerowany plik.

    ![Wygenerowany plik parametrów raportu elektronicznego ze źródłem danych sprzężenia.](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Analizowanie śledzenia wykonania operacji na formacie ER

1. W pierwszej sesji finansów lub RCS wybierz opcję **Projektant**.
2. Wybierz **Śledzenie wydajności**.
3. W siatce **Śledzenie wydajności** wybierz najwyższy rekord reprezentujący najnowsze śledzenie wydajności dla formatu ER, który używa bieżącego składnika mapowania modelu.
4. Kliknij przycisk **OK**.

    Statystyki przekazują następujące informacje:

    - Baza danych aplikacji została wywołana raz, aby można było pobrać rekordy z tabel **ERVendorTable**, **ERSolutionTable** i **ERSolutionVersionTable** w celu uzyskania dostępu do wymaganych pól.

    ![Szczegóły statystyki wydajności strony projektanta mapowania modelu ER.](./media/GER-JoinDS-Set2Run2.PNG)

    - Baza danych aplikacji została wywołana raz w celu obliczenia liczby wersji konfiguracji za pomocą sprzężeń skonfigurowanych w źródle danych **Szczegółów**.

    ![Strona projektanta mapowania modelu ER z wywołaniami bazy danych aplikacji.](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Ograniczenia

Jak widać z przykładu w tym temacie, źródło danych **SPRZĘŻENIE** można utworzyć na podstawie kilku źródeł danych, które opisują indywidualne zestawy danych rekordów, które muszą ostatecznie zostać sprzężone. Te źródła danych można skonfigurować przy użyciu wbudowanej funkcji ER [FILTER](er-functions-list-filter.md). Podczas konfigurowania źródła danych w taki sposób, aby było wywoływane poza źródłem danych **SPRZĘŻENIE**, można wykorzystać zakresy firm jako część warunku wyboru danych. Początkowa implementacja źródła danych **SPRZĘŻENIE** nie obsługuje źródeł danych tego typu. Na przykład w przypadku wywołania źródła danych opartego na funkcji [FILTER](er-functions-list-filter.md) w zakresie wykonania źródła danych **SPRZĘŻENIE**, jeśli wywołane źródło danych zawiera zakresy firm w ramach warunku wyboru danych, wystąpi wyjątek.

W aplikacji Microsoft Dynamics 365 Finance w wersji 10.0.12 (sierpień 2020 r.) można stosować zakresy firm jako część warunku wyboru danych w źródłach danych opartych na funkcji [FILTER](er-functions-list-filter.md), które są wywoływane w zakresie wykonania źródła danych **SPRZĘŻENIE**. Z powodu ograniczeń konstruktora [zapytań](../dev-ref/xpp-library-objects.md#query-object-model) aplikacji zakresy firm są obsługiwane tylko dla pierwszego źródła danych dla źródła danych **SPRZĘŻENIE**.

### <a name="example"></a>Przykład

Na przykład musisz wykonać jedno wywołanie bazy danych aplikacji, aby uzyskać listę transakcji handlu zagranicznego dla wielu firm oraz szczegóły dotyczące pozycji magazynowej przywoływanej w tych transakcjach.

W takim przypadku należy skonfigurować następujące artefakty w mapowaniu modelu ER:

- Główne źródło danych **Intrastat** reprezentujące tabelę **Intrastat**.
- Główne źródło danych **Pozycje** reprezentujące tabelę **InventTable**.
- Główne źródło danych **Firmy**, które zwraca listę firm ( **DEMF** i **GBSI** w tym przykładzie) z dostępnymi transakcjami. Kod firmy jest dostępny w polu **Companies.Code**.
- Główne źródło danych **X1**, które zawiera wyrażenie `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))`. W ramach warunku wyboru danych to wyrażenie zawiera definicję zakresu firm `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- Źródło danych **X2** jako zagnieżdżona pozycja źródła danych **X1**. Zawiera ono wyrażenie `FILTER (Items, Items.ItemId = X1.ItemId)`.

Na koniec również skonfigurować źródło danych **SPRZĘŻENIE**, gdzie **x1** to pierwsze źródło danych, a **X2** to drugie źródło danych. Można wybrać opcję **Zapytanie** jako opcję **Wykonaj**, aby wymusić uruchomienie tego źródła danych w module ER na poziomie bazy danych w postaci bezpośredniego wywołania SQL.

Gdy skonfigurowane źródło danych zostanie uruchomione podczas [kontrolowania](trace-execution-er-troubleshoot-perf.md) wykonania ER, w projektancie mapowania modelu ER poniższa instrukcja jest przedstawiana jako część śladu wydajności ER.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Błąd występuje, jeśli uruchomisz źródło danych **SPRZĘŻENIE** skonfigurowane w taki sposób, aby zawierało warunki wyboru danych z zakresami firm dla dodatkowych źródeł danych dla wykonywanego źródła danych **SPRZĘŻENIE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
