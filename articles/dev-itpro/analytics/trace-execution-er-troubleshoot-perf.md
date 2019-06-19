---
title: Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością
description: Ten temat zawiera informacje dotyczące korzystania z funkcji śledzenia wydajności w module Raportowanie elektroniczne (ER) w celu rozwiązywania problemów z wydajnością.
author: NickSelin
manager: AnnBe
ms.date: 05/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: aa71db2752889bc905c22bab1cf2fa46d7ee07c7
ms.sourcegitcommit: 67d00b95952faf0db580d341249d4e50be59119c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1576553"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Śledzenie wykonywania formatów ER w celu rozwiązywania problemów z wydajnością

[!include[banner](../includes/banner.md)]

W ramach procesu projektowania konfiguracji raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych należy zdefiniować metodę, która jest używana do uzyskiwania danych z Microsoft Dynamics 365 for Finance and Operations i wprowadzania ich do generowanych danych wyjściowych. Funkcja śledzenia wydajności systemu ER pozwala znacznie zmniejszyć koszty i czas, jakie pochłania zbieranie szczegółów dotyczących wykonywania formatów ER i używanie ich do rozwiązywania problemów z wydajnością. Ten samouczek zawiera wskazówki dotyczące zbierania śladów wydajności wykonywanych formatów ER w module Finance and Operations oraz sposobu używania informacji z tych śladów w celu zwiększania wydajności.

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym samouczku, musisz mieć następujące uprawnienia dostępu:

- Dostęp do programu Finance and Operations w jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia Regulatory Configuration Service (RCS), które zostało zainicjowane dla tej samej dzierżawy co Finance and Operations, dla jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

Musisz również pobrać i lokalnie zapisać następujące pliki.

| Plik                                  | Zawartość                               |
|---------------------------------------|---------------------------------------|
| Model śledzenia wydajności, wersja 1     | [Przykładowa konfiguracja modelu danych ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)    |
| Metadane śledzenia wydajności, wersja 1  | [Przykładowa konfiguracja metadanych ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)      |
| Mapowanie śledzenia wydajności, wersja 1.1 | [Przykładowa konfiguracja mapowania modelu ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Format śladu wydajności, wersja 1.1  | [Przykładowa konfiguracja formatu ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)       |

### <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER

Każdy ślad wydajności modułu ER generowany w Finance and Operations jest przechowywany jako załącznik do rekordu dziennika wykonania. Do zarządzania tymi załącznikami służy struktura zarządzania dokumentami (DM) Finance and Operations. Parametry ER należy skonfigurować z wyprzedzeniem, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności. W module Finance and Operation, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**. Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.

![Strona parametrów raportowania elektronicznego w module Finance and Operations](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):

- **Klasa:** Dołącz plik
- **Grupa:** Plik

![Strona Typy dokumentów w module Finance and Operations](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> Wybrany typ dokumentu musi być dostępny we wszystkich firmach bieżącego wystąpienia Finance and Operations, ponieważ załączniki DM są specyficzne dla firmy.

### <a name="configure-rcs-parameters"></a>Konfigurowanie parametrów RCS

Ślady wydajności ER generowane w module Finance and Operations zostaną zaimportowane do RCS w celu analizy za pomocą projektanta formatu ER i projektanta mapowania ER. Ponieważ dane śledzenia wydajności ER są przechowywane jako załączniki rekordu dziennika wykonania powiązanego z formatem ER, należy z wyprzedzeniem skonfigurować parametry RCS, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności. W wystąpieniu RCS, które zostało zainicjowane dla danej firmy, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**. Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.

![Strona parametrów raportowania elektronicznego w RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):

- **Klasa:** Dołącz plik
- **Grupa:** Plik

## <a name="design-an-er-solution"></a>Projektowanie rozwiązania ER

Załóżmy, że rozpoczęto projektowanie nowego rozwiązania ER w celu wygenerowania nowego raportu, który przedstawia transakcje dostawcy. Dotychczas transakcje wybranego dostawcy można było znaleźć na stronie **Transakcje dostawcy** (przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**, wybierz dostawcę, a następnie, w okienku akcji, na karcie **Dostawca**, w grupie **Transakcje** wybierz opcję **Transakcje**). Chcesz jednak mieć wszystkie transakcje dostawcy równocześnie w jednym dokumencie elektronicznym w formacie XML. To rozwiązanie będzie składać się z kilku konfiguracji ER, które zawierają wymagany model danych, metadane, mapowanie modeli i składniki formatu.

1. Zaloguj się do wystąpienia RCS, które zostało zainicjowane dla danej firmy.
2. W tym samouczku utworzysz i zmodyfikujesz konfiguracje dla przykładowej firmy **Litware, Inc.** Upewnij się zatem, że ten dostawca konfiguracji jest dodany do RCS i wybrany jako aktywny. Szczegółowe instrukcje znajdują się w procedurze [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
4. Na stronie **Konfiguracje** zaimportuj konfiguracje ER, które zostały pobrane jako wstępnie wymagane do RCS, w następującej kolejności: model danych, metadane, mapowanie modelu, format. Dla każdej konfiguracji wykonaj następujące czynności:

    1. W okienku akcji wybierz opcję **Wymiana \> Załaduj z pliku XML**.
    2. Kliknij przycisk **Przeglądaj**, aby wybrać odpowiedni plik wymaganej konfiguracji ER w formacie XML.
    3. Kliknij przycisk **OK**.

    ![Strona Konfiguracje w RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Uruchom rozwiązanie ER, aby śledzić wykonywanie

Załóżmy, że zakończono projektowanie pierwszej wersji rozwiązania ER. Chcesz teraz przetestować je w swoim wystąpieniu Finance and Operations oraz przeanalizować wydajność wykonywania.

### <a id='import-configuration'></a>Importowanie konfiguracji ER z RCS do Finance and Operations

1. Zaloguj się w swoim wystąpieniu rozwiązania Finance and Operations.
2. W tym samouczku zaimportujesz konfiguracje z wystąpienia RCS (w którym projektujesz składniki ER) do swojego wystąpienia Finance and Operations (w którym je testujesz i ostatecznie ich używasz). Upewnij się zatem, że zostały przygotowane wszystkie wymagane artefakty. Szczegółowe instrukcje zawiera procedura [Importowanie konfiguracji raportowania elektronicznego (RE) z usługi Regulatory Configuration Services (RCS)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations).
3. Aby zaimportować konfiguracje z RCS do Finance and Operations, należy wykonać następujące czynności:

    1. W obszarze roboczym **Raportowanie elektroniczne** na kafelku dostawcy konfiguracji **Litware, Inc.** wybierz opcję **Repozytoria**.
    2. Na stronie **Repozytorium konfiguracji** zaznacz repozytorium typu **RCS**, a następnie kliknij przycisk **Otwórz**.
    3. Na skróconej karcie **Konfiguracje** wybierz konfigurację **Format śladu wydajności**.
    4. Na skróconej karcie **Wersje** wybierz wersję **1.1** wybranej konfiguracji, a następnie kliknij przycisk **Importuj**.

    ![Strona repozytorium konfiguracji w module Finance and Operations](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Odpowiednie wersje konfiguracji modelu danych i mapowania modelu są automatycznie importowane jako wymagania wstępne dla importowanej konfiguracji formatu ER.

### <a name="turn-on-the-er-performance-trace"></a>Włączanie śledzenia wydajności ER

1. W module Finance and Operations przejdź do opcji **Administrowanie organizacją \> Raportowanie elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** wykonaj następujące czynności:

    1. W polu **Format śladu wykonania** wybierz opcję **Format śladu debugowania**, aby rozpocząć zbieranie szczegółowych informacji dotyczących wykonania formatu ER. Po wybraniu tej wartości ślad wydajności będzie zbierać informacje o czasie poświęcanym na następujące akcje:

        - Uruchamianie poszczególnych źródeł danych w mapowaniu modelu, które są wywoływane w celu uzyskania danych
        - Przetwarzanie poszczególnych elementów formatu w celu wprowadzenia danych w generowanych danych wyjściowych

        W polu **Format śladu wykonania** możesz określić format generowanego śladu wydajności, w którym są przechowywane szczegóły dotyczące wykonania, w odniesieniu do formatu ER i elementów mapowania. Wybranie opcji **Format śladu debugowania** jako wartości umożliwia analizę zawartości śladu w projektancie operacji ER oraz wyświetlenie formatu lub elementów mapowania wymienionych w śladzie.

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

    ![Okno dialogowe Parametry użytkownika w module Finance and Operations](./media/GER-PerfTrace-GER-UserParameters.png)

### <a id='run-format'></a>Uruchamianie formatu ER

1. W module Finance and Operations wybierz firmę **DEMF**.
2. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format śledzenia wydajności**.
4. W okienku akcji wybierz opcję **Uruchom**.

Generowany plik zawiera informacje dotyczące 265 transakcji dla sześciu dostawców.

## <a name="review-the-execution-trace"></a>Przeglądanie śladu wykonania

### <a id='export-trace'></a>Eksportowanie wygenerowanego śladu z modułu Finance and Operations

Ślady wydajności są odłączane od źródłowego formatu ER i można je serializować w zewnętrznym pliku zip.

1. W module Finance and Operations przejdź do opcji **Administrowanie organizacją \> Raportowanie elektroniczne \> Dzienniki debugowania konfiguracji**.
2. Na stronie **Dzienniki przebiegu raportowania elektronicznego** w lewym okienku w polu **Nazwa konfiguracji** wybierz opcję **Format śladu wydajności**, aby znaleźć rekordy dziennika wygenerowane przez wykonanie konfiguracji **Format śladu wydajności**.
3. Naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony lub naciśnij **Ctrl+Shift+A**.

    ![Przycisk Załączniki na stronie Dzienniki przebiegu raportowania elektronicznego w module Finance and Operations](./media/GER-PerfTrace-GER-DebugLog.png)

4. Na stronie **Załączniki do dzienników przebiegu raportowania elektronicznego** w okienku akcji kliknij przycisk **Otwórz**, aby pobrać ślad wydajności jako plik zip i zapisać go lokalnie.

    ![Załączniki strony Dzienniki przebiegu raportowania elektronicznego w module Finance and Operations](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> Generowany ślad zawiera odwołanie do źródłowego raportu ER w postaci unikatowego identyfikatora raportu tylko w formacie **GUID**. Numerowanie wersji formatu nie jest uwzględniane.

Skojarzenie między śladem wydajności, który został wygenerowany dla wykonywanego formatu ER, a mapowaniem modelu ER jest oparte na użytym deskryptorze głównym i wspólnym modelu danych. Numerowanie wersji formatu i mapowania modelu nie jest uwzględniane. Ustawienie opcji **Domyślne mapowanie modelu** mapowania modelu również nie jest uwzględniane.

### <a id='import-trace'></a>Importowanie wygenerowanego śladu do RCS

1. W RCS w obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń pozycję **Model śladu wydajności** i wybierz opcję **Format śladu wydajności**.
3. W okienku akcji wybierz opcję **Projektant**.
4. Na stronie **Projektant formatu** w okienku akcji wybierz opcję **Ślad wydajności**.
5. W oknie dialogowym **Ustawienia wyników śledzenia wydajności** wybierz opcję **Importuj ślad wydajności**.
6. Kliknij przycisk **Przeglądaj**, aby wybrać plik zip wyeksportowany wcześniej z modułu Finance and Operations.
7. Kliknij przycisk **OK**.

    ![Okno dialogowe ustawień wyników śledzenia wydajności w RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Użycie śledzenia wydajności do analizy w RCS — wykonanie formatu

1. W RCS na stronie **Projektant formatu** kliknij przycisk **Rozwiń/Zwiń**, aby rozwinąć zawartość wszystkich elementów formatu.

    Zostaną wyświetlone dodatkowe informacje dotyczące niektórych pozycji bieżącego formatu:

    - Rzeczywisty czas spędzony na wprowadzaniu danych w wygenerowanych danych wyjściowych przy użyciu elementu formatu
    - Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wygenerowanie wszystkich danych wyjściowych

    ![Strona projektanta formatu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Zamknij stronę **Projektant formatu**.

### <a id='use-trace'></a>Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu

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

![Komunikat dotyczący zduplikowanych żądań bazy danych na stronie projektanta mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

Wartość **\[Q:530\]** wskazuje, że tabela VendTrans została wywołana 530 razy, aby zwrócić rekord z tej tabeli do źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum. Wartość **\[530\]** wskazuje, że źródło danych VendTable\</Relations/VendTrans.VendTable\_AccountNum zostało wywołane 530 razy, aby zwrócić rekord z tego źródła danych i wprowadzić jego szczegóły do modelu danych.

Zaleca się buforowanie źródła danychVendTable/\<Relations/VendTrans.VendTable\_AccountNum w celu zmniejszenia liczby wywołań wykonywanych w celu uzyskania szczegółów dotyczących 265 transakcji i zwiększenia wydajności mapowania modelu.

Przydatne może być także zmniejszenie liczby wywołań źródła danych LedgerTransTypeList. To źródło danych służy do kojarzenia poszczególnych wartości wyliczenia **LedgerTransType** z etykietą. Korzystając z tego źródła danych, można znaleźć odpowiednią etykietę i wprowadzić ją do modelu danych dla poszczególnych transakcji dostawcy. Bieżąca liczba wywołań tego źródła danych (9027) jest dość duża jak na 265 transakcji.

![Strona projektanta mapowania modelu w RCS pokazująca 9027 wywołań źródła danych](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Poprawianie mapowania modelu na podstawie informacji ze śladu wykonywania

### <a name="modify-the-logic-of-the-model-mapping"></a>Modyfikowanie mapowania modelu

1. Aby zapobiec duplikowaniu wywołań bazy danych, należy użyć buforowania w następujący sposób:

    1. W RCS na stronie **Projektant mapowania modelu** w okienku **Źródła danych** wybierz pozycję **VendTable**.
    2. Wybierz opcję **Pamięć podręczna**.
    3. Rozwiń pozycję **VendTable**, rozwiń listę relacji jeden-do-wielu źródła danych VendTable (pozycja **\<Relacje**) i wybierz opcję **VendTrans.VendTable\_AccountNum**.
    4. Wybierz opcję **Pamięć podręczna**.

    ![Włączanie buforowania w celu zapobiegania duplikowaniu wywołań](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

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

    ![Włączanie buforowania pola $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

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

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-finance-and-operations"></a>Importowanie konfiguracji mapowania modelu ER z RCS do Finance and Operations

Powtórz kroki opisane w sekcji [Importowanie konfiguracji ER z RCS do Finance and Operations](#import-configuration) tego tematu, aby zaimportować wersję 1.2 konfiguracji **Mapowanie śledzenia wydajności** do modułu Finance and Operations.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Uruchom zmodyfikowane rozwiązanie ER, aby śledzić wykonywanie

### <a name="run-the-er-format"></a>Uruchamianie formatu ER

Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.

## <a name="review-the-execution-trace"></a>Przeglądanie śladu wykonania

### <a name="export-the-generated-trace-from-finance-and-operations"></a>Eksportowanie wygenerowanego śladu z modułu Finance and Operations

Powtórz kroki opisane w sekcji [Eksportowanie wygenerowanego śladu z modułu Finance and Operations](#export-trace) tego tematu, aby zapisać lokalnie nowy ślad wydajności.

### <a name="import-the-generated-trace-into-rcs"></a>Importowanie wygenerowanego śladu do RCS

Powtórz kroki opisane w sekcji [Importowanie wygenerowanego śladu do RCS](#import-trace) tego tematu, aby zaimportować nowy ślad wydajności do RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu

Powtórz kroki opisane w sekcji [Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu](#use-trace) tego tematu, aby przeanalizować najnowszy ślad wydajności.

Korekty wprowadzone w mapowaniu modelu wyeliminowały duplikowanie zapytań do bazy danych. Liczba wywołań tabel bazy danych i źródeł danych tego mapowania modelu również została zmniejszona. Wydajność całego rozwiązania ER uległa zatem poprawie.

![Informacje o śladzie źródła danych VendTable na stronie Projektant mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

Wartość **\[12\]** dla tabeli VendTable w śladzie wskazuje, że to źródło danych było wywoływane 12 razy. Wartość **\[Q:6\]** wskazuje, że sześć wywołań zostało przetłumaczonych na wywołania bazy danych do tabeli VendTable. Wartość **\[C:6\]** wskazuje, że rekordy pobrane z bazy danych były buforowane i sześć innych wywołań zostało przetworzonych przy użyciu pamięci podręcznej.

Liczba wywołań źródła danych LedgerTransTypeList została zmniejszona z z 9027 do 240.

![Informacje o śladzie źródła danych LedgerTransTypeList na stronie Projektant mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-finance-and-operations"></a>Przeglądanie śladu wykonania w module Finance and Operations

Oprócz RCS niektóre wersje modułu Finance and Operations mogą oferować możliwości korzystania z projektanta struktury ER. Te wersje modułu Finance and Operations zawierają opcję **Włącz tryb projektowania**, którą można włączyć. Ta opcja znajduje się na karcie **Ogólne** strony **Parametry raportowania elektronicznego** otwieranej z obszaru roboczego **Raportowanie elektroniczne**.

![Włączanie opcji trybu projektowania na stronie Parametry raportowania elektronicznego w module Finance and Operations](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

W przypadku korzystania z jednej z tych wersji modułu Finance and Operations można analizować szczegóły generowanych śladów wydajności bezpośrednio w module Finance and Operations. Nie trzeba ich eksportować z modułu Finance and Operations i importować do RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Przeglądanie śladu wykonania za pomocą narzędzi zewnętrznych

### <a name="configure-user-parameters"></a>Konfigurowanie parametrów użytkownika

1. W module Finance and Operations przejdź do opcji **Administrowanie organizacją \> Raportowanie elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** w polu **Format śladu wykonania** wybierz opcję **PerfView XML**.

### <a name="run-the-er-format"></a>Uruchamianie formatu ER

Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.

Przeglądarka sieci Web zaproponuje pobranie pliku zip. Ten plik zawiera ślad wydajności w formacie PerfView. Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView.
