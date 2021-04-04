---
title: GETCURRENTCOMPANY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETCURRENTCOMPANY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: fcb5ef2f218a85bab25f830db583343504c46e98
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567551"
---
# <a name="getcurrentcompany-er-function"></a>GETCURRENTCOMPANY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `GETCURRENTCOMPANY` zwraca wartość *Ciąg* reprezentującą kod firmy (jednostki prawnej), do której użytkownik jest aktualnie zalogowany.

## <a name="syntax"></a>Składnia

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `GETCURRENTCOMPANY ()` zwraca wartość **USMF** dla użytkownika zalogowanego do firmy **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]