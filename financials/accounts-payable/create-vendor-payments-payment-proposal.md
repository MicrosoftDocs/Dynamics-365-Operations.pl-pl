---
title: "Tworzenie płatności dla dostawców za pomocą propozycji płatności"
description: "Ten temat zawiera omówienie opcji propozycji płatności wraz z przykładami pokazującymi działanie propozycji płatności. Propozycje płatności są często używane do tworzenia płatności dostawcy, ponieważ za pomocą zapytań można szybko wybrać faktury dostawcy do zapłaty na podstawie kryteriów takich jak termin i rabat gotówkowy."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: b46037b9509f329e18f0da69d530f6b1f88c8888
ms.lasthandoff: 03/31/2017


---

# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Tworzenie płatności dla dostawców za pomocą propozycji płatności

Ten temat zawiera omówienie opcji propozycji płatności wraz z przykładami pokazującymi działanie propozycji płatności. Propozycje płatności są często używane do tworzenia płatności dostawcy, ponieważ za pomocą zapytań można szybko wybrać faktury dostawcy do zapłaty na podstawie kryteriów takich jak termin i rabat gotówkowy. 

Organizacje często używają propozycji płatności do tworzenia płatności dla dostawców, ponieważ przy użyciu propozycji płatności można szybko wybrać faktury od dostawcy do zapłacenia na podstawie terminu, rabatu gotówkowego i innych kryteriów. 

Kwerenda propozycji płatności zawiera różne karty, z których każda ma różne opcje wyboru faktur do zapłaty. **Parametr** karta zawiera opcje, których większość organizacji korzysta najczęściej. Na **rekordy dołączane** skróconej można określić, które faktury lub nabywcy do włączenia do zapłaty przez Definiowanie zakresów dla różnych charakterystyk. Na przykład jeśli chcesz zapłacić określony zakres dostawców, można zdefiniować filtr dla zakresu dostawcy. Ta funkcja służy często do wybierz opcję faktury dla konkretnej metody płatności. Na przykład, jeśli zdefiniować filtr gdzie **metody płatności** = **sprawdzić**, wybrano tylko faktur, które zostały tej metody płatności dla płatności, pod warunkiem, że spełniają one również inne kryteria, które są określone w kwerendzie. Karta **Parametry zaawansowane** zawiera dodatkowe opcje. Niektóre z nich mogą nie być odpowiednie dla danej organizacji. Na przykład ta karta zawiera opcje płatności faktur w ramach płatności scentralizowanych.

## <a name="parameters"></a>Parametry
-   **Wybierz opcję faktury przez** – faktur w zakres dat, który jest określony przez **od daty** i **do tej pory** pól można wybrać według daty wykonania, daty rabatu gotówkowego lub obu. Jeśli używasz daty rabatu gotówkowego, system szuka najpierw faktur, które mają daty rabatu gotówkowego między od dnia i do dnia. Następnie system za pomocą daty sesji określa, czy faktura kwalifikuje się do uzyskania rabatu gotówkowego, aby mieć pewność, że data rabatu nie upłynęła.
-   **Od dnia** i** Do dnia** — faktury z datą płatności lub rabatu gotówkowego w tym zakresie dat zostaną zaznaczone do opłacenia.
-   **Data płatności** — jeśli została zdefiniowana, wszystkie płatności zostaną utworzone tego dnia. Pole **Minimalna data płatności** jest ignorowane.
-   **Minimalna data płatności** — służy do wprowadzania daty minimalnej płatności. Na przykład **od daty** i **do tej pory** należy podać zakres od 1 września do 10 września, a datą minimalnej płatności 5 września. W takim przypadku wszystkie faktury z datą płatności od 1 września do 5 września mają daty płatności 5 września. Jednak wszystkie faktury z datą płatności od 5 września do 10 września mieć datę płatności, która jest równa termin realizacji każdej faktury.
-   **Limit kwoty** — wprowadź maksymalną kwotę całkowitą dla wszystkich płatności.
-   **Tworzenie płatności bez podglądu faktury** -Jeśli ta opcja jest ustawiona na **tak**, płatności zostanie utworzony natychmiast na **płatności dostawcy** strony. **Propozycji płatności** strona zostanie pominięta. Dzięki temu płatności zostaną utworzone szybciej. Płatności mogą być nadal modyfikowane na stronie **Płatności dostawcy**. Można też wrócić na stronę **propozycji płatności**, klikając przycisk **Edytuj faktury dla wybranej płatności**.

## <a name="advanced-options"></a>Opcje zaawansowane
-   **Sprawdź saldo dostawcy** — jeśli ta opcja jest ustawiona jako **Tak**, system sprawdza przed opłaceniem faktur, czy dostawca nie ma salda debetowego. Jeśli sprzedawca ma saldo debetowe, płatność nie jest tworzony. Na przykład dostawca może mieć faktury korygujące lub płatności, które zostały zaksięgowane, ale jeszcze nie została jeszcze rozliczona. W takim przypadku nie należy płacić dostawcy. Zamiast tego noty kredytowe lub płatności powinny zostać rozliczone względem niezapłaconych faktur.
-   **Usuń ujemne płatności** — opcja ta działa różnie, w zależności od tego, czy płatności dotyczą poszczególnych faktur czy sumy faktur spełniających kryteria płatności. Ta opcja jest określana w metodzie płatności.
-   **Płatność dla każdej faktury** — jeśli opcja **Usuń ujemne płatności** jest ustawiona jako **Tak**, a istnieją nierozliczone faktury i płatności dla dostawcy, tylko faktura zostanie zaznaczona do płatności. Płatność jest rozliczana na podstawie faktury na kwotę. Jeśli opcja **Usuń ujemne płatności** jest ustawiona jako **Nie**i nie są rozliczane faktury i płatności, do zapłacenia zostaną wybrane i faktury i płatności. Dla płatności jest tworzona płatność i zwrot (płatność ujemna).
-   **Płatności dla sumy faktur** — w przypadku ustawienia opcji **Usuń ujemne płatności** jako **Tak**, a istnieją nierozliczone faktury i płatności dla dostawcy, do płatności zostanie wybrana nierozliczona faktura i płatność, a kwoty te są sumowane w łączną kwotę płatności. Jedyny wyjątek występuje wtedy, jeśli suma skutkuje zwrotem. W takim przypadku faktury ani płatności nie są zaznaczane. Jeśli ** Usuń ujemne płatności ** opcja jest ustawiona na **nr**, faktury i płatności nie są rozliczane, zarówno faktury i płatności są wybrane do płatności i kwoty są dodawane łącznie do produkcji łącznej kwoty płatności.
-   **Drukuj tylko raport** — ustaw tę opcję jako **Tak**, aby zobaczyć wyniki propozycji płatności w raporcie, ale bez tworzenia płatności.
-   **Uwzględnij faktury od dostawców z innych firm** — jeśli dana organizacja ma scentralizowany proces płatności i propozycji płatności, a propozycja płatności powinna uwzględniać faktury z innych firm zamieszczonych w kryteriach wyszukiwania, ustaw tę opcję na **Tak**.
-   **Proponuj osobną płatność dostawcy dla każdej firmy** — jeśli ta opcja jest ustawiona jako **Tak**, dla każdej firmy zostanie utworzona osobna płatność na dostawcę. Dostawca w płatności jest taki sam jak na fakturze z każdej firmy. Jeśli ta opcja została ustawiona jako **Nie**, a ten sam dostawca ma faktury w wielu podmiotach prawnych, zostanie utworzona jedna płatność na łączną kwotę z wybranych faktur. Dostawca na płatności jest taki sam jak dostawca w bieżącej firmie. Jeśli nie istnieje konto dostawcy w bieżącej firmie, używane jest konto dostawcy dla pierwszej faktury do zapłaty.
-   **Waluta płatności** — to pole określa waluty, w której wszystkie płatności są tworzone w. Jeśli waluta nie jest zdefiniowana, płatności każdej faktury w walucie faktury.
-   **Dzień roboczy dla płatności** — umożliwia wprowadzenie dnia tygodnia, gdy płatność powinna zostać wykonana. To pole jest używane tylko wtedy, gdy skonfigurowano metody płatności do sumy faktur do zapłaty w określonym dniu tygodnia.
-   **Typ konta przeciwstawnego** i **konto przeciwstawne** — ustaw te pola, aby zdefiniować typ określonego konta (takie jak **księgi** lub **Bank**) i przeciwstawne konto (na przykład określonego konta bankowego). Metoda płatności dla faktury definiuje domyślny typ konta przeciwstawnego i koncie przeciwstawnym, ale można użyć tych pól do zastępowania wartości domyślnych.
-   **Dodatkowe filtry** – nad **rekordy dołączane** skróconej, można zdefiniować dodatkowe zakresy kryteriów. Na przykład jeśli chcesz zapłacić w zakresie dostawców, można zdefiniować filtr dla zakresu dostawcy. Ta funkcja służy często do wybierz opcję faktury dla konkretnej metody płatności. Na przykład, jeśli zdefiniować filtr gdzie **metody płatności** = **sprawdzić**, wybrano tylko faktur, które zostały tej metody płatności dla płatności, pod warunkiem, że spełniają one również inne kryteria, które są określone w kwerendzie.

## <a name="scenarios"></a>Scenariusze
| Dostawca | Faktura | Data faktury | Kwota faktury | Data wymagalności | Data rabatu gotówkowego | Kwota rabatu gotówkowego |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | 15 czerwca      | 500,00         | 15 lipca  | 29 czerwca            | 10,00                |
| 3050   | 1002    | 20 czerwca      | 600,00         | 20 lipca  | 4 lipca             | 12,00                |
| 3075   | 1003    | 15 czerwca      | 250,00         | 29 czerwca  |                    | 0,00                 |
| 3100   | 1004    | 17 czerwca      | 100,00         | 17 lipca  | 1 lipca             | 1,00                 |

W dniu 1 lipca April płaci dostawcom. Używa propozycji płatności, aby szybciej zrealizować zadanie.

### <a name="option-1-by-cash-discount"></a>Opcja 1: Według rabatu gotówkowego

April wybiera **rabat gotówkowy** jako typ propozycji. Wprowadza ona datę zakresu czerwca 26 do 10 lipca. Następujące faktury mają być uwzględniane w propozycji:

-   1002, ponieważ data rabatu 4 lipca mieści się w zakresie dat płatności.
-   1004, ponieważ data rabatu 1 lipca mieści się w zakresie dat płatności.

Następujące faktury nie są uwzględnione w propozycji:

-   1001, ponieważ data rabatu 29 czerwca już minęła, więc ta faktura nie spełnia kryteriów uzyskania rabatu gotówkowego.
-   1003, ponieważ ta faktura nie ma daty rabatu.

### <a name="option-2-by-due-date"></a>Opcja 2: według terminu płatności

April wybiera **Według terminu płatności** jako typ propozycji. Wprowadza ona datę zakresu czerwca 26 do 10 lipca. Następujące faktury mają być uwzględniane w propozycji:

-   1003, ponieważ termin płatności 29 czerwca mieści się w zakresie dat płatności.

Następujące faktury nie są uwzględnione w propozycji:

-   1001, ponieważ termin płatności 15 lipca nie mieści się w zakresie dat płatności.
-   1002, ponieważ termin płatności 20 lipca nie mieści się w zakresie dat płatności.
-   1004, ponieważ termin płatności 17 lipca nie mieści się w zakresie dat płatności.

### <a name="option-3-by-due-date-and-cash-discount"></a>Opcja 3: Według daty i rabatu gotówkowego

April wybiera **Termin i rabat gotówkowy** jako typ propozycji. Wprowadza ona datę zakresu czerwca 26 do 10 lipca. Następujące faktury mają być uwzględniane w propozycji:

-   1003, ponieważ termin płatności 29 czerwca mieści się w zakresie dat płatności.
-   1002, ponieważ data rabatu 4 lipca mieści się w zakresie dat płatności.
-   1004, ponieważ data rabatu 1 lipca mieści się w zakresie dat płatności.

Następujące faktury nie są uwzględnione w propozycji:

-   1001, ponieważ data rabatu 29 czerwca już minęła, więc ta faktura nie kwalifikuje się do uzyskania rabatu gotówkowego, a termin 15 lipca również jest poza zakresem dat.

## <a name="country-specific-considerations"></a>Zagadnienia specyficzne dla krajów
### <a name="norway"></a>Norwegia

#### <a name="dimension-control"></a>Kontrola wymiarów

Funkcja kontroli wymiarów umożliwia kontrolowanie grupowania wierszy generowanych przez propozycję płatności oraz ustawianie domyślnych wymiarów na podstawie wymiarów finansowych używanych w stosowanych fakturach. W krajowym kontekście norweskim dla każdej metody płatności istnieje karta wymiaru finansowego, gdzie można uaktywnić kontrolę wymiaru oraz włączyć grupowanie dla każdego wymiaru. Dostępne są następujące opcje:

-   Pole **Kontrola wymiarów** jest nieaktywne. Propozycja płatności działa tak, jak w przypadku jakiegokolwiek innego kraju.
-   Pole **Kontrola wymiarów** jest uaktywnione bez dalszego definiowania wymiarów. Propozycja płatności zostanie utworzona bez brania wymiarów pod uwagę. Utworzona transakcja nie dziedziczy żadnych wymiarów z zastosowanego zapisu.
-   Pole **Kontrola wymiarów** jest uaktywnione i włączono dodatkowe wymiary. Teraz można zdefiniować sposób kopiowania wymiarów do arkusza. Na przykład: • Wybierz **jednostką biznesową** pole wyboru, aby utworzyć propozycję płatności za jednostkę biznesową dla metody płatności, • wybierz **funkcja** pole wyboru, aby utworzyć propozycję płatności na MPK dla metody płatności

**Uwaga:** W przypadku wybrania kilku wymiarów w trzeciej opcji propozycja płatności zostanie utworzona z uwzględnieniem połączenia tych wymiarów.

#### <a name="bank-account-selection"></a>Wybór konta bankowego

Dla każdej metody płatności można zdefiniować standardowe konto płatności obciążających niezależnie od kontekstu krajowego. Konto jest ustawiane w wierszach płatności generowanych przez propozycję. Za pomocą funkcji konta bankowego można zdefiniować wiele kont bankowych obciążeń, które będą zarządzane według wymiaru i waluty lub ich dowolnej kombinacji, i używać różnych kont zależnie od potrzeb. Można skonfigurować te kombinacje w **metod płatności** stronę za pomocą **kont bankowych** przycisk dostępny dla każdej metody płatności w systemie **typu konta księgowania** = **Bank**.


