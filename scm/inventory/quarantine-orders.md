---
title: Zlecenia kwarantanny
description: "W tym artykule opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 394276e6908f2c1f6bc72eea061facc3afe701e9
ms.lasthandoff: 03/31/2017


---

# <a name="quarantine-orders"></a>Zlecenia kwarantanny

W tym artykule opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów. 

Zlecenia kwarantanny mogą służyć do blokowania zapasów. Na przykład możesz chcieć kwarantanny elementy ze względów kontroli jakości. Zapasy, które w kwarantannie są przenoszone do magazynu kwarantanny. **Uwaga:** Jeśli używasz zaawansowanych procesów zarządzania magazynem (dostępnych w module Zarządzanie magazynem), przetwarzanie zleceń kwarantanny jest używane tylko do zamówień sprzedaży na zwrot.

## <a name="quarantine-onhand-inventory-items"></a>Kwarantanny, stan zapasów towarów magazynowych
W celu poddania towarów kwarantannie można ręcznie tworzyć zlecenia kwarantanny lub skonfigurować system, aby tworzył zlecenia kwarantanny automatycznie podczas przetwarzania dostaw przychodzących. Aby automatycznie tworzyć zlecenia kwarantanny, zaznacz opcję **Zarządzanie kwarantanną** na karcie **Zasady zapasów** na stronie **Grupy modeli pozycji**. Należy także w magazynach przyjmujących określić domyślny magazyn kwarantanny w polu **Magazyn kwarantanny**. Gdy zapasy fizycznie dostępne są rejestrowane w zamówieniu zakupu lub zleceniu produkcyjnym, towary poddane kwarantannie są automatycznie przenoszone do magazynu kwarantanny w programie Microsoft Dynamics 365 for Operations. To przesunięcie następuje, ponieważ stan zlecenia kwarantanny zmienił się na **Rozpoczęte**. Podczas ręcznego tworzenia zleceń kwarantanny towar nie musi być skonfigurowany dla zarządzania kwarantanną w powiązanej grupie modeli towarów. W przypadku tego procesu należy określić dostępne zapasy wymagające kwarantanny oraz magazyn kwarantanny, który ma być używany. Pomocą w planowaniu tego procesu mogą być stany zleceń kwarantanny.

## <a name="quarantine-order-statuses"></a>Stany zleceń kwarantanny
Zlecenia kwarantanny mogą mieć następujące stany:

-   Utworzony
-   Rozpoczęta
-   Zgłoszone jako gotowe
-   Zakończono

### <a name="created"></a>Utworzony

Gdy zlecenie kwarantanny zostało utworzone ręcznie, ale towar nie został jeszcze umieszczony w magazynie kwarantanny, zlecenie otrzymuje stan **Utworzone**. Generowane są dwie transakcje magazynowe. Jedna to transakcja wydania, która może mieć stan **Zamówione**, **Fizycznie zarezerwowane** lub **Pobrane**. Druga to transakcja przyjęcia w magazynie kwarantanny, która może stan **Zamówione** lub **Zarejestrowane**. Aktualizacje zapasów można rezerwować, pobierać i rejestrować za pomocą zwykłych procesów.

### <a name="started"></a>Rozpoczęta

Gdy zlecenie kwarantanny ma stan **Rozpoczęte**, zapasy są przenoszone ze zwykłego magazynu do magazynu kwarantanny i następuje utworzenie dwóch transakcji magazynowych. Jedna transakcja ma stan **Wydane**, a druga ma stan **Otrzymane**. Jednocześnie tworzone są dwie transakcje magazynowe w celu realizacji przeniesienia zwrotnego. Te transakcje nie mają dat. Jedna transakcja ma stan **Fizycznie zarezerwowane**, a druga ma stan **Zamówione**.

### <a name="reported-as-finished"></a>Zgłoszone jako gotowe

Kliknięcie opcji **Zgłoszenie wyrobów gotowych** umożliwia zgłoszenie rozpoczętego zlecenia kwarantanny jako gotowego. Towar jest zwalniany z kwarantanny, ale nie jest jeszcze przenoszony z powrotem do zwykłego magazynu. Przesunięcie z powrotem do zwykłego magazynu można zrealizować za pomocą arkusza przyjęcia towaru, który można zainicjować w trakcie procesu zgłaszania wyrobów gotowych.

### <a name="ended"></a>Zakończono

Po zakończeniu zlecenia kwarantanny towar jest przenoszony z magazynu kwarantanny z powrotem do zwykłego magazynu. Transakcja towaru otrzymuje stan **Sprzedane** w magazynie kwarantanny i **Zakupione** w magazynie zwykłym.

## <a name="quarantine-order-scrap"></a>Odpadki zamówienia kwarantanny
W ramach procesu zlecenia kwarantanny można przekazać zapasy do likwidacji. Podczas przetwarzania odpadków stan zapasów zostanie ustawiony na **Sprzedane** przez transakcję wydania z magazynu kwarantanny.

<a name="see-also"></a>Informacje dodatkowe
--------

[Inventory blocking](inventory-blocking.md)


