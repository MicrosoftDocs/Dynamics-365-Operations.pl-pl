---
title: Funkcja REPEAT ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji REPEAT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220696"
---
# <a name="repeat-er-function"></a>Funkcja REPEAT ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ta funkcja `REPEAT` tworzy rekord zawierający pole, które ma wartość taką, która odpowiada określonym wartościom wejściowym. Następnie zwraca nową *listę rekordów* rekordu, która jest powtarzana określoną liczbę razy.

## <a name="syntax"></a>Składnia

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Argumenty

`item`: Dowolny obsługiwany pierwotny [lub](er-formula-supported-data-types-primitive.md) złożony [typ](er-formula-supported-data-types-composite.md) danych

Wartość do powtórzenia.

`number`: *Liczba całkowita*

Liczba powtórzeń.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Zwracana lista powtarzających się rekordów udostępnia następujące pola:

- Określ wartość (pole `Item`)
- Indeks bieżącego rekordu (pole `Number`)

> [!NOTE]
> Ponieważ dla tej funkcji jest używana numeracja oparta na jedynce, pole `Number` ma wartość **1** dla pierwszego rekordu listy wynikowej.

Ta funkcja umożliwia [pomnożenie istniejących danych, co umożliwia testowanie wydajności i objętości rozwiązań raportowania elektronicznego (ER)](general-electronic-reporting.md) za pomocą narzędzia [Regression suite automation (RSAT)](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Przykład

Aby wygenerować dokument w formacie XML `Party`, który musi zawierać tyle elementów XML, ile określono w polu wprowadzania danych w oknie dialogowym w czasie wykonywania, przed rozpoczęciem wykonywania formatu ER.

Na ilustracji poniżej widać [format](er-overview-components.md#format-component) ER. W tym formacie dodawany jest pojedynczy element XML `Party`, aby uwidocznić właściwości jednej strony.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

Na następnej ilustracji przedstawiono skonfigurowane źródła danych:

- Źródło danych `Party` reprezentujące jedną stronę. To pole `Party.Value` służy do uwidaczniania pojedynczej wartości tekstowej.
- Źródło [danych](er-user-input-parameter-data-sources.md) `NumberOfRepeats` używane do oferty pola wprowadzania danych w oknie dialogowym w czasie wykonywania, dzięki czemu można określić liczbę stron, które powinny zostać wprowadzone w generowanym dokumencie.
- Źródło danych `Party2`, które powtarza rekord `Party`, liczbę razy określoną w źródle danych `NumberOfRepeats`.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

Na następnej ilustracji przedstawiono powiązania danych edytowalnego formatu ER tworzonego w celu generowania danych wyjściowych w formacie XML. Ten wynik przedstawia poszczególne strony jako wyliczone węzły.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

Na poniższej ilustracji pokazano wynik uruchomienia zaprojektowanego formatu i `NumberOfRepeats` wartość źródła danych została określona jako **5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
