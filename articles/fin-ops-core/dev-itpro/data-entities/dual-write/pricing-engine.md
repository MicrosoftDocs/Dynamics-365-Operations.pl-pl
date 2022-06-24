---
title: Synchronizacja na żądanie z aparatem wyceny aplikacji Supply Chain Management
description: W tym artykule opisano sposób używania aparatu kalkulacji cen w Dynamics 365 Supply Chain Management z Microsoft Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 259bdd5f868945c3857b045fbd3cbd4fceb26951
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862227"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Synchronizacja na żądanie z aparatem wyceny aplikacji Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management udostępnia aparat kalkulacji cen, który obsługuje umowy handlowe, cenniki, programy lojalnościowe dla klientów, promocje i rabaty. Aparat cenowy używa złożonych reguł w celu określenia najlepszej ceny dla danej oferty lub zamówienia. W przypadku korzystania z funkcji podwójnego odpisu na stronach **oferta** i **zamówienie** w Microsoft Dynamics 365 Sales można stosować zarówno cenę statyczną, jak i aparat cenowy z Supply Chain Management.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Użycie aparatu cenowego z Supply Chain Management w Sales

1. W Sales przejdź do **Sales \> Zamówienia**.
1. Wybierz **Nowy**, aby utworzyć nowe zamówienie lub wybierz istniejące zamówienie z listy **Moje zamówienia**.
1. Dodaj nowy wiersz zamówienia.
1. W przypadku tworzenia nowego zamówienia w okienku akcji wybierz opcję **Zamówienie cenowe**. Jeśli aktualizujesz istniejące zamówienie, wybierz **Ponownie oblicz** w okienku akcji.
1. Następujące kolumny są automatycznie wypełniane:

    - Szczegółowa ilość
    - Procent rabatu
    - Rabat
    - Kwota przed frachtem
    - Kwota frachtu
    - Podatek razem
    - Łączna kwota

> [!NOTE]
> Podobny proces ma zastosowanie podczas tworzenia ofert.

## <a name="how-it-works"></a>Jak działa

Gdy tworzysz zamówienie w Sales, jest ono natychmiast synchronizowane z Supply Chain Management przy użyciu wartości wprowadzonych w Sales. Po wybraniu opcji **Zamówienie cenowe** lub **Oferta cenowa** w Sales, Supply Chain Management oblicza cenę dla każdego wiersza zamówienia oraz sumę zamówień na podstawie reguł umowy handlowej zdefiniowanych w zarządzaniu łańcuchem dostaw. Nowe obliczone wartości są następnie synchronizowane z powrotem z Sales.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Ustaw opcje oceny umowy handlowej w Supply Chain Management

Produkt Supply Chain Management można skonfigurować tak, aby uwzględniał lub ignorował umowy handlowe podczas obliczania ceny zamówienia utworzonego w aplikacji Sales. Wykonaj poniższe czynności, aby skonfigurować tę opcję.

1. Zaloguj się do swojego środowiska Supply Chain Management.
1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
1. Na karcie **Ceny**, na skróconej **karcie Ocena umowy handlowej** dodaj lub usuń wymagany wiersz zasady **wprowadzania ręcznego**. Obecność lub brak tej zasady kontroluje, czy aparat cenowy Supply Chain Management automatycznie zastąpi cenę sprzedaży wprowadzoną w Sales.

    - Jeśli **Ręczny wpis** zasady *nie ma* w konfiguracji **Ocena umowy handlowej**, głównym ceną jest Supply Chain Management. Gdy użytkownik wybierze **Zamówienie cenowe** lub **Cena cenowa** w okienku akcji w Sales, wywoływany jest aparat cenowy Supply Chain Management, a cena sprzedaży wprowadzona w Sprzedaży jest zastępowana, chyba że jest równa cena sprzedaży obliczona w rozwiązaniu Supply Chain Management.
    - Jeśli **Ręczny wpis** zasady *ma* w konfiguracji **Ocena umowy handlowej**, głównym ceną jest Sales. Cena sprzedaży wprowadzona w Sales jest zabezpieczona przed automatycznym nadpisaniem, gdy użytkownik wybierze **Zamówienie cenowe** lub **Cennik** w okienku akcji w Sales.
    - Wiersze zamówienia i wiersze oferty, które mają wartość **cena jednostkowa** lub **rabat** wynoszącą *0* (zero) w sekcji Sales, są traktowane jako przypadek szczególny. Jeśli dostępna jest odpowiednia cena umowy handlowej, Supply Chain Management *zawsze* zastosuje ją do tych pól, niezależnie od konfiguracji **Ocena umowy handlowej**.

    Aby zapoznać się z przykładem każdego z tych przypadków, zobacz poniższe scenariusze.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>Przykładowy scenariusz 1: Ocena umowy handlowej bez opcji ręcznego wprowadzania

W tym scenariuszu ustawienie **Ocena umowy handlowej** w Supply Chain Management *nie* obejmuje zasad **Wprowadzanie ręczne**. Użytkownik działu sprzedaży wprowadza wiersz zamówienia, który ma niezerową cenę sprzedaży w dziale Sales, a w Supply Chain Management nie zdefiniowano ceny sprzedaży dla tej pozycji.

1. W przypadku sprzedaży użytkownik tworzy wiersz zamówienia o wartości **cena jednostkowa** 1 złotych (USD).
1. Wiersz zamówienia jest synchronizowany z Supply Chain Management dostaw z ceną sprzedaży wynoszącą 1 USD.
1. W przypadku sprzedaży użytkownik wybiera **porządek ceny** w okienku akcji.
1. Supply Chain Management wyszukuje odpowiednie ceny i rabaty, a następnie oblicza sumy. Ponieważ towar nie ma ceny sprzedaży w Supply Chain Management, obliczenie aktualizuje wiersz, tak aby miał cenę sprzedaży 0 USD.
1. Nowa cena sprzedaży wiersza jest synchronizowana z Sales.
1. W wyniku tego w Sales jest zamówienie z ceną 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>Przykładowy scenariusz 2: Wycena umowy handlowej z opcją ręcznego wprowadzania danych

W tym scenariuszu ustawienie **Ocena umowy handlowej** w Supply Chain Management *obejmuje* zasad **Wprowadzanie ręczne**. Użytkownik Sales wprowadza wiersz zamówienia o niezerowej cenie sprzedaży w Sales. Supply Chain Management zawiera umowę handlową, która ustala cenę 2 USD pozycji zamówione.

1. W dziale sprzedaży użytkownik tworzy wiersz zamówienia dla pozycji, która ma **Cenę za jednostkę** o wartości 1 USD.
1. Wiersz zamówienia jest synchronizowany z Supply Chain Management dostaw z ceną sprzedaży wynoszącą 1 USD.
1. W przypadku sprzedaży użytkownik wybiera **porządek ceny** w okienku akcji.
1. Ponieważ ustawienie **Ocena umowy handlowej** w Supply Chain Management obejmuje zasadę **Wprowadzanie ręczne** , cena sprzedaży nie jest zmieniana, nawet jeśli odpowiednia umowa handlowa określa inną cenę sprzedaży.
1. Cena sprzedaży pozostaje bez zmian w dziale Sales i w dziale Supply Chain Management.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>Przykładowy scenariusz 3. Ocena umowy handlowej dla towaru o zerowej cenie Sales

W tym scenariuszu ustawienie **Ocena umowy handlowej** w Supply Chain Management *obejmuje* zasad **Wprowadzanie ręczne**. Użytkownik działu sprzedaży wprowadza wiersz zamówienia, który ma cenę sprzedaży równą 0 (zero) w dziale sprzedaży. Supply Chain Management zawiera umowę handlową, która ustala cenę 2 USD pozycji zamówione.

1. W dziale Sprzedaż użytkownik tworzy linię zamówienia, która ma **Cenę jednostkową** o wartości 0 USD i **Rabat** o wartości 0 USD.
1. Wiersz zamówienia jest synchronizowany z Supply Chain Management dostaw z ceną sprzedaży wynoszącą 0 USD.
1. Ponieważ otrzymano wiersz zamówienia o cenie sprzedaży 0 (zero), funkcja Supply Chain Management wywołuje aparat cen, nawet jeśli jest włączona opcja **Wprowadzanie ręczne**. Mechanizm cenowy zwraca cenę sprzedaży 2 USD ustaloną na podstawie umowy handlowej i aktualizuje wiersz zamówienia w Supply Chain Management.
1. Zaktualizowana cena sprzedaży nie została jeszcze zsynchronizowana z wierszem zamówienia w Sales.
1. W przypadku sprzedaży użytkownik wybiera **porządek ceny** w okienku akcji.
1. Wiersz zamówienia w Supply Chain Management przechowuje cenę 2 USD, która jest teraz synchronizowana z linią Sprzedaż. Dlatego cena **na wartość jednostkową** wiersza zamówienia w sprzedaży jest aktualizowana z 0 USD na 2 USD.
1. W zakładce Sprzedaż użytkownik wprowadza nową **rabatu** o wartości 0,50 USD. Sprzedaż teraz oblicza, że **rozszerzona wartość** kwoty dla wiersza jest 1.50 USD.
1. Wiersz zamówienia jest synchronizowany z Supply Chain Management z **rabatem** o wartości 0,50 USD.
1. W przypadku sprzedaży użytkownik wybiera **porządek ceny** w okienku akcji.
1. Brak zmian cen i rabatów dla wiersza zamówienia w Sales.

## <a name="limitations"></a>Ograniczenia

Po wypełnieniu kolumn w Sales obowiązują następujące ograniczenia:

- Konfigurowanie opłat i alokacji opłat w Supply Chain Management nie jest replikowane w Sales.
- W przypadku cen nie są uwzględniane specjalne ceny detaliczne określone w kolumnie **Kanał detaliczny** na stronie wiersz zamówienia sprzedaży w Supply Chain Management.
- Nie są brane pod uwagę rabaty zdefiniowane w sekcji **Zarządzania przydziałem handlowym** w Supply Chain Management.
- Ceny nie są uwzględniane w umowach sprzedaży.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
