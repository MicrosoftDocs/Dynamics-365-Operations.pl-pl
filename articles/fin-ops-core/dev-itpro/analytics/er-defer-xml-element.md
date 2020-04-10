---
title: Odłóż wykonanie elementów sekwencji XML w formatach ER
description: W tym temacie wyjaśniono, jak odroczyć wykonanie elementu XML w formacie modułu raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58381f491cda199d77e555e5d3da04714b6a5f8f
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138930"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>Odłóż wykonanie elementów sekwencji XML w formatach ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Omówienie

Za pomocą projektanta operacji w strukturze [elektronicznego modułu sprawozdawczego (ER)](general-electronic-reporting.md) można [skonfigurować](./tasks/er-format-configuration-2016-11.md) [składnik formatu](general-electronic-reporting.md#FormatComponentOutbound) rozwiązania ER używanego do generowania dokumentów wychodzących w formacie XML. Hierarchiczna struktura skonfigurowanego składnika formatu składa się z elementów formatu różnych typów. Te elementy formatu służą do wypełniania wygenerowanych dokumentów informacjami wymaganymi w czasie wykonywania. Domyślnie w przypadku uruchamiania formatu ER elementy formatu są uruchamiane w tej samej kolejności, w jakiej są przedstawione w hierarchii formatów: jeden po jednym — od góry do dołu. Jednak w czasie projektowania można zmienić kolejność wykonywania wszystkich elementów XML skonfigurowanych składników formatu.

Włączając opcję <a name="DeferredXmlElementExecution"></a>**Odroczone wykonanie** dla elementu XML w skonfigurowanym formacie, można odroczyć (przełożyć) wykonanie tego elementu. W takim przypadku element nie jest uruchamiany, dopóki nie zostaną uruchomione wszystkie pozostałe elementy jego obiektu nadrzędnego.

Wykonaj przykład z tego tematu, aby dowiedzieć się więcej na temat tej funkcji.

## <a name="limitations"></a>Ograniczenia

Opcja **Odroczonego wykonania** jest obsługiwana tylko w przypadku elementów XML skonfigurowanych dla formatu ER, które są używane do generowania **dokumentów wychodzących** w formacie XML.

**Opcja odroczonego wykonania** jest obsługiwana tylko dla elementów XML, które znajdują się tylko w jednym innym elemencie XML. Dlatego nie dotyczy elementów XML znajdujących się w innych typach elementów formatu (np. w elemencie **sekwencji XML**).

Opcja **Odroczonego wykonania** nie jest obsługiwana dla elementów XML, które znajdują się w elemencie formatu **Common\\File**, gdy opcja **podzielonego pliku** jest ustawiona na **Tak**. Po więcej informacji nt. dzielenia plików XML, zobacz [Dzielenie plików XML na podstawie rozmiaru pliku i ilości elementu zawartości.](er-split-files.md).

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>Przykład: Odłóż wykonanie elementu XML w formatacie ER

Poniższe kroki wyjaśniają, jak użytkownik w roli Administratora systemu lub konsultanta funkcjonalnego lub raportu elektronicznego [(rola)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) może skonfigurować format XML, który zawiera element sekwencji, w którym kolejność wykonywania różni się od kolejności w hierarchii formatu.

Kroki można wykonać na danych przykładowej firmy **USMF** w Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do firmy **USMF** wrozwiązaniu Finance dla jednej z następujących ról:

- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Jeśli nie zakończono jeszcze analizy przykładu, w sekcji [Wstrzymaj wykonywanie elementów sekwencji w formatach ER](er-defer-sequence-element.md#Example), pobierz następujące [konfiguracje](general-electronic-reporting.md#Configuration) przykładowego rozwiązania ER.

| Opis zawartości            | Nazwa pliku |
|--------------------------------|-----------|
| Konfiguracja modelu danych ER    | [Model do nauki elementów odłożonych.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Sesja mapowania konfiguracji modelu ER | [Mapowanie do nauki elementów odłożonych.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Przed rozpoczęciem należy również pobrać i zapisać następującą konfigurację przykładowego rozwiązania ER na maszynę lokalną.

| Opis zawartości     | Nazwa pliku |
|-------------------------|-----------|
| ER format konfiguracji | [Format do nauki odłożonych elementów XML.version.1.1.xml.](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

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
    2. Wybierz **Przeglądaj**, znajdź i wybierz plik **Format do nauki odłożonych elementów XML.1.1.xml**, a następnie kliknij **OK**.

6. W drzewie konfiguracji rozwiń węzeł **Model, aby poznać odłożone elementy**.
7. Przejrzyj listę zaimportowanych konfiguracji systemu ER w drzewie konfiguracji.

    ![Zaimportowane konfiguracje ER na stronie konfiguracje](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Aktywuj dostawcę konfiguracji

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** sprawdź, czy [dostawca konfiguracji](general-electronic-reporting.md#Provider) dla przykładowej firmy Litware, Inc.(`http://www.litware.com`) jest wymieniony na liście i czy jest oznaczony jako akywny. Jeśli tego dostawcy konfiguracji nie ma na liście lub jeśli nie jest on oznaczony jako aktywny, wykonaj kroki opisane w temacie [Tworzenia dostawcy konfiguracji i zaznaczanie go jako aktywny](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Przykładowa firma Litware Inc. na stronie konfiguracje lokalizacji](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

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

        ![Pole agregacji TotalSum na stronie parametrów edytowania „GroupBy”](./media/ER-DeferredXml-GroupByParameters.png)

9. Sprawdź, w jaki sposób skonfigurowane źródła danych są powiązane z modelem danych, i w jaki sposób uzyskują one dostęp do danych, aby udostępnić je w formacie ER:

    - **Filtrowane** źródło danych jest powiązane z polem **Data.list** modelu danych.
    - Pole **\$TaxAmount** **filtrowanego** źródła danych jest powiązane z polem **Data.List.Value** modelu danych.
    - Pole **TotalSum** **Pogrupowanego** źródła danych jest powiązane z polem **Data.Summary.Total** modelu danych.

    ![Modelowa strona projektanta mapowania](./media/ER-DeferredXml-ModelMapping.png)

10. Zamknij stronę **Konstruktor mapowania modeli** i **Mapowania modeli**.

### <a name="review-the-imported-format"></a>Przeglądanie zaimportowanego formatu

1. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz **Format, aby poznać konfigurację odroczonych elementów XML**.
2. Wybierz opcję **Projektant**, aby przejrzeć szczegóły formatu.
3. Wybierz **Pokaż szczegóły**.
4. Przejrzyj ustawienia składników formatu ER, które są skonfigurowane do generowania dokumentu wychodzącego w formacie XML zawierającym szczegółowe informacje o transakcjach podatkowych:

    - Element XML **Raport\\Wiadomość** jest skonfigurowany tak, aby wypełnił dokument wychodzący z jednym węzłem zawierającym zagnieżdżone elementy XML (**Nagłówek**, **Rekord** oraz **Podsumowanie**).
    - Element XML **Raport\\Wiadomości\\Nagłówek** jest skonfigurowany do wypełniania dokumentu wychodzącego jednym węzłem nagłówka, który pokazuje datę i godzinę rozpoczęcia przetwarzania.
    - Element sekwencji formatu **Raport\\Wiadomość\\Rekord** jest skonfigurowany tak, aby wypełnił dokument wychodzący jednym węzłem, w którym są wyświetlane szczegóły jednej transakcji podatkowejf.
    - Element XML **Raport\\Wiadomość\\Podsumowanie** jest skonfigurowany do wypełniania dokumentu wychodzącego jednym węzłem, który zawiera sumę wartości podatku z przetworzonych transakcji podatkowych.

    ![Element XML i elementy zagnieżdżone na stronie Projektant formatów](./media/ER-DeferredXml-Format.png)

5. Na karcie **Mapowanie** przejrzyj następujące informacje:

    - Element **Raport\\Wiadomość\\Nagłówek** nie musi być powiązany ze źródłem danych, aby wygenerować jeden wiersz w dokumencie wychodzącym.
    - Atrybut **ExecutionDateTime** generuje datę i godzinę (w tym milisekundy), po dodaniu węzła nagłówka.
    - Element **Raport\\Wiadomość\\Rekord** jest powiązany z **model.Data.List** i umożliwia wygenerowanie pojedynczego węzła rekordów dla każdego rekordu z listy powiązanej.
    - Atrybut **TaxAmount** jest powiązany z **model.Data.List.Value** (wyświetlanym jako **\@.Value** w widoku ścieżki względnej), aby wygenerować wartość podatku dla bieżącej transakcji podatkowej.
    - Atrybut **RunningTotal** jest symbolem zastępczym sumy wartości podatku. Obecnie ten atrybut nie ma wyjścia, ponieważ nie skonfigurowano dla niego powiązania ani wartości domyślnej.
    - Atrybut **ExecutionDateTime** generuje datę i godzinę (w tym milisekundy), po przetworzeniu bieżącej transakcji w tym raporcie.
    - Element **Raport\\Wiadomość\\Podsumowanie** nie musi być powiązany ze źródłem danych, aby wygenerować jeden węzeł w dokumencie wychodzącym.
    - Atrybut **TotalTaxAmount** jest powiązany z **model.Data.Summary.Total**, aby wygenerować sumę wartości podatku przetworzonych transakcji podatkowych.
    - Atrybut **ExecutionDateTime** generuje datę i godzinę (w tym milisekundy), po dodaniu węzła podsumowania.

    ![Zakłądka mapowania w Projektancie formatów](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Uruchamianie zaimportowanego formatu

1. Na stronie **Projektant formatów** wybierz opcję **Uruchom**.
2. Pobierz plik oferowany przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik](./media/ER-DeferredXml-Run.png)

Zauważ, że węzeł podsumowania przedstawia sumę wartości podatku dla przetwarzanych transakcji. Ponieważ format jest skonfigurowany do używania powiązania **model.Data.Summary.Total**, aby zwrócić tę sumę, suma jest obliczana przez wywołanie agregacji **TotalSum** dla **zgrupowanego** źródła danych typu *GroupBy*, który korzysta z mapowania modelu. Aby można było obliczyć tę agregację, mapowanie modeli powtarza się dla wszystkich transakcji, które zostały wybrane w **filtrowanym** źródle danych. Porównując czasy wykonania węzła podsumowania z ostatnim węzłem rekordu, można ustalić, że obliczenie sumy trwało 12 milisekund (ms). Porównując czasy wykonania pierwszego i ostatniego węzła rekordów, można ustalić, że wygenerowanie węzłów rekordów zajęło 9 milisekund (ms). W związku z tym wymagana było 21 ms.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Umożliwia zmodyfikowanie formatu w taki sposób, aby kalkulacja była oparte na wygenerowanych wynikach

Jeśli wielkość transakcji jest znacznie większa niż objętość w bieżącym przykładzie, czas kalkulacji może zwiększyć się i spowodować problemy z wydajnością. Zmiana ustawienia formatu pozwala uniknąć tych problemów z wydajnością. Ponieważ są dostępne wartości podatku w celu uwzględnienia ich w generowanym raporcie, można użyć tych informacji do kalkulacji wartości podatku. Aby uzyskać więcej informacji, zobacz [Konfigurowanie formatu w celu zliczania i sumowania](./tasks/er-format-counting-summing-1.md).

1. Na stronie **Projektant formatów** na karcie **Format** wybierz element pliku **Raportu** w drzewie formatu.
2. Ustawienie opcji **Zbierz szczegóły pliku wychodzącego** na wartość **Tak**. Teraz można skonfigurować ten format przy użyciu zawartości generowanego raportu jako źródła danych, do którego można uzyskać dostęp za pomocą wbudowanych funkcji ER w kategorii [zbieranie danych](er-functions-category-data-collection.md).
3. Na karcie **Mapowanie** wybierz element XML **Raport\\Wiadomość\\Rekord**.
4. Skonfiguruj wyrażenie **nazwy zebranego klucza danych** jako `WsColumn`.
5. Skonfiguruj wyrażenie **wartości zebranego klucza danych** jako `WsRow`.

    ![Rekord XML na stronie Projektant formatów](./media/ER-DeferredXml-Format3.png)

6. Wybierz atrybut **Raport\\Wiadomość\\Rekord\\TaxAmount**.
7. Skonfiguruj wyrażenie **nazwy zebranego klucza danych** jako `SummingAmountKey`.

    ![Atrybut TaxAmount na stronie Projektant formatów](./media/ER-DeferredXml-Format4.png)

    To ustawienie można uznać za wypełnienie arkusza wirtualnego, gdzie wartość komórki A1 jest dołączana do wartości podatku z każdej przetworzonej transakcji podatkowej.

8. Zaznacz atrybut **Raport\\Wiadomość\\Rekord\\RunningTotal**, a następnie wybierz opcję **Edytuj formułę**.
9. Skonfiguruj wyrażenie `SUMIF(SummingAmountKey, WsColumn, WsRow)` używając wbudowanej funckji ER [SUMIF](er-functions-datacollection-sumif.md), a następnie wybierz **Zapisz**.

    ![Wyrażenie SUMIF](./media/ER-DeferredXml-FormulaDesigner.png)

10. Zamknij stronę **Projektowanie formuły**.
11. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
12. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik](./media/ER-DeferredXml-Run1.png)

    Ostatni węzeł rekordów zawiera bieżącą sumę wartości podatku, które są obliczane dla wszystkich przetworzonych transakcji przy użyciu wygenerowanego wyniku jako źródła danych. To źródło danych rozpoczyna się od początku raportu i jest kontynuowane przez ostatnią transakcję podatkową. Węzeł podsumowania zawiera sumę wartości podatku dla wszystkich przetworzonych transakcji, które są obliczane w mapowaniu modelu przy użyciu źródła danych typu *GroupBy*. Zauważ, że te wartości są równe. Z tego względu można użyć sumowania danych wyjściowych zamiast **GroupBy**. Porównując czasy wykonania pierwszego węzła rekordów i węzła podsumowania, można ustalić, że wygenerowanie wszystkich rekordów i sumowanie zajęło 11 milisekund (ms). Z tego względu, jeśli chodzi o generowanie węzłów rekordów i sumowanie wartości podatku, zmodyfikowany format jest o około dwa razy szybszy niż format oryginalny.

13. Zaznacz atrybut **Raport\\Wiadomość\\Pdosumowanie\\TotalTaxAmountl**, a następnie wybierz opcję **Edytuj formułę**.
14. Umożliwia wprowadzenie wyrażenia `SUMIF(SummingAmountKey, WsColumn, WsRow)` zamiast istniejącego wyrażenia.
15. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
16. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik](./media/ER-DeferredXml-Run2.png)

    Należy zauważyć, że suma bieżąca wartości podatku w ostatnim węźle rekordów jest teraz równa sumie w węźle podsumowania.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Umożliwia umieszczenie wartości sumowania na podstawie danych wyjściowych w nagłówku raportu

Jeśli na przykład w nagłówku raportu trzeba przedstawić sumę wartości podatku, można zmodyfikować format.

1. Na stronie **Projektant formatów** na karcie **Format** wybierz element XML **Raport\\Wiadomość\\Podsumowanie**.
2. Wybierz **Przenieś w górę**.
3. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
4. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik](./media/ER-DeferredXml-Run3.png)

    Należy zauważyć, że suma wartości podatku w węźle jest teraz równa 0 (zero), ponieważ ta suma jest teraz obliczana na podstawie wygenerowanych danych wyjściowych. Po wygenerowaniu pierwszego węzła rekordów wygenerowane dane wyjściowe nie zawierają jeszcze węzłów rekordów z informacjami o transakcjach. Można skonfigurować ten format, aby odroczyć wykonanie elementu sekwencji **Raport\\Wiadomość\\Podsumowanie**, dopóki sekwencja **Raport\\Wiadomość\\Rekord** nie zostanie uruchomiony dla wszystkich wierszy raportu dla transakcji podatkowych.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Odłóż wykonanie podsumowania elementu XML, tak aby była używana obliczona suma

1. Na stronie **Projektant formatów** na karcie **Format** wybierz element XML **Raport\\Wiadomość\\Podsumowanie**.
2. Ustaw wartość opcji **Odłożone uruchomienie** na **Tak**.

    ![Opcja odroczonego wykonania podsumowania elementu XML na stronie Projektant formatów](./media/ER-DeferredXml-Format5.png)

3. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
4. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik](./media/ER-DeferredXml-Run4.png)

    Element sekwencji **Raport\\Wiadomość\\Podsumowanie** jest teraz uruchamiany tylko po uruchomieniu wszystkich pozostałych elementów zagnieżdżonych pod jego elementem **Raport\\Wiadomość**. Dlatego jest uruchamiany po uruchomieniu elementu sekwencji **Raport\\Wiadomość\\Rekord** dla wszystkich transakcji podatkowych źródła danych **model.Data.List**. Czasy wykonania pierwszego i ostatniego rekordu oraz węzły nagłówka i podsumowania ujawniają ten fakt.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie formatu do inwentaryzacji i sumowania](./tasks/er-format-counting-summing-1.md)
- [Śledzenie wykonywania formatu ER w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)
- [Odłóż wykonanie elementów sekwencji w formatach ER](er-defer-sequence-element.md#Example)
