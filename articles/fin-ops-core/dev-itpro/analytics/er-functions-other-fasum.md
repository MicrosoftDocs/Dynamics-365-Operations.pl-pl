---
title: FA_SUM, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji FA_SUM w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: bcedbc3df835b219b8df6d05f1db6b331f1e9254
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278926"
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
