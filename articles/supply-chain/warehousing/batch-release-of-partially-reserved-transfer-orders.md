---
title: Wsadowe zwalnianie częściowo zarezerwowanych zamówień przeniesienia
description: W tym temacie opisano sposób konfigurowania i stosowania zwalniania wsadowego częściowo zarezerwowanych zamówień przeniesienia z urządzenia przenośnego.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fbe12b66da68bcd130fdb188eb0106b686200c3b59edc2af96b79f65022567a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759389"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Wsadowe zwalnianie częściowo zarezerwowanych zamówień przeniesienia

[!include [banner](../includes/banner.md)]

Funkcja zwalniania wsadowego częściowo zarezerwowanych zamówień przeniesienia umożliwia częściowe zwolnienie zamówień przeniesienia do magazynu za pomocą zadania wsadowego.
Ponieważ masz możliwość zwolnienia częściowej ilości, nie musisz czekać ze zwolnieniem zamówienia, aż cała ilość z zamówienia będzie dostępne w magazynie.

Zwalnianie zamówień do magazynu to zaawansowany proces zarządzania magazynem. Ten proces obejmuje działania, takie jak pobieranie, pakowanie i wysyłka, które pracownik magazynu może wykonać, używając urządzenia przenośnego.

## <a name="where-it-applies"></a>Zastosowanie

Na potrzeby tej funkcji zamówienia przeniesienia są zwalniane do magazynu za pomocą zadania wsadowego. Ta funkcja jest przydatna, gdy nie masz wystarczającej ilości zapasów w magazynie, ale mimo to chcesz przenieść towary między magazynami.

## <a name="how-it-is-set-up"></a>Sposób konfiguracji

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Określanie kryteriów realizacji dla zamówień przeniesienia i zamówień sprzedaży

Przed częściowym zwolnieniem zamówienia do magazynu w partii należy zwolnić kryteria realizacji. Te kryteria realizacji są określane przez zasady realizacji.

Zasady realizacji dla zamówień przeniesienia i zamówień sprzedaży są określone na poziomie firmy. W zależności od konfiguracji zasad realizacji, zwolnienie zamówień w partii zostanie zaakceptowane lub odrzucone. Zamówienia zostaną następnie odpowiednio przetworzone.

-   Aby utworzyć zasady realizacji dla zamówień przeniesienia i zamówień sprzedaży, kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Zwolnij do magazynu** \> **Zasady realizacji**, a następnie utwórz zasady realizacji, wprowadzając nazwę i opis.

-   Aby określić współczynnik realizacji, typ wartości i komunikat wyświetlany po naruszeniu zasad realizacji, kliknij kolejno opcję **Zarządzanie magazynem** \> **Konfiguracja** \> **Zwolnij do magazynu** \> **Zasady realizacji**, a następnie ustaw pola **Współczynnik realizacji**, **Typ wartości** i **Komunikat dotyczący naruszenia współczynnika realizacji**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Ustawianie zasad realizacji dla zamówień przeniesienia i zamówień sprzedaży

-   Aby ustawić zasady realizacji dla zamówień przeniesienia kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Parametry modułu Zarządzanie zapasami i magazynem** \> **Zamówienia przeniesienia** \> **Zarządzanie magazynem**, a następnie wybierz zasady realizacji zamówienia przeniesienia.

-   Aby ustawić zasady realizacji zamówień sprzedaży dla zamówień sprzedaży, kliknij kolejno opcję **Rozrachunki z odbiorcami** \> **Konfiguracja** \> **Parametry modułu rozrachunków z odbiorcami** \> **Zarządzanie z magazynem**, a następnie wybierz zasady realizacji zamówienia sprzedaży.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>Zezwalanie na zwolnienie partii i określanie ilości, która ma zostać zwolniona w partii

Zadanie wsadowe służy do zwalniania zamówień do magazynu w partii. Parametry odróżniające zamówienia uruchamiane w zadaniu wsadowym są ustawiane na poziomie zadania.

Parametr **Ilość** określa, czy w partii ma być zwolniona cała ilość czy ilość fizycznie dostępna. Parametr **Zezwalaj na częściowe zwalnianie zamówień** określa, czy zamówienia w partii mają być akceptowane czy odrzucane, jeżeli zostały częściowo zwolnione wcześniej.

-   Aby ustawić parametry **Ilość** i **Zezwalaj na częściowe zwalnianie zamówień** dla zamówień przeniesienia, kliknij kolejno opcje **Zarządzanie magazynem** \> **Zwolnij do magazynu** \> **Automatyczne zwalnianie zamówień przeniesienia**.

-   Aby ustawić parametry **Ilość** i **Zezwalaj na częściowe zwalnianie zamówień** dla zamówień sprzedaży, kliknij kolejno opcje **Zarządzanie magazynem** \> **Zwolnij do magazynu** \> **Automatyczne zwalnianie zamówień sprzedaży**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]