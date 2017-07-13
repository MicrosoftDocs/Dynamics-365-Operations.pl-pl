---
title: "Omówienie zamówień odbiorców"
description: "Ten temat zawiera informacje o funkcjonalności zamówień odbiorców w programie Retail Modern POS (MPOS). Zamówienia odbiorców są również nazywane zamówieniami specjalnymi. Temat przedstawia powiązane parametry i przepływy transakcji."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 89e79c7227e05eec539d9bb142b8f41de092f01b
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017



---

# Omówienie zamówień odbiorców
<a id="customer-orders-overview" class="xliff"></a>

[!include[banner](includes/banner.md)]


Ten temat zawiera informacje o funkcjonalności zamówień odbiorców w programie Retail Modern POS (MPOS). Zamówienia odbiorców są również nazywane zamówieniami specjalnymi. Temat przedstawia powiązane parametry i przepływy transakcji.

W świecie wielokanałowego handlu detalicznego wielu sprzedawców udostępnia opcję składania zamówień przez odbiorców, inaczej zamówień specjalnych, które pomagają spełnić różne wymagania dotyczące produktów i realizacji dostaw. Poniżej przedstawiono niektóre typowe scenariusze:

-   Klient chce, aby produkty zostały dostarczane pod określony adres w określonym dniu.
-   Klient chce odebrać produkty ze sklepu lub lokalizacji innej niż ta, w której kupił produkty.
-   Klient chce, aby ktoś inny odebrał kupione przez niego produkty.

Sprzedawcy detaliczni wykorzystują również zamówienia odbiorców, aby minimalizować utraconą sprzedaż, jaką mogą powodować przestoje w zaopatrzeniu, ponieważ towar może być dostarczany lub odbierany w różnych miejscach i czasie.

## Konfigurowanie zamówień odbiorców
<a id="set-up-customer-orders" class="xliff"></a>
Oto kilka parametrów, które można skonfigurować na stronie **Parametry sieci sprzedaży** w celu zdefiniowania sposobu realizacji zamówień odbiorców:

-   **Domyślne oprocentowanie lokaty** — Określ kwotę, jaką odbiorca musi wpłacić jako depozyt, zanim zamówienie zostanie potwierdzone. Domyślna kwota kaucji jest obliczana jako procent wartości zamówienia. W zależności od posiadanych uprawnień pracownik sklepu może być w stanie ręcznie zmienić tę kwotę za pomocą opcji **Zastąpienie wpłaty**.
-   **Procent opłaty za anulowanie** — Jeśli z tytułu anulowania zamówienia odbiorcy będzie naliczana opłata, należy podać kwotę tej opłaty.
-   **Kod opłaty za anulowanie** — Jeśli z tytułu anulowania zamówienia odbiorcy będzie naliczana opłata, ta opłata będzie wykazywana pod odpowiednim kodem opłaty w zamówieniu sprzedaży. Za pomocą tego parametru można zdefiniować kod opłaty za anulowanie.
-   **Kod opłaty transportowej** — Sprzedawcy detaliczni mogą naliczać dodatkową opłatę za wysyłkę towarów do odbiorców. Kwota tej opłaty transportowej zostanie wykazana pod odpowiednim kodem opłaty w zamówieniu sprzedaży. Ten parametr służy do mapowania kodu opłaty transportowej na opłaty transportowe w zamówieniu odbiorcy.
-   **Zwróć opłaty transportowe** — Określ, czy opłaty transportowe skojarzone z zamówieniem odbiorcy podlegają zwrotowi.
-   **Maksymalna kwota bez zatwierdzenia** — Jeśli opłaty transportowe podlegają zwrotowi, określ maksymalną kwotę takiego zwrotu dla wszystkich zamówień zwrotu. Jeśli ta kwota zostanie przekroczona, w celu kontynuowania zwrotu jest konieczne ręczne zastąpienie przez menedżera. Aby umożliwić realizację scenariuszy opisanych poniżej, zwrot opłaty transportowej może przekraczać pierwotnie zapłaconą kwotę:
    -   Opłaty są stosowane na poziomie nagłówka zamówienia sprzedaży, a gdy pewna ilość z wiersza produktu jest zwracana, maksymalny zwrot opłat transportowych dozwolony dla produktów i ilości nie może zostać określony w sposób pasujący dla wszystkich odbiorców detalicznych.
    -   Opłaty transportowe są ponoszone dla każdego zdarzenia wysyłki. Jeśli odbiorca zwraca produkty wiele razy, a polityka sprzedawcy detalicznego określa, że ponosi on koszty zwrotu opłat transportowych, zwracane opłaty transportowe będą wyższe, niż faktyczne opłaty transportowe.

## Przepływ transakcji w zamówieniach odbiorców
<a id="transaction-flow-for-customer-orders" class="xliff"></a>
### Tworzenie zamówienia odbiorcy w aplikacji Retail Modern POS
<a id="create-a-customer-order-in-retail-modern-pos" class="xliff"></a>

1.  Dodaj odbiorcę do transakcji.
2.  Dodaj produkty do koszyka.
3.  Kliknij opcję **Utwórz zamówienie odbiorcy**, a następnie wybierz typ zamówienia. Typem zamówienia może być **Zamówienie odbiorcy** lub **Oferta**.
4.  Kliknij opcję **Wyślij wybrane** lub **Wyślij wszystko**, aby wysłać produkty pod adres na koncie odbiorcy, określić żądaną datę wysyłki i określić opłaty transportowe.
5.  Kliknij opcję **Odbierz wybrane** lub **Pobierz wszystko**, aby zaznaczyć produkty, które mają zostać pobrane z bieżącego sklepu lub innego sklepu w określonym dniu.
6.  Jeśli jest wymagana kaucja, pobierz ją.

### Edytowanie istniejącego zamówienia odbiorcy
<a id="edit-an-existing-customer-order" class="xliff"></a>

1.  Na stronie głównej kliknij opcję **Znajdź zamówienie**.
2.  Znajdź i zaznacz zamówienie, które chcesz zmodyfikować. U dołu strony kliknij przycisk **Edytuj**.

### Pobieranie zamówienia
<a id="pick-up-an-order" class="xliff"></a>

1.  Na stronie głównej kliknij opcję **Znajdź zamówienie**.
2.  Zaznacz zamówienie, dla którego chcesz pobrać produkty. U dołu strony kliknij opcję **Pobieranie i pakowanie**.
3.  Kliknij przycisk **Pobierz**.

### Anulowanie zamówienia
<a id="cancel-an-order" class="xliff"></a>

1.  Na stronie głównej kliknij opcję **Znajdź zamówienie**.
2.  Zaznacz zamówienie, które chcesz anulować. U dołu strony kliknij przycisk **Anuluj**.

#### Tworzenie zamówienia zwrotu
<a id="create-a-return-order" class="xliff"></a>

1.  Na stronie głównej kliknij opcję **Znajdź zamówienie**.
2.  Zaznacz zamówienie, którego produkty chcesz zwrócić, zaznacz fakturę do zamówienia, a następnie zaznacz wiersz produktu, który chcesz zwrócić.
3.  U dołu strony kliknij przycisk **Zwróć zamówienie**.

## Asynchroniczny przepływ transakcji w zamówieniach odbiorców
<a id="asynchronous-transaction-flow-for-customer-orders" class="xliff"></a>
Zamówienia odbiorców mogą być tworzone w aplikacji klienckiej punktu sprzedaży (POS) w trybie synchronicznym lub asynchronicznym.

### Włączanie funkcji tworzenia zamówień odbiorców w trybie asynchronicznym
<a id="enable-customer-orders-to-be-created-in-asynchronous-mode" class="xliff"></a>

1.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile funkcji**.
2.  Na skróconej karcie **Ogólne** w opcji **Utwórz zamówienie odbiorcy w trybie asynchronicznym** ustaw wartość **Tak**.

Gdy opcja **Utwórz zamówienie odbiorcy w trybie asynchronicznym** jest ustawiona na **Tak**, zamówienia odbiorców są zawsze tworzone w trybie asynchronicznym, nawet jeśli jest dostępna usługa Retail Transaction Service (RTS). Jeśli ustawisz tę opcję na **Nie**, zamówienia odbiorców są zawsze tworzone w trybie synchronicznym przy użyciu usługi RTS. Po utworzeniu zamówień odbiorców w trybie asynchronicznym są one pobierane i wstawiane do modułu Handel detaliczny przez zadania ściągania (P). Odnośne zamówienia sprzedaży są tworzone w module Handel detaliczny podczas wykonywania operacji **Synchronizuj zamówienia** ręcznie lub w procesie wsadowym.

Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Hybrydowe zamówienia odbiorców](hybrid-customer-orders.md)




