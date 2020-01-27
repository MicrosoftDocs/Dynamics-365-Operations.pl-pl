---
title: Projektant formuł w module Raportowanie elektroniczne (ER)
description: Ten temat zawiera ogólne informacje o używaniu projektanta formuł w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0028d1f64aced1bbff91b18456c81adbb95bce30
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914825"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Projektant formuł w module Raportowanie elektroniczne (ER)

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak używać projektanta formuł w raportowaniu elektronicznym (ER). Podczas projektowania formatu dla określonego dokumentu elektronicznego w module raportowania elektronicznego można używać formuł w celu przekształcania danych, tak aby spełniały one wymagania dotyczące wypełniania i formatowania tego dokumentu. Te formuły przypominają formuły w programie Microsoft Excel. W formułach obsługiwane są różne typy funkcji: tekstu, daty i godziny, matematyczne, logiczne, informacyjne i konwersji typów danych, a także funkcje specyficzne dla domeny biznesowej.

## <a name="formula-designer-overview"></a>Projektant formuł — omówienie

Moduł ER obsługuje projektanta formuł. Z tego względu w czasie projektowania można konfigurować wyrażenia, które mogą być używane do następujących zadań w czasie wykonywania:

- Przekształć dane odebrane z bazy danych aplikacji, które należy wprowadzić w modelu danych ER zaprojektowanym jako źródło danych dla formatów ER. (Te przekształcenia mogą na przykład obejmować filtrowanie, grupowanie i konwersję typu danych).
- Formatowanie danych, które muszą zostać wysłane do generowanego dokumentu elektronicznego zgodnie z układem i warunkami określonego formatu ER. (Formatowanie może się na przykład odbywać zgodnie z żądanym językiem, kulturą, kodowaniem itd.).
- Kontrolowanie procesu tworzenia dokumentów elektronicznych. (Wyrażenia mogą na przykład włączać lub wyłączać tworzenie określonych elementów formatu w zależności od przetwarzania danych. Mogą również przerywać proces tworzenia dokumentu lub wysyłać komunikaty do użytkowników).

Stronę **Projektant formuł** można otworzyć podczas wykonywania następujących czynności:

- Wiązanie elementów źródła danych ze składnikami modelu danych.
- Wiązanie elementów źródła danych ze składnikami formatu.
- Obsługa pól obliczeniowych w ramach źródeł danych.
- Definiowanie warunków widoczności dla parametrów wejściowych użytkownika.
- Projektowanie przekształceń formatu.
- Definiowanie warunków włączania składników formatu.
- Definiowanie nazw plików dla plikowych składników formatu.
- Definiowanie warunków weryfikacji kontroli procesu.
- Definiowanie treści komunikatów weryfikacji kontroli procesu.

## <a name="Binding">Wiązanie danych</a>

Projektant formuł raportowania elektronicznego może służyć do definiowania wyrażenia przekształcającego dane otrzymywane ze źródeł danych, dzięki czemu dane mogą być wprowadzane do użytkownika danych na następujące sposoby w czasie wykonywania:

- Ze źródeł danych aplikacji i parametrów czasu wykonywania na model danych ER
- Z modelu danych ER na format ER
- Ze źródeł danych aplikacji i parametrów czasu wykonywania na format ER

Poniższa ilustracja pokazuje projekt wyrażenia tego typu. W tym przykładzie wyrażenie zaokrągla wartość pola **Intrastat.AmountMST** w tabeli Intrastat do dwóch miejsc dziesiętnych, a następnie zwraca zaokrągloną wartość.

[![Wyrażenie wiązania danych](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

Poniższa ilustracja pokazuje sposób użycia wyrażenia tego typu. W tym przykładzie wynik zaprojektowanego wyrażenia jest wprowadzany w składniku **Transaction.InvoicedAmount** modelu danych **Model raportowania podatku**.

[![Używanie wyrażenia wiązania danych](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

W czasie wykonywania zaprojektowana formuła `ROUND (Intrastat.AmountMST, 2)` zaokrągla wartość pola **AmountMST** dla każdego rekordu w tabeli Intrastat do dwóch miejsc dziesiętnych. Następnie wprowadza zaokrągloną wartość w składniku **Transaction.InvoicedAmount** modelu danych **Raportowanie podatku**.

## <a name="Transformation">Formatowanie danych</a>

Projektant formuł ER może służyć do definiowania wyrażenia formatującego dane otrzymywane ze źródeł danych, dzięki czemu dane mogą być wysyłane w ramach generowania dokumentu elektronicznego. Być może istnieje formatowanie, które musi być stosowane jako typowa reguła powtarzana dla formatu. W takim przypadku można wprowadzić to formatowanie jeden raz do konfiguracji formatu jako nazwane przekształcenie zawierające wyrażenie formatujące. Później to nazwane przekształcenie można połączyć z wieloma składnikami formatu, których dane wyjściowe muszą być sformatowane zgodnie z utworzonym wyrażeniem formatującym.

Poniższa ilustracja pokazuje projekt przekształcenia tego typu. W tym przykładzie przekształcenie **TrimmedString** obcina przychodzące dane o typie danych *Ciąg*, usuwając spacje początkowe i końcowe. Następnie zwraca obciętą wartość ciągu.

[![Przekształcenie](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

Poniższa ilustracja pokazuje sposób użycia przekształcenia tego typu. W tym przykładzie kilka składników formatu wysyła tekst jako dane wyjściowe do generowania dokumentu elektronicznego w czasie wykonywania. Wszystkie te składniki formatu odwołują się do przekształcenia **TrimmedString** według nazwy.

[![Używanie przekształcenia](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Jeśli składniki formatu, takie jak **partyName** na poprzedniej ilustracji, odwołują się do przekształcenia **TrimmedString**, przekształcenie wysyła tekst jako dane wyjściowe do generowanego dokumentu elektronicznego. Tekst nie zawiera spacji wiodących ani końcowych.

Jeśli jest używane formatowanie, które musi być stosowane indywidualnie, można je wprowadzić jako indywidualne wyrażenie wiązania konkretnego składnika formatu. Poniższa ilustracja pokazuje wyrażenie tego typu. W tym przykładzie składnik formatu **partyType** jest powiązany ze źródłem danych poprzez wyrażenie, które konwertuje dane przychodzące z pola **Model.Company.RegistrationType** w źródle danych na tekst pisany wielkimi literami. Następnie wyrażenie wysyła ten tekst jako dane wyjściowe do dokumentu elektronicznego.

[![Stosowanie formatowania do jednego składnika](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="Validation">Kontrola przepływu procesu</a>

Projektant formuł ER może służyć do definiowania wyrażeń, które kontrolują przebieg procesu generowania dokumentów elektronicznych. Można wykonać następujące zadania:

- Zdefiniowanie warunków określających, kiedy proces tworzenia dokumentu musi zostać zatrzymany.
- Określenie wyrażeń, które będą tworzyły komunikaty do użytkownika o zatrzymanych procesach lub wyświetlały komunikaty z dziennika wykonywania o kontynuacji procesu generowania raportu.
- Określanie nazw plików generowanych dokumentów elektronicznych i kontrolowanie warunków ich tworzenia.

Każda reguła kontroli przepływu procesu została zaprojektowana jako indywidualny proces sprawdzania poprawności. Poniższa ilustracja pokazuje weryfikację tego typu. Poniżej znajduje się objaśnienie konfiguracji użytej w tym przykładzie:

- Sprawdzanie poprawności jest dokonywane po utworzeniu węzła **INSTAT** podczas generowania pliku XML.
- Jeśli lista transakcji jest pusta, mechanizm weryfikacji zatrzymuje proces wykonywania i zwraca wartość **FALSE**.
- Funkcja weryfikacji zwraca komunikat o błędzie zawierający treść etykiety SYS70894 w języku preferowanym przez użytkownika.

[![Weryfikacja](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Projektant formuł ER pozwala również ustawić nazwę pliku generowanego dokumentu elektronicznego i kontrolować proces tworzenia pliku. Poniższa ilustracja pokazuje projekt tego typu kontroli przebiegu procesu. Poniżej znajduje się objaśnienie konfiguracji użytej w tym przykładzie:

- Lista rekordów ze źródła danych **modelu. Intrastat** jest podzielona na partie. Każda partia zawiera maksymalnie 1000 rekordów.
- Dane wyjściowe mają postać pliku zip zawierającego jeden plik w formacie XML dla każdej utworzonej partii.
- Wyrażenie zwraca nazwę pliku dla generowania dokumentów elektronicznych, łącząc nazwę pliku i rozszerzenie nazwy pliku. Dla partii drugiej i wszystkich kolejnych nazwa pliku zawiera identyfikator partii jako sufiks.
- Wyrażenie umożliwia (poprzez zwrócenie wartości **TRUE**) proces tworzenia plików dla partii zawierających co najmniej jeden rekord.

[![Kontrola przepływu procesu](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="Enabled">Kontrola zawartości dokumentu</a>

Projektanta formuł ER można używać do konfigurowania wyrażeń kontrolujących, jakie dane będą umieszczane w wygenerowanych elektronicznych dokumentach w czasie wykonywania. Wyrażenia mogą na przykład włączać lub wyłączać tworzenie określonych elementów formatu w zależności od przetwarzania danych. Te wyrażenia można wprowadzić dla pojedynczego elementu formatu w polu **Włączone** na karcie **Mapowanie** na stronie **projektanta operacji**. Wyrażenia można wprowadzać jako warunek logiczny, który zwraca *wartość logiczną*:

- Jeśli warunek zwraca wartość **True**, bieżący element formatu jest uruchamiany.
- Jeśli warunek zwraca wartość **False**, bieżący element formatu jest pomijany.

Poniższa ilustracja pokazuje wyrażenia tego typu. (Wersja 11.12.11 formatu konfiguracji **polecenia przelewu ISO20022 (NO)** dostarczonego przez Microsoft jest używana jako przykład). Składnik formatu **XMLHeader** jest skonfigurowany do opisywania struktury komunikatu dotyczącego polecenia przelewu zgodnie ze standardami ISO 20022 dotyczącymi komunikatów XML). Składnik formatu **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** jest skonfigurowany do dodania do elementu XML **Ustrd** do wygenerowanego komunikatu i umieszczenia informacji o przekazie w formacie bez struktury jako tekstu następujących elementów XML:

- Składnik **PaymentNotes** jest używany do generowania tekstu uwag do płatności.
- Składnik **DelimitedSequence** umożliwia generowanie faktur rozdzielanych przecinkami, które służą do rozliczenia bieżącego przelewu kredytowego.

[![Składniki PaymentNotes i DelimitedSequence](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> Składniki **PaymentNotes** i **DelimitedSequence** są oznaczane przy użyciu znaku zapytania. Znak zapytania wskazuje, że użycie składnika jest warunkowe. W takim przypadku użycie składników opiera się na następujących kryteriach:
>
> - Wyrażenie `@.PaymentsNotes <> ""` zdefiniowane dla składnika **PaymentNotes** włącza (zwracając wartość **TRUE**) wypełnianie elementu XML **Ustrd** przy użyci uwag dotyczących płatności, jeśli ten tekst dla polecenia przelewu nie jest pusty.
>
>    [![Wyrażenie dla składnika PaymentNotes](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - Wyrażenie `@.PaymentsNotes = ""` zdefiniowane dla składnika **DelimitedSequence** włącza (zwracając wartość **TRUE**) wypełnianie elementu XML **Ustrd** przy użyciu oddzielanej przecinkami listy numerów faktur używanej do rozliczania bieżącego polecenia przelewu, gdy tekst uwag dotyczących płatności dla tego polecenia przelewu jest pusty.
>
>    [![Wyrażenie dla składnika DelimitedSequence](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> Na podstawie tej konfiguracji wygenerowana wiadomość dla każdej płatności dłużnika, element XML **Ustrd**, będzie zawierać tekst uwag do płatności lub, jeśli taki tekst jest pusty, rozdzielaną przecinkami listę numerów faktur używanych do rozliczenia płatności.

## <a name="TestFormula">Weryfikacja skonfigurowanych formuł</a>

Na stronie **Projektant formuł** wybierz pozycję **Testuj**, aby sprawdzić, jak działa skonfigurowana formuła.

[![Wybieranie testu w celu zweryfikowania formuły](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

Gdy wymagane są wartości argumentów formuły, można otworzyć okno dialogowe **Wyrażenie testowe** na stronie **Projektant formuł**. W większości przypadków te argumenty muszą być definiowane ręcznie, ponieważ skonfigurowane powiązania nie są uruchamiane w czasie projektowania. Na karcie **Wynik testu** na stronie **Projektant formuł** jest wyświetlany wynik z wykonania skonfigurowanej formuły.

W poniższym przykładzie pokazano, jak można przetestować formułę skonfigurowaną dla domeny handlu zagranicznego, aby upewnić się, że kod asortymentu Intrastat zawiera tylko cyfry.

Podczas testowania tej formuły można użyć okna dialogowego **Wyrażenie testowe**, aby określić wartość kodu asortymentu Intrastat do testowania.

[![Określanie kodu asortymentu Intrastat do testowania](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Po określeniu kodu asortymentu Intrastat i wybraniu przycisku **OK**na karcie **Wynik testu** na stronie **Projektant formuł** jest wyświetlany wynik wykonania skonfigurowanej formuły. Następnie możesz ocenić, czy wynik jest dopuszczalny. Jeśli wynik nie jest dopuszczalny, możesz zaktualizować formułę i przetestować ją ponownie.

[![Wynik testu](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Niektóre formuły nie mogą być testowane w czasie projektowania. Na przykład formuła może zwracać wynik typu danych, który nie może być wyświetlany na karcie **Wynik testu**. W takim przypadku zostanie wyświetlony komunikat o błędzie informujący, że nie można przetestować formuły.

[![Komunikat o błędzie](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Język formuł raportowania elektronicznego](er-formula-language.md)
