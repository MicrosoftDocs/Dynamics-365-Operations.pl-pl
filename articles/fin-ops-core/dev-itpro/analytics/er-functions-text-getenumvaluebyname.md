---
title: GETENUMVALUEBYNAME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETENUMVALUEBYNAME w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 33ccf358dc5355cd00d5ff41ebd8148a334cba38
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743862"
---
# <a name="getenumvaluebyname-er-function"></a>GETENUMVALUEBYNAME, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `GETENUMVALUEBYNAME` wyszukuje określoną wartość *wyliczenia* w źródle danych określonego wyliczenia przy użyciu nazwy wyliczenia, która jest określona jako wartość typu *Ciąg*. W przypadku znalezienia wartości typu *Wyliczenie* funkcja zwraca tę wartość. W przeciwnym razie funkcja zwraca wartość **null** wyliczenia.

## <a name="syntax"></a>Składnia

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argumenty

`enumeration data source path`: *Wyliczenie*

Prawidłowa ścieżka źródła danych jednego z następujących typów wyliczenia:

- Wyliczanie modelu raportowania elektronicznego (ER)
- Wyliczenie formatu ER
- Wyliczenie aplikacji Microsoft Dynamics 365 Finance

`enumeration value text`: *Ciąg*

Wartość ciągu, która reprezentuje nazwę pojedynczej wartości wyliczenia.

## <a name="return-values"></a>Wartości zwracane

*Wyliczenie* z dopuszczalną wartością null

Wyjściowa wartość wyliczenia.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wyjątek nie jest zgłaszany, jeśli wartość *wyliczenia* nie zostanie znaleziona przy użyciu nazwy wartości wyliczenia określonej jako wartość typu *Ciąg*.

## <a name="example"></a>Przykład

Na poniższej ilustracji wartość stałotekstowa **ReportDirection** została wprowadzona do modelu danych. Zauważ, że etykiety są zdefiniowane dla wartości wyliczenia.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Na ilustracji przedstawiono następujące szczegóły:

- Źródło danych **$Direction** jest skonfigurowane w raporcie ER. To źródło danych jest skonfigurowane na podstawie wyliczenia modelu **ReportDirection**.
- Wyrażenie `$IsArrivals` jest zaprojektowane tak, aby używało źródła danych **$Direction** opartego na wyliczeniu modelu jako parametru tej funkcji.
- Wartością tego wyrażenia porównania jest **TRUE**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
