---
title: Profil i poziomy buforu
description: Ten artykuł zawiera informacje o profilach i poziomach buforów, które określają minimalne i maksymalne poziomy zapasów, jakie powinny być utrzymywane dla każdego punktu rozłączenia.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: d254b949d31d0b15141646503c64760062b77fc7
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689167"
---
# <a name="buffer-profile-and-levels"></a>Profil i poziomy buforu

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Po zidentyfikowaniu punktów rozłączenia (kluczowych pozycji, które będziesz strategicznie utrzymywać w magazynie) musisz zdecydować, jak duże zapasy (bufor) będziesz utrzymywać w każdym z nich. Zadanie to jest drugim etapem planowania zasobów materiałów sterowanych popytem (DDMRP).

## <a name="buffer-levels-and-zones"></a>Poziomy i strefy buforowe

W DDMRP każdy bufor zapasów jest definiowany za pomocą trzech wartości: ilości minimalnej, ilości maksymalnej i punktu zamawiania. Wartości te wyznaczają trzy strefy różnic, które są oznaczone następującymi kodami kolorystycznymi:

- **Strefa czerwona** — obszar poniżej ilości minimalnej. Minimalna ilość określana jest również jako "góra czerwonego", a twoja strategia planowania powinna być tak opracowana, aby poziom zapasów był zawsze powyżej tego punktu.
- **Strefa żółta** — obszar między ilością minimalną a punktem ponownego zamówienia. Punkt zmiany kolejności jest również określany jako "góra żółtego". Po osiągnięciu tego punktu system powinien zmienić kolejność.
- **Strefa zielona** — obszar pomiędzy punktem zamówienia a ilością maksymalną. Maksymalna ilość określana jest również jako "góra zielonego". Ten punkt to maksymalny poziom, do którego zostaną uzupełnione zapasy.

Poniższa ilustracja przedstawia trzy kolorowe strefy i ich związek z ilością minimalną, ilością maksymalną i punktem zamawiania.

![Strefy i poziomy buforowe DDMRP.](media/ddmrp-buffer-levels.png "Strefy i poziomy buforowe DDMRP")

## <a name="calculating-the-buffer-zones"></a>Obliczanie stref buforowych

W tym rozdziale wyjaśniono, jak oblicza się wysokość każdej strefy buforowej.

Zazwyczaj najpierw obliczana jest strefa żółta. Ta strefa reprezentuje ilość, którą zużywasz od momentu złożenia zamówienia do chwili jego nadejścia. Innymi słowy, jest to spodziewane zużycie w czasie realizacji uzupełniania zapasów. Oblicza się ją za pomocą następującego równania:

- **Strefa żółta** = *Średnie dzienne wykorzystanie (ADU)* × *Odłączony czas realizacji*

*Odłączony czas realizacji zamówienia* oznacza czas potrzebny do wyprodukowania lub otrzymania przedmiotu, jeśli punkty rozłączne są zawsze w magazynie. Zazwyczaj jest on znacznie krótszy niż *skumulowany czas realizacji*, który jest tradycyjnie stosowany w planowaniu ogólnym. Prawidłowe ustawienia buforów są kluczem do zapewnienia, że punkty odprzęgania są zawsze w magazynie, ale nie w nadmiarze.

Czerwona strefa jest obliczana przy użyciu następujących równań:

- **Czerwona podstawa** = *ADU* × *Odłączony czas realizacji zamówienia* × *Współczynnik czasu realizacji zamówienia*
- **Czerwone bezpieczeństwo** = *Czerwona podstawa* × *Współczynnik zmienności*
- **Czerwona strefa** = *Czerwona podstawa* + *Czerwone bezpieczeństwo*

Zielona strefa jest obliczana jako maksymalny wynik trzech poniższych równań:

- *Minimalna ilość zamówienia*
- *ADU* × *Cykl zamówień*
- *ADU* × *Odłączony czas realizacji zamówienia* × *Współczynnik czasu realizacji zamówienia*

## <a name="calculating-average-daily-usage"></a>Obliczenie średniego dziennego użycia

System wykorzystuje jedną z trzech metod obliczania ilości, którą spożywasz w ciągu dnia:

- **Średnie dzienne zużycie (w przeszłości)** – To podejście jest oparte na rzeczywistym zużyciu w przeszłości.
- **Średnie dzienne zużycie (w przeszłości)** – To podejście opiera się na przewidywanym przyszłym zużyciu.
- **Średnie dzienne zużycie (połączone)** – To podejście jest oparte na ważonym zużyciu z przeszłości i prognozowanych.

### <a name="average-daily-usage-past"></a>Średnie dzienne użycie (przeszłe)

Dotychczasowe ADU oblicza się jako średnią, dodając ilości zużywane każdego dnia przez określoną liczbę dni w przeszłości, a następnie dzieląc sumę przez liczbę dni. Poniższa ilustracja pokazuje, jak działa to podejście, gdy obliczenia dotyczą trzech dni w przeszłości.

![Średnie dzienne użycie (przeszłe) — wykres](media/ddmrp-adu-past.png "Średnie dzienne użycie (przeszłe) — wykres")

Na poprzedniej ilustracji, jeśli dziś jest poranek 11 czerwca, to ADU za trzy poprzednie dni (8, 9 i 10 czerwca) wynosi 21.

- **ADU (przeszłe)** = (29 + 11 + 23) ÷ 3 = 21

Przy obliczaniu średniego dziennego zużycia (przeszłego) są brane pod uwagę następujące transakcje:

- Transakcje zmniejszające ilość towaru (w tabeli `inventtrans`, w której ilość jest mniejsza od zera)
- Transakcje o stanie *Zamówione*, *Zamówione zarezerwowane*, *Fizycznie zarezerwowane*, *Pobrane*, *Odjęte* lub *Sprzedane*
- Transakcje z datą w wybranym okresie wstecz (średni dzienny okres użytkowania w przeszłości)
- Transakcje inne niż praca magazynowa, kwarantanna, oferty sprzedaży lub zestawienia (`WHSWork`, `WHSQuarantine`, `SalesQuotation` lub `Statement`)
- Transakcje inne niż arkusze przeniesienia, które znajdują się w tym samym wymiarze zapotrzebowania

### <a name="average-daily-usage-forward"></a>Średnie dzienne użycie (w przód)

W przypadku nowego produktu możesz nie mieć żadnych danych dotyczących jego użytkowania w przeszłości. W związku z tym możesz zastosować przewidywaną liczbę jednostek ADU w przyszłości (na przykład na podstawie prognozowanego zapotrzebowania). Poniższa ilustracja pokazuje, jak działa to podejście, gdy obliczenia dotyczą trzech dni w przyszłości (łącznie z dniem dzisiejszym).

![Średnie dzienne użycie (w przód) – wykres](media/ddmrp-adu-forward.png "Średnie dzienne użycie (w przód) – wykres")

Na poprzedniej ilustracji, jeśli dziś jest poranek 11 czerwca, to ADU za trzy kolejne dni (11, 12 i 13 czerwca) wynosi 21.66.

- **ADU (przyszłe)** = (18 + 18 + 29) ÷ 3 = 21.66

Przy obliczaniu średniego dziennego zużycia (przyszłego) są brane pod uwagę następujące transakcje:

- Transakcje prognozowe dla pozycji, w której prognoza jest wybrana w planie głównym
- Transakcje z datą w wybranym okresie w przód (średni dzienny okres użytkowania w przyszłości)

### <a name="average-daily-usage-blended"></a>Średnie dzienne użycie (mieszane)

ADU mieszane łączy średnie zużycie w przeszłości i średnie zużycie w przyszłości, jak pokazano na poniższej ilustracji.

![Średnie dzienne użycie (mieszane) – wykres](media/ddmrp-adu-blended.png "Średnie dzienne użycie (mieszane) – wykres")

Z poprzedniej ilustracji wynika, że jeśli dziś jest poranek 11 czerwca, to mieszane ADU dla poprzedniego i kolejnych trzech dni (od 8 do 13 czerwca) wynosi 21,33.

- **ADU mieszane** = (*ADU przeszłe* + *ADU przyszłe*) ÷ 2<br>= (21 + 21.66) ÷ 2<br>= 21.33

## <a name="buffer-calculation-factors"></a>Współczynniki obliczeniowe bufora

Dla każdego elementu możesz zdefiniować dwa czynniki, które pozwolą Ci określić, jak duże powinny być czerwone i zielone strefy. W ten sposób możesz skompensować oczekiwany czas realizacji i zmienność popytu.

![Czas realizacji i czynniki zmienności.](media/ddmrp-zone-factors.png "Czas realizacji i czynniki zmienności")

Pierwszym czynnikiem jest czynnik *czasu naładowania*. Wartość jest wartością dziesiętną z zakresu od 0 do 1. Im dłuższy jest czas realizacji, tym niższa powinna być wartość. Demand Driven Institute zaleca następujące przedziały:

- **Długi czas realizacji:** 0,20–0,40
- **Średni czas realizacji:** 0,41–0,60
- **Krótki czas realizacji:** 0,61–1,00

Drugi czynnik to *czynnik zmienności*. Wartość jest wartością dziesiętną z zakresu od 0 do 1. Im większa jest zmienność popytu, tym niższa powinna być ta wartość. Demand Driven Institute zaleca następujące przedziały:

- **Niska zmienność:** 0,20–0,40
- **Średnia zmienność:** 0,41–0,60
- **Wysoka zmienność:** 0,61–1,00

## <a name="buffer-calculation-examples"></a>Przykłady obliczeń bufora

Ten przykład jest kontynuacją przykładu produkcji poduszek, który został przedstawiony w rozdziale [Pozycjonowanie zapasów](ddmrp-inventory-positioning.md). W tym przykładzie wybrano punkty rozłączne, które skróciły czas realizacji z 21 dni do pięciu dni, jak pokazano na poniższej ilustracji.

![Przykład odłączonego czasu realizacji.](media/ddmrp-bom-decoupled-lead-time-example.png "Przykład odłączonego czasu realizacji")

W tym przykładzie załóżmy, że ADU zostało obliczone jako 23 sztuki i, jak pokazano na poprzedniej ilustracji, odłączony czas realizacji zamówienia bez powiązania wynosi pięć dni. Korzystając z tych wartości, możesz obliczyć żółtą strefę za pomocą następującego równania:

- **Strefa żółta** = *ADU* × *Odłączony czas realizacji zamówienia* = 115

![Przykład obliczania strefy żółtej.](media/ddmrp-example-calc-yellow.png "Przykład obliczania strefy żółtej")

Kalkulacja strefy czerwonej przypomina kalkulację strefy żółtej, ale jest uzupełniona o zmienność i czas realizacji. W tym przykładzie załóż, że zaobserwowałeś średni czas realizacji zamówienia (współczynnik = 0,50) i dużą zmienność popytu (współczynnik = 0,8). Wykorzystując te wartości oraz składniki z równania dla strefy żółtej, możesz obliczyć strefę czerwoną, stosując następujące równania:

- **Czerwona podstawa** = *ADU* × *Odłączony czas realizacji zamówienia* × *Współczynnik czasu realizacji zamówienia* = 57.5
- **Czerwone bezpieczeństwo** = *Czerwona podstawa* × *Współczynnik zmienności* = 46
- **Czerwona strefa** = *Czerwona podstawa* + *Czerwone bezpieczeństwo* = 103.5

System zaokrągli czerwoną strefę do 104 sztuk (ea), ponieważ sztuki są liczone w liczbach całkowitych.

![Przykład obliczania strefy czerwonej.](media/ddmrp-example-calc-red.png "Przykład obliczania strefy czerwonej")

Kalkulacja strefy zielonej również obejmuje elementy z równania strefy żółtej, ale dopuszcza minimalną wielkość zamówienia, cykl zamówienia i współczynnik czasu realizacji. W tym przykładzie załóżmy, że nie ma cyklu zamówień (dlatego nie masz żadnych ograniczeń czasowych dotyczących częstotliwości składania zamówień), a minimalna ilość zamówienia wynosi 10 sztuk. Zielona strefa jest następnie obliczana jako maksymalny wynik trzech poniższych równań:

- *Minimalna ilość zamówienia* = 10
- *ADU* × *Cykl zamówienia* = 0
- *ADU* × *Odłączony czas realizacji zamówienia* × *Współczynnik czasu realizacji zamówienia* = 57.5

System zaokrągli zieloną strefę do 58 sztuk (ea), ponieważ sztuki są liczone w liczbach całkowitych.

![Przykład obliczania strefy zielonej.](media/ddmrp-example-calc-green.png "Przykład obliczania strefy czerwonej")

Poniższa ilustracja podsumowuje wyniki obliczeń stref, wykorzystując grafikę lejka, która jest często używana w DDMRP.

![Podsumowanie wyników obliczeń strefy.](media/ddmrp-example-calc-summary.png "Podsumowanie wyników obliczeń strefy")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a>Korekty dynamiczne

Dynamiczna regulacja pozwala zastosować *czynnik korekty zapotrzebowania* w okresach wysokiego lub niskiego zapotrzebowania. Ten współczynnik mnoży ADU we wszystkich obliczeniach dla wybranego okresu. Następnie strefy buforowe są kolejno modyfikowane. Zazwyczaj stosujesz ten czynnik po wygenerowaniu początkowych wartości buforów, aby móc je dostroić w czasie i w odpowiedzi na zmieniające się warunki. To zadanie jest trzecim krokiem procesu DDMRP.

Na przykład w sierpniu może być większe zapotrzebowanie na poduszki, ponieważ ludzie wyjeżdżają na wakacje. Dlatego oczekuje się, że sprzedaż będzie wyższa. W tym przypadku możesz zmienić wartość **Współczynnika korekty popytu** dla produktu na *1,5* dla wszystkich tygodni w sierpniu.

W ten sposób można obliczać wartości buforów w czasie, a następnie dostosowywać je w oparciu o więcej niż tylko informacje, które posiada system. W pełnej implementacji DDMRP będziesz codziennie obliczał nowe wartości buforów za pomocą zadania wsadowego i automatycznie akceptował te wartości. Następnie uruchomisz planowanie jako zadanie wsadowe i codziennie będziesz przeglądać zaplanowane zlecenia, aby uzupełnić bufory.

## <a name="implement-buffers-in-supply-chain-management"></a>Wdrożenie buforów w Supply Chain Management

W tym rozdziale opisano, jak wdrożyć strategię strefy buforowej w programie Microsoft Dynamics 365 Supply Chain Management. Zakłada on, że wykonałeś już analizy i obliczenia przedstawione w pierwszej części tego artykułu.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a>Ustaw bufory dla elementu punktu rozłącznego

Wykonaj poniższe kroki, aby ustawić wartości buforów dla punktu rozłącznego.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz uwolniony element, który jest ustawiony jako punkt rozłączenia. (Aby uzyskać więcej informacji, zobacz [Pozycjonowanie zapasów](ddmrp-inventory-positioning.md)).
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Objęcie przedmiotu**.
1. Na stronie **Zapotrzebowanie na towary** wybierz rekord zapotrzebowania na towar, który powoduje utworzenie punktu dekodowania. (W tym rekordzie pojawi się nazwa grupy pokrycia, która została utworzona w celu utworzenia punktów rozłączenia).
1. Kliknij kartę **Ogólne**.
1. Jeśli chcesz, aby system przeliczał wartości buforów codziennie lub co tydzień na podstawie historii sprzedaży, prognoz i ustawień grup pokrycia, wykonaj poniższe kroki:

    1. Ustaw wartość **Wartości buforowych** z czasu na *Tak*.
    1. Komunikat powiadamia Cię, że ręczne ustawienia buforu (**Minimum**, **Punkt ponownego zamówienia** i **Maksimum**) zostaną zresetowane, jeśli będziesz kontynuować. Wybierz **tak**, aby zachować nowe ustawienie.

    Jeśli wolisz obliczyć lub wprowadzić ustawienia bufora tylko raz, wykonaj poniższe kroki:

    1. Ustaw wartość **Wartości buforowych** z czasu na *Nie*.
    1. Ustaw pola **Minimum**, **Punkt ponownego zamówienia** oraz **Maksimum** na wartości buforów, które obliczyłeś dla elementu, tak jak to opisano wcześniej w tym artykule.

1. Ustaw następujące pola, aby zakończyć konfigurację obliczeń DDMRP dla elementu:

    - **Cykl zamówienia** — Określ liczbę dni, które muszą upłynąć między zamówieniami zakupu przedmiotu. Ustaw wartość na *0* (zero), jeśli nie istnieją ograniczenia kolejności. To pole wpływa na bufor maksymalnej ilości, o czym była mowa wcześniej w tym artykule.
    - **Średnie dzienne zużycie** — Możesz opcjonalnie wprowadzić szacunkową wartość ADU dla danego przedmiotu. To pole jest używane wyłącznie w celach informacyjnych. Zazwyczaj wartość ta jest obliczana automatycznie w ramach obliczeń bufora.
    - **Próg gwałtownego wzrostu zamówień** – Określ minimalną liczbę dziennych sprzedaży przedmiotu, które kwalifikują się jako gwałtowny wzrost sprzedaży (wyjątkowo duży popyt). System używa tego pola, aby zwiększyć wielkość zamówienia dla planowanych zamówień w okresach dużego zapotrzebowania. Aby uzyskać więcej informacji, zobacz [Planowanie zgodne z zapotrzebowaniem](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a>Obliczaj lub wprowadzaj odłączone czasy realizacji zamówień

W przypadku elementów, w których zdecydowałeś się zezwolić systemowi na [automatyczne obliczanie stref buforowych](#set-up-buffers), wykonaj poniższe kroki, aby obliczyć lub wprowadzić odłączone czasy realizacji dla elementu z punktem rozłączenia.

1. Otwórz stronę **Strona pokrycia przedmiotu** dla twojego punktu rozłączenia. (Więcej informacji znajdziesz w rozdziale [Ustawianie buforów dla punktu rozłącznego.](#set-up-buffers)).
1. Wybierz rekord pokrycia elementu, który tworzy punkt rozłączenia.
1. Wybierz kartę **Wartości buforowe**.
1. Jeśli w siatce nie są wyświetlane okresy, w okienku akcji na karcie **Wartości buforowe** wybierz opcję **Dodaj okresy**. System wypełnia siatkę wierszami dla każdego dziennego lub tygodniowego okresu czasu, w zależności od tego, czy pole **Min, max i okres punktu zmiany kolejności** dla [grupy zapotrzebowania](ddmrp-inventory-positioning.md) jest ustawione na *Dzienne* lub *Tygodniowe*. System doda tyle wierszy, aby osiągnąć limit czasu określony dla grupy pokrycia przypisanej do elementu.
1. Wybierz przedział czasowy, w którym chcesz obliczyć odłączony czas realizacji. (Zazwyczaj ten okres czasu to okres obejmujący dzisiejszą datę).
1. Na pasku akcji, w zakładce **Wartości bufora**, wybierz **Obliczanie odłączonego czasu realizacji zamówienia**.
1. W oknie dialogowym **Obliczanie odłączonego czasu realizacji zamówienia** ustaw następujące pola:

    - **BOM** — umożliwia wybór BOM, dla którego ma zostać uruchomione obliczenie.
    - **Data** — umożliwia wybór daty, dla którego ma zostać uruchomione obliczenie. Zestaw dostępnych zestawów BOM zostanie przefiltrowany tak, aby były widoczne tylko zestawy BOM aktywne dla wybranej daty.
    - **Ilość** – Wprowadź ilość, dla której chcesz wykonać obliczenia. Zbiór dostępnych zestawów BOM zostanie przefiltrowany tak, że zostaną pokazane tylko te zestawy BOM, które dotyczą określonej ilości.

1. Wybierz **OK**, aby wykonać obliczenia i zamknąć okno dialogowe **Obliczanie odłączonego czasu realizacji**. W kolumnie **Odłączony czas realizacji** dla wybranego okresu pojawia się teraz obliczona wartość.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a>Obliczanie lub wprowadzanie średniego dziennego zużycia

W przypadku elementów, dla których wybrano opcję [obliczania stref buforowych automatycznie](#set-up-buffers), wykonaj poniższe kroki, aby obliczyć lub wprowadzić ADU dla elementu punktu rozłączenia.

1. Otwórz stronę **Strona pokrycia przedmiotu** dla twojego punktu rozłączenia. (Więcej informacji znajdziesz w rozdziale [Ustawianie buforów dla punktu rozłącznego.](#set-up-buffers)).
1. Wybierz rekord pokrycia elementu, który tworzy punkt rozłączenia.
1. Wybierz kartę **Wartości buforowe**.
1. Jeśli w siatce nie są wyświetlane okresy, w okienku akcji na karcie **Wartości buforowe** wybierz opcję **Dodaj okresy**. System wypełnia siatkę wierszami dla każdego dziennego lub tygodniowego okresu czasu, w zależności od tego, czy pole **Min, max i okres punktu zmiany kolejności** dla [grupy zapotrzebowania](ddmrp-inventory-positioning.md) jest ustawione na *Dzienne* lub *Tygodniowe*. Ponadto wartości domyślne dla pól **Współczynnik czasu trwania** i **Współczynnik zmienności** są pobierane z grupy pokrycia. Możesz dowolnie edytować te wartości dla każdego wiersza.
1. Wybierz okres czasu, w którym chcesz obliczyć ADU.
1. Na pasku akcji, w zakładce **Wartości bufora**, wybierz **Obliczanie średniego dziennego zużycia**. System próbuje zebrać dane, które są wymagane do obliczenia ADU, zgodnie z definicją dla [grupy zapotrzebowania](ddmrp-inventory-positioning.md).
1. Wykonaj jeden z następujących kroków:

    - Jeśli wymagane dane są dostępne, wyniki obliczeń są dodawane do kolumny **Średnie dzienne użycie**. W tym przypadku nie jest wymagane żadne działanie.
    - Jeśli wymagane dane nie są dostępne, automatycznie nie zostaną dodane żadne wartości. W takim przypadku wprowadź ręcznie szacunkowe wartości dla każdego wiersza, w którym planujesz obliczyć wartości buforów.

### <a name="calculate-and-apply-buffer-values"></a>Obliczanie i stosowanie wartości buforów

W przypadku elementów, dla których wybrano opcję [obliczania stref buforowych automatycznie](#set-up-buffers), możesz ręcznie uruchomić obliczanie wartości bufora, wykonując poniższe kroki.

1. Dla odpowiedniego elementu punktu rozłączenia [konfiguruj obliczanie bufora](#set-up-buffers), [oblicz lub wprowadź odłączone czasy realizacji](#calc-lead-time) oraz [oblicz lub wprowadź średnie dzienne zużycie](#calc-adu) dla wszystkich odpowiednich okresów czasu, jak opisano wcześniej w tym artykule.
1. Otwórz stronę **Strona pokrycia przedmiotu** dla twojego punktu rozłączenia.
1. Wybierz zakładkę **Wartości bufora**, w której powinna być już widoczna lista okresów czasu.
1. Wybierz okres czasu, w którym chcesz obliczyć wartości bufora. (Zazwyczaj jest to okres obejmujący dzień dzisiejszy). Wybrany wiersz musi mieć już niezerowe wartości w kolumnach **Średnie dzienne użycie** i **Odłączony czas realizacji**.
1. Edytuj pole **Współczynnik korekty zapotrzebowania** dla jednego lub więcej wierszy, zgodnie z wymaganiami. System zastosuje ten współczynnik do wartości **Średnie dzienne użycie** we wszystkich obliczeniach bufora, w których ta wartość jest używana. Ten czynnik umożliwia dostosowanie się do zmian popytu w zależności od daty (na przykład w przypadku świąt lub artykułów sezonowych).
1. Na pasku akcji, na zakładce **Wartości bufora**, wybierz **Oblicz min, max i ilości punktu zamawiania**. System oblicza i wypełnia kolumny **Obliczone minimum**, **Obliczony punkt zmiany kolejności** oraz **Obliczone maksimum** w siatce na stronie **Pokrycie pozycji**.
1. Po zakończeniu przeglądania obliczonych wartości musisz je zastosować. W przeciwnym razie nie będą one miały żadnego wpływu. Gdy stosujesz obliczenia dla jednego lub więcej wierszy, wartości z pól **Obliczone min**, **Obliczone ponowne uporządkowanie** i **Obliczone max** są kopiowane odpowiednio do kolumn **Min**, **Punkt ponownego uporządkowania** i **Max**. W okienku akcji na karcie **Wartości buforów** w grupie **Podejmij działanie** wybierz jeden z następujących przycisków:

    - **Zaakceptuj wszystkie obliczenia** – Zastosuj wszystkie obliczone wartości w siatce.
    - **Akceptuj obliczenia dla wybranych wierszy** – zastosuj obliczone wartości tylko do wybranych wierszy.
    - **Odrzuć wszystkie obliczenia** – Odrzuć wszystkie obliczone wartości dla minimalnych ilości, maksymalnych ilości i punktów ponownego zamówienia w siatce.
    - **Odrzuć obliczenia dla wybranych wierszy** – Odrzuć wszystkie obliczone wartości dla minimalnych ilości, maksymalnych ilości i punktów ponownego zamówienia dla wybranych wierszy.

### <a name="schedule-automatic-buffer-value-calculations"></a>Zaplanuj automatyczne obliczanie wartości bufora

Po pełnym skonfigurowaniu ustawień DDMRP i potwierdzeniu, że działają one zgodnie z oczekiwaniami, prawdopodobnie będziesz chciał skonfigurować zadanie wsadowe, aby okresowo przeliczać wartości ADU i powiązanych buforów w zależności od potrzeb, na podstawie danych o rzeczywistym zużyciu i/lub zaktualizowanych prognoz. Ta procedura dotyczy tylko tych elementów, w których zdecydowałeś się pozwolić systemowi na [automatyczne obliczanie stref buforowych](#set-up-buffers).

Wykonaj poniższe kroki, aby zaplanować automatyczne obliczanie wartości bufora.

1. Przejdź do **Planowanie główne \> Planowanie główne \> DDMRP \> Obliczanie wartości buforów**.
1. W oknie dialogowym **Obliczanie wartości buforów** ustaw następujące pola:

    - **Obliczaj średnie dzienne zużycie** – Ustaw tę opcję na *Tak*, aby obliczyć ponownie ADU elementów punktu rozłącznego przy każdym uruchomieniu zadania. Ustaw dla niego wartość *Nie*, aby pominąć to obliczenie. Zazwyczaj dla tej opcji należy ustawić wartość *Tak*.
    - **Obliczanie odłączonego czasu realizacji zamówienia** – Ustaw tę opcję na *Tak*, aby obliczać ponownie odłączony czas realizacji zadania przy każdym jego uruchomieniu. Ustaw dla niego wartość *Nie*, aby pominąć to obliczenie. Zazwyczaj dla tej opcji należy ustawić wartość *Tak*.
    - **Oblicz wartości buforowe** – Ustaw tę opcję na wartość *Tak*, aby ponownie obliczyć wartości buforowe przy każdym uruchamiam zadania. Ustaw dla niego wartość *Nie*, aby pominąć to obliczenie. Zazwyczaj dla tej opcji należy ustawić wartość *Tak*.
    - **Akceptuj obliczenia dla min, maks i punktu porządku** - Ustaw tę opcję na *Tak*, aby automatycznie zatwierdzać i stosować przeliczone wartości buforów przy każdym uruchomieniu zadania. Ustaw wartość *Nie*, aby ponownie przeliczone wartości niestosowane. W tym przypadku przeliczone wartości nie wejdą w życie, chyba że ktoś ręcznie zastosuje je później na stronie **Pokrycie artykułu** każdego produktu. Zazwyczaj dla tej opcji należy ustawić wartość *Tak*.
    - **Plan główny** — Wybierz plan główny, który zawiera elementy, na które będą miały wpływ obliczenia. Obliczenia zostaną zastosowane do wszystkich elementów w filtrze planu, który zostanie dodatkowo ograniczony przez ustawienia **Filtr** w tym oknie dialogowym.

1. Aby ograniczyć zestaw rekordów, na których ma być uruchomione to zadanie wsadowe, na karcie **Rekordy do uwzględnienia** wybierz **Filtr**, aby otworzyć okno dialogowe **Zapytanie**. To okno dialogowe działa tak samo jak w przypadku innych typów [zadań w tle](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** określ, jak, kiedy i jak często mają być wykonywane wybrane obliczenia dla zaznaczonych elementów. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz **OK**, aby dodać nowe zadanie do kolejki zadań do wykonania.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Przejrzyj i oblicz ponownie czasy realizacji dla wszystkich pozycji

Wykonaj poniższe kroki, aby przejrzeć i ponownie obliczyć wszystkie czasy realizacji zamówienia, które są dostępne w twojej jednostce prawnej (firmie).

1. Przejdź do **Planowanie główne \> Planowanie główne \> DDMRP \> Odłączony czas realizacji**.
1. Na stronie **Odłączony czas realizacji zamówienia** przeglądaj i filtruj listę w zależności od potrzeb, aby znaleźć informacje, których szukasz. Aby zobaczyć jeszcze więcej informacji o danym elemencie, wybierz jego łącze w kolumnie **Numer artykułu**.
1. Jeśli chcesz ponownie obliczyć czas realizacji zamówienia dla dowolnego elementu, zaznacz ten element, a następnie wybierz **Obliczanie czasu realizacji zamówienia** na pasku akcji. Zostanie wyświetlone okno dialogowe **Obliczanie czasu realizacji zamówienia**. To okno dialogowe działa tak samo, jak wtedy, gdy [obliczasz czasy realizacji](#calc-lead-time) dla tego samego artykułu na stronie **Zapotrzebowanie na produkty**.
