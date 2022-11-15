---
title: Automatyzacja dostaw produktów na zamówienie
description: W tym artykule opisano sposób skonfigurowania i użycia różnych ulepszeń dodawanych przez funkcję automatyzacji dostaw od produktów do zamówienia.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d376c2f4d8514a4e6122e2e94455d57a39d2babf
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740202"
---
# <a name="make-to-order-supply-automation"></a>Automatyzacja dostaw produktów na zamówienie

[!include [banner](../includes/banner.md)]

Funkcja *automatyzacji dostaw na* zamówienie dodaje kilka ulepszeń rozwiązania Microsoft Dynamics 365 Supply Chain Management. Te ulepszenia umożliwiają wykonywanie następujących zadań:

- Umożliwia wyświetlenie obciążenia zdolności produkcyjnych zasobu dla okresu zdefiniowanego przez użytkownika, co pozwala na długoterminowe ocenianie obciążenia zdolności produkcyjnych.
- Zwiększ elastyczność, kontrolując tolerancję opóźnienia (liczby dni z ujemnym skutkiem) dla każdego planu głównego.
- Zachowaj dostępność produktów dla zamówień w ostatniej chwili i zoptymalizuj wykorzystanie istniejącej podaży, ustalając najnowszą możliwą podaż z popytem, zamiast korzystać z pierwszej możliwej podaży.
- Elastyczne przydzielanie komponentów dla zleceń produkcyjnych po ustaleniu, aby system mógł zoptymalizować pod kątem zmian popytu w ostatniej chwili. Oznacza to oznaczanie tylko jednego poziomu.
- Kontrolowanie zasad realizacji dla każdego zamówienia sprzedaży. Ustawienia domyślne są brane pod uwagę w ustawieniach odbiorcy.
- Popraw przepływ informacji międzyfirmowych. Zamówienia zakupu są aktualizowane tak, aby zawierały pola dotyczące sposobu dostawy, warunków dostawy i zewnętrznego numeru towaru. Ta zmiana zapewnia, że szczegółowe informacje o zapotrzebowaniu mogą płynąć do firmy dostarczającej.

W tym artykule opisano sposób skonfigurowania i użycia poszczególnych ulepszeń.

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>Włączanie funkcji automatyzacji dostaw na zamówienie

Aby można było skorzystać z funkcji opisanych w tym artykule, należy je włączyć w systemie. Administratorzy mogą korzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), gdzie ta funkcja widnieje jako:

- **Moduł:** *Planowanie główne*
- **Nazwa funkcji:** *Automatyzacja dostaw na zamówienie*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>Ustawienie liczby dni, jaka będzie pokazywana na stronie Obciążenie zdolności produkcyjnych

Strona **Obciążenie zdolności** produkcyjnych umożliwia przeglądanie dostępnych zdolności produkcyjnych zasobu. Funkcja *Automatyzacja dostaw na zamówienie* rozszerza stronę **Pojemność** o pole **Liczba dni**. Za pomocą tego pola można ograniczać liczbę dni w siatce **Przegląd**. Ustawiona wartość jest zapisywana w pamięci. Jeśli więc opuścisz tę stronę, a później wrócisz później, **w siatce Przegląd** będzie nadal pokazywana określona ostatnio określona liczba dni.

Aby otworzyć stronę **Obciążenie zdolności produkcyjnych**, aby można było przejrzeć dostępne zdolności produkcyjne dla poszczególnych zasobów, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Zasoby \> Zasoby**.
1. Wybierz zasób do sprawdzenia.
1. W okienku akcji, na karcie **Zasób** w grupie **Widok** wybierz **Obciążenie zdolności produkcyjnych**.
1. Użyj filtra **Liczba dni**, by ograniczyć liczbę dni wyświetlanych w siatce **Przegląd**.

Aby otworzyć stronę **Obciążenie zdolności produkcyjnych**, aby można było przejrzeć dostępne zdolności produkcyjne dla grup zasobów, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Zasoby \> Grupy zasobów**.
1. Wybierz grupę zasobów do sprawdzenia.
1. W okienku akcji, na karcie **Grupa zasobów** w grupie **Widok** wybierz **Obciążenie zdolności produkcyjnych**.
1. Użyj filtra **Liczba dni**, by ograniczyć liczbę dni wyświetlanych w siatce **Przegląd**.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Zastosuj jeden poziom zaznaczania podczas oznaczania zamówień planowanych

*Oznaczanie* służy do łączenia podaży i popytu. Opcja ta jest podobna do *oznaczania transakcji*, które określa, jak popyt ma zostać pokryty według planowania głównego. Oznaczanie jest jednak bardziej trwałe niż oznaczanie zerowych. Funkcja *automatyzacji dostaw* dodaje możliwość ograniczenia znakowania zapasów do jednego poziomu, gdy planowane zamówienia są ustalane. Dodaje następujące nowe opcje do pola **Aktualizuj oznaczenie** w oknie dialogowym **Akceptacja** podczas ustalania zamówienia planowanego:

- *Standardowy poziom* — używane jest oznaczanie jednopoziomowe. Oznaczanie jednopoziomowe oznacza tylko towar główny, a nie jego składniki BOM. Po ujednaniu można zachować elastyczne przypisanie składników do zleceń produkcyjnych. Oznaczanie jednopoziomowe umożliwia zoptymalizowanie pracy systemu pod kątem ostatnich zmian popytu. W *standardowym oznaczaniu* jednopoziomowym zamówienia zapotrzebowania są oznaczane na ich zamówieniach realizacji, ale zamówienia realizacji nie są zaznaczane, jeśli mają pozostałą ilość.
- *Rozszerzony o jeden poziom* — używane jest oznaczanie jednopoziomowe. W *rozszerzonym* oznaczaniu jednopoziomowym zamówienia zapotrzebowania są oznaczane względem ich zamówień realizacji, a zamówienia realizacji są zawsze oznaczane, niezależnie od tego, czy pozostała jakaś ilość.

Te opcje są również dostępne w polu **Zaktualizuj oznaczenie** na karcie **Standardowa aktualizacja** na stronie **Główne parametry planowania**, gdzie definiujesz domyślny wybór dla **Akceptacja** okna dialogowego.

Aby uzyskać więcej informacji, zobacz [Oznaczanie zapasów](planning-optimization/marking.md).

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Ustaw tolerancję opóźnienia (dni z ujemnym poziomem liczby dni) na poziomie planu głównego

Funkcja *automatyzacji dostaw produkcji na* zamówienie umożliwia konfigurowanie tolerancji opóźnienia (liczby dni z ujemnym poziomem liczby dni) na poziomie planu głównego. To ustawienie jest również dostępne na poziomie grup zapotrzebowania i zapotrzebowania na towar. Jeśli na więcej niż jednym poziomie są przypisywane dni z ujemnym poziomem, do decydowania, które ustawienie ma być stosowane, system stosuje następującą hierarchię:

- Jeśli na stronie **Plany główne** włączono dni ujemne, to ustawienie zastępuje wszystkie inne ustawienia dni ujemnych po uruchomieniu planu.
- Jeśli na stronie **Zapotrzebowania na towar** skonfigurowano ujemne liczby dni, ustawienie to zastępuje ustawienie grupy zapotrzebowania.
- Ujemne liczby dni skonfigurowane na stronie **Grupy zapotrzebowania** obowiązują tylko wtedy, gdy dla odpowiedniego towaru lub planu głównego nie skonfigurowano dni z ujemnym dniem.

Aby ustawić dla planu głównego ujemne liczby dni, należy wykonać następujące czynności.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz plan główny w okienku listy lub utwórz nowy.
1. Na skróconej karcie **Horyzont czasowy zapotrzebowania (dni)** ustaw opcję **Negatywne dni** na *Tak*.
1. W pobliskim polu wpisz dopuszczalną liczbę dni ujemnych.

Aby uzyskać więcej informacji na temat używania dni z ujemnym wartością, zobacz [Tolerancja opóźnienia (dni z ujemnym opóźnieniem)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Kontrola nad sekwencją oznaczania zrównania, która jest używana podczas planowania głównego

W planowaniu głównym do ustalenia, która podaż będzie pokrywać popyt, używana jest *sekwencja oznaczania* z popytem. *Automatyzacja dostaw na zamówienie* dodaje nową opcję **Użyj najnowszych możliwych dostaw**, która zapewnia większą kontrolę nad sekwencją ustalania. Nowa opcja pozwala zachować dostępność produktów dla zamówień w ostatniej chwili i zoptymalizować wykorzystanie istniejącej podaży, ustalając ostatnią możliwą podaż z popytem, zamiast korzystać z pierwszej możliwej podaży.

Sekwencję oznaczania relacji można ustawić na poziomie planu głównego, zapotrzebowania na towar lub grupy zapotrzebowania. Jeśli sekwencja ustalania jest ustawiona na więcej niż jednym poziomie, system stosuje następującą hierarchię, aby zdecydować, którego ustawienia użyć:

- Jeśli sekwencja ustalania jest skonfigurowana na stronie **Plany główne**, to ustawienie zastępuje wszystkie inne ustawienia sekwencji ustalania po uruchomieniu planu.
- Jeśli sekwencja ustalania jest skonfigurowana na stronie **Zapotrzebowanie na towary**, to ustawienie zastępuje ustawienie grupy pokrycia.
- Sekwencja oznaczania pegging skonfigurowana na stronie **Grupy zapotrzebowania** ma zastosowanie tylko w przypadku, gdy ustawienia sekwencji oznaczania pegging nie zostały skonfigurowane dla odpowiedniego towaru lub planu głównego.

Aby skonfigurować oznaczanie zapotrzebowania na poziomie grupy zapotrzebowania, należy wykonać następujące kroki.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Grupy zapotrzebowania**.
1. Wybierz grupę w okienku listy lub utwórz nową.
1. Na skróconej karcie **Ogólne**, w sekcji **Sekwencja oznaczania** użyj pól **Zużyj dostępne zapasy** i **użyj ostatnich pól dostaw**, aby skonfigurować sekwencję oznaczania transakcji. W tabeli w dalszej części tej sekcji pokazano, jak te ustawienia są łączone, aby zdefiniować sekwencję oznaczania.

Aby skonfigurować oznaczanie zapotrzebowania na poziomie pozycji, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt w siatce lub utwórz nowy.
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Objęcie przedmiotu**.
1. Strona **Zapotrzebowania na towar** zawiera wiersze, które pozwalają definiować reguły zapotrzebowania, które mają zastosowanie do towaru w poszczególnych magazynach. Wybierz istniejący wiersz w siatce lub utwórz nowy.
1. Na karcie **Ogólne** zaznacz pole wyboru **Zastąp sekwencję oznaczania transakcji**.
1. Użyj pól **Zużyj dostępne zapasy** i **Użyj ostatnich pól dostawy**, aby skonfigurować sekwencję oznaczania transakcji. W tabeli w dalszej części tej sekcji pokazano, jak te ustawienia są łączone, aby zdefiniować sekwencję oznaczania.

Aby skonfigurować ustalanie na poziomie planu głównego, wykonaj następujące kroki.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz plan główny w okienku listy lub utwórz nowy.
1. Na skróconej karcie **Ogólne** ustaw opcję **Zastąp sekwencję oznaczania** na *Tak*.
1. Użyj pól **Zużyj dostępne zapasy** i **Użyj ostatnich pól dostawy**, aby skonfigurować sekwencję oznaczania transakcji. W tabeli w dalszej części tej sekcji pokazano, jak te ustawienia są łączone, aby zdefiniować sekwencję oznaczania.

W poniższej tabeli pokazano, jak są łączone ustawienia **Zużyj dostępne zapasy** i **Użyj najnowszych ustawień dostaw**, aby określić kolejność oznaczania transakcji.

| | Użyj najnowszej dostawy = Tak | Użyj najnowszej dostawy = Nie |
|---|---|---|
| **Zużyj dane o dostępnych zapasach** = *przed całą dostawą* | <ol><li>Dostępne zapasy</li><li>Istniejąca podaż, która może dorównać dacie popytu</li><li>Istniejąca podaż, która nie może dorównać dacie popytu, ale wciąż w dniach z ujemnym popytem</li><li>Utwórz nową dostawę (planowane zamówienie)</li></ol> | <ol><li>Dostępne zapasy</li><li>Istniejąca podaż, która może dorównać dacie popytu</li><li>Istniejąca podaż, która nie może dorównać dacie popytu, ale wciąż w dniach z ujemnym popytem</li><li>Utwórz nową dostawę (planowane zamówienie)</li></ol> |
| **Zużyj dane o dostępnych zapasach** = *po całej dostawie* | <ol><li>Istniejąca podaż, która może dorównać dacie popytu</li><li>Dostępne zapasy</li><li>Istniejąca podaż, która nie może dorównać dacie popytu, ale wciąż w dniach z ujemnym popytem</li><li>Utwórz nową dostawę (planowane zamówienie)</li></ol> | <ol><li>Istniejąca podaż, która może dorównać dacie popytu</li><li>Istniejąca podaż, która nie może dorównać dacie popytu, ale wciąż w dniach z ujemnym popytem</li><li>Dostępne zapasy</li><li>Utwórz nową dostawę (planowane zamówienie)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Przejrzyj i ustaw zasady realizacji dotyczące poszczególnych zamówień sprzedaży

Zasady realizacji kontrolują procent całkowitej ceny zamówienia lub ilości, które muszą być fizycznie zarezerwowane przed zwolnieniem zamówienia sprzedaży do magazynu. Możesz ustawić globalną domyślną zasadę realizacji, a następnie zastąpić ją dla określonych klientów zgodnie z potrzebami. Funkcja *automatyzacji dostaw produkcji na zamówienie* umożliwia wyświetlenie zasad domyślnych, które w danym momencie dotyczą dowolnego zamówienia, i zastosowanie zastępowania specyficznego dla zamówienia, zgodnie z potrzebą.

- Aby ustawić domyślne globalne zasady realizacji dla zamówień sprzedaży, przejdź do **Rozrachunki z odbiorcami \> Konfiguracja \> Parametry modułu rozrachunków z odbiorcami**. Następnie na karcie **Zarządzanie magazynem** ustaw nazwę **zasady realizacji zamówienia sprzedaży**. 
- Aby ustawić specyficzne dla klienta zasady realizacji zamówień sprzedaży, przejdź do **Rozrachunki z odbiorcami \> Klienci \> Wszyscy klienci**. Następnie na karcie **Zarządzanie magazynem** ustaw w polu **Zasady realizacji** nazwę zasady, której chcesz użyć.

Aby wyświetlić zasady domyślne dotyczące dowolnego zamówienia i zastosować zastąpienie specyficzne dla zamówienia, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Otwórz zamówienie sprzedaży, które chcesz sprawdzić lub edytować.
1. Wybierz widok **nagłówka**.
1. W razie potrzeby na skróconej karcie **magazynowej** przejrzyj i edytuj następujące pola:

    - **Zasada realizacji zamówienia** — umożliwia wybór zasad realizacji dla wybranego zamówienia. Zasady domyślne zostaną zastąpione. Aby użyć domyślnej zasady realizacji wyświetlanej w polu **Domyślne zasady realizacji**, należy pozostawić to pole puste.
    - **Domyślna zasada realizacji** — w tym polu jest przedstawiana domyślna zasada realizacji, która ma zastosowanie, jeśli pole **Zasady realizacji zamówienia** jest puste. To pole jest przeznaczone tylko do odczytu. Jeśli pole to jest puste, nie zdefiniowano domyślnych zasad realizacji określonych dla odbiorcy ani globalnych.

    Jeśli zarówno pole **Zasady realizacji zamówień**, jak i pole **Domyślne zasady realizacji** są puste, nie mają zastosowania żadne zasady realizacji. Jednak mogą obowiązywać inne ograniczenia i może być konieczne, aby przed zwolnieniu zamówienia sprzedaży spełnione zostały rezerwacje lub inne warunki.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>Umożliwia ustawienie trybu dostawy i warunków dostawy w poszczególnych wierszach zamówienia zakupu

Wszystkie zamówienia zakupu zawierają **warunki dostawy** i ustawienia **trybu dostawy** w nagłówku zamówienia. Funkcja *automatyzacji dostaw produkcji na zamówienie* powoduje dodanie tych ustawień do każdego wiersza zamówienia. W związku z tym możesz zdefiniować nadpisania wartości **Warunki dostawy** lub **Sposób dostawy** dla dowolnego lub wszystkich wierszy zamówienia zgodnie z wymaganiami. W przypadku wierszy, w których nie zdefiniowano zastąpienia, używana jest wartość z nagłówka. Można określić, czy zmiana wartości jednego z tych pól w nagłówku zamówienia powinna także zaktualizować wszystkie wiersze.

Aby określić, co ma się stać z ustawieniami wiersza, gdy użytkownik zmieni wartość **Warunki dostawy** i/lub **Tryb dostawy** w nagłówku zamówienia, wykonaj te czynności.

1. Przejdź do **Zaopatrzenie i sourcing \> ustawień \> Parametry modułu Zaopatrzenie i sourcing**.
1. Na karcie **Ogólne**, na skróconej **karcie Wartości domyślne i** parametry zaznacz łącze **Aktualizuj wiersze zamówienia**.
1. W oknie dialogowym **Aktualizacja wierszy zamówienia** w polach **Aktualizowanie warunków dostawy** i **Aktualizuj tryb dostawy** wybierz jedną z następujących wartości:

    - *Nigdy* — nigdy nie należy aktualizować wierszy zamówienia po zmianie ustawień w nagłówku zamówienia.
    - *Zawsze* — Zawsze aktualizuj wszystkie wiersze zamówienia po zmianie ustawień w nagłówku zamówienia.
    - *Monituj* — jeśli użytkownik zmieni jedno lub obie ustawienia w nagłówku zamówienia, otwórz okno dialogowe z pytaniem, czy użytkownik chce zaktualizować wszystkie wiersze, aby dopasować zmianę do jednego lub obu ustawień.

Aby skonfigurować informacje o dostawie w nagłówku zamówienia zakupu, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Otwórz zamówienie zakupu, które chcesz edytować.
1. Wybierz widok **nagłówka**.
1. Na skróconej karcie **Dostawa** ustaw wymagane pola **Tryb dostawy** i **Warunki dostawy**.
1. W zależności od ustawień na stronie **Parametry zaopatrzenia i sourcingu** może zostać zadany monit o określenie, czy zmiany mają zostać wprowadzone do wszystkich wierszy zamówienia.

Aby ustawić zastąpienia informacji o dostawie dla wiersza zamówienia zakupu, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Otwórz zamówienie zakupu, które chcesz edytować.
1. Wybierz widok **Wiersze**.
1. Na skróconej karcie **Wiersze zamówienia zakupu** wybierz wiersz do edycji.
1. Na **Szczegóły linii** skróconej karty na karcie **Dostawa** ustaw wymagane pola **Sposób dostawy** i **Warunki dostawy**. Wyczyść jedno lub oba pola, aby użyć ustawień uzgadniania w nagłówku.

W przypadku zamówień międzyfirmowych wartości pól **Tryb dostawy** i **Warunki dostawy** w każdym wierszu zamówienia zakupu będą synchronizowane między zamówieniem zakupu a powiązanym z nim zamówieniem sprzedaży.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Synchronizuj zewnętrzne identyfikatory i opisy pozycji dla zamówień międzyfirmowych

W przypadku zamówień międzyfirmowych funkcja *Automatyzacja dostaw na zamówienie* umożliwia synchronizację zewnętrznych identyfikatorów towarów i opisów tekstowych w wierszach zamówienia zakupu z powiązanymi wierszami międzyfirmowego zamówienia sprzedaży, niezależnie od tego, czy zamówienie zakupu dotyczy dostawy bezpośredniej. Ta funkcja dodaje również możliwość określania końcowego konta odbiorcy zewnętrznego na międzyfirmowe zamówienie zakupu. System automatycznie pobierze zewnętrzne identyfikatory pozycji i opisy tekstowe z zewnętrznego rekordu klienta zamiast (wewnętrznego) rekordu dostawcy międzyfirmowego.

Aby skonfigurować dostawcę międzyfirmowego do synchronizowania identyfikatorów i nazw towarów zewnętrznych między międzyfirmowymi zamówieniami zakupu i powiązanymi międzyfirmowymi zamówieniami sprzedaży, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**.
1. Wybierz dostawcę międzyfirmowego, którego chcesz skonfigurować.
1. W okienku akcji na karcie **Ogólne** w grupie **Konfiguracja** wybierz **Międzyfirmowe**.
1. Na stronie **Międzyfirmowe** na karcie **Zamówienia zakupu**, w sekcji **Międzyfirmowe zamówienie zakupu -\> międzyfirmowe zamówienie sprzedaży** zaznacz pole wyboru **Zewnętrzny identyfikator towaru i nazwa towaru**.

Aby określić ostateczne konto odbiorcy zewnętrznego dla międzyfirmowego zamówienia zakupu, wykonaj następujące kroki. Pole **Konto odbiorcy** dotyczy tylko międzyfirmowych zamówień zakupu. Umożliwia określenie numeru konta odbiorcy, który ostatecznie odbiera towary. Gdy to pole jest ustawione, wiersze zamówienia zakupu będą przyjmować zewnętrzne opisy i numery towarów z określonego konta odbiorcy zamiast dostawcy międzyfirmowego określonego w zamówieniu zakupu. Jeśli później zmienisz konto odbiorcy, zewnętrzne opisy i identyfikatory towarów zostaną zaktualizowane, tak aby były zgodne z wartościami nowego konta. Z pasującymi wierszami będą także synchronizowane zewnętrzne opisy towarów i identyfikatory dla poszczególnych międzyfirmowe zamówienie sprzedaży.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Otwórz zamówienie zakupu, które chcesz skonfigurować, lub utwórz nowe.
1. Wybierz widok **nagłówka**.
1. W sekcji **Odwołanie** ustaw pole **Konto odbiorcy** na odpowiednie zewnętrzne konto odbiorcy.

Aby określić zewnętrzne identyfikatory towarów i opisy tekstowe wiersza zamówienia zakupu dla zamówienia międzyfirmowego, należy wykonać następujące kroki. Ustawione wartości zostaną zsynchronizowane z powiązanymi wierszami międzyfirmowego zamówienia sprzedaży, niezależnie od tego, czy zamówienie zakupu dotyczy dostawy bezpośredniej.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Otwórz zamówienie zakupu, które chcesz skonfigurować, lub utwórz nowe.
1. Wybierz widok **Wiersze**.
1. Na skróconej karcie **Wiersze zamówienia zakupu** wybierz wiersz do edycji.
1. Na skróconej karcie **Szczegóły wiersza**, na karcie **Ogólne**, w sekcji **Wiersz zamówienia**, w polu **Tekst** podaj zewnętrzny opis towaru określonego w wybranym wierszu zamówienia. Ta wartość zostanie zsynchronizowana z powiązanym wierszem międzyfirmowe zamówienie sprzedaży.
1. W sekcji **Odwołanie** w polu **Zewnętrzny** podaj zewnętrzny identyfikator pozycji dla towaru określonego w wybranym wierszu zamówienia. Ta wartość zostanie zsynchronizowana z powiązanym wierszem międzyfirmowe zamówienie sprzedaży.

Aby uzyskać więcej informacji, zobacz [Tworzenie i fakturowanie międzyfirmowego zamówienia sprzedaży dla odbiorcy zewnętrznego](../sales-marketing/intercompany-sales-order-for-external-customer.md).
