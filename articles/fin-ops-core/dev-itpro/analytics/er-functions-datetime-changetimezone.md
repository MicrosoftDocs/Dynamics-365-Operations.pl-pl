---
title: CHANGETIMEZONE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji CHANGETIMEZONE w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: be94f57cfcb6115ea386a279c379662f7d401d11
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903593"
---
# <a name="changetimezone-er-function"></a>CHANGETIMEZONE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `CHANGETIMEZONE` zwraca wartość *[Data/godzina](er-formula-supported-data-types-primitive.md#datetime)* w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]), która jest konwertowana z danej wartości daty/godziny w jednej strefie czasowej na wartość daty/godziny w innej strefie czasowej.

## <a name="syntax"></a>Składnia

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Argumenty

`datetime`: *Data/godzina*

Wartość daty/czasu w strefie czasowej Uniwersalny czas koordynowany, która reprezentuje wartość daty/godziny do konwersji.

`base time zone`: *[Ciąg](er-formula-supported-data-types-primitive.md#string)*

Nazwa strefy czasowej, do której przenoszona jest podana wartość daty/godziny przed konwersją.

`target time zone`: *Ciąg*

Nazwa strefy czasowej, do której przenoszona jest konwertowana wartość daty/godziny w trakcie konwersji.

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wynikowa wartość daty/godziny w strefie czasowej Uniwersalny czas koordynowany.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Aby określić źródłową i docelową strefę czasową, można użyć nazw stref czasowych [podawanych](https://data.iana.org/time-zones/releases/) przez organizację [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/) lub [obsługiwanych](/windows-hardware/manufacture/desktop/default-time-zones) przez system Microsoft Windows.

W czasie wykonywania wyjątek „Strefa czasowa '\<time zone name\>'” nie istnieje, jeśli nie znaleziono podanej nazwy na liście IANA lub w rejestrze systemu Windows.

W przypadku stref czasowych, w których jest stosowany czas letni, konwersja uwzględnia przesunięcie związane z czasem letnim w strefie uniwersalnego czasu koordynowanego. Podczas konwersji są używane najnowsze dostępne informacje o tym przesunięciu.

## <a name="example-1"></a>Przykład 1

W tym przykładzie są używane nazwy stref czasowych systemu Windows.

Konfigurujesz źródło danych **DSX** typu **Pole obliczeniowe**. Zawiera ono następujące wyrażenie.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

W przypadku konfigurowania wyrażenia źródła danych **DSY** typu **Pole obliczeniowe** jako `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, źródło danych **DSX** zwraca tekst **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Ten tekst pokazuje, że różnica czasu między dwiema wybranymi strefami czasowymi 1 czerwca wynosi więcej niż 24 godziny. Dlatego przekonwertowana wartość daty/godziny jest o jeden dzień wcześniejsza niż podana wartość daty/godziny, ponieważ podstawowa strefa czasowa znajduje się po docelowej strefie czasowej.

W przypadku konfigurowania wyrażenia źródła danych **DSY** typu **Pole obliczeniowe** jako `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, źródło danych **DSX** zwraca tekst **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Ten tekst pokazuje, że różnica czasu między dwiema wybranymi strefami czasowymi 1 grudnia wynosi mniej niż 24 godziny. Dlatego przekonwertowana wartość daty/godziny jest równa podanej wartości daty/godziny.

> [!NOTE]
> To samo wyrażenie zwraca różne odchylenie między podaną i przekonwertowaną wartością daty/godziny dla tej samej pary stref czasowych, ponieważ dla podanych stref czasowych w danej dacie/godzinie jest odnotowane różne przesunięcie uniwersalnego czasu koordynowanego przy zmianie czasu na letni.

## <a name="example-2"></a>Przykład 2

W tym przykładzie są używane nazwy stref czasowych organizacji IANA.

Konfigurujesz źródło danych **DSX** typu **Pole obliczeniowe**. Zawiera ono następujące wyrażenie.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

W przypadku konfigurowania wyrażenia źródła danych **DSY** typu **Pole obliczeniowe** jako `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, źródło danych **DSX** zwraca tekst **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Ten tekst pokazuje, że różnica czasu między dwiema wybranymi strefami czasowymi 1 czerwca wynosi więcej niż 24 godziny. Dlatego przekonwertowana wartość daty/godziny jest o jeden dzień wcześniejsza niż podana wartość daty/godziny, ponieważ podstawowa strefa czasowa znajduje się po docelowej strefie czasowej.

W przypadku konfigurowania wyrażenia źródła danych **DSY** typu **Pole obliczeniowe** jako `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, źródło danych **DSX** zwraca tekst **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Ten tekst pokazuje, że różnica czasu między dwiema wybranymi strefami czasowymi 1 grudnia wynosi mniej niż 24 godziny. Dlatego przekonwertowana wartość daty/godziny jest równa podanej wartości daty/godziny.

## <a name="example-3"></a>Przykład 3

Konfigurujesz źródło danych **DSX** typu **Pole obliczeniowe**. Zawiera ono następujące wyrażenie.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

W przypadku konfigurowania wyrażenia źródła danych **DSY** typu **Pole obliczeniowe** jako `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, źródło danych **DSX** zwraca tekst **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00'**. Ten tekst pokazuje, że różnica czasu między dwiema wybranymi strefami czasowymi 1 czerwca wynosi więcej niż 24 godziny. Dlatego przekonwertowana wartość daty/godziny jest o jeden dzień późniejsza niż docelowa wartość daty/czasu, ponieważ docelowa strefa czasowa znajduje się po podstawowej strefie czasowej.

## <a name="example-4"></a>Przykład 4

Użytkownik może otrzymać datę/sygnaturę czasową z zewnętrznego źródła jako tekst, który nie zawiera informacji o strefie czasowej. Można jednak znać strefę czasową, w których działa źródło. Można na przykład otrzymać datę/sygnaturę czasową **01/12/2021 12:55:00** z usługi obsługiwanej w Hiszpanii. Aby poprawnie zapisać tę wartość daty/godziny w bazie danych, należy wykonać następującą konwersję:

- Skonfiguruj źródło danych **DSY** typu **Pole obliczeniowe**, aby przekonwertować datę/sygnaturę czasową z tekstu na wartość daty/godziny w uniwersalnym czasie koordynowanym.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Skonfiguruj źródło danych **DSX** typu **Pole obliczeniowe**, aby zmienić przekonwertowaną wartość daty/godziny na uniwersalny czas koordynowany jako wartość daty/godziny dla strefy czasowej źródła zewnętrznego.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> Używając funkcji `CHANGETIMEZONE` do konwersji daty/czasu, należy pamiętać, że dowolna wartość daty/godziny jest przechowywana w bazie danych jako wartość w strefie czasowej Uniwersalny czas koordynowany. Zanim ta wartość będzie prezentowana na stronach aplikacji, zostanie przekształcona. Przekształcenie uwzględnia strefę czasową [ustawioną](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) jako strefę preferowaną dla aktualnie zalogowanego użytkownika aplikacji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
