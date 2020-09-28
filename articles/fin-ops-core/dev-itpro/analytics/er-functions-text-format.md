---
title: FORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FORMAT w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f3e8e5f6676c26b8d604ed950470463f04c0473
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743886"
---
# <a name="format-er-function"></a>FORMAT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `FORMAT` zwraca określoną wartość typu *Ciąg* po jej sformatowaniu przez zastąpienie wszystkich wystąpień elementu **%N** *N*-tym argumentem.

## <a name="syntax"></a>Składnia

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Argumenty

`string`: *Ciąg*

Odwołanie do źródła danych typu *Ciąg*, które musi zostać sformatowany. Ten argument jest wymagany.

`argument 1`: *Ciąg*

Pierwszy argument, który jest używany do zastępowania wystąpień **%1**. Ten argument jest wymagany.

`argument N`: *Ciąg*

*N*-ty argument, który jest używany do zastępowania wystąpień **%2**, **%3** itd. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Jeśli dla parametru nie podano argumentu, parametr jest zwracany w ciągu jako **"%N"**. Dla wartości typu *Rzeczywista* domyślna konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.

## <a name="example"></a>Przykład

Na poniższej ilustracji źródło danych **PaymentModel** zwraca listę rekordów klientów przy użyciu składnika **Klient**. Zwraca wartość daty przetwarzania przy użyciu pola **ProcessingDate**.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

W formacie raportowania elektronicznego (ER) przeznaczonym do generowania pliku elektronicznego dla wybranych klientów **PaymentModel** jest wybrane jako źródło danych i kontroluje przebieg procesu. Jeśli wybrany klient jest zablokowany w dniu generowania raportu, następuje zgłoszenie wyjątku w celu powiadomienia użytkownika. Formuła przeznaczona dla tego typu kontroli przetwarzania może skorzystać z poniższych zasobów:

- Etykieta SYS70894, która ma następujący tekst:

    - **W języku polskim:** „Nie ma nic do wydrukowania”
    - **W języku niemieckim:** „Nichts zu drucken”

- Etykieta SYS18389, która ma następujący tekst:

    - **W języku polskim:** „Klient %1 jest zablokowany do %2”.
    - **W języku niemieckim:** „Debitor '„%1” wird für %2 gesperrt”.

Poniżej przedstawiono wyrażenie, które można zaprojektować.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Jeśli raport jest przetwarzany dla odbiorcy **Litware Retail** w dniu 17 grudnia 2015 r. w kulturze **PL** i języku **PL**, formuła zwraca następujący tekst, który może być prezentowany użytkownikowi jako komunikat o wyjątku:

*Nie ma nic do wydrukowania. Odbiorca Litware Retail jest zablokowany do 17.12.2015.*

Jeśli ten sam raport będzie przetwarzany dla odbiorcy **Litware Retail** w dniu 17 grudnia 2015 w języku **DE** i kulturze **DE**, formuła zwraca następujący tekst:

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> W formułach raportowania elektronicznego dla etykiet jest stosowana następująca składnia:
>
> - **Etykiety aplikacji Microsoft Dynamics 365 Finance:** **\@X**, gdzie **X** oznacza identyfikator etykiety w drzewie obiektów aplikacji (AOT)
> - **Etykiety, które znajdują się w konfiguracjach ER:** **@"GER_LABEL:X"**, gdzie **X** oznacza identyfikator etykiety w konfiguracji raportowania elektronicznego

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
