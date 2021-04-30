---
title: Przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem
description: W tym temacie opisano sposób używania szablonów pracy i dyrektyw lokalizacji do określania, jak i gdzie praca jest wykonywana w magazynie.
author: perlynne
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy, TMSLoadBuildWorkbench, WHSCatchWeightTagRegistration, WHSCatchWeightTagFullDimDiscrepancies, WHSCatchWeightTagChangeWeightDropDownDialog, WHSCatchWeightLinkWorkLineTagDropDownDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: c263fdcf7fdf2888e1c66e7e2b67d8b26729128c
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907626"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem

[!include [banner](../includes/banner.md)]

## <a name="feature-exposure"></a>Funkcja ekspozycji

Aby używać funkcji zarządzania magazynem do przetwarzania ilości efektywnej produktów, trzeba użyć klucza konfiguracji licencji do włączania tej funkcji. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**. Następnie na karcie **Klucze konfiguracji** rozwiń opcje **Handel \> Zarządzanie magazynem i transportem** i zaznacz pole wyboru dla **Ilość efektywna dla magazynu**.

> [!NOTE]
> Zarówno klucz konfiguracji licencji **Zarządzanie magazynem i transportem**, jak i klucz konfiguracji licencji **Dystrybucja procesów \>ilości efektywnej** muszą być również włączone. Aby skonfigurować klucze konfiguracji dla ilości efektywnej, należy również włączyć tę funkcję za pomocą obszaru roboczego **zarządzanie funkcją**. Główną funkcją, która musi być włączona, jest **Przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem**. Dwie powiązane, ale opcjonalne funkcje, które można włączyć, to **zmiany stanu zapasów dla produktów w ilości efektywnej** i **użyj istniejących znaczników ilości efektywnej podczas zgłaszania zleceń produkcyjnych jako gotowych**.

Po włączeniu klucza konfiguracji licencji, gdy tworzysz zwolniony produkt, możesz wybierać **Ilości efektywną**. Można także skojarzyć zwolniony produkt z grupą wymiarów magazynowania, dla której wybrany jest parametr **Użyj procesów zarządzania magazynami**.

Przed użyciem tego produktu w module Zarządzanie magazynem należy wprowadzić pewne podstawowe ustawienia specyficzne dla produktu dla ilości efektywnej:

- Zdefiniuj konwersji nominalnej wagi między jednostką ilości efektywnej (opakowanie) a jednostką magazynową (kilogram \[kg\]) w ramach definicji konwersji jednostki.
- Zdefiniuj minimalne i maksymalne tolerancje wagi w ramach konfiguracji jednostki ilości efektywnej.
- Skonfiguruj grupę sekwencji jednostki, gdzie jednostka ilości efektywnej jest definiowana jako najniższa jednostka magazynowa (SKU).
- Skonfiguruj zasady obsługi towarów w ilości efektywnej.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie i obsługa towarów w ilości efektywnej](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Korekta transakcji

Ponieważ waga zapasów przychodzących do magazynu może różnić się od wagi w chwili wydania zapasów z magazynu, przetwarzania towarów w ilości efektywnej musi korygować zapasy.

> [!NOTE]
> Działanie urządzenia przenośnego spowoduje wyzwolenie korekt transakcji tylko wtedy, gdy metoda odchylenia wychodzącej wagi towaru w zasadach obsługi towarów w ilości efektywnej to **Zezwalaj na odchylenie masy**.

### <a name="example-1"></a>Przykład 1

Podczas procesu produkcyjnego **Zgłoś jako gotowe** waga wejściowa w numerze identyfikacyjnym ośmiu opakowań produktu w ilości efektywnej jest rejestrowana jako 80,1 kg. Numer identyfikacyjny jest następnie przechowywany w obszarze wyrobów gotowych, a podczas w okresie przechowywania część wagi ulatnia się.

Później w ramach procesu odbioru zamówienia sprzedaży waga tego samego numeru identyfikacyjnego jest mierzona i wynosi 79,8 kg. Dlatego w systemie istnieje różnica wagi jako część zestawu wymiarów fizycznych.

W takim przypadku system automatycznie koryguje różnicę, księgując transakcję dla brakujących 0,3 kg.

### <a name="example-2"></a>Przykład 2

W definicji produkt toleruje minimalną wagę 8 kg i maksymalną wagę 12 kg dla jednostki efektywnej **Opakowanie**.

Są dwa opakowania produktu i mają zarejestrowaną wagę 16 kilogramów. Jeśli pracownik magazynu odbierze i zważy jedno z opakowań i zarejestrowana waga wynosi 9 kg, drugie opakowanie będzie ważyć 7 kg. Jednak ponieważ 7 kg jest poniżej wagi minimalnej, system wykona automatyczną korektę, aby zwiększyć wagę dostępnych zapasów o 1 kg.

Aby skonfigurować konta, na których są księgowane te zmiany, przejdź do **Zarządzanie kosztami \> Ustawienia zasad integracji księgi \> Księgowanie**. Następnie na karcie **Zapasy** zdefiniuj następujące konta:

- Konto strat ilości efektywnej
- Konto zysków dla ilości efektywnej

## <a name="catch-weight-item-handling-policy"></a>Zasada obsługi towarów w ilości efektywnej

Zasady dotyczące obsługi towarów w ilości efektywnej obsługi definiują dwa główne przebiegi procesu zarządzania magazynem dla towarów: czas oraz sposób rejestrowania wagi towarów.

Można określić, kiedy waga jest rejestrowane dla sprzedaży i przetwarzania zamówień przeniesienia. Waga może być rejestrowana podczas jednego z następujących procesów:

- **Pobrania** — wagi są rejestrowane podczas pierwszego pobrania zlecenia produkcyjnego.
- **Pakowanie** — wagi są rejestrowane podczas ręcznego pakowania. (Należy wysłać towary do stanowiska pakowania).

Jeśli rzeczywista waga jest rejestrowana w punkcie pakowania w ramach procesów pakowania do kontenerów, pracownicy magazynu nie otrzymują monitu o zarejestrowanie wagi podczas odbioru. Zamiast tego średnia waga inwentaryzacji jest użyta jako waga pobranych zapasów, które są kierowane do punktu pakowania. Pojęcie to dotyczy także towarów w ilości efektywnej, które są śledzone przez znaczniki. W przypadku elementów śledzonych znacznikami parametry te definiują czas przechwytywania znacznika. Znacznik można przechwycić w czasie pobierania, korzystając z urządzenia przenośnego lub podczas ręcznego pakowania.

> [!NOTE]
> Ponieważ opcja **Opakowanie** powoduje aktualizację zapasów przy użyciu średniej pobranej wagi, może to wywołać niezgodność, która może spowodować korektę zysków/strat w ilości efektywnej i/lub różnicę między ilością dostępnych zapasów a wagą znaczników ilości efektywnej.

Dla wewnętrznych procesów zarządzania magazynem, takich jak liczenie i korekty, można zdefiniować, czy waga ma być rejestrowana. Jeśli nie jest rejestrowana, będzie używana waga nominalna. Inne opcje umożliwiają przechwytywanie wagi na jednostkę ilości efektywnej i za ilość zliczaną.

Można również zdefiniować sposób rejestrowania wagi. W jednym z dwóch głównych przepływów znaczniki ilości efektywnej są śledzone i służą do rejestrowania wagi. W drugim przepływie znaczniki wagi efektywnej nie są śledzone.

- **Tak** — towar używa znaczników ilości efektywnej. Każda liczba znacznika reprezentuje jednostkę ilości efektywnej (opakowanie), a w znaczniku uwzględnione są również waga i inne informacje. Dla procesów wychodzących używana jest waga skojarzona z tym znacznikiem.
- **Nie** — towar nie używa znaczników ilości efektywnej. Procesy przychodzące i wychodzące ważenia są oparte na rzeczywistej wadze zarejestrowanej w każdym procesie.

Proces śledzenia znaczników ilości efektywnej może być używany dla towarów, które nie zmienią wagi w okresie przechowywania. Waga zostanie zarejestrowana tylko podczas procesu przyjęcia do magazynu. W trakcie wydawania znaczniki ilości efektywnej będą tylko skanowane i wagi skojarzone z tymi znacznikami będą używane do przetwarzania transakcji na wyjściu.

Innym ważnym parametrem związanym z przetwarzaniem znaczników w ilości efektywnej jest **Metoda śledzenia wymiaru znaczników ilości efektywnej**. Tagi mogą być częściowo śledzone lub w pełni śledzone. Jeśli znacznik jest częściowo śledzony, śledzi wymiary produktów, wymiary śledzenia oraz stan zapasów. Jeśli znacznik jest całkowicie śledzony, śledzi wymiary produktów, wymiary śledzenia oraz **wszystkie** wymiary produktu.

Ponadto, gdy towar jest śledzony przez znacznik, istnieje parametr **Metody przechwytywania znacznika wychodzącego**. Ten parametr można skonfigurować w taki sposób, aby zawsze wyświetlany był monit o znacznik dotyczący transakcji wychodzących z urządzenia przenośnego. Można również ustawić parametr w taki sposób, aby etykiety były wyświetlane tylko wtedy, gdy są wymagane. Na przykład w magazynie na danym numerze identyfikacyjnym znajduje się pięć znaczników ilości efektywnej, co oznacza, że użytkownik chce pobrać wszystkie pięć znaczników z numeru identyfikacyjnego. W takim przypadku, jeśli parametr **Metody przechwytywania znacznika wychodzącego** ma ustawioną opcję **Monituj o znacznik, w razie potrzeby**, automatycznie pobieranych jest pięć znaczników. Nie ma konieczności skanowania każdego znacznika. Jeśli parametr ma wartość **Zawsze monituj o znacznik**, należy przeskanować każdy znacznik, nawet jeśli zostaną pobrane wszystkie pięć znaczników.

> [!NOTE]
> Z reguły tagi są przechwytywane i aktualizowane tylko z elementów menu urządzeń przenośnych. Istnieje jednak kilka scenariuszy, w których tagi są przechwytywane w innym miejscu (np. z ręcznej stacji pakowania). Jednak na ogół elementy menu urządzenia przenośnego powinny być używane dla wszystkich działań magazynowych, jeśli są używane znaczniki.

### <a name="how-to-capture-catch-weight"></a>Jak rejestrować ilość efektywną

**Ilość używane jest śledzenie ilości efektywnej**, znacznik musi zawsze zostać utworzony do każdej przyjmowanej jednostki ilości efektywnej i każdy znacznik musi być zawsze skojarzony z wagą.

Na przykład jednostką ilości efektywnej jest **Opakowanie** i odbierasz jedną paletę ośmiu opakowań. W takim przypadku osiem unikatowych znaczników ilości efektywnej musi zostać utworzonych i waga musi być skojarzona z każdym z tych znaczników. W zależności od znacznika ilości efektywnej przyjmowanej do magazynu można zarejestrować albo wagę wszystkich ośmiu opakowań, a następnie przypisać do każdego z nich wagę uśrednioną, lub można zważyć indywidualnie każde opakowanie.
W przypadku **użyj znaczników ilości efektywnej podczas zgłaszania funkcji zleceń produkcyjnych jako gotowych** z włączonym elementem menu urządzenia przenośnego zapasy są aktualizowane na podstawie istniejących informacji o znacznikach ilości efektywnej. W rezultacie aplikacja Warehouse Management nie monituje o przechwytywanie danych znaczników ilości efektywnej jako części raportu produkcji jako zakończonej operacji.

**Jeśli śledzenie znaczników ilości efektywnej nie jest używane**, można zarejestrować wagę dla każdego wymiaru (na przykład, dla każdego numeru identyfikacyjnego i wymiaru śledzenia). Alternatywnie waga może być rejestrowana na podstawie poziomu zagregowanego, np. pięciu numerów identyfikacyjnych (palet).

W przypadku metod przechwytywania wagi załadunkowej opcja **Na jednostkę ilości efektywnej** umożliwia określenie, że ważenie powinno być wykonane dla każdej jednostki ilości efektywnej (na przykład w przypadku pola). Opcja **Na jednostkę pobierania** umożliwia określenie, że waga powinna zostać przechwycona na podstawie ilości, która zostanie pobrana (na przykład trzy pola). Należy zwrócić uwagę, że dla procesu odbioru z linii produkcyjnej i wewnętrznego przeniesienia, średnia waga będzie używana, jeśli używana jest opcja **Nie zarejestrowano**.

Metody przechwytywania wielu wag są zdefiniowane w zasadach obsługi pozycji w ilości efektywnej. Każdy parametr metody przechwytywania wagi jest używany w różnych transakcjach. Poniższa tabela zawiera podsumowanie parametrów używanych przez te transakcje.

| Metoda                                     | Transakcja                                |
|--------------------------------------------|--------------------------------------------|
| Metoda rejestrowania masy dostawy wychodzącej           | Pobieranie sprzedaży, przenoszenie pobrania            |
| Metoda rejestrowania masy pobrania do produkcji | Pobieranie produkcji, zużycie produkcji |
| Metoda rejestrowania masy przenoszonych towarów           | Transakcje                                   |
| Kiedy rejestrować korektę masy       | Korekty, Zliczenia                      |
| Metoda rejestrowania obliczonej masy           | Zliczanie                                   |
| Metoda rejestrowania masy przesunięcia magazynowego | Przeniesienie magazynu                         |

Aby uniemożliwić procesom pobrania zarządzania magazynem przechwytywanie wag powodujące dopasowania zysku/straty ilości efektywnej, można użyć metody zarządzania odchyleniem masy dostawy wychodzącej. Metoda odchyleń wagi wychodzącej jest stosowana podczas następujących procesów urządzeń przenośnych: pobranie sprzedaży, przeniesienie pobrania, pobranie do produkcji, przesunięcia, Inwentaryzacja i przeniesienia magazynowe. Można skorzystać z opcji **Ogranicz odchylenie masy**, jeśli waga towaru w ilości efektywnej nie jest zmieniana w czasie przechowywania magazynu, a korekty zysku/straty w ilości efektywnej nie są wymagane. Można skorzystać z opcji **Zezwalaj na odchylenie masy**, jeśli waga może ulegać wahaniom, a korekty dotyczące zysku/straty są wymagane w przypadku rejestrowania wahań wagi.

## <a name="unsupported-scenarios"></a>Nieobsługiwane scenariusze

Nie wszystkie przepływy prac obsługują przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem. Obecnie obowiązują następujące ograniczenia. Dotyczą one wszystkich towarów w ilości efektywnej, niezależnie od tego, czy są oznakowane.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Konfigurowanie produktów ilości efektywnej dla procesów zarządzania magazynem

- Tylko przetwarzanie formuły jest obsługiwane dla produktów z ilością efektywną (nie BOM).
- Produkty w ilości efektywnej nie mogą być skojarzone z grupą śledzenia wymiarów za pomocą wymiaru Właściciel.
- Produkty w ilości efektywnej nie mogą być stosowane jako usługi.
- Produkty w ilości efektywnej mogą być używane jako „produkty magazynowane” tylko w ramach grupy modeli towaru.
- Produkty w ilości efektywnej nie mogą być używane razem z funkcją śledzenia „Aktywne w procesie sprzedaży.”
- Produkty w ilości efektywnej nie mogą być używane razem z funkcją rejestrowania numerów seryjnych. Z tego względu produkty nie mogą być przenoszone z „pustego” do numeru seryjnego w ramach procesu odbioru/pakowania.
- Produkty w ilości efektywnej nie mogą być używane razem z funkcją rejestrowania numerów seryjnych przed konsumpcją.
- Produkty w ilości efektywnej, które obsługują wariant, nie mogą być używane razem z funkcją konwersji jednostek miary wariantu.
- Produkty w ilości efektywnej nie mogą być oznaczone jako „zestaw produktów” handlowych.
- Produkty w ilości efektywnej mogą być używane tylko z grupą sekwencji jednostek, która ma jednostki obsługi ilości efektywnej, i w której jednostka ilości efektywnej ma najmniejszy numer sekwencyjny.
- Dla produktów w ilości efektywnej jednostka magazynowa może być konwertowana na jednostkę ilości efektywnej tylko wtedy, gdy konwersji generuje ilość nominalną większą niż 1.
- Konfiguracja kodów kreskowych dla produktów w ilości efektywnej nie obsługuje konfiguracji ilości zmiennej.

### <a name="order-processing"></a>Przetwarzanie zamówień

- Tworzenie wcześniejszego powiadomienia o wysyłce (struktury WPW/pakowania) nie obsługuje informacji o wadze.
- Ilość zamówienia musi być zachowana na podstawie jednostki ilości efektywnej.

### <a name="inbound-warehouse-processing"></a>Przetwarzanie przyjęć do magazynu

- Przyjęcie numeru identyfikacyjnego wymaga przypisania wagi podczas rejestracji, ponieważ informacje o wadze nie są obsługiwane w ramach wcześniejszego powiadomienia o wysyłce. Jeśli procesy znacznika ilości efektywnej są używane, numer znacznika musi być ręcznie przypisany wg jednostki ilości efektywnej.
- Praca kontroli jakości przychodzącej nie jest obsługiwana w przypadku produktów w ilości efektywnej. Jeśli ta konfiguracja jest skonfigurowana, praca sprawdzania jakości zostanie pominięta.

### <a name="inventory-and-warehouse-operations"></a>Operacje magazynowe i na zapasach

- Ręczne tworzenie zleceń kwarantanny nie jest obsługiwana dla produktów w ilości efektywnej.
- Ręczne przesuwanie zapasów powiązanych z otwartą pracę nie jest obsługiwane dla produktów w ilości efektywnej.
- Ładowanie numeru identyfikacyjnego do zainicjowania zapasów w magazynie nie jest obsługiwane dla produktów w ilości efektywnej.
- Procesy równoważenia partii nie są obsługiwane dla produktów w ilości efektywnej.
- Obsługa ujemnej inwentaryzacji nie jest obsługiwane dla produktów w ilości efektywnej.
- Oznaczanie zapasów nie mogą być używane dla produktów w ilości efektywnej.

### <a name="outbound-warehouse-processing"></a>Przetwarzanie wydań z magazynu

- Funkcja pobierania dla grupy nie jest obsługiwana dla produktów w ilości efektywnej.
- Przetwarzanie odbiorów i pakowania w magazynie nie jest obsługiwane dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej praca zdefiniowana w szablonie pracy nie może być uruchamiana automatycznie.
- Dla produktów w ilości efektywnej system nie wspiera ręcznego przetwarzania w punkcie pobrania, gdzie praca pobierania zapakowanych kontenerów jest tworzona po zamknięciu kontenerów, nie jest obsługiwane.
- Funkcja skanowania pojedynczych sztuk towaru nie jest obsługiwana dla produktów w ilości efektywnej.

### <a name="production-processing"></a>Przetwarzanie produkcji

- Dla produktów w ilości efektywnej tylko zamówienia partii dla produktów formuły są obsługiwane.
- Funkcja Kanban nie jest obsługiwana dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej numery seryjne nie mogą być rejestrowane przed skonsumowaniem.
- Funkcja cofania numerów identyfikacyjnych z produkcji nie jest obsługiwana dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej zgłaszanie jako wyrobów gotowych nie może być rejestrowane wg numeru seryjnego.

### <a name="transportation-management-processing"></a>Przetwarzanie zarządzania transportem

- Przetwarzanie na pulpicie kompilowania ładunku nie jest obsługiwane dla produktów w ilości efektywnej.
- Wiersze wniosku o transport nie są obsługiwane dla produktów w ilości efektywnej.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Inne ograniczenia i zachowania dla przetwarzania produktów w ilości efektywnej w kontekście zarządzania magazynem

- Podczas procesów pobierania, gdy użytkownik nie otrzymuje monitu o określenie wymiarów śledzenia, przypisanie wagi odbywa się a podstawie średniej wagi. To zachowanie występuje, kiedy np. kombinacja wymiarów śledzenia jest używana w tej samej lokalizacji i po wykonaniu odbioru przez użytkownika w lokalizacji pozostaje tylko jedna wartość wymiaru śledzenia.
- Jeśli zapasy są rezerwowane dla produktu w ilości efektywnej skonfigurowanego dla procesów zarządzania magazynem, rezerwacja odbywa się na podstawie zdefiniowanej wagi minimalnej, nawet jeśli ta ilość jest ostatnią obsługiwaną ilością stanu zapasów. To zachowanie różni się od zachowania dla towarów, które nie są skonfigurowane dla procesów zarządzania magazynem. Istnieje jeden wyjątek między tymi ograniczeniami. W przypadku pobierania produkcji, gdy jest pobierana Ostatnia obsługiwana ilość towaru w ilości efektywnej, która jest kontrolowana numerem seryjnym, używana jest rzeczywista waga.
- Nie należy używać rzeczywistej wagi w ramach obliczeń zdolności produkcyjnych (progów grupy czynności, maksymalnej liczby podziałów pracy, maksymalnej liczby kontenerów, możliwości obciążenia pracą lokalizacji itd.) Zamiast tego procesy opierają się na wadze bezpośredniej obsługi towarów zdefiniowanej dla produktu.
- Ogólnie funkcja Commerce nie jest obsługiwana dla produktów w ilości efektywnej.
- W przypadku produktów w ilości efektywnej stanu zapasów nie można zaktualizować z pola **Zmiana stanu magazynu**.

### <a name="catch-weight-tags"></a>Znaczniki ilości efektywnej

Znacznik ilości efektywnej można utworzyć za pomocą procesu aplikacji Warehouse Management, ręcznie za pomocą formularza, **Warehouse management > Zapytania i raporty > Metoda śledzenia wymiaru znaczników ilości efektywnej** albo stworzony za pomocą procesu jednostki danych. Jeśli znacznik ilości efektywnej jest skojarzony z wierszem dokumentu źródłowego przychodzącego, takim jak wiersz zamówienia zakupu, znacznik zostanie zarejestrowany. Jeśli wiersz jest używany do przetwarzania wychodzącego, znacznik zostanie zaktualizowany jako wysłany. Wszystkie historyczne zdarzenia metody śledzenia wymiaru znaczników ilości efektywnej można wyświetlić za pomocą opcji **Rejestracja wymiaru znaczników ilości efektywnej** na stronie **Metoda śledzenia wymiaru znaczników ilości efektywnej**.

Za pomocą opcji **Zmień znacznik ilości efektywnej** można ręcznie zaktualizować wartość ilości dla znacznika ilości efektywnej. Należy zauważyć, że ilość dostępnych zapasów nie zostanie skorygowana w ramach tego ręcznego procesu, ale można łatwo użyć strony **Rozbieżności dostępnych zapasów dla towarów ze znacznikami ilości efektywnej** w celu wyszukiwania wszelkich rozbieżności między aktualnie aktywnymi znacznikami ilości efektywnej a bieżącym stanem zapasów.

Inne opcje ręczne to **Rejestrowanie znaczników** w wierszu dokumentu źródłowego i **Rejestrowanie pracy** w ramach istniejącej pracy magazynowej.

Oprócz ograniczeń, które obecnie dotyczą produktów w ilości efektywnej, oznakowane produkty w ilości efektywnej mają inne ograniczenia, które obecnie obowiązują.

- Wszystkie ręczne aktualizacje zapasów (czyli aktualizacje, które nie zostały wykonane przy użyciu urządzenia przenośnego) muszą zawierać odpowiednie aktualizacje ręczne skojarzone ze skojarzonymi znacznikami ilości efektywnej, ponieważ te aktualizacje nie są wykonywane automatycznie. Na przykład ręczne arkusze korekty spowodują zaktualizowanie zapasów, ale nie skojarzonych tagów znaczników ilości efektywnej.
- Należy ręcznie zaktualizować znaczniki ilości efektywnej, aby odzwierciedlić zmiany pracy uzupełniania zapasów. Dzieje się tak dlatego, że system nie może przechwytywać wag podczas przetwarzania pracy uzupełniania i dlatego rejestruje średnią wagę.
- Przyjęcie mieszanych numerów identyfikacyjnych nie jest obsługiwane dla oznakowanych towarów z ilości efektywnej.
- Przetwarzanie przyjęcia zamówienia zwrotu sprzedaży może zapisywać znaczniki ilości efektywnej. Jednak proces nie sprawdza, czy zwrócony znacznik jest tym samym znacznikiem, który został pierwotnie wysłany dla zamówienia sprzedaży.
- Element menu urządzenia przenośnego z kodem **Rejestrowanie zużycia materiałów** nie obsługuje obecnie rejestrowania znaczników ilości efektywnej.
- Chociaż procesy zliczania są obsługiwane dla oznakowanych pozycji w ilości efektywnej, są one ograniczone. Można na przykład użyć opcji urządzenia przenośnego do zliczania oznakowanych pozycji w postaci ilości efektywnej, a także użyć średniej wagi. Jednak znaczniki ilości efektywnej nie są automatycznie aktualizowane przez transakcję zliczania. Po wykonaniu transakcji zliczania znaczniki ilości efektywnej muszą zostać ręcznie zaktualizowane, aby odzwierciedlały stan zapasów. Jeśli towary, których pierwotnie nie było w danej lokalizacji, są zliczane do tej lokalizacji, używana jest waga nominalna.
- Konsolidacja numeru identyfikacyjnego nie obsługuje obecnie otagowanych pozycji w ilości efektywnej.
- Funkcja wycofywania pracy nie jest obsługiwana w przypadku towarów w ilości efektywnej, które są śledzone w postaci numeru znacznika.

> [!NOTE]
> Powyższe informacje o znacznikach ilości efektywnej są prawidłowe tylko wtedy, gdy produkt w ilości efektywnej ma metodę śledzenia wymiarów znaczników ilości efektywnej, która jest w pełni śledzona (to znaczy, jeśli parametr **Metoda śledzenia wymiaru znaczników ilości efektywnej** w zasadzie obsługi towarów w ilości efektywnej jest ustawiany na **Wymiary produktu, wymiary śledzenia i wszystkie wymiary przechowywania**). Jeśli towar w ilości efektywnej jest tylko częściowo śledzony znacznikami (to znaczy, jeśli parametr **Metoda śledzenia wymiaru znaczników ilości efektywnej** w zasadzie obsługi towarów w ilości efektywnej jest ustawiany na **Wymiary produktu, wymiary śledzenia i stan zapasów**), obowiązują dodatkowe ograniczenia. Ponieważ w tym przypadku widoczność jest tracona między znacznikiem i zapasami, niektóre dodatkowe scenariusze nie są obsługiwane.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]