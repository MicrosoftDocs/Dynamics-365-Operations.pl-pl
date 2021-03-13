---
title: Odwołanie operacji zamówienia w punkcie sprzedaży
description: W tym temacie objaśniono możliwości funkcji dostępnych w przypadku ulepszonych stron wycofywania zamówień w punkcie sprzedaży.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 21e8045d754006345f5ad68e1e67579386c6df4a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010081"
---
# <a name="recall-order-operation-in-pos"></a>Odwołanie operacji zamówienia w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Operacja **odwoływania zamówienia** w punkcie sprzedaży (POS) programu Commerce zapewnia zaktualizowane wyszukiwanie i filtrowanie zamówień oraz informacji właściwych dla zamówienia. Ta funkcja jest dostępna w Commerce w wersjach 10.0.15 i nowszej.

Aby włączyć tę funkcję, należy włączyć opcję **Ulepszona operacja odwoływania zamówienia w punkcie sprzedaży** w obszarze roboczym **Zarządzanie funkcjami** w module Commerce Headquarters. Po włączeniu tej funkcji należy rozważyć aktualizację [układów ekranu](pos-screen-layouts.md) w punkcie sprzedaży, aby korzystać z niektórych zmienionych możliwości.

Konfiguracja przycisku operacji **Odwołanie zamówienia** pozwala organizacjom na wdrożenie operacji na wstępnie zdefiniowanym ekranie.

![Konfiguracja siatki przycisków](media/recallorderbuttongrid.png)

Opcje wyświetlania opisano poniżej.
- **Brak** — ta opcja powoduje wdrożenie operacji bez określonego ekranu. Gdy użytkownik otworzy operację z tą konfiguracją, zostanie wyświetlony monit o wyszukanie i znalezienie zamówień lub wybrania wstępnie zdefiniowanego filtru zamówień.
- **Zamówienia do realizacji** — gdy użytkownik uruchomi operację, zostanie ona automatycznie uruchomiona w celu przeszukania i wyświetlenia listy zamówień, które mają być zrealizowane przez sklep. Zamówienia te są konfigurowane do odbioru w sklepie lub wysyłki do sklepu, a wiersze tych zamówień nie zostały jeszcze pobrane ani zapakowane.
- **Zamówienia do odbioru** — gdy użytkownik uruchomi operację, automatycznie zostanie wykonane zapytanie w celu przeszukania i wyświetlenia listy zamówień, które są skonfigurowane do odbioru w bieżącym sklepie użytkownika.
- **Zamówienia do wysyłki** — gdy użytkownik uruchomi operację, automatycznie zostanie wykonane zapytanie w celu przeszukania i wyświetlenia listy zamówień, które są skonfigurowane do wysyłki z bieżącego sklepu użytkownika.

W przypadku uruchamiania operacji **Odwołanie zamówienia** z punktu sprzedaży, jeśli opcję wyświetlania skonfigurowano na **Brak**, użytkownik będzie mógł wyszukiwać i pobierać zamówienia w jeden z następujących sposobów:
- Skanowanie kodów kreskowych zamówień. Spowoduje to wyszukanie pól numeru zamówienia, odwołanie do kanału i identyfikatora odbioru pod kątem dopasowań.
- Wybierz ikonę **Wyszukaj zamówienia** lub **Wyszukaj i filtruj** na AppBar, aby zastosować mechanizm filtrowania do lokalizowania zamówień spełniających kryteria filtru.
- Umożliwia wybranie wstępnie zdefiniowanego filtru z menu rozwijanego **Pokaż zamówienia** (zamówienia do zrealizowania, zamówienia do odbioru lub zamówienia do wysłania).

![RecallOrderMainMenu](media/recallordermain.png)

Po zastosowaniu kryteriów wyszukiwania w aplikacji zostanie wyświetlona lista pasujących zamówień sprzedaży.

![RecallOrderDetail](media/orderrecalldetail.png)

Użytkownik może wybrać zamówienie z listy, aby wyświetlić dodatkowe szczegóły. Panel informacji po prawej stronie ekranu zawiera informacje dotyczące wybranego zamówienia, w tym szczegóły wiersza zamówienia, szczegóły dotyczące dostawy i szczegóły dotyczące realizacji.

W AppBar użytkownik może wybrać operację. Niektóre operacje mogą nie być włączane w zależności od stanu zamówienia.

- **Zwrot** — powoduje wykonanie zwrotu dla co najmniej jednej faktury powiązanej z wybranym zamówieniem odbiorcy.

- **Anuluj** — powoduje wygenerowanie pełnego anulowania wybranego zamówienia sprzedaży.

- **Zrealizuj** — przenosi użytkownika na stronę realizacji zamówienia, która zostanie wstępnie przefiltrowana pod kątem wybranego zamówienia. Zostaną wyświetlone tylko wiersze zamówienia otwarte do realizacji przez sklep użytkownika dla wybranego zamówienia.

- **Edycja** — pozwala użytkownikom na wprowadzanie zmian w wybranym zamówieniu odbiorcy.

- **Odbiór** — powoduje uruchomienie przepływu odbioru umożliwiającego użytkownikowi wybranie produktów, które mają zostać pobrane, i utworzenie transakcji pobrania sprzedaży.
