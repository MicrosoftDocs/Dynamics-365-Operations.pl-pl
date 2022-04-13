---
title: Grupowanie rekordów i łączenie obliczeń przy użyciu źródeł danych GROUPBY
description: W tym temacie wyjaśniono, jak można używać typu źródeł danych GROUPBY w Raportowaniu elektronicznym (ER).
author: NickSelin
ms.date: 03/18/2022
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b79dfe62122a031ae9ed7f51ea7ff578cd47358
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462305"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Grupowanie rekordów i łączenie obliczeń przy użyciu źródeł danych GROUPBY

[!include[banner](../includes/banner.md)]

Podczas konfigurowania mapowania lub formatów modelu [Raportowania elektronicznego (ER)](general-electronic-reporting.md) możesz [dodać](#AddMmDataSource2) wymagane źródła danych typu **GroupBy**.

W czasie projektowania źródło danych **GroupBy** jest skonfigurowane tak, aby identyfikować następujące elementy:

- Podstawowe [źródło danych zawierające](#BaseDataSource) rekordy, które zostaną pogrupowane w czasie wykonywania
- [Pola grupowania](#GroupingFields) podstawowego źródła danych, które będą używane do grupowania rekordów w czasie wykonywania
- [Funkcje agregowania](#AggregateFunctions) określające obliczenia agregowania, które będą wykonywane dla każdej odnalezionej grupy w czasie wykonywania

W czasie wykonywania skonfigurowana grupa źródeł danych **GroupBy** zawiera takie same wartości w polach grupowania, a następnie zwraca listę rekordów. Każdy rekord reprezentuje pojedynczą grupę. Dla każdej grupy źródło danych ujawnia wartości pól, według których zostały pogrupowane początkowe rekordy, wartości obliczonych funkcji agregujących oraz listę rekordów bazowego źródła danych, które należą do grupy.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>Funkcje agregujące

W trybie uruchomieniowym każde obliczenie zbiorcze jest wykonywane dla każdej grupy rekordów. To obliczenie jest wykonywane przy użyciu wartości pojedynczego pola lub wyrażenia w rekordach źródła danych, które zostało wybrane do grupowania w edytowalnym źródle danych typu **GroupBy**. Obecnie obsługiwane są następujące funkcje agregacji:

- **AVG** – ta funkcja zwraca średnią wartości z grupy. Można jej używać tylko z polami liczb.
- **COUNT** – ta funkcja zwraca liczbę towarów znalezionych w grupie.
- **Min** – ta funkcja zwraca wartość minimalną z wartości w grupie.
- **Max** – ta funkcja zwraca wartość maksymalną z wartości w grupie.
- **SUM** – ta funkcja zwraca sumę wszystkich wartości w grupie. Można jej używać tylko z polami liczb.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Lokalizacja wykonywania

Podczas edytowania źródła danych **GroupBy** i określania podstawowego źródła danych zawierającego rekordy, które muszą zostać pogrupowane, system automatycznie wykrywa najbardziej efektywną [lokalizację](#ExecutionLocation) wykonania tego źródła danych **GroupBy**. Jeśli podstawowe źródło danych [umożliwia wykonywanie kwerend](er-functions-list-filter.md#usage-notes) (to jest możliwe do uruchomienia na poziomie bazy danych), baza danych aplikacji jest także określana jako lokalizacja wykonania edytowalnego źródła danych **GroupBy**. W przeciwnym razie pamięć serwera aplikacji jest określana jako lokalizacja wykonania.

Możesz ręcznie zmienić automatycznie wykrytą lokalizację wykonania, wybierając lokalizację, która jest odpowiednia dla skonfigurowanego źródła danych. Jeśli wybrane miejsce wykonania nie jest odpowiednie, w czasie projektowania zostanie wyświetlony [błąd weryfikacji](er-components-inspections.md#i5).

> [!TIP]
> Zalecamy, byś używał lokalizacji bazy danych do grupowania źródeł danych, które wyświetlają dużą liczbę rekordów.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>Zużycie pamięci

Domyślnie jeśli źródło danych **GroupBy** jest uruchamiane w pamięci, pamięć serwera aplikacji jest używana do przechowywania rekordów podstawowego źródła danych należącego do każdej odnalezionej grupy jako rekordów z jednej grupy. Aby zredukować zużycie pamięci, można wyłączyć przechowywanie rekordów dla źródeł danych **GroupBy**, jeśli zostały one skonfigurowane do obliczania tylko zagregowanych funkcji, a rekordy ich grup nie są używane w czasie wykonywania. Aby w ten sposób zmniejszyć zużycie pamięci, włącz opcję **Zmniejsz zużycie pamięci w aplikacji ER**, jeśli grupowanie rekordów służy tylko do obliczania funkcji agregacji w obszarze roboczym **Zarządzanie funkcjami**.

## <a name="alternatives"></a><a name="Alternatives"></a>Alternatywy

Podobne agregacje można obliczyć przy użyciu [różnych](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) typów źródeł danych lub funkcji wbudowanych ER.

Zapoznaj się z następującym przykładem, aby dowiedzieć się więcej.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>Przykład: Użyj źródła danych GROUPBY do obliczeń zbiorczych i grupowania rekordów

Ten przykład pokazuje, jak użytkownik w roli administratora systemu lub konsultanta funkcjonalnego raportowania elektronicznego może skonfigurować odwzorowanie modelu ER ze źródłem danych **GROUPBY**, które jest używane do obliczania funkcji zbiorczych i grupowania rekordów. To odwzorowanie modelu jest używane do drukowania raportu kontrolnego, gdy generowana jest deklaracja Intrastat. Ten raport pozwala Ci przejrzeć zgłoszone transakcje Intrastat.

Zadania przedstawione w tym przykładzie można wykonać w kontekście firmy **DEMF** w Microsoft Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Przygotowywanie przykładowych danych

Upewnij się, że na stronie Intrastat są raportowanie transakcje **Intrastat**. Trzeba mieć transakcje dla różnych kodów transportu, ponieważ transakcje zostaną pogrupowane według pola **Transport** w tym przykładzie.

![Trwa przygotowywanie transakcji Intrastat na stronie Intrastat.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Wykonaj kroki opisane w sekcji [Konfigurowanie platformy ER](er-quick-start2-customize-report.md#ConfigureFramework), aby skonfigurować minimalny zestaw parametrów ER. Musisz zakończyć tę konfigurację, zanim zaczniesz używać platformy ER do projektowania odwzorowania modelu ER.

### <a name="import-the-standard-er-format-configuration"></a>Importowanie standardowej konfiguracji formatu ER

Postępuj zgodnie z instrukcjami w [Importuj standardową konfigurację formatu ER](er-quick-start2-customize-report.md#ImportERSolution1), aby dodać standardowe konfiguracje ER do bieżącego wystąpienia Dynamics 365 Finance. Zaimportuj z repozytorium wersję 1 konfiguracji **modelu Intrastat**.

### <a name="create-a-custom-data-model-configuration"></a>Utwórz konfigurację niestandardowego modelu danych

Wykonaj kroki opisane w punkcie [Dodaj konfigurację niestandardowego modelu danych](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration), aby ręcznie dodać nową **konfigurację modelu danych ER (Litware)**, która powstała z zaimportowanej **konfiguracji modelu danych ER**.

### <a name="configure-a-custom-data-model-component"></a>Skonfiguruj komponent własnego modelu danych

Wykonaj poniższe kroki, aby dokonać wymaganych zmian w pochodnym modelu danych **Intrastat model (Litware)**, tak aby mógł on być użyty do wyświetlenia kodów transportowych, które posiadają wymagane szczegóły.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Intrastat model (Litware)**.
3. Wybierz opcję **Konstruktor**.
4. Na stronie **Projektanta modelu danych**, w drzewie modelu, wybierz **Intrastat**.
5. Wybierz opcję **Nowy**, aby dodać nowy zagnieżdżony węzeł dla wybranego węzła **Intrastat**. W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. W polu **Nazwa** wpisz **Transport**.
    2. W polu **Kod przedmiotu** wybierz **Lista tabel**.
    3. Wybierz **Dodaj**, aby dodać nowy węzeł.

6. Wybierz pozycję **Nowy**, aby dodać nowy zagnieżdżony węzeł dla nowo dodanego węzła **transportu**. W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. Wprowadź **nazwę** w polu, wpisz **Kod**.
    2. W polu **Typ przedmiotu** wybierz **Ciąg**.
    3. Wybierz **Dodaj**, aby dodać nowy węzeł.

7. Wybierz pozycję **Nowy**, aby dodać kolejny zagnieżdżony węzeł dla nowo dodanego węzła **transportu**. W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. W polu **Nazwa** wpisz **TotalInvoicedAmount**.
    2. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
    3. Wybierz **Dodaj**, aby dodać nowy węzeł.

8. Wybierz pozycję **Nowy**, aby dodać kolejny zagnieżdżony węzeł dla nowo dodanego węzła **transportu**. W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. W polu **Nazwa** wpisz **NumberOfTransactions**.
    2. W polu **Typ elementu** wybierz opcję **Liczba całkowita**.
    3. Wybierz **Dodaj**, aby dodać nowy węzeł.

9. Wybierz pozycję **Nowy**, aby dodać kolejny zagnieżdżony węzeł dla nowo dodanego węzła **transportu**. W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. W polu **Nazwa** wpisz **Transakcje**.
    2. W polu **Kod przedmiotu** wybierz **Lista tabel**.
    3. Wybierz **Dodaj**, aby dodać nowy węzeł.

10. Dla węzła **Transakcja**, który właśnie dodałeś, na szybkiej karcie **Węzeł** wybierz **Przełącz odniesienie do elementu**.
11. W oknie dialogowym **Przełącz odwołanie do elementu** w drzewie modeli danych wybierz pozycję **CommodityRecord**. Następnie wybierz opcję **OK**.

![Skonfigurowany model danych w projektancie modeli danych ER.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Umożliwia zaprojektowanie niestandardowego projektu modelu danych

Wykonaj kroki opisane w części [Zakończ projektowanie modelu danych](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration), aby zakończyć projektowanie pochodnego **modelu danych Intrastat (Litware)**.

### <a name="create-a-new-model-mapping-configuration"></a>Stwórz nowy model konfiguracji mapowania

Wykonaj kroki opisane w punkcie [Utwórz nową konfigurację odwzorowania modelu](er-quick-start1-new-solution.md#CreateModelMapping), aby ręcznie dodać nową konfigurację **Odwzorowanie modelu Intrastat** odwzorowania modelu ER dla pochodnej konfiguracji **modelu Intrastat (Litware)**.

### <a name="add-a-new-model-mapping-component"></a>Dodaj nowy składnik odwzorowujący model

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model Intrastat**.
3. W polu Nazwa wpisz **Przykładowe mapowanie Intrastat**.
4. Wybierz opcję **Projektant**, aby otworzyć listę mapowań.
5. Wybierz polecenie **Usuń**, aby usunąć istniejący składnik mapowania.
6. Wybierz pozycję **Nowy**, aby dodać nowy składnik mapowania.
7. W polu **Definicja** zaznacz wartość **Intrastat**.
8. W polu **Nazwa** wpisz **Mapowanie Intrastat**.
9. Wybierz opcję **Projektant**, aby skonfigurować nowe mapowanie.

### <a name="design-the-added-model-mapping-component"></a>Zaprojektuj dodany komponent odwzorowujący model

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>Dodawanie źródeł danych w celu uzyskania dostępu do tabeli aplikacji

Skonfiguruj źródło danych, aby uzyskać dostęp do tabel aplikacji, które zawierają szczegóły transakcji Intrastat.

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Rekordy tabeli**.
2. W okienku **Źródła danych** wybierz pozycję **Dodaj główny**, aby dodać nowe źródło danych, które będzie używane w celu uzyskania dostępu do tabeli **Intrastat**. Każdy rekord w tabeli **Intrastat** reprezentuje pojedynczą transakcję Intrastat.
3. W oknie dialogowym **Właściwości źródła danych**, w polu **Nazwa** wpisz **Transakcja**.
4. W polu **Tabela** wprowadź **Intrastat**.
5. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Dodaj źródło danych do grupowania transakcji Intrastat

Skonfiguruj źródło danych **GroupBy** tak, aby grupować transakcje Intrastat i obliczać funkcje agregowania.

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz **Funkcje\\Grupuj wg**.
2. W panelu **Źródła danych** wybierz **Dodaj główne**, aby dodać nowe źródło danych, które będzie używane do grupowania transakcji Intrastat i obliczania funkcji agregujących.
3. W oknie dialogowym **Właściwości źródła danych**, w polu **Nazwa** wpisz **TransportRecord**.
4. Wybierz pozycję **Edytuj grupę według**, aby skonfigurować warunki grupowania.
5. Na stronie **Edytuj parametry 'Grupa wg'**, na liście źródeł danych w prawym panelu wybierz źródło danych **Transakcja** i rozwiń je.
6. Wybierz **Dodaj pole do grupy \> Jakiej grupy**, aby wskazać, że źródło danych **Transakcja** jest wybrane jako <a name="BaseDataSource">bazowe źródło danych</a> dla skonfigurowanego źródła danych **GroupBy**. Rekordy źródła danych **Transakcja** zostaną pogrupowane, a wartości pól tego źródła danych będą używane do obliczeń w funkcjach agregowania.
7. Zaznacz pole **Transakcja\Transport**, a następnie wybierz **Dodaj pole \> Pole zgrupowane**, aby wskazać, że pole **Transport** podstawowego źródła danych jest wybrane jako <a name="GroupingFields">kryterium grupowania</a> dla skonfigurowanego źródła danych **GroupBy**. Innymi słowy, rekordy źródła danych **Transakcja** zostaną pogrupowane na podstawie wartości pola **Transport**. Każdy rekord skonfigurowanego źródła danych **GroupBy** będzie reprezentował jeden kod transportu znaleziony w rekordach podstawowego źródła danych.
8. Zaznacz pole **Transakcja\AmountMST**, a następnie wykonaj następujące czynności:

    1. Wybierz opcję **Dodaj pole \> Pola zagregowane**, aby wskazać, że dla tego pola zostanie obliczona <a name="AggregateFunctions">funkcja agregacji</a>.
    2. W panelu **Agregacje**, w rekordzie, który został dodany dla wybranego pola **Transakcja\AmountMST**, w polu **Metoda** wybierz funkcję **Suma**.
    3. W opcjonalnym polu **Nazwa** wpisz **TotalInvoicedAmount**.

    Te ustawienia określają, że dla każdej grupy transportu zostanie obliczona łączna kwota pola **Transakcja\AmountMST**.

9. Zaznacz pole **Transakcja\RecId**, a następnie wykonaj następujące czynności:

    1. Wybierz opcję **Dodaj pole \> Pola zagregowane**, aby wskazać, że dla tego pola zostanie obliczona funkcja agregacji.
    2. W panelu **Agregacje**, w rekordzie, który został dodany dla wybranego pola **Transakcja\RecId**, w polu **Metoda** wybierz funkcję **Liczba**.
    3. W opcjonalnym polu **Nazwa** wpisz **NumberOfTransactions**.

    Te ustawienia określają, że dla każdej grupy transportowej będzie obliczana liczba transakcji w tej grupie.

10. Wybierz opcję **Zapisz**.
11. Przejrzyj parametry <a name="ExecutionLocation">wykonywania</a> edytowalnego źródła danych. Zwróć uwagę, że **autodetect** został automatycznie wybrany w polu **Lokalizacja wykonania**, a pole **Wykonanie w** zawiera wartość **SQL**. Ustawienia te określają, że wybrane bazowe źródło danych **Transakcja** jest aktualnie dostępne dla zapytań oraz że możesz uruchomić edytowalne źródło danych **GroupBy** na poziomie bazy danych.
12. Otwórz odnośniki do pola **Lokalizacja wykonania**, aby przejrzeć listę dostępnych wartości. Należy zauważyć, że można wybrać opcję **Zapytanie** lub **W pamięci**, aby wymusić uruchomienie źródła danych **GroupBy** na poziomie bazy danych lub w pamięci serwera aplikacji.
13. Wybierz **Zapisz**, a następnie zamknij stronę **Edycja parametrów 'Grupa wg'**.
14. Wybierz przycisk **OK**, aby zakończyć ustawienia źródła danych **GroupBy**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>Powiąż źródło danych GroupBy z polami modelu danych

Powiąż skonfigurowane źródło danych z polami modelu danych, aby określić, w jaki sposób model danych będzie wypełniany danymi aplikacji w trybie runtime.

1. Na stronie **Projektant mapowania modelu** w okienku **Model danych** rozwiń węzeł **Transport**.
2. W panelu **Źródła danych** rozwiń źródło danych **TransportRecord**.
3. Dodaj powiązanie, aby uwidaczniać listę odnalezionych grup transportu:

    1. W okienku **Model danych** wybierz **Transport**.
    2. W panelu **Źródła danych** rozwiń źródło danych **TransportRecord**.
    3. Wybierz **Powiąż**.

4. Dodaj wiązanie, aby ujawnić kod transportowy każdej odkrytej grupy transportowej:

    1. Wybierz pozycję modelu danych **Transport.Code**.
    2. Zaznacz pole zgrupowane **TransportRecord.grouped.TransportMode**.
    3. Wybierz **Powiąż**.

5. Dodaj wiązanie, aby ujawnić wartości obliczonych funkcji agregujących dla każdej odkrytej grupy transportowej:

    1. Wybierz pozycję modelu danych **Transport.NumberOfTransactions**.
    2. Zaznacz pole zagregowane **TransportRecord.aggregated.NumberOfTransactions**.
    3. Wybierz **Powiąż**.
    4. Wybierz pozycję modelu danych **Transport.TotalInvoicedAmount**.
    5. Zaznacz pole zagregowane **TransportRecord.aggregated.TotalInvoicedAmount**.
    6. Wybierz **Powiąż**.

6. Dodaj wiązanie, aby odsłonić rekordy transakcji, które należą do każdej odkrytej grupy transportowej:

    1. Wybierz pozycję modelu danych **Transport.Transaction**.
    2. Zaznacz pole **TransportRecord.lines**.
    3. Wybierz **Powiąż**.

    Możesz kontynuować konfigurowanie wiązań dla zagnieżdżonych pozycji modelu danych **Transport.Transaction** i pola źródła danych **TransportRecord.lines**, aby ujawnić w czasie rzeczywistym szczegóły transakcji Intrastat, które należą do każdej odkrytej grupy transportowej.

![Skonfigurowany model mapowania w projektancie modeli mapowania ER.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Debugowanie dodanego komponentu odwzorowującego model

Użycie [debugera źródła danych ER](er-debug-data-sources.md) do testowania skonfigurowanego mapowania modelu.

1. Przycisk **Rozpocznij debugowanie** na stronie **projektanta mapowania modelu**.
2. Na stronie **Źródła danych debugowania**, w lewym panelu wybierz źródło danych **TransportRecord**, a następnie wybierz **Odczytaj wszystkie rekordy**.
3. Rozwiń źródło danych **TransportRecord**, a następnie wykonaj poniższe kroki:

    1. Zaznacz źródło danych **TransportRecord.grouped.TransportMode**.
    2. Wybierz pozycję **Pobierz wartość**.
    3. Zaznacz źródło danych **TransportRecord.grouped.NumberOfTransactions**.
    4. Wybierz pozycję **Pobierz wartość**.
    5. Zaznacz źródło danych **TransportRecord.grouped.TotalInvoicedAmount**.
    6. Wybierz pozycję **Pobierz wartość**.

4. W okienku po prawej stronie włącz pozycję **Rozwiń wszystko**.

Źródło danych **TransportRecord** uwidacznia dwa rekordy i prezentuje dwa kody transportu. Dla każdego kodu transportu obliczana jest liczba transakcji i całkowita zafakturowana kwota.

> [!NOTE]
> Metoda „opóźnienie odczytu” jest używana, gdy źródło danych **GroupBy** jest wywoływane do optymalizowania wywołań baz danych. Dlatego niektóre wartości pól w źródle danych **GroupBy** są obliczane w debugerze źródeł danych ER tylko wtedy, gdy są one związane z polami modelu danych.

![Wyniki debugowania źródła danych na stronie Debugowanie źródeł danych.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Czy jest jakiś sposób obliczania sum sumy całkowitej podczas obliczania sum dla grupy?

Tak. Aby obliczyć sumy całkowite, skonfiguruj inne źródło danych **GroupBy**, w którym uprzednio skonfigurowane źródło danych **GroupBy** jest używane jako podstawowe źródło danych. Poniższa ilustracja przedstawia źródło danych **Totals** typu **GroupBy**, które jest używane do obliczania zagregowanej funkcji **SUM** na podstawie agregacji **SUM** źródła danych **TransportRecord** typu **GroupBy**.

![Źródło danych sumarycznych w projektancie odwzorowania modelu ER.](./media/er-groupby-data-sources-configure-model-mapping2.png)

Poniższa ilustracja pokazuje rezultaty debugowania źródła danych **Totals**.

![Wyniki debugowania źródła danych Totals na stronie Debugowanie źródeł danych.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych](er-debug-data-sources.md)
- [Korzystanie ze źródeł danych DATA COLLECTION w formatach raportowania elektronicznego](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
