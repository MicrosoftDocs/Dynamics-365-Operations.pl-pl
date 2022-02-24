---
title: Base64StringToContainer, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji Base64StringToContainer w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e92ae41a3e0f03cb14d4791ab768f096f2a0523
ms.sourcegitcommit: e8a46e127d70986539c138b27a641bff6f6874d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2020
ms.locfileid: "4739104"
---
# <a name="base64stringtocontainer-er-function"></a>Base64StringToContainer, funkcja ER

[!include [banner](../includes/banner.md)]

[Funkcja](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *[Kontener](er-functions-category-container.md)*.

## <a name="syntax"></a>Składnia

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

## <a name="return-values"></a>Wartości zwracane

*Kontener*

Wynikowa wartość binarna w formacie binarnym large object (BLOB).

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wyjątek „Parametr jest nieprawidłowy” występuje, jeśli ciąg wejściowy nie dostarcza prawidłowej grupy Base64 schematów kodowania binarnego na tekst.

## <a name="example"></a>Przykład

Definiuje się następujące źródła danych w mapowaniu modelu:

- Główne źródło danych **DocuTypeGroupEnum** typu *Dynamics 365 for Operations /Wyliczenie*, które odwołuje się do wyliczenia aplikacji **DocuTypeGroup**
- Główne źródło danych **Klient** typu *Dynamics 365 for Operations / rekordy tabeli* odwołujące się do tabeli aplikacji **CustTable**
- Źródło **\#Multimedia** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:

    - Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient**.
    - Zawiera wyrażenie `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- Źródło **\#MediaAsBase64String** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:

    - Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient.'\#Multimedia**.
    - Zawiera wyrażenie `Customer.'#Media'.'getFileContentAsBase64String()'`.

- Źródło **\#BlobFomBase64** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:

    - Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient.'\#Multimedia**.
    - Zawiera wyrażenie `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.

W tym przykładzie źródło danych **\#MediaAsBase64String** koduje zawartość binarną bieżącego załącznika multimediów jako tekst reprezentujący grupę Base64 schematów kodowania binarnego na tekst. Źródło danych **\#BlobFomBase64** dekoduje ciąg Base64 i zwraca wartość binarną w formacie obiektu BLOB.

![Przykładowe źródła danych na stronie projektanta mapowania modelu ER](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje kontenera](er-functions-category-container.md)
