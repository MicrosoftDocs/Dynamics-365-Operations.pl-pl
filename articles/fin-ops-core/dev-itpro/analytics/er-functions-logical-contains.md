---
title: Funkcje CONTAINS ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONTAINS w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557545"
---
# <a name="contains-er-function"></a>Funkcje CONTAINS ER

[!include [banner](../includes/banner.md)]

Ta funkcja `CONTAINS` określa, czy określone dane wejściowe zawierają określony tekst. Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe zawierają określony tekst. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.

## <a name="syntax"></a>Składnia

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może zawierać drugi argument.

`search text`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może znajdować się w pierwszym argumencie.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja może służyć do określania wyrażenia warunku funkcji [FILTER](er-functions-list-filter.md) tylko wtedy, gdy odpowiednie mapowanie jest skonfigurowane w [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) w celu uzyskania dostępu do [Microsoft Dataverse](../data-entities/data-integration-cds.md). W przeciwnym razie podczas projektowania zgłaszany jest wyjątek. Odebrany komunikat zaleca użycie funkcji [WHERE](er-functions-list-where.md) zamiast funkcji `FILTER`, ponieważ działa ona sprawniej.

## <a name="example-1"></a>Przykład 1

Wyrażenie zwraca `CONTAINS ("abc", "d")` wartość **FALSE**, podczas gdy wyrażenie zwraca `CONTAINS ("abc", "C")`wartość **TRUE**.

## <a name="example-2"></a>Przykład 2

Wyrażenie `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` zwraca wartość **TRUE**, jeśli wartość w polu **Adres** źródła danych **modelu** zawiera ciąg **DEU**. W przeciwnym jest zwracana wartość **FALSE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)
