---
title: DATETODATETIME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATETODATETIME w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: f9ce977b36cd96a27a228dba1bc8c8445bafd879
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916391"
---
# <a name="DATETODATETIME">DATETODATETIME, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `DATETODATETIME` zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]).

## <a name="syntax"></a>Składnia

```
DATETODATETIME (date)
```

## <a name="arguments"></a>Argumenty

`date`: *Data*

Wartość daty, która reprezentuje datę do przekonwertowania.

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="example-1"></a>Przykład 1

Funkcja `DATETODATETIME (CompInfo. 'getCurrentDate()')` zwraca datę bieżącej sesji aplikacji Microsoft Dynamics 365 Finance, 24 grudnia 2015 r. jako **12/24/2015 12:00:00 AM**. W tym przykładzie **CompInfo** jest źródłem danych modułu Raportowanie elektroniczne (ER) typu **Finance and Operations/Tabela** i odwołuje się do tabeli CompanyInfo.

## <a name="example-2"></a>Przykład 2

Funkcja `DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` zwraca wartość daty/godziny **11/12/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)
