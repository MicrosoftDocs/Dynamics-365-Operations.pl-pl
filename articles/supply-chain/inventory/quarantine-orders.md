---
title: Zlecenia kwarantanny
description: W tym temacie opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956189"
---
# <a name="quarantine-orders"></a>Zlecenia kwarantanny

[!include [banner](../includes/banner.md)]

W tym temacie opisano wykorzystywanie zleceń kwarantanny do blokowania zapasów.

Zlecenia kwarantanny pozwalają zablokować zapasy. Na przykład można poddać kwarantannie towary ze względów kontroli jakości. Zapasy poddane kwarantannie są przenoszone do magazynu kwarantanny.

> [!NOTE]
> Jeśli używasz zaawansowanych procesów zarządzania magazynem (dostępnych w module Zarządzanie magazynem), przetwarzanie zleceń kwarantanny jest używane tylko do zamówień sprzedaży na zwrot.

## <a name="quarantine-on-hand-inventory-items"></a>Dostępne pozycje magazynowe w kwarantannie

W celu poddania towarów kwarantannie można ręcznie tworzyć zlecenia kwarantanny lub skonfigurować system, aby tworzył je automatycznie podczas przetwarzania dostaw przychodzących.

Aby skonfigurować system do automatycznego generowania zleceń kwarantanny, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zapasy \> Grupy modeli pozycji**.
1. Wybierz odpowiednią grupę modeli w okienku listy lub utwórz nową grupę modeli.
1. Na skróconej karcie **Zasady zapasów** zaznacz pole wyboru **Zarządzanie kwarantanną**.
1. Zamknij stronę.
1. W polu **Magazyn kwarantanny** przyjmujących magazynów określ domyślny magazyn kwarantanny.

Jeśli towar zarejestrowany jako przyjęty w magazynie należy do grupy modeli, w której jest zaznaczone pole wyboru **Zarządzanie kwarantanną**, system wygeneruje dla niego zlecenie kwarantanny. Zlecenie kwarantanny poleca pracownikom, aby przenieśli towar do magazynu kwarantanny.

Podczas ręcznego tworzenia zleceń kwarantanny na stronie **Zlecenia kwarantanny** towar nie musi być skonfigurowany dla zarządzania kwarantanną w powiązanej grupie modeli pozycji. W przypadku tego procesu należy określić dostępne zapasy wymagające kwarantanny oraz magazyn kwarantanny, który ma być używany. Pomocą w planowaniu tego procesu mogą być stany zleceń kwarantanny.

## <a name="quarantine-order-statuses"></a>Stany zleceń kwarantanny

Zlecenia kwarantanny mogą mieć następujące stany:

- Utworzony
- Rozpoczęta
- Zgłoszone jako gotowe
- Zakończono

### <a name="created"></a>Utworzony

Gdy zlecenie kwarantanny zostało utworzone ręcznie, ale towar nie został jeszcze umieszczony w magazynie kwarantanny, zlecenie otrzymuje stan **Utworzone**. Generowane są dwie transakcje magazynowe. Jedna to transakcja wydania, która może mieć stan **Zamówione**, **Fizycznie zarezerwowane** lub **Pobrane**. Druga to transakcja przyjęcia w magazynie kwarantanny, która może stan **Zamówione** lub **Zarejestrowane**. Aktualizacje zapasów można rezerwować, pobierać i rejestrować za pomocą zwykłych procesów.

### <a name="started"></a>Rozpoczęta

Gdy zlecenie kwarantanny ma stan **Rozpoczęte**, zapasy są przenoszone ze zwykłego magazynu do magazynu kwarantanny i następuje utworzenie dwóch transakcji magazynowych. Jedna transakcja ma stan **Wydane**, a druga ma stan **Otrzymane**. Jednocześnie tworzone są dwie transakcje magazynowe w celu realizacji przeniesienia zwrotnego. Te transakcje nie mają dat. Jedna transakcja ma stan **Fizycznie zarezerwowane**, a druga ma stan **Zamówione**.

### <a name="reported-as-finished"></a>Zgłoszone jako gotowe

Aby zgłosić rozpoczęte zlecenie kwarantanny jako zakończone, otwórz zamówienie i wybierz opcję **Gotowe** w okienku akcji. Towar jest zwalniany z kwarantanny, ale nie jest jeszcze przenoszony z powrotem do zwykłego magazynu. Przesunięcie z powrotem do zwykłego magazynu można zrealizować za pomocą arkusza przyjęcia towaru, który można zainicjować w trakcie procesu zgłaszania gotowości.

### <a name="ended"></a>Zakończone

Po zakończeniu zlecenia kwarantanny towar jest przenoszony z magazynu kwarantanny z powrotem do zwykłego magazynu. Transakcja towaru otrzymuje stan *Sprzedane* w magazynie kwarantanny i *Zakupione* w magazynie zwykłym.

## <a name="quarantine-order-scrap"></a>Odpadki zamówienia kwarantanny

W ramach procesu zlecenia kwarantanny można przekazać zapasy do likwidacji. Podczas przetwarzania odpadków stan zapasów zostanie ustawiony na *Sprzedane* przez transakcję wydania z magazynu kwarantanny.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Blokowanie zapasów](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
