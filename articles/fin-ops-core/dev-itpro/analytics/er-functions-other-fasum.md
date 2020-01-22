---
title: FA_SUM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FA_SUM w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32eb07689598a3b6c852f272b480106670b88cd0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916989"
---
# <a name="FA_SUM">FA_SUM, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `FA_SUM` zwraca wartość *Kontener (rekord)*, która składa się z danych dla kwot składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji i zakresu dat.

## <a name="syntax"></a>Składnia

```
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
