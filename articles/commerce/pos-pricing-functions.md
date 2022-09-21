---
title: Funkcje cenowe w POS
description: W tym artykule opisano różne funkcje cen i rabatów w aplikacji punktu sprzedaży (POS) Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 210798ac192ee251594ec8ff9d23dab31ec2043e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473695"
---
# <a name="pricing-functions-in-pos"></a>Funkcje cenowe w POS

[!include [banner](includes/banner.md)]

W tym artykule opisano różne funkcje cen i rabatów w aplikacji punktu sprzedaży (POS) Microsoft Dynamics 365 Commerce.

Aplikacja Dynamics 365 Commerce POS zapewnia bogate możliwości, które umożliwiają pracownikom pierwszej linii wykonywanie operacji handlowych w sklepie. W poniższej tabeli przedstawiono funkcje ceny i rabatu, które są obecnie dostępne w aplikacji.

| Funkcja                       | Operacje punktu sprzedaży |
|--------------------------------|----------------|
| Wyświetl ceny                    | [Sprawdzanie ceny](#price-check) |
| Wyświetl rabaty                 | [Wyświetl wszystkie rabaty](#view-all-discounts)<br>[Wyświetl dostępne rabaty](#view-available-discounts) |
| Zastąp ceny                | [Zastąpienie ceny](#price-override) |
| Zastosuj lub usuń rabaty      | [Kwota rabatu wiersza](#line-discount-amount)<br>[Procent rabatu wiersza](#line-discount-percent)<br>[Łączna kwota rabatu](#total-discount-amount)<br>[Procent rabatu ogółem](#total-discount-percent)<br>[Usuń z transakcji rabaty systemowe](#remove-system-discounts-from-transaction)<br>[Ponownie zastosuj rabaty systemu](#reapply-system-discounts) |
| Zastosuj lub usuń kupony        | [Dodaj kod kuponu](#add-coupon-code)<br>[Usuń kod kuponu](#remove-coupon-code) |
| Oblicz ceny i rabaty | [Oblicz ponownie](#recalculate) |

Aby uzyskać informacje dotyczące sposobu konfigurowania poprzednich operacji w aplikacji poS oraz o tym, czy obsługują one tryb offline, zobacz [Operacje w trybie online i offline punkt sprzedaży (POS)](pos-operations.md).

## <a name="price-check"></a>Sprawdzanie ceny

Operacja **sprawdzania ceny** umożliwia użytkownikom w programie POS wyszukiwania wstępnie skonfigurowanych cen określonego produktu.

## <a name="view-all-discounts"></a>Wyświetl wszystkie rabaty

Operacja **Wyświetlanie wszystkich rabatów** umożliwia użytkownikom punktu sprzedaży wyszukiwania wszystkich efektywnych promocji, które są obecnie uruchomione w kanale sklepu. W szczególności w tej operacji są wyszczególniane wszystkie rabaty, które są zgodne z następującymi warunkami:

- Grupa cenowa rabatu jest zgodna z grupą cenową sklepu.
- Grupa cenowa rabatu jest zamapowana na przynależność lub do programu lojalnościowego.
- Grupa cenowa rabatu jest zamapowana na katalog skojarzony z danym sklepem.

Strona **Zobacz wszystkie rabaty** pokazuje tylko rabaty, które nie konkurują z żadnym już zastosowanym rabatem. To zachowanie pomaga zagwarantować, że jeśli sprzedawca poinformuje klienta o rabacie, a klient podejmie wymaganą akcję (np. klient kupuje jeszcze jedną pozycję, aby uzyskać 10% rabatu), rabat zostanie zastosowany do transakcji. Rabaty kuponowe są wyświetlane tylko wtedy, gdy włączony jest parametr **Zastosuj bez kodu kuponu**.

Wewnątrz operacji **Wyświetlanie wszystkich rabatów** użytkownicy punktu dostępu mogą wyszukiwać rabaty według nazwy i opisu. Rabaty mogą też filtrować na podstawie tego, czy potrzebują kuponu.

## <a name="view-available-discounts"></a>Wyświetl dostępne rabaty

Operacja **Wyświetlanie dostępnych rabatów** umożliwia użytkownikom punktu sprzedaży wyświetlanie wszystkich rabatów, które są stosowane do wybranego wiersza w transakcji lub w całej transakcji. Rabaty mające zastosowanie do wybranego wiersza obejmują rabaty, które zostały już zastosowane, oraz rabaty, które nie zostały jeszcze zastosowane, ale mogą zostać zastosowane (na przykład rabaty za skład zamówienia wymagające dodatkowych towarów). Jeśli stosowny rabat jest połączony z kuponem, dla którego jest włączony parametr **Zastosuj bez kodu kuponu**, użytkownik programu POS może również użyć funkcji **Zastosuj kupon** wewnątrz tej operacji w celu zrealizowania kuponu bezpośrednio bez konieczności wprowadzania lub skanowania kodów kuponów lub kodów kreskowych kuponów.

## <a name="price-override"></a>Zastąpienie ceny

Operacja **zastępowania ceny** umożliwia użytkownikom w programie POS zastępowanie ceny sprzedaży produktu w transakcji. Ta operacja działa tylko dla produktów skonfigurowanych w taki sposób, aby zezwalały na zastępowanie cen.

## <a name="line-discount-amount"></a>Kwota rabatu wiersza

Operacja **kwota rabatu wiersza** umożliwia użytkownikom w programie POS wprowadzanie kwoty rabatu dla wiersza towaru w transakcji. Ta operacja dotyczy tylko towarów, dla których można udzielać rabatów, i jest zgodne z wartością **kwoty maksymalnego rabatu wiersza** określoną dla użytkownika w grupie uprawnień w programie POS.

## <a name="line-discount-percent"></a>Procent rabatu wiersza

Operacja **Procent rabatu wiersza** umożliwia użytkownikom w programie POS wprowadzanie procent rabatu dla wiersza towaru w transakcji. Ta operacja dotyczy tylko towarów, dla których można udzielać rabatów, i jest zgodne z wartością **Maksymalny procent rabatu na wiersz** określoną dla użytkownika w grupie uprawnień w programie POS.

## <a name="total-discount-amount"></a>Łączna kwota rabatu

Operacja **Całkowita kwota rabatu** umożliwia użytkownikom w programie POS wprowadzanie kwoty rabatu dla transakcji. Ta operacja dotyczy tylko towarów, dla których można udzielać rabatów, i jest zgodne z wartością **Maksymalna łączna kwota rabatu** określoną dla użytkownika w grupie uprawnień w programie POS. Jeśli wprowadzona kwota rabatu przekracza maksymalną kwotę rabatu ogółem, operacja jest zablokowana i nie jest wyzwalany przepływ zastępowania uprawnień. Obecnie nie można zastosować łącznej kwoty rabatu do koszyka, który ma kombinację towarów sprzedaży i towarów zwracanych.

## <a name="total-discount-percent"></a>Procent rabatu ogółem

Operacja **Całkowity procent rabatu** umożliwia użytkownikom w programie POS wprowadzanie procentu rabatu dla transakcji. Ta operacja dotyczy tylko towarów, dla których można udzielać rabatów, i jest zgodne z wartością **Maksymalny całkowity procent rabatu** określoną dla użytkownika w grupie uprawnień w programie POS. Jeśli wprowadzony procent rabatu przekracza maksymalny łączny procent rabatu, operacja jest blokowana i nie jest wyzwalany żaden przepływ zastępowania uprawnień. Obecnie nie można zastosować całkowitego rabatu procentowego do koszyka, który zawiera zarówno przedmioty sprzedaży, jak i przedmioty zwracane.

## <a name="remove-system-discounts-from-transaction"></a>Usuń z transakcji rabaty systemowe

Operacja **usuwania rabatów systemowych z transakcji** umożliwia użytkownikom w programie POS usunięcie wszystkich zastosowanych rabatów systemowych (w tym rabatów opartych na kuponach) z transakcji. Po wykonaniu tej operacji aparat cen rozpoczyna wykluczanie rabatów systemowych z zakresu obliczania rabatów. Operacja **usuwania rabatów systemowych** z transakcji nie powoduje usunięcia rabatów ręcznych.

## <a name="reapply-system-discounts"></a>Ponownie zastosuj rabaty systemu

Operacja **Ponownie zastosuj rabaty systemowe** umożliwia użytkownikom punktu sprzedaży ponowne zastosowanie rabatów obliczonych przez system do transakcji, jeśli rabaty zostały usunięte za pomocą operacji **Usuń rabaty systemowe z transakcji**. Po wykonaniu tej operacji silnik cenowy zaczyna uwzględniać wszystkie rabaty systemowe w zakresie kalkulacji rabatów.

## <a name="add-coupon-code"></a>Dodaj kod kuponu

Operacja **Dodaj kod kuponu** umożliwia użytkownikom w programie POS dodawanie kuponu do transakcji przez wprowadzenie kodu kuponu. Alternatywnie użytkownicy POS mogą zeskanować kod kreskowy kuponu lub wprowadzić go za pomocą klawiatury numerycznej na ekranie **Transakcje**.

## <a name="remove-coupon-code"></a>Usuń kod kuponu

Operacja **Usuń kod kuponu** umożliwia użytkownikom w programie POS wybieranie i usuwanie jednego lub wielu kuponów, które są obecnie stosowane do transakcji.

## <a name="recalculate"></a>Oblicz ponownie

Operacja **Ponowne obliczanie umożliwia** użytkownikom w programie POS wyzwalanie kalkulacji cen na żądanie. Ta operacja jest wymagana, gdy jest włączona funkcja obliczania cen i/lub opóźnionych cen, a użytkownik aplikacji w programie POS chce ponownie obliczenia cen i rabatów po zmianie koszyka lub zamówienia. Operacja **ponownego przeliczania** zawsze przelicza całe zamówienie. Nie można jej użyć do ponownego przeliczenia wybranych wierszy sprzedaży. Aby zastosować rabaty ręczne do zablokowanego wiersza sprzedaży w programie POS, użytkownicy w pierwszej kolejności muszą użyć operacji **Ponowne obliczanie**, aby odblokować wszystkie wiersze sprzedaży.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
