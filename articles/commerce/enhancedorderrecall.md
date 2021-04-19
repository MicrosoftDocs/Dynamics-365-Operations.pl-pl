---
title: Odwołanie operacji zamówienia w punkcie sprzedaży
description: W tym temacie objaśniono możliwości funkcji dostępnych w przypadku ulepszonych stron wycofywania zamówień w punkcie sprzedaży.
author: hhainesms
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2f7ad4f53917bb607afe84a2c457518c3f8f7a08
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799114"
---
# <a name="recall-order-operation-in-pos"></a>Odwołanie operacji zamówienia w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Operacja **odwoływania zamówienia** w punkcie sprzedaży (POS) programu Commerce zapewnia zaktualizowane wyszukiwanie i filtrowanie zamówień oraz informacji właściwych dla zamówienia. Ta funkcja jest dostępna w Commerce w wersjach 10.0.15 i nowszej.

Aby włączyć tę funkcję, należy włączyć opcję **Ulepszona operacja odwoływania zamówienia w punkcie sprzedaży** w obszarze roboczym **Zarządzanie funkcjami** w module Commerce Headquarters. Po włączeniu tej funkcji należy rozważyć aktualizację [układów ekranu](pos-screen-layouts.md) w punkcie sprzedaży, aby korzystać z niektórych zmienionych możliwości.

Konfiguracja przycisku operacji **Odwołanie zamówienia** pozwala organizacjom na wdrożenie operacji na wstępnie zdefiniowanym ekranie.

![Konfiguracja siatki przycisków](media/recallorderbuttongrid.png)

Opcje wyświetlania opisano poniżej.
- **Brak** — ta opcja powoduje wdrożenie operacji bez określonego ekranu. Gdy użytkownik otworzy operację z tą konfiguracją, zostanie wyświetlony monit o wyszukanie i znalezienie zamówień lub wybrania wstępnie zdefiniowanego filtru zamówień.
- **Zamówienia do realizacji** — gdy użytkownik uruchomi operację, zostanie ona automatycznie uruchomiona w celu przeszukania i wyświetlenia listy zamówień, które mają być zrealizowane przez sklep użytkownika. Zamówienia te są konfigurowane do odbioru w sklepie lub wysyłki do sklepu, a wiersze tych zamówień nie zostały jeszcze pobrane ani zapakowane.
- **Zamówienia do odbioru** — gdy użytkownik uruchomi operację, automatycznie zostanie wykonane zapytanie w celu przeszukania i wyświetlenia listy zamówień, które są skonfigurowane do odbioru w bieżącym sklepie użytkownika.
- **Zamówienia do wysyłki** — gdy użytkownik uruchomi operację, automatycznie zostanie wykonane zapytanie w celu przeszukania i wyświetlenia listy zamówień, które są skonfigurowane do wysyłki z bieżącego sklepu użytkownika.

W przypadku uruchamiania operacji **Odwołanie zamówienia** z punktu sprzedaży, jeśli opcję wyświetlania skonfigurowano na **Brak**, użytkownik będzie mógł wyszukiwać i pobierać zamówienia w jeden z następujących sposobów:
- Skanowanie kodów kreskowych zamówień. Spowoduje to wyszukanie pól numeru zamówienia, odwołanie do kanału i identyfikatora odbioru pod kątem dopasowań.
- Wybierz ikonę **Wyszukaj zamówienia** lub **Wyszukaj i filtruj** na AppBar, aby zastosować mechanizm filtrowania do lokalizowania zamówień spełniających kryteria filtru.
- Umożliwia wybranie wstępnie zdefiniowanego filtru z menu rozwijanego **Pokaż zamówienia** (zamówienia do zrealizowania, zamówienia do odbioru lub zamówienia do wysłania).

![RecallOrderMainMenu](media/recallordermain.png)

Po zastosowaniu kryteriów wyszukiwania w aplikacji zostanie wyświetlona lista pasujących zamówień sprzedaży. Należy pamiętać, że w przypadku korzystania z opcji wyszukiwania/filtrowania pobrane zamówienia nie muszą być zamówieniami połączonymi z bieżącym sklepem użytkownika. Ten proces wyszukiwania spowoduje pobranie i wyświetlenie dowolnego zamówienia odbiorcy, który spełnia kryteria wyszukiwania, nawet jeśli zamówienie zostało utworzone lub ustawione jako spełnione przez inny sklep/kanał lub lokalizację magazynu.

![RecallOrderDetail](media/orderrecalldetail.png)

Użytkownik może wybrać zamówienie z listy, aby wyświetlić dodatkowe szczegóły. Panel informacji po prawej stronie ekranu zawiera informacje dotyczące wybranego zamówienia, w tym szczegóły wiersza zamówienia, szczegóły dotyczące dostawy i szczegóły dotyczące realizacji.

W AppBar użytkownik może wybrać operację. Niektóre operacje mogą nie być włączane w zależności od stanu zamówienia.

- **Zwrot** — inicjuje proces tworzenia zwrotu dla dowolnego z produktów zafakturowanych w wybranym zamówieniu odbiorcy.

- **Anuluj** — powoduje wygenerowanie pełnego anulowania wybranego zamówienia sprzedaży. Ta opcja nie będzie dostępna dla zamówień zainicjowanych za pośrednictwem kanału obsługi i nie można jej użyć do częściowego anulowania zamówienia.

- **Zrealizuj** — przenosi użytkownika na stronę realizacji zamówienia, która zostanie wstępnie przefiltrowana pod kątem wybranego zamówienia. Zostaną wyświetlone tylko wiersze zamówienia otwarte do realizacji przez sklep użytkownika dla wybranego zamówienia.

- **Edycja** — pozwala użytkownikom na wprowadzanie zmian w wybranym zamówieniu odbiorcy. Zamówienia można edytować tylko w [pewnych scenariuszach](customer-orders-overview.md#edit-an-existing-customer-order).

- **Odbiór** — ta opcja jest dostępna, jeśli zamówienie ma jeden lub więcej wierszy przeznaczonych do pobrania w bieżącym sklepie użytkownika. Operacja powoduje uruchomienie przepływu odbioru umożliwiającego użytkownikowi wybranie produktów, które mają zostać pobrane, i utworzenie transakcji pobrania sprzedaży.

## <a name="add-notifications-to-the-recall-order-operation"></a>Dodaj powiadomienia do operacji wycofania zamówienia

W wersji 10.0.18 lub nowszej można skonfigurować powiadomienia programu POS oraz alerty kafelków na żywo dla operacji **Odwołaj zamówienie**, jeśli jest to konieczne. Aby uzyskać więcej informacji, zobacz [Wyświetlanie powiadomień o zamówieniach w punkcie sprzedaży](notifications-pos.md)s  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
