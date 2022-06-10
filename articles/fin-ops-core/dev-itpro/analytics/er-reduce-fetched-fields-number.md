---
title: Zwiększ wydajność rozwiązań ER poprzez zredukowanie liczby pól tabeli pobieranych w czasie działania.
description: Ten temat wyjaśnia, jak możesz poprawić wydajność, redukując liczbę pól tabeli pobieranych w czasie wykonywania zadania.
author: NickSelin
ms.date: 05/12/2022
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
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: dd192a7718ac4fd8bcb636ede6c005ca29ee5f08
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811961"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Zwiększ wydajność rozwiązań ER poprzez zredukowanie liczby pól tabeli pobieranych w czasie działania.

[!include[banner](../includes/banner.md)]

Można zaprojektować [formaty](er-overview-components.md#format-components-for-outgoing-electronic-documents) [raportów elektronicznych](general-electronic-reporting.md) ER w taki sposób, aby generowały wychodzące dokumenty w różnych formatach. Podczas generowania dokumentu format ER wywołuje źródła danych, które zostały skonfigurowane w odpowiadającym im [mapowaniu modelu](er-overview-components.md#model-mapping-component) ER. Aby skonfigurować dostęp do tabel aplikacji, kwerend lub encji, można skorzystać z Awaryjnych źródeł danych typu *Zapisy tabeli*. Domyślnie źródło danych typu *Zapisy w tabeli* pobiera wartości wszystkich pól w żądanych rekordach. Możesz jednak skonfigurować ten typ źródła danych tak, aby pobierał tylko te wartości pól, które są wymagane dla działającego formatu ER. Taka konfiguracja pomaga zmniejszyć zużycie pamięci przez serwer aplikacji, który wykonuje pobieranie danych i dalsze buforowanie rekordów.

Aby dowiedzieć się więcej o tym, jak ograniczyć listę pobieranych pól w źródłach danych typu *rekordy tabeli*, wykonaj przykład w tym temacie.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Przykład: Zmniejsz liczbę pól tabeli, które są pobierane w czasie wykonywania zadania

Poniższe procedury pokazują, jak użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może skonfigurować odwzorowanie modelu ER tak, aby pobierało ono tylko te pola, które są wymagane do uruchomienia formatu ER, co pomaga zmniejszyć zużycie pamięci serwera aplikacji.

Wszystkie te procedury można wykonać na danych firmy **USMF** w Microsoft Dynamics 365 Finance. Nie są wymagane umiejętności kodowania.

Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do firmy **USMF** dla jednej z następujących ról:

- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

W tym przykładzie użyjesz [konfiguracji](general-electronic-reporting.md#Configuration) ER, które są dostarczone dla przykładowej firmy **Litware, Inc**. Upewnij się, że dostawca konfiguracji dla przykładowej firmy **Litware, Inc.** (`http://www.litware.com`) jest wymieniony dla struktury ER i jest oznaczony jako **Aktywny**. Jeśli tego dostawcy konfiguracji nie ma na liście lub jeśli nie jest on oznaczony jako **aktywny**, wykonaj kroki opisane w temacie [Tworzenia dostawcy konfiguracji i zaznaczanie go jako aktywny](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Wykonaj kroki opisane w sekcji [Konfigurowanie platformy ER](er-quick-start2-customize-report.md#ConfigureFramework), aby skonfigurować minimalny zestaw parametrów ER. Musisz zakończyć tę konfigurację, zanim zaczniesz używać framework ER do modyfikowania źródeł danych dostarczonego rozwiązania ER.

### <a name="import-the-sample-er-configurations"></a>Importuj przykładowe konfiguracje formatu ER

Jeśli nie ukończyłeś jeszcze przykładu z tematu [Zaprojektuj nowe rozwiązanie ER do drukowania niestandardowego raportu](er-quick-start1-new-solution.md), pobierz i przechowuj lokalnie pliki XML dla następujących konfiguracji dostarczonego rozwiązania ER.

| Opis zawartości            | Nazwa pliku |
|--------------------------------|-----------|
| Konfiguracja modelu danych ER    | [Kwestionariusze model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| Sesja mapowania konfiguracji modelu ER | [Kwestionariusze mapowania.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| ER format konfiguracji        | [Kwestionariusze format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Następnie wykonaj poniższe kroki, aby wgrać konfiguracje dostarczonego rozwiązania ER do swojej instancji finansów.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. Na stronie **Konfiguracje** zaimportuj konfigurację modelu danych ER.

    1. Wybierz **Wymiana**, a następnie wybierz opcję **Ładowanie z pliku XML**.
    2. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Questionnaires model.version.1.xml**, a następnie wybierz **OK**.

4. Zaimportuj plik mapowania modelu danych ER.

    1. Wybierz **Wymiana**, a następnie wybierz opcję **Ładowanie z pliku XML**.
    2. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Questionnaires mapping.1.1.xml**, a następnie wybierz **OK**.

5. Import konfiguracji formatu ER.

    1. Wybierz **Wymiana**, a następnie wybierz opcję **Ładowanie z pliku XML**.
    2. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Questionnaires format.1.1.xml**, a następnie wybierz **OK**.

6. W drzewie konfiguracji rozwiń węzeł **Wzory kwestionariuszy**.
7. Przejrzyj listę zaimportowanych konfiguracji systemu ER w drzewie konfiguracji.

    ![Przeglądanie listy zaimportowanych konfiguracji ER na stronie Konfiguracje.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>Przejrzyj dostarczone odwzorowanie modelu ER

1. Na stronie **Konfiguracje** wybierz opcję **Kwestionariusze mapowania**.
2. W okienku akcji wybierz opcję **Projektant**.
3. Na stronie **Mapowanie modelu na źródło danych** wybierz **Projektant**.
4. Na stronie **Projektanta odwzorowania modelu**, w Panelu akcji wybierz **Widok grupy**, aby włączyć widok **Grupy**.
5. W okienku **Model danych** rozwiń **Kwestionariusz**.

    Zauważ, że źródło danych **Kwestionariusz** zostało skonfigurowane tak, by miało dostęp do tabeli aplikacji `KMCollection`.

6. W panelu **Źródła danych** rozwiń **Rejestry tabel** \> **Kwestionariusz** \> **Pole**.

    Zauważ, jak wiele pól z tabeli aplikacji `KMCollection` jest eksponowanych przez źródło danych **Kwestionariusz** typu *Rekordy tabeli*.

    ![Przeglądanie dostarczonego odwzorowania modelu na stronie projektanta odwzorowania modelu, gdy włączony jest widok grupowy.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. Na panelu akcji ponownie wybierz **Widok grupy**, aby wyłączyć widok **Grupy**, a następnie wybierz **Pokaż wszystkie** \> **Pokaż tylko zmapowane**.

    Zauważ, że kilka pól z tabeli aplikacji `KMCollection` jest używanych do wypełnienia listy rekordów **Kwestionariusz** w modelu danych ER:

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![Przeglądanie dostarczonego odwzorowania modelu na stronie projektanta odwzorowania modelu, gdy wyłączony jest widok grupowy.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Włączanie śledzenia wydajności ER

Wykonaj kroki opisane w punkcie [Włącz śledzenie wydajności ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace), aby ustawić parametry użytkownika ER, które umożliwiają śledzenie wykonania komponentów ER.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>Uruchom dostarczony format ER, używając dostarczonego odwzorowania modelu

Wykonaj kroki opisane w [Uruchom zaprojektowany format z ER](er-quick-start1-new-solution.md#RunFormatFromER), aby uruchomić format ER dla pojedynczego kwestionariusza ze strony **Konfiguracje**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Przejrzyj ślad wykonania pierwszego przejazdu

1. Przejdź do opcji **Administrowanie organizacją** \> **Raporty elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** rozwiń **Model kwestionariusza** i wybierz **Mapowanie kwestionariusza**.

    > [!NOTE]
    > Szczegóły na szybkiej karcie **Wersje** wskazują, że wybrałeś wersję roboczą konfiguracji **Mapowanie kwestionariuszy**. Dlatego możesz modyfikować zawartość tego odwzorowania modelu.

3. W okienku akcji wybierz opcję **Projektant**.
4. Na stronie **Mapowanie modelu na źródło danych** wybierz **Projektant**.
5. Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.
6. W oknie dialogowym **Ustawienia wyników śladu wydajności** wybierz ślad, który został wygenerowany podczas ostatniego uruchomienia formatu.

    ![Wybieranie śladu w oknie dialogowym Ustawienia wyników śladu wydajności.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Kliknij przycisk **OK**. 
8. Na skróconej karcie **Szczegóły** wyfiltruj ścieżkę **Kwestionariusza**, która wskazuje na źródło danych **Kwestionariusza**.
9. Przejrzyj szczegóły zapytania do bazy danych, które zostało wygenerowane po wywołaniu źródła danych **Kwestionariusz**.

    Zauważ, że wszystkie pola tabeli aplikacji `KMCollection` zostały pobrane w czasie wykonywania zadania, gdy źródło danych **Kwestionariusz** zostało wywołane.

    ![Przeglądanie szczegółów zapytania do bazy danych na stronie projektanta odwzorowania modelu.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>Zmodyfikuj dostarczone odwzorowanie modelu ER

1. Na stronie **Projektanta odwzorowania modelu**, w panelu **Źródła danych** wybierz źródło danych **Kwestionariusz**.
2. W panelu **Źródła danych** wybierz **Edytuj**.
3. W oknie dialogowym **Właściwości źródła danych** zaznacz opcję **Wybierz pola**, aby określić listę pól odwołującej się tabeli aplikacji `KMCollection`, które będą pobierane w czasie działania, gdy wywoływane jest edytowalne źródło danych **Kwestionariusz**.

    ![Wybierając opcję Wybierz pola w oknie dialogowym Właściwości źródła danych, możesz rozpocząć konfigurowanie listy pól, które będą pobierane z tabeli aplikacji przy użyciu edytowalnego źródła danych.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. Na stronie **Wybierz pola** wybierz **Autouzupełnianie**.

    Lista **Wybranych pól** jest wypełniana automatycznie na podstawie wstępnie skonfigurowanych artefaktów odwzorowania modelu. Wszystkie pola i relacje z tabeli, do której się odwołujemy, wymienione w jakimkolwiek wiązaniu, formule lub źródle danych odwzorowania modelu są dodawane do listy.

    ![Konfigurowanie listy pól, które będą pobierane z tabeli aplikacji na stronie Wybierz pola.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Wybierz **Zapisz**, a następnie zamknij stronę **Wybierz pola**.
6. Wybierz **OK**, aby zapisać zmiany wprowadzone w ustawieniach źródła danych.
7. W okienku akcji wybierz pozycję **Pokaż wszystko**.

    Zauważ, że w źródle danych **Kwestionariusz** pojawia się teraz tekst **\<Fields are filtered\>**. Ten tekst wskazuje, że źródło danych zostało skonfigurowane do pobierania ograniczonej liczby pól z tabeli aplikacji, do której się odwołuje.

    ![Przeglądanie zaktualizowanego odwzorowania modelu na stronie Projektant odwzorowania modelu.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. Wybierz **Zapisz**, aby zapisać zmiany, których dokonałeś w edytowalnym odwzorowaniu modelu.

    > [!NOTE]
    > W czasie pracy ER analizuje dodane relacje i dodaje do zapytania do bazy danych wszystkie pola, które są w nich używane, nawet jeśli te pola nie zostały jawnie dodane do listy pobieranych pól w czasie projektowania.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>Uruchom dostarczony format ER, używając zaktualizowanego odwzorowania modelu

Wykonaj kroki opisane w [Uruchom zaprojektowany format z ER](er-quick-start1-new-solution.md#RunFormatFromER), aby uruchomić format ER dla pojedynczego kwestionariusza ze strony **Konfiguracje**.

### <a name="review-the-execution-trace-of-the-second-run"></a>Przejrzyj ślad wykonania drugiego przejazdu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** rozwiń **Model kwestionariusza** i wybierz **Mapowanie kwestionariusza**.
3. W okienku akcji wybierz opcję **Projektant**.
4. Na stronie **Mapowanie modelu na źródło danych** wybierz **Projektant**.
5. Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.
6. W oknie dialogowym **Ustawienia wyników śladu wydajności** wybierz ślad, który został wygenerowany podczas ostatniego uruchomienia formatu.
7. Kliknij przycisk **OK**.
8. Na skróconej karcie **Szczegóły** wyfiltruj ścieżkę **Kwestionariusza**, która wskazuje na źródło danych **Kwestionariusza**.
9. Przejrzyj szczegóły zapytania do bazy danych, które zostało wygenerowane po wywołaniu źródła danych **Kwestionariusz**.

    Zauważ, że tylko te pola, które są wymagane do wypełnienia źródła danych, zostały pobrane w trybie uruchomieniowym z tabeli aplikacji `KMCollection`, gdy źródło danych **Kwestionariusz** zostało wywołane.

    > [!NOTE]
    > Niektóre pola, takie jak pola identyfikatora partycji, identyfikatora obszaru danych i identyfikatora rekordu, są automatycznie dodawane przez framework zarządzania danymi aplikacji Finanse.

    ![Przeglądanie szczegółów zapytania do bazy danych dla zaktualizowanego odwzorowania modelu na stronie Projektant odwzorowania modelu.](./media/er-reduce-fetched-fields-number-query2.png)

Możesz użyć tej techniki, aby zredukować liczbę pobieranych rekordów, gdy musisz zmniejszyć zużycie pamięci przez działające odwzorowanie modelu ER i format ER.

## <a name="limitations"></a>Ograniczenia

Kiedy ograniczasz liczbę pobieranych pól dla źródła danych typu *Rekordy tabeli*, nie możesz używać metod tabeli aplikacji, do której odwołuje się źródło danych, ponieważ metadane aplikacji nie dostarczają informacji o polach tabeli, które są wymagane do wywołania tych metod.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Mimo że polecenie **Automatyczne uzupełnianie** automatycznie dodaje pola, nie usuwa automatycznie wcześniej dodanych pól, nawet jeśli nie są one już używane w wiązaniach, formułach i źródłach danych odwzorowania edytowalnego modelu.

Po wybraniu opcji **Automatyczne uzupełnianie** program ER analizuje powiązania, formuły i źródła danych, które mapowanie modelu można edytować po otwarciu do edycji. Jeśli zmienisz wiązania, formuły i źródła danych edytowalnego odwzorowania modelu i chcesz użyć polecenia **Automatyczne uzupełnianie**, zamknij projektanta odwzorowania modelu, a następnie otwórz go ponownie, aby edytować swoje odwzorowanie modelu. 

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)
- [Rozwiązywanie problemów z wydajnością w konfiguracjach ER](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
