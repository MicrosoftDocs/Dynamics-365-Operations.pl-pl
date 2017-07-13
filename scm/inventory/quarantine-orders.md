---
title: Zlecenia kwarantanny
description: "W tym artykule opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: ec3d54e8e08850cd81891e7058b2b787e08b0fb9
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Zlecenia kwarantanny
<a id="quarantine-orders" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym artykule opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów. 

Zlecenia kwarantanny mogą służyć do blokowania zapasów. Na przykład można poddać kwarantannie towary ze względów kontroli jakości. Zapasy poddane kwarantannie są przenoszone do magazynu kwarantanny. **Uwaga:** Jeśli używasz zaawansowanych procesów zarządzania magazynem (dostępnych w module Zarządzanie magazynem), przetwarzanie zleceń kwarantanny jest używane tylko do zamówień sprzedaży na zwrot.

## Dostępne pozycje magazynowe w kwarantannie
<a id="quarantine-onhand-inventory-items" class="xliff"></a>
W celu poddania towarów kwarantannie można ręcznie tworzyć zlecenia kwarantanny lub skonfigurować system, aby tworzył zlecenia kwarantanny automatycznie podczas przetwarzania dostaw przychodzących. Aby automatycznie tworzyć zlecenia kwarantanny, zaznacz opcję **Zarządzanie kwarantanną** na karcie **Zasady zapasów** na stronie **Grupy modeli pozycji**. Należy także w magazynach przyjmujących określić domyślny magazyn kwarantanny w polu **Magazyn kwarantanny**. Gdy zapasy fizycznie dostępne są rejestrowane w zamówieniu zakupu lub zleceniu produkcyjnym, towary poddane kwarantannie są automatycznie przenoszone do magazynu kwarantanny w programie Microsoft Dynamics 365 for Finance and Operations. To przesunięcie następuje, ponieważ stan zlecenia kwarantanny zmienił się na **Rozpoczęte**. Podczas ręcznego tworzenia zleceń kwarantanny towar nie musi być skonfigurowany dla zarządzania kwarantanną w powiązanej grupie modeli towarów. W przypadku tego procesu należy określić dostępne zapasy wymagające kwarantanny oraz magazyn kwarantanny, który ma być używany. Pomocą w planowaniu tego procesu mogą być stany zleceń kwarantanny.

## Stany zleceń kwarantanny
<a id="quarantine-order-statuses" class="xliff"></a>
Zlecenia kwarantanny mogą mieć następujące stany:

-   Utworzony
-   Rozpoczęta
-   Zgłoszone jako gotowe
-   Zakończono

### Utworzony
<a id="created" class="xliff"></a>

Gdy zlecenie kwarantanny zostało utworzone ręcznie, ale towar nie został jeszcze umieszczony w magazynie kwarantanny, zlecenie otrzymuje stan **Utworzone**. Generowane są dwie transakcje magazynowe. Jedna to transakcja wydania, która może mieć stan **Zamówione**, **Fizycznie zarezerwowane** lub **Pobrane**. Druga to transakcja przyjęcia w magazynie kwarantanny, która może stan **Zamówione** lub **Zarejestrowane**. Aktualizacje zapasów można rezerwować, pobierać i rejestrować za pomocą zwykłych procesów.

### Rozpoczęta
<a id="started" class="xliff"></a>

Gdy zlecenie kwarantanny ma stan **Rozpoczęte**, zapasy są przenoszone ze zwykłego magazynu do magazynu kwarantanny i następuje utworzenie dwóch transakcji magazynowych. Jedna transakcja ma stan **Wydane**, a druga ma stan **Otrzymane**. Jednocześnie tworzone są dwie transakcje magazynowe w celu realizacji przeniesienia zwrotnego. Te transakcje nie mają dat. Jedna transakcja ma stan **Fizycznie zarezerwowane**, a druga ma stan **Zamówione**.

### Zgłoszone jako gotowe
<a id="reported-as-finished" class="xliff"></a>

Kliknięcie opcji **Zgłoszenie wyrobów gotowych** umożliwia zgłoszenie rozpoczętego zlecenia kwarantanny jako gotowego. Towar jest zwalniany z kwarantanny, ale nie jest jeszcze przenoszony z powrotem do zwykłego magazynu. Przesunięcie z powrotem do zwykłego magazynu można zrealizować za pomocą arkusza przyjęcia towaru, który można zainicjować w trakcie procesu zgłaszania wyrobów gotowych.

### Zakończono
<a id="ended" class="xliff"></a>

Po zakończeniu zlecenia kwarantanny towar jest przenoszony z magazynu kwarantanny z powrotem do zwykłego magazynu. Transakcja towaru otrzymuje stan **Sprzedane** w magazynie kwarantanny i **Zakupione** w magazynie zwykłym.

## Odpadki zamówienia kwarantanny
<a id="quarantine-order-scrap" class="xliff"></a>
W ramach procesu zlecenia kwarantanny można przekazać zapasy do likwidacji. Podczas przetwarzania odpadków stan zapasów zostanie ustawiony na **Sprzedane** przez transakcję wydania z magazynu kwarantanny.

Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Blokowanie zapasów](inventory-blocking.md)




