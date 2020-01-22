---
title: DATEVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATEVALUE w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 700a48d2c5a77398267e6daaaea3ecb6c95e7f6e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916368"
---
# <a name="DATEVALUE">DATEVALUE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `DATEVALUE` zwraca wartość *daty*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej [kultury](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty. Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Składnia 1

```
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Składnia 2

```
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Tekst reprezentujący wartość do sformatowania.

`format`: *Ciąg*

Format danego tekstu.

`culture`: *Ciąg*

Kultura używana do formatowania danego tekstu.

## <a name="return-values"></a>Wartości zwracane

*Data*

Wyjściowa wartość daty.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący. Jeśli na przykład funkcja `DATEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej. Domyślna wartość `culture` to **EN-US**.

## <a name="example-1"></a>Przykład 1

Funkcja `DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` zwraca datę **21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.

## <a name="example-2"></a>Przykład 2

Funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` zwraca wartość daty **21 stycznia 2016** na podstawie określonego formatu niestandardowego i kultury.

Natomiast funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa data.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)
