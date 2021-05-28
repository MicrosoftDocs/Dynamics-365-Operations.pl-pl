---
title: Funkcja STARTSWITH ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji STARTSWITH w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 50883bb604d2d1f2947545ce27fa02099e70b0e6
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048849"
---
# <a name="startswith-er-function"></a>Funkcja STARTSWITH ER

[!include [banner](../includes/banner.md)]

Funkcja `STARTSWITH` określa, czy określone wejście zaczyna się określonym tekstem. Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe zaczyna się określonym tekstem. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.

## <a name="syntax"></a>Składnia

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może zaczyna się na drugim argumencie.

`start text`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może znajdować się na początku pierwszego argumentu.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja może służyć do określania wyrażenia warunku funkcji [FILTER](er-functions-list-filter.md) tylko wtedy, gdy odpowiednie mapowanie jest skonfigurowane w [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) w celu uzyskania dostępu do [Microsoft Dataverse](/power-platform/admin/data-integrator). W przeciwnym razie podczas projektowania zgłaszany jest wyjątek. Odebrany komunikat zaleca użycie funkcji [WHERE](er-functions-list-where.md) zamiast funkcji `FILTER`, ponieważ działa ona sprawniej.

## <a name="example-1"></a>Przykład 1

Wyrażenie zwraca `STARTSWITH ("abc", "d")` wartość **FALSE**, podczas gdy wyrażenie zwraca `STARTSWITH ("abc", "A")`wartość **TRUE**.

## <a name="example-2"></a>Przykład 2

Wyrażenie `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` zwraca wartość **TRUE**, jeśli wartość w polu **Adres** źródła danych **modelu** zaczyna się ciągiem **123 Coffee Street**. W przeciwnym jest zwracana wartość **FALSE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)
