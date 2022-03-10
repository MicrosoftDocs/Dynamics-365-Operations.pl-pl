---
title: Ponowne używanie konfiguracji ER z szablonami programu Excel do generowania raportów w formacie programu Word
description: W tym temacie opisano sposób konfigurowania formatów raportów zaprojektowanych do generowania raportów jako skoroszytów programu Excel, tak aby raporty były generowane jako dokumenty programu Word.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de8286c7612cd588b28cf4667340374906962dde
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2022
ms.locfileid: "8324069"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Ponowne używanie konfiguracji ER z szablonami programu Excel do generowania raportów w formacie programu Word

[!include [banner](../../includes/banner.md)]

Aby generować raporty jako dokumenty programu Microsoft Word, można [skonfigurować](../er-design-configuration-word.md) nowy format [raportowania elektronicznego](../general-electronic-reporting.md) (ER). Można również ponownie użyć formatu ER, który pierwotnie został zaprojektowany w celu generowania raportów jako skoroszytów programu Excel. W takim przypadku należy zastąpić szablon programu Excel szablonem programu Word.

Poniższe procedury pokazują, w jaki sposób użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może skonfigurować format raportowania elektronicznego, aby generować raporty jako pliki programu Word, ponownie korzystając z formatu ER przeznaczonego do generowania raportów jako plików programu Excel.

Te procedury można wykonać na danych firmy GBSI.

## <a name="prerequisites"></a>Wymagania wstępne

W celu wykonania tych procedur należy najpierw kroki z przewodnika zadania [Projektowanie konfiguracji do generowania raportów w formacie OPENXML](er-design-reports-openxml-2016-11.md).

Należy również pobrać i lokalnie zapisać następujące szablony dla przykładowego raportu:

- [Szablon raportu o płatnościach (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Ograniczony szablon raportu o płatnościach (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

Te procedury mają być stosowane w przypadku funkcji dodanej w aplikacji Dynamics 365 for Operations w wersji 1611 (listopad 2016 r.).

## <a name="select-the-existing-er-report-configuration"></a>Zaznaczenie istniejącej konfiguracji raportu ER

1. W aplikacji Dynamics 365 Finance wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Upewnij się, że dostawca konfiguracji **Litware, Inc.** jest oznaczony jako **Aktywny**. Jeśli nie, wykonaj kroki opisane w przewodniku zadania [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).
3. Wybierz **Raportowanie konfiguracji**. Ponownie wykorzystasz istniejącą konfigurację ER, który została pierwotnie zaprojektowana do generowania danych wyjściowych raportu w formacie OPENXML.
4. Na stronie **Konfiguracje** w drzewie konfiguracji w okienku po lewej wybierz pozycję **Model płatności**, a potem wybierz **Przykładowy raport arkusza**.

    > [!NOTE]
    > Roboczą wersję wybranego formatu ER można edytować na skróconej karcie **Wersje**.

5. Wybierz opcję **Konstruktor**.
6. Na stronie **projektanta formatów** zwróć uwagę, że tytuł elementu formatu głównego wskazuje, że szablon programu Excel jest obecnie używany.

![Wybieranie istniejącej konfiguracji.](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>Przeglądanie pobranego szablonu programu Word

1. W aplikacji programu Word otwórz pobrany wcześniej plik szablonu **SampleVendPaymDocReport.docx**.
2. Sprawdź, czy ten szablon zawiera tylko układ dokumentu, który chcesz wygenerować jako dane wyjściowe raportowania elektronicznego.

![Układ szablonu programu Word w aplikacji na komputerze.](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Zamień szablon programu Excel na szablon programu Word i dodaj niestandardową część XML

Obecnie dokument programu Excel jest używany jako szablon do generowania danych wyjściowych w formacie OPENXML. Zastąpisz ten szablon szablonem programu Word (SampleVendPaymDocReport.docx), który został pobrany wcześniej. Rozszerzysz również szablonu programu Word przez dodanie niestandardowej części XML.

1. W aplikacji Finance na stronie **Projektant formatów** na karcie **Format** wybierz **Załączniki**.
2. Na stronie **Załączniki** wybierz pozycję **Usuń**, aby usunąć istniejący szablon programu Excel. Wybierz **Tak**, aby potwierdzić zmianę.
3. Wybierz pozycję **Nowy** \> **Plik**.

    > [!NOTE]
    > Musisz wybrać typ dokumentu [skonfigurowany](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) w parametrach ER, aby przechowywać szablony formatów ER.

4. Wybierz pozycję **Przeglądaj**, a następnie przejdź do pliku **SampleVendPaymDocReport.docx**, który został pobrany wcześniej.
5. Kliknij przycisk **OK**.
6. Zamknij stronę **Załączniki**.
7. Na stronie **Projektant formatów** w polu **Szablon** wprowadź lub wybierz plik **SampleVendPaymDocReport.docx**, aby użyć tego szablonu programu Word, a nie wcześniej używanego szablonu programu Excel.
8. Wybierz opcję **Zapisz**.

    Oprócz zapisania zmian w konfiguracji akcja **Zapisz** aktualizuje dołączony szablon programu Word. Hierarchiczna struktura zaprojektowanego formatu jest dodawana do dołączonego dokumentu programu Word jako nowa niestandardowa część w postaci kodu źródłowego XML o nazwie **Raport**. Dołączony szablon programu Word zawiera układ dokumentu, który zostanie wygenerowany jako dane wyjściowe modułu ER, oraz strukturę danych, które moduł raportowania elektronicznego umieści w tym szablonie podczas wykonywania.

9. Zauważ, że tytuł elementu formatu głównego wskazuje, że szablon programu Word jest obecnie używany.

    ![Zamienianie szablonu programu Excel na szablon programu Word i dodawanie niestandardowej części XML.](../media/er-design-configuration-word-2016-11-image03.gif)

10. Na karcie **format** wybierz opcję **załączniki**.

Możesz teraz zamapować elementy niestandardowej części XML **Raport** do formantów zawartości dokumentu programu Word.

Jeśli znasz proces projektowania dokumentów programu Word jako formularzy zawierających [kontrolki zawartości](/office/client-developer/word/content-controls-in-word) i mapowanych na elementy [niestandardowych części XML](/visualstudio/vsto/custom-xml-parts-overview), wykonaj wszystkie kroki następnej procedury w celu utworzenia dokumentu. Więcej informacji zawiera sekcja [Tworzenie formularzy, które użytkownicy wypełniają lub drukują w aplikacji Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). W przeciwnym razie pomiń następną procedurę.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Pobieranie dokumentu programu Word z niestandardową częścią XML i mapowanie danych

1. W aplikacji Finance na stronie **Załączniki** wybierz pozycję **Otwórz**, aby pobrać wybrany szablon z aplikacji Finance i zapisać go lokalnie jako dokument programu Word.
3. W aplikacji klasycznej Word otwórz pobrany właśnie dokument.
4. Na karcie **Deweloper** wybierz opcję **Okienko mapowania XML**.

    > [!NOTE]
    > Jeśli karta **Deweloper** nie jest wyświetlana na wstążce, dostosuj ją, aby dodać tę kartę.

5. W okienku **Mapowanie XML** w polu **Niestandardowa część XML** wybierz niestandardową część XML **Raport**.
6. Zamapuj elementy wybranej niestandardowej części XML **Raport** i kontrolki zawartości dokumentu programu Word.
7. Zapisz zaktualizowany dokument programu Word lokalnie jako plik **SampleVendPaymDocReportBounded.docx**.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Przeglądanie szablonu programu Word, w którym niestandardowy element XML jest mapowany na kontrolki zawartości

1. W aplikacji programu Word otwórz plik szablonu **SampleVendPaymDocReportBounded.docx**.
2. Sprawdź, czy ten szablon zawiera układ dokumentu, który chcesz wygenerować jako dane wyjściowe raportowania elektronicznego. Kontrolki zawartości używane jako symbole zastępcze danych, które będą wprowadzane w tym szablonie w czasie wykonywania w modelu ER, są oparte na mapowaniach skonfigurowanych między elementami niestandardowej części XML **Raport** a kontrolkami zawartości dokumentu programu Word.

![Podgląd szablonu programu Word w aplikacji na komputerze.](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Przekazywanie szablonu programu Word, w którym niestandardowy element XML jest mapowany na kontrolki zawartości

1. W aplikacji Finance na stronie **Załączniki** wybierz pozycję **Usuń**, aby usunąć szablon programu Word, który nie ma mapowań między elementami niestandardowej części XML **Raport** i kontrolkami zawartości. Wybierz **Tak**, aby potwierdzić zmianę.
2. Wybierz pozycję **Nowy** \> **Plik**, aby dodać nowy plik szablonu zawierający mapowania między elementami niestandardowej części XML **Raport** i kontrolkami zawartości.

    > [!NOTE]
    > Musisz wybrać typ dokumentu [skonfigurowany](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) w parametrach ER, aby przechowywać szablony formatów ER.

3. Wybierz pozycję **Przeglądaj**, a następnie odszukaj i wybierz plik **SampleVendPaymDocReportBounded.docx** pobrany lub przygotowany przez wykonanie procedury w sekcji [Pobieranie dokumentu programu Word, która zawiera niestandardową część XML, w celu mapowania danych](#get-word-doc).
4. Kliknij przycisk **OK**.
5. Zamknij stronę **Załączniki**.
6. Na stronie **Projektant formatów** w polu **Szablon** wybierz pobrany właśnie dokument.
7. Wybierz opcję **Zapisz**.
8. Zamknij stronę **Projektowanie formuły**.

## <a name="mark-the-configured-format-as-runnable"></a>Oznaczanie skonfigurowanego formatu jako możliwego do uruchomienia

Aby uruchomić wersję roboczą formatu edytowalnego, należy oznaczyć go jako [możliwy do uruchomienia](../er-quick-start2-customize-report.md#MarkFormatRunnable).

1. W aplikacji Finance na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
2. W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.
3. W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była możliwa do edycji.
4. W przypadku aktualnie wybranej konfiguracji **Przykładowy raport arkusza** ustaw opcję **Uruchom wersję roboczą** na wartość **Tak**.
5. Wybierz opcję **Zapisz**.

## <a name="run-the-format-to-create-output-in-word-format"></a>Uruchamianie formatu w celu utworzenia danych wyjściowych w formacie programu Word

1. W aplikacji Finance przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności**.
2. W wprowadzonym wcześniej arkuszu płatności wybierz opcję **Wiersze**.
3. Na stronie **Płatności dostawcy** zaznacz wszystkie wiersze w siatce.
4. Wybierz pozycję **Stan płatności** \> **Brak**.

    ![Płatności do przetwarzania na stronie Płatności dostawcy.](../media/er-design-configuration-word-2016-11-image05.png)

5. W okienku akcji wybierz pozycję **Generuj płatności**.
6. W wyświetlonym oknie dialogowym wykonaj następujące kroki:

    1. W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.
    2. W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.
    3. Kliknij przycisk **OK**.

7. W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.
8. Wygenerowane dane wyjściowe są przedstawione w formacie programu Word i zawierają szczegóły przetworzonych płatności. Zbadaj wygenerowane dane wyjściowe.

    ![Wygenerowane dane wyjściowe w formacie programu Word.](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Projektowanie nowej konfiguracji modułu Raportowanie elektroniczne w celu generowania raportów w formacie programu Word](../er-design-configuration-word.md)
- [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
