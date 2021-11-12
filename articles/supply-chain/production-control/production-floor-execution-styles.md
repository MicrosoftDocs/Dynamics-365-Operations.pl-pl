---
title: Dobór stylu interfejsu wykonania hal produkcyjnych
description: W tym temacie opisano sposób konfigurowania formantów formularza, tak aby zostały do nich zastosowane domyślne style wykonania hal produkcyjnych.
author: johanhoffmann
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 32e49458f6ea7c484bc4200e414d930381b31891
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652060"
---
# <a name="style-the-production-floor-execution-interface"></a>Dobór stylu interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania formantów formularza, tak aby zostały do nich zastosowane domyślne style wykonania hal produkcyjnych.

## <a name="forms-and-dialogs"></a>Formularze i okna dialogowe

Style można stosować do formularza lub okna dialogowego tylko wtedy, gdy są spełnione następujące wymagania:

- Jeśli formularz ma przypominać istniejący formularz postępu raportu, nazwa formularza lub okna dialogowego musi rozpoczynać się od **JmgProductionFloorExecutionCustomInputDialog**.
- Formularz lub okno dialogowe może zawierać część formularza szczegółów. Aby zastosować do niego style, nazwa części formularza szczegółów musi się rozpoczynać od **JmgProductionFloorExecutionCustomDetailsDialog**.
- Jeśli formularz lub okno dialogowe powinno mieć widok prosty, nazwa widoku prostego musi rozpoczynać się od **JmgProductionFloorExecutionCustomDialog**. Przykładami formularzy z widokiem prostym są formularze startowe i formularz działań pośrednich.
- Wszystkie formanty w oknie dialogowym muszą być skonfigurowane w sposób opisany w tym temacie.

> [!IMPORTANT]
> Funkcje wymienione w pierwszych dwóch punktach tej listy wymagają rozwiązania Supply Chain Management w wersji 10.0.19 lub nowszej.

Style można zastosować do przycisku **OK** w oknie dialogowym tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od **OkButtonGroup**.

Style można zastosować do przycisku **Anuluj** w polu dialogowym tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od **CancelButtonGroup**.

## <a name="grid"></a>Siatka

Style są stosowane automatycznie. Nie jest wymagana żadna konfigurowacja.

## <a name="card-view"></a>Widok karty

Style można stosować do formantów widoku karty tylko wtedy, gdy są spełnione następujące wymagania:

- Każdy widok karty należy do grupy formularzy.
- Nazwa grupy rozpoczyna się od **CardGroup** (na przykład **CardGroupJobsView**).

Na poniższej ilustracji przedstawiono widok karty bez formantów wewnątrz tego widoku.

![Widok karty bez elementów.](media/pfe-styles-empty-card.png)

Na poniższych ilustracjach przedstawiono widoki karty z formantami wewnątrz tych widoków.

![Karta z elementami, które pokazują Hz.](media/pfe-styles-elements.png)

![Karta z elementami dla żądania konserwacji.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Karta biznesowa

Style można stosować do formantów karty biznesowej tylko wtedy, gdy są spełnione następujące wymagania:

- Każda karta biznesowa należy do grupy formularzy.
- Nazwa grupy rozpoczyna się od **BusinessCardGroup** (na przykład **BusinessCardGroupJobsList**).

Ustaw następujące właściwości na karcie biznesowej:

- **Styl**: **lista**
- **Rozszerzony styl**: **cardList**
- **Wybór wielokrotny**: **Nie**
- **Pokaż etykiety kolumn**: **Nie**

![Karta biznesowa.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Przycisk radiowy

Style można stosować do przycisków radiowych tylko wtedy, gdy są spełnione następujące wymagania:

- Każdy przycisk radiowy jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od **RadioTextBelow** lub **RadioTextRight**, w zależności od miejsca, w którym ma się pojawiać tekst.

Ustaw następujące właściwości na przycisku radiowym:

- **Przycisk przełączania**: **Sprawdź**
- **Wartość przełączania**: **Włączone**, jeśli należy wybrać przycisk radio; w przeciwnym razie **Wyłączone**

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

- **Wyświetlanie przycisku**: **TextWithImageLeft**.
- **Normalny obraz**: Ta właściwość nie może być pusta. W tym przykładzie użyj **CoffeeScript**.
- **Tekst**: Ta właściwość nie może być pusta. W tym przykładzie użyj **Rozpocznij przerwę**.
- **Szerokość**: **Automatycznie**.
- **Wysokość**: **Automatycznie**.

### <a name="primary-button"></a>Przycisk podstawowy

Style można stosować do przycisku głównego tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od **DefaultButtonGroup** lub **PrimaryButtonGroup** (na przykład **DefaultButtonGroup10**).

![Przycisk podstawowy.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Przycisk pomocniczy

Style można stosować do przycisku dodatkowego tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy to **Prawy panel** lub nazwa grupy rozpoczyna się od **SecondaryButtonGroup**.

![Przycisk dodatkowy.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Przycisk trzeciej grupy

Style można stosować do przycisku trzeciej grupy tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy to **Lewy panel** lub nazwa grupy rozpoczyna się od **ThirdButtonGroup**.

![Przycisk trzeciej grupy.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Przycisk czwartej grupy

Style można stosować do przycisku czwartej grupy tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od **FourthButtonGroup**.

Ustaw następujące właściwości na przycisku:

- **Wyświetlanie przycisku**: **TextOnly**.
- **Normalny obraz**: Ta właściwość musi być pusta.
- **Tekst**: Ta właściwość nie może być pusta. Na przykład użyj **widoku** lub **edycji**.
- **Szerokość**: **Automatycznie**.
- **Wysokość**: **Automatycznie**.

![Przycisk czwartej grupy.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Płaski przycisk

Style można stosować do płaskiego przycisku tylko wtedy, gdy są spełnione następujące wymagania:

- Przycisk jest zawarty w grupie formularzy.
- Nazwa grupy rozpoczyna się od **FlatButtonGroup**.

Ustaw następujące właściwości na przycisku:

- **Wyświetlanie przycisku**: **ImageOnly**.
- **Normalny obraz**: Ta właściwość nie może być pusta. W tym przykładzie użyj **CoffeeScript**.
- **Tekst**: Ta właściwość musi być pusta.
- **Szerokość**: **Automatycznie**.
- **Wysokość**: **Automatycznie**.

![Płaski przycisk.](media/pfe-styles-flat-button.png)

## <a name="combo-box"></a>Pole kombi

Pole kombi to kombinacja trzech formantów: formantu wprowadzania, przycisku, który umożliwia wyczyszczenie formantu wejściowego, oraz przycisku, który uruchamia wyszukiwanie.

Style można stosować do pola kombi tylko wtedy, gdy są spełnione następujące wymagania:

- Pole kombi jest zawarte w grupie formularzy.
- Nazwa grupy rozpoczyna się od **Combobox**.
- W obrębie grupy pierwszym formantem jest formant **AxFormStringControl**. Ten formant pokazuje bieżącą wartość i w tym miejscu użytkownik wprowadza wymaganą wartość.
- Drugim formantem jest **CommonButton**, a jego nazwa rozpoczyna się od **ClearButton**. Ten przycisk musi zawierać kod, który używa właściwości **enable** do pokazywania lub ukrywania tego przycisku. Na przykład aby wyświetlić lub ukryć przycisk **Wyczyść** podczas wpisywania informacji w formancie wejściowym, można użyć następującego kodu.

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

    Użyj następującego kody dla metody **kliknięcia** przycisku **Wyczyść**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Ustaw wartość formantu wejściowego **AxFormStringControl**, gdy formularz zostanie zainicjowany za pomocą metody **init**. Jeśli ta wartość nie jest pusta, włącz przycisk **Wyczyść**. Jeśli ta wartość jest pusta, wyłącz przycisk **Wyczyść**.

- Trzecim formantem jest **CommonButton**, a jego nazwa rozpoczyna się od **SearchButton**.

Na poniższej ilustracji przedstawiono dwa formanty pól kombi. Pole kombi po lewej stronie ma puste pole tekstowe i przycisk **Wyczyść** jest wyłączony. Pole kombi po prawej stronie ma tekst w polu tekstowym i przycisk **Wyczyść** jest włączony.

![Pola kombi z przyciskiem Wyczyść i bez niego.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Szybkie filtrowanie

Formant szybkiego filtrowania powoduje dodanie pola wyszukiwania do strony. Do szybkiego filtrowania można stosować style, pod warunkiem że są spełnione następujące wymagania:

- Szybkie filtrowanie jest zawarte w grupie formularzy.
- Nazwa grupy rozpoczyna się od **SearchInputGroup**.
- W obrębie grupy pierwszym formantem jest formant **QuickFilter**. (W tym miejscu użytkownik wprowadzi wyszukiwany ciąg.)
- Drugim formantem jest **FormStaticTextControl** o nazwie **NumberOfResults**. (Jest to opcjonalne i zawiera liczbę znalezionych pozycji, jeśli są uwzględnione.)
- Trzecim formantem jest **CommonButton**, a jego nazwa rozpoczyna się od **ClearButton**.

Na poniższej ilustracji przedstawiono dwa formanty szybkiego filtrowania. Szybkie filtrowanie po lewej stronie ma pusty szybkie filtrowanie, a liczba wyników nie jest widoczna. Szybki filtr po prawej stronie zawiera wyszukiwany ciąg i pokazuje liczbę wyników.

![Przykłady formantu szybkiego filtrowania z ciągiem wyszukiwania i bez niego.](media/pfe-styles-quick-filter.png "Przykłady formantu szybkiego filtrowania z ciągiem wyszukiwania i bez niego")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
