---
title: Planowanie oparte na priorytecie
description: W tym artykule opisano funkcję planowania opartej na priorytecie rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 4997ba123f105f683daaa6b29fe8c5ee72cb47cb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873819"
---
# <a name="priority-based-planning"></a>Planowanie oparte na priorytecie

[!include [banner](../../includes/banner.md)]

W tym artykule opisano funkcję planowania opartej na priorytecie rozwiązania Microsoft Dynamics 365 Supply Chain Management. Ta funkcja dodaje obsługę planowania sterowanego popytem, który jest jednym z kroków planowania zapotrzebowania materiałowego sterowanego popytem (DDMRP). Planowanie oparte na priorytecie umożliwia optymalizację planowania generowania zamówień planowanych, które są sterowane według priorytetów planowania, a nie dat zapotrzebowania.

Planowanie oparte na priorytecie umożliwia ustalanie priorytetów zamówień uzupełnienia, co zapewnia określanie priorytetów popytu pilnego nad mniej ważnym popytem. Na przykład zamówienie uzupełnienia zapasów będzie mieć priorytet nad standardowym zamówieniem uzupełnienia uzupełniającego. System może automatycznie dzielić większe zamówienia na osobne mniejsze zamówienia, w których wiersze zamówienia są grupowane według priorytetu. Następnie może najpierw przetworzyć wszystkie zamówienia o wysokim priorytecie.

Aby uzyskać szybki przegląd tej funkcji, zobacz następujący film: [Obsługa optymalizacji planowania dla planowania opartego na priorytecie w systemie Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc).

## <a name="turn-on-priority-based-planning-in-your-system"></a>Włączanie planowania opartego na priorytecie w systemie

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Planowanie główne*
- **Nazwa funkcji:** *Obsługa MRP opartego na priorytecie dla optymalizacji planowania*

## <a name="where-and-how-planning-priorities-are-assigned"></a>Miejsce i sposób przypisywania priorytetów planowania

*Informacje o priorytecie* planowania podaży i popytu stanowią podstawę planowania opartego na priorytecie. Priorytet planowania określa ważność wiersza podaży lub popytu. Optymalizacja planowania korzysta z tej wartości, gdy pole **Kod zapotrzebowania** ma wartość *Priorytet*.

Priorytet planowania to zwykle liczba z między 0 (zero) a 100, gdzie wartość 0 oznacza najwyższą ważność. Jest ona wyświetlana i ustawiana w polu **Priorytet planowania**. To pole można znaleźć na następujących stronach: **Wiersze prognozy popytu**, **Szczegóły zamówienia sprzedaży**, **Szczegóły zamówienia zakupu**, **Szczegóły zamówienia przeniesienia** i **Szczegóły zamówienia planowanego**.

Jeśli pole **Kod zapotrzebowania** dla odpowiedniej pozycji lub grupy zapotrzebowania ma wartość *Priorytet*, planowanie optymalizacji bilansuje podaż z popytem zgodnie z podejściem sterowanym popytem, obliczając priorytet planowania, a dla każdego zwolnionego produktu, uwzględnia wartości ustawione w polach **Minimum**, **Punkt ponownego zamówienia** i **Maksimum** na stronie **Zapotrzebowanie na towar**.

> [!NOTE]
> Wartość *Priorytet* jest dostępna dla pola **Kod zapotrzebowania** tylko po włączeniu optymalizacji planowania.

Powiązane modele *priorytetu planowania* sterują priorytetem planowania i dzielą planowane zamówienia według zakresu priorytetów. Umożliwiają one również ustawianie domyślnych wartości priorytetów planowania dla poszczególnych typów podaży lub popytu oraz definiowanie metod obliczania priorytetu.

## <a name="types-of-priority-calculation-methods"></a>Rodzaje metod obliczania priorytetów

Dla każdego modelu priorytetu planowania jest stosowane ustawienie **metody obliczania priorytetu**, które kontroluje, w jaki sposób planowanie główne stosuje się do zamówień planowanych. Dostępne wartości to *Procent maksymalnej ilości zapasów* oraz *Zakresy priorytetów*. *Zakresy priorytetów* reprezentują bardziej zaawansowaną wersję metody *Procent maksymalnej ilości zapasów*.

### <a name="percent-of-maximum-inventory-quantity"></a>Procent maksymalnej ilości zapasów

W metodzie obliczania *Procent maksymalnej ilości zapasów* obliczenie priorytetu dostaw pozwala znaleźć bieżący *całkowity dostępny zapas* (przepływ netto) jako procent maksymalnej wartości **ilości zapasów ustawionej** dla towaru. Dla towaru i dostawcy zostanie utworzone jedno zamówienie planowane (chyba że do wymuszania podziału służy maksymalna ilość zamówienia). Priorytet planowania zamówienia jest obliczany jako procent maksimum.

Stosowany jest poniższy wzór:

*Procent maksimum* = (*Pozycja przepływu netto* × 100) ÷ *maksymalna wartość ilości zapasów z zapotrzebowania na towar*

W przypadku takiej formuły *pozycja przepływu netto* jest obliczana w następujący sposób:

*Pozycja przepływu netto* = *na stanie* + *zamówione* – *Zakwalifikowany popyt*

- *Zamówione* to podaż na zamówieniu.
- *Zakwalifikowany popyt* reprezentuje zapotrzebowanie netto, które ma datę zapotrzebowania w granicach planowania.

Podczas planowania głównego nowe planowane zamówienia są tworzone, gdy pozycja przepływu netto jest mniejsza niż ilość punktów ponownego zamówienia dla towaru. Ilość zamówienia planowanego to różnica między **maksymalną wartością ilości zapasów** ustawioną na poziomie towaru a pozycją przepływu netto. Planowany priorytet zamówienia jest obliczany jako wartość *procentowa pozycji przepływu* netto **maksymalnej wartości ilości magazynowej**.

> [!NOTE]
> Obliczony priorytet nie może być ujemny, nawet jeśli popyt przekracza łączną podaż. Jeśli popyt przekracza łączną podaż, obliczony priorytet jest ustawiany na 0 (zero).

### <a name="priority-ranges"></a>Zakresy priorytetu

Metoda obliczania *priorytetów zakresów* jest bardziej zaawansowana niż metoda *Procent maksymalnej ilości zapasów* i jest konfigurowana na poziomie modelu priorytetu planowania. Można utworzyć kilka nowych planowanych zamówień dostaw w celu zrealizowania popytu na towar. Priorytety planowanej dostawy są zgodne z wartościami zdefiniowanymi w siatce **Zakresy priorytetów planowania** na stronie **Modele priorytetu planowania**.

Jeśli w polu **Metoda obliczania priorytetu** ustawiono wartości *Zakresy priorytetów*, obowiązują następujące dodatkowe reguły:

- Jeśli dla modelu **priorytetu planowanego priorytetu** jest ustawiona wartość *Tak*, priorytet ustawiony dla każdego wiersza popytu ograniczy przedział priorytetu. Priorytet każdego nowego planowanego zamówienia dla dostaw nie będzie niższy od priorytetu popytu. Górna wartość zakresu jest uważana za próg, z który jest porównywana wartość priorytetu popytu. Jeśli priorytet popytu znajduje się dokładnie w środku między wartościami górnego progu dwóch zakresów, zostanie wybrany zakres o najwyższym priorytecie (tj. najniższym priorytecie).
- Jeśli w polu **Tworzenie zamówienia planowanego** dla modelu priorytetu planowanego ustawiono wartość *Jedna dostawa z najważniejszym priorytetem*, zostanie utworzona tylko jedna dostawa w celu zrealizowania wszystkich maksymalną wartość. Dla priorytetu zostanie ustawiony priorytet pierwszego zakresu, który wyzwoli dostawę.
- Jeśli nie ma dostępnych zapasów, brak dostaw ani popytu, wiersz w siatce **Priorytet planowania zakresów**, w której zostanie ustawiona wartość **Zero** w polu *Od ilości*.
- Jeśli jest popyt, ale nie ma dostępnych zapasów ani oczekiwanej podaży, wiersz w siatce **Priorytet planowania zakresów**, w której zostanie ustawiona wartość **Zero** w polu *Od ilości*.
- Po oszacowaniu zakresu, w którym znajduje się popyt, nadal będzie obowiązywać ustawienie opcji **Przejmij priorytet popytu**.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>Różnice między tradycyjnymi obliczeniami osi czasu a planowaniem opartym na priorytecie

Planowanie oparte na priorytecie różni się od tradycyjnego obliczania osi czasu na następujące sposoby:

- Wszystkie zwykłe wstępnie planowane procesory są nadal dostępne. Te wstępne procesory obejmują oznaczanie zatwierdzeń zatwierdzonych zamówień zgodnie z popytem sprzedaży, mapowanie zapotrzebowania na zakup i logikę rezerwacji. Przetwarzany jest tylko popyt, który nie jest zrealizowany przez te wstępne przetwarzania.
- Podczas oznaczania popytu są traktowane wszystkie dostawy, niezależnie od ich priorytetu. Ta dostawa obejmuje dostępne zapasy, zwolnioną dostawę i nieustaloną część zatwierdzonych zamówień planowanych.
- Brak dni z ujemnym popytem na dostawę w całym okresie zapotrzebowania.
- Gdy podaż jest oznaczana popytem, w pierwszej kolejności jest używana podaż o najwyższym priorytecie (tj. najniższym priorytecie). Wartość priorytetu podaży zapasów jest równa 0 (zero). W związku z tym zostanie zużyte jako pierwsze źródło.
- Nowe planowane wiersze dostaw będą tworzone zgodnie ze zwykłymi regułami minimalnego rozmiaru zamówienia, maksymalnego rozmiaru zamówienia, ilości wielokrotności itp

## <a name="planning-priority-models"></a>Modele priorytetu planowania

*Modele priorytetu planowania* są przypisywane do grup zapotrzebowania i kontrolują priorytet planowania dla zamówień planowanych. Definiują one logikę, która określa sposób obliczania wartości priorytetu planowania dla każdego planowanego zamówienia, a także sposób przypisywania priorytetu do zamówień planowanych, wierszy dostaw i wierszy popytu.

Aby pracować z modelami priorytetu planowania, przejdź do **Planowanie główne \> Konfiguracja \> Modele priorytetu planowania**. Jak już wcześniej mówiono, jednym z najważniejszych ustawień modelu jest wartość **metody obliczania priorytetu**. To ustawienie steruje metodą obliczania, która jest używana, gdy planowanie główne przypisuje wartość priorytetu do zamówień planowanych.

> [!NOTE]
> Modele priorytetu planowania są stosowane w całej organizacji we wszystkich firmach.

### <a name="coverage-group"></a>Grupa zapotrzebowania

Skonfiguruj nową grupę zapotrzebowania, która ma być użyciu do planowania opartego na priorytecie, zgodnie z opisem w [Definiowanie reguł zapotrzebowania dla towarów](../tasks/define-coverage-rules-items.md). Po utworzeniu grupy zapotrzebowania należy ustawić następujące dodatkowe pola:

- **Kod zapotrzebowania** — umożliwia *wybranie priorytetu*, jeśli grupa zapotrzebowania korzysta z planowania opartego na priorytecie.
- **Model priorytetu planowania** — umożliwia wybór dowolnego modelu priorytetu planowania na całej organizacji.

### <a name="item-coverage"></a>Zapotrzebowanie na towary

Skonfiguruj ustawienia zapotrzebowania na towar zgodnie z opisem w [ustawieniach zapotrzebowania](../coverage-settings.md). Domyślnie wartość **kodu zapotrzebowania** wybrana dla grupy zapotrzebowania jest kopiowana do ustawień zapotrzebowania na towar. W razie potrzeby można jednak zastąpić wartość domyślną. W niektórych przypadkach pole **Kod zapotrzebowania** dla rekordu zapotrzebowania na towar ma wartość *Planowanie, ale dla powiązanej grupy zapotrzebowania* nie jest zdefiniowany żaden model priorytetu planowania. W takich przypadkach każdy model, w którym pole **Metoda obliczania priorytetów** jest ustawione na *Procent maksymalnej ilości zapasów* i pole **Planowane tworzenie zamówień** jest ustawione na *Pojedyncza dostawa z najważniejszym priorytetem* zostaną zastosowane domyślnie.

Ustaw w polu **Kod zapotrzebowania** wartość *Priorytet*, aby udostępnić pole **Punkt ponownego zamówienia** w ustawieniach zapotrzebowania na towar. W tym polu należy wprowadzić ilość punktów ponownego zamówienia, z których system będzie korzystać podczas ustalania, kiedy mają być składane zamówienia planowane o wartości **kodu zapotrzebowania** *Priorytet*.

Ilość punktów ponownego zamówienia jest często obliczana jako popyt w czasie realizacji powiększony o wartość minimalną (zapas bezpieczeństwa). Musi to być wartość między wartościami **Minimum** i **Maksimum**.

Na przykład pola można ustawić w następujący sposób:

- **Minimum:** *10*
- **Poziom ponownego zamówienia:** *45*
- **Maksimum:** *60*

W tym przykładzie ilość punktów ponownego zamówienia jest oparta na czasie realizacji 7 dni oraz średnim dziennym użyciu 5. W związku z tym popyt w czasie realizacji wynosi 35. Następnie należy dodać minimalną wartość 10 (zapas bezpieczeństwa), aby uzyskać punkt ponownego zamówienia 45. Gdy ta konfiguracja jest używana, podaż będzie proponowana, gdy prognozowany poziom zapasów będzie poniżej 45. Priorytet zamówienia jest oparty na konfiguracji priorytetu planowania.

### <a name="manage-planning-priority-models"></a>Zarządzaj modelami priorytetów planowania

Aby pracować z modelami priorytetu planowania. wykonaj następujące kroków.

1. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Modele priorytetu planowania**.
1. Wybierz istniejący model w okienku listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nowy model.
1. W nagłówku rekordu określ następujące pola:

    - **Nazwa** – wprowadź nazwę dla modelu. Nazwa musi być unikatowa we wszystkich firmach w Twojej organizacji.
    - **Opis** – wprowadź opis modelu.
    - **Priorytet metody obliczania** – Wybierz jedną z następujących wartości:

        - *Zakresy priorytetów* — po wybraniu tej wartości siatka **zakresów priorytetów planowania** staje się dostępna. Należy określić kilka zakresów priorytetów, aby zdefiniować wartość priorytetu planowania.
        - *Procent maksymalnej ilości zapasów* — Umożliwia obliczenie wartości priorytetu planowania jako wartości procentowej na podstawie prognozowanych poziomu zapasów powyżej maksymalnej ilości zapasów.

    - **Tworzenie zamówienia planowanego** — to pole jest dostępne, gdy w polu **Metoda obliczania priorytetu** są ustawione *zakresy priorytetów*. Należy wybrać jedną z następujących opcji:

        - *Jedna dostawa z najważniejszym priorytetem* — nie dziel zamówień planowanych na podstawie zakresu priorytetów. Priorytet planowania zamówienia planowanego zależy od najważniejszego zakresu priorytetów (tj. najniższej wartości priorytetu planowania).
        - *Podziel zgodnie z zakresami priorytetów* — podziel popyt na wiele zamówień planowanych w oparciu o zakresy priorytetów planowania. Priorytet planowania dla poszczególnych zamówień planowanych jest określony przez priorytet planowania w powiązanym zakresie priorytetów planowania.

    - **Rozważ priorytet popytu** – Ustaw tę opcję na Wartość *Tak*, aby ograniczyć priorytet nowego planowanego zamówienia utworzonego dla dostaw. (Priorytet nie będzie niższy od priorytetu powiązanego popytu.) Jeśli zostanie ustawiona opcja *Nie*, priorytety zamówienia popytu nie będą rozważane podczas obliczania priorytetu zamówienia dostawy.

1. Jeśli w polu **Metoda obliczania priorytetu** ustawiono wartości *Zakresy priorytetów*, użyj przycisków **Dodaj** i **usuń** na pasku narzędzi skróconej karty **Zakresy priorytetów planowania**, aby dodać lub usunąć w razie konieczne wiersze zakresu priorytetów. Jeśli istnieje wiele wierszy i wstawisz nowy wiersz, priorytet planowania zostanie automatycznie ustawiony na średnią wybranego wiersza i wiersz nad nim. Dla każdego wiersza ustaw następujące pola:

    - **Priorytet planowania** — wprowadź wartość z między 0,00 a 100,00. Ta wartość reprezentuje priorytet planowania, który jest używany dla wiersza. Najniższa wartość priorytetu reprezentuje najwyższy priorytet. Przypisana jest wartość domyślna, ale można ją zmienić według potrzeb. Tej samej wartości **priorytetu planowania** nie można użyć dla więcej niż jednego zakresu priorytetów planowania w tym samym modelu priorytetu planowania.
    - **Opis** — umożliwia wprowadzenie opisu zakresu priorytetu planowania (na przykład *Zmiana punktu zamówienia na Maksimum*).
    - **Od ilości** — dolny limit zakresu priorytetu planowania. Ta wartość jest tylko do odczytu i jest oparta na wartościach **Do ilości** i **Procentu do ilości** dla poprzedniego zakresu priorytetu planowania.
    - **Do ilości** — Należy wybrać pole z zapotrzebowania na towar, które ma być używane do definiowania górnego limitu zakresu. Obsługiwane są następujące wartości i wpływają na wartość **Od ilości** następnego zakresu:

        - *Zero* — ta wartość reprezentuje zakres od ujemnego do zera (*zero lub mniej* do *zera*). W przypadku wierszy, w których jest wybrana ta wartość, pole **Procent ilości** jest tylko do odczytu i zawsze ma wartość *100* procent.
        - *Minimalna ilość zapasów* — ta wartość reprezentuje wartość **minimalną** dla towaru na stronie **Zapotrzebowania na towar**. W przypadku wierszy, w których jest wybrana ta wartość, pole **Procent ilości** do można edytować i służy do ustawienia wartości **Od ilości** dla następnego zakresu (na przykład do *80% minimalnej ilości magazynowej*).
        - *Punkt zmiany kolejności* — ta wartość reprezentuje wartość **Punkt zmiany kolejności** dla towaru na stronie **Zapotrzebowania na towar**. W przypadku wierszy, w których jest wybrana ta wartość, pole **Procent ilości** do można edytować i służy do ustawienia wartości **Od ilości** dla następnego zakresu (na przykład do *80% Punktu zmiany kolejności*).
        - *Maksymalna ilość zapasów* — ta wartość reprezentuje wartość **maksymalną** dla towaru na stronie **Zapotrzebowania na towar**. W przypadku wierszy, w których jest wybrana ta wartość, pole **Procent ilości** do można edytować i służy do ustawienia **Od ilości** dla następnego zakresu (na przykład do *80% minimalnej ilości magazynowej*).
        - *Nieskończona* – Ta wartość reprezentuje nieskończony górny poziom zakresu (*Nieskończony lub mniej* do *Nieskończony*). W przypadku wierszy, w których jest wybrana ta wartość, pole **Procent ilości** jest tylko do odczytu i zawsze ma wartość *100* procent.

    - **Procent ilości** — Służy do wprowadzania wartości procentowej używanej do obliczania górnego limitu zakresu priorytetu planowania na podstawie wartości wybranej w polu **Do ilości**. Na przykład, jeśli w polu **Ilość do** ustawiono *minimalną ilość magazynową*, a w polu **Procent do ilości** jest ustawiona wartość *50*, górny limit będzie mieć wartość 50 procent minimalnej ilości zapasów z powiązanego zapotrzebowania na towar.

1. Na skróconej karcie **Planowanie domyślnych priorytetów** ustaw wymagane pola, aby zdefiniować domyślne priorytety planowania dla każdego typu podaży lub wiersza popytu (zamówienia sprzedaży, zamówienia zakupu, zamówienia przeniesienia lub prognozy popytu). Można wprowadzić tylko wartości dodatnie.

## <a name="view-and-maintain-planning-priority"></a>Wyświetl i zachowaj priorytet planowania

Priorytet planowania jest wyświetlany i ustawiany w polu **Priorytet planowania**. To pole można znaleźć na stronach wymienionych w poniższej tabeli. Priorytet jest ustawiany jako liczba z zakresu od 0 (zero) do 100, gdzie 0 oznacza najwyższą ważność.

| Strona | Lokalizacja w terenie | Źródło wartości |
|---|---|---|
| Wiersze prognozy popytu | <p>Karta **Towar**</p><p>(Wybierz wiersz w górnej sekcji, a następnie wybierz opcję Karta **Towar**)</p> | Wartość domyślna lub wartość ustawiana ręcznie |
| Szczegóły zamówienia sprzedaży | <p>Na karcie **Zamówienie** na skróconej karcie **Szczegóły wiersza**.</p><p>(Wybierz wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**, a następnie na **Szczegóły wiersza** wybierz kartę **Dostawa**).</p> | Wartość domyślna, wartość z firmy międzyfirmowej lub wartość ustawiona ręcznie |
| Szczegóły zamówienia zakupu | <p>Na karcie **Zamówienie** na skróconej karcie **Szczegóły wiersza**.</p><p>(Wybierz wiersz na skróconej karcie **Wiersze zamówienia zakupu**, a następnie na **Szczegóły wiersza** wybierz kartę **Dostawa**).</p> | Wartość ustawiana podczas procesu kompilowania zamówień planowanych, wartość z zamówień międzyfirmowych lub wartość ustawiana ręcznie |
| Szczegóły zamówienia przelewu | <p>Na karcie **Zamówienie** na skróconej karcie **Szczegóły wiersza**.</p><p>(Wybierz wiersz na skróconej karcie **Przenieś wiersze zamówienia**, a następnie na **Szczegóły wiersza** wybierz kartę **Dostawa**).</p> | Wartość ustawiana podczas ustalania z zamówień planowanych lub wartość ustawiana ręcznie |
| Szczegóły zamówienia planowanego | Skrócona karta **Ogólne** | Wartość obliczana podczas planowania głównego lub wartość ustawiana ręcznie |

### <a name="intercompany-trade"></a>Handel międzyfirmowy

Wartość **priorytetu planowania** w wierszach międzyfirmowej podaży i popytu jest współużytkowanych przez połączone jednostki. Modyfikacja po obu stronach zostanie odzwierciedlona w połączonym wierszu zamówienia.

Oto kilka przykładów:

- Użytkownik zmienia priorytet planowania dla wiersza międzyfirmowe zamówienie sprzedaży z 20 na 30. Ta zmiana jest odzwierciedlona w połączonym międzyfirmowe zamówienie zakupu.
- Użytkownik zmienia priorytet planowania dla wiersza międzyfirmowe zamówienie zakupu z 40 na 50. Ta zmiana jest odzwierciedlona w połączonym międzyfirmowe zamówienie sprzedaży.
