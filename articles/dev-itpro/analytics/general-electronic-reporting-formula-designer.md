---
title: Projektant formuł w module Raportowanie elektroniczne (ER)
description: W tym temacie wyjaśniono, jak używać projektanta formuł w raportowaniu elektronicznym (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/14/2014
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f8461f851f6f54def8a04d0f2548961b9a1ca4d
ms.sourcegitcommit: ce84a1faeda6013ef6a90038d811a72f375b604e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/12/2019
ms.locfileid: "1625879"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Projektant formuł w module Raportowanie elektroniczne (ER)

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak używać projektanta formuł w raportowaniu elektronicznym (ER). Podczas projektowania formatu dla określonego dokumentu elektronicznego w module raportowania elektronicznego można używać formuł w celu przekształcania danych, tak aby spełniały one wymagania dotyczące wypełniania i formatowania tego dokumentu. Te formuły przypominają formuły w programie Microsoft Excel. W formułach obsługiwane są różne typy funkcji: tekstu, daty i godziny, matematyczne, logiczne, informacyjne, konwersji typów danych i inne (specyficzne dla domeny biznesowej).

## <a name="formula-designer-overview"></a>Projektant formuł — omówienie

Moduł ER obsługuje projektanta formuł. Z tego względu w czasie projektowania można konfigurować wyrażenia, które mogą być używane do następujących zadań w czasie wykonywania:

- Przekształć dane odebrane z bazy danych Microsoft Dynamics 365 for Finance and Operations, które należy wprowadzić w modelu danych ER zaprojektowanym jako źródło danych dla formatów ER. (Te przekształcenia mogą na przykład obejmować filtrowanie, grupowanie i konwersję typu danych).
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

## <a name="designing-er-formulas"></a>Projektowanie formuł ER

### <a name="data-binding"></a>Wiązanie danych

Projektant formuł raportowania elektronicznego może służyć do definiowania wyrażenia przekształcającego dane otrzymywane ze źródeł danych, dzięki czemu dane mogą być wprowadzane do użytkownika danych w czasie wykonywania:

- Ze źródeł danych programu Finance and Operations i parametrów czasu wykonywania na model danych ER
- Z modelu danych ER na format ER
- Ze źródeł danych programu Finance and Operations i parametrów czasu wykonywania na format ER

Poniższa ilustracja pokazuje projekt wyrażenia tego typu. W tym przykładzie wyrażenie zaokrągla wartość pola **Intrastat.AmountMST** tabeli Intrastat programu Finance and Operations do dwóch miejsc dziesiętnych, a następnie zwraca zaokrągloną wartość.

[![Wiązanie danych](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

Poniższa ilustracja pokazuje sposób użycia wyrażenia tego typu. W tym przykładzie wynik zaprojektowanego wyrażenia jest wprowadzany w składniku **Transaction.InvoicedAmount** modelu danych **Model raportowania podatku**.

[![Używanie powiązania danych](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

W czasie wykonywania zaprojektowana formuła **ROUND (Intrastat.AmountMST, 2)** zaokrągla wartość pola **AmountMST** dla każdego rekordu w tabeli Intrastat do dwóch miejsc dziesiętnych. Następnie wprowadza zaokrągloną wartość w składniku **Transaction.InvoicedAmount** modelu danych **Raportowanie podatku**.

### <a name="data-formatting"></a>Formatowanie danych

Projektant formuł ER może służyć do definiowania wyrażenia formatującego dane otrzymywane ze źródeł danych, dzięki czemu dane mogą być wysyłane w ramach generowania dokumentu elektronicznego. Być może istnieje formatowanie, które musi być stosowane jako typowa reguła powtarzana dla formatu. W takim przypadku można wprowadzić to formatowanie jeden raz do konfiguracji formatu jako nazwane przekształcenie zawierające wyrażenie formatujące. Później to nazwane przekształcenie można połączyć z wieloma składnikami formatu, których dane wyjściowe muszą być sformatowane zgodnie z utworzonym wyrażeniem formatującym.

Poniższa ilustracja pokazuje projekt przekształcenia tego typu. W tym przykładzie przekształcenie **TrimmedString** obcina przychodzące dane o typie danych **Ciąg**, usuwając spacje początkowe i końcowe. Następnie zwraca obciętą wartość ciągu.

[![Przekształcenie](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

Poniższa ilustracja pokazuje sposób użycia przekształcenia tego typu. W tym przykładzie kilka składników formatu wysyła tekst jako dane wyjściowe do generowania dokumentu elektronicznego w czasie wykonywania. Wszystkie te składniki formatu odwołują się do przekształcenia **TrimmedString** według nazwy.

[![Używanie przekształcenia](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Jeśli składniki formatu, takie jak **partyName** na poprzedniej ilustracji, odwołują się do przekształcenia **TrimmedString**, przekształcenie wysyła tekst jako dane wyjściowe do generowanego dokumentu elektronicznego. Tekst nie zawiera spacji wiodących ani końcowych.

Jeśli jest używane formatowanie, które musi być stosowane indywidualnie, można je wprowadzić jako indywidualne wyrażenie wiązania konkretnego składnika formatu. Poniższa ilustracja pokazuje wyrażenie tego typu. W tym przykładzie składnik formatu **partyType** jest powiązany ze źródłem danych poprzez wyrażenie, które konwertuje dane przychodzące z pola **Model.Company.RegistrationType** w źródle danych na tekst pisany wielkimi literami. Następnie wyrażenie wysyła ten tekst jako dane wyjściowe do dokumentu elektronicznego.

[![Stosowanie formatowania do jednego składnika](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Kontrola przepływu procesu

Projektant formuł ER może służyć do definiowania wyrażeń, które kontrolują przebieg procesu generowania dokumentów elektronicznych. Można wykonać następujące zadania:

- Zdefiniowanie warunków określających, kiedy proces tworzenia dokumentu musi zostać zatrzymany.
- Określenie wyrażeń, które będą tworzyły komunikaty do użytkownika o zatrzymanych procesach lub wyświetlały komunikaty z dziennika wykonywania o kontynuacji procesu generowania raportu.
- Określanie nazw plików generowanych dokumentów elektronicznych i kontrolowanie warunków ich tworzenia.

Każda reguła kontroli przepływu procesu została zaprojektowana jako indywidualny proces sprawdzania poprawności. Poniższa ilustracja pokazuje weryfikację tego typu. Poniżej znajduje się objaśnienie konfiguracji użytej w tym przykładzie:

- Sprawdzanie poprawności jest dokonywane po utworzeniu węzła **INSTAT** podczas generowania pliku XML.
- Jeśli lista transakcji jest pusta, mechanizm weryfikacji zatrzymuje proces wykonywania i zwraca wartość **FALSE**.
- Funkcja weryfikacji zwraca komunikat o błędzie zawierający treść etykiety SYS70894 programu Finance and Operations w języku preferowanym przez użytkownika.

[![Sprawdzanie poprawności](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Projektant formuł ER pozwala również ustawić nazwę pliku generowanego dokumentu elektronicznego i kontrolować proces tworzenia pliku. Poniższa ilustracja pokazuje projekt tego typu kontroli przebiegu procesu. Poniżej znajduje się objaśnienie konfiguracji użytej w tym przykładzie:

- Lista rekordów ze źródła danych **modelu. Intrastat** jest podzielona na partie. Każda partia zawiera maksymalnie 1000 rekordów.
- Dane wyjściowe mają postać pliku zip zawierającego jeden plik w formacie XML dla każdej utworzonej partii.
- Wyrażenie zwraca nazwę pliku dla generowania dokumentów elektronicznych, łącząc nazwę pliku i rozszerzenie nazwy pliku. Dla partii drugiej i wszystkich kolejnych nazwa pliku zawiera identyfikator partii jako sufiks.
- Wyrażenie umożliwia (poprzez zwrócenie wartości **TRUE**) proces tworzenia plików dla partii zawierających co najmniej jeden rekord.

[![Kontrolowanie pliku](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Podstawowa składnia

Wyrażenia raportowania elektronicznego mogą zawierać dowolne lub wszystkie z następujących elementów:

- Stałe
- Operatorzy
- Odwołania
- Ścieżki
- Funkcje

#### <a name="constants"></a>Stałe

Do projektowania wyrażeń można używać stałych tekstowych i liczbowych (tzn. wartości, które nie są obliczane). Na przykład w wyrażeniu **VALUE ("100") + 20** są używane stała liczbowa **20** i stała ciągu **"100"**, a wyrażenie zwraca wartość liczbową **120**. Projektanta formuł ER obsługuje sekwencje specjalne. Oznacza to, że można określić ciąg wyrażenia, który powinien być traktowany inaczej. Na przykład wyrażenie **„Lew Tołstoj ”„Wojna i pokój”„ Tom 1”** zwraca ciąg tekstowy **Lew Tołstoj „Wojna i pokój” Tom 1**.

#### <a name="operators"></a>Operatory

W poniższej tabeli przedstawiono operatory arytmetyczne, których można używać do wykonania podstawowych operacji matematycznych, takich jak dodawanie, odejmowanie, mnożenie i dzielenie.

| Operator | Znaczenie               | Przykład |
|----------|-----------------------|---------|
| +        | Dodanie              | 1+2     |
| -        | Odejmowanie, zaprzeczenie | 5-2, -1 |
| \*       | Mnożenie        | 7\*8    |
| /        | Oddział              | 9/3     |

W poniższej tabeli przedstawiono obsługiwane operatory porównania. Tych operatorów można używać do porównywania dwóch wartości.

| Operator | Znaczenie                  | Przykład    |
|----------|--------------------------|------------|
| =        | Taka sama                    | X=Y        |
| &gt;     | Większe niż             | X&gt;Y     |
| &lt;     | Mniejsze niż                | X&lt;Y     |
| &gt;=    | Większe lub równe | X&gt;=Y    |
| &lt;=    | Mniejsze lub równe    | X&lt;=Y    |
| &lt;&gt; | Nie równa się             | X&lt;&gt;Y |

Ponadto można użyć znaku handlowego „i” (&) jako operatora łączenia tekstu. W ten sposób można połączyć (złożyć) jeden lub kilka ciągów tekstowych w jeden element tekstu.

| Operator | Znaczenie     | Przykład                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Złącz | „Nie ma nic do wydrukowania” & „:&nbsp;” & „nie znaleziono żadnych rekordów” |

##### <a name="operator-precedence"></a>Pierwszeństwo operatorów

Kolejność, w jakiej części wyrażenia złożonego są obliczane, jest ważna. Na przykład wynik wyrażenia **1 + 4 / 2** różni się w zależności od tego, czy jako pierwsza jest wykonywana operacja dodawania, czy dzielenia. Nawiasy umożliwiają jawne zdefiniowanie sposobu wyznaczania wartości wyrażenia. Na przykład aby wskazać, że najpierw powinna być wykonywana operacja dodawania, można zmienić poprzednie wyrażenie na **(1 + 4) / 2**. Jeśli nie zdefiniujesz jawnie kolejności operacji w wyrażeniu, kolejność jest zależna od domyślnego pierwszeństwa przypisanego do obsługiwanych operatorów. Poniższa tabela ilustruje pierwszeństwo przypisane do każdego operatora. Operatory o wyższym priorytecie (na przykład 7) są odczytywane przed operatorami, które mają niższy priorytet (na przykład 1).

| Pierwszeństwo | Operatorzy      | Składnia                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Grupowanie       | ( … )                                                                   |
| 6          | Dostęp do elementu członkowskiego  | … , …                                                                   |
| 5          | Wywołanie funkcji  | … ( … )                                                                 |
| 4          | Zwielokrotnianie | … \* …<br>… / …                                                         |
| 3          | Addytywny       | … + …<br>… - …                                                          |
| 2          | Porównanie     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Rozdzielanie     | … , …                                                                   |

Jeśli wyrażenie zawiera wiele następujących po sobie operatorów, które mają ten sam priorytet (pierwszeństwo), operacje te są wykonywane od lewej do prawej. Na przykład wyrażenie **1 + 6 / 2 \* 3 &gt; 5** zwraca wartość **prawda**. Zaleca się używanie nawiasów w celu jawnego wskazania żądanej kolejności operacji w wyrażeniach, aby ułatwić odczyt wyrażenia i zarządzanie nim.

#### <a name="references"></a>Odwołania

Wszystkie źródła danych bieżącego składnika ER, które są dostępne podczas projektowania wyrażenia, mogą być używane jako odwołania nazwane. (Bieżący składnik ER może być modelem lub formatem). Na przykład bieżący model danych ER zawiera źródło danych **ReportingDate**, które zwraca wartość typu **DATETIME**. Aby ta wartość była poprawnie sformatowana w generowanym dokumencie, można utworzyć odwołanie z wyrażenia do źródła danych w postaci **DATETIMEFORMAT (ReportingDate, "dd-MM-rrrr")**.

Wszystkie znaki w nazwie przywoływanego źródła danych, które nie reprezentują litery alfabetu, muszą być poprzedzone pojedynczym cudzysłowem ('). Jeśli nazwa przywoływanego źródła danych zawiera co najmniej jeden symbol, który nie reprezentuje litery alfabetu, musi zostać ujęta w pojedyncze cudzysłowy. (Symbolami nienależącymi do alfabetu mogą być na przykład znaki interpunkcyjne lub symbole piśmiennicze). Oto kilka przykładów:

- Źródło danych **Dzisiejsza data i godzina** musi mieć w wyrażeniu ER odwołanie **'Dzisiejsza data i godzina'**.
- Metoda **name()** ze źródła danych **Customers** musi mieć w wyrażeniu ER odwołanie **Customers.'name()'**.

Jeśli metody źródeł danych programu Finance and Operations mają parametry, następująca składnia jest wykorzystywana do wywoływania tych metod:

- Jeśli metoda **isLanguageRTL** źródła danych **System** zawiera parametr **EN-US** o typie danych **Ciąg**, musi być przywoływana w wyrażeniu ER jako **System.'isLanguageRTL'("EN-US")**.
- Cudzysłowy nie są wymagane, jeśli nazwa metody zawiera tylko symbole alfanumeryczne. Są jednak wymagane dla metody tabeli, gdy nazwa zawiera nawiasy.

Gdy źródło danych **System** zostanie dodane do mapowania raportowania elektronicznego, które odwołuje się do klasy **Global** aplikacji Finance and Operations, wyrażenie zwraca wartość logiczną **FALSE**. Zmodyfikowany wyrażenie **System.' isLanguageRTL'("AR")** zwraca wartość logiczną **TRUE**.

Można ograniczyć sposób, w jaki wartości są przekazywane do parametrów tego typu metody:

- Tylko stałe mogą być przekazywane do tego typu metod. Wartości stałych są definiowane w czasie projektowania.
- W parametrach tego typu są obsługiwane tylko pierwotne (podstawowe) typy danych. (Pierwotne typy danych to liczby całkowite, liczby rzeczywiste, wartości logiczne, ciągi tekstowe itd).

#### <a name="paths"></a>Ścieżki

Jeśli wyrażenie odwołuje się do źródła danych usystematyzowanych, można użyć definicji ścieżki, aby wybrać określony element podstawowy tego źródła danych. Znak kropki (.) jest używany do oddzielania poszczególnych elementów źródła danych usystematyzowanych. Na przykład bieżący model danych ER zawiera źródło danych **InvoiceTransactions**, które zwraca listę rekordów. Struktura rekordu **InvoiceTransactions** zawiera pola **AmountDebit** i **AmountCredit**, które zwracają wartości liczbowe. W związku z tym można zaprojektować następujące wyrażenie służące do obliczania zafakturowanej kwoty: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funkcje

W następnej sekcji opisano funkcje, które mogą być używane w wyrażeniach raportowania elektronicznego. Wszystkie źródła danych kontekstu wyrażenia (bieżący model danych ER lub format ER) mogą służyć jako parametry funkcji wywołujących, zgodnie z listą argumentów funkcji wywołujących. Parametrami funkcji wywołujących mogą być również stałe. Na przykład bieżący model danych ER zawiera źródło danych **InvoiceTransactions**, które zwraca listę rekordów. Struktura rekordu **InvoiceTransactions** zawiera pola **AmountDebit** i **AmountCredit**, które zwracają wartości liczbowe. W efekcie w celu obliczania zafakturowanej kwoty można zaprojektować następujące wyrażenie używające wbudowanej funkcji zaokrąglania ER: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Obsługiwane funkcje

W poniższych tabelach opisano funkcje edycji danych, które mogą służyć do projektowania modeli danych i raportów ER. Lista funkcji nie jest zamknięta. Programiści mogą dodawać inne funkcje. Aby wyświetlić listę funkcji, których można użyć, otwórz okienko funkcji w projektancie formuł ER.

### <a name="date-and-time-functions"></a>Funkcje daty i godziny

| Funkcja | Opis | Przykład |
|----------|-------------|---------|
| ADDDAYS (data i godzina, dni) | Dodawanie określonej liczby dni do określonej wartości daty/godziny. | **ADDDAYS (NOW(), 7)** zwraca datę i godzinę siedem dni w przyszłości. |
| DATETODATETIME (data) | Konwertowanie określonej wartości daty na wartość daty/godziny. | **DATETODATETIME (CompInfo. "getCurrentDate()')** zwraca datę bieżącej sesji programu Finance and Operations, 24 grudnia 2015 roku, jako **12/24/2015 12:00:00 AM**. W tym przykładzie **CompInfo** jest źródłem danych ER typu **Finance and Operations/Tabela** i odwołuje się do tabeli CompanyInfo. |
| NOW () | Zwracanie bieżącej daty i godziny serwera aplikacji Finance and Operations jako wartości daty/godziny. | |
| TODAY () | Zwracanie bieżącej daty i godziny serwera aplikacji Finance and Operations jako wartości daty. | |
| NULLDATE () | Zwracanie wartości daty **null**. | |
| NULLDATETIME () | Zwracanie wartości daty/godziny **null**. | |
| DATETIMEFORMAT (data i godzina, format) | Konwertowanie określonej wartości daty/godziny na ciąg znaków w określonym formacie. (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz [standardowe](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "dd-MM-rrrr")** zwraca datę serwera aplikacji Finance and Operations, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym. |
| DATETIMEFORMAT (data i godzina, format, kultura) | Konwertowanie określonej wartości daty/godziny na ciąg znaków w określonym formacie i [kulturze](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz [standardowe](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "d", "de")** zwraca bieżącą datę serwera aplikacji Finance and Operations, 24 grudnia 2015 roku, jako **"24.12.2015"**, zgodnie z wybraną kulturą niemiecką. |
| SESSIONTODAY () | Zwracanie bieżącej daty i godziny sesji programu Finance and Operations jako wartości daty. | |
| SESSIONNOW () | Zwracanie bieżącej daty i godziny sesji programu Finance and Operations jako wartości daty/godziny. | |
| DATEFORMAT (data, format) | Zwracanie określonej daty w określonym formacie w postaci ciągu tekstowego. | **DATEFORMAT (SESSIONTODAY (), "dd-MM-rrrr")** zwraca datę sesji programu Finance and Operations, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym. |
| DATEFORMAT (data, format, kultura) | Konwertowanie określonej wartości daty na ciąg znaków w określonym formacie i [kulturze](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz [standardowe](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** zwraca bieżącą datę sesji programu Finance and Operations, 24 grudnia 2015 roku, jako **"24.12.2015"**, zgodnie z wybraną kulturą niemiecką. |
| DAYOFYEAR (data) | Zwracanie reprezentacji liczby dni między 1 stycznia a określoną datą w postaci liczby całkowitej. | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-rrrr"))** zwraca wartość **61**. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-rrrr"))** zwraca wartość **1**. |
| DAYS (data 1, data 2) | Zwracanie liczby dni między pierwszą określoną datą a drugą określoną datą. Zwracanie wartości dodatniej, gdy pierwsza data jest późniejsza niż druga data, zwracanie wartości **0** (zero), gdy pierwsza data jest równa drugiej dacie, lub zwracanie wartości ujemnej, gdy pierwsza data jest wcześniejsza niż druga data. | **DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT(ADDDAYS(NOW(), 1), "rrrrMMdd"), "rrrrMMdd"))** zwraca wartość **-1**. |

### <a name="data-conversion-functions"></a>Funkcje konwersji danych

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| DATETODATETIME (data) | Konwertowanie określonej wartości daty na wartość daty/godziny. | **DATETODATETIME (CompInfo. "getCurrentDate()')** zwraca datę bieżącej sesji programu Finance and Operations, 24 grudnia 2015 roku, jako **12/24/2015 12:00:00 AM**. W tym przykładzie **CompInfo** jest źródłem danych ER typu **Finance and Operations/Tabela** i odwołuje się do tabeli CompanyInfo. |
| DATEVALUE (ciąg tekstowy, format) | Zwracanie określonego ciągu w określonym formacie w postaci daty. | **DATEVALUE ("21-gru-2016", "dd-MMM-rrrr")** zwraca datę 21 grudnia 2016 roku zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji. |
| DATEVALUE (ciąg tekstowy, kultura) | Zwracanie określonego ciągu tekstowego w określonym formacie i kulturze w postaci daty. | **DATEVALUE ("21-Gen-2016", "dd-MMM-rrrr", "IT")** zwraca datę 21 stycznia 2016 roku zgodnie z określonym formatem niestandardowym i kulturą. Natomiast funkcja **DATEVALUE ("21-Gen-2016", "dd-MMM-rrrr", "EN-US")** zgłasza wyjątek w celu poinformowanie użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa data. |
| DATETIMEVALUE (ciąg tekstowy, format) | Zwracanie określonego ciągu w określonym formacie w postaci daty/godziny. | **DATETIMEVALUE ("21-gru-2016 02:55:00", "dd-MMM-rrrr gg:mm:ss")** zwraca godzinę 2:55:00 AM dnia 21 grudnia 2016 roku, zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji. |
| DATETIMEVALUE (ciąg tekstowy, kultura) | Zwracanie określonego ciągu tekstowego w określonym formacie i kulturze w postaci daty/godziny. | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-rrrr gg:mm:ss", "IT")** zwraca godzinę 2:55:00 AM dnia 21 grudnia 2016 roku, zgodnie z określonym formatem niestandardowym i kulturą. Natomiast funkcja **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-rrrr gg:mm:ss", "EN-US")** zgłasza wyjątek w celu poinformowanie użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa data/godzina. |

### <a name="list-functions"></a>Lista funkcji

<table>
<thead>
<tr>
<th>Funkcja</th>
<th>opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr>
<td>SPLIT (dane wejściowe, długość)</td>
<td>Dzielnie podanego ciągu wejściowego na podciągi, z których każdy ma określoną długość. Wynik jest zwracany jako nowa lista.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> zwraca nową listę zawierającą dwa rekordy, które mają pole <strong>STRING</strong>. Pole w pierwszym rekordzie zawiera tekst <strong>&quot;abc&quot;</strong>, a pole w drugim rekordzie zawiera tekst <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr>
<td>SPLIT (dane wejściowe, separator)</td>
<td>Dzielnie podanego ciągu wejściowego na podciągi przy użyciu podanego separatora.</td>
<td><strong>SPLIT (&quot;XAb aBy&quot;, &quot;aB&quot;)</strong> zwraca nową listę zawierającą trzy rekordy, które mają pole <strong>STRING</strong>. Pole w pierwszym rekordzie zawiera tekst <strong>&quot;X&quot;</strong>, pole w drugim rekordzie zawiera tekst &quot;&nbsp;&quot;, a pole w trzecim rekordzie zawiera tekst <strong>&quot;y&quot;</strong>. Jeśli parametr „separator” jest pusty, zostanie zwrócona nowa lista składająca się z jednego rekordu mającego pole <strong>STRING</strong> zawierające tekst wejściowy. Jeśli parametr „dane wejściowe” jest pusty, zostanie zwrócona nowa pusta lista.
Jeśli parametr „dane wejściowe” lub „separator” jest nieokreślony (ma wartość null), aplikacja zgłasza wyjątek.</td>
</tr>
<tr>
<td>SPLITLIST (lista, liczba)</td>
<td>Dzielenie określonej listy na partie, z których każda zawiera określoną liczbę rekordów. Wynik jest zwracany jako nowa lista partii zawierająca następujące elementy:
<ul>
<li>Partie jako zwykłe listy (składnik <strong>Value</strong>)</li>
<li>Numer bieżącej partii (składnik <strong>BatchNumber</strong>)</li>
</ul>
</td>
<td>Na poniższej ilustracji źródło danych <strong>Lines</strong> jest tworzone jako lista trzech rekordów. Lista jest podzielona na partie, z których każdy zawiera maksymalnie dwa rekordy.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Na ilustracji poniżej widać zaprojektowany układ formatu. W tym układzie formatu są tworzone wiązania ze źródłem danych <strong>Lines</strong> w celu wygenerowania danych wyjściowych w formacie XML Te dane wyjściowe reprezentują poszczególne węzły każdej partii i zawartych w niej rekordów.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>
</td>
</tr>
<tr>
<td>LIST (rekord 1 [, rekord 2, ...])</td>
<td>Zwracanie nowej listy utworzonej na podstawie określonych argumentów.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> zwraca pusty rekord, w którym lista pól zawiera wszystkie pola z list rekordów <strong>MainData</strong> i <strong>OtherData</strong>.</td>
</tr>
<tr>
<td>LISTJOIN (lista 1, lista 2, ...)</td>
<td>Zwracanie połączonej listy utworzonej z list określonych argumentów.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> zwraca listę sześciu rekordów, gdzie jedno pole typu danych <strong>STRING</strong> zawiera pojedyncze litery.</td>
</tr>
<tr>
<td>ISEMPTY (lista)</td>
<td>Zwracanie wartości <strong>TRUE</strong>, jeśli określona lista nie zawiera żadnych elementów. W przeciwnym jest zwracana wartość <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr>
<td>EMPTYLIST (lista)</td>
<td>Zwracanie pustej listy poprzez użycie określonej listy jako źródła dla struktury listy.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> zwraca nową pustą listę, która ma taką samą strukturę jak lista zwracana przez funkcję <strong>SPLIT</strong>.</td>
</tr>
<tr>
<td>FIRST (lista)</td>
<td>Zwracanie pierwszego rekordu określonej listy, jeśli ten rekord nie jest pusty. W przeciwnym razie jest zgłaszany wyjątek.</td>
<td></td>
</tr>
<tr>
<td>FIRSTORNULL (list)</td>
<td>Zwracanie pierwszego rekordu określonej listy, jeśli ten rekord nie jest pusty. W przeciwnym razie jest zwracany rekord <strong>null</strong>.</td>
<td></td>
</tr>
<tr>
<td>LISTOFFIRSTITEM (lista)</td>
<td>Zwracanie listy zawierającej tylko pierwszy element określonej listy.</td>
<td></td>
</tr>
<tr>
<td>ALLITEMS (ścieżka)</td>
<td>Ta funkcja działa jako wybór w pamięci. Następnie zwraca nową spłaszczoną listę przedstawiającą wszystkie elementy pasujące do określonej ścieżki. Ścieżka musi być określona jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych Lista rekordów. Elementy danych, takie jak ciąg ścieżki i data, powinny powodować zgłaszanie błędu w konstruktorze wyrażeń ER w czasie projektowania.</td>
<td>Po wprowadzeniu <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> jako źródła danych (DS) funkcja <strong>COUNT( ALLITEMS (DS.Value))</strong> zwraca wartość <strong>3</strong>.</td>
</tr>
<tr>
<td>ALLITEMSQUERY (ścieżka)</td>
<td>Ta funkcja jest wykonywana jako sprzężone zapytanie SQL. Następnie zwraca nową spłaszczoną listę przedstawiającą wszystkie elementy pasujące do określonej ścieżki. Wskazana ścieżka musi być określona jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych Lista rekordów i musi zawierać co najmniej jedną relację. Elementy danych, takie jak ciąg ścieżki i data, powinny powodować zgłaszanie błędu w konstruktorze wyrażeń ER w czasie projektowania.</td>
<td>Zdefiniuj następujące źródła danych w swoim mapowanie modelu:
<ul>
<li><strong>CustInv</strong> (typ <strong>Rekordy tabeli</strong>), który odwołuje się do tabeli CustInvoiceTable</li> 
<li><strong>FilteredInv</strong> (typ <strong>Pole obliczeniowe</strong>), w którym znajduje się wyrażenie <strong>FILTER (CustInv, CustInv.InvoiceAccount = &quot;US-001&quot;)</strong></li>
<li><strong>JourLines</strong> (typ <strong>Pole obliczeniowe</strong>), w którym znajduje się wyrażenie <strong>ALLITEMSQUERY (FilteredInv.'&lt;Relations'.CustInvoiceJour.'&lt;Relations'.CustInvoiceTrans)</strong></li>
</ul>
<p>Po uruchomieniu mapowania modelu do wywoływania źródła danych <strong>JourLines</strong>, uruchamiana jest następująca instrukcja SQL:</p>
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN CUSTINVOICETRANS T3 WHERE...
</td>
</tr>
<tr>
<td>ORDERBY (lista [, wyrażenie 1, wyrażenie 2, …])</td>
<td>Zwracanie określonej listy po jej posortowaniu zgodnie z podanymi argumentami. Te argumenty można zdefiniować jako wyrażenia.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowany jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>ORDERBY (Vendors, Vendors.'name()')</strong> zwraca listę dostawców posortowaną według nazw w porządku rosnącym.</td>
</tr>
<tr>
<td>REVERSE (lista)</td>
<td>Zwracanie określonej listy w odwrotnym porządku sortowania.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowane jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> zwraca listę dostawców posortowaną według nazw w porządku malejącym.</td>
</tr>
<tr>
<td>WHERE (lista, warunek)</td>
<td>Zwracanie określonej listy po jej wyfiltrowaniu zgodnie z podanymi warunkami. Podany warunek jest stosowany do listy w pamięci. W ten sposób działanie funkcji <strong>WHERE</strong> różni się od działania funkcji <strong>FILTER</strong>.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowane jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> zwraca listę wyłącznie dostawców należących do grupy dostawców 40.</td>
</tr>
<tr>
<td>ENUMERATE (lista)</td>
<td>Zwracanie nowej listy, która zawiera stałotekstowe rekordy określonej listy oraz udostępnia następujące elementy:
<ul>
<li>Określona lista rekordów jako zwykłe listy (składnik <strong>Value</strong>)</li>
<li>Indeks bieżącego rekordu (składnik <strong>Number</strong>)</li>
</ul>
</td>
<td>Na poniższej ilustracji źródło danych <strong>Enumerated</strong> jest tworzone jako stałotekstowa lista rekordów dostawców ze źródła danych <strong>Vendors</strong>, które odwołuje się do tabeli VendTable.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>Na ilustracji poniżej widać format. W tym formacie są tworzone powiązania danych w celu wygenerowania danych wyjściowych w formacie XML Te dane wyjściowe prezentują poszczególnych dostawców jako stałotekstowe węzły.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>
</td>
</tr>
<tr>
<td>COUNT (lista)</td>
<td>Zwracanie liczby rekordów określonej listy, jeśli lista nie jest pusta. W przeciwnym jest zwracana wartość <strong>0</strong> (zero).</td>
<td>Funkcja <strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> zwraca wartość <strong>2</strong>, ponieważ funkcja <strong>SPLIT</strong> tworzy listę składającą się z dwóch rekordów.</td>
</tr>
<tr>
<td>LISTOFFIELDS (ścieżka)</td>
<td>Zwracanie listy rekordów utworzonej na podstawie argumentu o jednym z następujących typów:
<ul>
<li>Wyliczenie modeli</li>
<li>Wyliczenie formatów</li>
<li>Kontener</li>
</ul>
<p>Utworzona lista składa się z rekordów zawierających następujące pola:</p>
<ul>
<li>Nazwisko</li>
<li>Etykiety</li>
<li>opis</li>
</ul>
Podczas wykonywania pola <strong>Etykieta</strong> i <strong>Opis</strong> zwracają wartości zależne od ustawień języka formatu.
</td>
<td>Na poniższej ilustracji wartość stałotekstowa została wprowadzona do modelu danych.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>Na ilustracji przedstawiono następujące szczegóły:</p>
<ul>
<li>Wartość stałotekstowa modelu wstawiona do raportu jako źródło danych.</li>
<li>W wyrażeniu ER wartość stałotekstowa modelu jest używana jako parametr funkcji <strong>LISTOFFIELDS</strong>.</li>
<li>Źródło danych typu Lista rekordów jest wstawiane do raportu przy użyciu utworzonego wyrażenia ER.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>W poniższym przykładzie pokazano elementy formatu ER, które są powiązane ze źródłem danych typu Lista rekordów utworzonym przy użyciu funkcji <strong>LISTOFFIELDS</strong>.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE] Zgodnie z ustawieniami języka nadrzędnych elementów formatu PLIK i FOLDER przetłumaczone teksty etykiet i opisów są wprowadzane do danych wyjściowych formatu ER.</blockquote>
</td>
</tr>
<tr>
<td>LISTOFFIELDS (ścieżka, język)</td>
<td>Zwracanie listy rekordów utworzonej na podstawie argumentu, takiego jak wartość stałotekstowa modelu, wartość stałotekstowa formatu lub kontener. Utworzona lista składa się z rekordów zawierających następujące pola:
<ul>
<li>Nazwisko</li>
<li>Etykiety</li>
<li>opis</li>
<li>Jest przetłumaczone</li>
</ul>
Podczas wykonywania pola <strong>Etykieta</strong> i <strong>Opis</strong> zwracają wartości zależne od ustawień języka formatu i wybranego języka. Pole <strong>Jest przetłumaczone</strong> wskazuje, że zawartość pola <strong>Etykieta</strong> została przetłumaczona na wskazany język.
</td>
<td>Na przykład można użyć źródła danych o typie <strong>Pole obliczeniowe</strong> do skonfigurowania źródeł danych <strong>enumType_de</strong> i <strong>enumType_deCH</strong> dla elementu stałotekstowego modelu danych <strong>enumType</strong>.
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
<p>W tym przypadku można użyć następującego wyrażenia, aby otrzymać etykietę wartości stałotekstowej w języku niemieckim (Szwajcaria), jeśli takie tłumaczenie jest dostępne. Jeśli tłumaczenie na język niemiecki (Szwajcaria) nie jest dostępne, etykieta pozostaje w języku niemieckim.</p>
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
</td>
</tr>
<tr>
<td>STRINGJOIN (lista, nazwa pola, separator)</td>
<td>Zwracanie ciągu zawierającego połączone wartości z określonego pola na wybranej liście. Wartości są rozdzielone wybranym separatorem.</td>
<td>Jeśli jako źródło danych (DS) wpiszesz <strong>SPLIT(&quot;abc&quot; , 1)</strong>, wyrażenie <strong>STRINGJOIN (DS, DS.Value, &quot;-&quot;)</strong> zwraca wartość <strong>&quot;a-b-c&quot;</strong>.</td>
</tr>
<tr>
<td>SPLITLISTBYLIMIT (lista, wartość limitu, źródło limitu)</td>
<td>Dzielenie podanej listy na zbiór list podrzędnych i zwracanie wyniku w treści listy rekordów. Parametr <strong>wartości limitu</strong> określa wartość graniczną, przy której następuje podział oryginalnej listy. Parametr <strong>źródło limitu</strong> określa krok, o jaki jest zwiększana suma. Limit nie jest stosowany do pojedynczego elementu oryginalnej listy, jeżeli źródło limitu przekracza zdefiniowany limit.</td>
<td>Na ilustracji poniżej widać format. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p>Na poniższej ilustracji pokazano źródła danych używane dla formatu.</p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>Na ilustracji poniżej widać wynik uruchomienia formatu. W tym przypadku danymi wyjściowymi jest niezhierarchizowana lista towarów asortymentowych.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>Na poniższej ilustracji ten sam format został skorygowany w taki sposób, aby pokazywał listę towarów asortymentowych w partiach, gdzie jedna partia musi zawierać towary o łącznej wadze nieprzekraczającej limitu 9.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>Na ilustracji poniżej widać wynik uruchomienia zmodyfikowanego formatu.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE] Limit nie obowiązuje do ostatniej pozycji oryginalnej listy, ponieważ wartość (11) jej źródła limitu (waga) przekracza zdefiniowany limit (9). W razie potrzeby należy użyć funkcji <strong>WHERE</strong> albo wyrażenia <strong>Enabled</strong> odnośnego elementu formatu, aby zignorować (pominąć) listy podrzędne podczas generowania raportu.</blockquote>
</td>
</tr>
<tr>
<td>FILTER (lista, warunek)</td>
<td>Zwracanie określonej listy po zmodyfikowaniu zapytania w celu wyfiltrowania według podanego warunku. Ta funkcja różni się od funkcji <strong>WHERE</strong>, ponieważ podany warunek jest stosowany do każdego źródła danych ER o typie <strong>Rekordy tabeli</strong> na poziomie bazy danych. Listę i warunek można zdefiniować przy użyciu tabel i relacji.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowane jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> zwraca listę wyłącznie dostawców należących do grupy dostawców 40. Jeśli <strong>Vendor</strong> jest skonfigurowane jako źródło danych ER odwołujące się do tabeli VendTable, a element <strong>parmVendorBankGroup</strong> jest skonfigurowany jako źródło danych ER zwracające wartość o typie danych <strong>String</strong>, to funkcja <strong>FILTER (Vendor.'&lt;Relations'.VendBankAccount, Vendor.'&lt;Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> zwraca listę tylko kont dostawców należących do określonej grupy bankowej.</td>
</tr>
<tr>
<td>INDEKS (lista, indeks)</td>
<td>Ta funkcja zwraca rekord wybrany przez określony indeks liczbowy z listy. Jeśli indeks jest poza zakresem rekordów na liście, zostanie zwrócony wyjątek.</td>
<td>Jeśli wprowadzisz źródło danych <strong>DS</strong> dla typu <strong>Pole obliczeniowe</strong> i zawiera ono wyrażenie <strong>SPLIT ("A|B|C", “|”), 2</strong>, wyrażenie <strong>DS.Value</strong> zwraca wartość tekstową „B”. Wyrażenie <strong>INDEX (SPLIT ("A|B|C", “|”), 2).Value</strong> także zwróci wartość tekstową „B”.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funkcje logiczne

| Funkcja | Opis | Przykład |
|----------|-------------|---------|
| CASE (wyrażenie, opcja 1, wynik 1 \[, opcja 2, wynik 2\] ... \[, wynik domyślny\]) | Wyznaczanie wartości określonego wyrażenia względem określonych opcji alternatywnych. Zwracanie wyniku opcji równego wartości wyrażenia. W przeciwnym razie zwracanie opcjonalnego wyniku domyślnego, jeśli jest on zdefiniowany. (Wynikiem domyślnym jest ostatni parametr niepoprzedzony opcją). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "ZIMA", "11", "ZIMA", "12", "ZIMA", "")** zwraca ciąg **"ZIMA"**, gdy data bieżącej sesji programu Finance and Operations mieści się w okresie od października do grudnia. W przeciwnym razie zwraca ciąg pusty. |
| IF (warunek, wartość 1, wartość 2) | Zwracanie pierwszej określonej wartości, jeśli jest spełniony podany warunek. W przeciwnym razie zwracanie drugiej określonej wartości. Jeśli wartości 1 i 2 są rekordami lub listami rekordów, wynik zawiera tylko pola, które istnieją na obu listach. | **IF (1=2, "warunek jest spełniony", "warunek nie jest spełniony")** zwraca ciąg **"warunek nie jest spełniony"**. |
| NOT (warunek) | Zwracanie odwrotnej wartości logicznej określonego warunku. | **NOT (TRUE)** zwraca wartość **FALSE**. |
| AND (warunek 1\[, warunek 2, ...\]) | Zwracanie wartości **TRUE**, jeśli *wszystkie* określone warunki są spełnione. W przeciwnym jest zwracana wartość **FALSE**. | Funkcja **AND (1=1, "a"="a")** zwraca wartość **TRUE**. **AND (1=2, "a"="a")** zwraca wartość **FALSE**. |
| OR (warunek 1\[, warunek 2, ...\]) | Zwracanie wartości **FALSE**, jeśli *żaden* określony warunek nie jest spełniony. Zwracanie wartości **TRUE**, jeśli *którykolwiek* określony warunek jest spełniony. | **OR (1=2, "a"="a")** zwraca wartość **TRUE**. |
| VALUEIN (dane wejściowe, lista, wyrażenie elementu listy) | Ustalanie, czy podane dane wejściowe pasują do którejkolwiek wartości elementu na podanej liście. Zwracanie wartości **TRUE**, jeśli podane dane wejściowe są zgodne z wynikiem wykonania podanego wyrażenia dla co najmniej jednego rekordu. W przeciwnym jest zwracana wartość **FALSE**. Parametr **dane wejściowe** reprezentuje ścieżkę elementu źródła danych. To z wartością tego elementu będzie dokonywane porównanie. Parametr **lista** reprezentuje ścieżkę elementu źródła danych typu Lista rekordów jako listę rekordów zawierających wyrażenie. Wartość tego elementu będzie porównywana z podanymi danymi wejściowymi. Argument **wyrażenie elementu listy** reprezentuje wyrażenie wskazujące albo zawierające pojedyncze pole określonej listy, która ma być używana do porównania. | Aby uzyskać przykłady, zobacz następną sekcję [Przykłady: VALUEIN (dane wejściowe, lista, wyrażenie elementu listy)](#examples-valuein-input-list-list-item-expression). |

#### <a name="examples-valuein-input-list-list-item-expression"></a>Przykłady: VALUEIN (dane wejściowe, lista, wyrażenie elementu listy)
Zasadniczo funkcja **VALUEIN** jest przekształcana na zbiór warunków **OR**:

(dane wejściowe = list.item1.value) OR (dane wejściowe = list.item2.value) OR …

##### <a name="example-1"></a>Przykład 1
W mapowaniu modelu definiujesz następujące źródło danych: **List** (typ **Pole obliczeniowe**). To źródło danych zawiera wyrażenie **SPLIT ("a,b,c", ",")**.

Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia **VALUEIN ("B", List, List.Value)**, zwróci wartość **TRUE**. W tym przypadku funkcja **VALUEIN** jest przekształcana na następujący zbiór warunków:

**(("B" = "a") lub ("B" = "b") lub ("B" = "c"))**, gdzie **("B" = "b")** równa się **TRUE**

Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia **VALUEIN ("B", List, LEFT(List.Value, 0))**, zwróci wartość **FALSE**. W tym przypadku funkcja **VALUEIN** jest przekształcana na następujący warunek:

**("B" = "")**, co nie równa się **TRUE**

Należy zauważyć, że górny limit liczby znaków w treści takiego warunku to 32 768 znaków. Z tego względu nie należy tworzyć źródeł danych, które w czasie wykonywania mogą spowodować przekroczenie tego limitu. W przypadku przekroczenia limitu aplikacja przestanie działać i zgłosi wyjątek. Na przykład taka sytuacja może wystąpić, jeśli źródło danych jest skonfigurowane za pomocą wyrażenia **WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)**, a listy **List1** i **List2** zawierają bardzo dużo rekordów.

W niektórych przypadkach funkcja **VALUEIN** jest przekształcana na zestawienia bazy danych za pomocą operatora **EXISTS JOIN**. Takie zachowanie występuje, gdy jest używana funkcja **FILTER** i są spełnione następujące warunki:

- Opcja **Monituj o zapytanie** jest wyłączona w źródle danych funkcji **VALUEIN** odwołującej się do listy rekordów. (W czasie wykonywania do tego źródła danych nie będą stosowane żadne dodatkowe warunki).
- Nie skonfigurowano żadnych warunków zagnieżdżonych w źródle danych funkcji **VALUEIN** odwołującej się do listy rekordów.
- Element listy w funkcji **VALUEIN** odwołuje się do pola (a nie do wyrażenia lub metody) podanego źródła danych.

Warto rozważyć używanie tej opcji zamiast funkcji **WHERE** opisanej wcześniej w tym przykładzie.

##### <a name="example-2"></a>Przykład 2

Definiuje się następujące źródła danych w mapowaniu modelu:

- **In** (typ **Rekordy tabeli**), który odwołuje się do tabeli Intrastat
- **Port** (typ **Rekordy tabeli**), który odwołuje się do tabeli IntrastatPort

Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia **FILTER (In, VALUEIN(In.Port, Port, Port.PortId)**, zostanie wygenerowana poniższa instrukcja SQL w celu zwrócenia wyfiltrowanych rekordów tabeli Intrastat:

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Dla pól **dataAreaId** zostanie wygenerowana końcowa instrukcja SQL przy użyciu operatora **IN**.

##### <a name="example-3"></a>Przykład 3

Definiuje się następujące źródła danych w mapowaniu modelu:

- **Le** (typ **Pole obliczeniowe**), które zawiera wyrażenie **SPLIT ("DEMF,GBSI,USMF", ",")**
- **In** (typ **Rekordy tabeli**), które odwołuje się do tabeli Intrastat i ma włączoną opcję **Międzyfirmowe**

Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia **FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)**, końcowa instrukcja SQL zawiera następujący warunek:

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

### <a name="mathematical-functions"></a>Funkcje matematyczne

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| ABS (liczba) | Zwracanie wartości bezwzględnej podanej liczby. (Innymi słowy zwracanie liczby bez znaku). | **ABS (-1)** zwraca **1**. |
| POWER (liczba, potęga) | Zwracanie wyniku będącego podniesieniem podanej liczby dodatniej do określonej potęgi. | **POWER (10, 2)** zwraca **100**. |
| NUMBERVALUE (ciąg, separator dziesiętny, separator grupowania cyfr) | Konwertowanie określonego ciągu na liczbę. Wybrany separator dziesiętny rozdziela części całkowitą i ułamkową liczby dziesiętnej. Wybrany separator grupowania cyfr jest używany jako separator tysięcy. | **NUMBERVALUE("1 234,56", ",", " ")** zwraca wartość **1234.56**. |
| VALUE (ciąg) | Konwertowanie określonego ciągu na liczbę. Przecinki i kropki (.) są traktowane jako separatory dziesiętne, a wiodący łącznik (-) jako znak minusa. Zgłaszanie wyjątku, jeśli podany ciąg zawiera inne nieliczbowe znaki. | **VALUE ("1 234,56")** generuje wyjątek. |
| ROUND (liczba, miejsca dziesiętne) | Zwracanie podanej liczby po zaokrągleniu do określonej liczby miejsc po przecinku:<ul><li>Jeśli wartość parametru **miejsca dziesiętne** jest większa niż 0 (zero), podana liczba jest zaokrąglana do tej liczby miejsc po przecinku.</li><li>Jeśli wartość parametru **miejsca dziesiętne** wynosi **0** (zero), podana liczba jest zaokrąglana do najbliższej liczby całkowitej.</li><li>Jeśli wartość parametru **miejsca dziesiętne** jest mniejsza niż 0 (zero), podana liczba jest zaokrąglana do liczby na lewo od separatora dziesiętnego.</li></ul> | **ROUND (1200.767, 2)** zaokrągla do dwóch miejsc po przecinku i zwraca **1200.77**. **ROUND (1200.767, -3)** zaokrągla do najbliższej wielokrotności 1000 i zwraca **1000**. |
| ROUNDDOWN (liczba, miejsca dziesiętne) | Zwracanie podanej liczby po zaokrągleniu w dół do określonej liczby miejsc po przecinku.<blockquote>[!NOTE] Ta funkcja zachowuje się jak funkcja **ROUND**, ale zawsze zaokrągla podaną liczbę do dołu (w stronę zera).</blockquote> | **ROUNDDOWN (1200.767, 2)** zaokrągla w dół do dwóch miejsc po przecinku i zwraca **1200.76**. **ROUNDDOWN (1700.767, -3)** zaokrągla w dół do najbliższej wielokrotności 1000 i zwraca **1000**. |
| ROUNDUP (liczba, miejsca dziesiętne) | Zwracanie podanej liczby po zaokrągleniu w górę do określonej liczby miejsc po przecinku.<blockquote>[!NOTE] Ta funkcja zachowuje się jak funkcja **ROUND**, ale zawsze zaokrągla podaną liczbę do góry (od zera).</blockquote> | **ROUNDUP (1200.763, 2)** zaokrągla w górę do dwóch miejsc po przecinku i zwraca **1200.77**. **ROUNDUP (1200.767, -3)** zaokrągla w górę do najbliższej wielokrotności 1000 i zwraca **2000**. |

### <a name="data-conversion-functions"></a>Funkcje konwersji danych

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| VALUE (ciąg) | Konwertowanie określonego ciągu na liczbę. Przecinki i kropki (.) są traktowane jako separatory dziesiętne, a wiodący łącznik (-) jako znak minusa. Zgłaszanie wyjątku, jeśli podany ciąg zawiera inne nieliczbowe znaki. | **VALUE ("1 234,56")** generuje wyjątek. |
| NUMBERVALUE (ciąg, separator dziesiętny, separator grupowania cyfr) | Konwertowanie określonego ciągu na liczbę. Wybrany separator dziesiętny rozdziela części całkowitą i ułamkową liczby dziesiętnej. Wybrany separator grupowania cyfr jest używany jako separator tysięcy. | **NUMBERVALUE("1 234,56", ",", " ")** zwraca wartość **1234,56**. |
| INTVALUE (ciąg tekstowy) | Zwracanie podanego ciągu znaków w postaci liczby całkowitej. Wszystkie miejsca dziesiętne są obcinane. | **INTVALUE ("100,77")** zwraca wartość **100**. |
| INTVALUE (liczba) | Zwracanie podanej liczby w postaci liczby całkowitej. Wszystkie miejsca dziesiętne są obcinane. | **INTVALUE (-100,77")** zwraca wartość **-100**. |
| INT64VALUE (ciąg) | Zwracanie podanego ciągu znaków w postaci liczby int64. Wszystkie miejsca dziesiętne są obcinane. | **INT64VALUE ("-22565422744")** zwraca **22565422744**. |
| INT64VALUE (liczba) | Zwracanie podanej liczby w postaci liczby int64. Wszystkie miejsca dziesiętne są obcinane. | **INT64VALUE (22565422744.00)** zwraca **22565422744**. |

### <a name="record-functions"></a>Funkcje zapisu

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| NULLCONTAINER (lista) | Zwracanie rekordu **null**, który ma taką samą strukturę, jak podana lista rekordów lub rekord.<blockquote>[!NOTE] Ta funkcja jest przestarzała. Zamiast niej należy używać funkcji **EMPTYRECORD**.</blockquote> | **NULLCONTAINER (SPLIT ("abc", 1))** zwraca nowy pusty rekord, który ma taką samą strukturę, jak lista zwracana przez funkcję **SPLIT**. |
| EMPTYRECORD (rekord) | Zwracanie rekordu **null**, który ma taką samą strukturę, jak podana lista rekordów lub rekord.<blockquote>[!NOTE] Rekord **null** jest rekordem, w którym wszystkie pola mają wartość pustą. Wartość pusta to **0** (zero) w przypadku liczb, pusty ciąg w przypadku ciągów tekstowych, itd.</blockquote> | **EMPTYRECORD (SPLIT ("abc", 1))** zwraca nowy pusty rekord, który ma taką samą strukturę, jak lista zwracana przez funkcję **SPLIT**. |

### <a name="text-functions"></a>Funkcje tekstowe

<table>
<thead>
<tr>
<th>Funkcja</th>
<th>opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr>
<td>UPPER (ciąg)</td>
<td>Zwracanie określonego ciągu po jego przekonwertowaniu na wielkie litery.</td>
<td><strong>UPPER(&quot;Przykład&quot;)</strong> zwraca <strong>&quot;PRZYKŁAD&quot;</strong>.</td>
</tr>
<tr>
<td>LOWER (ciąg)</td>
<td>Zwracanie określonego ciągu po jego przekonwertowaniu na małe litery.</td>
<td><strong>LOWER (&quot;Przykład&quot;)</strong> zwraca <strong>&quot;przykład&quot;</strong>.</td>
</tr>
<tr>
<td>LEFT (ciąg, liczba znaków)</td>
<td>Zwracanie określonej liczby znaków od początku wskazanego ciągu tekstowego.</td>
<td><strong>LEFT (&quot;Przykład&quot;, 3)</strong> zwraca <strong>&quot;Prz&quot;</strong>.</td>
</tr>
<tr>
<td>RIGHT (ciąg, liczba znaków)</td>
<td>Zwracanie określonej liczby znaków od końca wskazanego ciągu tekstowego.</td>
<td><strong>RIGHT (&quot;Przykład&quot;, 3)</strong> zwraca <strong>&quot;ład&quot;</strong>.</td>
</tr>
<tr>
<td>MID (ciąg, pozycja początkowa, liczba znaków)</td>
<td>Zwracanie określonej liczby znaków z podanego ciągu, począwszy od wskazanej pozycji.</td>
<td><strong>MID (&quot;Przykład&quot;, 2, 3)</strong> zwraca <strong>&quot;rzy&quot;</strong>.</td>
</tr>
<tr>
<td>LEN (ciąg)</td>
<td>Zwracanie liczby znaków istniejących w podanym ciągu tekstowym.</td>
<td><strong>LEN (&quot;Przykład&quot;)</strong> zwraca <strong>6</strong>.</td>
</tr>
<tr>
<td>CHAR (liczba)</td>
<td>Zwracanie ciągu znaków, do którego odwołuje się określona liczba Unicode.</td>
<td><strong>CHAR (255)</strong> zwraca <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE] Ciąg zwrócony przez funkcję zależy od kodowania wybranego w nadrzędnym elemencie formatu PLIK. Lista obsługiwanych kodowań znajduje się w temacie <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Klasa Encoding</a>.</blockquote>
</td>
</tr>
<tr>
<td>CONCATENATE (ciąg 1 [, ciąg 2, …])</td>
<td>Zwracanie wszystkich podanych ciągów tekstowych po ich połączeniu w jeden ciąg.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> zwraca <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE] Wyrażenie <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> również zwraca wartość <strong>&quot;abcdef&quot;</strong>.</blockquote>
</td>
</tr>
<tr>
<td>TRANSLATE (ciąg, wzorzec, ciąg zastępczy)</td>
<td>Zwracanie określonego ciągu, w którym wszystkie wystąpienia znaków w określonym ciągu wzorcowym są zastąpione na odpowiednich pozycjach znakami z określonego ciągu zastępczego.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> zastępuje wzorzec <strong>&quot;cd&quot;</strong> ciągiem <strong>&quot;GH&quot;</strong> i zwraca <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>REPLACE (ciąg, wzorzec, ciąg zastępczy, flaga wyrażenia regularnego)</td>
<td>Gdy podany parametr <strong>flaga wyrażenia regularnego</strong> ma wartość <strong>true</strong>, funkcja zwraca podany ciągu znaków po zmodyfikowaniu przez zastosowanie wyrażenia regularnego określonego jako argument <strong>wzorzec</strong> tej funkcji. To wyrażenie służy do znalezienia znaków, które należy zastąpić. Znaki podanego argumentu <strong>ciąg zastępczy</strong> zastępują znalezione znaki. Gdy podany parametr <strong>flaga wyrażenia regularnego</strong> ma wartość <strong>false</strong>, funkcja zachowuje się jak funkcja <strong>TRANSLATE</strong>.</td>
<td><strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> stosuje wyrażenie regularne, które usuwa wszystkie symbole nieliczbowe i zwraca <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> zastępuje wzorzec <strong>&quot;cd&quot;</strong> ciągiem <strong>&quot;GH&quot;</strong> i zwraca <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>TEXT (dane wejściowe)</td>
<td>Zwracanie określonych danych wejściowych po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia programu Finance and Operations. Dla wartości typu <strong>faktyczny</strong> konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</td>
<td>Jeśli ustawienia regionalne serwera wystąpienia programu Finance and Operations są określone jako <strong>EN-US</strong>, funkcja <strong>TEXT (NOW ())</strong> zwraca datę bieżącej sesji programu Finance and Operations, 17 grudnia 2015 roku, jako ciąg tekstowy <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> zwraca <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr>
<td>FORMAT (ciąg 1, ciąg 2[, ciąg 3, ...])</td>
<td>Zwracanie określonego ciągu po sformatowaniu poprzez zastąpienie wszystkich wystąpień elementu <strong>%N</strong> <em>n</em>-tym argumentem. Argumenty są ciągami tekstowymi. Jeśli dla parametru nie podano argumentu, parametr jest zwracany w ciągu jako <strong>&quot;%N&quot;</strong>. Dla wartości typu <strong>faktyczny</strong> konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</td>
<td>Na poniższej ilustracji źródło danych <strong>PaymentModel</strong> zwraca listę rekordów odbiorców przy użyciu składnika <strong>Customer</strong> oraz wartość daty przetwarzania przy użyciu pola <strong>ProcessingDate</strong>.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>W formacie raportowania elektronicznego przeznaczonym do generowania pliku elektronicznego dla wybranych odbiorców <strong>PaymentModel</strong> jest wybrane jako źródło danych i kontroluje przebieg procesu. Jest zgłaszany wyjątek w celu poinformowania użytkownika, gdy wybrany odbiorca jest zablokowany w dniu generowania raportu. Formuła przeznaczona dla tego typu kontroli przetwarzania może skorzystać z poniższych zasobów:</p>
<ul>
<li>Etykieta SYS70894 programu Finance and Operations, która ma następujący tekst:
<ul>
<li><strong>W języku polskim:</strong> &quot;Nie ma nic do wydrukowania&quot;</li>
<li><strong>W języku niemieckim:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Etykieta SYS18389 programu Finance and Operations, która ma następujący tekst:
<ul>
<li><strong>W języku polskim:</strong> &quot;Odbiorca %1 jest zablokowany do %2.&quot;</li>
<li><strong>W języku niemieckim:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Poniżej przedstawiono formułę, którą można zaprojektować:</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Jeśli raport jest przetwarzany dla odbiorcy <strong>Litware Retail</strong> w dniu 17 grudnia 2015 r. w kulturze <strong>PL</strong> i języku <strong>PL</strong>, formuła zwraca następujący tekst, który może być prezentowany użytkownikowi jako komunikat o wyjątku:</p>
<p>&quot;Nie ma nic do wydrukowania. Odbiorca Litware Retail jest zablokowany do 17.12.2015.&quot;</p>
<p>Jeśli ten sam raport będzie przetwarzany dla odbiorcy <strong>Litware Retail</strong> w dniu 17 grudnia 2015 w języku <strong>DE</strong> i kulturze <strong>DE</strong>, formuła zwraca następujący tekst:</p>
<p>&quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot;</p>
<blockquote>[!NOTE] W formułach raportowania elektronicznego dla etykiet jest stosowana następująca składnia:
<ul>
<li><strong>Etykiety zasobów programu Finance and Operations:</strong> <strong>@&quot;X&quot;</strong>, gdzie <strong>X</strong> oznacza identyfikator etykiety w drzewie obiektów aplikacji (AOT)</li>
<li><strong>Etykiety, które znajdują się w konfiguracjach ER:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, gdzie <strong>X</strong> oznacza identyfikator etykiety w konfiguracji raportowania elektronicznego</li>
</ul>
</blockquote>
</td>
</tr>
<tr>
<td>NUMBERFORMAT (liczba, format)</td>
<td>Zwracanie określonej liczby w określonym formacie w postaci ciągu tekstowego. (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standardowe</a> i <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">niestandardowe</a>). Kontekst, w którym ta funkcja jest uruchamiana, decyduje o kulturze używanej do formatowania liczb.</td>
<td>W kulturze EN-US <strong>NUMBERFORMAT (0,45, &quot;p&quot;)</strong> zwraca <strong>&quot;% 45,00&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> zwraca <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr>
<td>NUMBERFORMAT (liczba, format, kultura)</td>
<td>Zwracanie określonego ciągu tekstowego o określonym numerze w określonym formacie i danej kulturze. (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz <a href="https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings">standardowe</a> i <a href="https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings">niestandardowe</a>.).</td>
<td><strong>NUMBERFORMAT (10/3, „F2”, „de”)</strong> powoduje <strong>zwrócenie 3,33,</strong> a <strong>NUMBERFORMAT (10/3, „F2”, „en-us”)</strong> powoduje <strong>zwrócenie 3.33</strong>.</td>
</tr>
<tr>
<td>NUMERALSTOTEXT (liczba, język, waluta, flaga nazwy waluty wydruku, miejsca dziesiętne)</td>
<td>Zwracanie podanej liczby po jej przeliterowaniu (przekonwertowaniu na ciągi tekstowe) w wybranym języku. Kod języka jest opcjonalny. Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używany kod języka aktualnie uruchomionego kontekstu. (Kod języka uruchomionego kontekstu jest określany dla generowanego folderu lub pliku). Również kod waluty jest opcjonalny. Gdy jest zdefiniowany jako pusty ciąg znaków, jest używana waluta firmy.
<blockquote>[!NOTE] Parametry <strong>flaga nazwy waluty wydruku</strong> i <strong>liczba miejsc dziesiętnych</strong> są analizowane tylko dla następujących kodów języków: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong> i <strong>RU</strong>. Ponadto parametr <strong>flaga nazwy waluty wydruku</strong> w programie Finance and Operations jest analizowany tylko dla firm, których kontekst kraju lub regionu obsługuje deklinację nazw walut.</blockquote>
</td>
<td><strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> zwraca <strong>&quot;One Thousand Two Hundred Thirty Four and 56&quot;</strong>. <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> zwraca <strong>&quot;Sto dwadzieścia&quot;</strong>. <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> zwraca <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr>
<td>PADLEFT (ciąg, długość, znaki dopełnienia)</td>
<td>Zwracanie ciągu o określonej długości, w którym początek ciągu jest dopełniany określonymi znakami.</td>
<td><strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> zwraca ciąg tekstowy <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr>
<td>TRIM (ciąg)</td>
<td>Zwracanie podanego ciągu tekstowego po obcięciu spacji wiodących i końcowych oraz usunięciu spacji wielokrotnych spomiędzy wyrazów.</td>
<td><strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Przykładowy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;tekst&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> zwraca <strong>&quot;Przykładowy tekst&quot;</strong>.</td>
</tr>
<tr>
<td>GETENUMVALUEBYNAME (ścieżka źródła danych wartości stałotekstowej, tekst etykiety wartości stałotekstowej)</td>
<td>Zwracanie wartości źródła danych wartości stałotekstowej na podstawie wskazanego tekstu w etykiecie wartości stałotekstowej.</td>
<td>Na poniższej ilustracji wartość stałotekstowa <strong>ReportDirection</strong> została wprowadzona do modelu danych. Należy zauważyć, że etykiety są zdefiniowane dla wartości stałotekstowych.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Na ilustracji przedstawiono następujące szczegóły:</p>
<ul>
<li>Wartość stałotekstowa <strong>ReportDirection</strong> modelu jest wstawiona do raportu jako źródło danych <strong>$Direction</strong>.</li>
<li>Wyrażenie ER <strong>$IsArrivals</strong> jest zaprojektowane tak, aby używało wartości stałotekstowej modelu jako parametru tej funkcji. Wartością tego wyrażenia jest <strong>TRUE</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>
</td>
</tr>
<tr>
<td>GUIDVALUE (dane wejściowe)</td>
<td>Przekształć dane wejściowe typu <strong>Ciąg</strong> na element danych o typie danych <strong>Identyfikator Guid</strong>.<blockquote>[!NOTE] Aby wykonać przekształcenie w przeciwnym kierunku (tzn. aby przekonwertować podane dane wejściowe o typie danych <strong>GUID</strong> na element danych o typie danych <strong>String</strong>), można użyć funkcji <strong>TEXT()</strong>.</blockquote></td>
<td>Definiuje się następujące źródła danych w mapowaniu modelu:
<ul>
<li><strong>myID</strong> (typ <strong>Pole obliczeniowe</strong>), w którym znajduje się wyrażenie <strong>GUIDVALUE(&quot;AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0&quot;)</strong></li>
<li><strong>Users</strong> (typ <strong>Rekordy tabeli</strong>), który odwołuje się do tabeli UserInfo</li>
</ul>
Po zdefiniowaniu tych źródeł danych, można użyć wyrażenia takiego jak <strong>FILTR (użytkownicy, Users.objectId = myID)</strong> do filtrowania tabeli UserInfo przez <strong>objectId</strong> pole <strong>GUID</strong> typu danych.
</td>
</tr>
<tr>
<td>JSONVALUE (identyfikator, ścieżka)</td>
<td>Analizowanie danych w formacie JSON (JavaScript Object Notation), do którego dostęp jest uzyskiwany za pośrednictwem wskazanej ścieżki w celu wyodrębnienia wartości skalarnej opartej na podanym identyfikatorze.</td>
<td>Źródło danych <strong>$JsonField</strong> zawiera następujące dane w formacie JSON: <strong>{&quot;Numer_kompilacji&quot;:&quot;7.3.1234.1&quot;, &quot;KeyThumbprint&quot;:&quot;7366E&quot;}</strong>. Dla tego źródła danych wyrażenie </strong>JSONVALUE (&quot;BuildNumber&quot;, $JsonField)</strong> zwraca wartość <strong>7.3.1234.1</strong> o typie danych <strong>Ciąg</strong>.</td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Funkcje konwersji danych

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| TEXT (dane wejściowe) | Zwracanie określonych danych wejściowych po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia programu Finance and Operations. Dla wartości typu **faktyczny** konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych. | Jeśli ustawienia regionalne serwera wystąpienia programu Finance and Operations są określone jako **EN-US**, funkcja **TEXT (NOW ())** zwraca datę bieżącej sesji programu Finance and Operations, 17 grudnia 2015 roku, jako ciąg tekstowy **"12/17/2015 07:59:23 AM"**. **TEXT (1/3)** zwraca **"0.33"**. |
| QRCODE (ciąg tekstowy) | Zwracanie obrazu kodu QR (Quick Response Code) w formacie binarnym base64 dla podanego ciągu. | **QRCODE ("Przykładowy tekst")** zwraca **U2FtcGxlIHRleHQ =**. |

### <a name="data-collection-functions"></a>Funkcje gromadzenia danych

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Zwracanie nazwy elementu bieżącego formatu. Zwracanie pustego ciągu, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona. | Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik po zadaniu **ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania**, który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**. |
| SUMIFS (ciąg klucza dla sumowania, ciąg zakresu kryteriów 1, ciąg wartości kryteriów 1 \[, ciąg zakresu kryteriów 2, ciąg wartości kryteriów 2, …\]) | Zwracanie sumy wartości, które zostały zebrane z węzłów XML (z nazwami zdefiniowanymi jako kluczami) podczas wykonywania formatu i spełniają wprowadzone warunki (pary zakresów i wartości). Zwracanie wartość **0** (zero), gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona. | |
| SUMIF (ciąg klucza dla sumowania, ciąg zakresu kryteriów, ciąg wartości kryteriów) | Zwracanie sumy wartości, które zostały zebrane z węzłów XML (z nazwami zdefiniowanymi jako kluczami) podczas wykonywania formatu i spełniają wprowadzony warunek (zakres i wartość). Zwracanie wartość **0** (zero), gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona. | |
| COUNTIFS (ciąg zakresu kryteriów 1, ciąg wartości kryteriów 1 \[, ciąg zakresu kryteriów 2, ciąg wartości kryteriów 2, …\]) | Zwracanie liczby węzłów XML, które zostały zebrane podczas wykonywania formatu i spełniają wprowadzone warunki (pary zakresów i wartości). Zwracanie wartość **0** (zero), gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona. | |
| COUNTIF (ciąg zakresu kryteriów, ciąg wartości kryteriów) | Zwracanie liczby węzłów XML, które zostały zebrane podczas wykonywania formatu i spełniają wprowadzony warunek (zakres i wartość). Zwracanie wartość **0** (zero), gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona. | |
| COLLECTEDLIST (ciąg zakresu kryteriów 1, ciąg wartości kryteriów 1 \[, ciąg zakresu kryteriów 2, ciąg wartości kryteriów 2, …\]) | Zwracanie listy wartości, które zostały zebrane z węzłów XML podczas wykonywania formatu i spełniają wprowadzone warunki (zakres i wartość). Zwracanie pustej listy, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona. | |

### <a name="other-business-domainspecific-functions"></a>Inne funkcje (specyficzne dla domeny biznesowej)

| Funkcja | opis | Przykład |
|----------|-------------|---------|
| CONVERTCURRENCY (kwota, waluta źródłowa, waluta docelowa, data, firma) | Konwertowanie określonej kwoty pieniężnej ze wskazanej waluty źródłowej na określoną walutę docelową przy użyciu ustawień określonej firmy programu Finance and Operations na określony dzień. | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** zwraca równoważność jednego euro w dolarach amerykańskich w dniu bieżącej sesji na podstawie ustawień dla firmy DEMF. |
| ROUNDAMOUNT (liczba, miejsca dziesiętne, reguła zaokrąglania) | Zaokrąglanie podanej kwoty do określonej liczby miejsc dziesiętnych zgodnie z ustawioną regułą zaokrąglania.<blockquote>[!NOTE] Reguła zaokrąglania musi być podana jako wartość elementu stałotekstowego **RoundOffType** programu Finance and Operations.</blockquote> | Jeśli w parametrze **model.RoundOff** ustawiono wartość **W dół**, wyrażenie **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** zwraca wartość **1000.78**. Jeśli w parametrze **model.RoundOff** ustawiono wartość **Normalnie** lub **Zaokrąglenie w górę**, wyrażenie **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** zwraca wartość **1000.79**. |
| CURCredRef (cyfry) | Zwracanie odwołania do wierzyciela w oparciu o cyfry określonego numeru faktury. | **CURCredRef ("VEND-200002")** zwraca **"2200002"**. |
| MOD\_97 (cyfry) | Zwracanie odwołania do wierzyciela jako wyrażenia MOD97 w oparciu o cyfry określonego numeru faktury. | **MOD\_97 ("VEND-200002")** zwraca **"20000285"**. |
| ISOCredRef (cyfry) | Zwracanie odwołania do wierzyciela w formacie Międzynarodowej Organizacji Normalizacyjnej (ISO) w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury.<blockquote>[!NOTE] Aby wyeliminować symbole z alfabetów niezgodnych z systemem ISO, parametr wejściowy musi zostać przetłumaczony przed przekazaniem go do tej funkcji.</blockquote> | **ISOCredRef ("VEND-200002")** zwraca **"RF23VEND-200002"**. |
| CN\_GBT\_AdditionalDimensionID (ciąg, liczba) | Pobieranie określonego identyfikatora dodatkowego wymiaru finansowego. W parametrze **ciąg** wymiary są przedstawiane jako identyfikatory rozdzielone przecinkami. Parametr **numer** określa numer kolejny żądanego wymiaru w ciągu. | **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** zwraca **"CC"**. |
| GetCurrentCompany () | Zwracanie tekstowej reprezentacji kodu firmy, do której użytkownik jest aktualnie zalogowany. | **GETCURRENTCOMPANY ()** zwraca **USMF** dla użytkownika zalogowanego do firmy **Contoso Entertainment System USA** w programie Finance and Operations. |
| CH\_BANK\_MOD\_10 (cyfry) | Zwracanie odwołania do wierzyciela jako wyrażenia MOD10 w oparciu o cyfry określonego numeru faktury. | **CH\_BANK\_MOD\_10 ("VEND-200002")** zwraca **3**. |
| FA\_SUM (kod środka trwałego, kod modelu ewidencji, data początkowa, data końcowa) | Zwracanie przygotowanego kontenera danych dla kwoty środka trwałego w wybranym okresie. | **FA\_SUM ("COMP-000001", "Current", Date1, Date2)** zwraca przygotowany kontener danych środka trwałego **"COMP-000001"**, który ma model ewidencji **"Bieżący"** za okres od **Date1** do **Date2**. |
| FA\_BALANCE (kod środka trwałego, kod modelu ewidencji, rok sprawozdawczy, data raportowania) | Zwracanie przygotowanego kontenera danych dla salda środka trwałego. Rok sprawozdawczy musi być podany jako wartość stałotekstowa **AssetYear** w programie Finance and Operations. | **FA\_SUM ("COMP-000001", "Bieżący", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** zwraca przygotowany kontener sald dla środka trwałego **"COMP-000001"**, który ma model ewidencji **"Bieżący"** na dzień bieżącej sesji programu Finance and Operations. |
| TABLENAME2ID (ciąg) | Zwracanie reprezentacji identyfikatora tabeli dla danej nazwy tabeli w postaci liczby całkowitej. | **TABLENAME2ID ("Intrastat")** zwraca **1510**. |
| ISVALIDCHARACTERISO7064 (ciąg) | Zwracanie wartości logicznej **TRUE**, gdy podany ciąg tekstowy reprezentuje prawidłowy międzynarodowy numer konta bankowego (IBAN). W przeciwnym razie zwracanie wartości logicznej **FALSE**. | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** zwraca wartość **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** zwraca wartość **FALSE**. |
| NUMSEQVALUE (kod numeracji, zakres, identyfikator zakresu) | Zwracanie nowo wygenerowanej wartości numeru kolejnego na podstawie podanego kodu numeracji, zakresu i identyfikatora zakresu. Zakres musi być określony jako wartość elementu stałotekstowego **ERExpressionNumberSequenceScopeType** (**Współdzielony**, **Podmiot prawny** lub **Firma**). Dla zakresu **Współdzielony** należy określić pusty ciąg jako identyfikator zakresu. Dla zakresów **Firma** i **Podmiot prawny** należy podać kod firmy jako identyfikatora zakresu. Jeśli dla zakresów **Firma** i **Podmiot prawny** określisz pusty ciąg jako identyfikator zakresu, zostanie użyty bieżący kod firmy. | Definiuje się następujące źródła danych w mapowaniu modelu:<ul><li>**enumScope** (typ **Element stałotekstowy programu Dynamics 365 for Operations**), który odwołuje się do elementu stałotekstowego **ERExpressionNumberSequenceScopeType**</li><li>**NumSeq** (typ **Pole obliczeniowe**), który zawiera wyrażenie **NUMSEQVALUE ("Gene\_1", enumScope.Company, "")**</li></ul>Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji **Gene\_1** skonfigurowanej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego. |
| NUMSEQVALUE (kod numeracji) | Zwracanie nowo wygenerowanej wartości numeracji na podstawie podanej numeracji, zakresu **Firma** i (jako identyfikatora zakresu) kodu firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego. | W mapowaniu modelu definiujesz następujące źródło danych: **NumSeq** (typ **Pole obliczeniowe**). To źródło danych zawiera wyrażenie **NUMSEQVALUE ("Gene\_1")**. Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji **Gene\_1** skonfigurowanej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego. |
| NUMSEQVALUE (identyfikator rekordu numeracji) | Zwracanie nowo wygenerowanej wartości numeru kolejnego na podstawie podanego identyfikatora rekordu numeracji. | Definiuje się następujące źródła danych w mapowaniu modelu:<ul><li>**LedgerParms** (typ **Rekordy tabeli**), który odwołuje się do tabeli LedgerParameters</li><li>**NumSeq** (typ **Pole obliczeniowe**), który zawiera wyrażenie **NUMSEQVALUE (LedgerParameters.'numRefJournalNum()'.NumberSequenceId)**</li></ul>Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji skonfigurowanej w oknie Parametry księgi głównej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego. Ta numeracja jednoznacznie identyfikuje arkusze i dostarcza numer partii, który łączy transakcje ze sobą. |

### <a name="functions-list-extension"></a>Rozszerzenie listy funkcji

Model raportowania elektronicznego umożliwia rozszerzanie listy funkcji używanych w wyrażeniach ER. Wymaga to działań programistycznych. Aby uzyskać szczegółowe informacje, zobacz [Rozszerzanie listy funkcji raportowania elektronicznego](general-electronic-reporting-formulas-list-extension.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Poszerzanie listy funkcji raportowania elektronicznego (ER)](general-electronic-reporting-formulas-list-extension.md)
