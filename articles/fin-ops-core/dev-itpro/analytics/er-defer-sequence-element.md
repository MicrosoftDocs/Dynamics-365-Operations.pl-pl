---
title: Odłóż wykonanie elementów sekwencji w formatach raportowania elektronicznego
description: W tym artykule wyjaśniono, jak odroczyć wykonanie elementu sekwencji w formacie modułu raportowanie elektroniczne (ER).
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: bb42da7b17713430c6143444d87d6fe187dd1124
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281851"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>Odłóż wykonanie elementów sekwencji w formatach ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Omówienie

Za pomocą projektanta operacji w strukturze [elektronicznego modułu sprawozdawczego](general-electronic-reporting.md) (ER) można [skonfigurować](tasks/er-format-configuration-2016-11.md) składnik formatu rozwiązania ER używanego do generowania dokumentów wychodzących w formacie tekstowym. Hierarchiczna struktura skonfigurowanego składnika formatu składa się z elementów formatu różnych typów. Te elementy formatu służą do wypełniania wygenerowanych dokumentów informacjami wymaganymi w czasie wykonywania. Domyślnie w przypadku uruchamiania formatu ER elementy formatu są uruchamiane w tej samej kolejności, w jakiej są przedstawione w hierarchii formatów: jeden po jednym — od góry do dołu. Jednak w czasie projektowania można zmienić kolejność wykonywania wszystkich elementów sekwencji skonfigurowanych składników formatu.

Włączając opcję <a name="DeferredSequenceExecution"></a>**Odroczone wykonanie** dla elementu formatu sekwencji w skonfigurowanym formacie, można odroczyć (przełożyć) wykonanie tego elementu. W takim przypadku element nie jest uruchamiany, dopóki nie zostaną uruchomione wszystkie pozostałe elementy jego obiektu nadrzędnego.

Wykonaj przykład z tego artykułu, aby dowiedzieć się więcej na temat tej funkcji.

## <a name="limitations"></a>Ograniczenia

Opcja **Odroczonego wykonania** jest obsługiwana tylko w przypadku elementów sekwencji skonfigurowanych dla formatu ER, które są używane do generowania **dokumentów wychodzących** w formacie tekstowym.

Opcja **Odroczonego wykonania** nie ma zastosowania w przypadku sekwencji skonfigurowanych jako przycięte sekwencje, w których maksymalna długość jest ograniczona.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>Przykład: Odłóż wykonanie elementu sekwencji w formatacie ER

Poniższe kroki wyjaśniają, jak użytkownik w roli Administratora systemu lub konsultanta funkcjonalnego lub raportu elektronicznego [(rola)](../sysadmin/tasks/assign-users-security-roles.md) może skonfigurować format ER, który zawiera element sekwencji, w którym kolejność wykonywania różni się od kolejności w hierarchii formatu.

Kroki można wykonać na danych przykładowej firmy **USMF** w aplikacji Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do firmy **USMF** wrozwiązaniu Finance dla jednej z następujących ról:

- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Jeśli nie zakończono jeszcze analizy przykładu, w artykule [Wstrzymaj wykonywanie elementów XML w formatach ER](er-defer-xml-element.md#Example), pobierz następujące [konfiguracje](general-electronic-reporting.md#Configuration) przykładowego rozwiązania ER.

| Opis zawartości            | Nazwa pliku |
|--------------------------------|-----------|
| Konfiguracja modelu danych ER    | [Model do nauki elementów odłożonych.version.1.xml](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| Sesja mapowania konfiguracji modelu ER | [Mapowanie do nauki elementów odłożonych.version.1.1.xml](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

Przed rozpoczęciem należy również pobrać i zapisać następującą konfigurację przykładowego rozwiązania ER.

| Opis zawartości     |Nazwa pliku |
|-------------------------|----------|
| ER format konfiguracji | [Format do nauki sekwencji odłożonych.version.1.1.xml](https://download.microsoft.com/download/0/f/5/0f55c341-8285-4d92-a46d-475d9a010927/Formattolearndeferredsequences.version.1.1.xml) |

### <a name="import-the-sample-er-configurations"></a>Importuj przykładowe konfiguracje formatu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. Na stronie **Konfiguracje**, jeśli konfiguracja **Model dla odłożonych elementów** nie jest dostępna w drzewie konfiguracji, zaimportuj konfigurację modelu danych ER:

    1. Wybierz **Wymiana**, a następnie wybierz opcję **Ładowanie z pliku XML**.
    2. Wybierz **Przeglądaj**, znajdź i wybierz plik **Model do nauki elementów odłożonych.xml**, a następnie kliknij **OK**.

4. Jeśli konfiguracja **Mapowanie do nauki odłożonych elementów** nie jest dostępna w drzewie konfiguracji, zaimportuj konfigurację mapowania ER:

    1. Wybierz **Wymiana**, a następnie wybierz opcję **Ładowanie z pliku XML**.
    2. Wybierz **Przeglądaj**, znajdź i wybierz plik **Mapowanie do nauki elementów odłożonych.1.1.xml**, a następnie kliknij **OK**.

5. Import konfiguracji formatu ER:

    1. Wybierz **Wymiana**, a następnie wybierz opcję **Ładowanie z pliku XML**.
    2. Wybierz **Przeglądaj**, znajdź i wybierz plik **Format do nauki sekwencji odłożonych.1.1.xml**, a następnie kliknij **OK**.

6. W drzewie konfiguracji rozwiń węzeł **Model, aby poznać odłożone elementy**.
7. Przejrzyj listę zaimportowanych konfiguracji systemu ER w drzewie konfiguracji.

    ![Zaimportowane konfiguracje ER na stronie konfiguracje.](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>Aktywuj dostawcę konfiguracji

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** sprawdź, czy [dostawca konfiguracji](general-electronic-reporting.md#Provider) dla przykładowej firmy Litware, Inc.(`http://www.litware.com`) jest wymieniony na liście i czy jest oznaczony jako akywny. Jeśli tego dostawcy konfiguracji nie ma na liście lub jeśli nie jest on oznaczony jako aktywny, wykonaj kroki opisane w artykule [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Przykładowa firma Litware Inc. na stronie konfiguracje lokalizacji.](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Przeglądanie zaimportowanego mapowania modelu

Przejrzyj ustawienia składnika mapowania modelu ER, które skonfigurowano w celu uzyskania dostępu do transakcji podatkowych i udostępnienie danych dostępnych na żądanie.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model do nauki elementów odłożonych**.
4. Wybierz konfigurację **Mapowanie, aby poznać elementy odłożone**.
5. Wybierz opcję **Projektant**, aby otworzyć listę mapowań.
6. Wybierz opcję **Projektant**, aby przejrzeć szczegóły mapowania.
7. Wybierz **Pokaż szczegóły**.
8. Przejrzyj źródła danych skonfigurowane pod kątem dostępu do transakcji podatkowych:

    - Źródło danych dla **Transakcji** w typie *Rekord tabeli* jest skonfigurowane do uzyskiwania dostępu do rekordów tabeli aplikacji **TaxTrans**.
    - Źródło danch **Załączników** w typie *Obliczane pole* jest skonfigurowane tak, aby zwracało wymagane kody załączników (**INV -10000349** i **INV -10000350**) jako listę rekordów.
    - W **Filtrowanym** źródle danych w typie *Obliczane pole* jest skonfigurowane do wyboru, od źródła danych **Transakcji**, po tylko transakcje podatkowych wymaganych załączników.
    - Pole **\$TaxAmount** typu *Pola obliczeniowego* jest dodawany do **Filtrowanego** źródła danych w celu udostępnienia wartości podatku o przeciwnym znaku.
    - **Zgrupowane** źródło danych dla typu *Grupuj według* jest skonfigurowane do grupowania odfiltrowanych transakcji podatkowych z **Filtrowanego** źródła danych.
    - Pole agregacji **TotalSum** w **Pogrupowanym** źródle danych jest skonfigurowane do podsumowywania wartości pola **\$TaxAmount** w **filtrowanym** źródle danych dla wszystkich przefiltrowanych transakcji podatkowych z tego źródła danych.

        ![Pole agregacji TotalSum na stronie parametrów edytowania „GroupBy”.](./media/ER-DeferredSequence-GroupByParameters.png)

9. Sprawdź, w jaki sposób skonfigurowane źródła danych są powiązane z modelem danych, i w jaki sposób uzyskują one dostęp do danych, aby udostępnić je w formacie ER:

    - **Filtrowane** źródło danych jest powiązane z polem **Data.list** modelu danych.
    - Pole **\$TaxAmount** **filtrowanego** źródła danych jest powiązane z polem **Data.List.Value** modelu danych.
    - Pole **TotalSum** **Pogrupowanego** źródła danych jest powiązane z polem **Data.Summary.Total** modelu danych.

    ![Modelowa strona projektanta mapowania.](./media/ER-DeferredSequence-ModelMapping.png)

10. Zamknij stronę **Konstruktor mapowania modeli** i **Mapowania modeli**.

### <a name="review-the-imported-format"></a>Przeglądanie zaimportowanego formatu

1. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz **Format, aby poznać konfigurację odroczonych sekwencji**.
2. Wybierz opcję **Projektant**, aby przejrzeć szczegóły formatu.
3. Wybierz **Pokaż szczegóły**.
4. Przejrzyj ustawienia składników formatu ER, które są skonfigurowane do generowania dokumentu wychodzącego w formacie tekstowym zawierającym szczegółowe informacje o transakcjach podatkowych:

    - Element sekwencji **Raport\\Wiersze** jest skonfigurowany tak, aby wypełnił dokument wychodzący z jednym wierszem generowanym na podstawie zagnieżdżonych elementów sekwencji(**nagłówek**, **rekord** i **podsumowanie**).

        ![Element formatu sekwencji wierszy i elementy zagnieżdżone na stronie Projektant formatów.](./media/ER-DeferredSequence-Format.png)

    - Element sekwencji formatu **Raport\\Wiersze\\Nagłówek** jest skonfigurowany do wypełniania dokumentu wychodzącego jednym wierszem nagłówka, który pokazuje datę i godzinę rozpoczęcia przetwarzania.
    - Element sekwencji formatu **Rapor\\Wiersze\\Rekord** jest skonfigurowany tak, aby wypełnił dokument wychodzący jednym wierszem, w którym są wyświetlane szczegóły poszczególnych transakcji podatkowych. Te transakcje podatkowe są oddzielane średnikiem.

        ![Element formatu sekwencji rekordów, który używa separatora jako ogranicznika.](./media/ER-DeferredSequence-Format1.png)

    - Element sekwencji formatu **Raport\\Wiersze\\Podsumowanie** jest skonfigurowany do wypełniania dokumentu wychodzącego jednym wierszem podsumowania, który zawiera sumę wartości podatku z przetworzonych transakcji podatkowych.

4. Na karcie **Mapowanie** przejrzyj następujące informacje:

    - Element **Raport\\Wiersze\\Nagłówek** nie musi być powiązany ze źródłem danych, aby wygenerować jeden wiersz w dokumencie wychodzącym.
    - Element **Prefix1** generuje symbole **P1** w celu wskazania, że dodawany wiersz jest wierszem nagłówka raportu.
    - Element **ExecutionDateTime** generuje datę i godzinę (w tym milisekundy), po dodaniu wiersza nagłówka.
    - Element **Raport\\Wiersze\\Rekord** jest powiązany z **model.Data.List** i umożliwia wygenerowanie pojedynczego wiersza dla każdego rekordu z listy powiązanej.
    - Element **Prefix2** generuje symbole **P2** w celu wskazania, że dodawany wiersz jest wierszem szczegółów podatkowych.
    - Element **TaxAmount** jest powiązany z **model.Data.List.Value** (wyświetlanym jako **\@.Value** w widoku ścieżki względnej), aby wygenerować wartość podatku dla bieżącej transakcji podatkowej.
    - Element **RunningTotal** jest symbolem zastępczym sumy wartości podatku. Obecnie ten element nie ma wyjścia, ponieważ nie skonfigurowano dla niego powiązania ani wartości domyślnej.
    - Element **ExecutionDateTime** generuje datę i godzinę (w tym milisekundy), po przetworzeniu bieżącej transakcji w tym raporcie.
    - Element **Raport\\Wiersze\\Podsumowanie** nie musi być powiązany ze źródłem danych, aby wygenerować jeden wiersz w dokumencie wychodzącym.
    - Element **Prefix3** generuje symbole **P3** w celu wskazania, że dodawany wiersz jest wierszem dot. wartości podatku.
    - Element **TotalTaxAmount** jest powiązany z **model.Data.Summary.Total**, aby wygenerować sumę wartości podatku przetworzonych transakcji podatkowych.
    - Element **ExecutionDateTime** generuje datę i godzinę (w tym milisekundy), po dodaniu wiersza podsumowania.

    ![Zakładka mapowania w Projektancie formatów.](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>Uruchamianie zaimportowanego formatu

1. Na stronie **Projektant formatów** wybierz opcję **Uruchom**.
2. Pobierz plik oferowany przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany przykładowy plik raportu.](./media/ER-DeferredSequence-Run.png)

Zauważ, że wiersz podsumowania 22 przedstawia sumę wartości podatku dla przetwarzanych transakcji. Ponieważ format jest skonfigurowany do używania powiązania **model.Data.Summary.Total**, aby zwrócić tę sumę, suma jest obliczana przez wywołanie agregacji **TotalSum** dla **zgrupowanego** źródła danych typu *GroupBy*, który korzysta z mapowania modelu. Aby można było obliczyć tę agregację, mapowanie modeli powtarza się dla wszystkich transakcji, które zostały wybrane w **filtrowanym** źródle danych. Porównując czasy wykonania wierszy 21 i 22, można ustalić, że obliczenie sumy zajęło 10 milisekund (ms). Porównując czasy wykonania wierszy 2 i 21, można ustalić, że wygenerowanie wszystkich linii wierszy transakcji zajęło 7 milisekund (ms). W związku z tym wymagana było 17 ms.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>Umożliwia zmodyfikowanie formatu w taki sposób, aby sumowanie było oparte na wygenerowanych wynikach

Jeśli wielkość transakcji jest znacznie większa niż objętość w bieżącym przykładzie, czas sumowania może zwiększyć się i spowodować problemy z wydajnością. Zmiana ustawienia formatu pozwala uniknąć tych problemów z wydajnością. Ponieważ są dostępne wartości podatku w celu uwzględnienia ich w generowanym raporcie, można użyć tych informacji do zsumowania wartości podatku. Aby uzyskać więcej informacji, zobacz [Konfigurowanie formatu w celu zliczania i sumowania](./tasks/er-format-counting-summing-1.md).

1. Na stronie **Projektant formatów** na karcie **Format** wybierz element pliku **Raportu** w drzewie formatu.
2. Ustawienie opcji **Zbierz szczegóły pliku wychodzącego** na wartość **Tak**. Teraz można skonfigurować ten format przy użyciu zawartości istniejącego raportu jako źródła danych, do którego można uzyskać dostęp za pomocą wbudowanych funkcji ER w kategorii [zbieranie danych](er-functions-category-data-collection.md).
3. Na karcie **Mapowanie** wybierz element sekwencji **Raport\\Wiersze**.
4. Skonfiguruj wyrażenie **nazwy zebranego klucza danych** jako `WsColumn`.
5. Skonfiguruj wyrażenie **wartości zebranego klucza danych** jako `WsRow`.

    ![Element sekwencji wierszy na stronie Projektant formatów.](./media/ER-DeferredSequence-Format3.png)

6. Wybierz element liczbow dla **Raport\\Wiersze\\Rekord\\TaxAmount**.
7. Skonfiguruj wyrażenie **nazwy zebranego klucza danych** jako `SummingAmountKey`.

    ![Element numeryczny TaxAmount na stronie Projektant formatów.](./media/ER-DeferredSequence-Format4.png)

    To ustawienie można uznać za wypełnienie arkusza wirtualnego, gdzie wartość komórki A1 jest dołączana do wartości podatku z każdej przetworzonej transakcji podatkowej.

8. Zaznacz element liczbowy **Raport\\Wiersze\\Rekord\\RunningTotal**, a następnie wybierz opcję **Edytuj formułę**.
9. Służy do konfigurowania wyrażenia `SUMIF(SummingAmountKey, WsColumn, WsRow)` przy użyciu wbudowanej funkcji ER [SUMIF](er-functions-datacollection-sumif.md).
10. Wybierz opcję **Zapisz**.

    ![Wyrażenie SUMIF.](./media/ER-DeferredSequence-FormulaDesigner.png)

11. Zamknij stronę **Projektowanie formuły**.
12. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
13. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik — zsumowane wartości podatku.](./media/ER-DeferredSequence-Run1.png)

    Wiersz 21 zawiera bieżącą sumę wartości podatku, które są obliczane dla wszystkich przetworzonych transakcji przy użyciu wygenerowanego wyniku jako źródła danych. To źródło danych rozpoczyna się od początku raportu i jest kontynuowane przez ostatnią transakcję podatkową. Wiersz 22 zawiera sumę wartości podatku dla wszystkich przetworzonych transakcji, które są obliczane w mapowaniu modelu przy użyciu źródła danych typu *GroupBy*. Zauważ, że te wartości są równe. Z tego względu można użyć sumowania danych wyjściowych zamiast **GroupBy**. Porównując czasy wykonania wierszy 2 i 21, można ustalić, że wygenerowanie i zsumowanie wszystkich linii wierszy transakcji zajęło 9 milisekund (ms). Z tego względu, jeśli chodzi o generowanie szczegółowych wierszy i sumowanie wartości podatku, zmodyfikowany format jest o około dwa razy szybszy niż format oryginalny.

14. Zaznacz element liczbowy **Raport\\Wiersze\\Podsumowanie\\TotalTaxAmount**, a następnie wybierz opcję **Edytuj formułę**.
15. Umożliwia wprowadzenie wyrażenia `SUMIF(SummingAmountKey, WsColumn, WsRow)` zamiast istniejącego wyrażenia.
16. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
17. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik z edytowaną formułą.](./media/ER-DeferredSequence-Run2.png)

    Należy zauważyć, że suma bieżąca wartości podatku w ostatnim wierszu szczegółów transakcji jest teraz równa sumie w wierszu podsumowania.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Umożliwia umieszczenie wartości sumowania na podstawie danych wyjściowych w nagłówku raportu

Jeśli na przykład w nagłówku raportu trzeba przedstawić sumę wartości podatku, można zmodyfikować format.

1. Na stronie **Projektant formatów** na karcie **Format** wybierz sekwencję elementu **Raport\\Wiersze\\Podsumowanie**.
2. Wybierz **Przenieś w górę**.
3. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
4. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik do sumowania w nagłówku raportu.](./media/ER-DeferredSequence-Run3.png)

    Należy zauważyć, że suma wartości podatku w wierszu podsumowania 2 jest teraz równa 0 (zero), ponieważ ta suma jest teraz obliczana na podstawie wygenerowanych danych wyjściowych. Po wygenerowaniu wiersza 2 wygenerowane dane wyjściowe nie zawierają jeszcze wierszy z informacjami o transakcjach. Można skonfigurować ten format, aby odroczyć wykonanie elementu sekwencji **Raport\\Wiersze\\Podsumowanie**, dopóki sekwencja **Raport\\Wiersze\\Rekord** nie zostanie uruchomiony dla wszystkich wierszy raportu dla transakcji podatkowych.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>Odłóż wykonanie sekwencji podsumowania, tak aby była używana obliczona suma

1. Na stronie **Projektant formatów** na karcie **Format** wybierz sekwencję elementu **Raport\\Wiersze\\Podsumowanie**.
2. Ustaw wartość opcji **Odłożone uruchomienie** na **Tak**.

    ![Opcja odroczonego wykonania elementu sekwencji podsumowania na stronie Projektant formatów.](./media/ER-DeferredSequence-Format5.png)

3. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
4. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik — odroczone wykonanie.](./media/ER-DeferredSequence-Run4.png)

    Element sekwencji **Raport\\Wiersze\\Podsumowanie** jest teraz uruchamiany tylko po uruchomieniu wszystkich pozostałych elementów zagnieżdżonych pod jego elementem **Raport\\Wiersze**. Dlatego jest uruchamiany po uruchomieniu elementu sekwencji **Raport\\Wiersze\\Rekord** dla wszystkich transakcji podatkowych źródła danych **model.Data.List**. Czasy wykonania wierszy 1, 2 i 3 oraz ostatni wiersz, 22, odsłoń ten fakt.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie formatu do inwentaryzacji i sumowania](./tasks/er-format-counting-summing-1.md)
- [Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)
- [Odłóż wykonanie elementów sekwencji XML w formatach ER](er-defer-xml-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
