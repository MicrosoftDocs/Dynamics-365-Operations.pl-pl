---
title: Lista funkcji modułu ER w kategorii funkcji listy
description: Ten temat zawiera ogólne informacje o funkcjach listy obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9461d0afd75f421cf03ddefed5dac379f1369ec7
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917771"
---
# <a name="list-of-er-functions-in-the-list-category"></a>Lista funkcji modułu ER w kategorii funkcji listy

[!include [banner](../includes/banner.md)]

Funkcje listy w module raportowania elektronicznego (ER) mogą być używane do wyodrębniania informacji z i wykonywania operacji na źródłach danych o typu danych *Lista rekordów* i *Kontener (rekordu)*. Ten temat zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Ta funkcja działa jako wybór w pamięci. Zwraca nową spłaszczoną wartość *Lista rekordów*, która składa się z listy rekordów reprezentującej wszystkie elementy, które odpowiadają określonej ścieżce. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Ta funkcja jest wykonywana jako sprzężone zapytanie SQL. Zwraca nową spłaszczoną wartość *Lista rekordów*, która składa się z listy rekordów reprezentującej wszystkie elementy, które odpowiadają określonej ścieżce. |
| [Zliczanie](er-functions-list-count.md)                       | Ta funkcja zwraca wartość typu *Liczba całkowita* reprezentującą liczbę rekordów na określonej liście, jeśli lista nie jest pusta. Jeśli lista jest pusta, ta funkcja zwraca wartość **0** (zero). |
| [EmptyList](er-functions-list-emptylist.md)               | Ta funkcja zwraca pustą wartość typu *Lista rekordów* przez użycie określonej listy jako źródła dla struktury listy.|
| [Wylicz](er-functions-list-enumerate.md)               | Ta funkcja zwraca nową wartość typu *Lista rekordów*, która składa się z wyliczonych rekordów określonej listy. |
| [Filtruj](er-functions-list-filter.md)                     | Ta funkcja zwraca określoną listę jako wartość typu *Lista rekordów* po zmianie zapytania tak, aby filtrowała ona dane pod kątem określonego warunku. |
| [Pierwsze](er-functions-list-first.md)                       | Ta funkcja zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta. Jeśli lista jest pusta, ta funkcja zgłasza wyjątek. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Ta funkcja zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ten rekord nie jest pusty. Jeśli rekord jest pusty, ta funkcja zwraca wartość null typu *Kontener (rekord)*. |
| [Index](er-functions-list-index.md)                       | Ta funkcja zwraca wartość typu *Kontener (rekord)*, która jest wybierana przy użyciu określonego indeksu liczbowego na określonej liście. Jeśli indeks jest poza zakresem rekordów na określonej liście, ta lista zgłasza wyjątek. |
| [IsEmpty](er-functions-list-isempty.md)                   | Ta funkcja zwraca wartość *logiczną* **TRUE**, jeśli określona lista nie zawiera żadnych rekordów. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [Lista](er-functions-list-list.md)                         | Ta funkcja zwraca wartość typu *Lista rekordów*, która składa się z nowej listy utworzonej na podstawie określonych argumentów.|
| [ListOfFields](er-functions-list-listoffields.md)         | Ta funkcja zwraca wartość typu *Lista rekordów*, która jest tworzona na podstawie struktury określonego argumentu typu *Wyliczenie* lub *Kontener (rekord)*. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Ta funkcja zwraca wartość typu *Lista rekordów*, która składa się tylko z pierwszego rekordu określonej listy.|
| [OrderBy](er-functions-list-orderby.md)                   | Ta funkcja zwraca określoną listę jako wartość typu *Lista rekordów* po jej posortowaniu zgodnie z określonymi argumentami. Te argumenty można zdefiniować jako wyrażenia. |
| [Wycofaj](er-functions-list-reverse.md)                   | Ta funkcja zwraca określoną listę jako wartość *Lista rekordów* w odwróconej kolejności sortowania. |
| [Podział](er-functions-list-split.md)                       | Ta funkcja dzieli określony ciąg wejściowy na podciągi i zwraca wynik jako nową wartość *Lista rekordów*. |
| [SplitList](er-functions-list-splitlist.md)               | Ta funkcja dzieli określoną listę na listy podrzędne (lub partie), z których każda zawiera określoną liczbę rekordów. Zwraca ona wynik jako nową wartość typu *Lista rekordów*, która składa się z partii. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Ta funkcja dzieli określoną listę na nową listę list podrzędnych (partii). Liczba rekordów w każdej partii jest obliczana dynamicznie. Funkcja zwraca wynik jako nową wartość typu *Lista rekordów*, która składa się z partii. |
| [StringJoin](er-functions-list-stringjoin.md)             | Ta funkcja zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola na wybranej liście. Wartości mogą być rozdzielone wybranym separatorem. |
| [Gdzie](er-functions-list-where.md)                       | Ta funkcja zwraca określoną listę jako wartość typu *Lista rekordów* po jej odfiltrowaniu zgodnie z określonym warunkiem. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)
