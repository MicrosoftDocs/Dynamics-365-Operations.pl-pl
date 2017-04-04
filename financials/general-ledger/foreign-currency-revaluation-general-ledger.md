---
title: "Przeszacowanie w walucie obcej dla księgi głównej"
description: "Ten temat zawiera omówienie następujących dla procesu przeszacowania waluty obcej księgi głównej - programu instalacyjnego, proces obliczania dla procesu i informacje dotyczące wycofywania transakcji przeszacowania, jeśli to konieczne."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5d6d13fe44eef7766b4dcaf274c3522bce3da816
ms.lasthandoff: 03/31/2017


---

# <a name="foreign-currency-revaluation-for-general-ledger"></a>Przeszacowanie w walucie obcej dla księgi głównej

Ten temat zawiera omówienie następujących dla procesu przeszacowania waluty obcej księgi głównej - programu instalacyjnego, proces obliczania dla procesu i informacje dotyczące wycofywania transakcji przeszacowania, jeśli to konieczne. 

Konwencje księgowe wymagają, aby podczas zamknięcia okresu salda kont księgi głównej w walutach obcych zostały przeszacowane przy użyciu różnych typów kursów wymiany (bieżących, historycznych, średnich itp.). Na przykład jedna konwencja księgowa wymaga, aby aktywa i pasywa zostały przeszacowane według bieżącego kursu wymiany, środki trwałe według historycznego kursu wymiany, a konta wynikowe według średniej miesięcznej. Funkcja przeszacowania w walucie obcej dostępna w księdze głównej może służyć do przeszacowywania wartości bilansu i rachunku zysków i strat (kont wynikowych). 

> [!NOTE]
> Przeszacowanie w walucie obcej jest również dostępna w module Rozrachunki z odbiorcami (AR) i rozrachunków z dostawcami (AP). Jeśli używasz tych modułów zaległe transakcje powinna zostać przeszacowana przy użyciu przeszacowania w walucie obcej w tych modułach. Przeszacowanie w walucie obcej w modułach rozrachunków z dostawcami i odbiorcami spowoduje utworzenie zapisu księgowego w księdze głównej w celu odzwierciedlenia niezrealizowany dodatnich lub ujemnych różnic kursowych, gwarantując możliwość uzgodnienia ksiąg podrzędnych z księgą główną. Ponieważ funkcja przeszacowania w walucie obcej w modułach AR i AP tworzy zapisy księgowe w księdze głównej, konta główne w modułach rozrachunków z odbiorcami i dostawcami powinny być wykluczone z przeszacowania w walucie obcej w księdze głównej. 

Podczas wykonywania procesu przeszacowania następuje przeszacowanie salda każdego konta głównego zaksięgowane w walucie obcej. Transakcje niezrealizowanych dodatnich lub ujemnych różnic kursowych, które są tworzone podczas procesu przeszacowania, są generowane przez system. Dwie transakcje mogą być tworzone, jednej waluty rozliczeniowej i drugiej waluty raportowania, stosownych. Każdy wpis księgowania zostanie zaksięgowany niezrealizowany zysk lub strata i przeszacowywanych konta głównego.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Przygotowanie do wykonania przeszacowania w walucie obcej
Przed uruchomieniem procesu przeszacowania potrzebne jest wykonanie następującej konfiguracji.

-   Na stronie **Konto główne**:
-   Jeśli konto główne ma zostać przeszacowane w księdze głównej, zaznacz opcję **Przeszacowanie w walucie obcej**. Jeśli konto główne nie powinno zostać przeszacowane (np. w modułach rozrachunków z odbiorcami i dostawcami, jeśli przeszacowanie odbywa się w księgach podrzędnych), wyczyść tę opcję.
-   Jeśli konto główne jest oznaczone do przeszacowania, wypełnij pole **Typ kursu wymiany**. Ten typ kursu wymiany będzie stosowany do przeszacowania konta głównego. Osobne pole **Typ kursu wymiany dla raportowania finansowego** jest dostępny dla sprawozdawczości finansowej. Te dwa pola nie są synchronizowane, co pozwala na używanie różnych typów kursów wymiany na potrzeby przeszacowania i sprawozdawczości finansowej.

-   Na stronie **Księga**:
-   Wypełnij pole **Typu kursu wymiany**. Jeśli typ kursu wymiany nie jest określony na koncie głównym, ten typ kursu wymiany będzie używany podczas przeszacowywania w walucie obcej.
-   Określ konta zrealizowanych oraz niezrealizowanych dodatnich i ujemnych różnic kursowych dla przeszacowania waluty. Konta zrealizowanych dodatnich i ujemnych różnic kursowych są używane do rozliczania transakcji w modułach AR i AP, a konta niezrealizowanych dodatnich i ujemnych różnic kursowych są używane do przeszacowywania otwartych transakcji na kontach głównych księgi głównej.

-   Na stronie **Konta przeszacowania waluty**:
-   Wybierz różne konta przeszacowania waluty dla każdej waluty i firmy. Jeśli nie zdefiniowano żadnych kont, używane są konta ze strony **Księga**.

## <a name="process-foreign-currency-revaluation"></a>Przetwarzanie przeszacowania w walucie obcej
Po zakończeniu konfigurowania użyj strony **Przeszacowanie w walucie obcej**, aby przeszacować salda kont głównych Można uruchomić proces w czasie rzeczywistym lub zaplanować uruchomienie przy użyciu zadania wsadowego. 

Na stronie **Przeszacowanie w walucie obcej** jest wyświetlana historia każdego procesu przeszacowania, w tym czas jego wykonania, zdefiniowane kryteria, łącze do załącznika utworzonego dla przeszacowania oraz informacja, czy poprzednie przeszacowanie zostało wycofane. Aby uruchomić proces przeszacowania, kliknij przycisk **Przeszacowanie w walucie obcej**. 

Wartości **Od dnia** i **Do dnia** określają przedział dat do obliczania salda w walucie obcej, które zostanie przeszacowane. Podczas przeszacowywania konta wynikowego jest przeszacowywana suma wszystkich transakcji, jakie nastąpiły w przedziale dat. Podczas przeszacowywania kont bilansowych data w polu Od dnia jest ignorowana. Zamiast tego saldo do przeszacowania obejmuje okres od początku roku obrachunkowego do obecnego dnia. 

**Data kursu** może służyć do definiowania daty, dla której należy domyślnie kursu wymiany. Na przykład można przeszacować równowagi między datą zakres od 1 stycznia do 31 stycznia, ale użyty kurs wymiany zdefiniowany dla 1 lutego. 

Wskaż, które konta główne mają zostać przeszacowane: Wszystkie, Bilans lub Wynikowe. Tylko konta główne oznaczone do przeszacowania (na stronie konta głównego) przeszacowane. Jeśli chcesz jeszcze bardziej ograniczyć zakres kont głównych, należy wykorzystać rekordy **aby uwzględnić** kartę, aby zdefiniować zakres kont głównych lub poszczególnych kont głównych. 

Proces aktualizacji wyceny mogą być uruchamiane dla jednego lub więcej podmiotów prawnych. Wyszukiwania zostaną wyświetlone tylko osoby prawne do których masz dostęp. Wybierz osoby prawne, dla których chcesz uruchomić proces aktualizacji wyceny. 

Przeszacowanie może być uruchomione dla jednej lub kilku walut obcych. Wyszukiwanie obejmie wszystkie waluty, które zostały zaksięgowane w zakresie odpowiednich dla typu konta głównego (bilans lub zysków i strat), dla osób prawnych wybrane do przeszacowywania. Walutą rozliczeniową znajdują się na liście, ale nic nie przeszacowane, jeśli walutą rozliczeniową jest zaznaczone. 

Ustaw **podgląd przed wysłaniem** do **tak** Jeśli chcesz przejrzeć wynikiem przeszacowania księgi głównej. Podgląd w ogóle księgi różni się od symulacji w AR i AP przeszacowania w walucie obcej. Symulacja w AR i AP jest raportem, ale księgi głównej wyposażona w klip podglądu, który można zaksięgować bez konieczności ponownie uruchomić proces aktualizacji wyceny. Wyniki w podglądzie mogą być eksportowane do programu Microsoft Excel, aby zachować historię obliczania kwot. Jeżeli chcesz wyświetlić podgląd wyników przeszacowania, nie można użyć przetwarzania wsadowego. Z poziomu okna podglądu użytkownik może zaksięgować wyniki wszystkich firm za pomocą przycisku **Księguj**. W przypadku problemów z wynikami pewnej firmy użytkownik ma także możliwość zaksięgowania przeszacowania tylko dla podzbioru firm, używając przycisku **Wybierz firmy do księgowania**. 

Po zakończeniu procesu przeszacowania w walucie obcej do śledzenia historii każdego uruchomienia zostanie utworzony rekord.  Oddzielny rekord zostanie utworzony dla każdej osoby prawnej i warstwy księgowania.

## <a name="calculate-unrealized-gainloss"></a>Obliczanie niezrealizowanych dodatnich/ujemnych różnic kursowych
Transakcje niezrealizowanych dodatnich/ujemnych różnic kursowych są tworzone inaczej w procesach przeszacowania dla księgi głównej i dla modułów rozrachunków z dostawcami i odbiorcami. W modułach rozrachunków z dostawcami i odbiorcami poprzednie przeszacowanie jest całkowicie stornowane (przy założeniu, że transakcja nie jest jeszcze rozliczona), po czym jest tworzona nowa transakcja przeszacowania dla niezrealizowanych dodatnich/ujemnych różnic kursowych na podstawie nowego kursu wymiany. Jest to spowodowane tym, że w modułach rozrachunków z dostawcami i odbiorcami jest przeszacowywana każda indywidualna transakcja. Poprzednie przeszacowania nie jest wycofane w księdze głównej. Zamiast tego transakcja jest tworzony dla delta między saldo konta głównego, w tym wszelkich poprzednich kwot przeszacowania i nową wartość, według kursu wymiany dla daty kursu. 

**Przykład** dla konta głównego 110110 istnieją następujące salda.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Data**   | **Konto finansowe** | **Kwota transakcji** | **Kwota księgowa** |
| 20 stycznia | 110110 (gotówka)      | 500 EUR (strona debetowa)        | 1000 USD (strona debetowa)      |

Konto główne jest rewaluowane z dniem 31 stycznia.  Niezrealizowany zysk/strata obliczana jest w następujący sposób.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Bieżące saldo w walucie transakcji** | **Bieżące saldo w walucie rozliczeniowej** | **Kursy wymiany w dniu przeszacowania** | **Nowa kwota w walucie rozliczeniowej** | **Niezrealizowana dodatnia/ujemna różnica kursowa**    |
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833,33 EUR (500 x 1,666667)        | Różnica ujemna 166,67 (833,33 – 1000) |

Zostanie utworzony następujący zapis księgowy.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **Data**   | **Konto finansowe**       | **Strona debetowa** | **Strona kredytowa** |
| 31 stycznia | 110110 (gotówka)            |           | 166.67     |
| 31 stycznia | 801400 (niezrealizowana ujemna różnica kursowa) | 166.67    |            |

Żadne nowe transakcje są księgowane w miesiącu lutym.  Konto główne jest rewaluowane z dniem 28 lutego.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Bieżące saldo w walucie transakcji** | **Bieżące saldo w walucie rozliczeniowej** | **Kursy wymiany w dniu przeszacowania** | **Nowa kwota w walucie rozliczeniowej** | **Niezrealizowana dodatnia/ujemna różnica kursowa**    |
| 500 EUR                                     | 833,33 USD (1000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | Dodatnia różnica kursowa 416,67 (1250 – 833,33) |

Zostanie utworzony następujący zapis księgowy.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **Data**    | **Konto finansowe**       | **Strona debetowa** | **Strona kredytowa** |
| 28 lutego | 110110 (gotówka)            | 416.67    |            |
| 28 lutego | 801600 (niezrealizowana dodatnia różnica kursowa) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Cofanie przeszacowania w walucie obcej
Jeśli musisz wycofać transakcję przeszacowania, kliknij przycisk **Wycofaj transakcję** znajdujący się na stronie **Przeszacowanie w walucie obcej**. Zostanie utworzony nowy rekord historyczny przeszacowania w walucie obcej na potrzeby prowadzenia dziennika historii pokazującego, kiedy przeszacowania nastąpiły lub zostały wycofane. 

Wyniki przeszacowania spośród kolejność dat można cofnąć, ale konieczne może być również odwrócić bardziej aktualnej przeszacowania do zapewnienia właściwych sald dla każdego przeszacowanego konta głównego. Odwrócenie może występować zamówienia nieaktualne, ponieważ jest sposobem kontroli konta główne, które przeszacowuje się i częstotliwość kiedy one przeszacowane. Na przykład organizacja może zdecydować się na co miesiąc przeszacować ich kont głównych środków pieniężnych na bazie kwartalnej, ale wszystkie inne konta głównego.


