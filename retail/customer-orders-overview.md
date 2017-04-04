---
title: "Omówienie zamówień klienta"
description: "Ten temat zawiera informacje o zamówieniach klienta w sprzedaży detalicznej nowoczesnych POS (MPOS). Zamówienia klientów są również nazywane zamówień specjalnych. Temat zawiera omówienie powiązane parametry i transakcji przepływów."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>Omówienie zamówień klienta

Ten temat zawiera informacje o zamówieniach klienta w sprzedaży detalicznej nowoczesnych POS (MPOS). Zamówienia klientów są również nazywane zamówień specjalnych. Temat zawiera omówienie powiązane parametry i transakcji przepływów.

W świecie handlu wielokanałowego wielu sprzedawców uwzględnienie możliwości klienta zamówienia lub zamówień specjalnych, aby spełnić wymagania różnych produktu i spełnienia. Poniżej przedstawiono niektóre typowe scenariusze:

-   Klient chce, aby produkty, które mają być dostarczane na określony adres w określonym dniu.
-   Klient chce odebrać produkty w sklepie lub lokalizację, która różni się od magazynu lub lokalizacji, gdzie klient zakupił tych produktów.
-   Klient chce się odebrać produkty, które klient zakupił innemu użytkownikowi.

Detaliści również użyć zamówień klienta, aby zminimalizować utraconej sprzedaży, powodującymi przestojów w zapasach; w przeciwnym razie, ponieważ towar może być dostarczane lub odebrać w innym czasie lub miejsce.

## <a name="set-up-customer-orders"></a>Ustawianie zamówień klienta
Oto kilka parametrów, które mogą być ustawione na **handlu detalicznego parametry** stronę do definiowania sposobu realizacji zleceń klienta:

-   **Domyślne oprocentowanie lokaty** — określić kwotę, jaką klient musi zapłacić jako depozyt, zamówienie może zostać potwierdzona. Kwota depozytu domyślna jest obliczana jako procent wartości zamówienia. W zależności od uprawnień, Pracownik sklepu może być w stanie zastąpić kwoty za pomocą **zastąpienie wpłaty**.
-   **Procent opłaty za anulowanie** -Jeśli opłaty zostaną zastosowane po anulowaniu zamówienia danego klienta, należy określić kwotę takich opłat.
-   **Kod opłaty za anulowanie** -Jeśli opłatę zostaną zastosowane po anulowaniu zamówienia danego klienta, że opłaty zostaną odzwierciedlone pod kodu opłaty dodatkowej w zamówieniu sprzedaży w systemie Microsoft Dynamics AX. Za pomocą tego parametru można zdefiniować kod opłaty za anulowanie.
-   **Kodzie opłaty transportowej** – Detaliści mogą być obciążani dodatkową opłatą za wysyłkę towarów do odbiorcy. Kwota tej opłaty transportowej zostaną odzwierciedlone w obszarze kod opłaty z zamówienia sprzedaży w systemie Dynamics AX. Ten parametr służy do mapowania wysyłki kodu opłaty dodatkowej opłaty za wysyłkę na zamówienie klienta.
-   **Zwrot opłaty za wysyłkę** — Określ, czy podlegają zwrotowi koszty wysyłki, które są skojarzone z zamówieniem klienta.
-   **Maksymalna kwota bez zgody** -Jeśli koszty wysyłki są zwracane, określić maksymalną ilość wysyłki zwrotów opłat dla zamówień zwrotu. Jeśli kwota ta zostanie przekroczona, override menedżera jest wymagane w celu kontynuowania refundacji. Aby uwzględnić następujące scenariusze, zwrot opłaty za wysyłkę można przekraczać kwoty, którą pierwotnie została wypłacona:
    -   Opłaty są stosowane na poziomie nagłówka zamówienia sprzedaży, a po pewną ilość linii produktu jest zwracany, maksymalny zwrot opłaty za wysyłkę dozwolony dla produktów i ilości, nie można określić w sposób, który działa dla wszystkich klientów detalicznych.
    -   Dla każdego wystąpienia wysyłki zostały poniesione koszty wysyłki. Jeśli klient zwraca produkty wiele razy, a punkt sprzedaży detalicznej zasady określają, że punkt sprzedaży detalicznej ponosi koszty wysyłki zwrotnej opłat, opłaty za wysyłkę zwrotu będzie więcej niż opłaty rzeczywisty koszt wysyłki.

## <a name="transaction-flow-for-customer-orders"></a>Przepływ transakcji zamówień odbiorców
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Utwórz zamówienie odbiorcy w programie Retail POS nowoczesny

1.  Dodaj odbiorcę do transakcji.
2.  Dodaj produkty do koszyka.
3.  Kliknij **Utwórz zamówienie odbiorcy**, a następnie wybierz typ zamówienia. Typ zamówienia można albo **zamówienia klienta** lub **oferta**.
4.  Kliknij **statek zaznaczone** lub **Wyślij wszystko** do wysyłki produktów do adresu na koncie odbiorcy, określić Żądana data wysyłki i określić koszty wysyłki.
5.  Kliknij **zaznaczone podnieść** lub **odbioru wszystkich** na wybieranie produktów, które odbierze od bieżącego magazynu lub innego magazynu w określonym dniu.
6.  Zebrać kwotę depozytu, jeśli wymagany jest depozyt.

### <a name="edit-an-existing-customer-order"></a>Edytowanie istniejącego zamówienia odbiorcy

1.  Na stronie głównej kliknij **znajdowanie zamówienia**.
2.  Znajdź i zaznacz zamówienie do edycji. U dołu strony, kliknij przycisk **edytować**.

### <a name="pick-up-an-order"></a>Pobierz zamówienie

1.  Na stronie głównej kliknij **znajdowanie zamówienia**.
2.  Wybierz kolejność, aby odebrać. U dołu strony, kliknij przycisk **pobrania i pakowania**.
3.  Kliknij **odebrać**.

### <a name="cancel-an-order"></a>Anulowanie zamówienia

1.  Na stronie głównej kliknij **znajdowanie zamówienia**.
2.  Wybierz zamówienie, aby anulować. U dołu strony, kliknij przycisk **anulowanie**.

#### <a name="create-a-return-order"></a>Tworzenie zamówienia zwrotu

1.  Na stronie głównej kliknij **znajdowanie zamówienia**.
2.  Wybierz zamówienie, aby powrócić, zaznacz fakturę dla zamówienia, a następnie wybierz linię produktów dla towarów powrócić.
3.  U dołu strony, kliknij przycisk **zamówienia zwrotu**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Przepływ asynchroniczny transakcji zamówień odbiorców
Zamówienia mogą być tworzone z punktu sprzedaży (POS) klienta w tryb synchroniczny lub asynchroniczny tryb.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Włącz zamówień klienta ma być utworzony w trybie asynchronicznym

1.  W systemie Dynamics AX, kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**profilu POS**&gt;**profile funkcji**.
2.  Na **ogólne** ustawić skróconej **Tworzenie zamówienia klienta w trybie asynchroniczne** opcji w celu **tak**.

Po **Tworzenie zamówienia klienta w trybie asynchroniczne** opcja jest ustawiona na **tak**, zamówienia klientów są zawsze tworzone w trybie asynchronicznym, nawet jeśli Retail Transaction Service (RTS) jest dostępna. Jeśli ustawisz tę opcję do **nr**, zamówienia klientów są zawsze tworzone w trybie synchronicznym przy użyciu RTS. Po utworzeniu zamówienia klienta w trybie asynchronicznym, są pobierane i wstawiane do systemu Dynamics AX przez zadania ściągania (P). Odpowiedniego zamówienia sprzedaży są tworzone w systemie Dynamics AX po **Synchronizuj zamówienia** jest uruchamiana ręcznie lub za pomocą procesu wsadowego.

<a name="see-also"></a>Informacje dodatkowe
--------

[Hybrydowe zamówienia klienta](hybrid-customer-orders.md)


