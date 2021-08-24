---
title: COUNTIF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNTIF w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: a2946a855929dd4dc9647b1e53f0f8a739c522ef8703570e11a4b43636be77dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714594"
---
# <a name="countif-er-function"></a>COUNTIF, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `COUNTIF` zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, oraz spełniającą określony warunek. Warunek składa się z zakresu kluczy i wartości klucza.

## <a name="syntax"></a>Składnia

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a>Argumenty

`condition range`: *Ciąg*

Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).

`condition value`: *Ciąg*

Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Właściwości **Nazwa pobranego klucza danych** i **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.

W argumencie `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.

W argumencie `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.

## <a name="example"></a>Przykład

Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje gromadzenia danych](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]