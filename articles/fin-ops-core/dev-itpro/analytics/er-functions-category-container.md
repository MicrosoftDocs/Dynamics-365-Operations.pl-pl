---
title: Lista funkcji modułu ER w kategorii kontenerów
description: Ten artykuł zawiera ogólne informacje o funkcjach kontenerów obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5c86b0ae6cbf4ac6515491b55390d42c371eae4b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883825"
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
