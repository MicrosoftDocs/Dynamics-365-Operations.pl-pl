---
title: Zaopatrzenie
description: W tym temacie objaśniono zaopatrzenie w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ec14f645af5dfdb3e840624e4cec95c46cfbbc25
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626438"
---
# <a name="procurement"></a>Zaopatrzenie

[!include [banner](../../includes/banner.md)]

W module Zarządzanie składnikami majątku można uzyskać przegląd zapotrzebowań zakupu i zamówień zakupu związanych ze zleceniami pracy. Istnieje również możliwość utworzenia zamówienia zakupu lub zapotrzebowania zakupu na podstawie zlecenia pracy.

Na stronie listy **Zapotrzebowanie na zakup zlecenia pracy** (**Zarządzanie składnikami majątku** > **Wspólne** > **Zaopatrzenie** > **Zapotrzebowanie na zakup zlecenia pracy**) jest wyświetlenia lista zapotrzebowań zakupu związanych z zleceniami pracy w puli zleceń pracy. Po wybraniu zadania zlecenia produkcyjnego na tej stronie można użyć przycisków w grupie **Pokaz** na karcie okienka akcji **Zapotrzebowanie na zakup zlecenia pracy**, aby wykonać różne akcje:

- Aby otworzyć powiązane zapotrzebowanie zakupu, wybierz **Zapotrzebowanie na zakup**. 
- Aby otworzyć powiązane zlecenie, zaznacz opcję **Zlecenie pracy**
- Aby uzyskać informacje o tym, gdzie jest używana pozycja w wybranym wierszu w odniesieniu do składników majątku, domyślnych typów zadań konserwacji, części zamiennych i zleceń pracy w module Zarządzanie składnikami majątku, wybierz opcję **Używająca pozycja**. Aby uzyskać więcej informacji na temat tego przeglądu, zobacz [Używająca pozycja](../controlling-and-reporting/item-where-used.md).

Na poniższej ilustracji przedstawiono przykład strony listy **Zapotrzebowanie na zakup zlecenia pracy**.

![Rysunek 1](media/08-work-orders.png)


Na stronie listy **Zapotrzebowanie na zakup zlecenia pracy** (**Zarządzanie składnikami majątku** > **Wspólne** > **Zaopatrzenie** > **Zakup zlecenia pracy**) jest wyświetlenia lista zamówień zakupu związanych ze zleceniami pracy. Po wybraniu zadania zlecenia produkcyjnego na tej stronie można użyć przycisków w grupie **Pokaz** na karcie okienka akcji **Zakup zlecenia pracy**, aby wykonać różne akcje:

- Aby otworzyć powiązane zamówienie zakupu, zaznacz opcję **Zamówienie zakupu** 
- Aby otworzyć powiązane zlecenie, zaznacz opcję **Zlecenie pracy**
- Aby uzyskać informacje o tym, gdzie jest używana pozycja w wybranym wierszu w odniesieniu do składników majątku, domyślnych typów zadań konserwacji, części zamiennych i zleceń pracy w module Zarządzanie składnikami majątku, wybierz opcję **Używająca pozycja**. Aby uzyskać więcej informacji na temat tego przeglądu, zobacz [Używająca pozycja](../controlling-and-reporting/item-where-used.md).

Na poniższej ilustracji przedstawiono przykład strony listy **Zakup zlecenia pracy**.

![Rysunek 2](media/09-work-orders.png)


Na stronie listy **Zakup zlecenia pracy** i stronie listy **Zapotrzebowanie na zakup zlecenia pracy**, po prawej stronie każdego wiersza jest wyświetlany symbol związany z kontrolą daty dostawy. Jeśli symbol zawiera wykrzyknik w czerwonym kółku, oznacza to, że dostawa powiązanego zamówienia zakupu lub zapotrzebowania na zakupu może zostać opóźniona.

W przypadku zamówienia zakupu data związana z wierszem zamówienia zakupu jest używana do obliczenia możliwego opóźnienia. Aby wyświetlić tę datę, na stronie **Zamówienie zakupu** należy wybrać wiersz zamówienia zakupu. Data ta jest wyświetlana w polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza**. Jeśli pole **Potwierdzona data dostawy** nie jest ustawione, do obliczania jest używana data w polu **Data dostawy** na skróconej karcie **Nagłówek zamówienia zakupu**. Jedna z tych dat jest porównywana z dostępną datą w zleceniu pracy lub zleceniu pracy w następującej kolejności:

1. Rzeczywista data rozpoczęcia w zleceniu pracy  

2. Zaplanowana data rozpoczęcia powiązanego zlecenia pracy 

3. Zaplanowana data rozpoczęcia w zleceniu pracy 

4. Oczekiwana data rozpoczęcia w zleceniu pracy lub 

W przypadku zapotrzebowania zakupu Data używana do obliczenia możliwego opóźnienia znajduje się w polu **Data wymagalności** na skróconej karcie **Nagłówek zapotrzebowania na zakup** strony **Zapotrzebowania na zakup**. Data w tym polu jest porównywana z datą dostępną w zleceniu pracy lub zadaniu zlecenia pracy w w takiej samej kolejności jak zamówienie zakupu.


## <a name="create-a-purchase-order-from-a-work-order"></a>Tworzenie zamówienia zakupu na podstawie zlecenia pracy

Na stronie listy **Wszystkie zlecenia pracy** można wybrać zadanie zlecenia pracy i utworzyć powiązane zamówienie zakupu lub zapotrzebowanie na zakup. W ten sposób można zapewnić istnienie relacji projektu między zamówieniem zakupu lub zapotrzebowaniem na zakup a zleceniem pracy.

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy, dla którego chcesz utworzyć zamówienie zakupu, a następnie wybierz **Edytuj**.

3. Na skróconej karcie **Zadania konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, dla którego chcesz utworzyć zamówienie zakupu.

4. Wybierz **Zadania dotyczące pozycji** > **Zamówienie zakupu z zadania zlecenia pracy**.

5. Na stronie listy **Zamówienie zakupu dla projektu** kliknij przycisk **Nowa**.

6. Tworzenie zamówienia zakupu:

>[!NOTE]
>Aby utworzyć powiązane zapotrzebowanie na zakup, wykonaj te same czynności. Jednak w kroku 4 wybierz **Zadania dotyczące pozycji** > **Zapotrzebowanie na zakup z zadania zlecenia pracy**.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relacja projektu między zleceniem produkcyjnym a zamówieniem zakupu lub zapotrzebowaniem zakupu

Wiersz zamówienia zakupu lub wiersz zapotrzebowania zakupu jest powiązany z zadaniem zlecenia w ramach projektu zlecenia produkcyjnego i powiązanego z nim numeru działania projektu. W przypadku tworzenia zamówienia zakupu lub zapotrzebowania zakupu na podstawie zadania zlecenia produkcyjnego numer powiązanego działania projektu jest obowiązkowy. Jeśli wszystkie zadania zlecenia pracy w powiązanych zleceniach pracy używają tego samego typu zadania konserwacji, numer działania projektu jest automatycznie wstawiany w zamówieniu zakupu lub zapotrzebowaniu na zakup. Jeśli zadania zlecenia pracy używają innego typu zadania konserwacji, numer działania projektu jest należy wstawić ręcznie w zamówieniu zakupu lub zapotrzebowaniu na zakup.

Aby wyświetlić lub wprowadzić numer działania powiązany z wierszem zamówienia zakupu, na stronie listy **Zakup zlecenia pracy** należy wybrać rekord zamówienia zakupu, a następnie w kolumnie **Zamówienie zakupu** wybrać łącze dla tego zamówienia. Pole **Numer działania** można znaleźć na karcie **Projekt** na skróconej karcie **Szczegóły wiersza**.

Poniższa ilustracja przedstawia przykład strony **Zamówienie zakupu** z naciskiem na **Numer działania**.

![Rysunek 3](media/10-work-orders.png)

Podobnie, aby wyświetlić lub wprowadzić numer działania powiązany z wierszem zapotrzebowania na zakup zlecenia pracy, na stronie listy **Zapotrzebowanie na zakup zlecenia pracy** należy wybrać rekord zapotrzebowania na zakup, a następnie w kolumnie **Zapotrzebowanie na zakup** wybrać łącze dla tego zapotrzebowania. Pole **Numer działania** można znaleźć na karcie **Projekt** na skróconej karcie **Szczegóły wiersza**.

