---
title: Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH
description: W tym temacie wyjaśniono, w jaki sposób można usprawnić działanie rozwiązań raportowania elektronicznego (ER), dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e3dc83b71300387c8123f5533522c5ead7d86333
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349191"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, w jaki sposób można pobierać [dane śledzenia wydajności](trace-execution-er-troubleshoot-perf.md) dla uruchomionych formatów [raportowania elektronicznego (ER)](general-electronic-reporting.md), a następnie używać informacji z tych procesów w celu zwiększenia wydajności, konfigurując źródło danych dla sparametryzowanych **pól obliczeniowych**.

W ramach procesu projektowania konfiguracji raportowania elektronicznego (ER) w celu generowania dokumentów biznesowych należy zdefiniować metodę, która jest używana do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych. Po zaprojektowaniu wstępnie zdefiniowanego źródła danych dla **Pola obliczeniowego** można zmniejszyć liczbę wywołań bazy danych i znacząco zredukować czas i koszt, który ma być związany z zbieraniem szczegółów dotyczących wykonania formatu ER.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do jednej z następujących [ról](../sysadmin/tasks/assign-users-security-roles.md):

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Firmę należy ustawić na wartość **DEMF**.
- Wykonaj kroki opisane w [dodatku 1](#appendix1) do tego tematu, aby pobrać składniki przykładowego rozwiązania Microsoft ER wymagane do przetwarzania płatności dostawców.
- Postępuj zgodnie z krokami opisanymi w [dodatku 2](#appendix2) do tego tematu, aby skonfigurować minimalny zestaw parametrów funkcji ER, który jest wymagany w celu zwiększenia wydajności przykładowego rozwiązania Microsoft ER.

## <a name="import-the-sample-er-solution"></a>Importuj przykładowe rozwiązania ER

Załóżmy, że rozpoczęto projektowanie nowego rozwiązania ER w celu wygenerowania nowego raportu, który przedstawia transakcje dostawcy. Dotychczas transakcje wybranego dostawcy można było znaleźć na stronie **Transakcje dostawcy** (przejdź do **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy**, wybierz dostawcę, a następnie, w okienku akcji, na karcie **Dostawca**, w grupie **Transakcje** wybierz opcję **Transakcje**). Chcesz jednak mieć wszystkie transakcje dostawcy w jednym dokumencie elektronicznym w formacie XML. To rozwiązanie będzie składać się z kilku konfiguracji ER, które zawierają wymagany model danych, metadane, mapowanie modeli i składniki formatu.

Pierwszym krokiem jest zaimportowanie przykładowego rozwiązania ER w celu wygenerowania raportu transakcji dostawcy.

1. Zaloguj się do wystąpienia Microsoft Dynamics 365 Finance, które zostało zainicjowane dla danej firmy.
2. W tym temacie utworzysz i zmodyfikujesz konfiguracje dla przykładowej firmy **Litware, Inc.** Upewnij się zatem, że ten dostawca konfiguracji jest dodany do wystąpienia Finance i wybrany jako aktywny. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
4. Na stronie **Konfiguracje** zaimportuj konfiguracje ER, które zostały pobrane jako wstępnie wymagane do Finance, w następującej kolejności: model danych, metadane, mapowanie modelu, format. Dla każdej konfiguracji wykonaj następujące czynności:

    1. W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.
    2. Kliknij przycisk **Przeglądaj** i wybierz odpowiedni plik wymaganej konfiguracji ER w formacie XML.
    3. Kliknij przycisk **OK**.

![Zaimportowane konfiguracje na stronie Konfiguracje.](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>Przejrzyj przykładowe rozwiązania ER

### <a name="review-the-model-mapping"></a>Przeglądanie mapowania modelu

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model poprawy wydajności**, a potem wybierz **Mapowanie poprawy wydajności**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Modelowanie do mapowania źródła danych**.

    W tym mapowaniu modelu ER jest przeznaczony do wykonywania następujących czynności:

    - Umożliwia pobieranie listy transakcji dostawcy, które są przechowywane w tabeli VendTrans (Źródło danych **transakcji**).
    - Dla każdej transakcji należy pobrać z tabeli VendTable rekord dostawcy, dla którego zaksięgowano transakcję (Źródło danych **\#Dostawca**).

    > [!NOTE]
    > Źródło danych **\#Dostawca** jest skonfigurowane do pobierania odpowiedniego rekordu dostawcy przy użyciu istniejącej relacji wiele-do-jednego **\@.'\>Relations'.VendTable\_AccountNum**.

    Mapowanie modelu w tej konfiguracji implementuje podstawowy model danych dla dowolnego formatu ER utworzonego dla tego modelu i wykonywanego w Finance. W wyniku tego zawartość źródeł danych **Transakcji** jest udostępniana dla formatów ER, takich jak **modelowe** źródła danych.

    ![Dodano źródło danych transakcji w konstruktorze mapowania modelu.](media/er-calculated-field-ds-performance-mapping-1.png)

4. Zamknij stronę **Projektant mapowania modelu**.
5. Zamknij stronę **Mapowanie modelu do źródła danych**.

### <a name="review-format"></a>Format przeglądu

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model poprawy wydajności**, a potem wybierz **Format poprawy wydajności**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Na stronie **Projektant formatów**, na karcie **Mapowanie** wybierz **Zwiń/Rozwiń**.
4. Rozwiń **Model**, **Dane,** i **Transakcja**.

    Ten format ER jest przeznaczony do generowania raportu transakcji dostawcy w formacie XML.

    ![Formatowanie źródeł danych i skonfigurowanych powiązań elementów formatu na stronie Projektant formatów.](media/er-calculated-field-ds-performance-format.png)

5. Zamknij stronę **Projektowanie formuły**.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>Uruchom przykładowe rozwiązanie ER, aby śledzić wykonywanie

Załóżmy, że zakończono projektowanie pierwszej wersji rozwiązania ER. Chcesz teraz przetestować je w swoim wystąpieniu Finance oraz przeanalizować wydajność wykonywania.

### <a name="turn-on-the-er-performance-trace"></a>Włączanie śledzenia wydajności ER

1. Wybierz pole firmę **DEMF**.
2. Przejdź przez kroki w [Włączanie śledzenia wydajności ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace), aby wygenerować śledzenie wydajności podczas uruchamiania formatu encji, gdy wykonywany jest format ER.

    ![Okno dialogowe parametry użytkownika.](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Uruchamianie formatu ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format poprawy wydajności**.
3. W okienku akcji wybierz opcję **Uruchom**.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>Śledzenie wydajności umożliwia analizowanie wydajności mapowania modeli

1. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie poprawy wydajności**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Mapowania modelu**.
4. Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.
5. Wybierz najnowszy wygenerowany wynik śledzenia, a następnie wybierz przycisk **OK**.

Zostaną teraz udostępnione nowe informacje dotyczące niektórych pozycji źródła danych bieżącego mapowania modelu:

- Rzeczywisty czas poświęcony na uzyskiwanie danych przy użyciu źródła danych
- Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wykonywanie całego mapowania modelu

![Szczegóły czasu wykonania na stronie projektanta mapowania modelu.](./media/er-calculated-field-ds-performance-mapping-2.png)

Siatka **Statystyka wydajności** pokazuje, że źródło danych **Transakcji** wywołuje tabelę VendTrans jeden raz. Wartość **\[265\]\[Q:265\]** źródła danych **Transakcji** wskazuje, że 265 transakcje dostawcy zostały pobrane z tabeli aplikacji i zwrócone do modelu danych.

Siatka **statystyk wydajności** pokazuje również, że bieżące mapowanie modeli powoduje duplikowanie żądań baz danych podczas uruchamiania źródła danych **\#Dostawca**. Duplikacja odbywa się z następujących powodów:

- Tabela dostawcy jest wywoływana dwa razy dla każdej z 265 powtarzających się transakcji dostawcy, co daje łączną liczbę wezwań 530:

    - Jedno wywołanie jest wykonywane w celu wprowadzenia numeru konta dostawcy.
    - Jedno wywołanie jest wykonywane w celu wprowadzenia nazwy dostawcy.

- Tabela dostawców jest wywoływana dla każdej powtarzanej transakcji dostawcy, nawet jeśli pobrane transakcje zostały zaksięgowane tylko dla pięciu dostawców. Spośród 530 wywołań, 525 to duplikaty. Na poniższej ilustracji przedstawiono komunikat dotyczący zduplikowanych wywołań (żądań bazy danych).

![Komunikat dotyczący zduplikowanych żądań bazy danych na stronie projektanta mapowania modelu.](./media/er-calculated-field-ds-performance-mapping-2a.png)

Spośród całkowitego czasu wykonywania mapowania modelu (około osiem sekund) pobieranie wartości z tabeli aplikacji VendTable zajęło więcej niż 80% (około sześciu sekund). Wartość procentowa jest zbyt duża dla dwóch atrybutów pięciu dostawców w porównaniu z ilością informacji z tabeli aplikacji VendTrans.

Aby zmniejszyć liczbę wywołań, które są wykonywane w celu uzyskania szczegółów dotyczących dostawcy dla każdej transakcji, oraz zwiększyć wydajność mapowania modeli, można korzystać z buforowania dla źródła danych **\#Dostawca**.

> [!NOTE]
> Źródło danych **Transakcja\\\#Dostawca** będzie buforowane w zakresie bieżącej transakcji źródła danych **transakcji** w czasie wykonywania.

Dzięki buforowaniu źródła danych **\#Dostawca** zmniejsza się liczbę zduplikowanych wywołań z 525 do 260, ale nie eliminuje to całkowicie duplikatów. Aby całkowicie wyeliminować duplikacje, można skonfigurować nowe, sparametryzowane źródło danych typu **pola obliczeniowego**.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Poprawianie mapowania modelu na podstawie informacji ze śladu wykonywania

### <a name="change-the-logic-of-the-model-mapping"></a>Zmiana mapowania modelu

Wykonaj poniższe kroki, aby użyć buforowania i źródła danych typu **pola obliczeniowego** w celu uniknięcia zduplikowanych wywołań bazy danych.

1. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie poprawy wydajności**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Mapowania modelu**.
4. Na stronie **Projektant mapowania modeli** wykonaj poniższe kroki, aby dodać źródło danych typu **rekord tabeli** w celu uzyskania dostępu do rekordów w tabeli aplikacji VendTable:

    1. W okienku **Typy źródła danych** rozwiń opcję **Dynamics 365 for Operations** i wybierz **Rekordy tabeli**.
    2. Wybierz **Dodaj element główny**.
    3. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Dostawca**.
    4. W polu **Tabela** wprowadź **VendTable**.
    5. Kliknij przycisk **OK**.

5. Można parametryzować wywołania źródeł danych **pola obliczeniowego** tylko wtedy, gdy te źródła danych znajdują się w kontenerze. Dlatego należy wykonać poniższe kroki w celu dodania źródła danych do typu **pustego kontenera** w celu przechowywania nowego sparametryzowanego źródła danych typu **obliczanego pola**:

    1. W okienku **Typy źródła danych** rozwiń opcję **Ogólne** i wybierz **Pusty kontener**.
    2. Wybierz **Dodaj element główny**.
    3. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Pole**.
    3. Kliknij przycisk **OK**.

    ![Dodano źródło danych pole w konstruktorze mapowania modelu.](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Aby dodać sparametryzowane źródło danych typu **pola obliczeniowego**, należy wykonać następujące kroki:

    1. Wybierz opcję **Pole** w okienku **Źródła danych**.
    2. W okienku **Typy źródła danych** rozwiń pozycję **Funkcje** i wybierz **Pole obliczeniowe**.
    3. Wybierz opcję **Dodaj**.
    4. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Dostawca**.
    5. Wybierz opcję **Edytuj formułę**.
    6. Na stronie **Projektant formuł** wybierz **Parametry**, aby określić parametry, które muszą zostać dostarczone, gdy to źródło danych zostanie wywołane.
    7. W oknie dialogowym **Parametry** wybierz przycisk **Nowy**.
    8. W polu **Nazwa** wpisz **parmVendAccNumber**.
    9. W polu **Typ** wybierz **Ciąg**.
    10. Kliknij przycisk **OK**.
    11. W polu **Formuła** wprowadź **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.
    13. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

7. Aby oznaczyć dodane źródło danych jako buforowane podczas wykonywania, należy wykonać następujące kroki:

    1. W okienku **Źródła danych** wybierz **Pole\\Dostawca**.
    2. Wybierz opcję **Pamięć podręczna**.

    > [!NOTE]
    > Źródło danych **Pole\\Dostawca** będzie buforowane w zakresie wszystkich transakcji źródła danych **transakcji** w czasie wykonywania.

8. Wykonaj poniższe kroki, aby zaktualizować zagnieżdżone źródło danych **Transakcja\\\#Dostawca**, aby korzystało ze źródła **Pole\\Dostawca**:

    1. W okienku **Źródła danych** rozwiń **Transakcja**.
    2. Wybierz źródło danych **Transakcje\\\#Dostawca**, a następnie wybierz opcję **Edytuj** \> **Edytuj formułę**.
    3. Na stronie **Projektant formuł** wprowadź w polu **Formuła** następującą wartość **Box.Vend(\@.AccountNum)**.
    4. Zamknij stronę **Projektowanie formuły** i wybierz **Zapisz**.
    5. Wybierz przycisk **OK**, aby ukończyć wprowadzanie zmian w wybranym źródle danych.

9. Wybierz opcję **Zapisz**.

    ![Źródło danych dostawca w konstruktorze mapowania modelu.](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Zamknij stronę **Projektant mapowania modelu**.
11. Zamknij stronę **Mapowanie modelu**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Kończenie zmodyfikowanej wersji mapowania modelu ER

1. Na stronie **Konfiguracje** na karcie skróconej **Wersje** wybierz wersję **1.2** konfiguracji **Mapowanie poprawy wydajności**.
2. Wybierz pozycję **Zmień stan** \> **Zakończone**, a następnie wybierz opcję **OK**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Uruchom zmodyfikowane rozwiązanie ER, aby śledzić wykonywanie

Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>Śledzenie wydajności umożliwia zmiany w mapowaniu modeli 

1. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie poprawy wydajności**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Mapowania modelu**.
4. Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.
5. Wybierz najnowszy wygenerowany wynik śledzenia, a następnie wybierz przycisk **OK**.

Korekty wprowadzone w mapowaniu modelu wyeliminowały duplikowanie zapytań do bazy danych. Liczba wywołań tabel bazy danych i źródeł danych tego mapowania modelu również została zmniejszona.

![Śledzenie danych w konstruktorze mapowania modelu 1.](./media/er-calculated-field-ds-performance-mapping-5.png)

Całkowity czas wykonania został zredukowany o 20 razy (z 8 sekund do około 400 milisekund). Wydajność całego rozwiązania ER uległa zatem poprawie.

![Śledzenie danych w konstruktorze mapowania modelu 2.](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>Dodatek 1: Pobierz składniki przykładowego rozwiązania Microsoft ER

Musisz również pobrać i lokalnie zapisać następujące pliki.

| Plik                                        | Zawartość |
|---------------------------------------------|---------|
| Performance improvement model.version.1     | [Przykładowa konfiguracja modelu danych ER](https://download.microsoft.com/download/4/6/f/46f0f3fa-782b-414a-8f7b-b6c64a388661/Performance_improvement_model.version.1.xml) |
| Performance improvement mapping.version.1.1 | [Przykładowa konfiguracja mapowania modelu ER](https://download.microsoft.com/download/8/9/1/8913a763-afb8-4bf4-aaf1-95ad793ffc5a/Performance_improvement_mapping.version.1.1.xml) |
| Performance improvement format.version.1.1  | [Przykładowa konfiguracja formatu ER](https://download.microsoft.com/download/9/0/c/90c75963-bc78-4edc-9096-556bbe281f10/Performance_improvement_format.version.1.1.xml) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>Dodatek 2: Konfigurowanie struktury ER

Zanim będzie można rozpocząć korzystanie z struktury ER w celu zwiększenia wydajności przykładowego rozwiązania Microsoft ER, należy skonfigurować minimalny zestaw parametrów ER.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Konfigurowanie parametrów modułu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Parametry raportowania elektronicznego**.
3. Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.
4. Na karcie **Załączniki** ustaw następujące parametry:

    - W polu **Konfiguracje** wybierz typ **Plik** dla firmy **DEMF**.
    - W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy wybrać typ **Plik**.

Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Aktywowanie dostawcy konfiguracji ER

Każda dodana konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER. W tym celu jest używany dostawca konfiguracji ER, który został aktywowany w obszarze roboczym **Raportowanie elektroniczne**. Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.

> [!NOTE]
> Tylko właściciel konfiguracji ER może edytować konfigurację. Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Przejrzenie listy dostawców konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.
3. Na stronie **Tabela dostawcy konfiguracji** każdy rekord dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony. Jeśli rekord dla **Litware, Inc.** już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Dodawanie nowego dostawcy formatu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.
3. Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.
4. W polu **Nazwa** wpisz **Litware, Inc.**
5. W polu **Adres internetowy** wprowadź `https://www.litware.com`.
6. Wybierz opcję **Zapisz**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Aktywowanie dostawcy konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz pozycję **Litware, Inc.**, a następnie wybierz pozycję **Ustaw, jako aktywne**.

Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)
- [Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
