---
title: Aby pobrać dane z wielu tabel aplikacji, należy zastosować SPRĘŻENIE źródeł danych w mapowaniach modeli ER
description: W tym temacie wyjaśniono, jak można używać SPRĘŻENIA źródeł danych wielu firm w Raportowaniu elektronicznym (ER).
author: NickSelin
manager: AnnBe
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: 224acc19ee5dda430cd9471aa50e9d870a4f8c60
ms.sourcegitcommit: 564aa8eec89defdbe2abaf38d0ebc4cca3e28109
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2019
ms.locfileid: "2667961"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Aby pobrać dane z wielu tabel aplikacji, należy zastosować SPRĘŻENIE źródeł danych w mapowaniach modeli Raportowania elektronicznego (ER)

[!include[banner](../includes/banner.md)]

Konfigurując mapowania lub formaty modeli raportowania elektronicznego (ER), można [dodać](#review) wymagane źródła danych typu **sprzężenia**. W czasie projektowania źródło danych **sprzężenia** jest konfigurowane jako zbiór kilku źródeł danych, z których każdy zwraca listę rekordów. Dla każdego źródła danych z wyjątkiem pierwszego należy zdefiniować niezbędne warunki, aby dołączyć rekordy bieżącego i poprzedniego źródła danych. W czasie wykonywania, skonfigurowane źródło danych typu **sprężenia** [zwraca](#executeERformat) pojedynczą połączoną listę rekordów zawierającą pola z rekordów zagnieżdżonych źródeł danych.

Obecnie obsługiwane są następujące typy sprężeń:

- Sprzężenie zewnętrzne (lewe):
    - Dołącz wszystkie rekordy w pierwszym (najbardziej do lewej) źródle danych, a następnie wszelkie uzgodnienia zgodnie z skonfigurowanymi rekordami warunków drugiego (najbardziej do prawej) źródła danych.
- Sprzężenie zewnętrzne (prawe):
    - Dołącz tylko rekordy w pierwszym (najbardziej do lewej) źródle danych, a następnie wszelkie uzgodnienia zgodnie z skonfigurowanymi rekordami warunków tylko drugiego (najbardziej do prawej) źródła danych.

W skonfigurowanym źródle danych **sprężenia**, gdy wszystkie źródła danych są typu **Rekordy tabeli**, wykonanie źródła danych sprzężenia można [wykonać na poziomie bazy danych](#analyze) przy użyciu pojedynczej instrukcji SQL. Zmniejsza to liczbę wywołań bazy danych, zwiększając wydajność mapowania modeli. W przeciwnym razie wykonanie źródła **Danych sprzężenia** jest wykonywane w pamięci.

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

Z wyprzedzeniem należy również pobrać z [Centrum pobierania Microsoft](https://go.microsoft.com/fwlink/?linkid=000000) i zapisać lokalnie następujące przykładowe pliki konfiguracji ER:

| **Opis zawartości**  | **Nazwa pliku**   |
|--------------------------|-----------------|
| Przykładowy plik konfiguracji **modelu danych ER**, który jest używany jako źródło danych przykładów.| [Model do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Przykładowy plik konfiguracji **modelu mapowania ER**, który wprowadza model danych ER dla przykładów. | [Mapowanie do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Przykładowa konfiguracja pliku **formatu ER**. Ten plik opisuje dane, które zapełnią składnik formatu ER dla przykładów. | [Format do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml.](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="activate-a-configurations-provider"></a>Aktywuj dostawcę konfiguracji

1. W pierwszej sesji przeglądarki sieci Web należy uzyskać dostęp do Finance lub RCS.
2. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.
3. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** sprawdź, czy dostawca konfiguracji dla przykładowej firmy Litware, Inc. (http://www.litware.com) jest wymieniony na liście i czy jest oznaczony jako **Aktywny**. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki w procedurze [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Obszar roboczy raportowania elektronicznego](./media/GER-JoinDS-ActiveProvider.PNG)

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
4.  Importuj plik konfiguracji formatu ER.
    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Wybierz przycisk **Przeglądaj**, aby znaleźć plik **Format do nauczenia SPRĘŻENIA źródeł danych.version.1.1.xml**.
    4. Kliknij przycisk **OK**.
5.  W drzewie konfiguracji rozwiń **Model do nauczenia SPRĘŻENIA źródeł danych**, a także inne elementy modelu (jeśli są dostępne).
6.  Zaobserwuj listę konfiguracji modelu ER w drzewie, jak również szczegóły wersji na karcie skróconej **Wersje** — będą one używane jako źródło danych dla przykładowego raportu.

    ![Strona konfiguracji raportowania elektronicznego](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Włącz opcje śledzenia wykonania
1.  Wybierz **KONFIGURACJE**.
2.  Wybierz **Parametry użytkownika**.
3.  Określ parametry śledzenia wykonania, tak jak pokazano na poniższym zrzucie ekranu.

    ![Strona parametrów użytkownika raportowania elektronicznego](./media/GER-JoinDS-Parameters.PNG)

    Jeśli te parametry są włączone, dla każdego wykonania importowanego pliku formatu ER zostanie wygenerowana funkcja śledzenia wykonania. Korzystając ze szczegółowych informacji o generowanym śledzeniu wykonania, można analizować wykonywanie formatów ER i składników mapowania modelu ER. Aby dowiedziec się więcej na temat funkcji śledzenia wykonywania ER, odwiedź stronę [Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md).

### <a name="review-er-model-mapping-part-1"></a>Przegląd mapowania modelu ER (część 1)

Przejrzyj ustawienia składnika mapowania modelu ER. Składnik jest skonfigurowany pod kątem dostępu do informacji na temat wersji konfiguracji systemu ER, szczegółów konfiguracji i dostawców konfiguracji bez użycia źródeł danych typu **Sprzężenia**.

1.  Wybierz konfigurację **Mapowanie do nauczenia SPRĘŻENIA źródeł danych**.
2.  Wybierz opcję **Projektant**, aby otworzyć listę mapowań.
3.  Wybierz opcję **Projektant**, aby przejrzeć szczegóły mapowania. 
4.  Wybierz **Pokaż szczegóły**.
5.  W drzewie konfiguracje rozwiń pozycję elementy modelu danych **Set1** i **Set1.Details**:

    1. Powiązanie **Szczegóły powiązania: Lista rekordów = wersje** wskazuje, że pozycja **Set1.Details** jest związana z **Wersjami** źródła danych zwracającymi rekordy tabeli **ERSolutionVersionTable**. Każdy rekord tej tabeli reprezentuje jedną wersję konfiguracji ER. Zawartość tej tabeli jest prezentowana na karcie skróconej **Wersje** na stronie **Konfiguracje**.
    2. Powiązanie **ConfigurationVersion: String = @.PublicVersionNumber** oznacza, że wartość publicznej wersji każdej konfiguracji jest pobierana z pola **PublicVersionNumber** tabeli **ERSolutionVersionTable** i umieszczana na elemencie **ConfigurationVersion**.
    3. Powiązanie **ConfigurationTitle: String = @.'>Relations'.Solution.Name** wskazuje, że nazwa konfiguracji ER odnoszącej się do obiektu jest pobierana z pola **Nazwa** tabeli **ERSolutionTable** oceniając przy użyciu relacji wiele-do-jednego (**'>Relacje'**) między tabelami **ERSolutionVersionTable** i **ERSolutionTable**. Nazwy konfiguracji ER dla bieżącego wystąpienia aplikacji są wyświetlane w drzewie konfiguracje na stronie **Konfiguracje**.
    4. Powiązanie **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** oznacza, że nazwa dostawcy konfiguracji, który posiada obecną konfigurację jest pobierana z pola **Nazwa** tabeli **ERVendorTable** oceniając przy użyciu relacji wiele-do-jednegomiędzy tabelami **ERSolutionTable** i **ERVendorTable**. Nazwy dostawców konfiguracji ER dla bieżącego wystąpienia aplikacji są wyświetlane w drzewie konfiguracje na stronie **Konfiguracje** na nagłówku dla każdej konfiguracji osobno. Całą listę dostawców konfiguracji modelu encja-relacja można znaleźć na stronie **Administrowanie organizacją \> Raportowanie elektroniczne \> Dostawca konfiguracji**.

    ![Strona projektanta mapowania modelu ER](./media/GER-JoinDS-Set1Review.PNG)

6.  W drzewie konfiguracje rozwiń pozycję modelu danych **Set1.Summary**:

    1. Powiązanie **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** wskazuje, że element **Set1.Summary.VersionsNumber** jest powiązany z polem agregacji **VersionsNumber** w polu **VersionsSummary** źródło danych typu **GroupBy**, które zostało skonfigurowane do zwracania liczby rekordów tabeli **ERSolutionVersionTable** za pośrednictwem **Wersji** źródła danych.

    ![Strona parametrów źródła danych GROUPBY](./media/GER-JoinDS-Set1GroupByReview.PNG)

7.  Zamknij stronę.

### <a name="review"></a> Przegląd mapowania modelu ER (część 2)

Przejrzyj ustawienia składnika mapowania modelu ER. Składnik jest skonfigurowany pod kątem dostępu do informacji na temat wersji konfiguracji systemu ER, szczegółów konfiguracji i dostawców konfiguracji z użyciem źródeł danych typu **Sprzężenia**.

1.  W drzewie konfiguracje rozwiń pozycję elementy modelu danych **Set2** i **Set2.Details**: Należy zauważyć, że powiązanie **Details: Record list = Details** wskazuje, że **Set2.Details** jest powiązany ze źródłem danych **Szczegółów** skonfigurowanym jako źródło danych typu **Sprzężenia**.

    ![Strona projektanta mapowania modelu ER](./media/GER-JoinDS-Set2Review.PNG)

    Źródło danych **sprzężenia** można dodać, wybierając **Functions\Join** źródło danych:

    ![Strona projektanta mapowania modelu ER](./media/GER-JoinDS-AddJoinDS.PNG)

2.  Wybierz źródło danych **szczegółów**.
3.  Wybierz opcję **Edytuj** w okienku **Źródła danych**.
4.  Wybierz opcję **Edycja sprężenia**.
5.  Wybierz **Pokaż szczegóły**.

    ![Strona parametrów źródła danych SPRĘŻENIA](./media/GER-JoinDS-JoinDSEditor.PNG)

    Ta strona służy do projektowania wymaganego źródła danych **typu sprzężenia**. W czasie wykonywania to źródło danych utworzy jedną przyłączoną listę rekordów ze źródeł danych w siatce **Połączonej listy**. Dołączenie rekordów zostanie rozpoczęte ze źródła danych **ConfigurationProviders**, które znajduje się w siatce jako pierwsza (dla niego jest pusta kolumna **Typ**). Rekordy z każdego innego źródła danych będą przyłączane w związku z rekordami nadrzędnego źródła danych na podstawie jego zamówienia w tej siatce. Każde dołączenie źródła danych musi być skonfigurowane jako źródło danych zagnieżdżone w docelowym źródle danych (**1Versions** źródło danych jest zagnieżdżone w **1Configurations**; źródło danych **1Configurations** jest zagnieżdżone w **ConfigurationProviders**). Każde skonfigurowane źródło danych musi zawierać warunki dla sprzężenia. W źródle danych dla tego konkretnego **Sprzężenia**zdefiniowano następujące sprzężenia:

    - Każdy rekord źródła danych **ConfigurationProviders** (odwołujący się do tabeli **ERVendorTable**) jest połączony tylko z rekordami **1Configurations** (określonymi w tabeli **ERSolutionTable**) o tej samej wartości w polach **SolutionVendor** i **RecId**. Typ **Sprzężenia wewnętrznego** jest używany dla tego sprzężenia, a także następujące warunki dotyczące dopasowywania rekordów: 

    FILTROWANIE (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Każdy rekord źródła danych **1Configurations** (odwołujący się do tabeli **ERSolutionTable**) jest połączony tylko z rekordami **1Versions** (określonymi w tabeli **ERSolutionVersionTable**) o tej samej wartości w polach **Solution** i **RecId**. Typ **Sprzężenia wewnętrznego** jest używany dla tego sprzężenia, a także następujące warunki dotyczące dopasowywania rekordów:

    FILTROWANIE (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - Opcja **Wykonaj** jest skonfigurowana jako **Kwerenda**, co oznacza, że to źródło danych sprzężenia zostanie wykonane w czasie wykonywania na poziomie bazy danych jako bezpośrednie wywołanie SQL.

    Należy zwrócić uwagę, że w przypadku dołączania rekordów źródeł danych reprezentujących tabele aplikacji można określać warunki sprzężenia za pomocą par pól innych niż te, które opisują istniejące relacje drzewa obiektów aplikacji (AOT) między tymi tabelami. Ten typ sprzężenia można skonfigurować do wykonywania również na poziomie bazy danych.

6.  Zamknij stronę.
7.  Wybierz **Anuluj**.
8.  W drzewie konfiguracje rozwiń pozycję modelu danych **Set2.Summary**:

    - Powiązanie **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** wskazuje, że element **Set2.Summary.VersionsNumber** jest powiązany z polem agregacji **VersionsNumber** w polu **DetailsSummary** źródło danych typu **GroupBy**, które zostało skonfigurowane do zwracania liczby połączonych rekordów źródła danych **Szczegóły** typu **Sprężenia**.
    - Warto zauważyć, że lokalizacja opcji **Wykonaj** jest skonfigurowana jako **Kwerenda**, co oznacza, że to źródło danych **GroupBy** zostanie wykonane w czasie wykonywania na poziomie bazy danych jako bezpośrednie wywołanie SQL. Jest to możliwe, ponieważ **Szczegóły** podstawowego źródła danych typu **Sprzężenia** są skonfigurowane jako wykonywane na poziomie bazy danych.

    ![Strona parametrów źródła danych GROUPBY](./media/GER-JoinDS-Set2GroupByReview.PNG)

9.  Zamknij stronę.
10. Wybierz **Anuluj**.

### <a name="executeERformat"></a> Wykonaj format ER

1.  Dostęp do Finance lub RCS w drugiej sesji przeglądarki sieci Web przy użyciu tych samych poświadczeń i firmy, co w pierwszej sesji.
2.  Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
3.  Rozwiń konfigurację **Model do nauczenia SPRĘŻENIA źródeł danych**.
4.  Wybierz konfigurację **Format do nauczenia SPRĘŻENIA źródeł danych**.
5.  Wybierz opcję **Konstruktor**.
6.  Wybierz **Pokaż szczegóły**.
7.  Wybierz **Mapowanie**.
8.  Wybierz **Rozwiń/zwiń**.

    Należy zauważyć, że ten format jest przeznaczony do wypełnienia wygenerowanego pliku tekstowego nowym wierszem dla każdej wersji konfiguracji ER (sekwencja **Wersji**). Każdy wygenerowany wiersz będzie zawierał nazwę dostawcy konfiguracji, który jest właścicielem bieżącej konfiguracji, nazwę konfiguracji i wersję konfiguracji rozdzielone średnikiem. Ostatni wiersz wygenerowanego pliku będzie zawierał liczbę odnalezionych wersji konfiguracji programu ER (sekwencja **Podsumowania**).

    ![Strona projektanta formatu ER](./media/GER-JoinDS-FormatReview.PNG)

    Źródła danych **Dane** i **Podsumowanie** służą do wypełniania szczegółów wersji konfiguracji do wygenerowanego pliku:

    - Informacje z modelu danych **Set1** są używane po wybraniu opcji **Nie** dla źródła danych **selektora** w czasie wykonywania na stronie dialogowym użytkownika podczas uruchamiania formatu ER.
    - Informacje z modelu danych **Set2** są używane po wybraniu opcji **Tak** dla źródła danych **Selektora** w czasie wykonywania na stronie dialogowym użytkownika.

    ![Strona projektanta formatu ER](./media/GER-JoinDS-FormatMappingReview.PNG)

9.  Wybierz opcję**Uruchom**.
10. Na stronie okna dialogowego wybierz opcję **Nie** w polu **Użyj SPRĘŻENIA źródeł danych**.
11. Kliknij przycisk **OK**.
12. Przeglądnij wygenerowany plik.

    ![Strona okna dialogowego użytkownika ER](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analizowanie śledzenia wykonania operacji na formacie ER

1.  W pierwszej sesji finansów lub RCS wybierz opcję **Projektant**.
2.  Wybierz **Śledzenie wydajności**.
3.  W siatce **Śledzenie wydajności** wybierz najwyższy rekord na najnowszym śledzeniu wydajności dla formatu ER, który używa bieżącego składnika mapowania modelu.
4.  Kliknij przycisk **OK**.

    Należy zauważyć, że statystyki wykonania powołują się na zduplikowane wywołania tabel aplikacji:

    - **ERSolutionTable** zostało wywołane tyle razy, ile jest rekordów wersji konfiguracji w tabeli **ERSolutionVersionTable**, podczas gdy liczba takich wywołań mogłaby zostać zmniejszona w czasie w celu zwiększenia wydajności.
    - **ERVendorTable** zostało wywołane dwa razy dla każdej wersji konfiguracji, która została odkryta w tabeli **ERSolutionVersionTable**, podczas gdy liczba takich wywołań mogłaby również zostać zmniejszona.

    ![Strona projektanta mapowania modelu ER](./media/GER-JoinDS-Set1Run2.PNG)

5.  Zamknij stronę.

### <a name="execute-er-format"></a>Wykonaj format ER

1.  Przełącz się na kartę przeglądarki sieci Web przy użyciu drugiej sesji Finance lub RCS.
2.  Wybierz opcję**Uruchom**.
3.  Na stronie okna dialogowego wybierz opcję **Tak** w polu **Użyj SPRĘŻENIA źródeł danych**.
4.  Kliknij przycisk **OK**.
5.  Przeglądnij wygenerowany plik.

    ![Strona okna dialogowego użytkownika ER](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze"></a> Analizowanie śledzenia wykonania operacji na formacie ER

1.  W pierwszej sesji finansów lub RCS wybierz opcję **Projektant**.
2.  Wybierz **Śledzenie wydajności**.
3.  W siatce **Śledzenie wydajności** wybierz najwyższy rekord reprezentujący najnowsze śledzenie wydajności dla formatu ER, który używa bieżącego składnika mapowania modelu.
4.  Kliknij przycisk **OK**.

    Należy zauważyć, że statystyki wykonania podano poniżej:

    - Baza danych aplikacji została wywołana raz, aby można było pobrać rekordy z tabel **ERVendorTable**, **ERSolutionTable** i **ERSolutionVersionTable** w celu uzyskania dostępu do wymaganych pól.

    ![Strona projektanta mapowania modelu ER](./media/GER-JoinDS-Set2Run2.PNG)

    - Baza danych aplikacji została wywołana raz w celu obliczenia liczby wersji konfiguracji za pomocą sprzężeń skonfigurowanych w źródle danych **Szczegółów**.

    ![Strona projektanta mapowania modelu ER](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)

