---
title: Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością
description: Ten temat zawiera informacje dotyczące korzystania z funkcji śledzenia wydajności w module Raportowanie elektroniczne (ER) w celu rozwiązywania problemów z wydajnością.
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 23b965bb51a4323164ae52bf70050133c9c9c9da
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344889"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Śledzenie wykonywania formatów ER w celu rozwiązywania problemów z wydajnością

[!include[banner](../includes/banner.md)]

W ramach procesu projektowania konfiguracji raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych należy zdefiniować metodę, która jest używana do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych. Funkcja śledzenia wydajności systemu ER pozwala znacznie zmniejszyć koszty i czas, jakie pochłania zbieranie szczegółów dotyczących wykonywania formatów ER i używanie ich do rozwiązywania problemów z wydajnością. Ten samouczek zawiera wskazówki dotyczące zbierania śladów wydajności wykonywanych formatów ER w module oraz sposobu używania informacji z tych śladów w celu zwiększania wydajności.

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym samouczku, musisz mieć następujące uprawnienia dostępu:

- Dostęp do jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia Regulatory Configuration Service (RCS), które zostało zainicjowane dla tej samej dzierżawy co aplikacja, dla jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

Musisz również pobrać i lokalnie zapisać następujące pliki.

| Plik                                  | Zawartość                               |
|---------------------------------------|---------------------------------------|
| Model śledzenia wydajności, wersja 1     | [Przykładowa konfiguracja modelu danych ER](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| Metadane śledzenia wydajności, wersja 1  | [Przykładowa konfiguracja metadanych ER](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| Mapowanie śledzenia wydajności, wersja 1.1 | [Przykładowa konfiguracja mapowania modelu ER](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| Format śladu wydajności, wersja 1.1  | [Przykładowa konfiguracja formatu ER](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER

Każdy ślad wydajności modułu ER generowany w aplikacji jest przechowywany jako załącznik do rekordu dziennika wykonania. Do zarządzania tymi załącznikami służy struktura zarządzania dokumentami (DM). Parametry ER należy skonfigurować z wyprzedzeniem, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności. W obszarze roboczym **Raportowanie elektroniczne** wybierz łącze **Parametry raportowania elektronicznego**. Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.

![Strona parametrów raportowania elektronicznego.](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):

- **Klasa:** Dołącz plik
- **Grupa:** Plik

![Strona Typy dokumentów.](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> Wybrany typ dokumentu musi być dostępny we wszystkich firmach bieżącego wystąpienia, ponieważ załączniki DM są specyficzne dla firmy.

### <a name="configure-rcs-parameters"></a>Konfigurowanie parametrów RCS

Ślady wydajności ER generowane zostaną zaimportowane do RCS w celu analizy za pomocą projektanta formatu ER i projektanta mapowania ER. Ponieważ dane śledzenia wydajności ER są przechowywane jako załączniki rekordu dziennika wykonania powiązanego z formatem ER, należy z wyprzedzeniem skonfigurować parametry RCS, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności. W wystąpieniu RCS, które zostało zainicjowane dla danej firmy, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**. Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.

![Strona parametrów raportowania elektronicznego w RCS.](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):

- **Klasa:** Dołącz plik
- **Grupa:** Plik

## <a name="design-an-er-solution"></a>Projektowanie rozwiązania ER

Załóżmy, że rozpoczęto projektowanie nowego rozwiązania ER w celu wygenerowania nowego raportu, który przedstawia transakcje dostawcy. Dotychczas transakcje wybranego dostawcy można było znaleźć na stronie **Transakcje dostawcy** (przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**, wybierz dostawcę, a następnie, w okienku akcji, na karcie **Dostawca**, w grupie **Transakcje** wybierz opcję **Transakcje**). Chcesz jednak mieć wszystkie transakcje dostawcy równocześnie w jednym dokumencie elektronicznym w formacie XML. To rozwiązanie będzie składać się z kilku konfiguracji ER, które zawierają wymagany model danych, metadane, mapowanie modeli i składniki formatu.

1. Zaloguj się do wystąpienia RCS, które zostało zainicjowane dla danej firmy.
2. W tym samouczku utworzysz i zmodyfikujesz konfiguracje dla przykładowej firmy **Litware, Inc.** Upewnij się zatem, że ten dostawca konfiguracji jest dodany do RCS i wybrany jako aktywny. Szczegółowe instrukcje znajdują się w procedurze [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
4. Na stronie **Konfiguracje** zaimportuj konfiguracje ER, które zostały pobrane jako wstępnie wymagane do RCS, w następującej kolejności: model danych, metadane, mapowanie modelu, format. Dla każdej konfiguracji wykonaj następujące czynności:

    1. W okienku akcji wybierz opcję **Wymiana \> Załaduj z pliku XML**.
    2. Kliknij przycisk **Przeglądaj**, aby wybrać odpowiedni plik wymaganej konfiguracji ER w formacie XML.
    3. Kliknij przycisk **OK**.

    ![Strona Konfiguracje w RCS.](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Uruchom rozwiązanie ER, aby śledzić wykonywanie

Załóżmy, że zakończono projektowanie pierwszej wersji rozwiązania ER. Chcesz teraz przetestować je w swoim wystąpieniu oraz przeanalizować wydajność wykonywania.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>Importowanie konfiguracji ER z RCS do Finance and Operations

1. Zaloguj się do swojego wystąpienia aplikacji.
2. W tym samouczku zaimportujesz konfiguracje z wystąpienia RCS (w którym projektujesz składniki ER) do swojego wystąpienia (w którym je testujesz i ostatecznie ich używasz). Upewnij się zatem, że zostały przygotowane wszystkie wymagane artefakty. Szczegółowe instrukcje zawiera procedura [Importowanie konfiguracji raportowania elektronicznego (RE) z usługi Regulatory Configuration Services (RCS)](rcs-download-configurations.md).
3. Aby zaimportować konfiguracje z RCS do aplikacji, należy wykonać następujące czynności:

    1. W obszarze roboczym **Raportowanie elektroniczne** na kafelku dostawcy konfiguracji **Litware, Inc.** wybierz opcję **Repozytoria**.
    2. Na stronie **Repozytorium konfiguracji** zaznacz repozytorium typu **RCS**, a następnie kliknij przycisk **Otwórz**.
    3. Na skróconej karcie **Konfiguracje** wybierz konfigurację **Format śladu wydajności**.
    4. Na skróconej karcie **Wersje** wybierz wersję **1.1** wybranej konfiguracji, a następnie kliknij przycisk **Importuj**.

    ![Strona Repozytorium konfiguracji.](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Odpowiednie wersje konfiguracji modelu danych i mapowania modelu są automatycznie importowane jako wymagania wstępne dla importowanej konfiguracji formatu ER.

### <a name="turn-on-the-er-performance-trace"></a>Włączanie śledzenia wydajności ER

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** wykonaj następujące czynności:

    1. W polu **Format śladu wykonania** możesz określić format generowanego śladu wydajności, w którym są przechowywane szczegóły dotyczące wykonania, w odniesieniu do formatu ER i elementów mapowania:

        - **Format śladu debugowania** – wybierz tę wartość, jeśli planujesz interaktywnie uruchomić format ER, który ma krótki czas wykonania. Następnie rozpoczyna się zbieranie szczegółów dotyczących wykonania formatu ER. Po wybraniu tej wartości ślad wydajności będzie zbierać informacje o czasie poświęcanym na następujące akcje:

            - Uruchamianie poszczególnych źródeł danych w mapowaniu modelu, które są wywoływane w celu uzyskania danych
            - Przetwarzanie poszczególnych elementów formatu w celu wprowadzenia danych w generowanych danych wyjściowych

            W przypadku wybrania wartości **Format śladu debugowania** można analizować zawartość śladu w konstruktorze operacji ER. Tam można zobaczyć format ER lub elementy mapowania, które są wymienione w śladzie.

        - **Zagregowany format śledzenia** – wybierz tę wartość, jeśli planujesz uruchomić format ER, który ma długi czas wykonania w trybie wsadowym. Następnie rozpoczyna się zbieranie zagregowanych szczegółów dotyczących wykonania formatu ER. Po wybraniu tej wartości ślad wydajności będzie zbierać informacje o czasie poświęcanym na następujące akcje:

            - Uruchamianie poszczególnych źródeł danych w mapowaniu modelu, które są wywoływane w celu uzyskania danych
            - Uruchamianie poszczególnych źródeł danych w mapowaniu formatu, które są wywoływane w celu uzyskania danych
            - Przetwarzanie poszczególnych elementów formatu w celu wprowadzenia danych w generowanych danych wyjściowych

            Wartość **Format śladu zagregowanego** jest dostępna w Microsoft Dynamics 365 Finance w wersji 10.0.20 i nowszych.

            W projektancie formatu ER i projektancie odwzorowania modelu ER możesz zobaczyć całkowity czas wykonania dla pojedynczego komponentu. Dodatkowo, ślad zawiera szczegóły dotyczące wykonania, takie jak liczba wykonań oraz minimalny i maksymalny czas pojedynczego wykonania.

            > [!NOTE]
            > To śledzenie jest zbierane na podstawie ścieżki śledzonych składników. Dlatego statystyki mogą być niepoprawne, gdy pojedynczy komponent nadrzędny zawiera kilka nienazwanych komponentów podrzędnych lub gdy kilka komponentów podrzędnych ma tę samą nazwę.

    2. Wybór ustawienia **Tak** następujących opcji umożliwia zbieranie szczegółów wykonania mapowania modelu ER i składników formatu ER:

        - **Zbieraj statystyki zapytań** — po włączeniu tej opcji śledzenie wydajności będzie zbierać następujące informacje:

            - Liczba wywołań bazy danych przez źródła danych
            - Liczba powielonych wywołań do bazy danych.
            - Szczegóły instrukcji SQL użytych w wywołaniach bazy danych

        - **Śledzenie dostępu funkcji buforowania** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o użyciu buforu mapowania modelu ER.
        - **Śledzenie dostępu do danych** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o liczbie wywołań do bazy danych dla wykonywanych źródeł danych typu listy rekordów.
        - **Element stałotekstowy listy śledzenia** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o liczbie rekordów, których żądają źródła danych typu listy rekordów.

    > [!NOTE]
    > Parametry w oknie dialogowym **Parametry użytkownika** są specyficzne dla użytkownika i bieżącej firmy.

    ![Okno dialogowe parametry użytkownika.](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Uruchamianie formatu ER

1. Wybierz pole firmę **DEMF**.
2. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format śledzenia wydajności**.
4. W okienku akcji wybierz opcję **Uruchom**.

Generowany plik zawiera informacje dotyczące 265 transakcji dla sześciu dostawców.

## <a name="review-the-execution-trace"></a>Przeglądanie śladu wykonania

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>Eksportowanie wygenerowanego śledzenia z aplikacji

Ślady wydajności są odłączane od źródłowego formatu ER i można je serializować w zewnętrznym pliku zip.

1. Otwórz **Administracja organizacji \> Elektroniczne raportowanie \> Dzienniki debugowania konfiguracji**.
2. Na stronie **Dzienniki przebiegu raportowania elektronicznego** w lewym okienku w polu **Nazwa konfiguracji** wybierz opcję **Format śladu wydajności**, aby znaleźć rekordy dziennika wygenerowane przez wykonanie konfiguracji **Format śladu wydajności**.
3. Naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony lub naciśnij **Ctrl+Shift+A**.

    ![Przycisk Załączniki na stronie Dzienniki przebiegu raportowania elektronicznego.](./media/GER-PerfTrace-GER-DebugLog.png)

4. Na stronie **Załączniki do dzienników przebiegu raportowania elektronicznego** w okienku akcji kliknij przycisk **Otwórz**, aby pobrać ślad wydajności jako plik zip i zapisać go lokalnie.

    ![Załączniki do dzienników przebiegu raportowania elektronicznego.](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> Generowany ślad zawiera odwołanie do źródłowego raportu ER w postaci unikatowego identyfikatora raportu tylko w formacie **GUID**. Numerowanie wersji formatu nie jest uwzględniane.

Skojarzenie między śladem wydajności, który został wygenerowany dla wykonywanego formatu ER, a mapowaniem modelu ER jest oparte na użytym deskryptorze głównym i wspólnym modelu danych. Numerowanie wersji formatu i mapowania modelu nie jest uwzględniane. Ustawienie opcji **Domyślne mapowanie modelu** mapowania modelu również nie jest uwzględniane.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>Importowanie wygenerowanego śladu do RCS

1. W RCS w obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń pozycję **Model śladu wydajności** i wybierz opcję **Format śladu wydajności**.
3. W okienku akcji wybierz opcję **Projektant**.
4. Na stronie **Projektant formatu** w okienku akcji wybierz opcję **Ślad wydajności**.
5. W oknie dialogowym **Ustawienia wyników śledzenia wydajności** wybierz opcję **Importuj ślad wydajności**.
6. Kliknij przycisk **Przeglądaj**, a następnie zaznacz plik zip, który został wcześniej eksportowany.
7. Kliknij przycisk **OK**.

    ![Okno dialogowe ustawień wyników śledzenia wydajności w RCS.](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Użycie śledzenia wydajności do analizy w RCS — wykonanie formatu

1. W RCS na stronie **Projektant formatu** kliknij przycisk **Rozwiń/Zwiń**, aby rozwinąć zawartość wszystkich elementów formatu.

    Zostaną wyświetlone dodatkowe informacje dotyczące niektórych pozycji bieżącego formatu:

    - Rzeczywisty czas spędzony na wprowadzaniu danych w wygenerowanych danych wyjściowych przy użyciu elementu formatu
    - Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wygenerowanie wszystkich danych wyjściowych

    ![Strona projektanta formatu w RCS.](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Zamknij stronę **Projektant formatu**.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu

1. W RCS na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie śledzenia wydajności**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Wybierz opcję **Konstruktor**.
4. Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.
5. Wybierz ślad, który zaimportowano wcześniej.
6. Kliknij przycisk **OK**.

Zostaną udostępnione nowe informacje dotyczące niektórych pozycji źródła danych bieżącego mapowania modelu:

- Rzeczywisty czas poświęcony na uzyskiwanie danych przy użyciu źródła danych
- Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wykonywanie całego mapowania modelu

Podczas uruchamiania źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum ER poinformuje, że bieżące mapowanie modelu duplikuje żądania bazy danych. To duplikowanie wynika z tego, że lista transakcji dostawcy jest wywoływana dwukrotnie dla każdego rekordu dostawcy przetwarzanego w ramach iteracji:

- Jedno wywołanie jest wykonywane w celu wprowadzenia szczegółów poszczególnych transakcji do modelu danych na podstawie skonfigurowanych powiązań.
- Jedno wywołanie jest wykonywane w celu wprowadzenia obliczonej liczby transakcji danego dostawcy do modelu danych.

![Komunikat dotyczący zduplikowanych żądań bazy danych na stronie projektanta mapowania modelu w RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

Wartość **\[Q:530\]** wskazuje, że tabela VendTrans została wywołana 530 razy, aby zwrócić rekord z tej tabeli do źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum. Wartość **\[530\]** wskazuje, że źródło danych VendTable\</Relations/VendTrans.VendTable\_AccountNum zostało wywołane 530 razy, aby zwrócić rekord z tego źródła danych i wprowadzić jego szczegóły do modelu danych.

Zaleca się buforowanie źródła danychVendTable/\<Relations/VendTrans.VendTable\_AccountNum w celu zmniejszenia liczby wywołań wykonywanych w celu uzyskania szczegółów dotyczących 265 transakcji i zwiększenia wydajności mapowania modelu.

Przydatne może być także zmniejszenie liczby wywołań źródła danych LedgerTransTypeList. To źródło danych służy do kojarzenia poszczególnych wartości wyliczenia **LedgerTransType** z etykietą. Korzystając z tego źródła danych, można znaleźć odpowiednią etykietę i wprowadzić ją do modelu danych dla poszczególnych transakcji dostawcy. Bieżąca liczba wywołań tego źródła danych (9027) jest dość duża jak na 265 transakcji.

![Strona projektanta mapowania modelu w RCS pokazująca 9027 wywołań źródła danych.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Poprawianie mapowania modelu na podstawie informacji ze śladu wykonywania

### <a name="modify-the-logic-of-the-model-mapping"></a>Modyfikowanie mapowania modelu

1. Aby zapobiec duplikowaniu wywołań bazy danych, należy użyć buforowania w następujący sposób:

    1. W RCS na stronie **Projektant mapowania modelu** w okienku **Źródła danych** wybierz pozycję **VendTable**.
    2. Wybierz opcję **Pamięć podręczna**.
    3. Rozwiń pozycję **VendTable**, rozwiń listę relacji jeden-do-wielu źródła danych VendTable (pozycja **\<Relacje**) i wybierz opcję **VendTrans.VendTable\_AccountNum**.
    4. Wybierz opcję **Pamięć podręczna**.

    ![Włączanie buforowania w celu zapobiegania duplikowaniu wywołań.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Aby sprowadzić źródło danych LedgerTransTypeList do zakresu źródła danych VendTable, należy wykonać następujące czynności:

    1. W okienku **Typy źródła danych** rozwiń pozycję **Funkcje** i wybierz pozycję **Pole obliczeniowe**.
    2. W okienku **Źródła danych** wybierz pozycję **VendTable**.
    3. Wybierz opcję **Dodaj**.
    4. W polu **Nazwa** wprowadź nazwę **\$TransType**.
    5. Wybierz opcję **Edytuj formułę**.
    6. W polu **Formuła** wpisz tekst **LedgerTransTypeList**.
    7. Wybierz opcję **Zapisz**.
    8. Zamknij stronę **Edytor formuł**.
    9. Kliknij przycisk **OK**.

3. Wykonaj następujące kroki w celu buforowania pola **\$TransType**:

    1. Wybierz pozycję **LedgerTransTypeList**.
    2. Wybierz opcję **Pamięć podręczna**.
    3. Wybierz pozycję **VendTable.\$TransType**.
    4. Wybierz opcję **Pamięć podręczna**.

    ![Włączanie buforowania pola $TransType.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Aby pole **\$TransTypeRecord** zaczęło korzystać z buforowanego pola **\$TransType**, wykonaj następujące kroki:

    1. W okienku **Źródła danych** rozwiń pozycję **VendTable**, rozwiń pozycję **\<Relacje**, rozwiń pozycję **VendTrans.VendTable\_AccountNum** i wybierz pozycję **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.
    2. Wybierz opcję **Edycja**.
    3. Wybierz opcję **Edytuj formułę**.
    4. W polu **Formuła** znajdź następujące wyrażenie:

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. W polu **Formuła** wprowadź następujące wyrażenie:

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. Wybierz opcję **Zapisz**.
    7. Zamknij stronę **Edytor formuł**.
    8. Kliknij przycisk **OK**.

5. Wybierz opcję **Zapisz**.
6. Zamknij stronę **Projektant mapowania modelu**.
7. Zamknij stronę **Mapowanie modelu**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Kończenie zmodyfikowanej wersji mapowania modelu ER

1. W RCS na stronie **Konfiguracje** na karcie skróconej **Wersje** wybierz wersję **1.2** konfiguracji **Mapowanie śledzenia wydajności**.
2. Wybierz opcję **Zmień stan**.
3. Wybierz opcję **Zakończone**.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>Importowanie konfiguracji mapowania modelu ER z RCS do aplikacji

Powtórz kroki opisane w sekcji [Importowanie konfiguracji ER z RCS do Finance and Operations](#import-configuration) tego tematu, aby zaimportować wersję 1.2 konfiguracji **Mapowanie śledzenia wydajności**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Uruchom zmodyfikowane rozwiązanie ER, aby śledzić wykonywanie

### <a name="run-the-er-format"></a>Uruchamianie formatu ER

Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.

## <a name="work-with-the-execution-trace"></a>Pracuj z śladem wykonania

### <a name="export-the-generated-trace-from-the-application"></a>Eksportowanie wygenerowanego śledzenia z aplikacji

Powtórz kroki opisane w sekcji [Eksportowanie wygenerowanego śladu z aplikacji](#export-trace) tego tematu, aby zapisać lokalnie nowy ślad wydajności.

### <a name="import-the-generated-trace-into-rcs"></a>Importowanie wygenerowanego śladu do RCS

Powtórz kroki opisane w sekcji [Importowanie wygenerowanego śladu do RCS](#import-trace) tego tematu, aby zaimportować nowy ślad wydajności do RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu

Powtórz kroki opisane w sekcji [Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu](#use-trace) tego tematu, aby przeanalizować najnowszy ślad wydajności.

Korekty wprowadzone w mapowaniu modelu wyeliminowały duplikowanie zapytań do bazy danych. Liczba wywołań tabel bazy danych i źródeł danych tego mapowania modelu również została zmniejszona. Wydajność całego rozwiązania ER uległa zatem poprawie.

![Informacje o śladzie źródła danych VendTable na stronie Projektant mapowania modelu w RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

Wartość **\[12\]** dla tabeli VendTable w śladzie wskazuje, że to źródło danych było wywoływane 12 razy. Wartość **\[Q:6\]** wskazuje, że sześć wywołań zostało przetłumaczonych na wywołania bazy danych do tabeli VendTable. Wartość **\[C:6\]** wskazuje, że rekordy pobrane z bazy danych były buforowane i sześć innych wywołań zostało przetworzonych przy użyciu pamięci podręcznej.

Liczba wywołań źródła danych LedgerTransTypeList została zmniejszona z z 9027 do 240.

![Informacje o śladzie źródła danych LedgerTransTypeList na stronie Projektant mapowania modelu w RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>Przejrzyj wyniki śledzenia wykonania w aplikacji

Oprócz RCS niektóre wersje mogą oferować możliwości korzystania z projektanta struktury ER. Te wersje zawierają opcję **Włącz tryb projektowania**, którą można włączyć. Ta opcja znajduje się na karcie **Ogólne** strony **Parametry raportowania elektronicznego** otwieranej z obszaru roboczego **Raportowanie elektroniczne**.

![Włącz opcję trybu projektowania na stronie parametry raportowania elektronicznego.](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

W przypadku korzystania z jednej z tych wersji modułu Finance and Operations można analizować szczegóły generowanych śladów wydajności bezpośrednio w aplikacji. Nie trzeba ich eksportować z aplikacji i importować do RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Przeglądanie śladu wykonania za pomocą narzędzi zewnętrznych

### <a name="configure-user-parameters"></a>Konfigurowanie parametrów użytkownika

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** w polu **Format śladu wykonania** wybierz opcję **PerfView XML**.

### <a name="run-the-er-format"></a>Uruchamianie formatu ER

Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.

Przeglądarka sieci Web zaproponuje pobranie pliku zip. Ten plik zawiera ślad wydajności w formacie PerfView. Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView.

![Informacje o śledzeniu wydajności w formacie PerfView.](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Narzędzia zewnętrzne umożliwiają przejrzenie śledzenie wykonywania obejmującego kwerendy bazy danych

Ze względu na udoskonalenia, które zostały wprowadzone w ramach systemu, śledzenie wydajności generowane w formacie PerfView zawiera więcej szczegółów dotyczących wykonywania operacji na formacie ER. W Microsoft Dynamics 365 for Finance and Operations wersji 10.0.4 (lipiec 2019) ten ślad może również zawierać szczegóły wykonanych kwerend SQL w bazie danych aplikacji.

### <a name="configure-user-parameters"></a>Konfigurowanie parametrów użytkownika

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** ustaw następujące parametry:

    - W polu **Format śledzenia wykonania** wybierz opcję **PerfView XML**.
    - Ustawienie opcji **Zbierz statystyki kwerendy** na wartość **Tak**.
    - Ustawienie opcji wartość **śledzenie kwerendy** na wartość **Tak**.

    ![Sekcja śledzenia wykonania, okno dialogowe Parametry użytkownika.](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Uruchamianie formatu ER

Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.

Przeglądarka sieci Web zaproponuje pobranie pliku zip. Ten plik zawiera ślad wydajności w formacie PerfView. Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView. Teraz ten ślad zawiera szczegóły dostępu do bazy danych SQL podczas wykonywania formatu ER.

![Informacje o śledzeniu dla wykonanego formatu ER w PerfView.](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
