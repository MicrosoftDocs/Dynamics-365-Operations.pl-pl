---
title: Język formuł raportowania elektronicznego
description: Ten temat zawiera ogólne informacje o używaniu języka formuł w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/18/2019
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
ms.openlocfilehash: bdd8b9c120fc4a860717a66b9dfa66e6b0daed93
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042718"
---
# <a name="electronic-reporting-formula-language"></a>Język formuł raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Raportowanie elektroniczne (ER) oferuje zaawansowane środowisko przekształcania danych. Język, który jest używany do wyrażania wymaganych modyfikacji danych w projektancie formuły ER, przypomina język formuł w programie Microsoft Excel.

## <a name="basic-syntax"></a>Podstawowa składnia

Wyrażenia raportowania elektronicznego mogą zawierać dowolne lub wszystkie z następujących elementów:

- [Stałe](#Constants)
- [Operatorzy](#Operators)
- [Odwołania](#References)
- [Ścieżki](#Paths)
- [Funkcje](#Functions)

## <a name="Constants">Stałe</a>

Do projektowania wyrażeń można używać stałych tekstowych i liczbowych (tzn. wartości, które nie są obliczane). Na przykład w wyrażeniu `VALUE ("100") + 20` są używane stała liczbowa **20** i stała ciągu **100**, a wyrażenie zwraca wartość liczbową **120**.

Projektanta formuł ER obsługuje sekwencje specjalne. Oznacza to, że można określić ciąg wyrażenia, który powinien być traktowany inaczej. Na przykład wyrażenie `"Leo Tolstoy ""War and Peace"" Volume 1"` zwraca ciąg tekstowy **Leo Tolstoy "War and Peace" Volume 1**.

## <a name="Operators">Operatory</a>

W poniższej tabeli przedstawiono operatory arytmetyczne, których można używać do wykonania podstawowych operacji matematycznych, takich jak dodawanie, odejmowanie, mnożenie i dzielenie.

| Operator | Znaczenie               | Przykład     |
|----------|-----------------------|-------------|
| +        | Dodanie              | `1+2`       |
| -        | Odejmowanie, zaprzeczenie | `5-2`, `-1` |
| \*       | Mnożenie        | `7\*8`      |
| /        | Oddział              | `9/3`       |

W poniższej tabeli przedstawiono obsługiwane operatory porównania. Tych operatorów można używać do porównywania dwóch wartości.

| Operator | Znaczenie                  | Przykład      |
|----------|--------------------------|--------------|
| =        | Równy                    | `X=Y`        |
| &gt;     | Większe niż             | `X>Y`        |
| &lt;     | Mniejsze niż                | `X<Y`        |
| &gt;=    | Większe lub równe | `X>=Y`       |
| &lt;=    | Mniejsze lub równe    | `X<=Y`       |
| &lt;&gt; | Nie równa się             | `X<>Y`       |

Ponadto można użyć znaku handlowego „i” (&) jako operatora łączenia tekstu. W ten sposób można połączyć (złożyć) jeden lub kilka ciągów tekstowych w jeden element tekstu.

| Operator | Znaczenie     | Przykład                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Złącz | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Pierwszeństwo operatorów

Kolejność, w jakiej części wyrażenia złożonego są obliczane, jest ważna. Na przykład wynik wyrażenia `1 + 4 / 2` różni się w zależności od tego, czy jako pierwsza jest wykonywana operacja dodawania, czy dzielenia. Nawiasy umożliwiają jawne zdefiniowanie sposobu wyznaczania wartości wyrażenia. Na przykład aby wskazać, że najpierw powinna być wykonywana operacja dodawania, można zmienić poprzednie wyrażenie na `(1 + 4) / 2`. Jeśli nie zdefiniujesz jawnie kolejności operacji w wyrażeniu, kolejność jest zależna od domyślnego pierwszeństwa przypisanego do obsługiwanych operatorów. Poniższa tabela ilustruje pierwszeństwo przypisane do każdego operatora. Operatory o wyższym priorytecie (na przykład 7) są odczytywane przed operatorami, które mają niższy priorytet (na przykład 1).

| Pierwszeństwo | Operatorzy      | Składnia                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Grupowanie       | ( … )                                                                   |
| 6          | Dostęp do elementu członkowskiego  | … , …                                                                   |
| 5          | Wywołanie funkcji  | … ( … )                                                                 |
| 4          | Zwielokrotnianie | … \* …<br>… / …                                                         |
| 3          | Addytywny       | … + …<br>… - …                                                          |
| 2          | Porównanie     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Rozdzielanie     | … , …                                                                   |

Jeśli wyrażenie zawiera wiele następujących po sobie operatorów, które mają ten sam priorytet (pierwszeństwo), operacje te są wykonywane od lewej do prawej. Na przykład wyrażenie `1 + 6 / 2 \* 3 > 5` zwraca wartość **prawda**. Zaleca się używanie nawiasów w celu jawnego wskazania żądanej kolejności operacji w wyrażeniach, aby ułatwić odczyt wyrażenia i zarządzanie nim.

## <a name="References">Odwołania</a>

Wszystkie źródła danych bieżącego składnika ER, które są dostępne podczas projektowania wyrażenia, mogą być używane jako odwołania nazwane. Bieżącym składnikiem modułu ER może być mapowanie modelu lub format. Na przykład bieżące mapowanie modelu danych ER zawiera źródło danych **ReportingDate**, które zwraca wartość o typie danych *DateTime*. Aby ta wartość była poprawnie sformatowana w generowanym dokumencie, można utworzyć odwołanie z wyrażenia do źródła danych w postaci `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Wszystkie znaki w nazwie przywoływanego źródła danych, które nie reprezentują litery alfabetu, muszą być poprzedzone pojedynczym cudzysłowem ('). Jeśli nazwa przywoływanego źródła danych zawiera co najmniej jeden symbol, który nie reprezentuje litery alfabetu, musi zostać ujęta w pojedyncze cudzysłowy. Symbolami nienależącymi do alfabetu mogą być na przykład znaki interpunkcyjne lub symbole piśmiennicze. Oto kilka przykładów:

- Źródło danych **Dzisiejsza data i godzina** musi mieć w wyrażeniu ER odwołanie `'Today''s date & time'`.
- Metoda **name()** ze źródła danych **Customers** musi mieć w wyrażeniu ER odwołanie `Customers.'name()'`.

Jeśli metody źródeł danych aplikacji mają parametry, następująca składnia jest wykorzystywana do wywoływania tych metod:

- Jeśli metoda **isLanguageRTL** źródła danych **System** zawiera parametr **EN-US** o typie danych *Ciąg*, musi być przywoływana w wyrażeniu ER jako `System.isLanguageRTL("EN-US")`.
- Cudzysłowy nie są wymagane, jeśli nazwa metody zawiera tylko symbole alfanumeryczne. Są jednak wymagane dla metody tabeli, gdy nazwa zawiera nawiasy.

Gdy źródło danych **System** zostanie dodane do mapowania raportowania elektronicznego, które odwołuje się do klasy **Global** aplikacji, wyrażenie `System.isLanguageRTL("EN-US ")` zwraca wartość *logiczną* **FALSE**. Zmodyfikowanie wyrażenie `System.isLanguageRTL("AR")` zwraca wartość *logiczną* **TRUE**.

Można ograniczyć sposób, w jaki wartości są przekazywane do parametrów tego typu metody:

- Tylko stałe mogą być przekazywane do tego typu metod. Wartości stałych są definiowane w czasie projektowania.
- W parametrach tego typu są obsługiwane tylko pierwotne (podstawowe) typy danych. Pierwotne typy danych to *liczby całkowite*, *liczby rzeczywiste*, *wartości logiczne* i *ciągi*.

## <a name="Paths">Ścieżki</a>

Jeśli wyrażenie odwołuje się do źródła danych usystematyzowanych, można użyć definicji ścieżki, aby wybrać określony element podstawowy tego źródła danych. Znak kropki (.) jest używany do oddzielania poszczególnych elementów źródła danych usystematyzowanych. Na przykład bieżące mapowanie modelu danych ER zawiera źródło danych **InvoiceTransactions**, które zwraca listę rekordów. Struktura rekordu **InvoiceTransactions** zawiera pola **AmountDebit** i **AmountCredit**, które zwracają wartości liczbowe. W związku z tym można zaprojektować następujące wyrażenie, aby obliczyć zafakturowaną kwotę: `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. Konstrukcja `InvoiceTransactions.AmountDebit` w tym wyrażeniu jest ścieżką, która jest używana do uzyskiwania dostępu do pola **AmountDebit** źródła danych **InvoiceTransactions** typu *Lista rekordów*.

### <a name="relative-path"></a>Ścieżka względna

Jeśli ścieżka źródła danych strukturalnych zaczyna się od znaku „at” (@), jest ścieżką względną. Zamiast pozostałej części ścieżki bezwzględnej struktury używanego drzewa hierarchicznego jest wyświetlany znak „at”. Na poniższej ilustracji pokazano przykład. W tym miejscu ścieżka bezwzględna `Ledger.'accountingCurrency()'` wskazuje, że wartość waluty rozliczeniowej ze źródła danych **Księga** jest wprowadzana w polu **AccountingCurrency** modelu danych.

![Przykładowa ścieżka bezwzględna na stronie projektanta mapowania modelu ER](./media/ER-FormulaLanguage-AbsolutePath.png)

W przykładzie na poniższej ilustracji pokazano, jak jest używana ścieżka względna. Ścieżka względna `@.AccountNum` wskazuje, że pole **AccountNum** źródła danych **Intrastat** (które pojawia się jeden poziom powyżej pola **AccountNum** w drzewie hierarchicznym modelu danych) służy do wprowadzania numeru konta odbiorcy lub klienta w polu **AccountNum** modelu danych.

![Przykładowa ścieżka względna na stronie projektanta mapowania modelu ER](./media/ER-FormulaLanguage-RelativePath1.png)

Pozostała część ścieżki bezwzględnej jest również wyświetlana w [edytorze formuł modułu ER](general-electronic-reporting-formula-designer.md).

![Pozostała część ścieżki bezwzględnej na stronie projektanta formuł ER](./media/ER-FormulaLanguage-RelativePath2.png)

## <a name="Functions">Funkcje</a>

Wbudowane funkcje modułu ER mogą być używane w wyrażeniach ER. Wszystkie źródła danych kontekstu wyrażenia (czyli bieżące mapowanie modelu ER lub format ER) mogą służyć jako parametry funkcji wywołujących, zgodnie z listą argumentów funkcji wywołujących. Parametrami funkcji wywołujących mogą być również stałe. Na przykład bieżące mapowanie modelu danych ER zawiera źródło danych **InvoiceTransactions**, które zwraca listę rekordów. Struktura rekordu **InvoiceTransactions** zawiera pola **AmountDebit** i **AmountCredit**, które zwracają wartości liczbowe. W efekcie w celu obliczania zafakturowanej kwoty można zaprojektować następujące wyrażenie używające wbudowanej funkcji zaokrąglania ER: `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`

Podczas projektowania mapowań modelu ER i raportów ER można używać funkcji ER z następujących kategorii:

- [Funkcje daty i godziny](er-functions-category-datetime.md)
- [Lista funkcji](er-functions-category-list.md)
- [Funkcje logiczne](er-functions-category-logical.md)
- [Funkcje matematyczne](er-functions-category-mathematical.md)
- [Funkcje zapisu](er-functions-category-record.md)
- [Funkcje tekstowe](er-functions-category-text.md)
- [Funkcje gromadzenia danych](er-functions-category-data-collection.md)
- [Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)
- [Funkcje konwersji typu](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>Rozszerzenie listy funkcji

Model raportowania elektronicznego umożliwia rozszerzanie listy funkcji używanych w wyrażeniach ER. Wymaga to działań programistycznych. Aby uzyskać szczegółowe informacje, zobacz [Rozszerzanie listy funkcji raportowania elektronicznego (ER)](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Wyrażenia złożone

Można utworzyć wyrażenia złożone, które używają funkcji z różnych kategorii, pod warunkiem, że typy danych są zgodne. Gdy używasz funkcji razem, dopasuj typ danych wyjściowych z jednej funkcji do typu danych wejściowych, który jest wymagany przez inną funkcję. Aby na przykład uniknąć ewentualnego błędu „list-is-empty” w powiązaniu pola z elementem formatu ER, połącz funkcje z kategorii [Lista](er-functions-category-list.md) z funkcją z kategorii [Logiczne](er-functions-category-logical.md), jak pokazano w poniższym przykładzie. W tym miejscu formuła używa funkcji [IF](er-functions-logical-if.md) do sprawdzenia, czy lista **IntrastatTotals** jest pusta, zanim zwróci wartość wymaganej agregacji z tej listy. Jeśli lista **IntrastatTotals** jest pusta, formuła zwraca wartość **0** (zero).

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Wiele rozwiązań

Często można uzyskać ten sam wynik przekształcenia danych na wiele sposobów, za pomocą funkcji z różnych kategorii lub różnych funkcji z tej samej kategorii. Na przykład poprzednie wyrażenie można również skonfigurować za pomocą funkcji [COUNT](er-functions-list-count.md) z kategorii [Lista](er-functions-category-list.md).

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Rozszerzanie listy funkcji Raportowania elektronicznego](general-electronic-reporting-formulas-list-extension.md)
