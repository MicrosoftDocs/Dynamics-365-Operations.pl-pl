---
title: SUMIFS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SUMIFS w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: d9d9ef51f3c8cb090f940670c4c3afae104268ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687969"
---
# <a name="sumifs-er-function"></a>SUMIFS, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `SUMIFS` zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza.

## <a name="syntax"></a>Składnia

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Argumenty

`key name for summing`: *Ciąg*

Wartość, która jest zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu modułu Raportowanie elektroniczne (ER), dla którego wartość powiązania musi być używana do celów sumowania.

Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Liczba** lub **Ciąg** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

`condition 1 range`: *Ciąg*

Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER). Ten argument jest obowiązkowy.

Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

`condition 1 value`: *Ciąg*

Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER). Ten argument jest obowiązkowy.

Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

`condition N range`: *Ciąg*

Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER). Te dodatkowe argumenty są opcjonalne.

Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

`condition N value`: *Ciąg*

Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER). Te dodatkowe argumenty są opcjonalne.

Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.

W argumentach `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.

W argumentach `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.

## <a name="example"></a>Przykład

Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje gromadzenia danych](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]