---
title: "Omówienie programu lojalnościowego"
description: "W tym temacie opisano funkcje programów lojalnościowych zawarte w aplikacji Microsoft Dynamics 365 for Retail oraz odnośne procedury konfiguracyjne, które ułatwią sprzedawcy detalicznemu rozpoczęcie tworzenia programów lojalnościowych."
author: scott-tucker
manager: AnnBe
ms.date: 10/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailLoyaltyPrograms, RetailPriceDiscGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16201
ms.assetid: f79559d2-bc2d-4f0b-a938-e7a61524ed80
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 09d4e46694e89b648981352f64da4a43ab1522e1
ms.contentlocale: pl-pl
ms.lasthandoff: 01/04/2019

---

# <a name="loyalty-overview"></a>Omówienie programu lojalnościowego

[!include [banner](includes/banner.md)]

Programy lojalnościowe mogą pomóc zwiększyć lojalność odbiorców poprzez wynagradzanie ich za interakcje z marką sprzedawcy detalicznego. W programie Microsoft Dynamics 365 for Retail można skonfigurować proste lub złożone programy lojalnościowe, które mają zastosowanie w firmach w dowolnym kanale sprzedaży detalicznej. W tym temacie opisano funkcje programów lojalnościowych zawarte w aplikacji Microsoft Dynamics 365 for Retail oraz odnośne procedury konfiguracyjne, które ułatwią sprzedawcy detalicznemu rozpoczęcie tworzenia programów lojalnościowych.

Program lojalnościowy można skonfigurować w taki sposób, żeby zawierał następujące opcje.

- Konfigurowanie wielu typów nagród ofertowanych w programach lojalnościowych, a następnie śledzenie uczestnictwa w programach lojalnościowych.
- Konfigurowanie programów lojalnościowych reprezentujących różne oferowane premie nagród. Można dołączyć warstwy programu lojalnościowego, aby oferować większe premie i nagrody dla klientów, którzy często kupują zakupów lub wydają więcej pieniędzy w sklepach.
- Określanienie reguł dochodów w celu identyfikacji działań, jakie odbiorca musi wykonać, aby zdobyć nagrody. Można także zdefiniować reguły realizacji, określające, kiedy i jak odbiorca może odebrać nagrody.
- Wystawianie kart lojalnościowych z dowolnego kanału sprzedaży detalicznej, który bierze udział w programach lojalnościowych, i łączenie kart lojalnościowych z jednym lub kilkoma programami lojalnościowymi, w których odbiorcy mogą brać udział. Można też połączyć rekord odbiorcy z kartą lojalnościową, aby umożliwić odbiorcy gromadzenie puli punktów lojalnościowych z wielu kart oraz ich wykorzystywanie.
- Ręczne dopasowanie kart lojalnościowych lub przeniesienie salda nagród w programie lojalnościowym z jednej karty do drugiej w celu dostosowania lub nagrodzenia odbiorcy.

## <a name="setting-up-loyalty-programs"></a>Konfigurowanie programów lojalnościowych

Należy skonfigurować kilka składników, aby włączyć funkcję lojalnościową w module Dynamics 365 for Retail. Na poniższym diagramie przedstawiono składniki lojalnościowe i ich relacje względem siebie.

![Przebieg procesu konfigurowania systemu lojalności](./media/loyaltyprocess.gif "Składniki lojalnościowe i ich relacje względem siebie")

## <a name="loyalty-components"></a>Składniki lojalnościowe

W poniższej tabeli opisano każdy składnik i miejsce, w którym jest on używany w konfiguracji lojalnościowej.

| Składnik                                        | opis | Miejsce użycia |
|--------------------------------------------------|-------------|-----------------|
| Konfigurowanie rabatów (wymaganie wstępne)                  | Konfigurowanie rabatów, które możesz zaoferować odbiorcom lojalnościowych. Możesz na przykład zaoferować 5 procent mniej za wszystkie produkty odzieżowe. | Rabaty muszą zostać dodane do grup cenowych, aby zostały uwzględnione w programie lojalnościowym. Grupy cenowe są przypisywane do warstwy lojalnościowej i programów lojalnościowych. |
| Konfigurowanie grup cenowych (wstępne wymaganie)               | Grupy cenowe są używane do tworzenia i obsługi cen i rabatów dla produktów sieci sprzedaży. Konfigurowanie grup cenowych, zawierających rabaty, które mają zastosowanie do programów lojalnościowych. | Grupy cenowe są przypisywane do warstwy lojalnościowej i programów lojalnościowych. |
| Konfigurowanie kanałów (wymaganie wstępne)                   | Kanały sprzedaży detalicznej to sklepy uczestniczące w programach lojalnościowych, takie jak sklepy tradycyjne, sklepy internetowe i biura obsługi. Przed przypisaniem programów lojalnościowych do nich, należy skonfigurować kanały sprzedaży detalicznej. | Kanały sprzedaży detalicznej należy przypisać do programu lojalnościowego w przypadku, gdy kanał sprzedaży detalicznej bierze udział w programie lojalnościowym. |
| Konfigurowanie metody płatności w programie lojalnościowym (wymaganie wstępne) | Należy skonfigurować metodę płatności, zanim będzie można użyć karty lojalnościowej przy kasie i zanim będzie można zrealizować punkty lojalnościowe jako część programu lojalnościowego. Metodę płatności w programie lojalnościowym należy również dodać do kanału sprzedaży detalicznej, aby odbiorcy mogli realizować ich punkty lojalnościowe jako płatność dla produktów. | Konfiguracja metody typu płatności w programie lojalnościowym, a następnie przypisanie metody płatności w programie lojalnościowym w kanałach sprzedaży detalicznej, uczestniczących w programie lojalnościowym. |
| Konfigurowanie zakresów dat                            | Zakresy dat umożliwiają elastyczne ustawianie odstępów czasu dla warstw lojalnościowych. Użyj zakresów dat do określenia, jak długo klient może zostać w warstwie lub ile czasu klient ma na ukończenie aktywności, by spełnić wymagania warstwy. | Zakresy dat mają zastosowanie tylko w przypadku korzystania z warstw w programach lojalnościowych. Można wybrać zakres dat, ktory ma zastosowanie do warstwy programu, a także zakresy dat, które dotyczą reguł warstwy programu. |
| Konfigurowanie punktów lojalnościowych                             | Punkty lojalnościowe to typy nagród oferowane odbiorcom. Punkty lojalnościowe mogą być wymienialne lub nie. Wymienialne punkty lojalnościowe mogą zostać wymienione na produkty. Niewymienialne punkty lojalnościowe są używane do celów śledzenia lub do przeniesienia odbiorcy do następnej warstwy w programie lojalnościowym. | Punkty lojalnościowe znajdują odwołanie w regułach warstwy i są używane do kwalifikowania odbiorcy dla określonej warstwy. Punkty lojalnościowe znajdują też odwołanie w programach lojalnościowych w regułach zdobywania i realizacji punktów. W regułach zdobywania, można określić nagrody, które odbiorcy mogą uzyskać dla określonego działania. W regułach wykorzystywania określa się nagrody, które odbiorca może zrealizować. |
| Konfigurowanie programów lojalnościowych                          | Programy lojalnościowe to podstawowa jednostka lojalnościowa, jaką oferujesz. Każdy program lojalnościowy może mieć przypisane warstwy lojalnościowe. Grupy cen i rabatów są przypisywane do programów lojalnościowych na poziomie programu lub poziomie warstwy. | Dla programów programów lojalnościowych tworzy się schematy lojalnościowe. Karty lojalnościowe przypisuje się do programów lojalnościowych, karty lojalnościowe można przypisać do odbiorcy. Kanały sprzedaży detalicznej uczestniczą w programach lojalnościowych, które są przypisane do schematów lojalnościowych. Wszyscy odbiorcy, którzy mają kartę lojalnościową, mogą uczestniczyć w programach lojalnościowych, które są przypisane do karty. |
| Konfigurowanie warstw lojalności i reguł warstwy              | Warstwy lojalnościowe to opcjonalne poziomy, które można zdefiniować dla programów lojalnościowych. Można skonfigurować podstawowe rabaty i nagrody dla wszystkich odbiorców, którzy biorą udział w programie lojalnościowym; można skonfigurować dodatkowe rabaty i nagrody dla odbiorców, którzy zdobywają różne poziomy w programie. Dla każdej definiowanej warstwy lojalnościowej można skonfigurować reguły, które kwalifikują odbiorcę dla każdej warstwy. Można także zdefiniować, jak długo klient może pozostawać w tej warstwie po jej osiągnięciu. | Warstwy lojalnościowe i zasady dotyczące warstwy lojalnościowej są definiowane w programach lojalnościowych. Jeśli nie zdefiniowano żadnych warstw lojalnościowych, wszyscy odbiorcy, którzy uczestniczą w programie lojalnościowym, kwalifikują się do rabatów, które można przypisać w grupie cenowej programu lojalnościowego. Po zdefiniowaniu warstw lojalnościowych można skonfigurować reguły zdobywania i reguły realizacji dla warstw lojalnościowych w programie lojalnościowym. |
| Konfigurowanie programów lojalnościowych                           | Schematy lojalnościowe określają reguły zdobywania i realizacji, które dotyczą wybranego programu lojalnościowego. Kanały sprzedaży detalicznej są przypisywane do schematu lojalnościowego, aby określić, który program lojalnościowy, reguły zdobywania i reguły realizacji stosuje się do sklepu sieci sprzedaży. | Schemat lojalnościowy jest przypisany do programu lojalnościowego oraz do kanałów sprzedaży detalicznej. Do tego samego programu lojalnościowego można przypisać wiele schematów lojalnościowych; wiele schematów lojalnościowych można przypisać do wielu kanałów sprzedaży detalicznej. |
| Konfigurowanie kart lojalnościowych                             | Karta lojalnościowa upoważnia posiadacza karty do uczestnictwa w programach lojalnościowych, które są przypisane do karty. Można wystawiać karty lojalnościowe anonimowo lub mogą być przypisane do określonego odbiorcy. Możliwe jest przeglądanie transakcji w programie lojalnościowym dla określonej karty; można wyświetlić podsumowanie punktów lojalnościowych, które zostały zgromadzone na karcie. Można wystawiać karty lojalnościowe z dowolnego kanału sprzedaży detalicznej. Można również ręcznie zmienić kartę lojalnościową, aby uaktualnić odbiorcę do innej warstwy, dodać punkty lojalnościowe lub przenieść saldo punktów lojalnościowych z jednej karty na inną. | Programy lojalnościowe są przypisywane do karty lojalnościowej. |

## <a name="loyalty-processes"></a>Procesy lojalnościowe

W poniższej tabeli opisano procesy, które należy wykonać, aby wysłać konfiguracje lojalnościowe i dane do sklepów i pobrać transakcje lojalnościowe ze sklepów.

| Nazwa procesu                         | Opis | Nazwa strony |
|--------------------------------------|-------------|-----------|
| 1050 (informacje o lojalności)           | Uruchom ten proces w celu wysyłania danych lojalnościowych z programu Dynamics 365 for Retail do sklepów sieci sprzedaży. Dobrze jest zaplanować częste wykonywanie tego procesu, tak aby dane lojalnościowe były przesyłane do wszystkich sklepów. | Harmonogram dystrybucji |
| Przetwarzanie programów lojalnościowych              | Uruchom ten proces, aby skojarzyć schematy lojalnościowe z kanałami sprzedaży detalicznej, do których jest przypisany schemat lojalnościowy. Ten proces może zostać zaplanowany do uruchamiania jako zadanie wsadowe. Należy uruchamiać ten proces przy każdej zmianie danych konfiguracji lojalności, takich jak harmonogramy, programy lojalnościowe lub punkty lojalnościowe. | Przetwarzanie programów lojalnościowych |
| Przetwarzaj transakcje programu lojalnościowego w trybie offline | Uruchom ten proces, aby zaktualizować karty lojalnościowe tak, aby uwzględniały transakcje przetworzone w trybie offline. Ten proces ma zastosowanie tylko wtedy, gdy jest zaznaczone pole wyboru **Uzyskaj w trybie offline** na stronie **Wspólne parametry sieci sprzedaży**, dzięki czemu możliwie jest odbieranie nagród offline. | Przetwarzaj transakcje programu lojalnościowego w trybie offline |
| Aktualizuj warstwy kart lojalnościowych            | Uruchom ten proces, aby ocenić aktywność zdobywania punktów odbiorcy pod kątem reguł warstwy dla programu lojalnościowego oraz zaktualizować stan warstwy odbiorcy. Ten proces jest wymagany tylko, gdy zmienisz reguły warstwy w programach lojalnościowych i chcesz wstecznie zastosować zaktualizowane reguły do kart lojalnościowych, które zostały już wystawione. Ten proces może być uruchamiany jako zadanie wsadowe lub dla poszczególnych kart. | Aktualizuj warstwy kart lojalnościowych |

## <a name="loyalty-enhancements"></a>Ulepszenia funkcjonalności programów lojalnościowych

Aplikacja Retail w wydaniu z października 2018 roku zawiera nowe funkcje programów lojalnościowych. Każde nowe ulepszenie omówiono poniżej.

- W ramach programu lojalnościowego w poprzednich wersjach sprzedawcy detaliczni mogli tworzyć różne reguły zdobywania punktów i realizacji z podziałem na warstwy (poziomy/szczeble) w celu zróżnicowania korzyści dla odbiorców na różnych poziomach. Teraz sprzedawcy detaliczni mogą w regułach zdobywania punktów i realizacji dodawać „przynależności”, tak aby określone grupy odbiorców mogły należeć do istniejących szczebli, ale otrzymywać punkty według innego schematu. Eliminuje to konieczność tworzenia dodatkowych szczebli.
    
    > [!NOTE]
    > Reguły zdobywania punktów w ramach programu lojalnościowego mają charakter dodatkowy. Na przykład jeśli utworzysz regułę przyznającą członkowi na szczeblu Gold 10 punktów za każdego wydanego dolara amerykańskiego, a dodatkowo utworzysz regułę przyznającą 5 punktów za każdego wydanego dolara amerykańskiego dla odbiorców o przynależności „stały klient”, to stały klient należący do warstwy Gold otrzyma 15 punktów za każdego wydanego dolara amerykańskiego, ponieważ spełnia oba kryteria. Jednak jeśli stały klient nie kwalifikował się do poziomu Gold, otrzyma 5 punktów za każdego dolara. Aby odzwierciedlić te zmiany w kanałach, uruchom zadania **Przetwarzanie programów lojalnościowych** i **1050** (informacje o lojalności).
    
    ![Zdobywanie punktów poprzez przynależność](./media/Affiliation%20based%20earning.png "Zdobywanie punktów poprzez przynależność")

- Sprzedawcy detaliczni często mają specjalne ceny dla określonych grup klientów, do których nie chcą stosować programów lojalnościowych. Na przykład odbiorcy hurtowni i pracownicy dostają specjalne ceny, ale nie otrzymują punktów lojalnościowych. Zazwyczaj ustawianie specjalnych cen dla takich grup odbiorców odbywa się za pomocą „przynależności”. Aby uniemożliwić określonym grupom odbiorców zdobywanie punktów lojalnościowych, sprzedawca detaliczny może zdefiniować jedną lub więcej przynależności w obszarze **Wykluczone przynależności** w ustawieniach programu lojalnościowego. W ten gdy odbiorcami należącymi do wykluczonych przynależności są uczestnicy programu lojalnościowego, nie będą otrzymywać punktów lojalnościowych za swoje zakupy. Aby odzwierciedlić te zmiany w kanałach, uruchom zadania **Przetwarzanie programów lojalnościowych** i **1050** (informacje o lojalności).

    ![Wykluczone przynależności](./media/Excluded%20affiliations.png "Wykluczanie przynależności z naliczania punktów lojalnościowych")
    
- Sprzedawcy detaliczni mogą generować numery kart lojalnościowych w kanałach. Przed aktualizacją z października 2018 r. sprzedawcy detaliczni mogli używać fizycznych kart lojalnościowych lub generować karty lojalnościowe przy użyciu wybranych unikatowy danych odbiorców, takich jak numer telefonu. Aby umożliwić automatyczne generowanie kart lojalnościowych w sklepach detalicznych, należy włączyć funkcję **Generuj numer karty lojalnościowej** w profilu funkcjonalności skojarzonym ze sklepem. W kanałach internetowych sprzedawcy detaliczni mogą używać interfejsu API IssueLoyaltyCard w celu wystawiania kart lojalnościowych odbiorcom. Sprzedawcy detaliczni mogą w tym interfejsie API podać numer karty lojalnościowej, który zostanie użyty do wygenerowania karty lojalnościowej, lub też system użyje numeracji kart lojalnościowych ustawionej w aplikacji Dynamics 365 for Retail. Jednak jeśli numeracja nie jest zdefiniowana, a sprzedawca detaliczny nie poda numeru karty lojalnościowej podczas wywoływania interfejsu API, zostanie wyświetlony błąd.

    ![Generowanie karty lojalnościowej](./media/Generate%20loyalty%20card.png "Automatyczne generowanie numeru karty lojalnościowej")

- Uzyskane i zrealizowane punkty lojalnościowe są teraz zapisywane dla każdej transakcji i zamówienia sprzedaży względem wiersza sprzedaży, dzięki czemu tę samą kwotę można zrefundować lub wycofać w przypadku zwrotów pełnych lub częściowych. Ponadto widoczność punktów na poziomie wiersza sprzedaży pozwala użytkownikom w biurze obsługi odpowiadać na pytania klientów o liczbę punktów zarobionych lub zrealizowanych dla każdego wiersza. Przed tą zmianą punkty lojalnościowe były zawsze ponownie obliczane w przypadku zwrotów, co powodowało różnicę kwot w porównaniu z oryginalnymi, jeśli w międzyczasie zmieniły się reguły zdobywania lub realizacji punktów, a użytkownicy w biurze obsługi nie widzieli szczegółowego podziału punktów. Punkty można obejrzeć w formularzu **Transakcje kartą** dla każdej karty lojalnościowej.    
- Teraz sprzedawcy detaliczni mogą definiować okres aktywowania każdego punktu lojalnościowego. Konfiguracja okresu aktywacji określi czas od dnia otrzymania punktów lojalnościowych, po którym punkty stają się dostępne dla odbiorców. Nieaktywne punkty można obejrzeć w kolumnie **Nieaktywowane punkty** na stronie **Karty lojalnościowe**. Ponadto sprzedawcy detaliczni mogą określać limit maksymalnej liczby punktów lojalnościowych dla każdej karty lojalnościowej. To pole umożliwia zmniejszenie negatywnych skutków oszustw w programach lojalnościowych. Po uzyskaniu maksymalnej liczby punktów lojalnościowych użytkownik nie może zdobyć ich więcej. Sprzedawca detaliczny może postanowić blokować takie karty do czasu zbadania, czy faktycznie doszło do oszustwa. W razie stwierdzenia oszustwa sprzedawca może nie tylko zablokować kartę lojalnościową odbiorcy, ale również zablokować samego odbiorcę. Aby to zrobić, należy ustawić właściwość **Blokuj rejestrację odbiorcy w programie lojalnościowym** na **Tak** w obszarze **Wszyscy odbiorcy** na skróconej karcie **Handel detaliczny**. Zablokowanym klientom nie będzie można wystawiać kart lojalnościowych w każdym z kanałów.

    ![Aktywowanie i maksymalna liczba punktów lojalnościowych](./media/Vesting%20and%20maximum%20reward%20points.png "Definiowanie aktywowania i maksymalnej liczby punktów lojalnościowych")

- Przynależności umożliwiają stosowanie specjalnych cen i rabatów, ale istnieją też przynależności, których sprzedawcy detaliczni nie chcą pokazywać klientom. Na przykład przynależność zatytułowana „Klient wydający dużo” może być negatywnie odbierana przez przedmiotowego odbiorcę. Ponadto istnieją przynależności, którymi nie powinno się zarządzać w sklepie. Przykładem jest przynależność „pracownicy”, ponieważ nie chcesz, aby kasjerzy decydowali, kto jest pracownikiem, i na tej podstawie przyznawali rabaty pracownicze. Sprzedawcy detaliczni mogą teraz wybierać przynależności, które mają być ukryte w kanałach sprzedaży detalicznej. Przynależności oznaczone jako **Ukryj w kanałach** nie mogą być wyświetlane, dodawane ani usuwane w punkcie sprzedaży. Jednak ceny i rabaty skojarzone z przynależnością nadal będą stosowane do produktów.

    ![Ukrywanie przynależności](./media/Hide%20affiliations.png "Ukrywanie przynależności w kanałach")
    
- Użytkownicy w biurze obsługi mogą teraz łatwiej wyszukiwać odbiorców przy użyciu danych z ich kart lojalnościowych oraz przechodzić do stron karty lojalnościowej i transakcji na karcie lojalnościowej odbiorcy ze strony **Obsługa klienta**.

    ![Obsługa klienta](./media/Customer%20service.png "Znajdowanie informacji lojalnościowych dla odbiorcy")
    
- W razie naruszenia zabezpieczeń karty lojalnościowej należy wygenerować kartę zastępczą, a następnie przenieść do niej istniejące punkty. W tej wersji uproszczono proces wymiany karty. Ponadto klienci mogą przekazywać część lub wszystkie punkty lojalnościowe znajomym i członkom rodziny. Po przeniesieniu punktów dla każdej karty lojalnościowej są tworzone wpisy korekty punktów. Funkcje wymiany karty i przenoszenia sald są dostępne na stronie **Karty lojalnościowe**.

    ![Wymiana karty i przenoszenie punktów](./media/Replace%20and%20transfer%20points.png "Wymiana karty lojalnościowej lub przeniesienie salda punktów")
    
- Sprzedawcy detaliczni mogą chcieć sprawdzać efektywność rejestrowania odbiorców w programie lojalnościowym przez określony kanał. Źródło rejestrowania kart lojalnościowych jest teraz zapisywane, dzięki czemu sprzedawcy detaliczni mogą generować raporty o tych danych. Źródło rejestracji jest automatycznie zapisywane dla wszystkich wydanych kartach lojalnościowych z aplikacji MPOS/CPOS i kanałów handlu elektronicznego. Dla kart lojalnościowych wydanych z aplikacji zaplecza użytkownik w biurze obsługi może wybrać odpowiedni kanał.
- W starszych wersjach sprzedawcy detaliczni mogli używać aplikacji MPOS/CPOS do realizowania punktów lojalnościowych odbiorców w sklepie. Jednak w tych wersjach saldo w programie lojalnościowym jest wyświetlane w punktach lojalnościowych, dlatego kasjer nie widział kwoty pieniężnej, którą można było wykorzystać w bieżącej transakcji. Kasjer musiał ręcznie przeliczyć punkty na walutę, zanim klient mógł zapłacić punktami lojalnościowymi. W obecnej wersji po dodaniu wierszy do transakcji kasjer widzi kwotę, jaką można pokryć punktami lojalnościowymi w bieżącej transakcji, dzięki czemu można łatwo zastosować część lub wszystkie punkty lojalnościowe do transakcji. Ponadto kasjer widzi punkty wygasające w ciągu najbliższych 30 dni, więc może zaproponować sprzedaż dodatkową lub wiązaną, aby zmotywować klienta do wydania wygasających punktów w tej transakcji.

    ![Pokrycie punktami z salda w programie lojalnościowym](./media/Points%20covered%20by%20loyalty%20balance.png "Wyświetlanie salda pokrytego punktami lojalnościowymi")

    ![Wygasające punkty](./media/Expiring%20points.png "Wyświetlanie wygasających punktów")
    
## <a name="upcoming-enhancements"></a>Nadchodzące ulepszenia

Następujące funkcje zostaną udostępnione w przyszłych miesięcznych aktualizacjach aplikacji Dynamics 365 for Retail.
    
- Klienci chcą mieć możliwość wyświetlania szczegółów swoich sald w programach lojalnościowych w kanałach, których używają. Podobnie ważne jest, aby kasjerzy mogli wyświetlać historie punktów lojalnościowych odbiorców w aplikacji MPOS/CPOS, co pozwoli szybko odpowiadać na pytania odbiorców. W nadchodzącej miesięcznej aktualizacji klienci i kasjerzy będą mogli wyświetlać szczegóły historii sald w programach lojalnościowych.
- Wielu sprzedawców detalicznych jest w stanie przyznawać punkty lojalnościowe wyłącznie na podstawie transakcji sprzedaży, ale sprzedawcy zorientowani bardziej prokonsumencko chcą też nagradzać za każdą interakcję z marką. Na przykład chcą przyznawać punkty za wypełnienie ankiety internetowej, odwiedziny sklepu, polubienie sprzedawcy w serwisie Facebook, wysłanie tweeta o sprzedawcy itd. W przyszłości dodamy możliwość przyznawania punktów lojalnościowych za każdą aktywność odbiorcy. W tym celu sprzedawca detaliczny może zdefiniować „inny typ działania”, a następnie zdefiniować reguły zdobywania punktów za to działanie. Udostępnimy interfejs API usługi Retail Server, który można wywoływać po zidentyfikowaniu działania mającego użyć reguły zdobywania punktów do przyznania odpowiedniej liczby punktów lojalnościowych.
- Aby stworzyć faktycznie wielokanałowe środowisko handlu detalicznego, pozwolimy klientom na zdobywanie i realizowanie punktów lojalnościowych we wszystkich kanałach.
- Jednym z czynników istotnie motywujących klientów do kupowania przez Internet jest bezpłatna lub tania dostawa. Aby umożliwić sprzedawcom detalicznym konfigurowanie promocji na dostawy, wprowadzimy nowy rodzaj promocji, w którym sprzedawca detaliczny może definiować progi, po których osiągnięciu odbiorcy otrzymają korzyść w postaci tańszej lub bezpłatnej dostawy.

