---
title: Lista funkcji modułu ER w kategorii kolekcji danych
description: Ten artykuł zawiera ogólne informacje o funkcjach kolekcji danych obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: a8d4f5068bedcf1f15ae5257e29004a4773ef84c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908569"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Lista funkcji modułu ER w kategorii kolekcji danych

[!include [banner](../includes/banner.md)]

Funkcje kolekcji danych w module Raportowanie elektroniczne (ER) służą do zliczania i sumowania w uruchamianym formacie ER na podstawie danych wyjściowych, które zostały już wygenerowane w formacie **Tekst** lub **XML**. To podejście umożliwia poprawę wydajności uruchamianego formatu ER w celu wprowadzenia wartości sum bieżących w wygenerowanych dokumentach i dla innych celów. Ten artykuł zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Ta funkcja zwraca wartość typu *Lista rekordów*, która zawiera listę wartości zwróconych przez właściwość **Zebrane dane wartości klucza** elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza. |
| [CountIF](er-functions-datacollection-countif.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek. Warunek składa się z zakresu kluczy i wartości klucza. |
| [CountIFs](er-functions-datacollection-countifs.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Ta funkcja zwraca wartość typu *Ciąg* reprezentującą nazwę bieżącego elementu formatu ER. |
| [SumIF](er-functions-datacollection-sumif.md) | Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek. Warunek składa się z zakresu kluczy i wartości klucza. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]