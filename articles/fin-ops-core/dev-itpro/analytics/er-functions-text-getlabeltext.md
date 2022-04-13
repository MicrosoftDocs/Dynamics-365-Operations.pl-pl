---
title: GETLABELTEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETLABELTEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 03/18/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 2ce66c9410abeee16bbd074204262edf79bf6d68
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462419"
---
# <a name="getlabeltext-er-function"></a>GETLABELTEXT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `GETLABELTEXT` wyszukuje określoną etykietę w celu zwrócenia wartości *[String](er-formula-supported-data-types-primitive.md#string)* reprezentującej tłumaczenie określonej etykiety w określonym języku.

## <a name="syntax"></a>Składnia

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argumenty

### <a name="label-id"></a>Identyfikator etykiety

`label id`: *Ciąg* lub *Identyfikator etykiety*

Poprawny identyfikator jednego z następujących typów etykiet:

- Etykieta [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- Etykieta Microsoft Dynamics 365 Finance

#### <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ten argument może być zdefiniowany tylko jako stała, przez użycie jednego z następujących obsługiwanych wzorców:

- Dla etykiet ER:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Dla etykiet Finance:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> W czasie projektowania na stronie **[Projektanta formuł](er-advanced-formula-editor.md)** wyświetlany jest komunikat o błędzie walidacji, jeśli nie można znaleźć żadnej etykiety przy użyciu podanego identyfikatora etykiety.

### <a name="language"></a>Język

`language`: *Ciąg*

Ciąg, który reprezentuje kod języka.

#### <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ten argument może być zdefiniowany jako stała tekstowa lub jako ścieżka do pola źródła danych, które zwraca wartość *Ciąg*.

> [!NOTE]
> W czasie projektowania wyświetlany jest komunikat o błędzie weryfikacji, jeśli nie można znaleźć kodu języka przy użyciu podanego argumentu `language`, gdy został on zdefiniowany jako stała tekstowa.
>
> W trybie uruchomieniowym, tłumaczenie dla języka systemowego `EN-US` jest zwracane dla podanej etykiety, jeśli nie znaleziono kodu języka za pomocą podanego argumentu `language`.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example-1-system-label"></a><a name=example-1></a>Przykład 1: etykieta systemowa

Wyrażenia `GETLABELTEXT (@"SYS70894", "en-us")` i `GETLABELTEXT ("SYS70894", "en-us")` zwracają return angielskie tłumaczenie „Nothing to print” dla etykiety aplikacji `@SYS70894`.

## <a name="example-2-er-label"></a><a name=example-2></a>Przykład 2: etykieta ER

Rozpoczynasz edycję [konfiguracji](general-electronic-reporting.md#Configuration) ER, która została [wyprowadzona](er-quick-start2-customize-report.md#DeriveProvidedFormat) konfiguracji **Komunikaty o przelewach ISO20022 (DE)**, wprowadzasz nowe źródło danych typu *[Pole kalkulowane](er-calculated-field-ds-performance.md)* i konfigurujesz wyrażenie `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` dla tego źródła danych. W tym przypadku źródło danych zwraca w trybie uruchomieniowe niemieckie tłumaczenie „Kreditorenname” dla etykiety ER `@GER_LABEL:VendorName`, która została pierwotnie skonfigurowana w bazowej konfiguracji **Transfer kredytowy ISO20022 (DE)** ER.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)

[Projektowanie raportów wielojęzycznych w module raportowanie elektroniczne](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
