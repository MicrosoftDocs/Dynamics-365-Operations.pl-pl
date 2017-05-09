---
title: "Projektant formuł w raportowaniu elektronicznym"
description: "W tym temacie wyjaśniono, jak używać projektanta formuł w raportowaniu elektronicznym (ER). Podczas projektowania formatu dla określonego dokumentu elektronicznego w module raportowania elektronicznego można używać formuł podobnych do znanych z programu Microsoft Excel w celu przekształcania danych w sposób spełniający wymagania dotyczące realizacji i formatowania tego dokumentu. Obsługiwane są różne typy funkcji: tekstu, daty i godziny, matematyczne, logiczne, informacyjne, konwersji typów danych i inne (specyficzne dla domeny biznesowej)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ac8d6c064ca826cc1c2fed07578ca9ce0c66ef66
ms.lasthandoff: 03/31/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Projektant formuł w raportowaniu elektronicznym

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak używać projektanta formuł w raportowaniu elektronicznym (ER). Podczas projektowania formatu dla określonego dokumentu elektronicznego w module raportowania elektronicznego można używać formuł podobnych do znanych z programu Microsoft Excel w celu przekształcania danych w sposób spełniający wymagania dotyczące realizacji i formatowania tego dokumentu. Obsługiwane są różne typy funkcji: tekstu, daty i godziny, matematyczne, logiczne, informacyjne, konwersji typów danych i inne (specyficzne dla domeny biznesowej).

<a name="formula-designer-overview"></a>Projektant formuł — omówienie
-------------------------

Raportowanie elektroniczne (ER) obsługuje projektanta formuł. Z tego względu w czasie projektowania można konfigurować wyrażenia, które mogą być używane do następujących zadań w czasie wykonywania:

-   Przekształcanie danych otrzymanych z bazy danych programu Microsoft Dynamics 365 for Operations, które powinny być umieszczone w modelu danych ER (raportowania elektronicznego) zaprojektowanym jako źródło danych dla formatów ER (filtrowanie, grupowanie, konwersje typów danych itp.).
-   Formatowanie danych, które muszą zostać wysłane do generowanego dokumentu elektronicznego zgodnie z układem i warunkami określonego formatu ER (według żądanego języka lub kultury, szyfrowania itp.).
-   Kontrolowania procesu generowania dokumentów elektronicznych (włączanie/wyłączanie tworzenia określonych elementów formatu w zależności od przetwarzania danych, przerywania tworzenia dokumentów, wysyłania komunikatów do użytkowników końcowych itp.).

Stronę projektanta formuł można otworzyć podczas wykonywania następujących czynności:

-   Wiązanie elementów źródła danych ze składnikami modelu danych.
-   Wiązanie elementów źródła danych ze składnikami formatu.
-   Obsługa pól obliczeniowych w ramach źródeł danych.
-   Definiowanie warunków widoczności dla parametrów wejściowych użytkownika.
-   Projektowanie przekształceń formatu.
-   Definiowanie warunków włączania składników formatu.
-   Definiowanie nazw plików dla plikowych składników formatu.
-   Definiowanie warunków weryfikacji kontroli procesu.
-   Definiowanie treści komunikatów weryfikacji kontroli procesu.

## <a name="designing-er-formulas"></a>Projektowanie formuł ER
### <a name="data-binding"></a>Wiązanie danych

Projektant formuł raportowania elektronicznego może służyć do definiowania wyrażenia przekształcającego dane otrzymywane ze źródeł danych, dzięki czemu dane mogą być umieszczane w danych klienta w czasie wykonywania:

-   ze źródeł danych programu Dynamics 365 for Operations i parametrów czasu wykonywania na model danych ER,
-   z modelu danych ER na format ER,
-   ze źródeł danych programu Dynamics 365 for Operations i parametrów czasu wykonywania na format ER.

Poniższa ilustracja pokazuje projekt wyrażenia tego typu. W tym przykładzie wyrażenie zwróci wartość pola **Intrastat.AmountMST** tabeli **Intrastat** programu Dynamics 365 for Operations po uprzednim zaokrągleniu wartości do dwóch miejsc dziesiętnych. [![picture-expression-binding](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) Na poniższej ilustracji przedstawiono sposób używania tego typu wyrażenia. W tym przykładzie wynik zaprojektowanego wyrażenia jest umieszczany w składniku **Transaction.InvoicedAmount** modelu danych **Model raportowania podatku**. [![picture-expression-binding2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) W czasie wykonywania zaprojektowana formuła **ROUND (Intrastat.AmountMST, 2)** zaokrągla wartość pola **AmountMST** dla każdego rekordu tabeli **Intrastat** do dwóch miejsc dziesiętnych, a następnie umieszcza zaokrągloną wartość w składniku **Transaction.InvoicedAmount** modelu danych **Raportowanie podatku**.

### <a name="data-formatting"></a>Formatowanie danych

Projektant formuł ER może służyć do definiowania wyrażenia formatującego dane otrzymywane ze źródeł danych, dzięki czemu dane mogą być wysyłane w ramach generowania dokumentu elektronicznego. Jeśli masz formatowanie, które musi być stosowane jako typowa reguła powtarzana dla formatu, można wprowadzić to formatowanie jeden raz do konfiguracji formatu jako nazwane przekształcenie zawierające wyrażenie formatujące. Później to nazwane przekształcenie można połączyć z wieloma składnikami formatu, których dane wyjściowe muszą być sformatowane zgodnie z utworzonym wyrażeniem. Poniższa ilustracja pokazuje projekt przekształcenia tego typu. W tym przykładzie przekształcenie **TrimmedString** pobiera przychodzące dane o typie danych **Ciąg**, a przy zwracaniu wartości ciągu obcina spacje początkowe i końcowe. [![picture-transformation-design](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) Poniższa ilustracja pokazuje sposób użycia przekształcenia tego typu. W tym przykładzie kilka składników formatu, które wysyłają tekst jako dane wyjściowe do generowania dokumentu elektronicznego w czasie wykonywania, odwołuje się do przekształcenia **TrimmedString** według nazwy. [![picture-transformation-usage](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) Jeśli składniki formatu odwołują się do przekształcenia **TrimmedString** (na przykład składnik **partyName** na poprzedniej ilustracji), powoduje to wysyłanie tekstu jako danych wyjściowych do generowanego dokumentu. Tekst nie zawiera spacji wiodących ani końcowych. Jeśli jest używane formatowanie, które musi być stosowane indywidualnie, można je wprowadzić jako indywidualne wyrażenie wiązania konkretnego składnika formatu. Poniższa ilustracja pokazuje wyrażenie tego typu. W tym przykładzie składnik formatu **partyType** jest powiązany ze źródłem danych poprzez wyrażenie, które konwertuje dane przychodzące z pola **Model.Company.RegistrationType** w źródle danych na tekst pisany wielkimi literami, a następnie wysyła ten tekst jako dane wyjściowe do dokumentu elektronicznego. [![picture-binding-with-formula](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Kontrola przepływu procesu

Projektant formuł ER może służyć do definiowania wyrażeń, które kontrolują przebieg procesu generowania dokumentów. Możesz wykonać następujące zadania:

-   Zdefiniowanie warunków określających, kiedy proces tworzenia dokumentu musi zostać zatrzymany.
-   Określenie wyrażeń, które będą tworzyły komunikaty do użytkownika końcowego o zatrzymanych procesach lub wyświetlały komunikaty z dziennika wykonywania o kontynuacji procesu generowania raportu.
-   Określanie nazw plików generowanych dokumentów i kontrolowanie warunków ich tworzenia.

Każda reguła kontroli przepływu procesu została zaprojektowana jako indywidualny proces sprawdzania poprawności. Poniższa ilustracja pokazuje weryfikację tego typu. Poniżej znajduje się objaśnienie konfiguracji użytej w tym przykładzie:

-   Sprawdzanie poprawności jest dokonywane po utworzeniu węzła **INSTAT** w generowanym pliku XML.
-   Jeśli lista transakcji jest pusta, mechanizm weryfikacji zatrzymuje proces wykonywania i zwraca wartość **FALSE**.
-   Funkcja weryfikacji zwraca komunikat o błędzie zawierający treść etykiety SYS70894 w języku preferowanym przez użytkownika.

[![picture-validation](./media/picture-validation.jpg)](./media/picture-validation.jpg) Projektant formuł ER pozwala również określić nazwę pliku generowanego dokumentu elektronicznego i kontrolować proces tworzenia pliku. Poniższa ilustracja pokazuje projekt tego typu kontroli przebiegu procesu. Poniżej znajduje się objaśnienie konfiguracji użytej w tym przykładzie:

-   Lista rekordów ze źródła danych **model.Intrastat** jest podzielona na partie zawierające do 1000 rekordów.
-   Dane wyjściowe mają postać pliku zip zawierającego jeden plik w formacie XML dla każdej utworzonej partii.
-   Wyrażenie zwraca nazwę pliku dla generowania dokumentów elektronicznych, łącząc nazwę pliku i rozszerzenie pliku. Dla partii drugiej i wszystkich kolejnych nazwa pliku zawiera identyfikator partii jako sufiks.
-   Wyrażenie umożliwia (poprzez zwrócenie wartości **TRUE**) proces tworzenia plików dla partii zawierających co najmniej jeden rekord.

[![picture-file-control](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Podstawowa składnia

Wyrażenia raportowania elektronicznego mogą zawierać dowolne lub wszystkie z następujących elementów:

-   Stałe
-   Operatory
-   Odwołania
-   Ścieżki
-   Funkcje

#### <a name="constants"></a>Stałe

Do projektowania wyrażeń można używać stałych tekstowych i liczbowych (wartości, które nie są obliczane). Na przykład w wyrażeniu **VALUE ("100") + 20** są używane stała liczbowa 20 i stała ciągu „100”, a wyrażenie zwraca wartość liczbową **120**. Projektant formuł ER obsługuje sekwencje specjalne, co oznacza, że można określić ciąg wyrażenia, który powinien być traktowany inaczej. Na przykład wyrażenie **„Lew Tołstoj ”„Wojna i pokój”„ Tom 1”** zwraca ciąg tekstowy **Lew Tołstoj „Wojna i pokój” Tom 1**.

#### <a name="operators"></a>Operatory

W poniższej tabeli przedstawiono operatory arytmetyczne, których można używać do wykonania podstawowych operacji matematycznych, takich jak dodawanie, odejmowanie, dzielenie i mnożenie.

| Operator | Znaczenie              | Przykład |
|----------|----------------------|---------|
| +        | Dodanie             | 1+2     |
| -        | Odejmowanie Zaprzeczenie | 5-2 -1  |
| \*       | Mnożenie       | 7\*8    |
| /        | Oddział             | 9/3     |

W poniższej tabeli przedstawiono operatory porównania, które są obsługiwane i których można używać do porównywania dwóch wartości.

| Operator | Znaczenie                  | Przykład    |
|----------|--------------------------|------------|
| =        | Taka sama                    | X=Y        |
| &gt;     | Większe niż             | X&gt;Y     |
| &lt;     | Mniejsze niż                | X&lt;Y     |
| &gt;=    | Większe lub równe | X&gt;=Y    |
| &lt;=    | Mniejsze lub równe    | X&lt;=Y    |
| &lt;&gt; | Nie równa się             | X&lt;&gt;Y |

Ponadto można użyć znaku handlowego „i” (&) jako operatora łączenia tekstu do łączenia (składania) jednego lub kilku ciągów tekstowych w jeden element tekstu.

| Operator | Znaczenie     | Przykład                                        |
|----------|-------------|------------------------------------------------|
| &        | Złącz | „Nie ma nic do wydrukowania” & „: ” & „nie znaleziono żadnych rekordów” |

#### <a name="operator-precedence"></a>Pierwszeństwo operatorów

Kolejność, w jakiej części wyrażenia złożonego są obliczane, jest ważna. Na przykład wynik wyrażenia **1 + 4 / 2** różni się w zależności od tego, czy jako pierwsza jest wykonywana operacja dodawania, czy dzielenia. Nawiasy umożliwiają jawne zdefiniowanie sposobu wyznaczania wartości wyrażenia. Na przykład aby wskazać, że najpierw powinna być wykonywana operacja dodawania, można zmodyfikować poprzednie wyrażenie na **(1 + 4) / 2**. Jeśli kolejność operacji, które muszą być wykonywane w wyrażeniu, nie jest jawnie zdefiniowana, kolejność jest zależna od domyślnego pierwszeństwa przypisanego do obsługiwanych operatorów. Poniższe tabele zawierają operatory i priorytety przypisane do każdego z nich. Operatory o wyższym priorytecie (na przykład 7) są odczytywane przed operatorami, które mają niższy priorytet (na przykład 1).

| Pierwszeństwo | Operatory      | Składnia                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Grupowanie       | ( … )                                                    |
| 6          | Dostęp do elementu członkowskiego  | … , …                                                    |
| 5          | Wywołanie funkcji  | … ( … )                                                  |
| 4          | Zwielokrotnianie | … \* … … / …                                             |
| 3          | Addytywny       | … + … … - …                                              |
| 2          | Porównanie     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Rozdzielanie     | … , …                                                    |

Operatory w tym samym wierszu mają równy priorytet. Jeśli wyrażenie zawiera więcej niż jeden z tych operatorów, jest obliczane od lewej do prawej. Na przykład wyrażenie **1 + 6 / 2 \* 3 &gt; 5** zwraca wartość **prawda**. Zaleca się używanie nawiasów w celu jawnego wskazania żądanej kolejności obliczania wyrażeń, aby ułatwić odczyt wyrażenia i zarządzanie nim.

#### <a name="references"></a>Odwołania

Wszystkie źródła danych bieżącego składnika ER (model lub format), które są dostępne podczas projektowania wyrażenia, mogą być używane jako odwołania nazwane. Na przykład bieżący model danych ER zawiera źródło danych **ReportingDate**, które zwraca wartość o typie danych **DATETIME**. Aby ta wartość była właściwie sformatowana w generowanym dokumencie, można utworzyć odwołanie z wyrażenia do źródła danych w następujący sposób: **DATETIMEFORMAT (ReportingDate, "dd-MM-rrrr")** Wszystkie znaki w nazwie przywoływanego źródła danych, które nie reprezentują litery alfabetu, muszą być poprzedzone pojedynczym cudzysłowem ('). Jeśli nazwa przywoływanego źródła danych zawiera co najmniej jeden symbol, który nie reprezentuje litery alfabetu (na przykład znaki interpunkcyjne lub inne symbole piśmiennicze), musi zostać ujęta w pojedyncze cudzysłowy. Oto kilka przykładów:

-   Źródło danych **Dzisiejsza data & godzina** musi mieć następujące odwołanie w wyrażeniu ER: **'Dzisiejsza data & godzina'**.
-   Metoda **name()** ze źródła danych **Customers** musi mieć następujące odwołanie w wyrażeniu ER: **Customers.'name()'**.

#### <a name="path"></a>Ścieżka

Jeśli wyrażenie odwołuje się do źródła danych usystematyzowanych, można użyć definicji ścieżki, aby wybrać określony element podstawowy tego źródła danych. Znak kropki (.) jest używany do oddzielania poszczególnych elementów źródła danych usystematyzowanych. Na przykład bieżący model danych ER zawiera źródło danych **InvoiceTransactions**, które zwraca listę rekordów. Struktura rekordu **InvoiceTransactions** zawiera pola **AmountDebit** i **AmountCredit**, które zwracają wartości liczbowe. W związku z tym można zaprojektować następujące wyrażenie służące do obliczania zafakturowanej kwoty: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funkcje

W następnej sekcji opisano funkcje, które mogą być używane w wyrażeniach raportowania elektronicznego. Wszystkie źródła danych kontekstu wyrażenia (bieżący model danych ER lub format ER), a także stałe, mogą służyć jako parametry wywoływania funkcji, zgodnie z listą argumentów wywoływania funkcji. Na przykład bieżący model danych ER zawiera źródło danych **InvoiceTransactions**, które zwraca listę rekordów. Struktura rekordu **InvoiceTransactions** zawiera pola **AmountDebit** i **AmountCredit**, które zwracają wartości liczbowe. W efekcie w celu obliczania zafakturowanej kwoty można zaprojektować następujące wyrażenie używające wbudowanej funkcji zaokrąglania ER: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Obsługiwane funkcje
W poniższych tabelach opisano funkcje edycji danych, które mogą służyć do projektowania modeli danych i raportów ER. Ta lista funkcji nie jest zamknięta i może być rozszerzana przez programistów. Aby wyświetlić listę funkcji, których można użyć, przejdź do okienka funkcji w projektancie formuł ER.

### <a name="date-and-time-functions"></a>Funkcje daty i godziny

| Funkcja                                   | Opis                                                                                                                                                                                                                                                                                                                                                      | Przykład                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (data i godzina, dni)                   | Dodawanie określonej liczby dni do określonej wartości daty i godziny.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** zwraca datę i godzinę siedem dni w przyszłości.                                                                                                                                                                                                                            |
| DATETODATETIME (data)                      | Konwertowanie określonej wartości daty na wartość daty i godziny.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. 'getCurrentDate()')** zwraca datę bieżącej sesji programu Dynamics 365 for Operations, 24.12.2015, jako **12/24/2015 12:00:00 AM**. W tym przykładzie **CompInfo** jest źródłem danych ER typu **Dynamics 365 for Operations/Tabela**, które odwołuje się do tabeli CompanyInfo. |
| NOW ()                                     | Zwracanie bieżącej daty i godziny serwera aplikacji Dynamics 365 for Operations jako wartości daty i godziny.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| TODAY ()                                   | Zwracanie bieżącej daty serwera aplikacji Dynamics 365 for Operations jako wartości daty.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Zwracanie wartości daty **null**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Zwracanie wartości daty i godziny **null**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (data i godzina, format)          | Konwertowanie określonej wartości daty i godziny na ciąg znaków w określonym formacie. (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz [standardowe](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).                                                                        | **DATETIMEFORMAT (NOW(), "dd-MM-rrrr")** zwraca bieżącą datę serwera aplikacji Dynamics 365 for Operations, 24.12.2015, jako **"24-12-2015"**, zgodnie z określonym niestandardowych formatem.                                                                                                          |
| DATETIMEFORMAT (data i godzina, format, kultura) | Konwertowanie określonej wartości daty i godziny na ciąg znaków w określonym formacie i [kulturze](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz [standardowe](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "d", "de")** zwraca bieżącą datę serwera aplikacji Dynamics 365 for Operations, 24.12.2015, jako **"24.12.2015"**, zgodnie z wybraną kulturą niemiecką.                                                                                                             |
| SESSIONTODAY ()                            | Zwraca datę bieżącej sesji programu Dynamics 365 for Operations jako wartość daty.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Zwraca datę i godzinę bieżącej sesji programu Dynamics 365 for Operations jako wartość daty i godziny.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (data, format)                  | Zwraca ciąg przedstawiający datę w określonym formacie.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "dd-MM-rrrr")** zwraca datę bieżącej sesji programu Dynamics 365 for Operations, 24.12.2015, jako **"24-12-2015"**, zgodnie z określonym niestandardowych formatem.                                                                                                                      |
| DATEFORMAT (data, format, kultura)         | Konwertowanie określonej wartości daty na ciąg znaków w określonym formacie i [kulturze](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz [standardowe](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).     | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** zwraca datę bieżącej sesji programu Dynamics 365 for Operations, 24.12.2015, jako **"24.12.2015"**, zgodnie z wybraną kulturą niemiecką.                                                                                                                       |

### <a name="list-functions"></a>Lista funkcji

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funkcja</th>
<th>opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SPLIT (dane wejściowe, długość)</td>
<td>Dzielnie podanego ciągu wejściowego na podciągi, z których każdy ma określoną długość. Wynik jest zwracany jako nowa lista.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> zwraca nową listę zawierającą dwa rekordy, które mają pole <strong>STRING</strong>. Pole w pierwszym rekordzie zawiera tekst <strong>&quot;abc&quot;</strong>, a pole w drugim rekordzie zawiera tekst <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (lista, liczba)</td>
<td>Dzielenie określonej listy na partie, z których każda zawiera określoną liczbę rekordów. Wynik jest zwracany jako nowa lista partii zawierająca następujące elementy:
<ul>
<li>Partie jako zwykłe listy (składnik <strong>Value</strong>)</li>
<li>Numer bieżącej partii (składnik <strong>BatchNumber</strong>)</li>
</ul></td>
<td>W poniższym przykładzie źródło danych <strong>Lines</strong> jest tworzone jako lista trzech rekordów podzielona na partie, z których każda zawiera maksymalnie dwa rekordy. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> Poniżej widać zaprojektowany układ formatu, gdzie są tworzone wiązania ze źródłem danych <strong>Lines</strong> w celu generowania danych wyjściowych w formacie XML, który przedstawia poszczególne węzły każdej partii oraz znajdujące się w nich rekordy. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a> Poniżej widać rezultat uruchomienia zaprojektowanego formatu. <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (rekord 1 [, rekord 2, ...])</td>
<td>Zwracanie nowej listy utworzonej na podstawie określonych argumentów.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> zwraca pusty rekord, w którym lista pól zawiera wszystkie pola z list rekordów <strong>MainData</strong> i <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (lista 1, lista 2, ...)</td>
<td>Zwracanie połączonej listy utworzonej z list określonych argumentów.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> zwraca listę sześciu rekordów, gdzie jedno pole typu danych <strong>STRING</strong> zawiera pojedyncze litery.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (lista)</td>
<td>Zwracanie wartości <strong>TRUE</strong>, jeśli określona lista nie zawiera żadnych elementów. W przeciwnym jest zwracana wartość <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (lista)</td>
<td>Zwracanie pustej listy poprzez użycie określonej listy jako źródła dla struktury listy.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> zwraca nową pustą listę, która ma taką samą strukturę jak lista zwracana przez funkcję <strong>SPLIT</strong>.</td>
</tr>
<tr class="odd">
<td>FIRST (lista)</td>
<td>Zwracanie pierwszego rekordu określonej listy, jeśli ten rekord nie jest pusty. W przeciwnym razie jest zgłaszany wyjątek.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (list)</td>
<td>Zwracanie pierwszego rekordu określonej listy, jeśli ten rekord nie jest pusty. W przeciwnym razie jest zwracany rekord <strong>null</strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (lista)</td>
<td>Zwracanie listy zawierającej tylko pierwszy element określonej listy.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (ścieżka)</td>
<td>Zwracanie nowej spłaszczonej listy przedstawiającej wszystkie elementy pasujące do określonej ścieżki. Ścieżka musi być określona jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych Lista rekordów. Ścieżka do ciągu tekstowego, daty i podobnych elementów danych powinna powodować zgłaszanie błędu w czasie projektowania w konstruktorze wyrażeń ER.</td>
<td>Po wprowadzeniu <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> jako źródła danych (DS) funkcja <strong>COUNT( ALLITEMS (DS.Value))</strong> zwraca wartość <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (lista [, wyrażenie 1, wyrażenie 2, …])</td>
<td>Zwracanie określonej listy sortowanej według określonych argumentów, które mogą zostać zdefiniowane jako wyrażenia.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowany jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>ORDERBY (Vendors, Vendors.'name()')</strong> zwraca listę dostawców posortowaną według nazw w porządku rosnącym.</td>
</tr>
<tr class="even">
<td>REVERSE (lista)</td>
<td>Zwracanie określonej listy w odwrotnym porządku sortowania.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowane jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> zwraca listę dostawców posortowaną według nazw w porządku malejącym.</td>
</tr>
<tr class="odd">
<td>WHERE (lista, warunek)</td>
<td>Zwracanie określonej listy wyfiltrowanej według określonego warunku. W odróżnieniu od funkcji <strong>FILTR</strong> podany warunek jest stosowany do listy w pamięci.</td>
<td>Jeśli <strong>Vendor</strong> jest skonfigurowane jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, funkcja <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> zwraca listę dostawców należących do grupy dostawców 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (lista)</td>
<td>Zwracanie nowej listy, która zawiera stałotekstowe rekordy określonej listy oraz udostępnia następujące elementy:
<ul>
<li>Określona lista rekordów jako zwykłe listy (składnik <strong>Value</strong>)</li>
<li>Indeks bieżącego rekordu (składnik <strong>Number</strong>)</li>
</ul></td>
<td>W poniższym przykładzie źródło danych <strong>Enumerated</strong> jest tworzone jako stałotekstowa lista rekordów dostawców ze źródła danych <strong>Vendors</strong>, które odwołuje się do tabeli <strong>VendTable</strong>. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>Poniżej widać format, gdzie są tworzone powiązania danych w celu wygenerowania danych wyjściowych w formacie XML prezentującym poszczególnych dostawców jako stałotekstowe węzły. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a> Oto rezultat uruchomienia zaprojektowanego formatu. <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (lista)</td>
<td>Zwracanie liczby rekordów określonej listy, jeśli lista nie jest pusta. W przeciwnym jest zwracana wartość <strong>0</strong> (zero).</td>
<td>Funkcja <strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> zwraca wartość <strong>2</strong>, ponieważ funkcja <strong>SPLIT</strong> tworzy listę składającą się z dwóch rekordów.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (ścieżka)</td>
<td>Zwraca listę rekordów utworzoną na podstawie argumentu o jednym z następujących typów:
<ul>
<li>Wyliczenie modeli</li>
<li>Wyliczenie formatów</li>
<li>Kontener</li>
</ul>
Utworzona lista będzie zawierała rekordy z następującymi polami:
<ul>
<li>Nazwisko</li>
<li>Etykiety</li>
<li>opis</li>
</ul>
Pola Etykieta i Opis będą zwracać wartości podczas wykonywania zależne od ustawień języka formatu.</td>
<td>W poniższym przykładzie pokazano wartość stałotekstową wprowadzoną w modelu danych. <a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>Przykład poniżej pokazuje:
<ul>
<li>Wartość stałotekstowa modelu wstawiona do raportu jako źródło danych.</li>
<li>Wyrażenie ER zaprojektowane tak, aby używało wartości stałotekstowej modelu jako parametru tej funkcji.</li>
<li>Źródło danych typu Lista rekordów wstawione do raportu przy użyciu utworzonego wyrażenia ER.</li>
</ul>
<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> W poniższym przykładzie pokazano elementy formatu ER, które są powiązane ze źródłem danych typu Lista rekordów utworzonym przy użyciu funkcji LISTOFFIELDS.<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>To jest rezultat uruchomienia zaprojektowanego formatu.<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Uwaga:</strong> Przetłumaczone teksty etykiet i opisów są wprowadzane do danych wyjściowych formatu ER zgodnie z ustawieniami języka skonfigurowanymi dla nadrzędnych elementów formatu PLIK i FOLDER.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (lista, nazwa pola, separator)</td>
<td>Zwraca ciąg połączonych wartości pola z listy o wartościach rozdzielonych wybranym separatorem.</td>
<td>Jeśli jako źródło danych DS wpisani SPLIT ("abc", 1), wyrażenie STRINGJOIN (DS, DS.Value, ":") zwraca wartość „a:b:c”</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (lista, wartość limitu, źródło limitu)</td>
<td>Dzieli podaną listę na zbiór list podrzędnych i zwraca wynik w treści listy rekordów. Parametr wartości limitu określa wartość graniczną, przy której następuje podział oryginalnej listy. Parametr źródła limitu określa krok, o jaki jest zwiększana suma. Limit nie jest stosowany do pojedynczego elementu podanej listy, jeżeli źródło limitu przekracza zdefiniowany limit.</td>
<td>W przykładzie poniżej pokazano przykładowy format korzystający ze źródeł danych. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>Jest to rezultat uruchomienia formatu prezentującej prostą listę towarów w asortymencie.<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>W poniższym przykładzie przedstawiono ten sam format skorygowany w celu wyświetlania listy towarów asortymentowych w partiach, gdzie jedna partia musi zawierać towary o łącznej wadze nieprzekraczającej limitu 9.<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>To jest wynik wykonania skorygowanego formatu. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Uwaga:</strong> Limit nie obowiązuje do ostatniej pozycji oryginalnej listy, ponieważ wartość [11] jej źródła limitu (waga) przekracza zdefiniowany limit (9). Należy użyć funkcji <strong>WHERE</strong> albo wyrażenia <strong>Enabled</strong> odnośnego elementu formatu, aby zignorować (pominąć) listy podrzędne podczas generowania raportu (w razie potrzeby).</td>
</tr>
<tr class="odd">
<td>FILTER (lista, warunek)</td>
<td>Zwraca wskazaną listę wyfiltrowaną względem podanego warunku poprzez zmodyfikowanie zapytania. W odróżnieniu od funkcji <strong>WHERE</strong> podany warunek jest stosowany na poziomie bazy danych do każdego źródła danych ER o typie Rekordy tabeli.</td>
<td>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;) zwraca listę wyłącznie dostawców należących do grupy dostawców „40”, gdy <strong>Vendor</strong> jest skonfigurowane jako źródło danych ER odwołujące się do tabeli <strong>VendTable</strong>.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funkcje logiczne

| Funkcja                                                                                | opis                                                                                                                                                                                                                                                                     | Przykład                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CASE (wyrażenie, opcja 1, wynik 1 \[, opcja 2, wynik 2\] ... \[, wynik domyślny\]) | Wyznaczanie wartości określonego wyrażenia względem określonych opcji alternatywnych. Zwracany jest wynik opcji równej wartości wyrażenia. W przeciwnym razie jest zwracany opcjonalnie wprowadzony wynik domyślny (ostatni parametr niepoprzedzony opcją). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "ZIMA", "11", "ZIMA", "12", "ZIMA", "")** zwraca ciąg **"ZIMA"**, gdy data bieżącej sesji programu Dynamics 365 for Operations mieści się w okresie od października do grudnia. W przeciwnym razie zwraca ciąg pusty. |
| IF (warunek, wartość 1, wartość 2)                                                        | Zwracanie podanej wartości 1, jeśli określony warunek jest spełniony. W przeciwnym wypadku jest zwracana wartość 2. Jeśli wartości 1 i 2 są rekordami lub listami rekordów, wynik będzie miał tylko pola, które istnieją na obu listach.                                                                     | **IF (1=2, "warunek jest spełniony", "warunek nie jest spełniony")** zwraca ciąg **"warunek nie jest spełniony"**.                                                                                                                                                      |
| NOT (warunek)                                                                         | Zwracanie odwrotnej wartości logicznej określonego warunku.                                                                                                                                                                                                                   | **NOT (TRUE)** zwraca wartość **FALSE**.                                                                                                                                                                                                                            |
| AND (warunek 1\[, warunek 2, ...\])                                                 | Zwracanie wartości **TRUE**, jeśli *wszystkie* określone warunki są spełnione. W przeciwnym jest zwracana wartość **FALSE**.                                                                                                                                                                                            | Funkcja **AND (1=1, "a"="a")** zwraca wartość **TRUE**. **AND (1=2, "a"="a")** zwraca wartość **FALSE**.                                                                                                                                                                           |
| OR (warunek 1\[, warunek 2, ...\])                                                  | Zwracanie wartości **FALSE**, jeśli *żaden* określony warunek nie jest spełniony. Zwracanie wartości **TRUE**, jeśli *którykolwiek* określony warunek jest spełniony.                                                                                                                                                                 | **OR (1=2, "a"="a")** zwraca wartość **TRUE**.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Funkcje matematyczne

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funkcja</th>
<th>Opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ABS (liczba)</td>
<td>Zwracanie wartości bezwzględnej podanej liczby (liczby bez znaku).</td>
<td><strong>ABS (-1)</strong> zwraca <strong>1</strong>.</td>
</tr>
<tr class="even">
<td>POWER (liczba, potęga)</td>
<td>Zwracanie wyniku będącego podniesieniem podanej liczby dodatniej do określonej potęgi.</td>
<td><strong>POWER (10, 2)</strong> zwraca <strong>100</strong>.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (ciąg, separator dziesiętny, separator grupowania cyfr)</td>
<td>Konwertowanie określonego ciągu na liczbę. Podany symbol jest używany do oddzielania części całkowitych od ułamkowych w liczbie dziesiętnej. Jest również używany określony separator tysięcy.</td>
<td><strong>NUMBERVALUE(&quot;1 234,56&quot;, &quot;,&quot;, &quot; &quot;)</strong> zwraca wartość <strong>1234.56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (ciąg)</td>
<td>Konwertowanie określonego ciągu na liczbę. Przecinki i kropki (.) są traktowane jako separatory dziesiętne, a wiodący łącznik (-) jako znak minusa. W przypadku wystąpienia innych nieliczbowych znaków w określonym ciągu jest zgłaszany wyjątek.</td>
<td><strong>VALUE (&quot;1 234,56&quot;)</strong> generuje wyjątek.</td>
</tr>
<tr class="odd">
<td>ROUND (liczba, miejsca dziesiętne)</td>
<td>Zwracanie podanej liczby, która jest zaokrąglana do określonej liczby miejsc po przecinku:
<ul>
<li>Jeśli podana wartość miejsc dziesiętnych jest większa niż 0 (zero), liczba jest zaokrąglana do określonej liczby miejsc po przecinku.</li>
<li>Jeśli wartość miejsc dziesiętnych wynosi 0 (zero), liczba jest zaokrąglana do najbliższej liczby całkowitej.</li>
<li>Jeśli wartość miejsc dziesiętnych jest mniejsza niż 0 (zero), liczba jest zaokrąglana do liczby na lewo od separatora dziesiętnego.</li>
</ul></td>
<td><strong>ROUND (1200.767, 2)</strong> zaokrągla do dwóch miejsc po przecinku i zwraca <strong>1200.77</strong>. <strong>ROUND (1200.767, -3)</strong> zaokrągla do najbliższej wielokrotności 1000 i zwraca <strong>1000</strong>.</td>
</tr>
<tr class="even">
<td>ROUNDDOWN (liczba, miejsca dziesiętne)</td>
<td>Zwracanie podanej liczby, która jest zaokrąglana do dołu (w kierunku zera) do określonej liczby miejsc po przecinku. <strong>Uwaga:</strong> Ta funkcja zachowuje się jak funkcja <strong>ROUND</strong>, ale zawsze zaokrągla podaną liczbę do dołu.</td>
<td><strong>ROUNDDOWN (1200.767, 2)</strong> zaokrągla w dół do dwóch miejsc po przecinku i zwraca <strong>1200.76</strong>. <strong>ROUNDDOWN (1700.767, -3)</strong> zaokrągla w dół do najbliższej wielokrotności 1000 i zwraca <strong>1000</strong>.</td>
</tr>
<tr class="odd">
<td>ROUNDUP (liczba, miejsca dziesiętne)</td>
<td>Zwracanie podanej liczby, która jest zaokrąglana do góry (w kierunku od zera do nieskończoności) do określonej liczby miejsc po przecinku. <strong>Uwaga:</strong> Ta funkcja zachowuje się jak funkcja <strong>ROUND</strong>, ale zawsze zaokrągla podaną liczbę do góry.</td>
<td><strong>ROUNDUP (1200.763, 2)</strong> zaokrągla w górę do dwóch miejsc po przecinku i zwraca <strong>1200.77</strong>. <strong>ROUNDUP (1200.767, -3)</strong> zaokrągla w górę do najbliższej wielokrotności 1000 i zwraca <strong>2000</strong>.</td>
</tr>
</tbody>
</table>

### <a name="record-functions"></a>Funkcje zapisu

| Funkcja             | Opis                                                                                                                                                                                                                                     | Przykład                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (lista) | Zwracanie rekordu **null**, który ma taką samą strukturę, jak podana lista rekordów lub rekord. **Uwaga:** Ta funkcja jest przestarzała. Zamiast niej należy używać funkcji **EMPTYRECORD**.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** zwraca nowy pusty rekord, który ma taką samą strukturę, jak lista zwracana przez funkcję **SPLIT**. |
| EMPTYRECORD (rekord) | Zwracanie rekordu **null**, który ma taką samą strukturę, jak podana lista rekordów lub rekord. **Uwaga:** Rekord **null** jest rekordem, w którym wszystkie pola mają wartość pustą (**0** \[zero\] w przypadku liczb, pusty ciąg w przypadku ciągów tekstowych itp.). | **EMPTYRECORD (SPLIT ("abc", 1))** zwraca nowy pusty rekord, który ma taką samą strukturę, jak lista zwracana przez funkcję **SPLIT**.   |

### <a name="text-functions"></a>Funkcje tekstowe

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funkcja</th>
<th>Opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (ciąg)</td>
<td>Zwracanie określonego ciągu, który jest konwertowany na wielkie litery.</td>
<td><strong>UPPER(&quot;Przykład&quot;)</strong> zwraca <strong>&quot;PRZYKŁAD&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (ciąg)</td>
<td>Zwracanie określonego ciągu, który jest konwertowany na małe litery.</td>
<td><strong>LOWER (&quot;Przykład&quot;)</strong> zwraca <strong>&quot;przykład&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (ciąg, liczba znaków)</td>
<td>Zwracanie określonej liczby znaków od początku wskazanego ciągu tekstowego.</td>
<td><strong>LEFT (&quot;Przykład&quot;, 3)</strong> zwraca <strong>&quot;Prz&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (ciąg, liczba znaków)</td>
<td>Zwracanie określonej liczby znaków od końca wskazanego ciągu tekstowego.</td>
<td><strong>RIGHT (&quot;Przykład&quot;, 3)</strong> zwraca <strong>&quot;ład&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (ciąg, pozycja początkowa, liczba znaków)</td>
<td>Zwracanie określonej liczby znaków z podanego ciągu, począwszy od wskazanej pozycji.</td>
<td><strong>MID (&quot;Przykład&quot;, 2, 3)</strong> zwraca <strong>&quot;rzy&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (ciąg)</td>
<td>Zwracanie liczby znaków istniejących w podanym ciągu tekstowym.</td>
<td><strong>LEN (&quot;Przykład&quot;)</strong> zwraca <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (liczba)</td>
<td>Zwracanie ciągu znaków, do którego odwołuje się określona liczba Unicode.</td>
<td><strong>CHAR (255)</strong> zwraca <strong>&quot;ÿ&quot;</strong>. <strong>Uwaga:</strong> Zwrócony ciąg zależy od kodowania wybranego w nadrzędnym elemencie formatu PLIK. Lista obsługiwanych kodowań znajduje się w temacie <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Klasa Encoding</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (ciąg 1 [, ciąg 2, …])</td>
<td>Zwracanie wszystkich podanych ciągów tekstowych, które są połączone w jeden ciąg.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> zwraca <strong>&quot;abcdef&quot;</strong>. <strong>Uwaga:</strong> Wyrażenie <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> również zwraca wartość <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TRANSLATE (ciąg, wzorzec, ciąg zastępczy)</td>
<td>Zwracanie określonego ciągu, w którym wszystkie wystąpienia znaków w określonym ciągu wzorcowym są zastąpione na odpowiednich pozycjach znakami z określonego ciągu zastępczego.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> zastępuje wzorzec <strong>&quot;cd&quot;</strong> ciągiem <strong>&quot;GH&quot;</strong> i zwraca <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (ciąg, wzorzec, ciąg zastępczy, flaga wyrażenia regularnego)</td>
<td>Gdy ustawioną flagą wyrażenia regularnego jest <strong>true</strong>, funkcja zwraca podany ciągu znaków, który jest zmodyfikowany przez zastosowanie wyrażenia regularnego określonego jako argument wzorca tej funkcji. To wyrażenie służy do znalezienia znaków, które należy zastąpić. Znaki podanego argumentu zastępczego zastępują znalezione znaki. Gdy ustawioną flagą wyrażenia regularnego jest <strong>false</strong>, funkcja zachowuje się jak funkcja <strong>TRANSLATE</strong>.</td>
<td>  <strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> stosuje wyrażenie regularne, które usuwa wszystkie symbole nieliczbowe i zwraca <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> zastępuje wzorzec <strong>&quot;cd&quot;</strong> ciągiem <strong>&quot;GH&quot;</strong> i zwraca <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (dane wejściowe)</td>
<td>Zwracanie określonych danych wejściowych przekształconych na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia programu Dynamics 365 for Operations. Dla wartości typu <strong>faktyczny</strong> konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</td>
<td>Jeśli ustawienia regionalne serwera wystąpienia programu Dynamics 365 for Operations są określone jako <strong>EN-US</strong>, funkcja <strong>TEXT (NOW ())</strong> zwraca datę bieżącej sesji programu Dynamics 365 for Operations, 17.12.2015, jako ciąg tekstowy <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> zwraca <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (ciąg 1, ciąg 2[, ciąg 3, ...])</td>
<td>Zwracanie określonego ciągu sformatowanego poprzez zastąpienie wszystkich wystąpień elementu <strong>%N</strong> argumentem o numerze <em>n</em>. Argumenty są ciągami tekstowymi. Jeśli dla parametru nie podano argumentu, parametr jest zwracany w ciągu jako <strong>&quot;%N&quot;</strong>. Dla wartości typu <strong>faktyczny</strong> konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</td>
<td>W tym przykładzie źródło danych <strong>PaymentModel</strong> zwraca listę rekordów odbiorców przy użyciu składnika <strong>Customer</strong> oraz wartość daty przetwarzania przy użyciu pola <strong>ProcessingDate</strong>. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a> W formacie raportowania elektronicznego przeznaczonym do generowania pliku elektronicznego dla wybranych odbiorców <strong>PaymentModel</strong> jest wybrane jako źródło danych i kontroluje przebieg procesu. Wyjątek jest zgłaszany w przypadku użytkowników końcowych, gdy wybrany odbiorca jest zablokowany w dniu generowania raportu. Formuła przeznaczona dla tego typu kontroli przetwarzania może skorzystać z poniższych zasobów:
<ul>
<li>Etykieta SYS70894 programu Dynamics 365 for Operations, która ma następujący tekst:
<ul>
<li><strong>W języku polskim:</strong> &quot;Nie ma nic do wydrukowania&quot;</li>
<li><strong>W języku niemieckim:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Etykieta SYS18389 programu Dynamics 365 for Operations, która ma następujący tekst:
<ul>
<li><strong>W języku polskim:</strong> &quot;Odbiorca %1 jest zablokowany do %2.&quot;</li>
<li><strong>W języku niemieckim:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
Poniżej przedstawiono formułę, którą można zaprojektować: FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;)) Jeśli raport jest przetwarzany dla <strong>odbiorcy Litware Retail</strong> w dniu 17 grudnia 2015 r. w kulturze <strong>polskiej</strong> i języku <strong>polskim</strong>, formuła zwraca następujący tekst, który może być prezentowany jako komunikat o wyjątku dla użytkownika końcowego: &quot;Nie ma nic do wydrukowania. Odbiorca Litware Retail jest zablokowany do 17.12.2015.&quot; Jeśli ten sam raport będzie przetwarzany dla <strong>odbiorcy Litware Retail</strong> w dniu 17 grudnia 2015 w języku <strong>niemieckim</strong> i kulturze <strong>niemieckiej</strong>, formuła zwraca następujący tekst: &quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot; <strong>Uwaga:</strong> W formułach raportowania elektronicznego dla etykiet jest stosowana następująca składnia:
<ul>
<li><strong>Etykiety zasobów programu Dynamics 365 for Operations:</strong> <strong>@&quot;X&quot;</strong>, gdzie X oznacza identyfikator etykiety w drzewie obiektów aplikacji (AOT)</li>
<li><strong>Etykiety, które znajdują się w konfiguracjach ER:</strong> <strong>@&quot;ER_LABEL:X&quot;</strong>, gdzie X oznacza identyfikator etykiety w konfiguracji raportowania elektronicznego</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (liczba, format)</td>
<td>Zwracanie określonej liczby w określonym formacie w postaci ciągu tekstowego. (Aby uzyskać informacje na temat obsługiwanych formatów, zobacz <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standardowe</a> i <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">niestandardowe</a>). Kontekst, w którym ta funkcja jest uruchamiana, decyduje o kulturze używanej do formatowania liczb.</td>
<td>W kulturze EN-US <strong>NUMBERFORMAT (0,45, &quot;p&quot;)</strong> zwraca <strong>&quot;% 45,00&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> zwraca <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (liczba, język, waluta, flaga nazwy waluty wydruku, miejsca dziesiętne)</td>
<td>Zwraca liczbę w zapisie fonetycznym (przekonwertowaną) do ciągów tekstowych w zdefiniowanym języku. Kod języka jest opcjonalny. Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używany aktualnie uruchomiony kod języka kontekstu (zdefiniowany dla generowanego pliku lub folderu). Kod waluty jest opcjonalny. Gdy jest zdefiniowany jako pusty ciąg znaków, jest pobierana waluta firmy. Uwaga: Parametry <strong>Nazwa waluty wydruku</strong> i <strong>Miejsca dziesiętne</strong> są analizowane tylko następujące kodów języków: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong> i <strong>RU</strong>. Uwaga: Parametr <strong>Nazwa waluty wydruku</strong> w programie Dynamics 365 for Operations jest analizowany tylko dla firm z kontekstem kraju obsługującym deklinację walut.</td>
<td>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2) zwraca „One Thousand Two Hundred Thirty Four and 56” NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0) zwraca „Sto dwadzieścia” NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2) zwraca „Сто двадцать евро 21 евроцент”</td>
</tr>
<tr class="odd">
<td>PADLEFT (ciąg, długość, znaki dopełnienia)</td>
<td>Zwraca ciąg o określonej długości, w którym początek bieżącego ciągu jest dopełniany określonymi znakami.</td>
<td>PADLEFT ("1234", 10, " ") zwraca ciąg tekstowy „      1234”</td>
</tr>
</tbody>
</table>

### <a name="data-collection-functions"></a>Funkcje gromadzenia danych

Funkcja

opis

Przykład

FORMATELEMENTNAME ()

Zwraca nazwę elementu bieżącego formatu. Zwraca pusty ciąg, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona.

Aby dowiedzieć się więcej o korzystaniu z tych funkcji, zobacz przewodnik po zadaniu **ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania** (część procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**).

SUMIFS (ciąg klucza dla sumowania, ciąg zakresu kryteriów 1, ciąg wartości kryteriów 1 \[, ciąg zakresu kryteriów 2, ciąg wartości kryteriów 2, …\])

Zwraca sumę wartości węzłów (z nazwami zdefiniowanymi jako kluczami) w kodzie XML, które zostały zebrane podczas wykonywania tego formatu i spełniają wprowadzone warunki (pary zakresu i wartości). Zwraca wartość zerową, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona.

SUMIF (ciąg klucza dla sumowania, ciąg zakresu kryteriów, ciąg wartości kryteriów)

Zwraca sumę wartości węzłów (z nazwami zdefiniowanymi jako kluczami) w kodzie XML, które zostały zebrane podczas wykonywania tego formatu i spełniają wprowadzony warunek (zakres i wartość). Zwraca wartość zerową, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona.

COUNTIFS (ciąg zakresu kryteriów 1, ciąg wartości kryteriów 1 \[, ciąg zakresu kryteriów 2, ciąg wartości kryteriów 2, …\])

Zwraca liczbę węzłów w kodzie XML, które zostały zebrane podczas wykonywania tego formatu i spełniają wprowadzone warunki (pary zakresu i wartości). Zwraca wartość zerową, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona.

COUNTIF (ciąg zakresu kryteriów, ciąg wartości kryteriów)

Zwraca liczbę węzłów w kodzie XML, które zostały zebrane podczas wykonywania tego formatu i spełniają wprowadzony warunek (zakres i wartość). Zwraca wartość zerową, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona.

COLLECTEDLIST (ciąg zakresu kryteriów 1, ciąg wartości kryteriów 1 \[, ciąg zakresu kryteriów 2, ciąg wartości kryteriów 2, …\])

Zwraca listę wartości węzłów w kodzie XML, które zostały zebrane podczas wykonywania tego formatu i spełniają wprowadzone warunki (zakres i wartość). Zwraca pustą listę, gdy flaga **Pobierz szczegóły rezultatu** dla bieżących plików jest wyłączona.

### <a name="other-business-domainspecific-functions"></a>Inne funkcje (specyficzne dla domeny biznesowej)

| Funkcja                                                                         | opis                                                                                                                                                                                                                                                        | Przykład                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (kwota, waluta źródłowa, waluta docelowa, data, firma)        | Konwertowanie określonej kwoty pieniężnej z waluty źródłowej na walutę docelową przy użyciu ustawień określonej firmy programu Dynamics 365 for Operations na określony dzień.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** zwraca równoważność jednego euro w dolarach amerykańskich w dniu bieżącej sesji na podstawie ustawień dla firmy DEMF.                                                                                                                                  |
| ROUNDAMOUNT (liczba, miejsca dziesiętne, reguła zaokrąglania)                                       | Zaokrąglanie określonej kwoty zgodnie z określoną regułą zaokrąglania i podaną liczbą miejsc dziesiętnych. **Uwaga:** Reguła zaokrąglania musi być podana jako wartość elementu stałotekstowego **RoundOffType** programu Dynamics 365 for Operations.                          | Jeśli w parametrze **model.RoundOff** ustawiono wartość ****W dół****, wyrażenie **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** zwraca wartość **1000.78**. Jeśli w parametrze **model.RoundOff** ustawiono wartość **Normalnie** lub **Zaokrąglenie w górę**, wyrażenie **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** zwraca wartość **1000.79**. |
| CURCredRef (cyfry)                                                              | Zwracanie odwołania do wierzyciela w oparciu o cyfry określonego numeru faktury.                                                                                                                                                                                  | **CURCredRef ("VEND-200002")** zwraca **"2200002"**.                                                                                                                                                                                                                                                         |
| MOD\_97 (cyfry)                                                                 | Zwracanie odwołania do wierzyciela jako wyrażenia MOD97 w oparciu o cyfry określonego numeru faktury.                                                                                                                                                            | **MOD\_97 ("VEND-200002")** zwraca **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (cyfry)                                                              | Zwracanie odwołania do wierzyciela w formacie ISO w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury. **Uwaga:** Aby wyeliminować symbole z alfabetów niezgodnych z systemem ISO, parametr wejściowy musi zostać przetłumaczony przed przekazaniem go do tej funkcji. | **ISOCredRef ("VEND-200002")** zwraca **"RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (ciąg, liczba)                                  | Pobieranie identyfikatora dodatkowego wymiaru finansowego. Wymiary są przedstawiane w tym ciągu jako identyfikatory rozdzielone przecinkami. Liczby określają kod numeracji żądanego wymiaru w tym ciągu.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3) zwraca „CC”                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Zwraca kod firmy, której użytkownik jest obecnie zalogowany.                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                               |
| CH\_BANK\_MOD\_10 (cyfry)                                                       | Zwraca odwołanie do wierzyciela jako wyrażenia MOD10 w oparciu o cyfry podanego numeru faktury.                                                                                                                                                                      | CH\_BANK\_MOD\_10 ("VEND-200002") zwraca 3                                                                                                                                                                                                                                                                   |
| FA\_SUM (kod środka trwałego, kod modelu ewidencji, data początkowa, data końcowa)               | Zwraca przygotowany kontener danych dla kwot środków trwałych w okresie.                                                                                                                                                                                         | FA\_SUM ("COMP-000001", "Bieżący", Data1, Data2) zwraca przygotowany kontener danych środka trwałego „COMP-000001” z modelem ewidencji „Bieżący” za okres od Data1 do Data 2.                                                                                                                        |
| FA\_BALANCE (kod środka trwałego, kod modelu ewidencji, rok sprawozdawczy, data raportowania) | Zwraca przygotowany kontener danych dla sald środków trwałych. Rok sprawozdawczy musi być podany jako wartość stałotekstowa **AssetYear** programu Dynamics 365 for Operations.                                                                                           | FA\_SUM ("COMP-000001", "Bieżący", AxEnumAssetYear.ThisYear, SESSIONTODAY ()) zwraca przygotowany kontener sald dla środka trwałego „COMP-000001” z modelem ewidencji „Bieżący” na dzień bieżącej sesji programu Dynamics 365 for Operations.                                                                |

### <a name="functions-list-extension"></a>Rozszerzenie listy funkcji

Model raportowania elektronicznego umożliwia rozszerzanie listy funkcji używanych w wyrażeniach ER. Wymaga to działań programistycznych. Aby uzyskać szczegółowe informacje, zobacz [Rozszerzanie listy funkcji raportowania elektronicznego](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Informacje dodatkowe
--------

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Poszerzanie listy funkcji raportowania elektronicznego (ER)](general-electronic-reporting-formulas-list-extension.md)




