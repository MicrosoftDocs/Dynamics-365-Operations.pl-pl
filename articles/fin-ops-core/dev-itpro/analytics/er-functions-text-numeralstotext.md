---
title: NUMERALSTOTEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMERALSTOTEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 31fd4076d04ce7d849555bc8301c4d23ad8e1a7e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041021"
---
# <a name="NUMERALSTOTEXT">NUMERALSTOTEXT, funkcja ER</a>

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
