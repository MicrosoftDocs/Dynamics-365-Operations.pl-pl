---
title: Przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem
description: W tym temacie opisano sposób używania szablonów pracy i dyrektyw lokalizacji do określania, jak i gdzie praca jest wykonywana w magazynie.
author: perlynne
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 6e295456838ca0195a472518b5979dfdc7819f74
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2019
ms.locfileid: "1617980"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/pivate-preview-banner.md)]


## <a name="feature-exposure"></a>Funkcja ekspozycji

Aby używać funkcji zarządzania magazynem do przetwarzania ilości efektywnej produktów, trzeba użyć klucza konfiguracji licencji do włączania tej funkcji. (Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**. Następnie na karcie **Klucze konfiguracji** rozwiń opcje **Handel \> Zarządzanie magazynem i transportem** i zaznacz pole wyboru dla **Ilość efektywna dla magazynu**).

> [!NOTE]
> Zarówno klucz konfiguracji licencji **Zarządzanie magazynem i transportem**, jak i klucz konfiguracji licencji **Dystrybucja procesów \>ilości efektywnej** muszą być również włączone.

Po włączeniu klucza konfiguracji licencji, gdy tworzysz zwolniony produkt, możesz wybierać **Ilości efektywną**. Można także skojarzyć zwolniony produkt z grupą wymiarów magazynowania, dla której wybrany jest parametr **Użyj procesów zarządzania magazynami**.

Przed użyciem tego produktu w module Zarządzanie magazynem należy wprowadzić pewne podstawowe ustawienia specyficzne dla produktu dla ilości efektywnej:

- Zdefiniuj konwersji nominalnej wagi między jednostką ilości efektywnej (opakowanie) a jednostką magazynową (kilogram \[kg\]) w ramach definicji konwersji jednostki.
- Zdefiniuj minimalne i maksymalne tolerancje wagi w ramach konfiguracji jednostki ilości efektywnej.
- Skonfiguruj grupę sekwencji jednostki, gdzie jednostka ilości efektywnej jest definiowana jako najniższa jednostka magazynowa (SKU).
- Skonfiguruj zasady obsługi towarów w ilości efektywnej.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie i obsługa towarów w ilości efektywnej](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Korekta transakcji

Ponieważ waga zapasów przychodzących do magazynu może różnić się od wagi w chwili wydania zapasów z magazynu, przetwarzania towarów w ilości efektywnej musi korygować zapasy.

**Przykład 1**

Podczas procesu produkcyjnego **Zgłoś jako gotowe** waga wejściowa w numerze identyfikacyjnym ośmiu opakowań produktu w ilości efektywnej jest rejestrowana jako 80,1 kg. Numer identyfikacyjny jest następnie przechowywany w obszarze wyrobów gotowych, a podczas w okresie przechowywania część wagi ulatnia się.

Później w ramach procesu odbioru zamówienia sprzedaży waga tego samego numeru identyfikacyjnego jest mierzona i wynosi 79,8 kg. Dlatego w systemie istnieje różnica wagi jako część zestawu wymiarów fizycznych.

W takim przypadku system automatycznie koryguje różnicę, księgując transakcję dla brakujących 0,3 kg.

**Przykład 2**

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

Jeśli rzeczywista waga jest rejestrowana w punkcie pakowania w ramach procesów pakowania do kontenerów, pracownicy magazynu nie otrzymają monitu o zarejestrowanie wagi podczas odbioru. Zamiast tego średnia waga inwentaryzacji zostanie użyta jako waga pobranych zapasów, które są kierowane do punktu pakowania.

Dla wewnętrznych procesów zarządzania magazynem, takich jak liczenie i korekty, można zdefiniować, czy waga ma być rejestrowana czy nie. Jeśli nie jest rejestrowana, będzie używana waga nominalna.

Można również zdefiniować sposób rejestrowania wagi. W jednym z dwóch głównych przepływów znaczniki ilości efektywnej są śledzone i służą do rejestrowania wagi. W drugim przepływie znaczniki wagi efektywnej nie są śledzone.

- **Tak** — towar używa znaczników ilości efektywnej. Każda liczba znacznika reprezentuje jednostkę ilości efektywnej (opakowanie), a w znaczniku uwzględnione są również waga i inne informacje. Dla procesów wychodzących używana jest waga skojarzona z tym znacznikiem.
- **Nie** — towar nie używa znaczników ilości efektywnej. Procesy przychodzące i wychodzące ważenia są oparte na rzeczywistej wadze zarejestrowanej w każdym procesie.

Proces śledzenia znaczników ilości efektywnej może być używany dla towarów, które nie zmienią wagi w okresie przechowywania. Waga zostanie zarejestrowana tylko podczas procesu przyjęcia do magazynu. W trakcie wydawania znaczniki ilości efektywnej będą tylko skanowane i wagi skojarzone z tymi znacznikami będą używane do przetwarzania transakcji na wyjściu.

### <a name="how-to-capture-catch-weight"></a>Jak rejestrować ilość efektywną

Ilość używane jest śledzenie ilości efektywnej, znacznik musi zawsze zostać utworzony do każdej przyjmowanej jednostki ilości efektywnej i każdy znacznik musi być zawsze skojarzony z wagą.

Na przykład jednostką ilości efektywnej jest **Opakowanie** i odbierasz jedną paletę ośmiu opakowań. W takim przypadku osiem unikatowych znaczników ilości efektywnej musi zostać utworzonych i waga musi być skojarzona z każdym z tych znaczników. W zależności od znacznika ilości efektywnej przyjmowanej do magazynu można zarejestrować albo wagę wszystkich ośmiu opakowań, a następnie przypisać do każdego z nich wagę uśrednioną, lub można zważyć indywidualnie każde opakowanie.

Jeśli śledzenie znaczników ilości efektywnej nie jest używane, można zarejestrować wagę dla każdego wymiaru (na przykład, dla każdego numeru identyfikacyjnego i wymiaru śledzenia). Alternatywnie waga może być rejestrowana na podstawie poziomu zagregowanego, np. pięciu numerów identyfikacyjnych (palet).

Dla metod rejestrowania wagi wychodzącej można określić, czy ważenia jest wykonywane dla każdej jednostki ilości efektywnej (czyli wg opakowania) czy też waga jest rejestrowana na podstawie odebranej ilości (np. trzy opakowania). Należy zwrócić uwagę, że dla procesu odbioru z linii produkcyjnej i wewnętrznego przeniesienia, średnia waga będzie używana, jeśli używana jest opcja **Nie zarejestrowano**.

Aby uniemożliwić procesom pobrania zarządzania magazynem przechwytywanie wag powodujące dopasowania zysku/straty ilości efektywnej, można użyć metody zarządzania odchyleniem masy dostawy wychodzącej.

## <a name="supported-scenarios"></a>Obsługiwane scenariusze

Nie wszystkie przepływy prac obsługują przetwarzanie ilości efektywnej produktu przy użyciu funkcji zarządzania magazynem. Obecnie obowiązują następujące ograniczenia.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Konfigurowanie produktów ilości efektywnej dla procesów zarządzania magazynem

- Dla produktów w ilości efektywnej nie można zmienić grupy wymiarów magazynowania dla towarów (tak aby można było używać dla nich procesów zarządzania magazynem).
- Tylko przetwarzanie formuły jest obsługiwane dla produktów z ilością efektywną (nie BOM).
- Produkty w ilości efektywnej nie mogą być skojarzone z grupą śledzenia wymiarów za pomocą wymiaru Właściciel.
- Produkty w ilości efektywnej nie mogą być stosowane jako usługi.
- Produkty w ilości efektywnej mogą być używane jako „produkty magazynowane” tylko w ramach grupy modeli towaru.
- Produkty w ilości efektywnej nie mogą być używane razem z funkcją śledzenia „Aktywne w procesie sprzedaży.”
- Produkty w ilości efektywnej nie mogą być używane razem z funkcją rejestrowania numerów seryjnych. Z tego względu produkty nie mogą być przenoszone z „pustego” do numeru seryjnego w ramach procesu odbioru/pakowania.
- Produkty w ilości efektywnej nie mogą być używane razem z funkcją rejestrowania numerów seryjnych przed konsumpcją.
- Produkty w ilości efektywnej, które obsługują wariant, nie mogą być używane razem z funkcją konwersji jednostek miary wariantu.
- Produkty w ilości efektywnej nie mogą być oznaczone jako „zestaw produktów” w sprzedaży detalicznej.
- Produkty w ilości efektywnej mogą być używane tylko z grupą sekwencji jednostek, która ma jednostki obsługi ilości efektywnej, i w której jednostka ilości efektywnej ma najmniejszy numer sekwencyjny.
- Dla produktów w ilości efektywnej jednostka magazynowa może być konwertowana na jednostkę ilości efektywnej tylko wtedy, gdy konwersji generuje ilość nominalną większą niż 1.
- Konfiguracja kodów kreskowych dla produktów w ilości efektywnej nie obsługuje konfiguracji ilości zmiennej.
 
### <a name="order-processing"></a>Przetwarzanie zamówień

- Tworzenie wcześniejszego powiadomienia o wysyłce (struktury WPW/pakowania) nie obsługuje informacji o wadze.
- Ilość zamówienia musi być zachowana na podstawie jednostki ilości efektywnej.
 
### <a name="inbound-warehouse-processing"></a>Przetwarzanie przyjęć do magazynu

- Przyjęcie numeru identyfikacyjnego wymaga przypisania wagi podczas rejestracji, ponieważ informacje o wadze nie są obsługiwane w ramach wcześniejszego powiadomienia o wysyłce. Jeśli procesy znacznika ilości efektywnej są używane, numer znacznika musi być ręcznie przypisany wg jednostki ilości efektywnej.
 
### <a name="inventory-and-warehouse-operations"></a>Operacje magazynowe i na zapasach

- Ręczne tworzenie zleceń kwarantanny nie jest obsługiwana dla produktów w ilości efektywnej.
- Ręczne przesuwanie zapasów powiązanych z pracę nie jest obsługiwane dla produktów w ilości efektywnej.
- Konsolidacja numerów identyfikacyjnych nie jest obsługiwane dla produktów w ilości efektywnej.
- Ładowanie numeru identyfikacyjnego do zainicjowania zapasów w magazynie nie jest obsługiwane dla produktów w ilości efektywnej.
- Procesy równoważenia partii nie są obsługiwane dla produktów w ilości efektywnej.
- Obsługa ujemnej inwentaryzacji nie jest obsługiwane dla produktów w ilości efektywnej.
- Oznaczanie zapasów nie mogą być używane dla produktów w ilości efektywnej.
 
### <a name="outbound-warehouse-processing"></a>Przetwarzanie wydań z magazynu

- Funkcja pobierania dla grupy nie jest obsługiwana dla produktów w ilości efektywnej.
- Przetwarzanie odbiorów i pakowania w magazynie nie jest obsługiwane dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej praca zdefiniowana w szablonie pracy może być uruchamiana automatycznie.
- Funkcja cofania pracy nie jest obsługiwana dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej ręczne przetwarzanie w punkcie odbierania, gdzie praca jest tworzona po zamknięciu kontenerów, nie jest obsługiwane.
- Funkcja skanowania pojedynczych sztuk towaru nie jest obsługiwana dla produktów w ilości efektywnej.
 
### <a name="production-processing"></a>Przetwarzanie produkcji

- Dla produktów w ilości efektywnej tylko zamówienia partii dla produktów formuły są obsługiwane.
- Funkcja Kanban nie jest obsługiwana dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej numery seryjne nie mogą być rejestrowane przed skonsumowaniem.
- Funkcja cofania numerów identyfikacyjnych nie jest obsługiwana dla produktów w ilości efektywnej.
- Dla produktów w ilości efektywnej zgłaszanie jako wyrobów gotowych nie może być rejestrowane wg numeru seryjnego.

### <a name="transportation-management-processing"></a>Przetwarzanie zarządzania transportem

- Przetwarzanie na pulpicie kompilowania ładunku nie jest obsługiwane dla produktów w ilości efektywnej.
- Wiersze wniosku o transport nie są obsługiwane dla produktów w ilości efektywnej.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Inne ograniczenia i zachowania dla przetwarzania produktów w ilości efektywnej w kontekście zarządzania magazynem

- Podczas procesów pobierania, gdy użytkownik nie otrzymuje monitu o określenie wymiarów śledzenia, przypisanie wagi odbywa się a podstawie średniej wagi. To zachowanie występuje, kiedy np. kombinacja wymiarów śledzenia jest używana w tej samej lokalizacji i po wykonaniu odbioru przez użytkownika w lokalizacji pozostaje tylko jedna wartość wymiaru śledzenia.
- Jeśli zapasy są rezerwowane dla produktu w ilości efektywnej skonfigurowanego dla procesów zarządzania magazynem, rezerwacja odbywa się na podstawie zdefiniowanej wagi minimalnej, nawet jeśli ta ilość jest ostatnią obsługiwaną ilością stanu zapasów. To zachowanie różni się od zachowania dla towarów, które nie są skonfigurowane dla procesów zarządzania magazynem.
- Nie należy używać rzeczywistej wagi w ramach obliczeń zdolności produkcyjnych (progów grupy czynności, maksymalnej liczby podziałów pracy, maksymalnej liczby kontenerów, możliwości obciążenia pracą lokalizacji itd.) Zamiast tego procesy opierają się na wadze bezpośredniej obsługi towarów zdefiniowanej dla produktu.
- Ogólnie funkcja Retail nie jest obsługiwana dla produktów w ilości efektywnej.
 
### <a name="catch-weight-tags"></a>Znaczniki ilości efektywnej

Obecnie funkcja znaczników ilości efektywnej jest obsługiwana tylko w ramach następujących scenariuszy:

- Podczas przetwarzania zlecenia zakupu otrzymanego w aplikacji magazynu.
- Podczas przetwarzania przyjęcia ładunku za pośrednictwem aplikacji magazynu.
- W przypadku przyjęcia numeru identyfikacyjnego związanego z ładunkiem zamówienia zakupu, wysyłane jest żądanie przypisania wagi w trakcie procesu przyjęcia. Z drugiej strony dla przyjęć zamówień przeniesienia używana jest waga z danych wysyłki dla zamówienia przeniesienia.
- Dla pozycji zamówienia przeniesienia i wiersza przyjęcia, które pochodzą z magazynu, w którym nie jest używany proces zarządzania magazynem.
- Podczas przetwarzania przyjęcia zamówienia zwrotu sprzedaży można rejestrować znaczniki ilości efektywnej, ale przetwarzanie nie będzie weryfikowane, jeśli znaczniki są tymi samymi znacznikami, które były oryginalnie wysłane dla konkretnego wiersza zamówienia sprzedaży.
- Podczas przetwarzania stanu zapasów zmienionego za pomocą aplikacji magazynu.
- Jeśli przesunięcie magazynowe odbywa się przy użyciu aplikacji magazynu.
- Podczas przetwarzania korekty na wejściu i wyjściu za pomocą aplikacji magazynu.
- Podczas przetwarzania przyjęcia dla zamówień sprzedaży i przesunięcia. (Należy zauważyć, że znaczniki ilości efektywnej nie mogą być rejestrowane do pobierania składników produkcji).
- Jeśli przyjęte ilości są ograniczone wobec wierszy ładunku niezależnie od tego, czy kontenery są używane.
- Gdy produkty są pakowane w kontenerach w punkcie pakowania.
- Gdy kontenery są ponownie otwierane.
- Kiedy produkty formuły są zgłaszane jako gotowe wyroby przy użyciu aplikacji magazynu.
- Kiedy ładunki transportu są przetwarzane przy użyciu aplikacji magazynu.

Znacznik ilości efektywnej można utworzyć za pomocą procesu aplikacji magazynu, ręcznie za pomocą formularza, albo za pomocą procesu jednostki danych. Jeśli znacznik ilości efektywnej jest skojarzony z wierszem dokumentu źródłowego przychodzącego, takim jak wiersz zamówienia zakupu, znacznik zostanie zarejestrowany. Jeśli wiersz jest używany do przetwarzania wychodzącego. Znacznik zostanie zaktualizowany jako wysłany.
