---
title: JSONVALUE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji JSONVALUE w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 10/25/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: fba1141bce91fd7c9da3cd21aef13ce99329f379
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267972"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `JSONVALUE` analizuje dane w formacie JSON (JavaScript Object Notation), do których dostęp jest uzyskiwany za pośrednictwem wskazanej ścieżki oraz wyodrębnia wartość skalarną opartą na podanym identyfikatorze. Następnie zwraca wartość skalarną wyodrębnioną jako wartość typu *Ciąg*.

## <a name="syntax"></a>Składnia

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg*, który zawiera dane JSON.

`path`: *Ciąg*

Identyfikator wartości skalarnej danych JSON. Ukośnik (/) oddziela nazwy powiązanych węzłów JSON. Aby określić indeks określonej wartości w tablicy JSON, użyj notacji z nawiasami okrągłymi (\[\]). Należy zwrócić uwagę, że dla tego indeksu jest używana numerowanie oparte na wartości zerowej.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example-1"></a>Przykład 1

Źródło danych **JsonField** zawiera następujące dane w formacie JSON: **{"Numer_kompilacji":"7.3.1234.1", "KeyThumbprint":"7366E"}**. W tym przypadku wyrażenie `JSONVALUE (JsonField, "BuildNumber")` zwraca następującą wartość typu danych *String*: **"7.3.1234.1".**

## <a name="example-2"></a>Przykład 2

Źródło danych **JsonField** typu *Pole obliczeniowe* zawiera następujące wyrażenie: `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

To wyrażenie jest skonfigurowane do zwracania wartości [*ciągu*](er-formula-supported-data-types-primitive.md#string) reprezentującego następujące dane w formacie JSON.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

W tym przypadku wyrażenie `JSONVALUE(json, "workers/[1]/emails/[0]")` zwraca następującą wartość typu danych *Ciąg*: `JohnS@Contoso.com`.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
