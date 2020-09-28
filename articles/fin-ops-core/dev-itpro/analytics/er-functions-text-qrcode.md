---
title: QRCODE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji QRCODE w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f634976d83fb4066a953b7ab09c963214415e29b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743765"
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
