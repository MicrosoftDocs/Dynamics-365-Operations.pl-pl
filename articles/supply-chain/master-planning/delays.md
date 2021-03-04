---
title: Opóźnienia
description: Ten temat zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da09d670fd952d885f013693b6362cf9002343ff
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435468"
---
# <a name="delays"></a>Opóźnienia

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.

Planowanie główne pozwala obliczać najwcześniejszą datę realizacji transakcji na podstawie czasów realizacji, dostępności materiałów, dostępności zdolności produkcyjnych i różnych parametrów planowania. 

Jeżeli funkcja planowania głównego obliczy datę zamówienia, która będzie wcześniejsza niż data bieżąca, zamówienia nie da się zrealizować w terminie. Takie zamówienie jest opóźnione. W takim przypadku planowanie główne planuje zamówienie w przyszłość od daty bieżącej i uwzględnia czasy realizacji. Te czasy realizacji zaczynają się od dowolnego składnika niższego poziomu. Następnie zamówienie otrzymuje datę opóźnienia. Data opóźnienia jest realistyczną datą realizacji obliczaną na podstawie bieżących danych. Planowanie główne oblicza również liczbę dni opóźnienia. 

W niektórych przypadkach można wybrać, by nie do obliczać opóźnienia, np. kiedy wiadomo, że czas realizacji można przyspieszyć, wybierając alternatywne metody dostawy. 

Można skonfigurować sposób obliczania opóźnienia dla grupy zapotrzebowania. Następnie można dołączyć grupę zaopatrzenia do towaru później. 

Na stronie **Parametry planowania głównego** można ustawić czas rozpoczęcia dla obliczania opóźnień. Jeżeli zamówienie zostało zamknięte po tym czasie, do daty opóźnienia zamówienia dodawany jest jeden dzień opóźnienia. 

> [!NOTE]
> We wcześniejszych wersjach obliczane opóźnienia były nazywane *komunikatami prognoz*, data opóźniona była nazywana *datą prognozy*, a transakcja opóźnienia była nazywana *transakcją z datą w przyszłości*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Ograniczone opóźnienia w konfiguracji produkcji z wieloma poziomami BOM
Podczas pracy z opóźnieniami w konfiguracji produkcji, która ma wiele poziomów BOM, należy zwrócić uwagę, że tylko towary znajdujące się bezpośrednio powyżej towaru (w strukturze BOM), które powodują opóźnienie, będą aktualizowane z opóźnieniem w ramach procesu planowania głównego. Inne towary w strukturze BOM nie uzyskują opóźnień zastosowanych do momentu zaakceptowania lub zaakceptowania pierwszego planu głównego, gdy zamówienie planowane na najwyższy poziom jest potwierdzone lub wyprodukowane. 

W celu obejścia tego znanego ograniczenia zlecenia produkcyjne w górnej części struktury BOM z opóźnieniami mogą zostać zatwierdzone (lub wyprodukowane) przed kolejnym uruchomieniem planowania głównego. Dzięki temu opóźnienie z opóźnionych zatwierdzonych planowanych zleceń produkcyjnych zostanie zachowane, a wszystkie podskładniki zostaną odpowiednio zaktualizowane.
Komunikaty akcji mogą być również używane do identyfikowania zamówień planowanych, które można przenieść do późniejszej daty z powodu innych opóźnień w strukturze BOM.

## <a name="desired-date"></a>Wymagana data

Na stronie **zamówienia planowanego** na karcie **opóźnień** jest **Żądana data** dla tego zamówienia. Wymagana data planowanego zamówienia jest podstawową datą dla opóźnień, która jest obliczona i jest równa **Żądanej dacie** obliczonej ze **zapotrzebowania netto**. Jeśli planowane zamówienie jest wierszem BOM, wierszem produkcji lub wierszem na karcie kanban, wymagana data opiera się na **Dacie zapotrzebowania** i żądana data nie będzie wyświetlana na stronie **zamówienia planowanego**.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Ustawienia zapotrzebowania](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]