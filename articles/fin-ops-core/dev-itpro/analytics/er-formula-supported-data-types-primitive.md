---
title: Obsługiwane typy danych pierwotnych dla formuł raportowania elektronicznego
description: Ten artykuł zawiera ogólne informacje o funkcjach danych pierwotnych obsługiwanych w formułach Raportowania elektronicznego (ER).
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41cda188e774630e96c46fba1200fd2e640f9915
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891883"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Obsługiwane typy danych pierwotnych dla formuł raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera ogólne informacje o funkcjach danych pierwotnych obsługiwanych w wyrażeniach [Raportowania elektronicznego (ER)](general-electronic-reporting.md). Oto lista pierwotnych typów danych:

- [wartość logiczna](#boolean)
- [data](#date)
- [data/godzina](#datetime)
- [tekst stały](#enumeration)
- [guid](#guid)
- [liczba całkowita](#integer)
- [int64](#int64)
- [rzeczywisty](#real)
- [ciąg](#string)

## <a name="boolean"></a><a name="boolean"></a>Wartość logiczna

Pierwotny typ danych *logiczny* zawiera wartość, która jest oceniana jako *true* lub *false*. Możesz używać zarezerwowanych literalnych słów kluczowych **True** i **False** wszędzie tam, gdzie oczekiwane jest wyrażenie *logiczne*. Domyślna wartość to *false*.

Wewnętrzna reprezentacja *wartości logicznej* to *liczba całkowita*. *Liczba całkowita* 0 (zero) jest oceniana jako *false*, a wszystkie inne *liczby całkowite* są oceniane jako *true*. Podczas [sprawdzania poprawności](general-electronic-reporting-formula-designer.md#TestFormula) skonfigurowanego wyrażenia, które zwraca *wartość logiczną* w [projektancie formuł ER](er-advanced-formula-editor.md), okienko wyników testu przedstawia wartość *0* (zero), gdy wyrażenie zwraca wartość *false*. W przeciwnym razie okienko wyników testu przedstawia *1*.

*Wartość logiczna* nie ma konwersji niejawnych. Można jednak użyć funkcji [TEXT](er-functions-text-text.md), aby jawnie konwertować *wartość logiczną* na *ciąg*:

- Wartość *false* jest konwertowana na ciąg tekstowy **False**.
- Wartość *true* jest konwertowana na ciąg tekstowy **True**.

> [!NOTE]
> Ta konwersja nie zależy od podanego [kontekstu](er-design-multilingual-reports.md) języka i kultury.

[Operatory](er-formula-language.md#Operators) porównania są jedynym typem operatora, który może być używany z typem danych *wartości logicznych*. Następujące operatory mogą być używane do porównywania dwóch *wartości logicznych*: \<\> i =.

## <a name="date"></a><a name="date"></a>Data

Typ danych pierwotnych *data* przechowuje dzień, miesiąc i rok. Daty można inicjować za pomocą następujących funkcji:

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

Typ danych *daty* może zawierać daty między 1 stycznia 1900 r. a 31 grudnia 2154 r. Wartość domyślna to **null**, a reprezentacja wewnętrzna to data 1 stycznia 1900.

*Data* nie ma konwersji niejawnych. Można jednak użyć następujących funkcji konwersji jawnych:

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

Funkcja [ADDDAYS](er-functions-datetime-adddays.md) umożliwia dodawanie i odejmowanie dni od dat. W ten sposób można przenieść datę określoną liczbę dni w przyszłość i przeszłość. Funkcja [DAYS](er-functions-datetime-days.md) umożliwia odejmowanie dat od siebie i obliczanie różnicy w dniach. Aby uzyskać więcej informacji na temat przekształcania wartości *daty*, zobacz [Lista funkcji ER w kategorii Data i godzina](er-functions-category-datetime.md).

[Operatory](er-formula-language.md#Operators) porównania są jedynym typem operatora, który może być używany z typem danych *data*. Następujące operatory mogą być używane do porównywania dwóch wartości *daty*:\<\>, \<, \<=, =, \> i \>=.

## <a name="datetime"></a><a name="datetime"></a>Data/godzina

Pierwotny typ danych *daty/godziny* łączy typ *daty* i wartość, która reprezentuje czas, który minął od północy. Czas jest wyrażony w godzinach, minutach, sekundach i ułamkach sekundy. W wartości *daty i godziny* są także podane informacje o strefie czasowej.

Typ danych *daty i godziny* może zawierać daty między 1 stycznia, 1900 (1900-01-01T00:00:00.0000000+00:00 w [formacie](/dotnet/standard/base-types/standard-date-and-time-format-strings) przejścia w obie strony) a 31 grudnia 2154 (2154/12/31T11:59:59.9999999+00:00 w formacie przejścia w obie strony). Najmniejsza jednostka czasu w *dacie i godzinie* to dziesięciomilionowa część sekundy.

> [!NOTE]
> Gdy [modyfikator](/dotnet/standard/base-types/standard-date-and-time-format-strings) **hh** jest używany dla godzin, wartości czasu powyżej 12:59:59:9999999 nie mogą być interpretowane jako czasy prawidłowe.
>
> Gdy modyfikator **HH** jest używany dla godzin, wartości czasu powyżej 23:59:59:9999999 nie mogą być interpretowane jako czasy prawidłowe.

Wartość domyślna to **null**, a reprezentacja wewnętrzna to data 1 stycznia, 1900 (1900-01-01T00:00:00.0000000+00:00 w formacie przejścia w obie strony).

Datę i czas można inicjować za pomocą następujących funkcji:

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

*Data i czas* nie ma konwersji niejawnych. Można jednak użyć następujących funkcji konwersji jawnych:

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

Aby uzyskać więcej informacji na temat przekształcania wartości *daty i czasu*, zobacz [Lista funkcji ER w kategorii Data i godzina](er-functions-category-datetime.md).

[Operatory](er-formula-language.md#Operators) porównania są jedynym typem operatora, który może być używany z typem danych *data i czas*. Następujące operatory mogą być używane do porównywania dwóch wartości *daty i czasu*:\<\>, \<, \<=, =, \> i \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Tekst stały

Pierwotny typ danych *wyliczenia* jest listą literałów. Można używać wyliczeń zdefiniowanych w [kodzie źródłowym](../dev-ref/xpp-data-primitive.md#enum) aplikacji. Można również wprowadzić własne wyliczenia w modelu danych ER i składnikach formatu ER.

*Wyliczenie* aplikacji może być używane w wyrażeniach dowolnego mapowania modelu ER i formatu ER.

Na poniższej ilustracji pokazano, jak można dodać wyliczenie modelu **CustVendCorrectiveReasonCode** do edytowalnego modelu danych ER.

[![Konfiguracja wyliczenia modelu w projektancie modeli danych ER.](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

*Wyliczenie* modeli może być używane w wyrażeniach dowolnego mapowania modelu ER i formatu ER utworzonych w modelu danych, w którym zostało wprowadzone *wyliczenie*.

Poniższa ilustracja przedstawia sposób dodania do edytowalnego formatu ER wyliczenia formatu **Lista podkategorii obciążenia zwrotnego Natura**.

[![Konfiguracja wyliczenia formatu w projektancie formatu danych ER.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

*Wyliczenie* formatów może być używane tylko w wyrażeniach formatu ER, w którym wprowadzono *wyliczenie*.

Należy użyć odpowiedniego typu źródeł danych ER, aby wprowadzić konkretne wyliczenie do skonfigurowanego komponentu ER jako stałą lub wartość, którą użytkownik uruchamiający rozwiązanie ER zdefiniował w oknie dialogowym w momencie uruchomienia.

- Wyliczenia aplikacji są dostępne za pomocą źródeł danych **Dynamics 365 for Operations \ Wyliczenie** i **Ogólne \ Parametry wejściowe użytkownika**. Na poniższej ilustracji pokazano, jak można dodać edytowalny format aplikacji ER do źródeł danych **appenumNoYes** i **uipNoYes**, które odwołują się do wyliczenia aplikacji **NoYes**.

    [![Dodawanie źródeł danych wyliczenia aplikacji w konstruktorze formatu ER.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- Wyliczenia modelu danych są dostępne za pomocą źródeł danych **Model danych \ Wyliczenie** i **Model danych \ Parametry wejściowe użytkownika wyliczenia**. Na poniższej ilustracji pokazano, jak można dodać edytowalny format aplikacji ER do źródła danych **CustVendCorrectiveReasonCode**, które odwołuje się do modelu danych **CustVendCorrectiveReasonCode**.

    [![Dodawanie źródeł danych wyliczenia modelu w konstruktorze formatu ER.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- Wyliczenia formatu są dostępne za pomocą źródeł danych **Format \ Wyliczenie** i **Format \ Parametry wejściowe użytkownika wyliczenia**. Na poniższej ilustracji pokazano, jak można dodać edytowalny format aplikacji ER do źródła danych **NaturaReverseCharge**, które odwołuje się do modelu danych **Podkategorie odwrotnego obciążenia Natura**.

    [![Dodawanie źródeł danych wyliczenia formatu w konstruktorze formatu ER.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

*Wyliczenie* nie ma konwersji niejawnych. Można jednak użyć funkcji konwersji [TEXT](er-functions-text-text.md), aby przekonwertować tekst *wyliczenia* na ciąg tekstowy. Ta konwersja nie jest zależna od języka. Aby się dowiedzieć, jak można skojarzyć wartość *wyliczenia* z odpowiednimi etykietami właściwymi dla języka, zobacz przykłady użycia funkcji [LISTOFFIELDS](er-functions-list-listoffields.md) i [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md).

[Operatory](er-formula-language.md#Operators) porównania są jedynym typem operatora, który może być używany z typem danych *wyliczenie*. Następujące operatory mogą być używane do porównywania dwóch *wyliczeń*: \<\> i =.

## <a name="guid"></a><a name="guid"></a>Identyfikator Guid

Pierwotny typ danych *guid* zawiera globalnie unikatową wartość identyfikatora (GUID). Identyfikator GUID to wartość, której można używać we wszystkich komputerach i sieciach, gdzie jest wymagany unikatowy identyfikator. Jest mało prawdopodobne, że numer ten zostanie powielony. Prawidłowy identyfikator GUID spełnia wszystkie następujące warunki:

- Muszą to być 32 cyfry szesnastowe.
- Dodatkowo muszą być cztery znaki myślnika, które są osadzone w następujących miejscach: 8-4-4-4-12.
- Ponadto opcjonalne nawiasy klamrowe — \{\} — można dodawać na początku i na końcu ciągu. Na przykład zarówno **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}**, jak i **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** są prawidłowymi ciągami GUID.
- W zależności od tego, czy dodano nawiasy klamrowe, musi zawierać łącznie 36 lub 38 znaków.
- Litery, które są używane jako cyfry szesnastkowe, mogą być wielkie (A-F), małe (a-f) lub mieszane.

Można zastosować następujące funkcje konwersji jawnej:

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

[Operatory](er-formula-language.md#Operators) porównania są jedynym typem operatora, który może być używany z typem danych *guid*. Następujące operatory mogą być używane do porównywania dwóch *guid*: \<\> i =.

## <a name="integer"></a><a name="integer"></a>Wartość całkowita

Pierwotny typ danych *liczb całkowitych* reprezentuje liczbę, która nie ma miejsc dziesiętnych. Liczby całkowite są używane jako zmienne kontrolne w powtarzanych instrukcjach lub jako indeksy na listach rekordów.

Literał *liczby całkowitej* jest liczbą całkowitą wprowadzaną bezpośrednio w [wyrażeniu](general-electronic-reporting-formula-designer.md#formula-designer-overview) ER (formule), na przykład **12345**. *Liczba całkowita* ma 32 bity szerokości. Wartość domyślna to **0**, a reprezentacja wewnętrzna to liczba długa. *Liczba całkowita* jest automatycznie konwertowana na *rzeczywistą*.

Można też zastosować następujące funkcje konwersji jawnej:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

Zakres *liczby całkowitej* to \[ -2,147,483,647 : 2,147,483,647\]. Wszystkie liczby całkowite z tego zakresu mogą być używane jako literały.

Wszystkie [operatory](er-formula-language.md#Operators) porównawcze i matematyczne mogą być używane z typem danych *liczb całkowitych*.

## <a name="int64"></a><a name="int64"></a>Int64

Pierwotny typ danych *int64* reprezentuje liczbę, która nie ma miejsc dziesiętnych. Wartości *Int64* są używane jako zmienne kontrolne w powtarzanych instrukcjach lub jako indeksy na listach rekordów.

*Int64* ma 64 bity szerokości. Wartość domyślna to **0**, a reprezentacja wewnętrzna to liczba długa. *Int64* jest automatycznie konwertowane na wartość *rzeczywistą*.

Można też zastosować następujące funkcje konwersji jawnej:

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

Zakres *int64* to \[ -9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\].

Wszystkie [operatory](er-formula-language.md#Operators) porównawcze i matematyczne mogą być używane z typem danych *int64*.

## <a name="real"></a><a name="real"></a>Rzeczywisty

*Rzeczywisty* pierwotny typ danych może zawierać wartości dziesiętne oprócz liczb całkowitych. Literałów dziesiętnych można używać w każdym oczekiwanym miejscu *rzeczywistym*. Literał dziesiętny jest separatorem dziesiętnym wprowadzonym bezpośrednio w kodzie, np. **2,19**.

> [!NOTE]
> W wyrażeniach ER jako separator dziesiętny jest zawsze używana kropka.

Wartości rzeczywiste mogą być używane we wszystkich wyrażeniach i mogą być używane zarówno z operatorami porównawczymi, jak i arytmetycznymi. *Wartość rzeczywista* ma precyzję 16 cyfr znaczących. Domyślna *wartość rzeczywista* to **0,0**, a reprezentacja wewnętrzna to numer cyfrowy (BCD) z kodem binarnym. Kodowanie BCD umożliwia dokładne odwzorowanie wartości, które są wielokrotnościami 0,1. Zakres zmiennej *rzeczywistej* wynosi od -(10)<sup>127</sup> do (10)<sup>127</sup>. Wszystkie wartości rzeczywiste z tego zakresu mogą być używane jako literały w wyrażeniach ER.

*Wartość rzeczywista* nie ma konwersji niejawnych. Można jednak użyć następujących funkcji, aby jawnie przekonwertować *wartość rzeczywistą* na inne typy danych i inne typy danych na *rzeczywistą*:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Wszystkie [operatory](er-formula-language.md#Operators) porównawcze i matematyczne mogą być używane z typem danych *wartość rzeczywista*.

## <a name="string"></a><a name="string"></a>Ciąg

Pierwotny typ danych *ciąg* reprezentuje sekwencję znaków używanych jako teksty, numery kont, adresy i numery telefonów.

Literały *ciągów* to znaki ujęte w cudzysłów („”). Literały *ciągu* mogą być używane tam, gdzie spodziewane są wartości *ciągów* w wyrażeniach ER. W wyrażeniach logicznych, takich jak porównania, można używać ciągów. Ponadto wartości *ciągu* mogą być współbieżne za pomocą operatora **\&** lub funkcji [CONCATENATE](er-functions-text-concatenate.md).

> [!NOTE]
> Jeśli wartości *ciągu* zostały użyte w ramach funkcji CONCATENATE, a wynikowy *ciąg* ma obejmować więcej niż jeden wiersz, należy użyć separatora podziału wiersza między wartościami. W przypadku danych wyjściowych funkcji TEXT ten separator może być znakiem generowanym za pomocą wyrażenia [CHAR](er-functions-text-char.md)(10) lub CHAR(13). W formacie HTML może to być znacznik **\<br\>**.

Domyślną wartością *ciągu* jest pusty ciąg tekstowy bez znaków, a wewnętrzna reprezentacja jest listą znaków.

Nie ma żadnych automatycznych konwersji dla ciągów. Można jednak użyć następujących funkcji konwersji jawnych:

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

Aby uzyskać więcej informacji na temat przekształcania wartości *ciagów*, zobacz [Lista funkcji ER w kategorii tekstu](er-functions-category-text.md).

*Ciąg* może zawierać nieograniczoną liczbę znaków.

Wszystkie [operatory](er-formula-language.md#Operators) porównawcze i matematyczne mogą być używane z typem danych *ciąg*.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Język formuł raportowania elektronicznego](er-formula-language.md)
- [Obsługiwane złożone typy danych](er-formula-supported-data-types-composite.md)
