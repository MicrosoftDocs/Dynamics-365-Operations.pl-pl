---
title: Lista funkcji modułu ER w kategorii kontenerów
description: Ten artykuł zawiera ogólne informacje o funkcjach kontenerów obsługiwanych w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: f07c3645f824fc2fe8ca156c8cf06840e993a9a5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282660"
---
# <a name="list-of-er-functions-in-the-container-category"></a>Lista funkcji modułu ER w kategorii kontenerów

[!include [banner](../includes/banner.md)]

[Funkcje](er-formula-language.md#Functions) kontenerów [raportowania elektronicznego (ER)](general-electronic-reporting.md) mogą służyć do wykonywania operacji na źródłach danych o typie danych *Kontener*. Te operacje są wykonywane, gdy dane przetwarzania reprezentują kolekcję danych binarnych w formacie binarnego dużego obiektu (BLOB). Ten artykuł zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | opis |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | Ta funkcja zwraca wartość *kontenera*, która zawiera zawartość binarną, która jest dekodowana z określonego ciągu ASCII, reprezentującego grupę Base64 schematów kodowania binarnego do tekstu. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
