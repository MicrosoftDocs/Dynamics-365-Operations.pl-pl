---
title: Przy anulowaniu zamówienia sprzedaży nie można zmniejszyć ilości
description: Przy anulowaniu zamówienia sprzedaży nie można zmniejszyć ilości.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230843"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>Przy anulowaniu zamówienia sprzedaży nie można zmniejszyć ilości

Kod błędu: SYS138831

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Nie można zmniejszyć ilości. Liczba transakcji inwentaryzacyjnych w zamówieniu jest zbyt mała, ponieważ ilość lub jej część jest odniesiona do zlecenia wyjściowego lub produkcyjnego lub jest oznaczona w stosunku do innych transakcji.

## <a name="cause"></a>Powód

Jeśli praca jest skojarzona z zamówieniem sprzedaży, nie można anulować zamówienia sprzedaży, dopóki praca nie zostanie anulowana i wycofana. To wymaganie ma zastosowanie nawet wtedy, gdy praca skojarzona z zamówieniem sprzedaży jest zamknięta.

## <a name="resolution"></a>Rozwiązanie

Aby naprawić ten problem, wykonaj jedno z następujących zadań:

1. Anuluj otwartą pracę.
1. Usuń ładunek.
1. Zmniejsz ilość pobraną.

### <a name="cancel-open-work"></a>Anuluj otwartą pracę

Aby anulować otwartą pracę, wykonaj następujące kroki.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować, a obecnie ma wartość pola **Stan pracy** *Otwarta*, *W toku*, *Anulowana*, *Połączona* lub *Zamknięta*.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.

### <a name="delete-the-load"></a>Usuń ładunek

Aby usunąć ładunek, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Otwórz odnośne zamówienie sprzedaży.
1. W skróconej karcie **Wiesze zamówień sprzedaży**, wybierz opcję **Magazyn \> Szczegóły pracy**.
1. Na stronie **Praca**, w okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Anulowanie pracy**.
1. Potwierdź, że pole **Stan pracy** ma wartość *Anulowana*.
1. Zamknij stronę **Praca**.
1. Na stronie szczegółów zamówienia sprzedaży, na skróconej karcie **wiersze zamówienia sprzedaży** zaznacz szczegóły dotyczące **Magazynu \> szegółów ładunku**.
1. W okienku akcji wybierz opcję **Usuń**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz usunąć ładunek.
1. Zamknij stronę **ładunek**.

### <a name="reduce-the-picked-quantity"></a>Zmniejsz ilość pobraną

Po anulowaniu całej pracy należy wykonać następujące kroki, aby zmniejszyć ilość pobrań.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Otwórz odnośne zamówienie sprzedaży.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** zaznacz pozycję **Aktualizuj wiersz \> Pobieranie** na pasku narzędzi.
1. Na stronie **Pobrania** w sekcji **Transakcje** wybierz wiersz, w którym w polu **Stan wydania** ustawiono wartość *Pobrano*.
1. W sekcji **Transakcje** wybierz pozycję **Dodaj wiersz pobrania** z paska narzędzi.
1. W sekcji **Wiersze pobrania** wybierz pozycję **Potwierdź pobranie wszystkiego** z paska narzędzi.
1. Zamknij stronę **Pobieranie**.
1. Na stronie szczegółów zamówienia sprzedaży w okienku akcji na karcie **Zamówienie sprzedaży** w grupie **Utrzymanie** wybierz **Anuluj**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować zmówienie sprzedaży.
