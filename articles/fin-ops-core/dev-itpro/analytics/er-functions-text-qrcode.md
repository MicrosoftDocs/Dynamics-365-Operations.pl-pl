---
title: QRCODE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji QRCODE w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 9de62eefb82942ccc72e81bd9bf36eed07c99dba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287197"
---
# <a name="qrcode-er-function"></a>QRCODE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `QRCODE` zwraca wartość typu *Kontener*, która przedstawia obraz kodu szybkiej odpowiedzi (kod QR) dla określonego ciągu w formacie binarnym.

## <a name="syntax"></a>Składnia

```vb
QRCODE (text)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość *ciągu* reprezentująca oryginalny tekst.

## <a name="return-values"></a>Wartości zwracane

*Kontener*

Wynikowy strumień binarny.

## <a name="example"></a>Przykład

Można skonfigurować format modułu Raportowanie elektroniczne (ER) do generowania dokumentu wychodzącego w formacie pakietu Microsoft Office (skoroszyty programu Excel lub dokumenty programu Word) przy użyciu wstępnie zdefiniowanego szablonu. Ten szablon może zawierać obiekt **Obraz** (skoroszyt programu Excel) lub **kontrolkę zawartości obrazu** (dokument programu Word) jako symbol zastępczy obrazu kodu QR. Musisz dodać do skonfigurowanego formatu ER element **Komórka**, który będzie używany do wypełnienia tego symbolu zastępczego. Aby określić, jakie informacje będą przechowywane w kodzie QR, należy zdefiniować powiązanie dla tego elementu **Komórka**. Na przykład można skonfigurować takie powiązanie jako zawierające następujące wyrażenie:

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

Po uruchomieniu skonfigurowanego formatu ER wartość tekstowa pola **LabelText** źródła danych **model.ListOfShelfLabels** będzie używana do generowania obrazu kodu QR. Ten obraz zastąpi symbol zastępczy obrazu kodu QR w szablonie dokumentu używanym do wygenerowania dokumentu wychodzącego. Po zeskanowaniu tego obrazu wygenerowanego dokumentu jest zwracany tekst pobrany z pola **LabelText** źródła danych **model.ListOfShelfLabels**. Aby uzyskać więcej informacji, zobacz [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
