---
title: Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi
description: Ten temat zawiera informacje dotyczące sposobu porównywania wyników generowanych raportów ER z wartości raportu bazowego.
author: NickSelin
manager: AnnBe
ms.date: 06/17/2019
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
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1643e7fb3128faf6ad638d4cdad313b3667463b1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181687"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi

[!include[banner](../includes/banner.md)]

Można śledzić wyniki raportów elektronicznych (ER), dzięki którym są generowane wychodzące dokumenty elektroniczne. Po włączeniu generowania śledzenia (parametr użytkownika ER **Uruchom w trybie debugowania**), nowy rekord śledzenia jest generowany w dzienniku formatu ER po każdym uruchomieniu raportu ER. Następujące informacje są przechowywane w każdym śledzeniu, które jest generowane:

- Wszystkie ostrzeżenia wygenerowane przez reguły weryfikacji
- Wszystkie błędy wygenerowane przez reguły weryfikacji
- Wszystkie wygenerowane pliki przechowywane jako załączniki rekordu śledzenia

Można przechowywać pojedyncze podstawowe pliki aplikacji dla dowolnego formatu ER. Pliki są traktowane jako bazowe, jeśli opisują oczekiwane wyniki generowanych raportów. Jeśli plik podstawowy jest dostępny dla formatu ER, który jest uruchomiony przy włączonej funkcji generowania śladu, sklep śledzi nie tylko szczegóły wspomniane wcześniej, ale również wynik porównania wygenerowanego dokumentu elektronicznego z plikiem podstawowym. Za pomocą jednego kliknięcia można umieścić wygenerowany dokument elektroniczny i jego plik podstawowy w jednym pliku zip. Następnie można przeprowadzić szczegółowe porównanie za pomocą narzędzi zewnętrznych, takich jak WinDiff.

Można ocenić śledzenie w celu przeanalizowania, czy wygenerowane dokumenty elektroniczne mają oczekiwaną zawartość. Można przeprowadzić tę ewaluację w środowisku testowania akceptacji użytkownika (UAT) po zmianie kodu podstawowego (na przykład jeśli zostanie przeniesiony do nowej instancji aplikacji, zainstalowane będą pakiety poprawek albo po wdrożeniu modyfikacji kodu). W ten sposób można uzyskać pewność, że ocena nie wpłynie na wykonywanie używanych raportów modułu ER. W wielu raportach modułu ER ocena może zostać przeprowadzona w trybie nienadzorowanym.

Aby dowiedzieć się więcej o tej funkcji, należy odtworzyć przewodniki zadań **ER Generowanie raportów i porównanie wyników (część 1)** i **ER Generowanie raportów i porównanie wyników (część 2)**, które wchodzą w skład procesu biznesowego **7.5.4.3 Informatyczne usługi lub rozwiązania testowe (10679)** i można je pobrać z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Te wskazówki zadania przeprowadzą Cię przez proces konfigurowania struktury ER w celu użycia plików wyjściowych do oceny wygenerowanych dokumentów elektronicznych.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Przykład: śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi

W tej procedurze opisano sposób konfigurowania struktury ER w celu zbierania informacji na temat wykonania formatów w module ER, a następnie oceny wyników tych operacji. W ramach tej oceny wygenerowane dokumenty są porównywane z ich plikami bazowymi. W tym przykładzie utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Ta procedura jest przeznaczona dla użytkowników z przypisaną rola Administrator systemu lub Deweloper raportowania elektronicznego. Kroki te można wykonać przy użyciu dowolnego zestawu danych.

Aby wykonać kroki w tym przykładzie, należy najpierw wykonać kroki w [„Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** sprawdź, czy dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest wymieniony na liście i czy jest oznaczony jako **aktywny**. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki w [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-document-management-parameters"></a>Konfigurowanie parametrów zarządzania dokumentami

1. Przejdź do **dokumentów zarządzania**\> **dokumentów administrowania organizacją**\> **Typ dokumentów** i utwórz nowy typ dokumentu, na którym będą przechowywane pliki bazowe.
2. W polu **klasy** wybierz **Dołącz plik**.
3. W polu **grupa** wybierz **Plik**.

![Strona typów dokumentów](media/GER-BaselineSample-SetupDocumentType.PNG "Zrzut ekranu strony typu dokumentów")

> [!NOTE]
> Nowy typ dokumentu o tej samej nazwie musi być skonfigurowany dla każdego zbioru danych, w którym ma być używana funkcja odniesienia do systemu ER.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Skonfiguruj Parametry modułu ER, aby rozpocząć korzystanie z funkcji podstawy

1. W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.

    ![Obszar roboczy raportowania elektronicznego](media/GER-BaselineSample-ERWorkspace.PNG "Zrzut ekranu obszaru roboczego raportowania elektronicznego")

2. Na karcie **załączniki**, w polu wiersz **bazowy**, wprowadź lub wybierz typ dokumentu, który właśnie utworzono.

    ![Karta załączniki w obszarze zrzut ekranu strony parametry](media/GER-BaselineSample-ERParameters.PNG "raportowania elektronicznego na stronie parametry raportowania elektronicznego")

3. Wybierz **Zapisz**, a następnie zamknij stronę **Parametry raportowania elektronicznego**.

### <a name="add-a-new-er-model-configuration"></a>Dodawanie nowej konfiguracji modelu ER

1. W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
2. W okienku akcji wybierz **Utwórz konfigurację**.
3. W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **model, aby uzyskać informacje o modelach bazowych modelu ER**.
4. Wybierz opcję **Utwórz konfigurację**, aby potwierdzić utworzenie nowego wpisu modelu danych ER.

![Okno dialogowe listy rozwijanej Tworzenie konfiguracji](media/GER-BaselineSample-ModelAdd.PNG "zrzut ekranu okna dialogowego Utwórz konfigurację")

### <a name="design-a-data-model"></a>Projektowanie modelu danych

1. Na stronie **konfiguracje**, w okienku akcji wybierz opcję **Projektant**.
2. Wybierz pozycję **Nowy**.
3. W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **Element główny**.
4. Wybierz opcję **Dodaj**.
5. Wybierz **Odwołanie do elementu głównego**.
6. Zaznacz element **Zapisz** i kliknij przycisk **OK**.
7. Zamknij stronę **Projektant modelu**.
8. Wybierz opcję **Zmień stan**.
9. Zaznacz element **Zakończ** i kliknij przycisk **OK**.

![Strona konfiguracji](media/GER-BaselineSample-ModelComplete.PNG "Zrzut ekranu strony konfiguracji")

### <a name="add-a-new-er-format-configuration"></a>Dodawanie nowej konfiguracji formatu ER

1. Na stronie **konfiguracje**, w okienku akcji wybierz opcję **Utwórz konfigurację**.
2. W oknie dialogowym listy rozwijanej w polu **Nowa** grupa pól wybierz opcję **format oparty na modelu uzyskiwania informacji o modelach bazowych ER**.
3. W polu **nazwa** wprowadź **format, aby uzyskać informacje o planach bazowych modelu ER**.
4. Wybierz opcję **Utwórz konfigurację**, aby potwierdzić utworzenie nowego wpisu formatu ER.

![Okno dialogowe listy rozwijanej Utwórz konfigurację](media/GER-BaselineSample-FormatAdd.PNG "zrzut ekranu okna dialogowego Utwórz konfigurację")

### <a name="design-a-format"></a>Projektowanie formatu

W tym przykładzie utworzysz prosty format ER, który będzie generował dokumenty XML.

1. Na stronie **konfiguracje**, w okienku akcji wybierz opcję **Projektant**.
2. Wybierz **Dodaj element główny**.
2. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W drzewie zaznacz element **Wspólne\\Plik**.
    2. W polu **Nazwa** wprowadź nazwę **Dane wyjściowe**.
    3. Kliknij przycisk **OK**.

3. Wybierz opcję **Dodaj**.
4. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W drzewie zaznacz element **XML\\Element**.
    2. W polu **Nazwa** wpisz **Dokument**.
    3. Kliknij przycisk **OK**.

5. W widoku drzewa wybierz **Wyjście\\Dokument**.
6. Wybierz opcję **Dodaj**.
7. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W drzewie zaznacz element **XML\\Atrybut**.
    2. Wprowadź **nazwę** w polu, wpisz **ID**.
    3. Kliknij przycisk **OK**.

    ![Strona projektant formatu](media/GER-BaselineSample-FormatLayoutDesign.PNG "Zrzut strony strony Projektant formatów")

8. Na karcie **mapowanie** wybierz opcję **Usuń**.
9. Wybierz **Dodaj element główny**.
10. W oknie dialogowym rozwijanym w drzewie wybierz **Ogólne\\Parametr wprowadzany przez użytkownika**, a następnie wykonaj następujące kroki:

    1. Wprowadź **nazwę** w polu, wpisz **ID**.
    2. W polu **Etykieta** wejdź do **Wpisz ID**.
    3. Kliknij przycisk **OK**.

11. W drzewie wybierz **Wyjście\\Dokument\\ID**.
12. Zaznacz element **Powiąż** i kliknij przycisk **Zapisz**.

![Strona projektant formatu](media/GER-BaselineSample-FormatMappingDesign.PNG "Zrzut strony strony Projektant formatów")

Zgodnie z zaprojektowaną strukturą, skonfigurowany format będzie generował plik XML. Ten kod XML zawiera **element główny** z atrybutem **ID**, który jest ustawiany na wartość wprowadzaną przez użytkownika w oknie dialogowym programu ER.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Generowanie nowego pliku odniesienia dla zaprojektowanego formatu ER

1. Na stronie **konfiguracje** w skróconej karcie **wersje** wybierz opcję **Uruchom**.
2. W polu **Wpisz ID** wpisz **1**.
3. Kliknij przycisk **OK**.

    ![Okno dialogowe Parametry raportu elektronicznego](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "zrzut ekranu okna dialogowego Parametry raportu elektronicznego")

4. Umożliwia zapisanie lokalnej kopii pliku **out.Admin.xml**, dzięki czemu można go później wykorzystać jako plan bazowy dla tego formatu ER.

    ![Powiadomienie dotyczące wygenerowanego pliku na stronie](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "konfiguracja zrzutu ekranu powiadomienia o wygenerowanym pliku na stronie konfiguracje")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Skonfiguruj Parametry modułu ER, aby rozpocząć korzystanie z funkcji plików bazowych

1. na stronie **konfiguracje** na panelu akcji na karcie **Konfiguracje** wybierz **Parametry użytkownika**.
2. Ustaw opcję **Uruchom w trybie debugowania** jako **tak**.
3. Kliknij przycisk **OK**.

![Okno dialogowe Parametry użytkownika](media/GER-BaselineSample-ERUserParameters.PNG "zrzut ekranu okna dialogowego Parametry użytkownika")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Dodawanie nowego pliku odniesienia dla zaprojektowanego formatu ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. W okienku akcji kliknij pozycję **Pliki bazowe**.

    ![Przycisk Pliki bazowe na stronie Konfiguracje](media/GER-BaselineSample-OpenBaselinePage.PNG "zrzut ekranu przycisku plików bazowych na stronie Konfiguracje")

3. W okienku akcji wybierz opcję **Nowy**.
4. Wybierz **format, aby uzyskać informacje o plikach bazowych ER**, który został zaprojektowany wcześniej.
5. Wybierz opcję **Zapisz**.

![Strona elektronicznego raportowania formatu plików bazowych](media/GER-BaselineSample-AddBaseline.PNG "Zrzut ekranu strony elektronicznego raportowania formatu plików bazowych")

Pliki bazowe zostaną dodane do **formatu w celu poznania się z formatem plików bazowych ER**.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Skonfiguruj regułę bazową dla dodanego planu bazowego

1. Na stronie **Elektronicznego raportowania formatów plików bazowych** w okienku akcji wybierz przycisk **załączniki** (symbol spinacza).
2. W okienku akcji wybierz **Nowy** \> **Plik**. W parametrach modułu ER **Plik** dokumentu powinien być poprzednio wybrany jako typ dokumentu używany do przechowywania plików bazowych.
3. Wybierz opcję **Przeglądaj**, a następnie wybierz plik **out.admin.xml**, który został wygenerowany w przypadku wcześniejszego uruchomienia skonfigurowanego formatu ER

    ![Strona załączników](media/GER-BaselineSample-UploadBaselineFile.PNG "Zrzut ekranu strony załączników")

4. Zamknij stronę **Załączniki**.
5. W skróconej karcie **Plików bazowych** wybierz opcję **nowy**.
6. W polu **Nazwa** wpisz **Linia Bazowa 1**.
7. W polu **nazwa składnika pliku** wprowadź lub wybierz opcję **wyjście**. Ta wartość wskazuje, że skonfigurowany plan bazowy będzie porównywany z plikiem generowanym za pomocą elementu formatu **Wyjście**.
8. W polu **Maska nazwy pliku** wpisz **\*.xml**.

    > [!NOTE]
    > Można zdefiniować maskę nazwy pliku. W przypadku zdefiniowania maski nazw plików rekord bazowy zostanie użyty do oceny wygenerowanego wydruku tylko wtedy, gdy wygenerowana nazwa pliku wyjściowego spełnia tę maskę.

9. Jeśli skonfigurowany plik bazowy powinien być używany tylko w przypadku, **formatu do zapoznania się z plikami bazowymi ER**, użytkownicy zalogowani do określonych firm wybrać te firmy w polu **Firmy**.
10. W polu **plan bazowy** wprowadź lub wybierz załącznik **out.Admin**.
11. Wybierz opcję **Zapisz**.

![Strona elektronicznego raportowania formatu plików bazowych](media/GER-BaselineSample-SetupBaselineLine.PNG "Zrzut ekranu strony elektronicznego raportowania formatu plików bazowych")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Uruchom zaprojektowany format ER i przejrzyj dziennik, aby przeanalizować wyniki

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. W drzewie rozwiń **Model, aby uzyskać informacje o planach bazowych modelu er**, a następnie wybierz **Model w celu poznania się z formatem bazowym modelu ER\\Format w celu poznania się z formatem bazowym modelu ER**.
3. Na skróconej karcie **Wersje** wybierz **Uruchom**.
4. W polu **Wpisz ID** wpisz **1**.
5. Kliknij przycisk **OK**.
6. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Dzienniki debugowania konfiguracji**.

    ![Strona elektrownicznego raportowania dzienników przebiegu](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Zrzut ekranu strony elektrownicznego raportowania dzienników przebiegu")

    > [!NOTE]
    > Dziennik wykonania zawiera informacje o wynikach porównania wygenerowanego pliku ze skonfigurowaną linią bazową. W tym przykładzie dziennik wskazuje, że wygenerowany plik i plan bazowy są takie same.

7. Wybierz opcję **Usuń wszystko**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Uruchom zaprojektowany format ER i przejrzyj dziennik, aby przeanalizować wyniki

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. W drzewie rozwiń **Model, aby uzyskać informacje o planach bazowych modelu er**, a następnie wybierz **Model w celu poznania się z formatem bazowym modelu ER\\Format w celu poznania się z formatem bazowym modelu ER**.
3. Na skróconej karcie **Wersje** wybierz **Uruchom**.
4. W polu **Wpisz ID** wpisz **2**.
5. Kliknij przycisk **OK**.
6. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Dzienniki debugowania konfiguracji**.

    ![Strona elektrownicznego raportowania dzienników przebiegu](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Zrzut ekranu strony elektrownicznego raportowania dzienników przebiegu")

    > [!NOTE]
    > Dziennik wykonania zawiera informacje o wynikach porównania wygenerowanego pliku ze skonfigurowaną linią bazową. W tym przykładzie dziennik wskazuje, że wygenerowany plik i plan bazowy są różne.

7. Wybierz **Porównaj**.

> [!NOTE]
> Wygenerowany plik i plik bazowy są oferowane jako pliki zip. Do porównywania plików i przeglądania różnic można użyć narzędzi do porównywania zewnętrznego, takich jak WinDiff.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie struktury ER](electronic-reporting-er-configure-parameters.md)
