---
title: Zaopatrzenie
description: W tym temacie objaśniono zaopatrzenie w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875838"
---
# <a name="procurement"></a>Zaopatrzenie


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W module Zarządzanie składnikami majątku można uzyskać przegląd zapotrzebowań zakupu i zamówień zakupu związanych z zleceniami produkcyjnymi. Istnieje również możliwość utworzenia zamówienia zakupu lub zapotrzebowania zakupu na podstawie zlecenia produkcyjnego.

Na liście **Zapotrzebowanie na zakup zlecenia pracy** (**Zarządzanie składnikami majątku** > **Wspólne** > **Zaopatrzenie** > **Zapotrzebowanie na zakup zlecenia pracy**) jest wyświetlenia lista zapotrzebowań zakupu związanych z zleceniami pracy w puli zleceń pracy.

- Wybierz zadanie zlecenia pracy w liście **Zapotrzebowanie na zakup zlecenia pracy** i kliknij przycisk **Zapotrzebowanie na zakup**, żeby otworzyć pokrewne zapotrzebowanie na zakup.  
- Wybierz zadanie zlecenia pracy w liście **Zapotrzebowanie na zakup zlecenia pracy** i kliknij przycisk **Zlecenie pracy**, żeby otworzyć pokrewne zlecenie pracy.  
- Wybierz zadanie zlecenia pracy z listy **Zapotrzebowanie na zakup zlecenia pracy** i kliknij **Używająca pozycja** przycisk, jeśli chcesz uzyskać przegląd tego, gdzie element w wybranym wierszu jest używany w Zarządzaniu składnikami majątku w odniesieniu do składników, domyślnych typów zadań konserwacji, części zamiennych i zleceń pracy. 

![Rysunek 1](media/08-work-orders.png)


Na liście **Zapotrzebowanie na zakup zlecenia pracy** (**Zarządzanie składnikami majątku przedsiębiorstwa** > **Wspólne** > **Zaopatrzenie** > **Zapotrzebowanie na zakup zlecenia pracy**) jest wyświetlenia lista zapotrzebowań zakupu związanych z zleceniami pracy.

- Wybierz zadanie zlecenia pracy w liście **Zapotrzebowanie na zakup zlecenia pracy** i kliknij przycisk **Zamówienie zakupu**, żeby otworzyć pokrewne zamówienie zakupu.  
- Wybierz zadanie zlecenia pracy w liście **Zakup zlecenia pracy** i kliknij przycisk **Zlecenie pracy**, żeby otworzyć pokrewne zlecenie pracy.  
- Wybierz zadanie zlecenia pracy z listy zakupów **Zlecenia pracy** i kliknij **Używająca pozycja** przycisk, jeśli chcesz uzyskać przegląd tego, gdzie element w wybranym wierszu jest używany w Zarządzaniu składnikami majątku w odniesieniu do składników, domyślnych typów zadań konserwacji, części zamiennych i zleceń pracy. 

![Rysunek 2](media/09-work-orders.png)


Na wyświetlonych powyżej listach ikona dotycząca kontroli daty dostawy jest umieszczana po prawej stronie każdego wiersza. Jeśli ikona zawiera wykrzyknik w czerwonym kółku, oznacza to, że dostawa w powiązanym zapotrzebowaniu na zakup lub zamówieniu zakupu może zostać opóźniona.

W przypadku zapotrzebowania zakupu Data używana do obliczenia możliwego opóźnienia znajduje się w formularzu **Zapotrzebowania na zakup** > skrócona lista **Nagłówek zapotrzebowania na zakup** > pole **Data wymagalności**. Data ta jest porównywana z datą dostępną w zleceniu produkcyjnym lub zamówieniu pracy w taki sam sposób jak Data zamówienia zakupu.

W zamówieniu zakupu Data używana do obliczenia możliwego opóźnienia to data związana z wierszem zamówienia zakupu, który jest wyświetlany w formularzu **Zamówienia zakupu** > wybierz wiersz zamówienia zakupu > **szczegóły wiersza** w skróconej karcie > **karta Ustawienia** > pole **Potwierdzona data dostawy**. Jeśli to pole nie jest wypełnione, zostanie użyta Data z pola **Data dostawy** w skróconej karcie **Nagłówek zamówienia zakupu**. Jedna z tych dat jest porównywana z dostępną datą w zleceniu pracy lub zleceniu pracy w następującej kolejności:

- Rzeczywista data rozpoczęcia w zleceniu pracy lub  

- Zaplanowana data rozpoczęcia powiązanego zlecenia pracy lub  

- Zaplanowana data rozpoczęcia w zleceniu pracy lub  

- Oczekiwana data rozpoczęcia w zleceniu pracy lub  


## <a name="create-purchase-order-from-a-work-order"></a>Tworzenie zamówienia zakupu na podstawie zlecenia pracy

We **wszystkich zleceniach pracy** można wybrać zadanie zlecenia produkcyjnego i utworzyć powiązane zamówienie zakupu lub zapotrzebowanie zakupu. W ten sposób można zapewnić relację projektu między zamówieniem zakupu lub zapotrzebowaniem zakupu a zleceniem produkcyjnym.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Na liście **Wszystkie zlecenia pracy** lub **aktywne zlecenia pracy** wybierz zlecenie pracy, dla którego chcesz utworzyć zamówienie zakupu, i kliknij przycisk **Edytuj.**

3. W formularzu **zlecenie pracy** > na skróconej karcie **Zadania konserwacji zlecenia pracy** wybierz zadanie zlecenia produkcyjnego, dla którego chcesz utworzyć zamówienie zakupu.

4. Kliknij **Zadania dotyczące pozycji** > **Zamówienie zakupu z zadania zlecenia pracy**.

5. Na stronie lista **Zamówienie zakupu dla projektu** zakupu dla projektu kliknij przycisk **Nowa**.

6. Tworzenie zamówienia zakupu:

>[!NOTE]
>Tworzenie zapotrzebowania zakupu jest prawie identyczne z tworzeniem zamówienia zakupu. Jedyną różnicą jest to, że w powyższej procedurze należy kliknąć **Zadania dotyczące pozycji** > **Zapotrzebowanie na zakup z zadania zlecenia pracy** w kroku 2.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relacja projektu między zleceniem produkcyjnym a zamówieniem zakupu lub zapotrzebowaniem zakupu

Wiersz zamówienia zakupu lub wiersz zapotrzebowania zakupu jest powiązany z zadaniem zlecenia w ramach projektu zlecenia produkcyjnego i powiązanego z nim numeru działania projektu. W przypadku tworzenia zamówienia zakupu lub zapotrzebowania zakupu na podstawie zadania zlecenia produkcyjnego numer powiązanego działania projektu jest obowiązkowy. Numer działania projektu jest automatycznie wstawiany w zamówieniu zakupu lub zapotrzebowaniu zakupu, jeśli powiązane zlecenie produkcyjne zawiera zadania zlecenia produkcyjnego, które używają tego samego typu zadania obsługi. Jeśli zadania zlecenia produkcyjnego zawierają różne typy zadań obsługi, numer działania projektu musi zostać wstawiony ręcznie.

Aby wyświetlić lub wstawić numer działania związanego z wierszem zamówienia zakupu, otwórz **Zakup zlecenia pracy** > wybierz rekord zamówienia zakupu > kliknij opcję zamówienie zakupu w kolumnie **zamówienie zakupu** > skrócona karta **Szczegóły wiersza** > karta **Projekt** > pole **Numer działania**.


![Rysunek 3](media/10-work-orders.png)


Aby wyświetlić lub wstawić numer działania związanego z wierszem zapotrzebowanie zakupu, otwórz **Zapotrzebowanie na zakup zlecenia pracy** > wybierz rekord zapotrzebowanie zakupu > kliknij opcję zapotrzebowanie zakupu w kolumnie **Zapotrzebowanie na zakup** > skrócona karta **Szczegóły wiersza** > karta **Projekt** > pole **Numer działania**.

