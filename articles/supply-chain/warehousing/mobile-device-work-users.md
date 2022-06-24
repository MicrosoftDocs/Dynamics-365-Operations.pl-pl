---
title: Konta użytkownika urządzenia przenośnego
description: W tym artykule opisano sposób konfigurowania i zarządzania kontami użytkowników, które umożliwiają pracownikom logowanie się i używanie aplikacji magazynu.
author: Mirzaab
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ffb4a9842f454094b41a1765d1438f6a40ae610b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851312"
---
# <a name="mobile-device-user-accounts"></a>Konta użytkownika urządzenia przenośnego

[!include [banner](../includes/banner.md)]

Gdy pracownik zaczyna korzystać z aplikacji magazynu, musi się zalogować, używając nazwy użytkownika i hasła. Z każdym pracownikiem w systemie można skojarzyć dowolną liczbę użytkowników aplikacji magazynu, a magazyny są zwykle skojarzone z każdym z tych użytkowników aplikacji magazynu. Różne opcje są również konfigurowane dla każdego pracownika, aby określić ustawienia domyślne i inne ustawienia odpowiednie do korzystania z aplikacji magazynu.

## <a name="set-up-the-required-worker-and-employee-records"></a>Konfigurowanie wymaganych rekordów pracowników i pracowników etatowych

Aby można było skonfigurować użytkowników aplikacji magazynu, każdy pracownik musi istnieć jako pracownik lub pracownik etatowy w rozwiązaniu Supply Chain Management w module **Human Resources**.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Konfigurowanie kont użytkownika urządzenia przenośnego

Po skonfigurowaniu wymaganych pracowników i pracowników etatowych w module Human Resources można przypisać do każdego z nich aplikację magazynu i skonfigurować inne opcje wpływające na sposób korzystania z tej aplikacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.
1. Aby zmodyfikować istniejącego pracownika, zaznacz go w okienku listy. Aby dodać nowy rekord, w okienku akcji wybierz opcję **Nowe**.
1. Jeśli jest ustawiany nowy pracownik, wykonaj następujące czynności:

    1. W polu **Pracownik** wybierz użytkownika docelowego z listy pracowników.
    1. Wybierz pozycję **Wybierz**.
    1. Na okienku akcji wybierz opcję **Zapisz**.

1. Domyślny profil może służyć jako przewodnik pracownika magazynu w stacji pakowania przez wymagany w tym miejscu proces. Domyślny profil może również służyć do zapisywania preferowanych ustawień profilu dla pracownika. Na skróconej karcie **Profil** ustaw następujące pola:

    - **Zasady pakowania kontenerów** — umożliwia wybór zasad pakowania kontenerów, które definiują sposób przetwarzania kontenerów w stacji pakowania. Zasady pakowania kontenerów wybrane w tym miejscu zostaną wstępnie wybrane dla pracownika po otwarciu stacji pakowania. Aby uzyskać więcej informacji, zobacz następujący wpis w blogu: [Poprawiona funkcjonalność pakowania](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **Identyfikator profilu pakowania** — umożliwia wybór identyfikatora profilu pakowania, który definiuje stosowane zasady pakowania i ustawienia kontenera. Jeśli wybrany identyfikator profilu pakowania jest skojarzony z zasadami pakowania kontenerów, nie będzie można zmienić ustawienia **Zasady pakowania kontenerów** na tej stronie.

1. Na skróconej karcie **Domyślna stacja pakowania** ustaw następujące pola, aby zdefiniować domyślną stację pakowania, która ma zastosowanie, gdy pracownik się podpisuje. W razie potrzeby, pracownik może wybrać inną stację pakowania.

    - **Lokalizacja** — umożliwia wybranie miejsca, w którym zlokalizowana jest domyślna stacja pakowania.
    - **Magazyn** — umożliwia wybranie magazynu, w którym zlokalizowana jest domyślna stacja pakowania.
    - **Lokalizacja** — umożliwia wybór lokalizacji domyślnej stacji pakowania.

1. Skrócona karta **Użytkownicy** umożliwia utworzenie dowolnej liczby kont użytkowników aplikacji magazynu dla wybranego pracownika. Każde konto jest skojarzone z określonym magazynem lub magazynami. Ten pasek narzędzi umożliwia dodawanie lub usuwanie kont użytkowników, resetowanie hasła dla wybranego konta lub przypisywanie magazynów do wybranego konta. Dla każdego konta użytkownika możesz ustawić następujące pola:

    - **Identyfikator użytkownika** — wprowadź unikatowy identyfikator.
    - **Nazwa użytkownika** — wprowadź nazwę identyfikatora.
    - **Domyślny magazyn** — ustawienie domyślnego magazynu, w którym pracownik zwykle pracuje. Tego paska narzędzi można używać do przypisywania dodatkowych magazynów, a pracownik może przełączać się między magazynami za pomocą pośredniego działania elementu menu urządzenia przenośnego **Zmień magazyn**.
    - **Nazwa menu** — wybierz menu główne, które będzie stroną początkową dla pracownika. Możliwość skonfigurowania menu głównego dla każdego pracownika jest przydatna, ponieważ umożliwia kontrolowanie struktury menu, z którego może korzystać każdy pracownik. Na przykład menu dla pracowników aktywnych tylko w obszarze wychodzącym można dostosować do zadań związanych z operacjami wychodzącymi w tym obszarze.
    - **Nieaktywne** — zaznaczone pole wyboru wskazuje, że konto użytkownika jest nieaktywne. Konto użytkownika jest automatycznie dezaktywowane, jeśli pracownik wprowadzi niewłaściwe hasło pięć razy w wierszu w aplikacji magazynu. Jednakże opcję można również zaznaczyć ręcznie. Wyczyść to pole wyboru, aby ponownie aktywować użytkownika.

1. Na skróconej karcie **Praca** ustaw następujące pola:

    - **Zezwalaj na zastępowanie lokalizacji pobrania** — Ustaw tę opcję na wartość *Tak*, aby pracownik mógł zastąpić lokalizację dla kroków pobrania. Ta możliwość może być przydatna, jeśli zapasy fizyczne nie odpowiadają lokalizacji sugerowanej przez system.
    - **Zezwalaj na zastępowanie lokalizacji odłożenia** — Ustaw tę opcję na wartość *Tak*, aby pracownik mógł zastąpić lokalizację dla kroków odłożenia. Ta możliwość może być użyteczna, jeśli sugerowana lokalizacja odłożenia jest obecnie pełna lub niedostępna albo gdy lokalizacje przemieszczania zostały zmienione.
    - **Zezwalaj na pobieranie nadmiarowe sprzedaży** — ustaw tę opcję na wartość *Tak*, aby pracownik mógł pobierać nadmiar zamówienia sprzedaży podczas pobierania. Aby uzyskać więcej informacji, zobacz [Nadmierne pobieranie dla zamówień sprzedaży i zamówień przeniesienia](over-picking-for-sales-and-transfer-orders.md).
    - **Zezwalaj na pobieranie nadmiarowe zamówienie przeniesienia** — ustaw tę opcję na wartość *Tak*, aby pracownik mógł pobierać nadmiar zamówienia przeniesienia podczas pobierania. Aby uzyskać więcej informacji, zobacz [Nadmierne pobieranie dla zamówień sprzedaży i zamówień przeniesienia](over-picking-for-sales-and-transfer-orders.md).
    - **Zezwalaj na przesuwanie zapasów za pomocą skojarzonej pracy** — ustaw tę opcję na wartość *Tak*, aby pracownik mógł przesuwać zapasy, które są już zarezerwowane lub jest już skojarzone z inną pracą. Aby uzyskać więcej informacji, zobacz [Przenoszenie zapasów za pomocą skojarzonej pracy w module Zarządzanie magazynem](move-inventory-associated-work.md).
    - **Zezwalaj na ręczną alokację pozycji** — tę opcję należy ustawić na wartość *Tak*, aby włączyć ręczną alokację dla pracownika podczas krótkiego pobierania. Alokacja pozycji prowadzi pracowników do pobrania zapasów z innej lokalizacji. Chociaż automatyczna ponowna alokacja jest dostępna dla wszystkich pracowników, ręczna ponowna alokacja wymaga jawnej konfiguracji dla pracownika. Możliwość kontrolowania ręcznej zmiany alokacji dla każdego pracownika może być przydatna, ponieważ umożliwia kontrolowanie widoczności, jaką ma każdy pracownik, gdy na przykład pobranie towaru z obszaru kwarantanny lub obszaru zbiorczego jest ograniczone do zaufanych pracowników. Aby uzyskać więcej informacji, zobacz następujący wpis w blogu: [Automatyczna i ręczna zmiana alokacji pozycji podczas krótkiego pobierania](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **Jest kierownikiem ds. liczników cyklu** — ustaw tę opcję na wartość *Tak*, aby pracownik był kierownikiem ds. licznika cyklu. W tym przypadku wszystkie liczniki cyklu, które pracownik wykonuje w aplikacji magazynu, zostaną natychmiast zatwierdzone. Pola **Maksymalny limit procentu**, **Maksymalny limit ilości** i **Maksymalny limit wartości** nie są brane pod uwagę dla pracowników, dla których ta opcja ma wartość *Tak*.
    - **Maksymalny limit procentowy** — wprowadź najwyższy dozwolony limit, o który wyliczenie cyklu może różnić się od oczekiwanej liczby bez konieczności zatwierdzenia wyliczenia cyklu przez kierownika.
    - **Maksymalny limit ilości** — służy do wprowadzania łącznej ilości, która może różnić się od oczekiwanej ilości (w jednostkach) bez konieczności zatwierdzania przez kierownika ds. licznika cyklu.
    - **Maksymalny limit wartości** — wprowadź najwyższą ilość, o którą koszt zapasów może różnić się od oczekiwanego kosztu bez konieczności zatwierdzenia wyliczenia cyklu przez kierownika.

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Po dodaniu nowego konta użytkownika pojawi się okno dialogowe **Ustaw hasło**, w którym można utworzyć proste hasło, za pomocą którego użytkownik może zalogować w aplikacji mobilnej. Wprowadź hasło proste dwa razy, a następnie wybierz przycisk **Zapisz hasło**, aby kontynuować.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Ustaw język, formaty liczb i strefę czasową dla każdego użytkownika aplikacji magazynowej

Gdy pracownik rejestruje się do aplikacji mobilnej Warehouse Management, język, formaty liczb i strefa czasowa zmieniają się tak, aby odpowiadały preferencjom tego pracownika. Ustawienia konta pracownika wybranego w kroku 3 w sekcji [Konfiguracja kont użytkowników urządzeń przenośnych](#set-wma-users) określają używane ustawienia. Jeśli dla każdego użytkownika są wymagane osobne ustawienia, należy użyć innych kont pracowników. Poniżej przedstawiono procedurę zmiany języka, formatów liczb i stref czasowych dla poszczególnych użytkowników aplikacji magazynu.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.
1. Znajdź nazwisko pracownika, którego chcesz skonfigurować. Upewnij się, że pracownik ma wszystkie wymagane konta użytkowników aplikacji magazynu, które są wymienione na skróconej karcie **Użytkownicy**. Utwórz nowego pracownika i/lub dodaj konta użytkowników aplikacji magazynowych zgodnie z potrzebami, zgodnie z krokami w sekcji [Konfigurowanie kont użytkowników urządzeń przenośnych](#set-wma-users).
1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
1. Wybierz konto użytkownika, w którym kolumna **Osoba** zawiera imię i nazwisko pracownika, którego znaleziono w kroku 2.

    > [!IMPORTANT]
    > Wartości **Identyfikator użytkownika** wyświetlane na stronie **Użytkownicy** *nie* są powiązane z wartością wyświetlaną na skróconej karcie **Użytkownicy** na stronie **Pracownik**, która została otwarta w kroku 1.

1. W Okienku akcji wybierz **Opcje użytkownika**.
1. Na karcie **Preferencje** ustaw następujące pola:

    - **Język** — wybierz język preferowany przez pracownika. To pole steruje także formatem liczby wyświetlanym w aplikacji magazynu.
    - **Format daty, czasu i liczby** — wybierz format daty i czasu preferowany przez pracownika. Aplikacja magazynu używa formatu liczby skojarzonego z językiem wybranym w polu **Język** zamiast tego ustawienia.
    - **Strefa czasowa** — umożliwia wybór strefy czasowej, w której pracuje pracownik. To pole wpływa na sygnaturę czasową wszystkich rejestracji, które pracownik wykonuje za pomocą aplikacji.

> [!NOTE]
> W niektórych przypadkach aplikacja magazynu nie będzie w stanie odnaleźć określonych ustawień pracownika, które ustalają język, formaty liczb i strefę czasową. Obowiązują następujące zasady:
>
> - Jeśli aplikacja nie jest połączona ze środowiskiem Supply Chain Management (na przykład przy pierwszym uruchomieniu aplikacji po jej instalacji), używany jest język urządzenia lokalnego. Gdy zmienia się język urządzenia, zmienia się także język aplikacji. Aby uzyskać więcej informacji dotyczących konfigurowania języka dla lokalnego urządzenia, zapoznaj się z dokumentacją urządzenia i/lub systemu operacyjnego.
> - Jeśli aplikacja jest połączona ze środowiskiem Supply Chain Management, ale nie ustawiono żadnych preferencji dla zalogowanego pracownika, język, formaty liczb i strefa czasowa są wybierane na podstawie konta skojarzonego z identyfikatorem klienta, którego urządzenie używa do nawiązywania połączenia z rozwiązaniem Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Tworzenie i konfigurowanie konta użytkownika w programie Supply Chain Management](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Jeśli użytkownik zauważy, że dla rejestracji wykonanych za pomocą aplikacji magazynu są wyświetlane niepoprawne sygnatury czasowe, konieczne może być skorygowanie strefy czasowej ustawionej dla konta użytkownika, którego pracownicy używają do logowania się i/lub uwierzytelniania w rozwiązaniu Supply Chain Management. Jak już wymieniono, ustawienie strefy czasowej może pochodzić z konta użytkownika używanego do logowania się do aplikacji magazynu, zgodnie z ustawieniami na stronie **Pracownik**. Jeśli nie ustawiono konta użytkownika na stronie **Pracownik**, strefa czasowa pochodzi ze strefy czasowej konta użytkownika skojarzonego z identyfikatorem klienta używanym do uwierzytelniania, zgodnie z ustawieniami na stronie **[aplikacje Azure Active Directory](install-configure-warehouse-management-app.md)**.
