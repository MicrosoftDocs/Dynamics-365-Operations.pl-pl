---
title: Aktualizacje fizyczne i finansowe
description: "W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d68006c756f6b29804cad1d05db9ced2bd33897d
ms.lasthandoff: 03/31/2017


---

# <a name="physical-and-financial-updates"></a>Aktualizacje fizyczne i finansowe

W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów. 

Transakcje magazynowe można zaktualizowane fizycznie i finansowo zaktualizowane w programie Microsoft Dynamics 365 dla operacji. Niektóre typy transakcji fizycznych i finansowych zwiększają ilości zapasów, podczas gdy inne je zmniejszają.

## <a name="physical-increases"></a>Wzrost fizyczny
Po zaksięgowaniu transakcji fizycznej stan tej transakcji przyjmuje wartość **Otrzymano**. Oto transakcje, które stanowią wzrost fizyczny:

-   zamówienie zakupu — przychód,
-   zwrot dokumentu dostawy zamówienia sprzedaży,
-   Zgłaszanie zlecenia produkcyjnego jako zakończonego
-   według produktów na liście pobrania zlecenia produkcyjnego.

## <a name="financial-increases"></a>Wzrost finansowy
Po zaksięgowaniu finansowej transakcji przychodu stan rekordu tej transakcji powodującej zwiększenie ilości przyjmuje wartość **Zakupiono**. Oto transakcje, które stanowią wzrost finansowy:

-   Faktura dostawcy
-   faktura zamówienia zakupu do zwrotu,
-   wycena zlecenia produkcyjnego,
-   Arkusze magazynowe z ilością dodatnią, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.

## <a name="transactions-that-increase-quantity"></a>Transakcje, które zwiększają ilość
Transakcje zwiększające ilość są księgowane według dynamicznych średnich kosztów własnych. Dynamics 365 dla operacji obliczania średniego kosztu, który jest oparty na koszt każdego z tych transakcji dla każdego wymiaru magazynowego, która jest śledzona finansowo. Aby uzyskać informacje o uruchamianiu średnich kosztów własnych, zobacz [Dynamiczne średnie koszty własne](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transakcje, które zmniejszają ilość
Dynamics 365 dla operacji używa obliczona średnia krocząca kosztu podczas księgowania transakcji, która zmniejsza ilość, bez względu na model magazynu, która jest skojarzona z tego magazynu. Wymaga to, aby transakcja, która zmniejsza ilość nie została wcześniej oznaczona dla innej transakcji przed zaksięgowaniem. Jeśli fizyczne dostępne zapasy staje się ujemna, Dynamics 365 dla operacji używa koszt zapasów, który jest zdefiniowany dla elementu na **elementu** strony. **Uwaga:** Jeśli włączono funkcję wielooddziałowości, to koszt ten będzie zastępczo używany jako koszt magazynowy, zdefiniowany dla oddziału na stronie **Ustawienia domyślne zamówień**.

## <a name="physical-issues-vs-financial-issues"></a>Rozchody fizyczne a finansowe
Po zaksięgowaniu transakcji fizycznego rozchodu stan rekordu transakcji przyjmuje wartość **Zmniejszono**. Oto transakcje stanowiące fizyczne rozchody:

-   arkusz listy pobrań zlecenia produkcyjnego,
-   dokument dostawy zamówienia sprzedaży,
-   zwrot dokumentu dostawy zamówienia zakupu.

Po zaksięgowaniu transakcji finansowej stan rekordu tej transakcji przyjmuje wartość **Sprzedano**. Oto transakcje stanowiące finansowe rozchody:

-   Kończenie zlecenia produkcyjnego
-   Faktura dla zamówienia sprzedaży
-   Zwrot z faktury od dostawcy
-   Arkusze magazynowe z ilością ujemną, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.

Transakcje zmniejszające ilość są księgowane według dynamicznych średnich kosztów własnych. Z tego powodu proces zamknięcia magazynu jest wymagany w celu rozliczenia transakcji rozchodu z transakcjami przychodu, według modelu magazynu przypisanego dla danego towaru.


