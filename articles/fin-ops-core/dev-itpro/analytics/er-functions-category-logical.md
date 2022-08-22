---
title: Lista funkcji modułu ER w kategorii funkcji logicznych
description: Ten artykuł zawiera ogólne informacje o funkcjach logicznych obsługiwanych w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 1d011968d9cfa4125e7283ca36c3558e3e79b93a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291303"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Lista funkcji modułu ER w kategorii funkcji logicznych

[!include [banner](../includes/banner.md)]

Funkcje logiczne w module raportowania elektronicznego (ER) mogą służyć do pracy z wartościami logicznymi w celu wykonania więcej niż jednego porównania w pojedynczym wyrażeniu lub przetestowania wielu warunków. Ten artykuł zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [i](er-functions-logical-and.md)                       | Ta funkcja zwraca wartość *logiczną* **TRUE**, jeśli wszystkie wybrane warunki zostaną spełnione. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [Skrzynka](er-functions-logical-case.md)                     | Ta funkcja oblicza wartość określonego wyrażenia względem określonych alternatywnych opcji i zwraca wynik pierwszej opcji, która jest równa wartości określonego wyrażenia. W przeciwnym razie zwraca ona domyślny wynik opcjonalny, jeśli domyślny wynik jest określony jako ostatni argument wywołanej funkcji, który nie jest poprzedzony opcją. Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych. |
| [Zawiera](er-functions-logical-contains.md)             | Ta funkcja określa, czy określone dane wejściowe zawierają określony tekst. Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe zawierają określony tekst. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [Endswith](er-functions-logical-endswith.md)             | Ta funkcja określa, czy określone wejście kończy się określonym tekstem. Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe kończą się określonym tekstem. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [Jeśli](er-functions-logical-if.md)                         | Ta funkcja zwraca pierwszą określoną wartość, jeśli jest spełniony podany warunek. W przeciwnym razie zwraca ona drugą określoną wartość. Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych. |
| [Nie](er-functions-logical-not.md)                       | Ta funkcja zwraca odwróconą wartość logiczną określonego warunku jako wartość *logiczną*. |
| [Or](er-functions-logical-or.md)                         | Ta funkcja zwraca wartość *logiczną* **FALSE**, jeśli żadne wybrane warunki nie zostały spełnione. Jeśli dowolny wybrany warunek został spełniony, ta funkcja zwraca wartość *logiczną* **TRUE**. |
| [Startswith](er-functions-logical-startswith.md)         | Ta funkcja określa, czy określone wejście zaczyna się określonym tekstem. Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe zaczyna się określonym tekstem. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Ta funkcja określa, czy podane dane wejściowe pasują do którejkolwiek wartości określonego elementu na podanej liście. Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Ta funkcja określa, czy podane dane wejściowe typu *Int64* lub *Integer* pasują do którejkolwiek wartości określonego elementu na podanej liście. Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |


## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
