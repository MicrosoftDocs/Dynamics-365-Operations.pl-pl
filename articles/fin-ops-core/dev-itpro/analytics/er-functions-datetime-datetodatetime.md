---
title: DATETODATETIME, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji DATETODATETIME w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 30fe75c7fd68edfff3e3778192723792d0f342ab
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287317"
---
# <a name="datetodatetime-er-function"></a>DATETODATETIME, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `DATETODATETIME` zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]).

## <a name="syntax"></a>Składnia

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Argumenty

`date`: *Data*

Wartość daty, która reprezentuje datę do przekonwertowania.

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="example-1"></a>Przykład 1

Funkcja `DATETODATETIME (CompInfo. 'getCurrentDate()')` zwraca datę bieżącej sesji aplikacji Microsoft Dynamics 365 Finance, 24 grudnia 2015 r. jako **12/24/2015 12:00:00 AM**. W tym przykładzie **CompInfo** jest źródłem danych modułu Raportowanie elektroniczne (ER) typu **aplikacje finansowe i operacyjne/Tabela** i odwołuje się do tabeli CompanyInfo.

## <a name="example-2"></a>Przykład 2

Funkcja `DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` zwraca wartość daty/godziny **11/12/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
