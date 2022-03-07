---
title: GETENUMVALUEBYNAME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETENUMVALUEBYNAME w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 09/23/2020
ms.topic: article
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
ms.openlocfilehash: bfc173130a9fc57385826f77443ec28946ef68fd
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570597"
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

## <a name="example-1"></a>Przykład 1

Na poniższej ilustracji wartość stałotekstowa **ReportDirection** została wprowadzona do modelu danych. Zauważ, że etykiety są zdefiniowane dla wartości wyliczenia.

![Dostępne wartości dla wyliczenia modelu danych](./media/ER-data-model-enumeration-values.PNG)

Na ilustracji przedstawiono następujące szczegóły:

- Źródło danych **$Direction** jest skonfigurowane w raporcie ER. To źródło danych jest skonfigurowane na podstawie wyliczenia modelu **ReportDirection**.
- Wyrażenie `$IsArrivals` jest zaprojektowane tak, aby używało źródła danych **$Direction** opartego na wyliczeniu modelu jako parametru tej funkcji.
- Wartością tego wyrażenia porównania jest **TRUE**.

![Przykład wyliczenia modelu danych](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>Przykład 2

Funkcje `GETENUMVALUEBYNAME` i [`LISTOFFIELDS`](er-functions-list-listoffields.md) umożliwiają pobieranie wartości i etykiet obsługiwanych wyliczeń jako wartości tekstowe. (Obsługiwane wyliczenia to wyliczenia aplikacji, wyliczenia modeli danych i wyliczenia formatów.)

Na poniższej ilustracji źródło danych **TransType** zostało wprowadzone w odwzorowaniu modelu. To źródło danych odwołuje się do wyliczenia aplikacji **LedgerTransType**.

![Źródło danych mapowania modelu, które odwołuje się do wyliczenia aplikacji](./media/er-functions-text-getenumvaluebyname-example2-1.png)

Na poniższej ilustracji przedstawiono źródło danych **TransTypeList** skonfigurowane w odwzorowaniu modelu. To źródło danych jest skonfigurowane na podstawie wyliczenia aplikacji **TransType**. Funkcja `LISTOFFIELDS` służy do zwracania wszystkich wartości wyliczenia jako listy rekordów zawierających pola. W ten sposób szczegóły wszystkich wartości wyliczenia są ujawniane.

> [!NOTE]
> Pole **EnumValue** jest skonfigurowane dla źródła danych **TransTypeList** za pomocą wyrażenia `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`. To pole zwraca wartość wyliczenia dla każdego rekordu na liście.

![Źródło danych mapowania modelu, które zwraca wszystkie wartości wyliczenia wybranego wyliczenia jako listę rekordów](./media/er-functions-text-getenumvaluebyname-example2-2.png)

Na poniższej ilustracji przedstawiono źródło danych **VendTrans** skonfigurowane w odwzorowaniu modelu. To źródło danych zwraca rekordy transakcji dostawcy z tabeli aplikacji **VendTrans**. Typ księgi każdej transakcji jest określony przez wartość pola **VendTrans**.

> [!NOTE]
> Pole **TransTypeTitle** jest skonfigurowane dla źródła danych **VendTrans** za pomocą wyrażenia `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`. To pole zwraca etykietę wartości wyliczenia bieżącej transakcji jako tekst, jeśli ta wartość jest dostępna. W przeciwnym razie zwraca pustą wartość ciągu.
>
> Pole **TransTypeTitle** jest powiązane z polem **LedgerType** modelu danych, które umożliwia używanie tych informacji w każdym formacie ER, który używa modelu danych jako źródła danych.

![Źródło danych mapowania modelu, które zwraca transakcje dostawcy](./media/er-functions-text-getenumvaluebyname-example2-3.png)

Na poniższej ilustracji przedstawiono sposób użycia [debugera źródła danych](er-debug-data-sources.md) do testowania skonfigurowanego mapowania modelu.

![Użycie debugera źródła danych do testowania skonfigurowanego mapowania modelu](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

Pole **LedgerType** model danych udostępnia etykiety typów transakcji zgodnie z oczekiwaniami.

Jeśli to rozwiązanie ma być używane w przypadku dużej ilości danych transakcyjnych, należy wziąć pod uwagę wydajność wykonania. Aby uzyskać więcej informacji, zobacz [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)

[Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)

[LISTOFFIELDS, funkcja ER](er-functions-list-listoffields.md)

[FIRSTORNULL, funkcja ER](er-functions-list-firstornull.md)

[WHERE, funkcja ER](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]