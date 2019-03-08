---
title: Śledzenie prowizji w punkcie sprzedaży (POS) przy użyciu grup sprzedaży
description: 'W sklepach detalicznych typową praktyką jest śledzenia sprzedaży realizowanej przez pracowników, którzy mają bezpośredni kontakt z odbiorcami: udzielają im pomocy, proponują zakup powiązanych lub dodatkowych produktów, przetwarzają transakcje itd.'
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ed4f9b3055e164600827b62d57b7a5068edb3b1a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "325119"
---
# <a name="track-commissions-in-the-point-of-sale-pos-by-using-sales-groups"></a>Śledzenie prowizji w punkcie sprzedaży (POS) przy użyciu grup sprzedaży

[!include [banner](includes/banner.md)]

W sklepach detalicznych typową praktyką jest śledzenia sprzedaży realizowanej przez pracowników, którzy mają bezpośredni kontakt z odbiorcami: udzielają im pomocy, proponują zakup powiązanych lub dodatkowych produktów, przetwarzają transakcje itd.

Śledzenie sprzedaży wykonywanej przez przedstawicieli handlowych pozwala mierzyć ich umiejętności sprzedażowe, natomiast w przypadku kasjerów pozwala mierzyć szybkość i sprawność działania. Śledzenie sprzedaży realizowanej przez przedstawicieli handlowych jest także często wykorzystywane do obliczania prowizji i innych premii.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Konfigurowanie pracownika jako przedstawiciela handlowego w aplikacji punktu sprzedaży

Gdy pracownik zostanie dodany do grupy sprzedaży, kwalifikują się do otrzymywania prowizji i może być identyfikowany jako przedstawiciel handlowy w systemie. Pracownik, który nie znajduje się w grupy sprzedaży, nie kwalifikuje się do otrzymywania prowizji i nie będzie wymieniony jako przedstawiciel handlowy w aplikacji punktu sprzedaży (POS). W aplikacji punktu sprzedaży lista przedstawicieli handlowych jest tworzona na podstawie wszystkich grup sprzedaży zawierających co najmniej jednego pracownika przypisanego do sklepu. Lista jest wyświetlana w aplikacji POS w postaci kombinacji identyfikatora grupy sprzedaży i nazwy użytkownika (identyfikator: nazwa). Pracownikom można przypisać domyślną grupę sprzedaży w celu obsługi scenariuszy, gdzie sprzedawca detaliczny chce automatycznie ustawiać przedstawicieli handlowych w wierszach w aplikacji POS. Użytkownicy mogą wybierać spośród wszystkich grup sprzedaży, których pracownik jest członkiem.

## <a name="functionality-profile-settings"></a>Ustawienia profilu funkcji

Dla sklepu istnieje wiele ustawień profilu funkcji, które w aplikacji punktu sprzedaży decydują o przepływie operacji i procesie z udziałem przedstawicieli handlowych.

<table>
<thead>
<tr>
<th>Profil</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Domyślnie kasjer, gdy jest dostępny</td>
<td>Jeśli ta opcja jest włączona, aplikacja POS będzie automatycznie wypełniać wiersze transakcji domyślną grupą sprzedaży bieżącego kasjera. Jeśli kasjer nie ma zdefiniowanej domyślnej grupy sprzedaży, wartość nie będzie ustawiona. Użytkownik może ręcznie ustawić grupę sprzedaży przy użyciu przycisku z siatki przycisków aplikacji POS.</td>
</tr>
<tr>
<td>Monituj o podanie przedstawiciela handlowego</td>
<td>Ta opcja ma trzy możliwe wartości:
<ul>
<li><strong>Nie</strong> — Jeśli jest zaznaczona ta wartość, użytkownik nie będzie monitowany o wybranie grupy sprzedaży. Wartość może być ustawiona także przy użyciu domyślnej grupy sprzedaży kasjera lub ręcznie przy użyciu przycisku z siatki przycisków aplikacji POS.</li>
<li><strong>Rozpocznij transakcję</strong> — Jeśli jest zaznaczona ta wartość i albo opcja <strong>Domyślnie kasjer</strong> nie jest włączona, albo bieżący kasjer nie ma domyślnej grupy sprzedaży, użytkownik będzie monitowany o wybranie grupy sprzedaży na początku każdej transakcji. Wybranie grupy sprzedaży w oknie monitu spowoduje domyślne ustawienie we wszystkich kolejnych wierszach wybranej grupy sprzedaży. Użytkownik może ręcznie ustawić grupę sprzedaży przy użyciu przycisku z siatki przycisków aplikacji POS.</li>
<li><strong>Dla każdego wiersza</strong> — Jeśli jest zaznaczona ta wartość i albo opcja <strong>Domyślnie kasjer</strong> nie jest włączona, albo bieżący kasjer nie ma domyślnej grupy sprzedaży, użytkownik będzie monitowany o wybranie grupy sprzedaży po dodaniu każdego wiersza. Użytkownik może ręcznie ustawić grupę sprzedaży przy użyciu przycisku z siatki przycisków aplikacji POS.</li>
</ul>
</td>
</tr>
<tr>
<td>Wymagaj</td>
<td>Ta opcja działa tylko wtedy, gdy w aplikacji punktu sprzedaży skonfigurowano monitowanie o podanie przedstawiciela handlowego. Jeśli jest włączona, użytkownik będzie musiał przed kontynuowaniem wybrać grupę sprzedaży. W przeciwnym razie użytkownik będzie monitowany, ale może anulować monit i kontynuować bez dokonywania wyboru. Po dodaniu wiersza użytkownik posiadający wystarczające uprawnienia może usunąć grupę sprzedaży z wiersza. W tej sytuacji opcja „Wymagaj przedstawiciela handlowego” nie jest wymuszana.</td>
</tr>
</tbody>
</table>

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Wyświetlanie informacji o przedstawicielach handlowych na ekranie transakcji w aplikacji POS

Układ i zawartość ekranu transakcji w aplikacji punktu sprzedaży można konfigurować przy użyciu projektanta układu ekranu, a układy ekranu można przypisywać do sklepów, kas lub pracowników. Pole **Przedstawiciel handlowy** można dodać do karty Wiersze w okienku pokwitowania.  Spowoduje to wyświetlenie identyfikatora odnośnej grupy sprzedaży dla każdego wiersza na ekranie transakcji.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Dodawanie operacji przedstawicieli handlowych do siatek przycisków aplikacji POS

W aplikacji punktu sprzedaży użytkownicy mogą konfigurować siatki przycisków, które się znajdą w układach ekranu i umożliwią dostęp do operacji aplikacji. Następujące operacje aplikacji POS można przypisać do przycisków w siatkach przycisków dotyczących przedstawicieli handlowych.

| Operacja                                 | opis |
|-------------------------------------------|-------------|
| Ustaw przedstawiciela handlowego w wierszu          | Ta operacja aplikacji POS wyświetla listę kwalifikujących się grup sprzedaży (identyfikator: nazwa) dla sklepu. Zaznaczenie grupy sprzedaży na tej liście spowoduje ustawienie wartości w bieżącym wierszu transakcji. |
| Wyczyść przedstawiciela handlowego w wierszu        | Ta operacja aplikacji POS usuwa bieżącą wartość grupy sprzedaży z bieżącego wiersza transakcji. |
| Ustaw przedstawiciela handlowego w transakcji   | Ta operacja aplikacji POS wyświetla listę kwalifikujących się grup sprzedaży (identyfikator: nazwa) dla sklepu. Zaznaczenie grupy sprzedaży na tej liście spowoduje ustawienie domyślnej wartości w bieżącej transakcji. Wartość zostanie ustawiona we wszystkich istniejących wierszach bez przypisanej grupy sprzedaży oraz we wszystkich później dodawanych wierszach. |
| Wyczyść przedstawiciela handlowego w transakcji | Ta operacja aplikacji POS usuwa bieżącą domyślną wartość grupy sprzedaży z bieżącej transakcji. Nie wpływa na żadne wiersze już istniejące w transakcji. |

## <a name="calculating-commissions"></a>Naliczanie prowizji

Prowizja jest obliczana dla pracowników we wskazanych grupach sprzedaży w momencie księgowania zestawienia lub zamówienia sprzedaży. Kwota prowizji jest określana na podstawie udziału pracownika w prowizji, zgodnie z definicją w grupie sprzedaży oraz odnośnymi ustawieniami obliczania prowizji dla odbiorcy i/lub produktów w transakcji.
