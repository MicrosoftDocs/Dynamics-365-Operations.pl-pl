---
title: DATETIMEVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATETIMEVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: de601ad08b85797a4241ef74ecb3eba37eda37ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917541"
---
# <a name="DATETIMEVALUE">DATETIMEVALUE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `DATETIMEVALUE` zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości tekstowej w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty/godziny. Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Składnia 1

```
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Składnia 2

```
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Tekst reprezentujący wartość do sformatowania.

`format`: *Ciąg*

Format danego tekstu.

`culture`: *Ciąg*

Kultura używana do formatowania danego tekstu.

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący. Jeśli na przykład funkcja `DATETIMEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej. Domyślna wartość `culture` to **EN-US**.

## <a name="example-1"></a>Przykład 1

Funkcja `DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` zwraca datę **2:55:00 21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.

## <a name="example-2"></a>Przykład 2

Funkcja `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` zwraca **2:55:00 21 grudnia 2016** na podstawie określonego formatu niestandardowego i kultury.

Natomiast funkcja `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa wartość daty/godziny dla określonej kultury.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)
