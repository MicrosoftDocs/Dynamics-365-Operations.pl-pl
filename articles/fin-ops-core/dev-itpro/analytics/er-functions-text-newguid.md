---
title: NEWGUID, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji NEWGUID w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 381dbcbe816c189c1966ffe962020d5aa2b1f3eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274781"
---
# <a name="newguid-er-function"></a>NEWGUID, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NEWGUID` generuje nowy unikatowy identyfikator globalny (GUID) i zwraca go jako wartość identyfikatora *[GUID](er-formula-supported-data-types-primitive.md#guid)*.

## <a name="syntax"></a>Składnia

```vb
NEWGUID ()
```

## <a name="return-values"></a>Wartości zwracane

*GUID*

Wyjściowa wartość identyfikatora GUID.

## <a name="example"></a>Przykład

Funkcja `NEWGUID()` zawsze zwraca nową wartość identyfikatora *GUID*, na przykład **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
