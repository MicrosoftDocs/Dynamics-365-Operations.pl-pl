---
title: NUMERALSTOTEXT, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji NUMERALSTOTEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a19c0aa9d8db9b1a6dae55208b866c3dd5858a03
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892930"
---
# <a name="numeralstotext-er-function"></a>NUMERALSTOTEXT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NUMERALSTOTEXT` zwraca określoną liczbę jako wartość *Ciąg* po jej zapisaniu (czyli przekonwertowaniu na ciągi tekstowe) w określonym języku.

## <a name="syntax"></a>Składnia

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba całkowita* lub *Liczba rzeczywista*

Wartość liczbowa, która określa liczbę do zapisania.

`language`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kod języka.

`currency`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kod waluty.

`print currency name flag`: *Wartość logiczna*

Wartość *logiczna* wskazująca, czy nazwa waluty musi zostać dodana do napisanego tekstu.

`decimal points`: *Liczba całkowita*

Wartość *całkowita*, która wskazuje liczbę miejsc dziesiętnych na potrzeby zapisanego tekstu.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Kod języka jest opcjonalny. Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używany kod języka aktualnie uruchomionego kontekstu. Domyślny kod języka to **EN-US**. Kod języka dla uruchomionego kontekstu jest zdefiniowany w elemencie **Folder** lub **Plik** w uruchomionym formacie raportowania elektronicznego (ER).

Kod waluty jest opcjonalny. Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używana waluta firmy aktualnie uruchomionego kontekstu.

> [!NOTE] 
> Argumenty `print currency name flag` i `decimal points` są analizowane tylko dla następujących kodów języków: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** i **RU**. Ponadto argument `print currency name flag` jest analizowany tylko dla firm, których kontekst kraju lub regionu obsługuje deklinację nazw walut.

## <a name="example-1"></a>Przykład 1

Funkcja `NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` zwraca wartość **"One Thousand Two Hundred Thirty Four and 56"**.

## <a name="example-2"></a>Przykład 2

Funkcja `NUMERALSTOTEXT (120, "PL", "", false, 0)` zwraca wartość **„Sto dwadzieścia”**. 

## <a name="example-3"></a>Przykład 3

Funkcja `NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` zwraca wartość **„сто двадцать евро 21 евроцент”**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]