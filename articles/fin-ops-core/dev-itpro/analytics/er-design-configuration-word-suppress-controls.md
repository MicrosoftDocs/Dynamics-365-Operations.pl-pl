---
title: Pomijanie formantów zawartości programu Word w generowanych raportach
description: W tym artykule wyjaśniono, jak skonfigurować format raportowania elektronicznego w celu generowania raportów jako plików Microsoft Word, w których są pomijane formanty zawartości.
author: kfend
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.search.form:
- ERWorkspace, ERSolutionTable, EROperationDesigner
- LedgerJournalTable, LedgerJournalTransVendPaym
ms.openlocfilehash: 8787d43a0c453d49dd1d0efcbb7b5d276721be9e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267323"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Pomijanie formantów zawartości programu Word w generowanych raportach

[!include [banner](../includes/banner.md)]

Aby generować raporty jako dokumenty Microsoft Word, musisz zaprojektować szablon raportów jako dokument Word. Ten szablon musi zawierać kontrolki zawartości programu Word jako symbole zastępcze dla danych, które zostaną wypełnione w czasie wykonywania. Aby użyć dokumentu Word, który jest tworzony jako szablon dla twoich raportów, możesz [skonfigurować](er-design-configuration-word.md) nowe [rozwiązanie](er-quick-start1-new-solution.md) [Raportowania elektronicznego (ER)](general-electronic-reporting.md). To rozwiązanie musi zawierać [konfigurację](general-electronic-reporting.md#Configuration) zawierającą składnik formatu ER. Ten format raportu ER musi być skonfigurowany do używania zaprojektowanego szablonu do generowania raportów.

W wersji 10.0.6 i nowszych Dynamics 365 Finance możesz skonfigurować formuły w formacie ER, aby pomijać niektóre kontrolki zawartości programu Word w generowanych dokumentach.

Poniższe kroki wyjaśniają, w jaki sposób użytkownik przypisany do roli administratora systemu lub konsultanta funkcjonalnego raportowania elektronicznego może skonfigurować format ER, który generuje raporty jako pliki programu Word i pomija niektóre elementy sterujące zawartością w wygenerowanych raportach, które zostały skonfigurowane za pomocą szablonu programu Word.

Kroki można wykonać na danych firmy GBSI.

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać te kroki, musisz najpierw wykonać kroki opisane w następujących przewodnikach po zadaniach:

- [Projektowanie konfiguracji do generowania raportów w formacie OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Ponowne użycie konfiguracji modułu Raportowanie elektroniczne z szablonami programu Excel do generowania raportów w formacie programu Word](./tasks/er-design-configuration-word-2016-11.md)

Po ukończeniu kroków tych przewodników po zadaniach przygotowane zostaną następujące elementy:

- **Raport przykładowego arkusza skonfigurowany** formatu ER do generowania dokumentu w formacie programu Word
- Wersja robocza **Przykładowego arkusza formatu raportu** ER, który jest oznaczony jako **Możliwy do uruchomienia**
- **Elektroniczna** metoda płatności skonfigurowana do używania formatu **Raportu przykładowego arkusza** ER do przetwarzania płatności dostawców

Musisz również pobrać i zapisać następujący szablon przykładowego raportu:

- [Ograniczony szablon raportu 2 o płatnościach (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/1/9/b/19b36e39-861a-414e-9150-9880d9d2487c/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>Przeglądanie pobranego szablonu programu Word

1. W aplikacji programu Word otwórz pobrany wcześniej plik szablonu **SampleVendPaymDocReportBounded2.docx**.
2. Sprawdź, czy plik szablonu zawiera sekcję podsumowania, która pokazuje łączne kwoty płatności dla każdego kodu waluty, który został osiągnięty w przetworzonych płatnościach.

    - Sekcja podsumowania znajduje się w oddzielnej tabeli dokumentu programu Word.
    - Pierwszy wiersz tej tabeli zawiera nagłówki kolumn tabeli jako nagłówki sekcji.
    - Drugi wiersz tej tabeli zawiera powtarzającą się kontrolkę zawartości jako szczegóły sekcji.
    - Ta kontrolka zawartości jest zamapowana na pole **SummaryLines** w niestandardowej części XML **Raportu**.
    - Na podstawie tego mapowania kontrola zawartości jest skojarzona z elementem **SummaryLines** w edytowalnym formacie raportu ER.

    > [!NOTE]
    > Powtarzający się formant zawartości jest otagowany przez klucz **SummaryLines**, który pasuje do pola niestandardowej części XML, do której została zmapowana.

    ![Układ szablonu programu Word.](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Zaznaczenie istniejącej konfiguracji raportu ER

W następnych krokach ponownie użyjesz istniejącej konfiguracji ER skonfigurowanej po wykonaniu kroków opisanych we wcześniej wspomnianych przewodnikach po zadaniach.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model płatności**, a potem wybierz **Przykładowy raport arkusza**.
4. Wybierz pozycję **Konstruktor**, aby edytować wersję roboczą wybranego formatu ER.

## <a name="replace-the-current-template-with-the-new-template"></a>Zastąp bieżący szablon nowym szablonem

Obecnie plik SampleVendPaymDocReportBounded.docx jest używany jako szablon do generowania danych wyjściowych w formacie Word. W kolejnych krokach zastąpisz ten szablon programu Word nowym szablonem programu Word, SampleVendPaymDocReportBounded2.docx, który został pobrany wcześniej.

1. Na stronie **Projektant formatów** wybierz opcję **Załączniki**.
2. Na stronie **Załączniki** wybierz pozycję **Usuń**, aby usunąć istniejący szablon.
3. Wybierz **Tak**, aby potwierdzić usunięcie.
4. Wybierz pozycję **Nowy** \> **Plik**.
5. Wybierz pozycję **Przeglądaj**, a następnie przejdź do pliku **SampleVendPaymDocReportBounded2.docx**, który został pobrany wcześniej.
6. Kliknij przycisk **OK**.
7. Zamknij stronę **Załączniki**.
8. Na stronie **Projektant formatów** w polu **Szablon** wprowadź lub wybierz plik **SampleVendPaymDocReportBounded2.docx**.

## <a name="run-the-format-to-create-word-output"></a>Uruchomienie formatu w celu utworzenia danych wyjściowych programu Word

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności**.
2. Na stronie **Płatności dostawcy** na karcie **Lista** zaznacz wszystkie płatności.
3. Wybierz pozycję **Stan płatności** \> **Brak**.
4. Wybierz **Generuj płatności**.
5. W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.
6. W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.
7. Kliknij przycisk **OK**.
8. W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK** i analizuj wygenerowane dane wyjściowe.

    ![Płatności do przetwarzania na stronie Płatności dostawcy.](./media/er-design-configuration-word-suppress-controls-image2.gif)

    Wynik jest prezentowany w formacie programu Word i zawiera sekcję podsumowania.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>Skonfiguruj edytowalny format, aby pomijać sekcję podsumowania

Jeśli chcesz pominąć sekcję podsumowania w wygenerowanym dokumencie, na podstawie żądania użytkownika, który uruchamia ten format ER, musisz zmodyfikować edytowalny format ER.

1. Przejdź do **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne** i otwórz wersję roboczą formatu raportowania elektronicznego w celu edycji.
2. Wybierz **Raportowanie konfiguracji**. 
3. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model płatności** \> **Przykładowy raport arkusza**.
4. Wybierz opcję **Konstruktor**.
5. Na stronie **Projektant formatów** rozwiń pozycję **Word** i wybierz pozycję **SummaryLines**.
6. Na karcie **Mapowanie** dodaj nowe źródło danych, aby w czasie wykonywania zadać pytanie, czy sekcja podsumowania ma zostać pominięta:

    1. Wybierz **Dodaj element główny**.
    2. W oknie dialogowym **Dodawanie źródła danych** wybierz opcję **Ogólne\Parametr wejściowy użytkownika**, aby otworzyć okno dialogowe Właściwości źródła danych **Parametr wejściowy użytkownika**.
    3. W polu **Nazwa** wpisz **uipSuppress**.
    4. W polu **Etykieta wprowadź** sekcję **Pomiń podsumowanie**.
    5. W polu **Nazwa typu danych w programie Operations** wybierz lub wprowadź wartość **NoYes**.
    6. Kliknij przycisk **OK**.

7. Następnie należy dodać nowe źródło danych typu **Kod NoYes**:

    1. Wybierz **Dodaj element główny**.
    2. W oknie dialogowym **Dodawanie źródła danych** wybierz opcję **Dynamics 365 for Operations\Wyliczenie**, aby otworzyć okno dialogowe **Właściwości źródła danych „Wyliczenie”**.
    3. W polu **Nazwa** wpisz **enumNoYes**.
    4. W polu **Etykieta wprowadź** sekcję **Pomiń opcje**.
    5. W polu **Nazwa typu danych w programie Operations** wybierz lub wprowadź wartość **NoYes**.
    6. Kliknij przycisk **OK**.

8. Dla wybranego elementu formatu **SummaryLines** skonfiguruj formułę, aby określić, kiedy ma zostać pominięta kontrola zawartości programu Word skojarzona z wybranym elementem formatu:

    1. N karcie **Mapowanie** w sekcji **Usunięte** wybierz **Edytuj**, aby otworzyć kartę **[Projektant formuł](general-electronic-reporting-formula-designer.md)**.
    2. W polu **Formuła** wprowadź następujące `uipSuppress = enumNoYes.Yes`.
    3. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.

        > [!NOTE]
        > Ta formuła zostanie zastosowana do wygenerowanego dokumentu **po uruchomieniu wszystkich innych elementów formatu**. Aby zastosować tę formułę, w generowanym dokumencie znajduje się formant zawartości programu Word, który jest oznaczony jako element formatu, dla których jest skonfigurowana formuła (w tym przypadku **SummaryLines**). Ta kontrola zawartości zostanie całkowicie usunięta wraz z wierszem w tabeli programu Word, który ją zawiera. Wiersz szczegółów sekcji podsumowania jest usuwany z wygenerowanego dokumentu.
        >
        > W czasie projektowania można skonfigurować formułę **Usunięta** dla elementu formatu, nawet jeśli w szablonie programu Word nie ma formantu zawartości, który jest używany, ma znacznik, który pasuje do nazwy elementu formatu, dla których skonfigurowano właściwość **Usunięte**. Podczas sprawdzania poprawności formatu w czasie projektowania jest wyświetlane [ostrzeżenie](er-components-inspections.md#i14) o niezgodności.
        >
        > W czasie wykonywania występuje wyjątek, jeśli żaden formant zawartości w szablonie programu Word, który jest używany, ma znacznik, który pasuje do nazwy elementu formatu, dla których skonfigurowano właściwość **Usunięte**.

    4. Na karcie **Mapowanie** w sekcji **Usunięte** dla opcji **Z elementem nadrzędnym** ustaw wartość **Tak**.

        > [!NOTE]
        > Musisz ustawić tę opcję na wartość **Tak**, aby usunąć całą tabelę programu Word jako obiekt nadrzędny wiersza, który zawiera szczegóły sekcji podsumowania. Jeśli zostanie ustawiona opcja **Nie**, wiersz nagłówka sekcji pozostanie w generowanym dokumencie.

9. Wybierz **Zapisz**, by zapisać zmiany w formacie do edycji.

    ![Wygenerowane dane wyjściowe w formacie programu Word.](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Uruchomienie zmodyfikowanego formatu w celu utworzenia danych wyjściowych programu Word

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności**.
2. Wybierz utworzony przez siebie arkusz płatności, a następnie wybierz **Wiersze**.
3. Na stronie **Płatności dostawcy** zaznacz wszystkie wiersze, a następnie wybierz **Stan płatności** \> **Brak**.
4. Wybierz **Generuj płatności**.
5. W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.
6. W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.
7. Kliknij przycisk **OK**.
8. W oknie dialogowym **Parametry raportu elektronicznego** w polu **Pomiń podsumowanie** wybierz opcję **Tak**.
9. Wybierz przycisk **OK** i przeanalizuj wygenerowane dane wyjściowe.

    ![Wygenerowane dane wyjściowe w formacie programu Word.](./media/er-design-configuration-word-suppress-controls-image4.gif)

    Zauważ, że dane wyjściowe nie zawierają sekcji podsumowania, ponieważ została pominięta.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Projektowanie konfiguracji do generowania raportów w formacie OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Projektowanie nowej konfiguracji modułu Raportowanie elektroniczne w celu generowania raportów w formacie programu Word](er-design-configuration-word.md)
- [Ponowne użycie konfiguracji modułu Raportowanie elektroniczne z szablonami programu Excel do generowania raportów w formacie programu Word](./tasks/er-design-configuration-word-2016-11.md)
- [Sprawdzanie skonfigurowanego składnika ER, aby zapobiec problemom w czasie wykonywania](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
