---
title: LISTOFFIELDS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTOFFIELDS w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 1d8d9f41d6ee5256f560c83486c95ecd47f5b081
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686519"
---
# <a name="listoffields-er-function"></a>LISTOFFIELDS, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `LISTOFFIELDS` zwraca wartość typu *Lista rekordów*, która jest tworzona na podstawie struktury określonego argumentu typu *Wyliczenie* lub *Kontener (rekord)*.

## <a name="syntax-1"></a>Składnia 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Składnia 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Argumenty

`path`: odwołanie do źródła danych

Prawidłowa ścieżka odwołania źródła danych jednego z następujących typów danych:

- Wyliczenie modeli
- Wyliczenie formatów
- Wyliczenie aplikacji
- Kontener (rekord)

`language`: *Ciąg*

Tekst, który reprezentuje kod języka.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Utworzona lista składa się z rekordów zawierających następujące pola:

- **Nazwa** (typ danych *Ciąg*)
- **Etykieta** (typ danych *Ciąg*)
- **Opis** (typ danych *Ciąg*)
- **Przetłumaczone** (typ danych *Wartość logiczna*)

Jeśli argument `path` odwołuje się do źródła danych typu *Kontener (rekord)*, dla każdego przywołanego pola rekordu kontenera do utworzonej listy dodawany jest nowy rekord. Dla każdego utworzonego rekordu pole **nazwa** zwraca nazwę pola przywołanego rekordu kontenera, dla którego utworzono bieżący rekord.

Jeśli argument `path` odwołuje się do źródła danych jednego z typów *Wyliczenie*, dla każdej wartości przywołanego wyliczenia do utworzonej listy dodawany jest nowy rekord. Dla każdego utworzonego rekordu pole **Nazwa** zwraca wartość przywołanego wyliczenia, dla którego utworzono bieżący rekord, pole **Opis** zwraca opis tego wyliczenia, a pole **Etykieta** — jego etykietę.

W czasie wykonywania, gdy jest używana składnia 1, pola **Etykieta** i **Opis** muszą zwracać wartości, które są oparte na ustawieniach językowych uruchomionego formatu modułu Raportowanie elektroniczne (ER):

- Jeśli etykiety i opisy dla żądanego języka są dostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na tym języku, a pole **Przetłumaczone** zwraca wartość **True**.
- Jeśli etykiety i opisy dla żądanego języka są niedostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na domyślnym języku **EN-US**, a pole **Przetłumaczone** zwraca wartość **False**.

W czasie wykonywania, gdy jest używana składnia 2, pola **Etykieta** i **Opis** muszą zwracać wartości, które są oparte na języku zdefiniowanym jako drugi argument wywołanej funkcji:

- Jeśli etykiety i opisy dla żądanego języka są dostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na tym języku, a pole **Przetłumaczone** zwraca wartość **True**.
- Jeśli etykiety i opisy dla żądanego języka są niedostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na języku **EN-US**, a pole **Przetłumaczone** zwraca wartość **False**.

## <a name="example-1"></a>Przykład 1

Na poniższej ilustracji wyliczenie zostało wprowadzone do modelu danych ER.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

Na ilustracji przedstawiono następujące szczegóły:

- Wartość stałotekstowa modelu wstawiona do raportu jako źródło danych.
- W wyrażeniu ER wyliczenie modelu jest używane jako parametr funkcji `LISTOFFIELDS`.
- Źródło danych typu *Lista rekordów* jest wstawiane do raportu przy użyciu utworzonego wyrażenia ER.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

W poniższym przykładzie pokazano elementy formatu ER, które są powiązane ze źródłem danych typu *Lista rekordów* utworzonym przy użyciu funkcji `LISTOFFIELDS`.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> Zgodnie z ustawieniami języka nadrzędnych elementów formatu **PLIK** i **FOLDER** przetłumaczone teksty etykiet i opisów są wprowadzane do danych wyjściowych formatu ER.

## <a name="example-2"></a>Przykład 2

Typ źródła danych *Pole obliczeniowe* jest używane do konfigurowania źródeł danych **enumType\_de** i **enumType\_deCH** dla wyliczenia modelu danych **enumType**:

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

W tym przypadku można użyć następującego wyrażenia, aby otrzymać etykietę wyliczenia w języku niemieckim (Szwajcaria), jeśli takie tłumaczenie jest dostępne. Jeśli tłumaczenie na język niemiecki (Szwajcaria) nie jest dostępne, etykieta pozostaje w języku niemieckim.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
