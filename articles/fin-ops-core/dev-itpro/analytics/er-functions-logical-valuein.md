---
title: VALUEIN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUEIN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 08/18/2020
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
ms.openlocfilehash: b4f88c0d71b6fa6980ee8e180ae5be482a463f1c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744678"
---
# <a name="valuein-er-function"></a>VALUEIN, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `VALUEIN` określa, czy podane dane wejściowe pasują do którejkolwiek wartości określonego elementu na podanej liście. Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.

## <a name="syntax"></a>Składnia

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Argumenty

`input`: *Pole*

Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów*. To z wartością tego elementu będzie dokonywane porównanie.

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`list item expression`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które wskazuje na albo zawiera pojedyncze pole określonej listy, która ma być używana do porównania.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Zasadniczo funkcja `VALUEIN` jest przekształcana na zbiór warunków **OR**. Jeśli lista warunków **OR** jest duża, a maksymalna całkowita długość instrukcji SQL mogła zostać przekroczona, należy rozważyć użycie funkcji [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

W niektórych przypadkach można ją przekształcić na instrukcję SQL bazy danych za pomocą operatora `EXISTS JOIN`.

## <a name="example-1"></a>Przykład 1

W mapowaniu modelu definiujesz źródło danych **Lista** typu *Pole obliczeniowe*. To źródło danych zawiera wyrażenie `SPLIT ("a,b,c", ",")`.

Gdy źródło danych jest wywoływane, jeśli zostało skonfigurowane jako wyrażenie `VALUEIN ("B", List, List.Value)`, zwraca wartość **TRUE**. W tym przypadku funkcja `VALUEIN` jest przekształcana na następujący zbiór warunków: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, gdzie `("B" = "b")` równa się **TRUE**.

Gdy źródło danych jest wywoływane, jeśli zostało skonfigurowane jako wyrażenie `VALUEIN ("B", List, LEFT(List.Value, 0))`, zwraca wartość **FALSE**. W tym przypadku funkcja `VALUEIN` jest przekształcana na następujący warunek: , gdzie `("B" = "")` nie równa się **TRUE**.

Górny limit liczby znaków w treści takiego warunku to 32 768 znaków. Z tego względu nie należy tworzyć źródeł danych, które w czasie wykonywania mogą spowodować przekroczenie tego limitu. W przypadku przekroczenia limitu aplikacja przestaje działać i zgłasza wyjątek. Na przykład taka sytuacja może wystąpić, jeśli źródło danych jest skonfigurowane za pomocą wyrażenia `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, a listy **List1** i **List2** zawierają bardzo dużo rekordów.

W niektórych przypadkach funkcja `VALUEIN` jest przekształcana na instrukcję bazy danych za pomocą operatora `EXISTS JOIN`. Takie zachowanie występuje, gdy jest używana funkcja [`FILTER`](er-functions-list-filter.md) i są spełnione następujące warunki:

- Opcja **MONITUJ O ZAPYTANIE** jest wyłączona w źródle danych funkcji `VALUEIN` odwołującej się do listy rekordów. W czasie wykonywania do tego źródła danych nie będą stosowane żadne dodatkowe warunki.
- Nie skonfigurowano żadnych warunków zagnieżdżonych w źródle danych funkcji `VALUEIN` odwołującej się do listy rekordów.
- Element listy w funkcji `VALUEIN` odwołuje się do pola podanego źródła danych, a nie do wyrażenia lub metody tego źródła danych.

Warto rozważyć używanie tej opcji zamiast funkcji [`WHERE`](er-functions-list-where.md), którą opisano wcześniej w tym przykładzie.

## <a name="example-2"></a>Przykład 2

Definiuje się następujące źródła danych w mapowaniu modelu:

- Źródło danych **In** typu *Rekordy tabeli*. To źródło danych odnosi się do tabeli Intrastat.
- Źródło danych **Port** typu *Rekordy tabeli*. To źródło danych odnosi się do tabeli IntrastatPort.

Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, zostanie wygenerowana poniższa instrukcja SQL w celu zwrócenia odfiltrowanych rekordów tabeli Intrastat.

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Dla pól **dataAreaId** zostanie wygenerowana końcowa instrukcja SQL przy użyciu operatora `IN`.

## <a name="example-3"></a>Przykład 3

Definiuje się następujące źródła danych w mapowaniu modelu:

- Źródło danych **Le** typu *Pole obliczeniowe*. To źródło danych zawiera wyrażenie `SPLIT ("DEMF,GBSI,USMF", ",")`.
- Źródło danych **In** typu *Rekordy tabeli*. To źródło danych odnosi się do tabeli Intrastat z włączoną opcją **Między firmami**.

Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, końcowa instrukcja SQL zawiera następujący warunek.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)

[Funkcje VALUEINLARGE](er-functions-logical-valueinlarge.md)
