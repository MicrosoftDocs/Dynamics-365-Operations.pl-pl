---
title: Omówienie programu lojalnościowego
description: W tym artykule opisano funkcje programów lojalnościowych zawarte w aplikacji Dynamics 365 Commerce oraz odnośne procedury konfiguracyjne, które ułatwią sprzedawcy detalicznemu rozpoczęcie tworzenia programów lojalnościowych.
author: scott-tucker
ms.date: 07/21/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyPrograms, RetailPriceDiscGroup
audience: Application User
ms.reviewer: josaw
ms.custom:
- "16201"
- intro-internal
ms.assetid: f79559d2-bc2d-4f0b-a938-e7a61524ed80
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 667c30e52bae34f8ddfdc7b74f271d08612ac594
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883910"
---
# <a name="loyalty-overview"></a>Omówienie programu lojalnościowego

[!include [banner](includes/banner.md)]

Programy lojalnościowe mogą pomóc zwiększyć lojalność odbiorców poprzez wynagradzanie ich za interakcje z marką sprzedawcy detalicznego. W programie Dynamics 365 Commerce można skonfigurować proste lub złożone programy lojalnościowe, które mają zastosowanie w firmach w dowolnym kanale handlowym. W tym artykule opisano funkcje programów lojalnościowych zawarte w aplikacji Commerce oraz odnośne procedury konfiguracyjne, które ułatwią sprzedawcy detalicznemu rozpoczęcie tworzenia programów lojalnościowych.

Program lojalnościowy można skonfigurować w taki sposób, żeby zawierał następujące opcje.

- Konfigurowanie wielu typów nagród ofertowanych w programach lojalnościowych, a następnie śledzenie uczestnictwa w programach lojalnościowych.
- Konfigurowanie programów lojalnościowych reprezentujących różne oferowane premie nagród. Można dołączyć warstwy programu lojalnościowego, aby oferować większe premie i nagrody dla klientów, którzy często kupują zakupów lub wydają więcej pieniędzy w sklepach.
- Określanienie reguł dochodów w celu identyfikacji działań, jakie odbiorca musi wykonać, aby zdobyć nagrody. Można także zdefiniować reguły realizacji, określające, kiedy i jak odbiorca może odebrać nagrody.
- Wystawianie kart lojalnościowych z dowolnego kanału, który bierze udział w programach lojalnościowych, i łączenie kart lojalnościowych z jednym lub kilkoma programami lojalnościowymi, w których odbiorcy mogą brać udział. Można też połączyć rekord odbiorcy z kartą lojalnościową, aby umożliwić odbiorcy gromadzenie puli punktów lojalnościowych z wielu kart oraz ich wykorzystywanie.
- Ręczne dopasowanie kart lojalnościowych lub przeniesienie salda nagród w programie lojalnościowym z jednej karty do drugiej w celu dostosowania lub nagrodzenia odbiorcy.

## <a name="setting-up-loyalty-programs"></a>Konfigurowanie programów lojalnościowych

Należy skonfigurować kilka składników, aby włączyć funkcję lojalnościową w Commerce. Na poniższym diagramie przedstawiono składniki lojalnościowe i ich relacje względem siebie.

![Przebieg procesu konfigurowania systemu lojalności.](./media/loyaltyprocess.gif "Składniki lojalności oraz sposób ich odnoszenia się do siebie")

## <a name="loyalty-components"></a>Składniki lojalnościowe

W poniższej tabeli opisano każdy składnik i miejsce, w którym jest on używany w konfiguracji lojalnościowej.

| Składnik                                        | opis | Miejsce użycia |
|--------------------------------------------------|-------------|-----------------|
| Konfigurowanie rabatów (wymaganie wstępne)                  | Konfigurowanie rabatów, które możesz zaoferować odbiorcom lojalnościowych. Możesz na przykład zaoferować 5 procent mniej za wszystkie produkty odzieżowe. | Rabaty muszą zostać dodane do grup cenowych, aby zostały uwzględnione w programie lojalnościowym. Grupy cenowe są przypisywane do warstwy lojalnościowej i programów lojalnościowych. |
| Konfigurowanie grup cenowych (wstępne wymaganie)               | Grupy cenowe są używane do tworzenia i obsługi cen i rabatów dla produktów. Konfigurowanie grup cenowych, zawierających rabaty, które mają zastosowanie do programów lojalnościowych. | Grupy cenowe są przypisywane do warstwy lojalnościowej i programów lojalnościowych. |
| Konfigurowanie kanałów (wymaganie wstępne)                   | Kanały handlowe to sklepy uczestniczące w programach lojalnościowych, takie jak sklepy tradycyjne, sklepy internetowe i biura obsługi. Przed przypisaniem programów lojalnościowych do nich, należy skonfigurować kanały. | Kanały należy przypisać do programu lojalnościowego w przypadku, gdy kanał bierze udział w programie lojalnościowym. |
| Konfigurowanie metody płatności w programie lojalnościowym (wymaganie wstępne) | Aby mieć pewność, że punkty lojalnościowe można wykorzystać w dowolnym kanale, na przykład w sklepach stacjonarnych, sklepach internetowych lub telefonicznych centrach obsługi, należy ustawić zakres pojemników dla kart lojalnościowych na stronie **Numery kart**. | Konfiguracja metody typu płatności w programie lojalnościowym, a następnie przypisanie metody płatności w programie lojalnościowym w kanałach, uczestniczących w programie lojalnościowym. |
| Konfigurowanie zakresów dat                            | Zakresy dat umożliwiają elastyczne ustawianie odstępów czasu dla warstw lojalnościowych. Użyj zakresów dat do określenia, jak długo klient może zostać w warstwie lub ile czasu klient ma na ukończenie aktywności, by spełnić wymagania warstwy. | Zakresy dat mają zastosowanie tylko w przypadku korzystania z warstw w programach lojalnościowych. Można wybrać zakres dat, ktory ma zastosowanie do warstwy programu, a także zakresy dat, które dotyczą reguł warstwy programu. |
| Konfigurowanie punktów lojalnościowych                             | Punkty lojalnościowe to typy nagród oferowane odbiorcom. Punkty lojalnościowe mogą być wymienialne lub nie. Wymienialne punkty lojalnościowe mogą zostać wymienione na produkty. Niewymienialne punkty lojalnościowe są używane do celów śledzenia lub do przeniesienia odbiorcy do następnej warstwy w programie lojalnościowym. | Punkty lojalnościowe znajdują odwołanie w regułach warstwy i są używane do kwalifikowania odbiorcy dla określonej warstwy. Punkty lojalnościowe znajdują też odwołanie w programach lojalnościowych w regułach zdobywania i realizacji punktów. W regułach zdobywania, można określić nagrody, które odbiorcy mogą uzyskać dla określonego działania. W regułach wykorzystywania określa się nagrody, które odbiorca może zrealizować. |
| Konfigurowanie programów lojalnościowych                          | Programy lojalnościowe to podstawowa jednostka lojalnościowa, jaką oferujesz. Każdy program lojalnościowy może mieć przypisane warstwy lojalnościowe. Grupy cen i rabatów są przypisywane do programów lojalnościowych na poziomie programu lub poziomie warstwy. | Dla programów programów lojalnościowych tworzy się schematy lojalnościowe. Karty lojalnościowe przypisuje się do programów lojalnościowych, karty lojalnościowe można przypisać do odbiorcy. Kanały uczestniczą w programach lojalnościowych, które są przypisane do schematów lojalnościowych. Wszyscy odbiorcy, którzy mają kartę lojalnościową, mogą uczestniczyć w programach lojalnościowych, które są przypisane do karty. |
| Konfigurowanie warstw lojalności i reguł warstwy              | Warstwy lojalnościowe to opcjonalne poziomy, które można zdefiniować dla programów lojalnościowych. Można skonfigurować podstawowe rabaty i nagrody dla wszystkich odbiorców, którzy biorą udział w programie lojalnościowym; można skonfigurować dodatkowe rabaty i nagrody dla odbiorców, którzy zdobywają różne poziomy w programie. Dla każdej definiowanej warstwy lojalnościowej można skonfigurować reguły, które kwalifikują odbiorcę dla każdej warstwy. Można także zdefiniować, jak długo klient może pozostawać w tej warstwie po jej osiągnięciu. | Warstwy lojalnościowe i zasady dotyczące warstwy lojalnościowej są definiowane w programach lojalnościowych. Jeśli nie zdefiniowano żadnych warstw lojalnościowych, wszyscy odbiorcy, którzy uczestniczą w programie lojalnościowym, kwalifikują się do rabatów, które można przypisać w grupie cenowej programu lojalnościowego. Po zdefiniowaniu warstw lojalnościowych można skonfigurować reguły zdobywania i reguły realizacji dla warstw lojalnościowych w programie lojalnościowym. |
| Konfigurowanie programów lojalnościowych                           | Schematy lojalnościowe określają reguły zdobywania i realizacji, które dotyczą wybranego programu lojalnościowego. Kanały są przypisywane do schematu lojalnościowego, aby określić, który program lojalnościowy, reguły zdobywania i reguły realizacji stosuje się do sklepu. | Schemat lojalnościowy jest przypisany do programu lojalnościowego oraz do kanałów. Do tego samego programu lojalnościowego można przypisać wiele schematów lojalnościowych; wiele schematów lojalnościowych można przypisać do wielu kanałów. |
| Konfigurowanie kart lojalnościowych                             | Karta lojalnościowa upoważnia posiadacza karty do uczestnictwa w programach lojalnościowych, które są przypisane do karty. Można wystawiać karty lojalnościowe anonimowo lub mogą być przypisane do określonego odbiorcy. Możliwe jest przeglądanie transakcji w programie lojalnościowym dla określonej karty; można wyświetlić podsumowanie punktów lojalnościowych, które zostały zgromadzone na karcie. Można wystawiać karty lojalnościowe z dowolnego kanału. Można również ręcznie zmienić kartę lojalnościową, aby uaktualnić odbiorcę do innej warstwy, dodać punkty lojalnościowe lub przenieść saldo punktów lojalnościowych z jednej karty na inną. | Programy lojalnościowe są przypisywane do karty lojalnościowej. |

## <a name="loyalty-processes"></a>Procesy lojalnościowe

W poniższej tabeli opisano procesy, które należy wykonać, aby wysłać konfiguracje lojalnościowe i dane do sklepów i pobrać transakcje lojalnościowe ze sklepów.

| Nazwa procesu                         | Opis | Nazwa strony |
|--------------------------------------|-------------|-----------|
| 1050 (informacje o lojalności)           | Uruchom ten proces w celu wysyłania danych lojalnościowych z programu Commerce do sklepów. Dobrze jest zaplanować częste wykonywanie tego procesu, tak aby dane lojalnościowe były przesyłane do wszystkich sklepów. | Harmonogram dystrybucji |
| Przetwarzanie programów lojalnościowych              | Uruchom ten proces, aby skojarzyć schematy lojalnościowe z kanałami, do których jest przypisany schemat lojalnościowy. Ten proces może zostać zaplanowany do uruchamiania jako zadanie wsadowe. Należy uruchamiać ten proces przy każdej zmianie danych konfiguracji lojalności, takich jak harmonogramy, programy lojalnościowe lub punkty lojalnościowe. | Przetwarzanie programów lojalnościowych |
| Księguj uzyskane punkty lojalnościowe w partiach | Uruchom ten proces, aby zaktualizować karty lojalnościowe tak, aby uwzględniały transakcje przetworzone w trybie offline. Ten proces ma zastosowanie tylko wtedy, gdy jest zaznaczone pole wyboru **Księguj uzyskane punkty w partiach** na stronie **Wspólne parametry handlu**, dzięki czemu możliwie jest odbieranie nagród offline. | Księguj uzyskane punkty lojalnościowe w partiach |
| Aktualizuj warstwy kart lojalnościowych            | Uruchom ten proces, aby ocenić aktywność zdobywania punktów odbiorcy pod kątem reguł warstwy dla programu lojalnościowego oraz zaktualizować stan warstwy odbiorcy. Ten proces jest wymagany tylko, gdy zmienisz reguły warstwy w programach lojalnościowych i chcesz wstecznie zastosować zaktualizowane reguły do kart lojalnościowych, które zostały już wystawione. Ten proces może być uruchamiany jako zadanie wsadowe lub dla poszczególnych kart. | Aktualizuj warstwy kart lojalnościowych |

## <a name="loyalty-capabilities"></a>Możliwości lojalnościowe

- Korzystając z grup cenowych związanych z programem lojalnościowym i poziomami lojalnościowymi, detaliści mogą łatwo tworzyć specjalne ceny i rabaty dla członków zarejestrowanych w programie lojalnościowym.

- W ramach programu lojalnościowego sprzedawcy detaliczni mogli tworzyć różne reguły zdobywania punktów i realizacji z podziałem na warstwy (poziomy/szczeble) w celu zróżnicowania korzyści dla odbiorców na różnych poziomach. Również sprzedawcy detaliczni mogą w regułach zdobywania punktów i realizacji dodawać „przynależności”, tak aby określone grupy odbiorców mogły należeć do istniejących szczebli, ale otrzymywać punkty według innego schematu. Eliminuje to konieczność tworzenia dodatkowych szczebli.
    
    > [!NOTE]
    > Reguły zdobywania punktów w ramach programu lojalnościowego mają charakter dodatkowy. Na przykład jeśli utworzysz regułę przyznającą członkowi na szczeblu Gold 10 punktów za każdego wydanego dolara amerykańskiego, a dodatkowo utworzysz regułę przyznającą 5 punktów za każdego wydanego dolara amerykańskiego dla odbiorców o przynależności „stały klient”, to stały klient należący do warstwy Gold otrzyma 15 punktów za każdego wydanego dolara amerykańskiego, ponieważ spełnia oba kryteria. Jednak jeśli stały klient nie kwalifikował się do poziomu Gold, klient otrzyma 5 punktów za każdego dolara. Aby odzwierciedlić te zmiany w kanałach, uruchom zadania **Przetwarzanie programów lojalnościowych** i **1050** (informacje o lojalności).
    
    ![Zarobki na podstawie przynależności.](./media/Affiliation-based-earning.png "Zarobki na podstawie przynależności")

- Sprzedawcy detaliczni często mają specjalne ceny dla określonych grup klientów, do których nie chcą stosować programów lojalnościowych. Na przykład odbiorcy hurtowni i pracownicy dostają specjalne ceny, ale nie otrzymują punktów lojalnościowych. Zazwyczaj ustawianie specjalnych cen dla takich grup odbiorców odbywa się za pomocą „przynależności”. Aby uniemożliwić określonym grupom odbiorców zdobywanie punktów lojalnościowych, sprzedawca detaliczny może zdefiniować jedną lub więcej przynależności w obszarze **Wykluczone przynależności** w ustawieniach programu lojalnościowego. W ten gdy odbiorcami należącymi do wykluczonych przynależności są uczestnicy programu lojalnościowego, nie będą otrzymywać punktów lojalnościowych za swoje zakupy. Aby odzwierciedlić te zmiany w kanałach, uruchom zadania **Przetwarzanie programów lojalnościowych** i **1050** (informacje o lojalności).

    ![Wykluczone przynależności.](./media/Excluded-affiliations.png "Wykluczone przynależności z naliczania punktów lojalnościowych")
    
- Punkt sprzedaży umożliwia elastyczności detalicznej korzystanie z fizycznych kart lojalnościowych lub automatyczne generowanie unikatowego numeru karty lojalnościowej. Aby umożliwić automatyczne generowanie kart lojalnościowych w sklepach, należy włączyć funkcję **Generuj numer karty lojalnościowej** w profilu funkcjonalności skojarzonym ze sklepem. W kanałach internetowych sprzedawcy detaliczni mogą używać interfejsu API IssueLoyaltyCard w celu wystawiania kart lojalnościowych odbiorcom. Sprzedawcy detaliczni mogą w tym interfejsie API podać numer karty lojalnościowej, który zostanie użyty do wygenerowania karty lojalnościowej, lub też system użyje numeracji kart lojalnościowych ustawionej w aplikacji Commerce. Jednak jeśli numeracja nie jest zdefiniowana, a sprzedawca detaliczny nie poda numeru karty lojalnościowej podczas wywoływania interfejsu API, zostanie wyświetlony błąd.

    ![Generuj kartę lojalnościową.](./media/Generate-loyalty-card.png "Automatycznie Generuj numer karty lojalnościowej")

- Uzyskane i zrealizowane punkty lojalnościowe teraz mogą być zapisywane dla każdej transakcji i zamówienia sprzedaży względem wiersza sprzedaży, dzięki czemu tę samą kwotę można zrefundować lub wycofać w przypadku zwrotów pełnych lub częściowych. Ponadto widoczność punktów na poziomie wiersza sprzedaży pozwala użytkownikom w biurze obsługi odpowiadać na pytania klientów o liczbę punktów zarobionych lub zrealizowanych dla każdego wiersza. Przed tą zmianą punkty lojalnościowe były zawsze ponownie obliczane w przypadku zwrotów, co powodowało różnicę kwot w porównaniu z oryginalnymi, jeśli w międzyczasie zmieniły się reguły zdobywania lub realizacji punktów, a użytkownicy w biurze obsługi nie widzieli szczegółowego podziału punktów. Punkty można obejrzeć w formularzu **Transakcje kartą** dla każdej karty lojalnościowej. Aby włączyć tę funkcję, włącz konfigurację **Księguj punkty lojalnościowe według wierszy sprzedaży** na karcie **Wspólne parametry handlu** \> **Ogólne**.

    > [!NOTE]
    > Zdecydowanie zalecamy włączenie tej funkcji w celu zapewnienia, w przypadku zwrotów, refundacji lub potrącenia poprawnej liczby punktów klienta.

- Teraz sprzedawcy detaliczni mogą definiować okres aktywowania każdego punktu lojalnościowego. Konfiguracja okresu aktywacji określi czas od dnia otrzymania punktów lojalnościowych, po którym punkty stają się dostępne dla odbiorców. Nieaktywne punkty można obejrzeć w kolumnie **Nieaktywowane punkty** na stronie **Karty lojalnościowe**. Gdy odbiorcy zwracają pewne towary, dla których zdobyto punkty lojalnościowe, domyślnie system potrąci nienabyte punkty, a następnie odliczy salda od dostępnych punktów. Można jednak tak skonfigurować system, aby odliczać tylko dostępne punkty zamiast odejmowania od nienabytych punktów.

Ponadto sprzedawcy detaliczni mogą określać limit maksymalnej liczby punktów lojalnościowych dla każdej karty lojalnościowej. To pole umożliwia zmniejszenie negatywnych skutków oszustw w programach lojalnościowych. Po uzyskaniu maksymalnej liczby punktów lojalnościowych użytkownik nie może zdobyć ich więcej. Sprzedawca detaliczny może postanowić blokować takie karty do czasu zbadania, czy faktycznie doszło do oszustwa. W razie stwierdzenia oszustwa sprzedawca może zablokować kartę lojalnościową odbiorcy i zablokować samego odbiorcę. Aby to zrobić, należy ustawić właściwość **Blokuj rejestrację odbiorcy w programie lojalnościowym** na **Tak** w obszarze **Wszyscy odbiorcy** na skróconej karcie **Commerce**. Zablokowanym klientom nie będzie można wystawiać kart lojalnościowych w każdym z kanałów.

   ![Przysługujące i maksymalne nagrody.](./media/Vesting-and-maximum-reward-points.png "Określ przysługujące i maksymalne nagrody")

- Przynależności umożliwiają stosowanie specjalnych cen i rabatów, ale istnieją też przynależności, których sprzedawcy detaliczni nie chcą pokazywać klientom. Na przykład przynależność zatytułowana „Klient wydający dużo” może być negatywnie odbierana przez przedmiotowego odbiorcę. Ponadto istnieją przynależności, którymi nie powinno się zarządzać w sklepie. Przykładem jest przynależność „pracownicy”, ponieważ nie chcesz, aby kasjerzy decydowali, kto jest pracownikiem, i na tej podstawie przyznawali rabaty pracownicze. Sprzedawcy detaliczni mogą teraz wybierać przynależności, które mają być ukryte w kanałach. Przynależności oznaczone jako **Ukryj w kanałach** nie mogą być wyświetlane, dodawane ani usuwane w punkcie sprzedaży. Jednak ceny i rabaty skojarzone z przynależnością nadal będą stosowane do produktów.

    ![Ukryj przynależności.](./media/Hide-affiliations.png "Ukryj przynależności w kanałach")
    
- Użytkownicy w biurze obsługi mogą teraz łatwiej wyszukiwać odbiorców przy użyciu danych z ich kart lojalnościowych oraz przechodzić do stron karty lojalnościowej i transakcji na karcie lojalnościowej odbiorcy ze strony **Obsługa klienta**.

    ![Obsługa klienta.](./media/Customer-service.png "Znajdowanie informacji lojalnościowych dla odbiorcy")
    
- W razie naruszenia zabezpieczeń karty lojalnościowej należy wygenerować kartę zastępczą, a następnie przenieść do niej istniejące punkty. W tej wersji uproszczono proces wymiany karty. Ponadto klienci mogą przekazywać część lub wszystkie punkty lojalnościowe znajomym i członkom rodziny. Po przeniesieniu punktów dla każdej karty lojalnościowej są tworzone wpisy korekty punktów. Funkcje wymiany karty i przenoszenia sald są dostępne na stronie **Karty lojalnościowe**.

    ![Zamień punkty zastępowania i przenoszenia.](./media/Replace-and-transfer-points.png "Zamień kartę lojalnościową lub przenieś saldo")
    
- Sprzedawcy detaliczni mogą chcieć sprawdzać efektywność rejestrowania odbiorców w programie lojalnościowym przez określony kanał. Źródło rejestrowania kart lojalnościowych jest teraz zapisywane, dzięki czemu sprzedawcy detaliczni mogą generować raporty o tych danych. Źródło rejestracji jest automatycznie zapisywane dla wszystkich wydanych kartach lojalnościowych z aplikacji MPOS/CPOS i kanałów handlu elektronicznego. Dla kart lojalnościowych wydanych z aplikacji zaplecza użytkownik w biurze obsługi może wybrać odpowiedni kanał.
- W starszych wersjach sprzedawcy detaliczni mogli używać aplikacji MPOS/CPOS do realizowania punktów lojalnościowych odbiorców w sklepie. Jednak w tych wersjach saldo w programie lojalnościowym jest wyświetlane w punktach lojalnościowych, dlatego kasjer nie widział kwoty pieniężnej, którą można było wykorzystać w bieżącej transakcji. Kasjer musiał ręcznie przeliczyć punkty na walutę, zanim klient mógł zapłacić punktami lojalnościowymi. W obecnej wersji po dodaniu wierszy do transakcji kasjer widzi kwotę, jaką można pokryć punktami lojalnościowymi w bieżącej transakcji, dzięki czemu można łatwo zastosować część lub wszystkie punkty lojalnościowe do transakcji. Ponadto kasjer widzi punkty wygasające w ciągu najbliższych 30 dni, więc może zaproponować sprzedaż dodatkową lub wiązaną, aby zmotywować klienta do wydania wygasających punktów w tej transakcji.

    ![Saldo objęte punktami lojalnościowymi.](./media/Points-covered-by-loyalty-balance.png "Wyświetl saldo objęte punktami lojalnościowymi")

    ![Wygasające punkty.](./media/Expiring-points.png "Wyświetlanie wygasające punkty")

- W wersji 8.1.3 udostępniliśmy opcję „płatności lojalnościowej” w kanale biura obsługi. Aby włączyć tę opcję, utwórz typ lojalnościowych metod płatności i skojarz go z biurem obsługi. 

    > [!NOTE]
    > Ponieważ płatności lojalnościowe są konfigurowane jako płatności kartą, należy wybrać kartę ze strony **Ustawienia karty**. 

    ![Konfiguracja karty lojalnościowej.](./media/LoyaltyCardSetup.png "Konfiguracja karty lojalnościowej")

    Po skonfigurowaniu tej opcji odbiorcy mogą wykorzystywać swoje punkty lojalnościowe w biurze obsługi. Ulepszamy też środowisko użytkownika, aby pokazywało „Kwotę pokrywaną przez punkty lojalnościowe”, żeby użytkownicy biura obsługi nie musieli przechodzić do innego ekranu celem sprawdzenia salda w programie lojalnościowym.

- Wielu sprzedawców detalicznych przyznaje punkty lojalnościowe wyłącznie na podstawie transakcji sprzedaży, ale sprzedawcy zorientowani bardziej prokonsumencko chcą też nagradzać za każdą interakcję z marką. Na przykład chcą przyznawać punkty za wypełnienie ankiety internetowej, odwiedziny sklepu, polubienie sprzedawcy w serwisie Facebook, wysłanie tweeta o sprzedawcy itd. W tym celu sprzedawca detaliczny może zdefiniować dowolną liczbę „innego typu działań”, a następnie zdefiniować reguły zdobywania punktów za to działanie. Dostępny jest również otwarty interfejs Commerce Scale Unit API „PostNonTransactionalActivityLoyaltyPoints”, który można wywołać w przypadku identyfikacji działania, za które klient powinien otrzymać punkty lojalnościowe. Ten interfejs API oczekuje identyfikatora karty lojalnościowej, identyfikatora kanału i identyfikatora typu innego działania, tak aby klient, który powinien otrzymać punkty, mógł zostać zlokalizowany i mogła zostać zidentyfikowana zasada przyznawania punktów za działanie. 

    Przyznawanie punktów za działania nietransakcyjne zwykle ma dwa główne etapy:

    - Zarejestrowanie wykonania działania, za które należą się punkty.
    - Przyznanie odpowiedniej liczby punktów.

    Pierwszy etap jest zewnętrzny względem Commerce, na przykład wysłanie tweeta o marce lub opublikowanie linku do marki na portalu Facebook. Po zarejestrowaniu wystąpienia działania sprzedawca może wywołać powyższy interfejs Commerce Scale Unit API i przyznać punkty lojalnościowe w czasie rzeczywistym. W takich scenariuszach nie ma potrzeby kroku oceny, ponieważ aktywność już wystąpiła i powinny zostać przyznane odpowiednie punkty. Są jednak scenariusze, w których sprzedawca chce ocenić rekordy przed przyznaniem punktów. Na przykład sprzedawca ustawił warsztat w sklepie, do którego klienci rejestrują się w witrynie e-commerce lub na dowolnym innym wydarzeniu rejestrującym zgłoszenia. Jednak punkty lojalnościowe należą się tylko tym, którzy przyjdą na warsztat osobiście. W wersji 10.0 dla takich scenariuszach możemy wprowadzić jednostkę danych o nazwie **Punkty lojalnościowe w sklepie inne niż wiersze typu działania**. Ta jednostka danych umożliwia sprzedawcom używanie narzędzia importu/eksportu danych (DIXF) lub interfejsu API OData do rejestrowania działań, w których należy przyznać odbiorcom punkty lojalnościowe. Jednostka danych zapisuje działania w arkuszu o nazwie **Wierszy lojalnościowe dla innych działań**, którego można używać do celów oceny i modyfikacji. Po sprawdzeniu danych użytkownik IT może albo ręcznie zaksięgować wiersze działania lub uruchomić zadanie o nazwie **Przetwarzaj inne typy działania dla wierszy lojalności**, które zaksięguje wszystkie niezaksięgowane wiersze działania i przyzna punkty odbiorcom na podstawie reguł otrzymywania punktów. W powyższym scenariuszu wniosek o rejestrację zdarzenia wywoła interfejs OData API do wysyłania informacji do programu Commerce. Jednak użytkownik IT można zaksięgować wiersze czynności tylko tych klientów, którzy przyszli na warsztat, i usunąć wiersze działania innych klientów. 

    > [!NOTE]
    > Obecnie system zmusza użytkowników do ustawienia sekwencji numerów dla „innych typów działań”, ale nie będzie to krok wymagany w przyszłych wersjach. Aby ustawić sekwencję numerów, przejdź do opcji **Wspólne parametry handlu** \> **Sekwencje numerów** i wybierz sekwencję numerów dla pozycji **Identyfikator innego typu działania w programie lojalnościowym**.

- Aby zapewnić dobrą obsługę klienta i skutecznie rozwiązywać kwerendy klientów, kasjer musi mieć dostęp kompletnego profilu klienta. W wersji 10.0 kasjer będzie mógł wyświetlać szczegóły historii lojalnościową wraz ze skojarzonym programem lojalnościowym oraz informacje warstwy w POS.
- Jednym z czynników istotnie motywujących klientów do kupowania przez Internet jest bezpłatna lub tania dostawa. Aby umożliwić sprzedawcom detalicznym konfigurowanie promocji na dostawy, w wersji 10.0 wprowadziliśmy nowy rodzaj promocji o nazwie „Rabat progu wysyłki”, w którym sprzedawca detaliczny może definiować progi, po osiągnięciu których odbiorcy otrzymają korzyść w postaci tańszej lub bezpłatnej dostawy. Na przykład, wydaj $35, aby otrzymać darmową wysyłkę w ciągu dwóch dni lub darmową wysyłkę w ciągu dwóch dni dla wszystkich odbiorców w programie lojalnościowym. Ta funkcja wykorzystuje nową funkcję Zaawansowane opłaty automatyczne. Zobacz [dokumentację funkcji Zaawansowane opłaty automatyczne](/dynamics365/unified-operations/retail/omni-auto-charges). Zaawansowane opłaty automatyczne trzeba włączyć dla wysyłania promocji do pracy. Można je włączyć na karcie **Zamówienia odbiorcy** na stronie **Parametry handlu** oraz włączyć konfigurację "Użyj zaawansowanego automatycznego naliczania opłat". Dodatkowo, ponieważ sprzedawca może skonfigurować wiele typów opłat, takich jak obsługa czy instalacja, trzeba określić, która opłata jest uważana za opłatę transportową. Te rabaty są stosowane tylko do opłat transportowych. Aby określić opłatę jako transportową, przejdź do formularza **Kody opłaty** w menu **Sprzedaż detaliczna i inna** \> **Składniki IT w handlu detalicznym i innym** \> **Konfiguracja kanału** \> **Opłaty** i zaznacz pole wyboru „Opłata transportowa” dla żądanych opłat. Teraz można przejść do formularza **rabatu za próg wysyłki** i skonfigurować rabat.

    Podobnie jak rabat na produkty, ten rabat uwzględnia wszystkie istniejące standardowe opcje rabatu, takie jak zezwolenie sprzedawcy na ograniczenie tych rabatów za pomocą kuponów, aby tylko odbiorcy z kuponami mogli korzystać z tych rabatów. Ponadto rabaty te wykorzystują również funkcję Grup cen do określenia dostępności takich rabatów. Na przykład sprzedawca może uruchomić te promocje tylko w kanałach online i/lub w różnych kanałów dla pewnych grup odbiorców, takich jak odbiorcy w programie lojalnościowym. Gdy wiersze zamówienia z określonym trybem dostawy spełniają warunki określonego progu, rabat wysyłkowy jest stosowany i ogranicza opłatę transportową na podstawie konfiguracji rabatu. 

    > [!NOTE]
    > W przeciwieństwie do innych rabatów okresowych, takich jak ilościowy, prosty, mieszany i progowy rabat wysyłkowy nie tworzy wierszy rabatu, tylko edytuje zmiany opłaty transportowej bezpośrednio i dodaje nazwę rabatu do opisu opłaty.


[!INCLUDE[footer-include](../includes/footer-banner.md)]