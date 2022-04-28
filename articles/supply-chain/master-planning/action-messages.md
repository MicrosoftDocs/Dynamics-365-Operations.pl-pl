---
title: Komunikaty akcji
description: Komunikat akcji jest generowaną przez system sugestią dotyczącą zmiany istniejącego zamówienia planowanego lub zaakceptowanego.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570262"
---
# <a name="action-messages"></a>Komunikaty akcji

[!include [banner](../includes/banner.md)]

Komunikat o działaniu to wygenerowana przez system sugestia zmiany istniejącego planowanego, zatwierdzonego lub potwierdzonego zlecenia.

Komunikaty akcji są generowane przez obliczenia planowania głównego w odpowiedzi na zmianę wymagań. Na przykład data wysyłki lub ilość jest zmieniana w zamówieniu sprzedaży po utworzeniu zamówienia zakupu w celu realizacji zapotrzebowania na to zamówienie sprzedaży. W takim przypadku w obliczeniach planowania głównego generowany jest jeden lub więcej komunikatów o działaniach sugerujących aktualizację zamówienia zakupu. Użytkownik decyduje, czy konieczne jest wprowadzenie sugerowanych zmian.

Istnieje możliwość konfiguracji sposobu obliczania komunikatów akcji dla grupy zapotrzebowania, którą można dołączyć do towaru.

## <a name="select-action-messages"></a>Wybieranie komunikatów akcji

Na stronie **grup zapotrzebowania** można wybrać komunikaty akcji, które mają być generowane przez system, oraz grupy lub elementy, których te komunikaty będą dotyczyć. W poniższej tabeli przedstawiono listę komunikatów o działaniach, które można wybrać.

| Komunikat | Opis |
|---|---|
| Zaliczka | System będzie generował komunikaty o działaniach, w miarę potrzeby, w celu przeniesienia zleceń na wcześniejszą datę. W polu **Dop. opóźnienie** można określić maksymalną liczbę dni, które mogą upłynąć między przyjęciem a wydaniem dokumentu bez podjęcia działań wyprzedzających. |
| Odrocz | System będzie generował komunikaty o działaniach, w miarę potrzeby, w celu przeniesienia zleceń na późniejszą datę. W polu **Dop. wyprzedzenie** można określić maksymalną liczbę dni, które mogą upłynąć między przyjęciem a wydaniem dokumentu bez wykonania akcji odroczenia. |
| Zmniejsz | System będzie generował komunikaty o działaniach, gdy zlecenia produkcyjne, zamówienia zakupu i inne transakcje przyjęcia powinny zostać zmniejszone, aby zapobiec nadmiernemu poziomowi zapasów. |
| Zwiększ | System będzie generował komunikaty o działaniach, gdy zlecenia produkcyjne, zamówienia zakupu i inne transakcje przyjęcia powinny zostać zwiększone, aby zapobiec brakom w zapasach. |
| Akcje pochodne | Komunikaty akcji utworzone dla transakcji odbioru będą propagowane do wszystkich wymagań pochodnych, a niezbędne komunikaty akcji będą generowane dla transakcji odbioru, które spełniają te wymagania. |

W kolejnych częściach przedstawiono kilka szczegółowych scenariuszy.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Zwiększ i zmniejsz akcje o domyślne ilości w zamówieniu produktu

Na stronie **Ustawienia domyślne** zamówienia dla towaru można skonfigurować minimalną ilość zamówienia, maksymalną ilość zamówienia oraz wiele wartości. Następnie system bierze te ustawienia pod uwagę, sugeruje akcje, aby mieć pewność, że te sugestie nigdy nie będą powodować pod odpowiedzialności.

Na przykład na stronie **Ustawienia domyślne zamówień** znajduje się towar o następujących ustawieniach:

- **Minimalna ilość zamówienia:** *0*
- **Maksymalna ilość zamówienia:** *90*
- **Wielokrotność:** *20*

Jeśli istnieje zapotrzebowanie na ilość 60 sztuk tego towaru, planowanie główne utworzy planowane zamówienie zakupu ilość 60. Jeśli popyt wzrośnie o 30, planowanie ogólne zasugeruje wzrost o 40, ponieważ będzie to zgodne z wielokrotnością 20 i nigdy nie spowoduje niedostatecznej podaży.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>Komunikaty akcji dotyczące zamówień związanych z zapasem bezpieczeństwa

Komunikaty akcji dla zleceń, które dostarczają zapas bezpieczeństwa, nigdy nie będą sugerować zmniejszenia ilości poniżej ilości potrzebnej dla zapasu bezpieczeństwa. Innymi słowy, jeśli istnieje zamówienie, które zaspokaja zapas bezpieczeństwa i zapotrzebowanie klienta, a zapotrzebowanie zostanie zmniejszone lub anulowane, planowanie główne zasugeruje zmniejszenie planowanego zamówienia o zmniejszone zapotrzebowanie. Jednak nigdy nie będzie sugerować wartości niższej niż wymagany zapas bezpieczeństwa.

System nie będzie sugerował odroczenia działań związanych z dostarczeniem zapasu bezpieczeństwa, ponieważ zakłada, że zapas bezpieczeństwa musi być dostarczony w wymaganym czasie i w wymaganym terminie.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Przyspieszanie i odkładanie działań związanych z BOM

Akcje związane ze składnikami BOM muszą być stosowane przed akcjami ich towarów nadrzędnych, ponieważ mogą mieć wpływ na dalsze zamówienia związane z BOM wyższego poziomu. Następnie należy ponownie uruchomić planowanie główne, aby ponownie wykonać ich obliczanie i zasugerować odpowiednie akcje.

Na przykład, masz następującą sytuację:

- Dobra finalne *FG* typu *produkcja* mają listę BOM zawierającą surowce *RM*.
- Dzisiejsza data to 21 stycznia.
- Istniejące, zwolnione zlecenie produkcyjne *FG* jest zaplanowane na 25 stycznia.
- Aby wesprzeć istniejące zlecenie produkcyjne, dział planowania głównego utworzył planowane zlecenie zakupu wymaganego surowca *RM*. Data zapotrzebowania dla tego zamówienia to 25 stycznia.
- W dniu dzisiejszym zostało utworzone nowe zamówienie sprzedaży dla *FG*. Datą wymagalności jest dzień dzisiejszy (21 stycznia).
- 21 stycznia jest zamknięty dla dostawy w kalendarzu *RM*, ale 22 stycznia jest otwarte.

Gdy uruchamiane jest planowanie główne, generowane są komunikaty o działaniach wyprzedzających, które sugerują przesunięcie wcześniej zaplanowanej produkcji, tak aby można było zrealizować dzisiejsze zamówienie.

- Aby sprostać nowemu zapotrzebowaniu, sugeruje przesunięcie zamówienia na produkcję *FG* na 21 stycznia. (Sugestia ta jest wprowadzana bez uwzględnienia daty zamknięcia dla *RM*)
- Ponieważ *RM* jest nadal wymagany dla zlecenia produkcyjnego, sugeruje przesunięcie w górę również planowanego zlecenia zakupu. Jednak tym razem sprawdza kalendarz *RM*. W związku z tym proponuje przesunięcie planowanego zlecenia zakupu dla *RM* na 22 stycznia (ponieważ 21 stycznia jest zamknięty).

Jak widać, wymagany surowiec *RM* zostanie dostarczony zbyt późno, aby zdążyć na zaplanowaną produkcję *FG*. Dlatego należy najpierw zastosować działanie wyprzedzające do planowanego zamówienia zakupu dla *RM*, a następnie ponownie uruchomić planowanie główne. W tym momencie planowanie główne wygeneruje nowy komunikat o działaniu, w którym zaproponuje przesunięcie zlecenia produkcyjnego dla *FG* na 22 stycznia.
