---
title: FORMATELEMENTNAME, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji FORMATELEMENTNAME w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 1c8c319075f8f39bec963df2c88d2d8d3beace43
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275446"
---
# <a name="formatelementname-er-function"></a>FORMATELEMENTNAME, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `FORMATELEMENTNAME` zwraca wartość typu *Ciąg* reprezentującą nazwę bieżącego elementu formatu raportowania elektronicznego (ER).

## <a name="syntax"></a>Składnia

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Tę funkcję można wywoływać w wyrażeniach ER skonfigurowanych dla właściwości **Nazwa pobranego klucza danych** i **Wartość pobranego klucza danych** składnika formatu ER z grupy **Tekst** znajdującej się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.

## <a name="example"></a>Przykład

Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje gromadzenia danych](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
