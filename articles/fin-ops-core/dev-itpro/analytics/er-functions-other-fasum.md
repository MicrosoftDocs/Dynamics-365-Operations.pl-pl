---
title: FA_SUM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FA_SUM w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744302"
---
# <a name="fa_sum-er-function"></a>FA_SUM, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `FA_SUM` zwraca wartość *Kontener (rekord)*, która składa się z danych dla kwot składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji i zakresu dat.

## <a name="syntax"></a>Składnia

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>Argumenty

`fixed asset code`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kod elementu składnika majątku, dla którego jest obliczane saldo.

`value model code`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kod modelu wartości, dla którego jest obliczane saldo.

`start date`: *Data*

Wartość typu *Data* reprezentująca datę początkową okresu, dla którego są obliczane kwoty składników majątku.

`end date`: *Data*

Wartość typu *Data* reprezentująca datę końcową okresu, dla którego są obliczane kwoty składników majątku.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="example"></a>Przykład

Funkcja `FA_SUM ("COMP-000001", "Current", Date1, Date2)` zwraca kontener danych dla składnika majątku **COMP-000001** przygotowanego dla modelu ewidencji **Bieżące** i przez okres od **Data1** do **Data2**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]