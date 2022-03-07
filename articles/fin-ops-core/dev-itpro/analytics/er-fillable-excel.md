---
title: Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel
description: Ten temat zawiera informacje o tym, jak zaprojektować format modułu raportowania elektronicznego (ER) do wypełniania w szablonie programu Excel, a następnie generować dokumenty wychodzące w formacie programu Excel.
author: NickSelin
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87d5929557e5120a5339ee46eac655fd399679d1
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2021
ms.locfileid: "7943619"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel

[!include[banner](../includes/banner.md)]

Istnieje możliwość zaprojektowania konfiguracji formatu modułu [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) ze składnikiem formatu ER, który można skonfigurować do generowania dokumentu wychodzącego w formacie skoroszytu programu Microsoft Excel. W tym celu muszą być używane określone składniki formatu ER.

Aby dowiedzieć się więcej o tej funkcji, wykonaj kroki opisane w temacie [Projektowanie konfiguracji do generowania raportów w formacie OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Dodawanie nowego formatu ER

Podczas dodawania nowej konfiguracji formatu ER do generowania dokumentu wychodzącego w formacie skoroszytu programu Excel należy wybrać wartość **Excel** dla atrybutu **Typ formatu** lub pozostawić atrybut **Typ formatu**.

- W przypadku wybrania pozycji **Excel** można skonfigurować format w celu generowania dokumentu wychodzącego tylko w formacie programu Excel.
- Jeśli atrybut pozostanie pusty, można skonfigurować format do generowania dokumentu wychodzącego w dowolnym formacie obsługiwanym przez platformę ER.

Aby skonfigurować składnik formatu ER konfiguracji, wybierz pozycję **Projektant** w okienku akcji, a następnie otwórz składnik formatu ER do edycji w projektancie operacji ER.

![Strona Konfiguracje.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Składnik pliku programu Excel

### <a name="manual-entry"></a>Wpis ręczny

Musisz dodać składnik **Excel\\Plik** do skonfigurowanego formatu ER, aby wygenerować dokument wychodzący w formacie programu Excel.

![Składnik Excel\Plik.](./media/er-excel-format-add-file-component.png)

Aby określić układ dokumentu wychodzącego, dołącz skoroszyt programu Excel z rozszerzeniem xlsx do składnika **Excel\\Plik** jako szablon dokumentów wychodzących.

> [!NOTE]
> Podczas ręcznego dołączania szablonu należy użyć [typu dokumentu](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types), który został skonfigurowany dla tego celu w obszarze [parametrów ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Dodawanie załącznika do składnika Excel\Plik.](./media/er-excel-format-add-file-component2.png)

Aby określić sposób, w jaki dołączony szablon będzie wypełniany po uruchomieniu skonfigurowanego formatu ER, musisz dodać zagnieżdżone składniki **Arkusz**, **Zakres** i **Komórka** do składnika **Excel\\Plik**. Każdy zagnieżdżony składnik musi być skojarzony z nazwanym elementem programu Excel.

### <a name="template-import"></a>Importowanie szablonu

Możesz wybrać pozycję **Importuj z programu Excel** na karcie **Importowanie** w okienku akcji, aby zaimportować nowy szablon do pustego formatu ER. W tym przykładzie składnik **Excel\\Plik** zostanie utworzony automatycznie, a następnie zostanie do niego dołączony zaimportowany szablon. Wszystkie wymagane składniki ER również zostaną utworzone automatycznie na podstawie listy odnalezionych nazwanych elementów w programie Excel.

![Wybieranie pozycji Importuj z programu Excel.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Jeśli chcesz utworzyć opcjonalny element **Arkusz** w edytowalnym formacie ER, ustaw opcję **Utwórz element formatu Arkusz programu Excel** na **Tak**.

## <a name="sheet-component"></a>Składnik Arkusz

Składnik **Arkusz** wskazuje arkusz dołączonego skoroszytu programu Excel, który musi zostać wypełniony. Nazwa arkusza w szablonie programu Excel jest definiowana we właściwości **Arkusz** tego składnika.

> [!NOTE]
> Ten składnik jest opcjonalny dla skoroszytów programu Excel zawierających pojedynczy arkusz.

Na karcie **Mapowanie** projektanta operacji ER można skonfigurować właściwość **Włączone** dla składnika **Arkusz**, aby określić, czy składnik musi być umieszczany w generowanym dokumencie:

- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Prawda** w czasie wykonywania lub nie skonfigurowano żadnego wyrażenia, odpowiedni arkusz zostanie umieszczony w wygenerowanym dokumencie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane tak, aby zwracało wartość **Fałsz** w czasie wykonywania, wygenerowany dokument nie będzie zawierać arkusza.

![Przykład składnika Arkusz.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Składnik Zakres

Składnik **Zakres** wskazuje zakres programu Excel, który musi być kontrolowany przez ten składnik ER. Nazwa zakresu jest definiowana we właściwości **Zakres programu Excel** tego składnika.

### <a name="replication"></a>Replikacja

Właściwość **Kierunek replikacji** określa, czy i w jaki sposób zakres będzie powtarzany w wygenerowanym dokumencie:

- Jeśli właściwość **Kierunek replikacji** została ustawiona na wartość **Brak replikacji**, odpowiedni zakres programu Excel nie będzie powtarzany w wygenerowanym dokumencie.
- Jeśli właściwość **Kierunek replikacji** została ustawiona na wartość **Pionowo**, odpowiedni zakres programu Excel będzie powtarzany w wygenerowanym dokumencie. Każdy replikowany zakres jest umieszczany poniżej oryginalnego zakresu w szablonie programu Excel. Liczba powtórzeń jest definiowana przez liczbę rekordów w źródle danych typu **Lista rekordów** powiązanego z tym składnikiem ER.
- Jeśli właściwość **Kierunek replikacji** została ustawiona na wartość **Poziomo**, odpowiedni zakres programu Excel będzie powtarzany w wygenerowanym dokumencie. Każdy replikowany zakres jest umieszczany po prawej stronie oryginalnego zakresu w szablonie programu Excel. Liczba powtórzeń jest definiowana przez liczbę rekordów w źródle danych typu **Lista rekordów** powiązanego z tym składnikiem ER.

Aby dowiedzieć się więcej o replikacji poziomej, wykonaj kroki opisane w temacie [Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel](tasks/er-horizontal-1.md).

### <a name="nested-components"></a>Składniki zagnieżdżone

Składnik **Zakres** może zawierać inne zagnieżdżone składniki ER, które służą do wprowadzania wartości w odpowiednich nazwanych zakresach programu Excel.

- Jeśli dowolny składnik grupy **Tekst** jest używany do wprowadzania wartości, wartość jest wprowadzana w zakresie programu Excel jako wartość tekstowa.

    > [!NOTE]
    > Ten wzorzec służy do formatowania wprowadzonych wartości na podstawie ustawień regionalnych zdefiniowanych w aplikacji.

- Jeśli składnik **Komórka** grupy **Excel** jest używany do wprowadzania wartości, wartość jest wprowadzana w zakresie programu Excel jako wartość typu danych definiowana przez powiązanie tego składnika **Komórka** (np **Ciąg**, **Liczba rzeczywista** lub **Liczba całkowita**).

    > [!NOTE]
    > Ten wzorzec służy do formatowania w aplikacji Excel wprowadzonych wartości na podstawie ustawień regionalnych komputera lokalnego, na którym jest otwierany dokument wychodzący.

### <a name="enabling"></a>Włączanie

Na karcie **Mapowanie** projektanta operacji ER można skonfigurować właściwość **Włączone** dla składnika **Zakres**, aby określić, czy składnik musi być umieszczany w generowanym dokumencie:

- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Prawda** w czasie wykonywania lub nie skonfigurowano żadnego wyrażenia, odpowiedni zakres zostanie wypełniony w wygenerowanym dokumencie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Fałsz** w czasie wykonywania, a zakres nie reprezentuje całych wierszy lub kolumn, odpowiedni zakres nie zostanie wypełniony w wygenerowanym dokumencie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Fałsz** w czasie wykonywania, a zakres reprezentuje całe wiersze lub kolumny, wygenerowany dokument będzie zawierać te wiersze i kolumny jako ukryte.

### <a name="resizing"></a>Zmiana rozmiaru

Można skonfigurować szablon programu Excel do używania komórek do prezentować dane tekstowe. Aby mieć pewność, że cały tekst w komórce jest widoczny w generowanym dokumencie, można skonfigurować komórkę do automatycznego oznaczania tekstu wewnątrz tej komórki. Można również skonfigurować wiersz zawierający komórkę, aby automatycznie korygował jej wysokość, jeśli tekst otoki nie jest w pełni widoczny. Aby uzyskać więcej informacji, zobacz sekcję „Tekst w komórce” w sekcji [Popraw dane, które są odciętych w komórkach](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e).

> [!NOTE]
> Z powodu znanego [ograniczenia programu Excel](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353), nawet jeśli skonfigurujesz komórki do zawijania tekstu i skonfigurujesz wiersze zawierające te komórki tak, aby automatycznie dopasowywały ich wysokość do zawiniętego tekstu, możesz nie być w stanie użyj funkcji **AutoFit** i **Zawijanie tekstu** Excela dla scalonych komórek i zawierających je wierszy. 

Na podstawie wersji Dynamics 365 Finance 10.0.23 można wymusić na ER obliczenie, w generowanym dokumencie, wysokości każdego wiersza, który został skonfigurowany tak, aby jego wysokość automatycznie pasowała do zawartości zagnieżdżonych komórek za każdym razem, gdy wiersz zawiera co najmniej jedną scalone komórkę, która została skonfigurowana do oznaczania tekstu wewnątrz tego wiersza. Obliczona wysokość służy do zmiany rozmiaru wiersza w celu zapewnienia, że wszystkie komórki wiersza są widoczne w generowanym dokumencie. Aby rozpocząć korzystanie z tej funkcji po uruchomieniu formatów raportów elektronicznych skonfigurowanych do generowania dokumentów wychodzących za pomocą szablonów programu Excel, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Parametry raportowania elektronicznego**.
3. Na stronie **Parametry raportowania elektronicznego** na karcie **środowisko uruchomieniowe** ustaw opcję **Automatycznie dopasuj wysokość wiersza** na **Tak**.

Aby zmienić tę regułę dla jednego formatu ER, zaktualizuj wersję roboczą tego formatu, wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji w lewym okienku wybierz konfigurację ER zaprojektowaną do generowania dokumentów wychodzących przy użyciu szablonu programu Excel.
4. Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.
5. W okienku akcji wybierz opcję **Projektant**.
6. Na stronie **Projektant formatów** w drzewie formatów w lewym okienku wybierz składnik programu Excel połączony z szablonem programu Excel.
7. Na karcie **Format** w polu **Dostosuj wysokość wiersza** wybierz wartość, która określa, czy w czasie wykonywania raport ER ma być wymuszany w celu zmiany wysokości wierszy w dokumencie wychodzącym generowanym w edytowanym formacie ER:

    - **Domyślne** — należy użyć ustawienia ogólnego skonfigurowanego w polu **Autodopasowanie wysokości wiersza** na stronie **Parametry raportowania elektronicznego**.
    - **Tak** — zastąp ustawienie ogólne i zmień wysokość wiersza w czasie wykonywania.
    - **Nie** — zastąp ustawienie ogólne i nie zmienia wysokość wiersza w czasie wykonywania.

## <a name="cell-component"></a>Składnik Komórka

Składnik **Komórka** służy do wypełniania nazwanych komórek, kształtów i obrazów w programie Excel. Aby wskazać nazwany obiekt programu Excel, który musi zostać wypełniony przez składnik ER **Komórka**, należy określić nazwę tego obiektu we właściwości **Zakres programu Excel** składnika **Komórka**.

Na karcie **Mapowanie** projektanta operacji ER można skonfigurować właściwość **Włączone** dla składnika **Komórka**, aby określić, czy obiekt musi być wypełniany w generowanym dokumencie:

- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Prawda** w czasie wykonywania lub nie skonfigurowano żadnego wyrażenia, odpowiedni obiekt zostanie wypełniony w wygenerowanym dokumencie. Powiązanie tego składnika **Komórka** określa wartość, która jest umieszczana w odpowiednim obiekcie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane tak, aby zwracało wartość **Fałsz** w czasie wykonywania, odpowiedni obiekt nie będzie wypełniany w wygenerowanym dokumencie.

Jeśli składnik **Komórka** został skonfigurowany do wprowadzania wartości w komórce, może być powiązany ze źródłem danych zwracającym wartość z pierwotnym typem danych (na przykład **Ciąg**, **Liczba rzeczywista** lub **Liczba całkowita**). W takim przypadku wartość jest wprowadzana do komórki jako wartość tego samego typu danych.

Jeśli składnik **Komórka** został skonfigurowany do wprowadzania wartości w kształcie programu Excel, może być powiązany ze źródłem danych zwracającym wartość z pierwotnym typem danych (na przykład **Ciąg**, **Liczba rzeczywista** lub **Liczba całkowita**). W takim przypadku wartość jest wprowadzana w kształcie programu Excel jako tekst tego kształtu. W przypadku wartości typów danych innych niż **Ciąg**, konwersja na tekst jest dokonywana automatycznie.

> [!NOTE]
> Składnik **Komórka** można skonfigurować do wypełniania kształtu tylko w przypadkach, w których właściwość tekstu kształtu jest obsługiwana.

Jeśli składnik **Komórka** został skonfigurowany do wprowadzania wartości w obrazie programu Excel, może być powiązany ze źródłem danych zwracającym wartość z typem danych **Kontener**, które reprezentuje obraz w formacie binarnym. W takim przypadku wartość jest wprowadzana w obrazie programu Excel jako obraz.

> [!NOTE]
> Każdy obraz i kształt programu Excel jest traktowany jako zakotwiczony do lewego górnego rogu do konkretnej komórki lub zakresu w programie Excel. Aby replikować obraz lub kształt programu Excel, należy skonfigurować komórkę lub zakres, do którego zostały one zakotwiczone, jako zreplikowaną komórkę lub zakres.

Aby dowiedzieć się więcej na temat osadzania obrazów i kształtów, zobacz temat [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Składnik Podział strony

Składnik **PageBreak** wymusza rozpoczęcie nowej strony przez program Excel. Ten składnik nie jest wymagany, jeśli ma być używany domyślne stronicowanie programu Excel, ale powinien być używany, jeśli chcesz, aby program Excel korzystał z formatu ER w celu utworzenia struktury stronicowania.

## <a name="page-component"></a><a name="page-component"></a>Składnik strony

### <a name="overview"></a>Omówienie

Składnik **Strona** może być używany, jeśli program Excel ma stosować strukturę stronicowania i format raportowania elektronicznego w generowanym dokumencie wychodzącym. Gdy w formacie raportowania elektronicznego są uruchamiane składniki pod składnikiem **Strona**, wymagane podziały strony są automatycznie dodawane. W trakcie tego procesu są rozważane: rozmiar wygenerowanej zawartości, konfiguracja strony szablonu programu Excel i rozmiar papieru wybrany w szablonie programu Excel.

Jeśli należy podzielić wygenerowany dokument na różne sekcje, z których każda ma inną paginację, można skonfigurować kilka składników **Strony** w każdym składniku [arkusza](er-fillable-excel.md#sheet-component).

### <a name="structure"></a><a name="page-component-structure"></a>Struktura

Jeśli pierwszy składnik pod składnikiem **Strona** jest składnikiem [Zakres](er-fillable-excel.md#range-component), dla którego właściwość **Kierunek replikacji** ma wartość **Brak replikacji**, ten zakres jest traktowany jako nagłówek strony do stronicowania opartego na ustawieniach bieżącego składnika **Strona**. Zakres programu Excel skojarzony z tym składnikiem formatu jest powtarzany w górnej części każdej strony generowanej przy użyciu ustawień bieżącego składnika **Strona**.

> [!NOTE]
> W przypadku prawidłowego stronicowania, jeśli wiersze do [powtórzenia w górnym](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) zakresie zostały skonfigurowane w szablonie programu Excel, adres tego zakresu programu Excel musi być adresem zakresu programu Excel skojarzonego z poprzednio opisanym składnikiem **Zakres**.

Jeśli ostatni składnik pod składnikiem **Strona** jest składnikiem **Zakres**, dla którego właściwość **Kierunek replikacji** ma wartość **Brak replikacji**, ten zakres jest traktowany jako stopka strony do stronicowania opartego na ustawieniach bieżącego składnika **Strona**. Zakres programu Excel skojarzony z tym składnikiem formatu jest powtarzany w dolnej części każdej strony generowanej przy użyciu ustawień bieżącego składnika **Strona**.

> [!NOTE]
> W przypadku prawidłowego stronicowania nie należy zmieniać rozmiaru zakresów programu Excel skojarzonych ze składnikami **Zakres** w czasie wykonywania. Nie zaleca się formatowania komórek tego zakresu przy użyciu [opcji](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84) **Zawiń tekst w komórce** i **Autodopasowania wysokości** programu Excel.

Aby określić sposób wypełnienia generowanego dokumentu, można dodać wiele innych składników **Zakresu** między opcjonalnymi składnikami **Zakresu**.

Jeśli zestaw zagnieżdżonych składników **Zakres** w składniku **Strona** nie jest zgodny z wcześniej opisaną strukturą, podczas projektowania w konstruktorze formatu raportowania elektronicznego występuje [błąd](er-components-inspections.md#i17) sprawdzania poprawności. Komunikat o błędzie informuje, że problem może spowodować problemy w czasie wykonywania.

> [!NOTE]
> Aby wygenerować poprawne dane wyjściowe, nie określaj powiązania dla żadnego składnika **Zakresu** w składniku **Strony**, jeśli właściwość **Kierunku replikacji** dla tego składnika **Zakresu** ma wartość **Brak replikacji**, a zakres jest skonfigurowany do generowania nagłówków lub stopek stron.

Jeśli chcesz, aby sumy i obliczenia związane z podziałem na strony obliczały sumy i sumy na stronę, zalecane jest skonfigurowanie wymaganych źródeł danych [gromadzenia danych](er-data-collection-data-sources.md). Aby dowiedzieć się, jak używać składnika **Strony** do stronicowania wygenerowanego dokumentu programu Excel, wykonaj procedury w temacie [Projektowanie formatu raportowania elektronicznego do stronicowania wygenerowanego dokumentu w formacie programu Excel](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Ograniczenia

Podczas używania składnika **Strony** do stronicowania programu Excel nie będzie wiadomo, jaka będzie końcowa liczba stron wygenerowanego dokumentu, dopóki nie zostanie ukończone stronicowanie. Dlatego nie można obliczyć łącznej liczby stron za pomocą formuł raportowania elektronicznego i wydrukować poprawnej liczby stron wygenerowanego dokumentu na dowolnej stronie przed ostatnią stroną.

> [!TIP]
> Aby uzyskać ten wynik, w nagłówku lub stopce programu Excel można użyć specjalnego [formatowania](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) programu Excel dla nagłówków i stopek.

Skonfigurowane składniki **Strona** nie są rozważane podczas aktualizowania szablonu programu Excel w formacie edytowalnym w wersji 10.0.22 rozwiązania Dynamics 365 Finance. Ta funkcja jest rozważana w dalszych wersjach rozwiązania Finance.

Jeśli szablon programu Excel zostanie skonfigurowany do [formatowania warunkowego](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting), w niektórych przypadkach może nie działać zgodnie z oczekiwaniami.

### <a name="applicability"></a>Możliwość stosowania

Składnik **Strona** działa dla składnika formatu [pliku programu Excel](er-fillable-excel.md#excel-file-component) tylko w przypadku, gdy dla tego składnika skonfigurowano używanie szablonu w programie Excel. Jeśli szablon programu Excel zostanie [zastąpiony](tasks/er-design-configuration-word-2016-11.md) szablonem programu Word, a następnie uruchomiony zostanie edytowalny format raportowania elektronicznego, składnik **Strona** będzie ignorowany.

Składnik **Strona** działa tylko w przypadku włączenia funkcji **Włącz użycie biblioteki EPPlus w strukturze raportowania elektronicznego**. Wystąpił wyjątek w czasie wykonywania, jeśli raportowanie elektroniczne próbuje przetworzyć składnik **Strona**, gdy ta funkcja jest wyłączona.

> [!NOTE]
> Wystąpił wyjątek w czasie wykonywania, jeśli format raportowania elektronicznego przetwarza składnik **Strona** dla szablonu programu Excel zawierającego co najmniej jedną formułę, która odwołuje się do nieprawidłowej komórki. Aby zapobiec błędom w czasie wykonywania, popraw szablon programu Excel w sposób opisany w temacie [Jak naprawić błąd #REF!](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Składnik stopki

Składnik **Stopki** służy do wypełniania stopek u dołu wygenerowanego arkusza w skoroszycie programu Excel.

> [!NOTE]
> Ten składnik można dodać dla każdego składnika **Arkusza**, aby określić różne stopki dla różnych arkuszy w generowanym skoroszycie programu Excel.

Podczas konfigurowania pojedynczych składników **Stopki** można używać właściwości **Wyglądu nagłówka/stopki**, aby określić strony, do których składnik jest używany. Dostępne są następujące wartości:

- **Dowolny** — umożliwia uruchomienie skonfigurowanego składnika **Stopki** dla dowolnej strony nadrzędnego arkusza programu Excel.
- **Pierwszy** — umożliwia uruchomienie skonfigurowanego składnika **Stopki** dla pierwszej strony nadrzędnego arkusza programu Excel.
- **Policzalne** — umożliwia uruchomienie skonfigurowanego pierwszego składnika **Stopki** dla policzalnych stron nadrzędnego arkusza programu Excel.
- **Niepoliczalne** — umożliwia uruchomienie skonfigurowanego pierwszego składnika **Stopki** dla niepoliczalnych stron nadrzędnego arkusza programu Excel.

Dla jednego składnika **Arkusza** można dodać kilka składników **stopki**, z których każdy ma inną wartość właściwości **Wyglądu Nagłówka/stopki**. W ten sposób można generować różne stopki dla różnych typów stron w arkuszu programu Excel.

> [!NOTE]
> Upewnij się, że każdy składnik **Stopka**, który dodajesz do pojedynczego składnika **Arkusza** ma inną wartość właściwości **Wyglądu Nagłówka/stopki**. W przeciwnym razie [wystąpi błąd weryfikacji](er-components-inspections.md#i16). Odbierany komunikat o błędzie powiadamia o niespójności.

Pod dodanym składnikiem **Stopki** dodaj wymagane zagnieżdżone składniki ciągu **Text\\String**, **Text\\DateTime** lub innego typu. Skonfiguruj powiązania tych składników, aby określić sposób wypełnienia stopki strony.

Można również użyć specjalnych [kodów formatowania](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers), aby poprawnie sformatować zawartość wygenerowanej stopki. Aby się dowiedzieć, jak korzystać z tego podejścia, wykonaj kroki opisane w [Przykładzie 1](#example-1), dalej w tym temacie.

> [!NOTE]
> Konfigurując formaty ER, należy wziąć pod uwagę limit programu Excel i [maksymalną liczbę znaków](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) dla jednego nagłówka lub stopki.

## <a name="header-component"></a>Składnik nagłówka

Składnik **Nagłówek** służy do wypełniania nagłówek u góry wygenerowanego arkusza w skoroszycie programu Excel. Jest używana jak składnik **Stopki**.

## <a name="edit-an-added-er-format"></a>Edytowanie dodanego formatu ER

### <a name="update-a-template"></a>Aktualizowanie szablonu

Możesz wybrać pozycję **Aktualizuj z programu Excel** na karcie **Importowanie** w okienku akcji, aby zaimportować zaktualizowany szablon do edytowalnego formatu ER. W trakcie tego procesu szablon wybranego składnika **Excel\\File** zostanie zastąpiony nowym szablonem. Zawartość edytowalnego formatu ER zostanie zsynchronizowana z zawartością zaktualizowanego szablonu ER.

- Nowy składnik formatu ER zostanie utworzony automatycznie dla każdej nazwy programu Excel, jeśli składnik formatu ER nie zostanie znaleziony w formacie edytowalnym.
- Każdy składnik formatu ER zostanie usunięty z edytowalnego formatu ER, jeśli dla niego nie zostanie znaleziona odpowiednia nazwa programu Excel.

> [!NOTE]
> Ustaw opcję **Utwórz element formatu Arkusz programu Excel** na **Tak**, jeśli chcesz utworzyć opcjonalny element **Arkusz** w edytowalnym formacie ER.
>
> Jeśli edytowalny format ER pierwotnie zawierał elementy **Arkusz**, zalecamy ustawienie opcji **Utwórz element formatu Arkusz programu Excel** na wartość **Tak** podczas importowania zaktualizowanego szablonu. W przeciwnym razie wszystkie zagnieżdżone elementy oryginalnego elementu **Arkusz** zostaną utworzone od początku. Dlatego wszystkie powiązania nowo utworzonych elementów formatu zostaną utracone w zaktualizowanym formacie ER.

![Opcja Utwórz element formatu Arkusz programu Excel w oknie dialogowym aktualizowania z programu Excel.](./media/er-excel-format-update-template.png)

Aby dowiedzieć się więcej o tej funkcji, wykonaj kroki opisane w temacie [Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Weryfikowanie formatu ER

Podczas weryfikowania formatu ER, który można edytować, jest przeprowadzane sprawdzenie spójności w celu upewnienia się, że nazwa programu Excel znajduje się w aktualnie używanym szablonie programu Excel. Otrzymasz powiadomienie o ewentualnych niespójnościach. W przypadku niektórych niespójności będą oferowane opcje automatycznego rozwiązania danego problemu.

![Komunikat o błędzie weryfikacji.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Sterowanie obliczaniem formuł programu Excel

Podczas generowania dokumentu wychodzącego w formacie skoroszytu programu Microsoft Excel niektóre komórki tego dokumentu mogą zawierać formuły programu Excel. Gdy jest włączona funkcja **Włącz korzystanie z biblioteki EPPlus w ramach raportowania elektronicznego**, można kontrolować, kiedy formuły będą obliczane, zmieniając wartość [parametru](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) **Opcje obliczania** w używanym szablonie programu Excel:

- Wybierz opcję **Automatycznie**, aby ponownie obliczać wszystkie formuły zależne za każdym razem, gdy do wygenerowanego dokumentu są dołączane nowe zakresy, komórki itp.

    >[!NOTE]
    > Może to spowodować problemy z wydajnością działania szablonów programu Excel zawierających wiele powiązanych formuł.

- Wybierz opcję **Ręcznie**, aby uniknąć ponownego obliczania formuł podczas generowania dokumentu.

    >[!NOTE]
    > Ponowne obliczanie formuł jest wymuszane ręcznie po otwarciu wygenerowanego dokumentu do podglądu za pomocą programu Excel.
    > Nie należy stosować tej opcji w przypadku konfigurowania miejsca docelowego modułu ER, które zakłada używanie wygenerowanego dokumentu bez obejrzenia jego podglądu w programie Excel (konwersja do pliku PDF, wysłanie wiadomości e-mail itp.), ponieważ wygenerowany dokument może nie zawierać wartości w komórkach z formułami.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Przykład 1. Zawartość stopki formatu

1. Użyj dostarczonych konfiguracji ER do [wygenerowania](er-generate-printable-fti-forms.md) dokumentu faktury elektronicznej (FTI) do wydrukowania.
2. Przejrzyj stopkę wygenerowanego dokumentu. Należy zauważyć, że zawiera informacje o numerze bieżącej strony i łącznej liczbie stron w dokumencie.

    ![Przejrzyj stopkę wygenerowanego dokumentu w formacie programu Excel.](./media/er-fillable-excel-footer-1.gif)

3. W konstruktorze formatów ER [otwórz](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) przykładowy format ER do przeglądu.

    Stopka arkusza **Faktury** jest generowana na podstawie ustawień dwóch składników **Ciągu**, które znajdują się w składniku **Stopki**:

    - Pierwszy składnik **Ciągu** wypełnia następujące specjalne kody formatowania, aby wymusić zastosowanie określonego formatowania w programie Excel:

        - **&C** — umożliwia wyrównanie tekstu stopki do środka.
        - **&"Segoe UI,Regular"&8** – tekst stopki należy prezentować w czcionce "Segoe UI Regular" w rozmiarze 8 punktów.

    - Drugi składnik **Ciągu** wypełnia tekst zawierający numer bieżącej strony oraz łączną liczbę stron w bieżącym dokumencie.

    ![Sprawdzanie poprawności stopki składnika formatu ER na stronie Projektant formatów.](./media/er-fillable-excel-footer-2.png)

4. Dostosuj przykładowy format ER w celu zmodyfikowania stopki bieżącej strony:

    1. [Utwórz](er-quick-start2-customize-report.md#DeriveProvidedFormat) pochodny **Darmowy niestandardowy format ER (Excel) faktury elektronicznej** oparty na przykładowym formacie ER.
    2. Dodaj pierwszą nową parę składników **Ciągu** dla składnika **Stopki** arkusza **Faktura**:

        1. Dodaj składnik **Ciąg**, który wyrówna nazwę firmy po lewej stronie i przedstawia ją w 8-punktowej czcionce "Segoe UI Regular" (**"&L&"Segoe UI,Regular"&8"**).
        2. Dodaj **Ciąg**, który wypełnia nazwę firmy (**model.InvoiceBase.CompanyInfo.Name**).

    3. Dodaj drugą nową parę składników **Ciągu** dla składnika **Stopki** arkusza **Faktura**:

        1. Dodaj składnik **Ciąg**, który wyrównuje datę przetwarzania z prawej strony i przedstawia ją w 8-punktowej czcionce "Segoe UI Regular" (**"&R&"Segoe UI,Regular"&8"**).
        2. Umożliwia dodanie składnika **Ciągu**, który wypełnia datę przetwarzania w niestandardowym formacie (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![Sprawdzanie poprawności stopki składnika formatu ER na stronie Projektant formatów.](./media/er-fillable-excel-footer-3.png)

    4. [Ukończ](er-quick-start2-customize-report.md#CompleteDerivedFormat) wersję roboczą **Niestandardowej darmowej pochodnej faktury elektronicznej (Excel)** formatu ER.

5. [Skonfiguruj](er-generate-printable-fti-forms.md#configure-print-management) zarządzanie drukowaniem, aby używać pochodnego formatu ER **Faktura niezależna (Excel) - niestandardowa** zamiast przykładowego formatu ER.
6. Wygeneruj dokument FTI, który można wydrukować, i przejrzyj stopkę wygenerowanego dokumentu.

    ![Sprawdzanie stopki wygenerowanego dokumentu w formacie programu Excel.](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a>Przykład 2. Rozwiązywanie problemu EPPlus dotyczącego scalonych komórek

Aby wygenerować dokument wychodzący w formacie skoroszytu programu Excel, można uruchomić format ER. Jeśli funkcja **Włącz użycie biblioteki EPPlus w strukturze raportowania elektronicznego** zostanie włączona w obszarze roboczym **Zarządzanie funkcjami**, [biblioteka EPPlus](https://www.nuget.org/packages/epplus/4.5.2.1) będzie używana do tworzenia danych wyjściowych programu Excel. Jednak ze względu na znane [zachowanie programu Excel](https://answers.microsoft.com/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9) oraz ograniczenie biblioteki EPPlus może wystąpić wyjątek „Nie można usuwać/zastępować scalonych komórek. Zakres został częściowo scalony z innym scalonym zakresem”. Aby dowiedzieć się, jakiego rodzaju szablony programu Excel mogą być przyczyną tego wyjątku i jak można rozwiązać ten problem, wykonaj poniższy przykład.

1. W aplikacji klasycznej Excel utwórz nowy skoroszyt programu Excel.
2. W arkuszu **Sheet1** dodaj nazwę **ReportTitle** dla komórki **A2**.
3. Scal komórki **A1** i **A2**.

    ![Przeglądanie wyników scalania komórek A1 i A2 w zaprojektowanym skoroszycie programu Excel w aplikacji klasycznej Excel.](./media/er-fillable-excel-example2-1.png)

3. Na stronie **Konfiguracje** [dodaj nowy format ER](er-fillable-excel.md#add-a-new-er-format), aby wygenerować dokument wychodzący w formacie skoroszytu programu Excel.
4. Na stronie **Projektant formatów** [zaimportuj](er-fillable-excel.md#template-import) zaprojektowany skoroszyt programu Excel do dodanego formatu ER jako nowy szablon dokumentów wychodzących.
5. Na karcie **Mapowanie** skonfiguruj powiązanie składnika **ReportTitle** typu [Komórka](er-fillable-excel.md#cell-component).
6. Uruchom skonfigurowany format ER. Zwróć uwagę, że wystąpił następujący wyjątek: „Nie można usunąć/zastąpić scalonych komórek. Zakres został częściowo scalony z innym scalonym zakresem”.

    ![Przejrzyj wyniki uruchomienia skonfigurowanego formatu ER na stronie Projektant formatów.](./media/er-fillable-excel-example2-2.png)

Problem można rozwiązać przy użyciu jednego z poniższych sposobów:

- **Łatwiejszy, ale niezalecany:** w obszarze roboczym **Zarządzanie funkcjami** wyłącz funkcję **Włącz użycie biblioteki EPPlus w strukturze raportowania elektronicznego**. Chociaż takie podejście jest łatwiejsze, mogą wystąpić inne problemy, ponieważ niektóre funkcje ER są obsługiwane tylko wtedy, gdy włączono funkcję **Włącz użycie biblioteki EPPlus w strukturze raportowania elektronicznego**.
- **Zalecany:** wykonaj następujące czynności:

    1. W aplikacji klasycznej Excel zmodyfikuj skoroszyt programu Excel na jeden z następujących sposobów:

        - W arkuszu **Sheet1** rozdziel komórki **A1** i **A2**.
        - Zmień odwołanie dla nazwy **ReportTitle** z **=Sheet1!$A$2** na **=Sheet1!$A$1**.

        ![Przeglądanie wyników zmiany odwołania w zaprojektowanym skoroszycie programu Excel w aplikacji klasycznej Excel.](./media/er-fillable-excel-example2-3.png)

    2. Na stronie **Konstruktor formatów** [zaimportuj](er-fillable-excel.md#template-import) zmodyfikowany skoroszyt programu Excel do edytowalnego formatu ER w celu zaktualizowania istniejącego szablonu.
    3. Uruchom zmodyfikowany format ER.

        ![Przeglądanie wygenerowanego dokumentu programu Excel w aplikacji klasycznej.](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>Ograniczenia

### <a name="known-epplus-library-limitations"></a>Znane ograniczenia biblioteki EPPlus

#### <a name="external-data-sources"></a>Zewnętrzne źródła danych

Jeśli jeden z szablonów zawiera tabelę przestawną opartą na modelu PowerPivot który odwołuje się do [zewnętrznego źródła danych](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b), włączono funkcję **Włącz użycie biblioteki EPPlus w narzędziach raportowania elektronicznego**, po uruchomieniu formatu raportowania elektronicznego korzystającego z tego szablonu w celu wygenerowania dokumentu wychodzącego w formacie Excel: "Źródło pamięci podręcznej nie jest arkuszem." Aby naprawić ten problem, skorzystaj z jednej z następujących opcji:

- **Zalecane jest** przeprojektowanie używanych rozwiązań Excel:

    1. Wyodrębnij część zawierającą pivots w osobnym skoroszycie programu Excel (skoroszyt A). 
    2. Funkcji tej można użyć w celu wygenerowania na podstawie danych finansowych drugiego skoroszytu programu Excel (skoroszyt B) z wymaganymi szczegółami. 
    3. Po wygenerowaniu skoroszytu B zapoznaj się ze skoroszytem B w skoroszycie A.

- Aby wyłączyć tę funkcję, należy użyć opcji innej niż EPPlus. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektowanie konfiguracji do generowania raportów w formacie OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel](tasks/er-horizontal-1.md)

[Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)

[Konfigurowanie w module Raportowanie elektroniczne (ER) ściągania danych do usługi Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
