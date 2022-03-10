---
title: FORMATELEMENTNAME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FORMATELEMENTNAME w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 72977edfbe06e0d68d9226c9c25fa0633e7951d22438e053ae2a7cf4ef9a5848
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764496"
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