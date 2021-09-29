---
title: Projektowanie formatu ER do stronicowania wygenerowanych dokumentów w programie Excel
description: W tym temacie opisano sposób projektowania formatu raportowania elektronicznego, który stronicuje wygenerowany dokument w programie Microsoft Excel.
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.openlocfilehash: ce29225c4bce24adc2abefc3d3d6f20774852af4
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488346"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Projektowanie formatu ER do stronicowania wygenerowanych dokumentów w programie Excel

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak użytkownik w roli administratora systemu lub konsultanta funkcjonalnego ds. raportowania elektronicznego może skonfigurować format [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) w celu generowania dokumentów wychodzących w programie Microsoft Excel i zarządzania stronicowaniem dokumentów.

W tym przykładzie zmodyfikujesz dostarczony przez firmę Microsoft format raportowania elektronicznego, który jest używany do drukowania raportu kontrolnego, gdy deklaracja Intrastat jest [generowana](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Ten raport pozwala obserwować zgłoszone transakcje Intrastat. Twoje modyfikacje pozwolą Ci zarządzać stronicowaniem generowanych raportów kontrolnych.

Zadania przedstawione w tym temacie można wykonać w kontekście firmy **DEMF**. Nie są wymagane umiejętności kodowania. Przed rozpoczęciem musisz pobrać i zapisać następujące pliki.

| opis       | Nazwa pliku |
|-------------------|-----------| 
| Szablon raportu 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Szablon raportu 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Wykonaj kroki opisane w sekcji [Konfigurowanie platformy ER](er-quick-start2-customize-report.md#ConfigureFramework), aby skonfigurować minimalny zestaw parametrów ER. Tę konfigurację należy ukończyć przed rozpoczęciem korzystania z platformy ER do projektowania niestandardowej wersji standardowego formatu ER.

## <a name="import-the-standard-er-format-configuration"></a>Importowanie standardowej konfiguracji formatu ER

Postępuj zgodnie z instrukcjami w [Importuj standardową konfigurację formatu ER](er-quick-start2-customize-report.md#ImportERSolution1), aby dodać standardowe konfiguracje ER do bieżącego wystąpienia Dynamics 365 Finance. Importuj **wersję 1.9** konfiguracji formatu **raportu Intrastat**. Podstawowa wersja 1 podstawowej konfiguracji **modelu Intrastat** jest automatycznie importowana z repozytorium.

## <a name="customize-the-standard-er-format"></a>Dostosowywanie standardowego formatu ER

### <a name="create-the-custom-er-format"></a>Utwórz niestandardowy format ER

W tym scenariuszu jesteś przedstawicielem Litware, Inc., która jest obecnie wybrana jako aktywny dostawca konfiguracji ER. Należy utworzyć nową konfigurację formatu ER, używając konfiguracji raportu **Intrastat** jako podstawy.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w okienku po lewej wybierz pozycję **Model Intrastat**, a potem wybierz **Raport Intrastat**. Litware, Inc. będzie używał wersji 1.9 tej konfiguracji formatu ER jako podstawy dla wersji niestandardowej.
3. Wybierz przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe. Nowe okno dialogowe pozwoli utworzyć nową konfigurację dla niestandardowego formatu płatności.
4. W **Nowej** grupie pól, wybierz opcję **Pochodzi z nazwy: raport Intrastat, Microsoft**.
5. W polu **nazwa** wprowadź **raport Intrastat Litware**.
6. Wybierz **Stwórz konfiguracj**, aby stworzyć nowy format.

Utworzono konfigurację tematu ER **Raport Intrastat Litware** w wersji 1.9.1. Ta wersja ma [stan](general-electronic-reporting.md#component-versioning) **Wersji roboczej** i można ją edytować. Bieżąca zawartość niestandardowego formatu ER jest zgodna z zawartością formatu dostarczonego przez Microsoft.

### <a name="make-the-custom-format-runnable"></a>Spraw, aby niestandardowy format można było uruchomić

Teraz, gdy została utworzona pierwsza wersja formatu niestandardowego i ma ona stan **Wersja robocza**, można uruchomić format w celach testowych. Aby uruchomić raport, należy przetworzyć płatność dostawcy, używając metody płatności, która odwołuje się do niestandardowego formatu encji (ER). Domyślnie, podczas wywoływania formatu ER w aplikacji, jedynie wersje, które mają stan **Zakończono** lub **Udostępniono**, są [używane](general-electronic-reporting.md#component-versioning). To zachowanie pomaga zapobiegać używaniu formatów ER, w których znajdują się nieukończone projekty. Jednak w przypadku uruchamiania testów można wymusić na aplikacji używanie wersji formatu ER, która ma stan **Wersja robocza**. W ten sposób można dostosować bieżącą wersję formatu, jeśli są wymagane jakiekolwiek modyfikacje. Aby uzyskać więcej informacji, zobacz [Zastosowanie](electronic-reporting-destinations.md#applicability).

Aby można było skorzystać z wersji roboczej formatu ER, należy odpowiednio go oznaczyć.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.
4. W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była możliwa do edycji.
5. W drzewie konfiguracji w lewym okienku wybierz opcję **Raport Intrastat Litware**.
6. Dla opcji **Uruchom wersję roboczą** określ wartość **Tak**, a następnie wybierz pozycję **Zapisz**.

    ![Uruchom Wersję roboczą na stronie konfiguracje.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Skonfiguruj parametry handlu zagranicznego, aby używać niestandardowego formatu ER

Wykonaj poniższe czynności, aby skonfigurować parametry handlu zagranicznego, aby można było użyć formatu niestandardowego.

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Parametry handlu zagranicznego**.
2. Na stronie **Parametry handlu zagranicznego**, na skróconej karcie **Intrastat** w polu **Mapowanie formatu pliku** wybierz pozycję **Raport Intrastat Litware**.
3. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat Litware**.
4. Wybierz opcję **Zapisz**.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Skonfiguruj niestandardowy format, aby użyć pobranego szablonu raportu

### <a name="review-the-first-downloaded-excel-template"></a>Przejrzyj pierwszy pobrany szablon programu Excel

1. W aplikacji programu Excel otwórz pobrany wcześniej plik szablonu **ERIntrastatReportDemo1.xlsx**.
2. Sprawdź, czy szablon zawiera nazwane zakresy, aby utworzyć nagłówek raportu, szczegóły raportu i sekcje stopki raportu w wygenerowanych dokumentach.

    ![Układ szablonu Excel 1 w aplikacji klasycznej.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Zastąp bieżący szablon programu Excel w niestandardowym formacie ER

Musisz dodać nowy szablon programu Excel do niestandardowego formatu ER.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w okienku po lewej wybierz pozycję **Model Intrastat** \> **Raport Intrastat** i wybierz konfigurację **Raport Intrastat Litware**.
3. Wybierz opcję **Konstruktor**.
4. Na stronie **Projektant formatów** w okienku akcji wybierz opcję **Pokaż szczegóły**.
5. Upewnij się, że wybrany jest składnik formatu głównego **Intrastat: Excel**, a następnie w okienku akcji na karcie **Import** w grupie **Import** wybierz **Aktualizuj z Excela**.
6. W oknie dialogowym **Aktualizacja z programu Excel** wybierz pozycję **Aktualizuj szablon**.
7. W oknie dialogowym **Otwórz** przejdź do i wybierz pobrany wcześniej plik **ERIntrastatReportDemo1.xlsx**, a następnie wybierz **Otwórz**.
8. Kliknij przycisk **OK**.
9. Wybierz opcję **Zapisz**.

![Struktura formatu w konstruktorze formatów ER po dodaniu nowego szablonu programu Excel.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Zmień powiązanie danych, aby wyświetlić opis pozycji w wygenerowanym raporcie

1. Na stronie **Projektant formatów** wybierz kartę **mapowanie.**
2. Rozwiń **Intrastat** \> **wiersze raportu** i zaznacz składnik **kodu asortymentu**.
3. Wybierz opcję **Edytuj formułę**.
4. Zmień formułę powiązania z `@.CommodityCode` na `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Wybierz opcję **Zapisz**.

![Skonfigurowane powiązanie do wyświetlania opisu pozycji w konstruktorze formatu ER.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Wygeneruj raport kontrolny deklaracji Intrastat

Najpierw upewnij się, że na stronie Intrastat są raportowanie transakcje **Intrastat**.

![Transakcje na stronie Intrastat.](./media/er-paginate-excel-reports-transactions1.gif)

Następnie użyj niestandardowego formatu ER, aby wygenerować raport kontrolny deklaracji Intrastat.

1. Wybierz kolejno opcje **Podatek** \> **Deklaracje** \> **Handel zagraniczny** \> **Intrastat**.
2. Na stronie **Intrastat** w okienku akcji wybierz pozycję **Wychodzące** \> **Raport**.
3. Aby uruchomić raport, w oknie dialogowym **Raport Intrastat** wykonaj następujące czynności:

    1. Aby uwzględnić w raporcie określone transakcje Intrastat, należy ustawić pola **Od dnia** i **Do dnia**.
    2. W polu **Generuj plik** wybierz opcję **No**.
    3. W polu **Generuj raport** wybierz opcję **Tak**.
    4. Kliknij przycisk **OK**.

4. Pobierz i zapisz wygenerowany dokument.
5. Otwórz dokument w programie Excel i przejrzyj go.

    ![Wygenerowano dokument Excel w aplikacji na komputerze.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Konfigurowanie formatu niestandardowego do tworzyć strony wygenerowanych dokumentów

### <a name="review-the-second-downloaded-excel-template"></a>Przejrzyj drugi pobrany szablon Excela

1. W Excel otwórz pobrany wcześniej plik szablonu **ERIntrastatReportDemo2.xlsx**.
2. Porównaj ten szablon z szablonem **ERIntrastatReportDemo1.xlsx** i sprawdź, czy zawiera kilka nowych nazw programu Excel do tworzenia i wypełniania sekcji specyficznych dla strony w wygenerowanych dokumentach:

    - Zakres **ReportPageHeader** jest dodawany do tworzenia nagłówków stron.
    - Zakres **ReportPageFooter** jest dodawany do tworzenia stopek stron.
    - Komórka **ReportPageFooter\_PageLines** jest skonfigurowana do pokazywania liczby transakcji na stronie.
    - Komórka **ReportPageFooter\_PageAmount** jest skonfigurowana tak, aby pokazywać łączną liczbę transakcji na stronę.
    - Komórka **ReportPageFooter\_PageWeight** jest skonfigurowana do pokazywania łącznej wagi transakcji na stronę.
    - Komórka **ReportPageFooter\_RunningCounterLines** jest skonfigurowana do pokazywania uruchomionego licznika transakcji od początku raportu za pośrednictwem bieżącej strony.
    - Komórka **ReportPageFooter\_RunningTotalAmount** jest skonfigurowana do pokazywania sumy bieżącej dla wszystkich transakcji od początku raportu do bieżącej strony.
    - Komórka **ReportPageFooter\_RunningTotalWeight** jest skonfigurowana tak, aby pokazywać wagę sumy bieżącej dla transakcji od początku raportu do bieżącej strony.

    ![Układ szablonu Excel 2 w aplikacji klasycznej.](./media/er-paginate-excel-reports-template2a.gif)

    Komórka **CommodityCode** w tym szablonie jest skonfigurowana do oznaczania tekstu komórki komórki. Ponieważ wiersz szczegółów transakcji jest skonfigurowany tak, aby automatycznie dopasowywał się do wysokości wiersza, wysokość całego wiersza musi się automatycznie zmieniać, gdy tekst w komórce **CommodityCode** jest zawijany.

    ![Komórka CommodityCode skonfigurowana do tekstu komórki cell.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Powtórz wymianę obecnego szablonu Excel w niestandardowym formacie ER

1. Wykonaj kroki w sekcji [Zamień bieżący szablon programu Excel w niestandardowej sekcji formatu ER](#replace-template) tego tematu. W kroku 7 należy jednak wybrać plik **ERIntrastatReportDemo2.xlsx**.
2. Na stronie **Projektant formatów** rozwiń **Intrastat**.
3. Nazwij składniki formatu [zakresu](er-fillable-excel.md#range-component), które zostały dodane do edytowalnego formatu ER w celu zsynchronizowania struktury ze strukturą zastosowanego szablonu programu Excel:

    1. Wybierz składnik **Zakres** skojarzony z nazwą programu Excel **ReportPageHeader**.
    2. Na karcie **Format** w polu **Nazwa** wprowadź **nagłówek strony raportu**.
    3. Wybierz składnik **Zakres** skojarzony z nazwą programu Excel **ReportPageFooter**.
    4. Na karcie **Format** w polu **Nazwa** wprowadź **Stopka strony raportu**.

4. Wybierz opcję **Zapisz**.

![Struktura formatu w projektancie formatu ER po zastąpieniu szablonu programu Excel.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>Zmień strukturę formatu w celu zaimplementowania numeracji stronicowania dokumentu

1. Na stronie **Projektant formatów** w drzewie formatów w lewym okienku wybierz składnik główny **Intrastat**.
2. Wybierz opcję **Dodaj**.
3. W oknie dialogowym **Dodawanie** zaznacz składnik [strony](er-fillable-excel.md#page-component) w grupie składników programu **Excel**.
4. W oknie dialogowym **Właściwości składnika** w polu **Nazwa** wpisz **Zgłoś stronę**. Następnie wybierz opcję **OK**.
5. Aby użyć składnika **nagłówka strony raportu** jako nagłówka strony na każdej generowanej stronie, należy wykonać następujące czynności:

    1. Wybierz składnik **nagłówka strony raportu**, a następnie wybierz **opcję Wytnij**.
    2. Wybierz składnik **Strona raportu**, a następnie wybierz **Wklej**.
    3. Rozwiń **stronę raportu**.
    4. Aby wymusić, by komponent **Strona** [traktował](er-fillable-excel.md#page-component-structure) ten zakres jako nagłówek strony, wybierz **Zgłoś nagłówek strony**, a następnie na karcie **Format** wybierz **Kierunek replikacji** wybierz **Brak replikacji**.

6. Aby tworzyć strony wygenerowanego dokumentu, tak aby uwzględnić zawartość wierszy raportu, należy wykonać następujące czynności:

    1. Wybierz składnik **Wiersze raportu**, a następnie wybierz **opcję Wytnij**.
    2. Wybierz składnik **Strona raportu**, a następnie wybierz **Wklej**.

7. Aby dołączyć stopkę raportu po wierszach raportu, ale przed ostatnią stopką strony, wykonaj następujące kroki:

    1. Wybierz składnik **Stopka raportu**, a następnie wybierz **opcję Wytnij**.
    2. Wybierz składnik **Strona raportu**, a następnie wybierz **Wklej**.

8. Aby użyć składnika **Stopka strony raportu** jako stopki strony na każdej generowanej stronie, należy wykonać następujące czynności:

    1. Wybierz składnik **Stopka strony raportu**, a następnie wybierz **opcję Wytnij**.
    2. Wybierz składnik **Strona raportu**, a następnie wybierz **Wklej**.
    3. Aby wymusić, by komponent **Strona** [traktował](er-fillable-excel.md#page-component-structure) ten zakres jako stopkę strony, wybierz **Zgłoś stopkę strony**, a następnie na karcie **Format** wybierz **Kierunek replikacji** wybierz **Brak replikacji**.

![Struktura formatu w projektancie formatu ER po zaimplementowaniu stronicowania dokumentu.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Dodaj źródła danych w celu obliczenia sum stopki strony

Należy skonfigurować nowe źródła danych, aby obliczyć sumę stron, licznik bieżący i sumy bieżące oraz wyświetlić je w sekcji stopki strony. W tym celu zaleca się korzystanie ze źródeł danych [gromadzenia danych](er-data-collection-data-sources.md).

1. Na stronie **Projektant formatów** wybierz kartę **mapowanie.**
2. Wybierz znowu opcję **Dodaj poziom główny**, a następnie wykonaj następujące kroki:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Ogólne** wybierz pozycję **Pusty kontener**.
    2. W oknie dialogowym **Właściwości źródła danych Pusty kontener** w polu **Nazwa** wprowadź wartość **Suma**.
    3. Kliknij przycisk **OK**.

3. Wybierz opcję **Suma** źródła danych, **dodaj**, a następnie wykonaj następujące czynności:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Ogólne** wybierz pozycję **Pusty kontener**.
    2. W oknie dialogowym **Właściwości źródła danych Pusty kontener** w polu **Nazwa** wprowadź wartość **Strona**.
    3. Kliknij przycisk **OK**.

4. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Ogólne** wybierz pozycję **Pusty kontener**.
    2. W oknie dialogowym **Właściwości źródła danych Pusty kontener** w polu **Nazwa** wprowadź wartość **Uruchomione**.
    3. Kliknij przycisk **OK**.

5. Wybierz opcję **Suma.Strona** źródła danych, **dodaj**, a następnie wykonaj następujące czynności:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Funkcje** wybierz pozycję **zbieranie danych**.
    2. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **Ilość**.
    3. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
    4. Ustawienie opcji **Zbierz wszystkie wartości** na wartość **Tak**.
    5. Kliknij przycisk **OK**.

6. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Funkcje** wybierz pozycję **zbieranie danych**.
    2. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **Waga**.
    3. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
    4. Ustawienie opcji **Zbierz wszystkie wartości** na wartość **Tak**.
    5. Kliknij przycisk **OK**.

7. Wybierz opcję **Total.Running** źródła danych, **Dodaj**, a następnie wykonaj następujące czynności:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Funkcje** wybierz pozycję **zbieranie danych**.
    2. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **Ilość**.
    3. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
    4. Ustawienie pola **Zbierz wszystkie wartości** na wartość **Tak**.
    5. Kliknij przycisk **OK**.

8. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Funkcje** wybierz pozycję **zbieranie danych**.
    2. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **Waga**.
    3. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
    4. Ustawienie pola **Zbierz wszystkie wartości** na wartość **Tak**.
    5. Kliknij przycisk **OK**.

9. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Funkcje** wybierz pozycję **zbieranie danych**.
    2. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **Wiersze**.
    3. W polu **Typ elementu** wybierz opcję **Liczba całkowita**.
    4. Ustawienie pola **Zbierz wszystkie wartości** na wartość **Tak**.
    5. Kliknij przycisk **OK**.

10. Wybierz opcję **Zapisz**.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Dodaj źródła danych, aby kontrolować widoczność stopki strony

Jeśli planujesz kontrolować widoczność stopki strony i nie planujesz umieszczać stopki na ostatniej stronie, jeśli zawiera ona transakcje, skonfiguruj nowe źródło danych, aby obliczyć wymagany licznik bieżący.

1. Na stronie **Projektant formatów** wybierz kartę **mapowanie.**
2. Wybierz źródło danych **Total.Running**, wybierz opcję **Dodaj**.
3. W oknie dialogowym **Dodawanie źródła danych** w sekcji **Funkcje** wybierz pozycję **zbieranie danych**.
4. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **Wiersze2**.
5. W polu **Typ elementu** wybierz opcję **Liczba całkowita**.
6. Ustawienie opcji **Zbierz wszystkie wartości** na wartość **Tak**.
7. Kliknij przycisk **OK**.
8. Wybierz opcję **Zapisz**.

![Dodano źródła danych w konstruktorze formatów ER.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Konfiguruj powiązania w celu zbierania wartości łącznych

1. Na stronie **Projektant formatów** w drzewie formatów rozwiń składnik **Wiersze raportu** i wybierz zagnieżdżony składnik **wartości faktury**.
2. Wybierz opcję **Edytuj formułę**.
3. Zmień formułę powiązania z `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` na `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > Oprócz umieszczenia wartości kwoty w komórce programu Excel dla każdej iterated transakcji, to powiązanie zbiera wartość w źródle danych **Total.Page.Amount**.

4. Wybierz zagnieżdżony składnik **wagi**.
5. Wybierz opcję **Edytuj formułę**.
6. Zmień formułę powiązania z `@.'$RoundedWeight'` na `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > Oprócz umieszczania wartości wagi w komórce programu Excel dla każdej iterowanej transakcji to powiązanie zbiera wartość w źródle danych **Total.Page.Weight**.

![Skonfigurowane powiązania do zbierania łącznych wartości w projektancie formatu ER.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Konfigurowanie powiązań do wypełniania sum stopek stron

1. Na stronie **Projektant formatów** w drzewie formatów rozwiń składnik **Stopka strony raportu** i wybierz zagnieżdżony składnik **Zakres**, który odwołuje się do komórki programu Excel **ReportPageFooter\_PageAmount**, a następnie wykonaj następujące kroki:

    1. W drzewie źródeł danych w prawym okienku wybierz element **Total.Page.Amount.Sum()**.
    2. Wybierz **Powiąż**.
    3. Wybierz opcję **Edytuj formułę**.
    4. Zaktualizuj formułę na `Total.Page.Amount.Sum(false)`.

    > [!NOTE]
    > Należy określić argument tej funkcji jako **Fałsz**, aby zachować zebrane dane dla bieżącej strony, ponieważ są one niezbędne do obliczenia łącznej kwoty, łącznej liczby wierszy na stronę oraz uruchomienia licznika wierszy.

2. W drzewie formatów wybierz zagnieżdżony składnik **Zakresu**, który odwołuje się do komórki programu Excel **ReportPageFooter\_PageWeight**, a następnie wykonaj następujące czynności:

    1. W drzewie źródeł danych w prawym okienku wybierz element **Total.Page.Weight.Sum()**.
    2. Wybierz **Powiąż**.
    3. Wybierz opcję **Edytuj formułę**.
    4. Zaktualizuj formułę na `Total.Page.Weight.Sum(false)`.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Skonfiguruj powiązania, aby wypełnić sumy bieżące na stronie

1. Na stronie **Projektant formatów** w drzewie formatów rozwiń składnik **Stopka strony raportu** i wybierz zagnieżdżony składnik **Zakres**, który odwołuje się do komórki programu Excel **ReportPageFooter\_RunningTotalAmount**, a następnie wykonaj następujące kroki:

    1. W drzewie źródeł danych w prawym okienku wybierz element **Total.Running.Amount.Collect()**.
    2. Wybierz **Powiąż**.
    3. Wybierz opcję **Edytuj formułę**.
    4. Zaktualizuj formułę na `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`.

    > [!NOTE]
    > Operand `Total.Running.Amount.Sum(false)` zwraca poprzednio zebraną sumę bieżącą. Operand `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` zwraca całkowitą kwotę bieżącej strony. Musisz określić argument funkcji zagnieżdżonej drugiego operandu jako **Prawda**, aby zresetować kolekcję danych `Total.Page.Amount` zaraz po umieszczeniu tej wartości w `Total.Running.Amount` prowadzenie całkowitej kolekcji. Określony argument musi rozpocząć od zbierania sumy następnej strony od wartości 0 (zero).
    >
    > Funkcja `Total.Running.Amount.Sum(false)` jest wywoływana w celu wprowadzenia sumy bieżącej w komórce Excel **ReportPageFooter\_RunningTotalAmount** na bieżącej stronie.

2. W drzewie formatów wybierz zagnieżdżony składnik **Zakresu**, który odwołuje się do komórki programu Excel **ReportPageFooter\_RunningTotalWeight**, a następnie wykonaj następujące czynności:

    1. W drzewie źródeł danych w prawym okienku wybierz element **Total.Running.Weight.Collect()**.
    2. Wybierz **Powiąż**.
    3. Wybierz opcję **Edytuj formułę**.
    4. Zaktualizuj formułę na `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Skonfiguruj powiązania, aby wypełnić licznik uruchomionych stron

1. Na stronie **Projektant formatów** w drzewie formatów rozwiń składnik **Stopka strony raportu** i wybierz zagnieżdżony składnik **Zakres**, który odwołuje się do komórki programu Excel **ReportPageFooter\_RunningCounterLines**.
2. Wybierz opcję **Edytuj formułę**.
3. Dodaj formułę `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`.

    > [!NOTE]
    > Ta formuła zwraca liczbę zebranych wartości kwot dla całego raportu. Ta liczba jest równa liczbie transakcji, które zostały w danej chwili poddane iteracji. Równocześnie formuła gromadzi zwróconą wartość w kolekcji **Total.Running.Lines**.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Skonfiguruj powiązania, aby wypełnić licznik w stopce strony

1. Na stronie **Projektant formatów** w drzewie formatów rozwiń składnik **Stopka strony raportu** i wybierz zagnieżdżony składnik **Zakres**, który odwołuje się do komórki programu Excel **ReportPageFooter\_PageLines**.
2. Wybierz opcję **Edytuj formułę**.
3. Dodaj formułę `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`.

    > [!NOTE]
    > Ta formuła oblicza liczbę transakcji na bieżącej stronie jako różnicę między liczbą transakcji, która została zebrana w **Total.Page.Amount.Result** dla całego raportu a liczbą transakcji, które zostały zapisane w tym etap w **Total.Running.Lines.Sum**. Ponieważ liczba transakcji na bieżącej stronie jest przechowywana w tabeli **Total.Running.Lines** w powiązaniu składnika **Zakres**, który odwołuje się do komórki programu Excel **ReportPageFooter\_RunningCounterLines**, liczba transakcji na bieżącej stronie nie jest jeszcze uwzględniana. Dlatego ta różnica jest równa liczbie transakcji na bieżącej stronie.

![Skonfigurowane powiązania do wypełniania licznika stopki strony w projektancie formatu ER.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Skonfiguruj widoczność komponentów

Możesz zmienić widoczność nagłówka i stopki strony na określonej stronie wygenerowanego dokumentu, aby ukryć następujące elementy:

- Nagłówek strony na pierwszej stronie, ponieważ nagłówek raportu zawiera już tytuły kolumn
- Nagłówek strony na dowolnej stronie, która nie zawiera transakcji, które mogą wystąpić dla ostatniej strony
- Stopka strony na dowolnej stronie, która nie zawiera transakcji, które mogą wystąpić dla ostatniej strony

Aby zmienić widoczność, zaktualizuj właściwość **Włączone** **nagłówka strony raportu** i **składników stopki strony raportu**.

1. Na stronie **Projektant formatów** w drzewie formatów rozwiń składnik **Strona raportu** i wybierz zagnieżdżony składnik **Nagłówek strony raportu**, a następnie wykonaj następujące kroki:

    1. Wybierz pozycję **Edytuj** dla pola **Włączone**.
    2. Na stronie **Projektant formuł** wprowadź w polu **Formuła** następującą wartość:

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. W drzewie formatów zaznacz składnik **stopki zagnieżdżonych stron raportu**, a następnie wykonaj następujące czynności:

    1. Wybierz pozycję **Edytuj** dla pola **Włączone**.
    2. Na stronie **Projektant formuł** wprowadź w polu **Formuła** następującą wartość:

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > Konstrukcja `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` służy do obliczania liczby transakcji na bieżącej stronie. Konstrukcja `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` służy do dodawania liczby transakcji na bieżącej stronie do kolekcji, aby poprawnie obsłużyć widoczność następnej strony stopka.
    >
    > Kolekcji `Total.Running.Lines` nie można tutaj ponownie użyć, ponieważ przetwarzana jest właściwość **Włączone** składnika podstawowego **po** przetwarzane są powiązania składników zagnieżdżonych. Podczas przetwarzania właściwości **Włączone** kolekcja `Total.Running.Lines` jest już powiększana o liczbę transakcji na bieżącej stronie.

3. Wybierz opcję **Zapisz**.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Wygeneruj raport kontrolny deklaracji Intrastat (aktualizowane)

1. Upewnij się, że na stronie **Intrastat** masz 24 transakcje. Powtórz kroki w sekcji [Generowanie raportu kontroli deklaracji Intrastat](#generate-intrastat-control-report) w tym temacie, aby wygenerować i przejrzeć raport kontroli.

    Wszystkie transakcje są prezentowane na pierwszej stronie. Sumy i liczniki strony są równe sumom i licznikom raportu. Zakres nagłówka strony jest ukryty na pierwszej stronie, ponieważ nagłówek raportu zawiera już tytuły kolumn. Nagłówek i stopka strony są ukryte na drugiej stronie, ponieważ ta strona nie zawiera żadnych transakcji.

    ![Wygenerowano dokument Excel w aplikacji na komputerze.](./media/er-paginate-excel-reports-document2.gif)

2. Na stronie **Intrastat** zaktualizuj dwie transakcje, zmieniając **kod pozycji** z **D00006** na **L0010**. Zwróć uwagę, że nazwa nowego produktu, **Para aktywnych głośników stereo**, jest dłuższa niż nazwa produktu oryginalnego, **Głośnik standardowy**. Ta sytuacja wymusza zawijanie tekstu w odpowiedniej komórce wygenerowanego dokumentu. Należy teraz zaktualizować paginację dokumentów oraz sumowanie i liczenie stron. Powtórz kroki w sekcji [Generowanie raportu kontroli deklaracji Intrastat](#generate-intrastat-control-report), aby wygenerować i przejrzeć raport kontroli.

    Aktualnie transakcje są prezentowane na dwóch stronach, a sumy i liczniki stron są poprawnie obliczane. Zakres nagłówka strony jest poprawnie ukryty na pierwszej stronie i widoczny na drugiej stronie. Stopka strony jest widoczna na obu stronach, ponieważ zawierają transakcje.

    ![Zaktualizowano wygenerowany dokument Excel w aplikacji desktopowej.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>Czy istnieje sposób na rozpoznanie, kiedy ostateczna strona jest przetwarzana przez składnik Format strony?

Składnik **strony** [nie udostępnia](er-fillable-excel.md#page-component-limitations) informacji o numerze przetwarzanej strony i łącznej liczbie stron w generowanym dokumencie. Mimo tego można skonfigurować [formuły](er-formula-language.md) ER, które będą rozpoznawały stronę końcową. Oto przykład:

- Oblicz łączną liczbę transakcji, które zostały już przetworzone za pomocą składnika **strony raportu**. Możesz wykonać to obliczenie za pomocą formuły `COUNT(Total.Page.Amount.Result)`. 
- Oblicz łączną liczbę transakcji, które muszą zostać przetworzone, na podstawie powiązania `model.CommodityRecord` skonfigurowanego dla składnika **Wiersze raportu**. Możesz wykonać to obliczenie za pomocą formuły `COUNT(model.CommodityRecord)`.
- Porównanie dwóch cyfr w celu rozpoznania strony końcowej. Gdy obie wartości są takie same, generowana jest strona końcowa.

> [!NOTE]
> Zaleca się stosowanie tej metody tylko wtedy, gdy właściwość **Włączona** składnika **wierszy raportu** nie zawiera formuły, która może zwracać Wartość [False](er-formula-supported-data-types-primitive.md#boolean) w czasie wykonywania dla niektórych iterowanych [rekordów](er-formula-supported-data-types-composite.md#record) na [liście rekordów](er-formula-supported-data-types-composite.md#record-list) powiązanych.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel](er-fillable-excel.md)
- [Korzystanie ze źródeł danych DATA COLLECTION w formatach raportowania elektronicznego (ER)](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
