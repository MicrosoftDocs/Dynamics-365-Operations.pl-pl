---
title: "Opóźnienia"
description: "Ten artykuł zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9113c7728c5d23b70e3809bab31136aff63c6acf
ms.lasthandoff: 03/31/2017


---

# <a name="delays"></a>Opóźnienia

Ten artykuł zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.

Planowanie główne pozwala obliczać najwcześniejszą datę realizacji transakcji na podstawie czasów realizacji, dostępności materiałów, dostępności zdolności produkcyjnych i różnych parametrów planowania. 

Jeżeli funkcja planowania głównego obliczy datę zamówienia, która będzie wcześniejsza niż data bieżąca, zamówienia nie da się zrealizować w terminie. Takie zamówienie jest opóźnione. W takim przypadku planowanie główne planuje zamówienie w przyszłość od daty bieżącej i uwzględnia czasy realizacji. Te czasy realizacji zaczynają się od dowolnego składnika niższego poziomu. Następnie zamówienie otrzymuje datę opóźnienia. Data opóźnienia jest realistyczną datą realizacji obliczaną na podstawie bieżących danych. Planowanie główne oblicza również liczbę dni opóźnienia. 

W niektórych przypadkach można wybrać, by nie do obliczać opóźnienia, np. kiedy wiadomo, że czas realizacji można przyspieszyć, wybierając alternatywne metody dostawy. 

Można skonfigurować sposób obliczania opóźnienia dla grupy zapotrzebowania. Następnie można dołączyć grupę zaopatrzenia do towaru później. 

Na stronie **Parametry planowania głównego** można ustawić czas rozpoczęcia dla obliczania opóźnień. Jeżeli zamówienie zostało zamknięte po tym czasie, do daty opóźnienia zamówienia dodawany jest jeden dzień opóźnienia. 

**Uwaga:** w starszych wersjach, obliczone opóźnienia były znane jako *komunikatów prognoz*, Opóźniona data był znany jako *daty prognozy*, i opóźnionego transakcja została przekazana jako *transakcji, która została zestaw przyszłych*.

<a name="see-also"></a>Informacje dodatkowe
--------

[Ustawienia zapotrzebowania](coverage-settings.md)


