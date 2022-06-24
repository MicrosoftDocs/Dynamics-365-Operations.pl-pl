---
title: Dobór stylu interfejsu wykonania hal produkcyjnych
description: W tym artykule opisano sposób konfigurowania formantów formularza, tak aby zostały do nich zastosowane domyślne style wykonania hal produkcyjnych.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ad6ecd591353fe8ddc1a5b9049d65491fb58e98a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859148"
---
# <a name="style-the-production-floor-execution-interface"></a>Dobór stylu interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania formantów formularza, tak aby zostały do nich zastosowane domyślne style wykonania hal produkcyjnych.

## <a name="forms-and-dialogs"></a>Formularze i okna dialogowe

Style można stosować do formularza lub okna dialogowego tylko wtedy, gdy są spełnione następujące wymagania:

- Jeśli formularz ma przypominać istniejący formularz postępu raportu, nazwa formularza lub okna dialogowego musi rozpoczynać się od `JmgProductionFloorExecutionCustomInputDialog`.
- Formularz lub okno dialogowe może zawierać część formularza szczegółów. Aby zastosować do niego style, nazwa części formularza szczegółów musi rozpoczynać się od `JmgProductionFloorExecutionCustomDetailsDialog`.
- Jeśli formularz lub okno dialogowe powinno mieć widok prosty, nazwa widoku prostego musi rozpoczynać się od `JmgProductionFloorExecutionCustomDialog`. Przykładami formularzy z widokiem prostym są formularze startowe i formularz działań pośrednich.
- Wszystkie formanty w oknie dialogowym muszą być skonfigurowane w sposób opisany w tym artykule.

> [!IMPORTANT]
> Funkcje wymienione w pierwszych dwóch punktach tej listy wymagają rozwiązania Supply Chain Management w wersji 10.0.19 lub nowszej.

Style można zastosować do przycisku **OK** w oknie dialogowym tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `OkButtonGroup`.

Style można zastosować do przycisku **Anuluj** w polu dialogowym tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `CancelButtonGroup`.

### <a name="header"></a>Nagłówek

Na poniższej ilustracji przedstawiono typowy formularz lub nagłówek okna dialogowego.

![Typowy formularz lub nagłówek okna dialogowego.](media/pfe-styles-header.png "Typowy formularz lub nagłówek okna dialogowego")

W programie Visual Studio nagłówki są tworzone przy użyciu struktury, takiej jak pokazana na poniższej ilustracji.

![Typowa struktura kodu do tworzenia nagłówka.](media/pfe-styles-header-code-structure.png "Typowa struktura kodu do tworzenia nagłówka")

Aby dodać tekst do nagłówka, użyj kodu, takiego jak poniższy przykład.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

Podczas wpisania kodu nagłówka należy zastosować następujące reguły:

- Nazwa grupy głównej musi mieć nazwę `TableRowHeaderGroup`.
- Każdy blok tekstu (oddzielony przecinkami) musi rozpoczynać się od `HeaderFieldWithSeparatorText`.
- Nazwisko musi zaczynać się od `HeaderFieldText`.
- `CaptionImage` można pominąć.

### <a name="progress-indicator"></a>Wskaźnik postępu

Możesz uwzględnić wskaźnik postępu, który jest wyświetlany po prawej stronie nagłówka. Na poniższej ilustracji przedstawiono wskaźnik postępu.

![Typowy wskaźnik postępu.](media/pfe-styles-header-progress.png "Typowy wskaźnik postępu")

Aby wyświetlić wskaźnik postępu, pole tekstowe musi mieć nazwę `ShowProgress`.

## <a name="grid"></a>Siatka

Style są stosowane automatycznie. Nie jest wymagana żadna konfigurowacja.

Siatka powinna mieć styl `TabularView`, a metoda `run()` w formularzu niestandardowym musi zostać nadpisana, ponieważ nowa siatka nie jest jeszcze obsługiwana. Dodaj następujący kod źródłowy języka.

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

Aby odświeżyć dane w głównym widoku, możesz użyć czegoś takiego jak `this.parmParentForm().updateLayout();` w metodzie `click` akcji. (Dla przykładu spójrz na klasę `JmgProductionFloorExecutionReportFeedbackAction`.) Upewnij się tylko, że `parmDataSource` jest ustawione w metodzie `init` nowego formularza (`formCaller.parmDataSource(this.dataSource(1));`). Przykładowy przykład można sprawdzić w formularzu `JmgProductionFloorExecutionMainGrid`.

## <a name="card-view"></a>Widok karty

Style można stosować do formantów widoku karty tylko wtedy, gdy są spełnione następujące wymagania:

- Każdy widok karty należy do grupy formularzy.
- Nazwa grupy rozpoczyna się od `CardGroup` (na przykład, `CardGroupJobsView`).

Na poniższej ilustracji przedstawiono widok karty bez formantów wewnątrz tego widoku.

![Widok karty bez elementów.](media/pfe-styles-empty-card.png)

Na poniższych ilustracjach przedstawiono widoki karty z formantami wewnątrz tych widoków.

![Karta z elementami, które pokazują Hz.](media/pfe-styles-elements.png)

![Karta z elementami dla żądania konserwacji.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Karta biznesowa

Style można stosować do formantów karty biznesowej tylko wtedy, gdy są spełnione następujące wymagania:

- Każda karta biznesowa należy do grupy formularzy.
- Nazwa grupy rozpoczyna się od `BusinessCardGroup` (na przykład, `BusinessCardGroupJobsList`).

Ustaw następujące właściwości na karcie biznesowej:

- **Styl:** *lista*
- **Rozszerzony styl:** *cardList*
- **Wybór wielokrotny:** *Nie*
- **Pokaż etykiety kolumn:** *Nie*

![Karta biznesowa.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Przycisk radiowy

Style można stosować do przycisków radiowych tylko wtedy, gdy są spełnione następujące wymagania:

- Każdy przycisk radiowy jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `RadioTextBelow` lub `RadioTextRight`, w zależności od miejsca, w którym ma się pojawiać tekst.

Ustaw następujące właściwości na przycisku radiowym:

- **Przycisk przełączania:** *Sprawdź*
- **Wartość przełączania:** *Włączone*, jeśli należy wybrać przycisk radio; w przeciwnym razie *Wyłączone*

Na poniższej ilustracji pokazano przykład, gdzie tekst jest widoczny poniżej przycisków radiowych.

![Przyciski radiowe z tekstem poniżej.](media/pfe-styles-radio-text-below.png)

Na poniższej ilustracji pokazano przykład, gdzie tekst jest widoczny po prawej stronie przycisków radiowych.

![Przyciski radiowe z tekstem po prawej stronie.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Przyciski radiowe w przeglądarce Internet Explorer

Style przycisków radiowych nie są obsługiwane w przeglądarce Internet Explorer. Na poniższej ilustracji przedstawiono, jak wyglądają przyciski radiowe w przeglądarce Internet Explorer.

![Przyciski radiowe w przeglądarce Internet Explorer.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Guziki

Style można stosować do przycisków tylko wtedy, gdy są spełnione następujące wymagania:

- Każda grupa przycisków jest zawarta w grupie formularzy. Wszystkie przyciski w grupie będą mieć ten sam styl.
- Brak wymagań dotyczących nazwy grupy.

Ustaw następujące właściwości na przyciskach:

- **Wyświetlanie przycisku:** *TextWithImageLeft*.
- **Normalny obraz:** Ta właściwość nie może być pusta. W tym przykładzie użyj *CoffeeScript*.
- **Tekst:** Ta właściwość nie może być pusta. W tym przykładzie użyj *Rozpocznij przerwę*.
- **Szerokość:** *auto* lub *sizeToContent*
- **Wysokość:** *auto* lub *sizeToContent*

### <a name="primary-button"></a>Przycisk podstawowy

Style można stosować do przycisku głównego tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `DefaultButtonGroup` lub `PrimaryButtonGroup` (na przykład, `DefaultButtonGroup10`).

![Przycisk podstawowy.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Przycisk pomocniczy

Style można stosować do przycisku dodatkowego tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy to **Prawy panel** lub nazwa grupy rozpoczyna się od `SecondaryButtonGroup`.

![Przycisk dodatkowy.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Przycisk trzeciej grupy

Style można stosować do przycisku trzeciej grupy tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy to **Lewy panel** lub nazwa grupy rozpoczyna się od `ThirdButtonGroup`.

![Przycisk trzeciej grupy.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Przycisk czwartej grupy

Style można stosować do przycisku czwartej grupy tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `FourthButtonGroup`.

Ustaw następujące właściwości na przycisku:

- **Wyświetlanie przycisku:** *TextOnly*.
- **Normalny obraz:** Ta właściwość musi być pusta.
- **Tekst:** Ta właściwość nie może być pusta. Na przykład użyj *widoku* lub *edycji*.
- **Szerokość:** *Automatycznie*.
- **Wysokość:** *Automatycznie*.

![Przycisk czwartej grupy.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Płaski przycisk

Style można stosować do płaskiego przycisku tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `FlatButtonGroup`.

Ustaw następujące właściwości na przycisku:

- **Wyświetlanie przycisku:** *ImageOnly*.
- **Normalny obraz:** Ta właściwość nie może być pusta. W tym przykładzie użyj *CoffeeScript*.
- **Tekst:** Ta właściwość musi być pusta.
- **Szerokość:** *auto* lub *sizeToContent*
- **Wysokość:** *auto* lub *sizeToContent*

![Płaski przycisk.](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>Przycisk Kontynuuj

Style można zastosować do przycisku Kontynuuj tylko wtedy, gdy spełnione są następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od `ContinueButtonGroup`.

Ustaw następujące właściwości na przycisku:

- **Wyświetlanie przycisku:** *ImageOnly*.
- **Normalny obraz:** *w przód*
- **Tekst:** Ta właściwość musi być pusta.
- **Szerokość:** *auto* lub *sizeToContent*
- **Wysokość:** *auto* lub *sizeToContent*

![Przycisk Kontynuuj.](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>Pole kombi

Pole kombi to kombinacja trzech formantów: formantu wprowadzania, przycisku, który umożliwia wyczyszczenie formantu wejściowego, oraz przycisku, który uruchamia wyszukiwanie.

Style można stosować do pola kombi tylko wtedy, gdy są spełnione następujące wymagania:

- Pole kombi jest zawarte w grupie formularzy.
- Nazwa grupy rozpoczyna się od `Combobox`.
- W obrębie grupy pierwszym formantem jest formant `AxFormStringControl`. Ten formant pokazuje bieżącą wartość i w tym miejscu użytkownik wprowadza wymaganą wartość.
- Drugim formantem jest `CommonButton`, a jego nazwa rozpoczyna się od `ClearButton`. Ten przycisk musi zawierać kod, który używa właściwości `enable` do pokazywania lub ukrywania tego przycisku. Na przykład aby wyświetlić lub ukryć przycisk **Wyczyść** podczas wpisywania informacji w formancie wejściowym, można użyć następującego kodu.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Powinna istnieć jedna metoda, w której dane są ustawiane w formancie wejściowym. Włącz przycisk **Wyczyść** w tej metodzie. Oto przykład.

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    Użyj następującego kody dla metody `clicked` przycisku **Wyczyść**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Ustaw wartość formantu wejściowego `AxFormStringControl`, gdy formularz zostanie zainicjowany za pomocą metody `init`. Jeśli ta wartość nie jest pusta, włącz przycisk **Wyczyść**. Jeśli ta wartość jest pusta, wyłącz przycisk **Wyczyść**.

- Trzecim formantem jest `CommonButton`, a jego nazwa rozpoczyna się od `SearchButton`.

Na poniższej ilustracji przedstawiono dwa formanty pól kombi. Pole kombi po lewej stronie ma puste pole tekstowe i przycisk **Wyczyść** jest wyłączony. Pole kombi po prawej stronie ma tekst w polu tekstowym i przycisk **Wyczyść** jest włączony.

![Pola kombi z przyciskiem Wyczyść i bez niego.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Szybkie filtrowanie

Formant szybkiego filtrowania powoduje dodanie pola wyszukiwania do strony. Do szybkiego filtrowania można stosować style, pod warunkiem że są spełnione następujące wymagania:

- Szybkie filtrowanie jest zawarte w grupie formularzy.
- Nazwa grupy rozpoczyna się od `SearchInputGroup`.
- W obrębie grupy pierwszym formantem jest formant `QuickFilter`. (W tej kontrolce użytkownik wprowadza ciąg wyszukiwania).
- Drugi formant to `FormStaticTextControl` nazwany `NumberOfResults`. (Ta kontrola jest opcjonalna. Jeśli jest uwzględniony, pokazuje liczbę znalezionych przedmiotów).
- Trzecim formantem jest `CommonButton`, a jego nazwa rozpoczyna się od `ClearButton`.

Na poniższej ilustracji przedstawiono dwa formanty szybkiego filtrowania. Szybkie filtrowanie po lewej stronie ma pusty szybkie filtrowanie, a liczba wyników nie jest widoczna. Szybki filtr po prawej stronie zawiera wyszukiwany ciąg i pokazuje liczbę wyników.

![Przykłady formantu szybkiego filtrowania z ciągiem wyszukiwania i bez niego.](media/pfe-styles-quick-filter.png "Przykłady formantu szybkiego filtrowania z ciągiem wyszukiwania i bez niego")

## <a name="center-align-elements-on-a-tab"></a>Elementy wyrównania do środka na karcie

Aby wyrównać elementy na środku karty, nazwa grupy musi się rozpoczynać od `TabContentGroup`, a grupa musi mieć następujące właściwości:

- **Tryb szerokości:** `SizeToAvailable`
- **Tryb wysokości:** `SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>Wyrównanie siatki, części szczegółów i szybkiego filtru

Aby dopasować siatkę, część szczegółów i szybki filtr tak, aby przypominały standardowy projekt, należy pamiętać o następujących elementach, gdy są ze sobą połączone:

- Jeśli siatka ma szybki filtr, siatka i szybki filtr powinny znaleźć się w obrębie grupy o nazwie, od których rozpoczyna się od `GridGroup`.
- Aby zastosować style do części szczegółów, nazwa grupy musi zaczynać się od `DetailInformationGroup`,

Na poniższej ilustracji przedstawiono typową siatkę z szybkim filtrem i częścią szczegółową po prawej stronie.

![Typowa siatka zawierająca szybki filtr i część szczegółową](media/pfe-styles-align-grid.png "Typowa siatka zawierająca szybki filtr i część szczegółową")

W programie Visual Studio siatkę, część szczegółową i szybki filtr można utworzyć przy użyciu struktury, takiej jak ta pokazana na poniższej ilustracji.

![Typowa struktura kodu, która wyrównuje siatkę, część szczegółową i szybki filtr](media/pfe-styles-header-code-structure2.png "Typowa struktura kodu, która wyrównuje siatkę, część szczegółową i szybki filtr")

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Dostosowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-customize.md)
- [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
