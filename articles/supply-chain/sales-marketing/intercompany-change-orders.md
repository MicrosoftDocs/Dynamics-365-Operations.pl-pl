---
title: Zmienianie zamówień międzyfirmowych
description: W tym temacie wyjaśniono zmianę funkcjonalności zamówień międzyfirmowych
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 1129794bf0ac6513770f8b2a0eeb7fb6154d7942
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548480"
---
# <a name="change-intercompany-orders"></a>Zmienianie zamówień międzyfirmowych

[!include [banner](../../includes/banner.md)]

Jeśli zmienisz międzyfirmowe zamówienie sprzedaży lub zamówienie zakupu, odpowiednie zamówienie sprzedaży lub zamówienie zakupu w odpowiedniej firmie również odzwierciedla tę zmianę.

## <a name="adding-new-lines"></a>Dodawanie nowych wierszy

Nowe wiersze można dodawać do międzyfirmowe zamówienie sprzedaży zamówienia zakupu, jeśli oryginalne zamówienie sprzedaży jest częścią łańcucha zamówień międzyfirmowych. Możesz również dodać nowe wiersze, jeśli oryginalne zamówienie sprzedaży nie jest dostawą bezpośrednią. Jeśli oryginalne zamówienie sprzedaży jest dostawą bezpośrednią, możesz dodać nowe wiersze zamówienia do międzyfirmowego zamówienia sprzedaży i zamówienia zakupu tylko wtedy, gdy pole **Zezwalaj na tworzenie pośrednie** jest zaznaczone na **Ustawienia międzyfirmowe** skrócona karta na skróconej karcie oryginalne zamówienie sprzedaży.

## <a name="changing-prices-and-discounts"></a>Zmienianie cen i rabatów

Możesz zmienić ceny i rabaty, jeśli na stronie **Międzyfirmowe** zaznaczono pola wyboru **Zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu**.

Zmiana ceny jednostkowej jednego z istniejących wierszy w międzyfirmowym zamówieniu sprzedaży powoduje zmianę ceny jednostkowej w międzyfirmowym zamówieniu zakupu.

Jeśli zmienisz dowolne z pól rabatu w wierszu międzyfirmowego zamówienia sprzedaży, odpowiednie pola rabatu w międzyfirmowym zamówieniu zakupu zostaną zaktualizowane.

## <a name="changing-and-adding-new-charges"></a>Zmienianie i dodawanie nowych opłat

Możesz zmienić opłaty, jeśli na stronie **Międzyfirmowe** zaznaczono pola wyboru **Zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu**.

Jeśli dodasz nową opłatę do nagłówka międzyfirmowego zamówienia sprzedaży i nową opłatę do międzyfirmowego wiersza sprzedaży, obie opłaty są kopiowane do międzyfirmowego zamówienia zakupu. W związku z tym międzyfirmowe zamówienie sprzedaży i międzyfirmowe zamówienie zakupu mają tę samą łączną kwotę. Opłaty nigdy nie są kopiowane do oryginalnego zamówienia sprzedaży.

## <a name="copying-a-fee"></a>Kopiowanie opłaty

Aby skopiować opłatę do oryginalnego zamówienia sprzedaży, utwórz je jako nowy wiersz sprzedaży z towarem typu **Usługa**.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Zmienianie ilości w wierszach międzyfirmowego zamówienia sprzedaży i zakupu oraz usuwanie tych wierszy

Możesz zmienić ilość lub usunąć wiersz międzyfirmowego zamówienia zakupu lub wiersz zamówienia sprzedaży tylko wtedy, gdy wiersz został utworzony bezpośrednio z formularza **Zamówienie sprzedaży** lub **Zamówienie zakupu**. Ta zmiana powoduje, że źródłem jest międzyfirmowe zamówienie zakupu lub zamówienie sprzedaży lub wiersze zamówienia.

## <a name="origins-of-orders-and-order-lines"></a>Początki zamówień i wierszy zamówień

Zamówienia międzyfirmowe i wiersze zamówień mogą mieć jedno z dwóch źródeł:

- **Pochodny** – Zamówienie zostało utworzone automatycznie z łańcucha zamówień międzyfirmowych.
- **Źródło**  — zamówienie zostało utworzone ręcznie przez użytkownika.

Pochodzenie jest wskazane w nagłówku zamówienia międzyfirmowych zamówień zakupu i zamówień sprzedaży w polu **Pochodzenie**. To pole znajduje się na skróconej karcie **Ustawienia międzyfirmowe** w zamówieniu sprzedaży i na skróconej karcie **Ustawienia** w zamówieniu zakupu.

Źródła **pochodne** i **źródłowe** dotyczą tylko zamówień międzyfirmowych. Dlatego pole **Pochodzenie** jest puste w przypadku wszystkich innych zamówień sprzedaży, zamówień zakupu i wierszy zamówienia. Jest ono również puste w oryginalnym zamówieniu sprzedaży.

## <a name="example-derived-origin"></a>Przykład: Pochodzenie pochodne

Tworzysz oryginalne zamówienie sprzedaży dla klienta zewnętrznego. Zamówienie to zawiera jeden wiersz zamówienia. To oryginalne zamówienie sprzedaży tworzy międzyfirmowe zamówienie zakupu zawierające jeden wiersz zamówienia, który tworzy międzyfirmowe zamówienie sprzedaży zawierające jeden wiersz zamówienia. Nagłówek międzyfirmowego zamówienia zakupu i wiersz zamówienia są tworzone automatycznie na podstawie oryginalnego zamówienia sprzedaży.

Wartość pola **Źródło** na skróconej karcie **Ustawienia** międzyfirmowe zamówienie zakupu skróconej karcie **ustawień międzyfirmowych** nagłówków międzyfirmowe zamówienie sprzedaży ma wartość **Pochodna**. Wartość pola **Źródło** na karcie **Szczegóły wiersza** w wierszach zamówienia zakupu i wiersza zamówienia sprzedaży również jest **pochodna**.

Jeśli wiersz zamówienia ma pochodzenie **Pochodne**, nie można go bezpośrednio usunąć. Wiersz zamówienia można usunąć tylko ze źródła, które utworzyło wiersz zamówienia. Możesz również zmienić zamawianą ilość tylko ze źródła, które utworzyło wiersz zamówienia.

Jeśli oryginalne zamówienie sprzedaży i wiersz oryginalnego zamówienia sprzedaży są częścią łańcucha zamówień międzyfirmowych, to zamówione ilości można zmienić w oryginalnym zamówieniu sprzedaży i można usunąć wiersze zamówienia z oryginalnego zamówienia sprzedaży.

## <a name="example-source-origin"></a>Przykład: źródło pochodzenia

Użytkownik tworzy zamówienie zakupy dla dostawcy międzyfirmowego. Międzyfirmowe zamówienie zakupu i wiersz zamówienia mają pochodzenie **Źródło**. W związku z tym to międzyfirmowe zamówienie zakupu jest kontrolerem, a międzyfirmowe zamówienie sprzedaży, które jest tworzone automatycznie w firmie dostawcy, ma pochodzenie **Pochodne**.

Ponadto zamówionych ilości wiersza zamówienia utworzonego w międzyfirmowym zamówieniu zakupu nie można zmienić w międzyfirmowym zamówieniu sprzedaży. Wiersz zamówienia można usunąć tylko z międzyfirmowego zamówienia zakupu. Jeśli do międzyfirmowego zamówienia sprzedaży zostanie dodany nowy wiersz, wiersz międzyfirmowego zamówienia sprzedaży ma pochodzenie **Źródło**.

Gdy oryginalne zamówienie sprzedaży jest częścią łańcucha zamówień międzyfirmowych, zamówienia międzyfirmowe i wiersze zamówienia międzyfirmowego można zawsze kontrolować z oryginalnego zamówienia sprzedaży.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
