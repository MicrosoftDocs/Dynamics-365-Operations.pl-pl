---
title: CONVERTCURRENCY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONVERTCURRENCY w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 0f0d5bace9b62cf6f0d7576744a6cc271666bf73
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567647"
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