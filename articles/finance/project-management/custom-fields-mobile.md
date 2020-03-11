---
title: Implementowanie pól niestandardowych aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet w systemach iOS i Android
description: W tym temacie przedstawiono typowe wzorce używania rozszerzeń do implementowania pól niestandardowych.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 48854c15e429d51dcf30ea804eb636dee7965443
ms.sourcegitcommit: a356299be9a593990d9948b3a6b754bd058a5b3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/21/2020
ms.locfileid: "3080779"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Implementowanie pól niestandardowych aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet w systemach iOS i Android

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono typowe wzorce używania rozszerzeń do implementowania pól niestandardowych. Omawiane są następujące tematy:

- Różne typy danych obsługiwane przez strukturę pól niestandardowych
- Sposób wyświetlania pól tylko do odczytu lub edytowalnych we wpisach karty czasu pracy oraz zapisywania wartości wprowadzonych przez użytkownika z powrotem do bazy danych
- Sposób wyświetlania pól tylko do odczytu w nagłówku karty czasu pracy
- Sposób integrowania innej niestandardowej logiki biznesowej w celu wprowadzania wartości domyślnych w polach i przeprowadzania dodatkowej weryfikacji

## <a name="audience"></a>Odbiorcy

Ten temat jest przeznaczony dla deweloperów integrujących pola niestandardowe w aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet dostępnej na systemy Apple iOS i Google Android. Przyjmuje się, że czytelnicy umieją programować w języku X++ i znają funkcje karty czasu pracy projektu.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Umowa dotycząca danych — klasa X++ TSTimesheetCustomField

Klasa **TSTimesheetCustomField** jest klasą umowy dotyczącej danych języka X++, która reprezentuje informacje o polu niestandardowym dla funkcji karty czasu pracy. Listy obiektów pól niestandardowych są przekazywane zarówno w umowie dotyczącej danych TSTimesheetDetails, jak i umowie dotyczącej danych TSTimesheetEntry w celu wyświetlania pól niestandardowych w aplikacji mobilnej.

- **TSTimesheetDetails** — umowa dotycząca nagłówka karty czasu pracy.
- **TSTimesheetEntry** — umowa dotycząca transakcji karty czasu pracy Grupy tych obiektów, których same informacje o projekcie i wartość **timesheetLineRecId** są takie same, tworzą wiersz.

### <a name="fieldbasetype-types"></a>fieldBaseType (typy)

Właściwość **FieldBaseType** obiektu **TsTimesheetCustom** określa typ pola, które pojawia się w aplikacji. Obsługiwane są następujące wartości **Typu**:

| Wartości typu | Typ              | Notatki |
|-------------|-------------------|-------|
| 0           | Ciąg (i Wyliczenie) | Pole jest wyświetlane jako pole tekstowe. |
| 1           | Wartość całkowita           | Wartość jest pokazywana jako liczba bez miejsc dziesiętnych. |
| 2           | Rzeczywisty              | Wartość jest pokazywana jako liczba z miejscami dziesiętnymi.<p>Aby w aplikacji była wyświatlana wartość rzeczywista w walucie, należy skorzystać z właściwości **fieldExtenededType**. Właściwość **numberOfDecimals** służy do ustawiania liczby wyświetlanych miejsc dziesiętnych.</p> |
| 3           | Data              | Formaty daty zależą od ustawienia **Format daty, godziny i liczb** użytkownika, które jest określone w sekcji **Preferencje dotyczące języka i kraju/regionu** w oknie **Opcje użytkownika**. |
| 4           | Wartość logiczna           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Jeśli właściwość **stringOptions** nie została podana w obiekcie **TSTimesheetCustomField**, użytkownikowi jest udostępniane pole tekstu niezależnego.

    Właściwość **stringLength** może służyć do ustawienia maksymalnej długości ciągu, jaką użytkownicy mogą wprowadzać.

- Jeśli właściwość **stringOptions** jest podana w obiekcie **TSTimesheetCustomField**, te elementy listy są jedynymi wartościami, które użytkownicy mogą wybierać za pomocą przycisków opcji (przycisków radiowych).

    W takim przypadku pole ciągu może pełnić funkcję wartości wyliczenia na potrzeby wprowadzania wartości przez użytkownika. Aby zapisać wartość w bazie danych jako wyliczenie, należy ręcznie zmapować wartość ciągu z powrotem na wartość wyliczenia przed zapisaniem jej w bazie danych za pomocą łańcucha poleceń (stosowny przykład jest pokazany w sekcji „Zapisywanie wpisu karty czasu pracy zwrotnie z aplikacji w bazie danych przy użyciu łańcucha poleceń na klasie TSTimesheetEntryService”).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

Ta właściwość służy do formatowania wartości rzeczywistych w walucie. Takie podejście ma zastosowanie tylko wtedy, gdy wartością **fieldBaseType** jest **Rzeczywista**.

- **TSCustomFieldExtendedType: brak** — formatowanie nie jest stosowane.
- **TSCustomFieldExtendedType::Waluta** — formatowanie wartości jako waluty.

    Jeśli formatowanie waluty jest aktywne, przy użyciu pola **stringValue** można przekazać kod waluty, który ma być wyświetlany w aplikacji. Wartość jest tylko do odczytu.

    Pole **realValue** zawiera kwotę pieniędzy, która ma zostać zapisana w bazie danych.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

Ta właściwość służy do określania, gdzie w aplikacji ma być wyświetlane pole niestandardowe.

- **TSCustomFieldSection::Nagłówek** — pole będzie wyświetlane w sekcji **Wyświetl więcej szczegółów** w aplikacji. Te pola są zawsze tylko do odczytu.
- **TSCustomFieldSection::Wiersz** — pole będzie wyświetlane po wszystkich polach gotowych wierszy we wpisach karty czasu pracy. Mogą to być pola z możliwością edycji lub tylko do odczytu.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Ta właściwość identyfikuje pole, gdy wartości dostarczone przez aplikację są zapisywane z powrotem w bazie danych.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Ta właściwość identyfikuje pole, gdy wartości dostarczone przez aplikację są zapisywane z powrotem w bazie danych.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Jeśli użytkownicy mają mieć możliwość edytowania pola w sekcji wpisu karty czasy pracy, należy ustawić wartość **Tak** tej właściwości. Jeśli pole ma być tylko do odczytu, należy ustawić wartość **Nie** właściwości.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Jeśli pole w sekcji wpisu karty czasy pracy ma być obowiązkowe, należy ustawić wartość **Tak** tej właściwości.

### <a name="label-str"></a>label (str)

Ta właściwość określa etykietę wyświetlaną obok pola w aplikacji.

### <a name="stringoptions-list-of-strings"></a>stringOptions (lista ciągów)

Ta właściwość ma znaczenie tylko wtedy, gdy ustawioną wartością właściwości **fieldBaseType** jest **Ciąg**. Jeśli jest ustawiona właściwość **stringOptions**, wartości ciągów, które użytkownik może wybrać za pomocą przycisków opcji (przycisków radiowych), są określane przez ciągi na liście. Jeśli nie podano żadnych ciągów, w polu ciągu jest dozwolony tekst niezależny (stosowny przykład jest pokazany w sekcji „Zapisywanie wpisu karty czasu pracy zwrotnie z aplikacji w bazie danych przy użyciu łańcucha poleceń na klasie TSTimesheetEntryService”).

### <a name="stringlength-int"></a>stringLength (int)

Ta właściwość określa maksymalną długość pola ciągu. Ma znaczenie tylko wtedy, gdy ustawioną wartością właściwości **fieldBaseType** jest **Ciąg**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Ta właściwość określa liczbę miejsc dziesiętnych wyświetlanych dla pola wartości rzeczywistej. Ma znaczenie tylko wtedy, gdy ustawioną wartością właściwości **fieldBaseType** jest **Rzeczywista**.

### <a name="ordersequence-int"></a>orderSequence (int)

Ta właściwość określa kolejność wyświetlania pól niestandardowych w aplikacji w przypadku określenia więcej niż jednego pola niestandardowego. Pola, które mają mniejsze numery, są wyświetlane jako pierwsze.

### <a name="booleanvalue-boolean"></a>booleanValue (wartość logiczna)

W przypadku pól typu **Wartość logiczna** ta właściwość przekazuje wartość logiczną pola między serwerem i aplikacją.

### <a name="guidvalue-guid"></a>guidValue (guid)

W przypadku pól typu **GUID** ta właściwość przekazuje wartość unikatowego identyfikatora globalnego (GUID) pola między serwerem i aplikacją.

### <a name="int64value-int64"></a>int64Value (int64)

W przypadku pól typu **Int64** ta właściwość przekazuje wartość int64 pola między serwerem i aplikacją.

### <a name="intvalue-int"></a>intValue (int)

W przypadku pól typu **Int** ta właściwość przekazuje wartość int pola między serwerem i aplikacją.

### <a name="realvalue-real"></a>realValue (real)

W przypadku pól typu **Rzeczywista** ta właściwość przekazuje wartość rzeczywistą pola między serwerem i aplikacją.

### <a name="stringvalue-str"></a>stringValue (str)

W przypadku pól typu **Ciąg** ta właściwość przekazuje wartość ciągu pola między serwerem i aplikacją. Jest ona również stosowana do pól typu **Rzeczywista**, które są sformatowane jako waluta. W przypadku tych pól właściwość służy do przekazania kodu waluty do aplikacji.

### <a name="datevalue-date"></a>dateValue (data)

W przypadku pól typu **Data** ta właściwość przekazuje wartość daty pola między serwerem i aplikacją.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Wyświetlanie i zapisywanie pola niestandardowego w sekcji wpisu karty czasu pracy

Poniżej znajduje się zrzut ekranu tworzenia wpisu karty czasu pracy w aplikacji mobilnej. Są w nim widoczne gotowe pola oraz pole niestandardowe w sekcji „Wpis czasu” o nazwie „Ciąg testowy” z ustawioną wartością wyliczenia „Druga opcja”.

![Pole niestandardowe ciągu testowego w aplikacji](media/timesheet-entry.jpg)



Poniżej znajduje się zrzut ekranu, na którym użytkownik wybiera jedną z opcji wyliczenia dostępnych w polu niestandardowym „Ciąg testowy” w aplikacji mobilnej.  Opcje „Pierwsza opcja” i „Druga opcja” są wyświetlane jako przyciski radiowe. Zaznaczona jest druga opcja.

![Przyciski opcji (przyciski radiowe) pola niestandardowego ciągu testowego](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>Rozszerzanie tabeli TSTimesheetLine o pole niestandardowe

W typowych scenariuszach pole niestandardowe sekcji wpisu karty czasu pracy jest zazwyczaj zapisywane w tabeli TSTimesheetLine. Możliwe jest jednak użycie innych tabel, jeśli dane mogą być pobierane na podstawie dostarczonego rekordu TSTimesheetTrans lub jeśli nie ma on określonego kontekstu rekordów (na przykład, jeśli w parametrach projektu pole jest ustawione jako tylko do odczytu).

Należy pamiętać, że pola niestandardowe nie muszą zawierać żadnych kopii zapasowych rekordów bazy danych. Można je dynamicznie generować na podstawie logiki X++. Ta metoda może być przydatna w scenariuszach tylko do odczytu (przykłady dynamicznie generowanych wartości pól niestandardowych są pokazane w sekcji „Wypełnianie szczegółów karty czasy pracy przy użyciu łańcucha poleceń na klasie TSTimesheetDetails class, metodzie buildCustomFieldListForHeader”).

Poniżej znajduje się zrzut ekranu drzewa obiektów aplikacji z programu Visual Studio. Jest w nim widoczne rozszerzenie tabeli TSTimesheetLine z polem TestLineString dodanym jako pole niestandardowe.

![Ciąg wiersza](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>Wyświetlanie pola w sekcji wpisu karty czasu pracy przy użyciu łańcucha poleceń na metodzie buildCustomFieldList klasy TSTimesheetSettings

Ten kod steruje ustawieniami wyświetlania pola w aplikacji. Na przykład określa typ pola, etykietę, czy pole jest wymagane oraz sekcję, w której jest wyświetlane pole.

Poniższy przykład przedstawia pole ciągu we wpisach czasu. W tym polu dostępne są dwie opcje, **Pierwsza opcja** i **Druga opcja**, które są dostępne za pośrednictwem przycisków opcji (przycisków radiowych). Pole w aplikacji jest skojarzone z polem **TestLineString**, które jest dodawane do tabeli TSTimesheetLine.

Należy zwrócić uwagę na użycie metody **TSTimesheetCustomField::newFromMetatdata()** w celu uproszczenia inicjowania właściwości pól niestandardowych: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** i **numberOfDecimals**. Parametry te można również ustawić ręcznie.

```xpp
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>Wprowadzanie wartości we wpisie karty czasu pracy użyciu łańcucha poleceń na metodzie buildCustomFieldListForEntry klasy TSTimesheetEntry

Metoda **buildCustomFieldListForEntry** służy do wprowadzania wartości w zapisanych wierszach karty czasu pracy w aplikacji mobilnej. Przyjmuje ona rekord TSTimesheetTrans jako parametr. Pola z tego rekordu mogą być używane do wstawiania wartości pola niestandardowego w aplikacji.

```xpp
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>Zapisywanie wpisu karty czasu pracy zwrotnie z aplikacji w bazie danych przy użyciu łańcucha poleceń na klasie TSTimesheetEntryService

Aby zapisać pole niestandardowe z powrotem w bazie danych w typowym użyciu, należy rozszerzyć wiele metod:

- Metoda **timesheetLineNeedsUpdating** służy do określenia, czy rekord wiersza został zmieniony przez użytkownika w aplikacji i musi zostać zapisany w bazie danych. Jeśli wydajność nie jest istotna, można uprościć tę metodę, tak aby zawsze zwracała wartość **true**.
- Metody **populateTimesheetLineFromEntryDuringCreate** i **populateTimesheetLineFromEntryDuringUpdate** można rozszerzać, tak aby wprowadzały w rekordzie bazy danych TSTimesheetLine wartości z dostarczonego rekordu umowy dotyczącej danych TSTimesheetEntry. W poniższym przykładzie należy zauważyć, że mapowanie między polem bazy danych i polem wprowadzania jest wykonywane ręcznie za pomocą kodu X++.
- Metodę **populateTimesheetWeekFromEntry** można również rozszerzyć, jeśli pole niestandardowe zmapowane do obiektu **TSTimesheetEntry** musi zostać zapisane z powrotem w tabeli bazy danych TSTimesheetLineweek.

> [!NOTE]
> W poniższym przykładzie wartość **firstOption** lub **secondOption**, zależnie od wyboru użytkownika, jest zapisywana w bazie danych jako wartość ciągu nieprzetworzonego. Jeśli pole bazy danych jest polem typu **Wyliczenie**, wartości te można zamapować ręcznie na wartość wyliczenia, a następnie zapisać je w polu wyliczenia w tabeli bazy danych.

```xpp
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Wyświetlanie pola niestandardowego w sekcji nagłówka karty czasu pracy

Poniżej znajduje się zrzut ekranu do przeglądania karty czasu pracy w aplikacji mobilnej przez użytkownika. W prawym górnym rogu naciśnięto przycisk „Więcej informacji”, aby wyświetlić opcję „Wyświetl więcej szczegółów”.  

![Polecenie Wyświetl więcej szczegółów](media/show-more.png)

Poniżej znajduje się zrzut ekranu z sekcją „Więcej” karty czasu pracy w aplikacji mobilnej. Do sekcji nagłówka karty czasu pracy dodano pole niestandardowe o nazwie „Stopień wykorzystania tej karty czasu pracy (obliczone pole niestandardowe)” W polu niestandardowym ustawiono wartość tylko do odczytu „0,667”.

![Sekcja Więcej](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>Rozszerzanie tabeli TSTimesheetTable o pole niestandardowe

W typowych scenariuszach pole niestandardowe sekcji nagłówka pochodzi zazwyczaj z tabeli TSTimesheetHeader. Możliwe jest jednak użycie innych tabel, jeśli dane mogą być pobierane na podstawie dostarczonego rekordu TSTimesheetTable lub jeśli nie ma on określonego kontekstu rekordów (na przykład, jeśli w parametrach projektu pole jest ustawione jako tylko do odczytu).

Należy pamiętać, że pola niestandardowe nie muszą zawierać żadnych kopii zapasowych rekordów bazy danych. Można je dynamicznie generować na podstawie logiki X++. Poniższy przykład ilustruje to podejście.

Pola w sekcji nagłówka są zawsze tylko do odczytu w aplikacji.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>Wyświetlanie pola w sekcji nagłówka przy użyciu łańcucha poleceń na metodzie buildCustomFieldList klasy TSTimesheetSettings

Ten kod steruje ustawieniami wyświetlania pola w aplikacji. Na przykład określa typ pola, etykietę, czy pole jest wymagane oraz sekcję, w której jest wyświetlane pole.

W poniższym przykładzie przedstawiono obliczoną wartość w sekcji nagłówka w aplikacji.

```xpp
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>Wypełnianie szczegółów karty czasu pracy użyciu łańcucha poleceń na metodzie buildCustomFieldListForHeader klasy TSTimesheetDetails

Metoda **buildCustomFieldListForHeader** służy do wypełniania szczegółów nagłówka karty czasu pracy w aplikacji mobilnej. Przyjmuje ona rekord TSTimesheetTable jako parametr. Pola z tego rekordu mogą być używane do wstawiania wartości pola niestandardowego w aplikacji. W poniższym przykładzie nie są odczytywane żadne wartości z bazy danych. Zamiast tego przy użyciu logiki X++ generowana jest obliczona wartość, która jest następnie wyświetlana w aplikacji.


```xpp
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Inne możliwości konfigurowania/rozszerzania

### <a name="adding-additional-validation-for-the-app"></a>Wstawianie dodatkowych weryfikacji do aplikacji

Istniejąca logika funkcji karty czasu pracy na poziomie bazy danych będzie nadal działać zgodnie z oczekiwaniami. Aby przerwać kończenie operacji zapisywania lub przesyłania i wyświetlić określony komunikat o błędzie, można dodać wiersz **throw error("message to user")** do kodu za pośrednictwem łańcucha rozszerzenia polecenia. Oto trzy przykłady przydatnych metod rozszerzania:

- Jeśli **validateWrite** w tabeli TSTimesheetLine zwraca wartość **false** podczas operacji zapisywania wiersza karty czasu pracy, w aplikacji mobilnej jest wyświetlany komunikat o błędzie.
- Jeśli **validateSubmit** w tabeli TSTimesheetTable zwraca wartość **false** podczas przesyłania karty czasu pracy w aplikacji, użytkownikowi jest wyświetlany komunikat o błędzie.
- Logika, która wypełnia pola (na przykład **Właściwośćwiersza**) w trakcie metody **insert** w tabeli TSTimesheetLine, będzie nadal działać.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Ukrywanie i oznaczanie gotowych pól jako tylko do odczytu za pomocą konfiguracji

Z poziomu parametrów projektu można tworzyć gotowe pola tylko do odczytu lub ukryte w aplikacji mobilnej. Opcje są ustawiane w sekcji **Mobilne karty czasu pracy** na karcie **Karta czasu pracy** strony **Parametry modułu Zarządzanie projektami i ich księgowanie**.

![Parametry projektu](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>Zmienianie działań dostępnych do wybrania za pomocą rozszerzeń

Działania dostępne do wybrania dla projektu są wypełniane za pośrednictwem metod **getActivitiesForProject ()** i **getActivityQuery ()** w klasie **TsTimesheetProjectService**. Za pomocą łańcucha poleceń można zmienić to zachowanie w celu dopasowania go do scenariusza biznesowego dla działań dostępnych do wybrania dla konkretnego projektu.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Wprowadzanie domyślnej kategorii projektu we wpisach karty czasu pracy

Wprowadzanie domyślnej kategorii projektu we wpisach karty czasu pracy odbywa się na trzech poziomach. Zachowanie na dowolnym z tych poziomów można rozszerzyć za pomocą łańcucha poleceń, aby osiągnąć pożądane zachowanie. Obowiązuje następująca hierarchia:

1. Aplikacja próbuje umieścić domyślną kategorię z zasobu projektu. Ta kategoria domyślna jest ustawiana w metodach **getCurrentUserResource** i **getDelegatedResourcesForCurrentUser** w klasie **TSTimesheetSettingsService**.
2. Jeśli na poziomie zasobów projektu nie określono kategorii domyślnej, aplikacja próbuje ściągnąć ją z działania projektu. Ta kategoria domyślna jest ustawiana w metodzie **getActivitiesForProject** w klasie **TSTimesheetProjectService**.
3. Jeśli na poziomie działania projektu nie określono kategorii domyślnej, kategoria domyślna jest pobierana z parametrów projektu. Ta kategoria domyślna jest ustawiana w metodzie **getProjectDetailsbyRule** w klasie **TSTimesheetProjectService**.
