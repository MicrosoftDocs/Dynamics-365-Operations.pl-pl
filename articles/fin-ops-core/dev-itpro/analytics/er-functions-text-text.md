---
title: TEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: d489da24d0589549153913bbc6db699e3c217e72
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682902"
---
# <a name="text-er-function"></a>TEXT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `TEXT` zwraca określoną liczbę jako wartość typu *Ciąg* po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia aplikacji.

## <a name="syntax"></a>Składnia

```vb
TEXT (number)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba całkowita* lub *Liczba rzeczywista*

Wartość numeryczna, która musi zostać przekonwertowana na ciąg tekstowy.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Dla wartości typu *Liczba rzeczywista* konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.

## <a name="example"></a>Przykład

Jeśli ustawienia regionalne serwera wystąpienia aplikacji Microsoft Dynamics 365 Finance są określone jako **EN-US**, funkcja `TEXT (NOW ())` zwraca datę bieżącej sesji aplikacji, 17 grudnia 2015 roku, jako ciąg tekstowy **"12/17/2015 07:59:23 AM"**. Funkcja `TEXT (1/3)` zwraca wartość **"0.33"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]