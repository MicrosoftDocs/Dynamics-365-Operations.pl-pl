---
title: Przykłady wyników amortyzacji z cofnięciami
description: W tym artykule opisano potencjalne skutki stornowania transakcji na środkach trwałych.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4952f94d635a9c9cdc7892e6cc142cfe4d526e44
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241217"
---
# <a name="depreciation-effects-with-reversals"></a>Przykłady wyników amortyzacji z cofnięciami

[!include [banner](../includes/banner.md)]

W tym artykule opisano potencjalne skutki stornowania transakcji na środkach trwałych. 

Można cofać transakcje dotyczące środka trwałego oraz transakcje skojarzone ze środkiem trwałym. Można też anulować wycofaną transakcję. 

Można wycofać lub anulować transakcję, która nie jest ostatnią transakcją zaksięgowaną w księdze środka trwałego. Najpierw należy określić, czy po wycofywanej transakcji zostały zaksięgowane jakieś inne transakcje amortyzacji. Jest to spowodowane tym, że amortyzacja nie zostanie ponownie obliczona podczas wycofywania transakcji. Z tego względu często jest zawyżona lub zaniżona po wycofaniu, jak to przedstawiono w przykładach. 

Aby upewnić się, że po wycofaniu transakcji amortyzacja będzie poprawna, nie należy doprowadzać wycofania do końca, jeśli podczas tego procesu pojawi się komunikat informujący o tym, że amortyzacja nie zostanie ponownie wyliczona. Najpierw wycofaj transakcję amortyzacji, którą zaksięgowano po transakcji, którą chcesz wycofać, a dopiero wtedy możesz przejść do wycofania tej transakcji. Nie pojawi się wówczas ostrzeżenie dotyczące ponownego obliczania amortyzacji i można dokończyć wycofywanie. 

W podanych dalej przykładach przedstawiono obliczenia mające miejsce w wypadku, gdy zignorujesz komunikat z ostrzeżeniem i nie wycofasz najpierw transakcji amortyzacji.

## <a name="example-1-depreciation-is-overstated"></a> Przykład 1. Amortyzacja zawyżona
Dla środka trwałego skonfigurowano 5-letni okres użytkowania oraz amortyzację liniową (60 okresów amortyzacji). W tym przykładzie amortyzacja jest zawyżona.
#### <a name="asset-transaction-history"></a>Historia transakcji dotyczących środka trwałego

| Data       | Typ transakcji                                                          | Kwota                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1 stycznia  | Nabycie                                                               | 59 000,00                                 |
| 1 stycznia  | Korekta wartości początkowej                                                    | 1000,00                                  |
| 31 stycznia | Amortyzacja (na podstawie proponowanej amortyzacji dla jednego okresu) | 1,000.00 Obliczenie: wartość księgowa (59,000 + 1,000) / liczba pozostałych okresów amortyzacji (60) |

#### <a name="reversal-action"></a>Akcja wycofania

| Data      | Typ transakcji                | Kwota    |
|-----------|---------------------------------|-----------|
| 1 stycznia | Wycofanie korekty amortyzacji | –1000,00 |

#### <a name="depreciation-effect"></a>Końcowa wartość amortyzacji

| Data        | Typ transakcji        | Kwota                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 28 lutego | Amortyzacja (propozycja) | 983.05 Obliczenie: wartość księgowa (59 000 - amortyzacja 1000) / liczba pozostałych okresów amortyzacji (59) |

Amortyzacja jest zawyżona o 16,95 (1000 - 983,05).

## <a name="example-2-depreciation-is-understated"></a> Przykład 2. Amortyzacja zaniżona
Dla środka trwałego skonfigurowano 5-letni okres użytkowania oraz amortyzację liniową (60 okresów amortyzacji). W tym przykładzie amortyzacja jest zaniżona.
#### <a name="asset-transaction-history"></a>Historia transakcji dotyczących środka trwałego

| Data       | Typ transakcji                                                          | Kwota                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1 stycznia  | Nabycie                                                               | 59 000,00                                   |
| 1 stycznia  | Zmniejszenie wartości                                                     | 1000,00                                    |
| 31 stycznia | Amortyzacja (na podstawie proponowanej amortyzacji dla jednego okresu) | 966.67 Obliczenie: wartość księgowa (59,000 + 1,000) / liczba pozostałych okresów amortyzacji (60) |

#### <a name="reversal-action"></a>Akcja wycofania

| Data      | Typ transakcji               | Kwota    |
|-----------|--------------------------------|-----------|
| 1 stycznia | Zapisanie korekty amortyzacji | –1000,00 |

#### <a name="depreciation-effect"></a>Końcowa wartość amortyzacji

| Data        | Typ transakcji        | Kwota                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 28 lutego | Amortyzacja (propozycja) | 983.62 Obliczenie: wartość księgowa (59 000 - amortyzacja 966,67) / liczba pozostałych okresów amortyzacji (59) |

Amortyzacja jest zaniżona o 16,95 (983,62 – 966,67).



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Amortyzacja środka trwałego](fixed-asset-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]