---
title: "Opóźnienia"
description: "Ten artykuł zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fed78a7eba16d286a81b1e9ad709142422298c91
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="delays"></a>Opóźnienia

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.

Planowanie główne pozwala obliczać najwcześniejszą datę realizacji transakcji na podstawie czasów realizacji, dostępności materiałów, dostępności zdolności produkcyjnych i różnych parametrów planowania. 

Jeżeli funkcja planowania głównego obliczy datę zamówienia, która będzie wcześniejsza niż data bieżąca, zamówienia nie da się zrealizować w terminie. Takie zamówienie jest opóźnione. W takim przypadku planowanie główne planuje zamówienie w przyszłość od daty bieżącej i uwzględnia czasy realizacji. Te czasy realizacji zaczynają się od dowolnego składnika niższego poziomu. Następnie zamówienie otrzymuje datę opóźnienia. Data opóźnienia jest realistyczną datą realizacji obliczaną na podstawie bieżących danych. Planowanie główne oblicza również liczbę dni opóźnienia. 

W niektórych przypadkach można wybrać, by nie do obliczać opóźnienia, np. kiedy wiadomo, że czas realizacji można przyspieszyć, wybierając alternatywne metody dostawy. 

Można skonfigurować sposób obliczania opóźnienia dla grupy zapotrzebowania. Następnie można dołączyć grupę zaopatrzenia do towaru później. 

Na stronie **Parametry planowania głównego** można ustawić czas rozpoczęcia dla obliczania opóźnień. Jeżeli zamówienie zostało zamknięte po tym czasie, do daty opóźnienia zamówienia dodawany jest jeden dzień opóźnienia. 

**Uwaga:** We wcześniejszych wersjach obliczane opóźnienia były nazywane *komunikatami prognoz*, data opóźniona była nazywana *datą prognozy*, a transakcja opóźnienia była nazywana *transakcją z datą w przyszłości*.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Ustawienia zapotrzebowania](coverage-settings.md)




