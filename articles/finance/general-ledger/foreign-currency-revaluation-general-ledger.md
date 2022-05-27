---
title: Przeszacowanie w walucie obcej dla księgi głównej
description: 'W tym temacie omówiono następujące aspekty procesu przeszacowania w walucie obcej dla księgi głównej: konfiguracja, uruchamianie procesu, wykonywanie obliczeń dla procesu oraz wycofywanie transakcji przeszacowania, jeśli okaże się to konieczne.'
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.reviewer: kfend
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4a138a26a23c804f5fd358d335b04aee3897dce
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720346"
---
# <a name="foreign-currency-revaluation-for-general-ledger"></a>Przeszacowanie w walucie obcej dla księgi głównej

[!include [banner](../includes/banner.md)]

W tym temacie omówiono następujące aspekty procesu przeszacowania w walucie obcej dla księgi głównej: konfiguracja, uruchamianie procesu, wykonywanie obliczeń dla procesu oraz wycofywanie transakcji przeszacowania, jeśli okaże się to konieczne. 

Konwencje księgowe wymagają, aby podczas zamknięcia okresu salda kont księgi głównej w walutach obcych zostały przeszacowane przy użyciu różnych typów kursów wymiany (bieżących, historycznych, średnich itp.). Na przykład jedna konwencja księgowa wymaga, aby aktywa i pasywa zostały przeszacowane według bieżącego kursu wymiany, środki trwałe według historycznego kursu wymiany, a konta wynikowe według średniej miesięcznej. Funkcja przeszacowania w walucie obcej dostępna w księdze głównej może służyć do przeszacowywania wartości bilansu i rachunku zysków i strat (kont wynikowych). 

> [!NOTE]
> Funkcja przeszacowania w walucie obcej jest również dostępna w modułach Rozrachunki z odbiorcami (AR) i Rozrachunki z dostawcami (AP). Jeśli używasz tych modułów, transakcje oczekujące powinny zostać przeszacowane za pomocą funkcji przeszacowania w walucie obcej zawartej w tych modułach. Przeszacowanie w walucie obcej w modułach rozrachunków z dostawcami i odbiorcami spowoduje utworzenie zapisu księgowego w księdze głównej w celu odzwierciedlenia niezrealizowany dodatnich lub ujemnych różnic kursowych, gwarantując możliwość uzgodnienia ksiąg podrzędnych z księgą główną. Ponieważ funkcja przeszacowania w walucie obcej w modułach AR i AP tworzy zapisy księgowe w księdze głównej, konta główne w modułach rozrachunków z odbiorcami i dostawcami powinny być wykluczone z przeszacowania w walucie obcej w księdze głównej. 

Podczas wykonywania procesu przeszacowania następuje przeszacowanie salda każdego konta głównego zaksięgowane w walucie obcej. Transakcje niezrealizowanych dodatnich lub ujemnych różnic kursowych, które są tworzone podczas procesu przeszacowania, są generowane przez system. W razie potrzeby mogą być tworzone dwie transakcje: jedna dla waluty rozliczeniowej i druga dla waluty raportowania. Każdy zapis księgowy zostanie zaksięgowany jako niezrealizowana dodatnia lub ujemna różnica kursowa i dodatkowo na przeszacowywanym koncie głównym.

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

Pole **Data kursu** może służyć do zdefiniowania daty, z której ma domyślnie pochodzić kurs wymiany. Na przykład można przeszacować salda w przedziale dat od 1 do 31 stycznia, ale użyć kursu wymiany zdefiniowanego na 1 lutego. 

Wskaż, które konta główne mają zostać przeszacowane: Wszystkie, Bilans lub Wynikowe. Przeszacowane zostaną tylko konta główne oznaczone do przeszacowania (na stronie Konto główne). Jeśli chcesz dodatkowo ograniczyć zakres kont głównych, na karcie **Rekordy do uwzględnienia** zdefiniuj zakres kont głównych lub poszczególne konta główne. 

Proces przeszacowania można uruchomić dla jednej lub wielu firm. Wyszukiwanie spowoduje wyświetlenie tylko tych firm, do których masz dostęp. . Następnie zaznacz firmy, dla których ma zostać uruchomiony proces przeszacowania. 

Przeszacowanie może być uruchomione dla jednej lub kilku walut obcych. Wyszukiwanie obejmie wszystkie waluty, w których księgowano transakcje w przedziale dat odpowiednim dla typu konta głównego (bilansowe lub wynikowe) firm wybranych do przeszacowania. Waluta rozliczeniowa znajdzie się na liście, ale jej zaznaczenie spowoduje, że nie nastąpi żadne przeszacowanie. 

Jeśli chcesz przejrzeć spodziewane wyniki przeszacowania księgi głównej, w opcji **Wyświetl podgląd przed zaksięgowaniem** zaznacz wartość **Tak**. Podgląd w księdze głównej różni się od symulacji przeszacowania w walucie obcej w modułach rozrachunków z dostawcami i odbiorcami. Symulacja w tych modułach jest raportem, podczas gdy księga główna oferuje funkcję podglądu umożliwiającą zaksięgowanie, bez konieczności ponownego uruchamiania procesu przeszacowania. Wyniki w podglądzie mogą być eksportowane do programu Microsoft Excel, aby zachować historię obliczania kwot. Jeżeli chcesz wyświetlić podgląd wyników przeszacowania, nie można użyć przetwarzania wsadowego. Z poziomu okna podglądu użytkownik może zaksięgować wyniki wszystkich firm za pomocą przycisku **Księguj**. W przypadku problemów z wynikami pewnej firmy użytkownik ma także możliwość zaksięgowania przeszacowania tylko dla podzbioru firm, używając przycisku **Wybierz firmy do księgowania**. 

Po zakończeniu procesu przeszacowania w walucie obcej zostanie utworzony rekord, co pozwala śledzić historię wszystkich sesji.  Oddzielne rekordy są tworzone dla każdej firmy i warstwy księgowania.

## <a name="calculate-unrealized-gainloss"></a>Obliczanie niezrealizowanych dodatnich/ujemnych różnic kursowych
Transakcje niezrealizowanych dodatnich/ujemnych różnic kursowych są tworzone inaczej w procesach przeszacowania dla księgi głównej i dla modułów rozrachunków z dostawcami i odbiorcami. W modułach rozrachunków z dostawcami i odbiorcami poprzednie przeszacowanie jest całkowicie stornowane (przy założeniu, że transakcja nie jest jeszcze rozliczona), po czym jest tworzona nowa transakcja przeszacowania dla niezrealizowanych dodatnich/ujemnych różnic kursowych na podstawie nowego kursu wymiany. Jest to spowodowane tym, że w modułach rozrachunków z dostawcami i odbiorcami jest przeszacowywana każda indywidualna transakcja. W księdze głównej poprzednie przeszacowanie nie jest wycofywane. Zamiast tego jest tworzona transakcja na różnicę między saldem konta głównego, włącznie z wszelkimi poprzednimi kwotami przeszacowania, a nową wartością opartą na kursie wymiany z dnia Data kursu. 

**Przykład** Istnieją następujące salda dla konta głównego 110110.

| Data   | Konto finansowe| Kwota transakcji | Kwota księgowa |
|------------|--------------------|------------------------|-----------------------|
| 20 stycznia | 110110 (gotówka)      | 500 EUR (strona debetowa)        | 1000 USD (strona debetowa)      |

Konto główne zostało przeszacowane 31 stycznia.  Niezrealizowana dodatnia/ujemna różnica kursowa jest obliczana w następujący sposób.

| Bieżące saldo w walucie transakcji | Bieżące saldo w walucie rozliczeniowej | Kursy wymiany w dniu przeszacowania | Nowa kwota w walucie rozliczeniowej | Niezrealizowana dodatnia/ujemna różnica kursowa    |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833,33 USD (500 x 1,666667)        | Różnica ujemna 166,67 (833,33 – 1000) |

Zostanie utworzony następujący zapis księgowy.

| Data   | Konto finansowe       | Uznanie | Strona kredytowa |
|------------|--------------------------|-----------|------------|
| 31 stycznia | 110110 (gotówka)            |           | 166.67     |
| 31 stycznia | 801400 (niezrealizowana ujemna różnica kursowa) | 166.67    |            |

W lutym nie zaksięgowano żadnych nowych transakcji.  Konto główne zostało przeszacowane 28 lutego.

| Bieżące saldo w walucie transakcji | Bieżące saldo w walucie rozliczeniowej | Kursy wymiany w dniu przeszacowania | Nowa kwota w walucie rozliczeniowej | Niezrealizowana dodatnia/ujemna różnica kursowa    |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR                                     | 833,33 USD (1000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | Dodatnia różnica kursowa 416,67 (1250 – 833,33) |

Zostanie utworzony następujący zapis księgowy.

| Data    | Konto finansowe       | Uznanie | Strona kredytowa |
|-------------|--------------------------|-----------|------------|
| 28 lutego | 110110 (gotówka)            | 416.67    |            |
| 28 lutego | 801600 (niezrealizowana dodatnia różnica kursowa) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Cofanie przeszacowania w walucie obcej
Jeśli musisz wycofać transakcję przeszacowania, kliknij przycisk **Wycofaj transakcję** znajdujący się na stronie **Przeszacowanie w walucie obcej**. Zostanie utworzony nowy rekord historyczny przeszacowania w walucie obcej na potrzeby prowadzenia dziennika historii pokazującego, kiedy przeszacowania nastąpiły lub zostały wycofane. 

Można cofnąć wyniki przeszacowania bez zachowania chronologii, ale wtedy może być również konieczne wystornowanie nowszego przeszacowania, aby zapewnić poprawność sald wszystkich przeszacowywanych kont głównych. Cofnięcie może nastąpić bez zachowania chronologii, ponieważ nie ma możliwości kontrolowania, które konta główne są przeszacowywane i jaką częstotliwością. Na przykład organizacja może zdecydować się na przeszacowywanie kont głównych środków pieniężnych co kwartał, ale wszystkich pozostałych kont głównych co miesiąc.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
