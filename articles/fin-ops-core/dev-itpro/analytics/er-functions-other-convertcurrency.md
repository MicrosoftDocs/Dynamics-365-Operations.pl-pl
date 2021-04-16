---
title: CONVERTCURRENCY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONVERTCURRENCY w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: fb8f7f28f5a9bb27402544efcffa6393238e38d8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744374"
---
# <a name="convertcurrency-er-function"></a>CONVERTCURRENCY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `CONVERTCURRENCY` zwraca wartość *rzeczywistą*, która reprezentuje wynik konwertowania określonej kwoty pieniężnej ze wskazanej waluty źródłowej na określoną walutę docelową przy użyciu ustawień określonej firmy na określony dzień.

## <a name="syntax"></a>Składnia

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Argumenty

`amount`: *Liczba całkowita* lub *Liczba rzeczywista*

Wartość liczbowa, która reprezentuje kwotę pieniężną do przekonwertowania.

`source currency`: *Ciąg*

Kod waluty źródłowej.

`target currency`: *Ciąg*

Kod waluty docelowej.

`date`: *Data*

Wartość typu *Data* reprezentująca datę, która jest używana do określania kursu wymiany na potrzeby konwersji.

`company`: *Ciąg*

Wartość typu *Ciąg*, która reprezentuje kod firmy dostarczającej ustawienia używane do konwersji.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="example"></a>Przykład

Funkcja `CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` zwraca równoważność jednego euro w dolarach amerykańskich w dniu bieżącej sesji na podstawie ustawień dla firmy **DEMF**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]