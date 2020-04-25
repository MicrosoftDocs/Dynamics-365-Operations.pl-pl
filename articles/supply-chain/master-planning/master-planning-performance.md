---
title: Zwiększanie wydajności planowania głównego
description: W tym temacie objaśniono różne opcje, które mogą pomóc w poprawie wydajności planowania głównego lub rozwiązywaniu problemów.
author: t-benebo
manager: tfehr
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 01db8a02e57c61daf940e2f459124a857ced68cb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213614"
---
# <a name="improve-master-planning-performance"></a>Zwiększanie wydajności planowania głównego

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

W tym temacie objaśniono różne opcje, które mogą pomóc w poprawie wydajności planowania głównego lub rozwiązywaniu problemów. Zawiera informacje o parametrach i ustawieniach oraz zalecane konfiguracje i akcje. Zawiera on także podsumowanie wszystkich ważnych parametrów, które należy wziąć pod uwagę w przypadku długotrwałych zadań planowania głównego.

Ten temat jest przeznaczony dla administratorów systemu lub użytkowników systemów informatycznych, którzy mają możliwość rozwiązania problemu. Jest on również przeznaczony do planowania produkcji lub dostaw, ponieważ zawiera informacje o parametrach związanych z wymaganiami dotyczącymi planowania biznesowego. 

## <a name="parameters-related-to-master-planning-performance"></a>Parametry związane z wydajnością planowania głównego

Różne parametry wpływają na czas pracy planowania głównego i powinny być brane pod uwagę.

### <a name="number-of-threads"></a>Liczba wątków

Parametr **Liczba wątków** umożliwia dostosowanie procesu planowania głównego w celu zwiększenia wydajności określonego zbioru danych. Ten parametr określa łączną liczbę wątków, które zostaną użyte w celu uruchomienia planowania głównego. Powoduje to paralelizację procesu planowania głównego, która pomaga w zmniejszeniu czasu działania systemu. 

Można określić paramentr **Liczby wątków** w oknie dialogowym **Uruchom planowanie główne**. By otworzyć to okno dialogowe, przejdź do **Planowania głównego \> planowania głównego \> Uruchom \> Planowania głównego** lub wybierz opcję **Uruchom** w obszarze roboczym **Planowanie główne**. Aby określić najlepszą wartość tego parametru, należy przeprowadzić metodę prób i błędów. Można jednak obliczać wartość początkową przy użyciu następujących formuł:

- **Jeśli używany jest przemysł produkcyjny:** (Liczba wątków) = (Liczba zamówień planowanych ÷ 1000)
- **W przeciwnym razie:** (Liczba wątków) = (Liczba pozycji ÷ 1000)

Liczba pomocników używanych podczas planowania głównego musi być mniejsza lub równa maksymalnej liczbie wątków, które są dozwolone na serwerze przetwarzania wsadowego. Jeśli liczba pomocników przekracza liczbę wątków na serwerze przetwarzania wsadowego, dodatkowe wątki nie wykonują żadnej pracy.

> [!NOTE]
> Ustawienie parametru **Liczba wątków** na **0** (zero) wydłuża czas wykonywania planowania głównego. Dlatego zalecamy, aby zawsze określić wartość większą niż 0.

### <a name="number-of-tasks-in-helper-task-bundle"></a>Liczba zadań w pakiecie zadań wątku

Zmiana **liczby zadań w ustawieniu pakiet** zadania (czyli rozmiaru pakietu) może skrócić czas pracy. To ustawienie określa liczbę towarów planowanych razem przez pojedynczego pomocnika.

**Liczbę zadań w parametrze pakiet zadań** można określić w sekcji **Wydajność** na karcie **Ogólne** na stronie **Parametry planowania głównego** (**planowanie główne \> Ustawienia \> Parametry planowania głównego**). Najlepsza wartość tego parametru zależy od danych użytkownika. Dlatego zalecamy rozpoczęcie od wartości **1**, a następnie użycie metody prób i błędów w celu określenia najlepszej wartości konfiguracji.

Zaleca się, aby na ogół zwiększyć liczbę zadań, gdy liczba towarów jest bardzo duża (w setkach tysięcy). W przeciwnym razie należy zmniejszyć liczbę zadań. W odniesieniu do następujących konkretnych branż należy wziąć pod uwagę następujące rekomendacje:

- W przemyśle detalicznym i dystrybucji, gdzie jest wiele niezależnych towarów, należy stosować wiele pomocników, ponieważ nie ma zależności między elementami. 
- W przemyśle produkcyjnym, w którym istnieje wiele BOM i współużytkowanych podskładników, należy zmniejszyć liczbę pomocników, ponieważ zależności między towarami mogą powodować czas oczekiwania.

> [!TIP]
> W przypadku problemów z wydajnością zaleca się zmniejszenie **liczby pomocników w ustawieniu pakietu** zadań na **1**. Następnie można rozpocząć metodę prób i błędów, aby znaleźć najlepszą wartość ustawienia. Na ogół występują problemy z wydajnością, gdy jeden towar zabiera więcej czasu niż pozostałe towary. W takim przypadku można zauważyć, że dwa kolejne zadania, które mają stan **Zapotrzebowania** w planowaniu głównym, zajmują znacznie odmienny czas do uruchomienia. W skrajnych przypadkach różnica ta może wynosić nawet 30 minut. Można określić czas, przez jaki zadania mają być wykonywane, patrząc na czas trwania każdego zadania.

### <a name="use-of-cache"></a>Użycie pamięci podręcznej

Parametr **Użycie pamięci podręcznej** umożliwia dostosowanie procesu planowania głównego w celu lepszego dostosowania go do określonego zbioru danych. Można na przykład dostosować go w celu osiągnięcia następujących wyników:

- Jeśli wykonano więcej pamięci podręcznej, gromadzonych jest więcej danych w pamięci danych. Oczekuje się, że dane będą używane ponownie później. Jeśli dane znajdują się w pamięci, można zapisać niektóre żądania bazy danych. Jeśli jednak gromadzonych jest więcej danych w pamięci podręcznej, wzrasta zapotrzebowanie na pamięć.
- Jeśli gromadzone jest mniej w pamięci podręcznej, może być konieczne pobranie tych samych danych z bazy danych częściej. Ponadto serwer obiektów aplikacji (AOS) przechowuje w pamięci niewielkie dane w całym procesie.

Trudno przewidzieć, która opcja będzie lepsza, ponieważ każdy przypadek zależy nie tylko od danych, ale również do sprzętu. Na przykład, ponieważ mniejsze buforowanie powoduje dodatkowe obciążenie serwera bazy danych, nie zaleca się używania tej opcji, jeśli serwer bazy danych jest już przeciążony.

**Wykorzystanie pamięci podręcznej** można określić w sekcji **Wydajność** na karcie **Ogólne** na stronie **Parametry planowania głównego** (**planowanie główne \> Ustawienia \> Parametry planowania głównego**). Efektywność buforowania zależy w dużym stopniu od danych klientów. Jeśli na przykład buforowane dane nie są potrzebne, to pamięć jest marnowana, jeśli dane są przechowywane do końca procesu planowania. W takim przypadku, jeśli zostanie skonfigurowane mniejsze buforowanie, wydajność może się zwiększyć, ponieważ serwer AOS wymaga mniej pamięci, a zasoby serwera są zwalniane dla innych zadań.

> [!TIP]
> Ogólnie zalecamy **ustawienie parametru pamięci podręcznej** na **wartość maksimum**, ponieważ parametr jest przeznaczony do stosowania jako funkcja zwiększania wydajności. Zaleca się ustawienie parametru na wartość **minimalną**, jeśli jest wykonywana na miejscu i ma ograniczony rozmiar pamięci (około 2 \[gigabajtów\]).

### <a name="number-of-orders-in-firming-bundle"></a>Liczba zamówień w pakiecie akceptacji

**Liczba lub zamówienia w parametrze pakietu określającego pakiet** określa łączną liczbę zamówień, które będą przetwarzane w danym momencie przez poszczególne wątki/partie. Powoduje to paralelizację procesu autoakceptowania.

**Liczbę zamówień w pakiecie określającym** można określić w sekcji **Wydajność** na karcie **Ogólne** na stronie **Parametry planowania głównego** (**planowanie główne \> Ustawienia \> Parametry planowania głównego**). Paralelizacja procesu autoustalania jest oparta na zamówieniach, które muszą zostać przetworzone razem. Na przykład jeśli ten parametr ma wartość **50**, na przykład każdy wątek lub zadanie wsadowe będzie pobierać 50 zamówień w tym samym czasie i przetwarzać je razem. W celu znalezienia najlepszej wartości zalecamy użycia metody prób i błędów. Można jednak obliczać wartość początkową przy użyciu następującej formuły:

(Liczba zamówień na pakiet) = (Liczba pozycji na żądanie ÷ liczba wątków)

> [!NOTE]
> Jeśli **Liczba zamówień w parametrze pakietu określającego** ustawiona jest na **0** (zero), to nie wystąpi żadna paralelizacja procesu autoakceptowania. Cały proces zostanie uruchomiony w jednym zadaniu wsadowym i będzie miał skumulowany czas pracy. Z tego powodu czas trwania planowania głównego zostanie zwiększony. Dlatego zalecamy ustawienie tego parametru na wartość większą niż **0** (zero).

### <a name="time-fences"></a>Horyzonty czasowe

Horyzonty czasowe określają, jak daleko w przyszłości obliczenia i inne zapotrzebowania muszą być obliczane przez planowanie główne. Im większy horyzont czasowy, tym dłużej będzie wykonywane planowanie główne. W związku z tym należy określić horyzonty czasowe zgodnie z wymaganiami biznesowymi użytkownika. Aby uzyskać więcej informacji o horyzontach czasowych, zapoznaj się z tematem [Konfigurowanie planowania głównego](master-planning-setup.md).

### <a name="actions"></a>Akcje

Wśród horyzontów czasowych można również znaleźć parametr **Komunikatu akcji**. Obliczanie komunikatów akcji powoduje dłuższy czas pracy planowania głównego. Jeśli komunikaty akcji nie są regularnie analizowane i stosowane (codziennie, co tydzień itd.), należy rozważyć wyłączenie obliczeń podczas przebiegu planowania głównego Aby wyłączyć obliczanie, na stronie **Plany główne** (**Planowanie główne \> Ustawienia \> Plany \> Plany główne**) ustaw wartość w polu horyzontu czasowego **komunikatu akcji** na **0** (zero). Upewnij się również, że ustawienie **Komunikatu akcji** jest wyłączone dla wszystkich grup zapotrzebowania.

### <a name="futures"></a>Prognozy

Obliczanie prognoz powoduje dłuższy czas pracy planowania głównego. Jeśli nie są planowane specyfikacje BOM lub jeśli opóźnienia nie muszą być propagowane z podaży do popytu podczas planowania, należy rozważyć wyłączenie obliczeń prognoz podczas planowania głównego. Aby wyłączyć obliczenia, należy określić horyzont czasowy **prognozy** na **0** (zero) dla planu głównego, który jest uruchomiony. Upewnij się również, że ustawienie **Prognoz** jest wyłączone dla wszystkich grup zapotrzebowania.

## <a name="one-heavy-routine-at-a-time"></a>Pojedyncza procedura ciężka w danym czasie

Planując planowanie główne, nie należy jednocześnie planować żadnego innego zadania wsadowego. Należy pamiętać, że w tym samym czasie nie są planowane żadne inne procedury ciężkie, takie jak zamknięcie magazynu.

## <a name="review-the-session-log"></a>Przegląd dziennika sesji

System może zbierać dodatkowe informacje o zadaniach, które są uruchamiane podczas planowania głównego. Aby system gromadził te informacje, włącz ustawienie **Śledzenie czasu przetwarzania** w oknie dialogowym **Uruchamianie planowania głównego**. Zebrane informacje mogą pomóc w znalezieniu wąskich gardeł w działaniu. Jeśli na przykład **liczba zadań w parametrze pakietu** ma wartość **1**, to można zidentyfikować towar o najdłuższym czasie wykonywania. Można także porównywać czasy rozpoczęcia dla różnych wątków, które mają stan **zapotrzebowania** i porównywać czas trwania każdego zadania.

Aby przejrzeć przebieg planowania głównego systemu, należy postąpić zgodnie z jednym z tych kroków.

- W obszarze roboczym **Planowanie główne** w polu rozwijanym wybierz plan główny, a następnie na kafelku **Planowanie główne** wybierz pozycję **Historia**. Wybierz zadanie, wybierz **zapytania** w skróconej karcie, a następnie wybierz opcję **Czas trwania zadania procesowego**.
- Na stronie **plany główne** wybierz plan w lewym okienku, a następnie wybierz opcję **historia** na skróconej karcie. Wybierz zadanie, wybierz **zapytania** w skróconej karcie, a następnie wybierz opcję **Czas trwania zadania procesowego**.

Podczas przeglądania dziennika sesji należy wziąć pod uwagę następujące kwestie:

- **Aktualizacja** nie może trwać długo (zazwyczaj może trwać do 30 minut), ale obejmuje pojedynczy wątek.
- **Plan kopiowania** nie powinien trwać długo (zajmie to około jednej minuty).
- **Automatyczne akceptowanie** zazwyczaj trwa około 30 minut. Może to jednak potrwać do wielu godzin, w zależności od liczby zamówień i złożoności towarów.
- **Automatyczne akceptowanie** powinno trwać krócej niż **zapotrzebowanie**.
- **Zapotrzebowanie** powinno trwać najdłużej w stosunku do reszty.
- **Akcja** i **Przyszły komunikat** mogą trwać długo, w zależności od danych i liczby BOM.

## <a name="filtering-of-items"></a>Filtrowanie towarów

Filtry stosowane w oknie dialogowym **Uruchomienie planowania głównego** wpływają na czas trwania procesu planowania głównego. Przejdź do **Planowania głównego \> planowania głównego \> Uruchom \> Planowania głównego** lub wybierz opcję **Uruchom** w obszarze roboczym **Planowanie główne.** Aby wykluczyć elementy z uruchomienia, zaleca się filtrowanie według stanu cyklu życia towaru (nie według numerów towarów). Podczas filtrowania według stanu cyklu życia proces aktualizacji zajmie mniej czasu niż podczas filtrowania według numerów towarów.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Automatycznie filtruj według towarów z bezpośrednim popytem

Aby poprawić czas przebiegu planowania głównego, można wybrać opcję uwzględnienia tylko towarów z bezpośrednim zapotrzebowaniem. Ten filtr może być używany tylko w przypadku kompletnego przebiegu planowania głównego bez innych filtrów zastosowanych w polu **Rekordy do uwzględnienia**. Przebieg planowania głównego z filtrami zignoruje ustawienie **Automatycznie filtruj według elementów z bezpośrednim popytem**.

Pole **Automatycznie filtruj według elementów z bezpośrednim popytem** znajduje się na stronie **Parametry planowania głównego** i może być używane z ustawieniami przetwarzania wstępnego i przetwarzania końcowego.

### <a name="pre-processing"></a>Przetwarzanie wstępne
Parametr **Przetwarzanie wstępne: automatycznie filtruj według towarów z bezpośrednim popytem** zapewnia, że faza wstępnego przetwarzania planowania głównego obejmuje tylko towary, które spełniają co najmniej jeden z następujących warunków:
  - Towar ma oczekiwane przyjęcie lub wydanie, takie jak zamówienie zakupu, zamówienie sprzedaży, oferta, zlecenie przeniesienia lub zlecenie produkcyjne. 
  - Towar ma pokrycie zapasu z zapasów bezpieczeństwa (minimalne dostępne zapasy).
  - Istnieje prognozowany popyt na towar po dniu dzisiejszym.
  - Istnieje prognozowana podaż towaru po dniu dzisiejszym.
  - Towar zawiera wszystkie wiersze sprzedaży ciągłej z modułu biura obsługi jeszcze do utworzenia.

> [!NOTE]
> Towar, który ma fizycznie dostępne zapasy, nie będzie pokazywać transakcji zapotrzebowania, ponieważ nie ma popytu na towar.

### <a name="post-processing"></a>Przetwarzanie końcowe
Opcja **Przetwarzanie końcowe: automatycznie filtruj według towarów z bezpośrednim popytem** ma zastosowanie tylko wtedy, gdy w grupach zapotrzebowania ustawiono **wymaganie wersji BOM**. W przeciwnym razie nie trzeba włączać parametru. 

Przed uruchomieniem kroku zapotrzebowania następuje etap wstępnego zapotrzebowania, podczas którego elementy z zapotrzebowaniem ustawionym na **wymaganie wersji BOM** będą ponownie przetwarzane. Odbywa się to w celu zapewnienia, że towary z wymaganej wersji BOM są planowane. Towary, które są uważane za towary z popytem podczas wstępnego przetwarzania, nie mają już popytu i dlatego powinny zostać wykluczone z przebiegu planowania.

## <a name="performance-checklist-summary"></a>Podsumowanie listy kontrolnej wydajności

- **Liczba wątków** ustawiona na wartość większą niż **0** (zero).
- **Liczba zadań w pakiecie zadania pomocnika** — jest ustawiona na wartość większą niż **0** (zero). (Należy skorzystać z formuł podanych we wcześniejszej części tego tematu)
- **Użycie pamięci podręcznej** — ustawione na wartość **maksimum**, chyba że w systemie brakuje pamięci.
- **Liczba zamówień w pakiecie zadania określonego** — jest ustawiona na wartość większą niż **0** (zero). (Należy skorzystać z formuły podanej we wcześniejszej części tego tematu.)
- **Horyzonty czasowe** — dopasowuje do potrzeb biznesowych użytkownika.
- **Akcje i prognozy** — wyłącza akcje i prognozę, jeśli nie są używane.
- **Pojedyncza procedura ciężka w danym czasie** — nie uruchamia planowania głównego razem z żadną inną operacją ciężkiej procedury.
- **Przegląd dziennika sesji.**
- **Filtrowanie towarów** — użycie stanu cyklu życia do wykluczenia towarów z przebiegu planowania głównego. (Nie używaj numerów pozycji.)
