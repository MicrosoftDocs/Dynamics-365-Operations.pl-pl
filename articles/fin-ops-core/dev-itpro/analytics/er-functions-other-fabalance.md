---
title: FA_BALANCE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FA_BALANCE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 5570e1295ff6da0eadd7e18143a2206032597ae5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684842"
---
# <a name="fa_balance-er-function"></a>FA_BALANCE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `FA_BALANCE` zwraca wartość *Kontener (rekord)*, która składa się z danych dla salda składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji, roku sprawozdawczego i daty raportowania.

## <a name="syntax"></a>Składnia

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Argumenty

`fixed asset code`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kod elementu składnika majątku, dla którego jest obliczane saldo.

`value model code`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kod modelu wartości, dla którego jest obliczane saldo.

`reporting year`: *Wartość wyliczenia*

Wartość wyliczenia aplikacji **AssetYear** definiujący okres na potrzeby obliczania salda.

`reporting date`: *Data*

Wartość typu *Data* definiująca datę obliczenia salda.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="example"></a>Przykład

Funkcja `FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` zwraca przygotowany kontener sald dla środka trwałego **COMP-000001**, który ma model ewidencji **Bieżący** na dzień bieżącej sesji aplikacji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)
