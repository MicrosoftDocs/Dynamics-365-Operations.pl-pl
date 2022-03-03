---
title: Zaakceptuj zamówienia planowane
description: W tym temacie wyjaśniono sposób ustalania zamówień planowanych. Podczas ustalania zamówień planowanych są one przekształcane w rzeczywiste zamówienia zakupu, zamówienia przeniesienia lub zlecenia produkcyjne.
author: ChristianRytt
ms.date: 04/22/2021
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7e3a86e2aa0e7182f7f9e853b9e8667e677a8ad6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102720"
---
# <a name="firm-planned-orders"></a>Zaakceptuj zamówienia planowane

[!include [banner](../../includes/banner.md)]

Zamówienia planowane muszą zostać *ustalone* (czyli zwolnione) w procesie planowania głównego. Podczas ustalania zamówień planowanych są one przekształcane w rzeczywiste zamówienia zakupu, zamówienia przeniesienia lub zlecenia produkcyjne. Zamówienia te są również znane jako zamówienia *zwolnione* lub *otwarte*.

Istnieją trzy metody ustalania zamówień planowanych:

- **Ręczne ustalanie** — należy wybrać określone zamówienia planowane z listy, a następnie ręcznie rozpocząć proces.
- **Automatyczne ustalanie** — służy do definiowania domyślnego horyzontu czasowego dla grup zapotrzebowania, pojedynczych towarów oraz kombinacji towarów i planów głównych. Następnie, podczas planowania głównego, zamówienia planowane będą automatycznie ustalane, jeśli data zamówienia znajduje się w podanym horyzoncie czasowym dla ustalania.
- **Ustalanie oparte na kwerendzie** — umożliwia zdefiniowanie kwerendy w celu wybrania zamówień planowanych na podstawie ich właściwości. Można skonfigurować zadanie wsadowe w celu regularnego uruchamiania kwerendy i ustalania spełniających warunki zamówień.

W tym temacie opisano szczegółowo poszczególne metody.

## <a name="enable-the-features-that-are-described-in-this-topic"></a><a name="enable-features"></a>Włączanie funkcji opisanych w tym temacie

Większość funkcji zamówienia planowanego jest dostępna we wszystkich standardowych instalacjach rozwiązania Microsoft Dynamics 365 Supply Chain Management, które korzystają z optymalizacji planowania. Jednak kilka funkcji opisanych w tym temacie musi zostać włączonych w module Zarządzanie funkcjami, aby można ich było używać.

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>Włącz lub wyłącz równoległe potwierdzanie planowanych zamówień

Równoległe ustalanie pomaga przyspieszyć proces ustalania przez przeprowadzanie go równolegle w wielu wątkach. Takie podejście może być przydatne, jeśli jest ustalanych wiele zamówień planowanych. Aby można było korzystać z tej funkcji, w systemie musi być włączona funkcja *Równoległe oznaczanie zamówień planowanych*. Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli korzystasz z wersji starszej niż 10.0.25, możesz włączyć lub wyłączyć tę funkcję, przechodząc do [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i wyszukując funkcję *Równoległe usztywnianie planowanych zleceń*.

### <a name="enable-planned-order-firming-with-filtering"></a>Włączanie ustalania zamówień z filtrowaniem

Ustalanie zamówień planowanych z filtrowaniem umożliwia określenie logicznych kryteriów wybierania zamówień planowanych do ustalenia. Można także wyświetlić podgląd wybranych zamówień planowanych, uruchomić proces w tle i/lub zaplanować je jako zadanie wsadowe.

Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując *Planowane ustalanie zamówień z funkcją filtrowania* w obszarze roboczym [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="enable-auto-firming-for-planning-optimization"></a>Włączanie automatycznego ustalania dla optymalizacji planowania

Funkcja automatycznego ustalania umożliwia ustalanie zamówień planowanych w ramach procesu planowania głównego w okresie horyzontu czasowego ustalania. Automatyczne ustalanie jest zawsze obsługiwane przez aparat planowania wbudowany w module Supply Chain Management. Aby jednak używać go również w przypadku optymalizacji planowania, należy włączyć tę funkcję.

Aby udostępnić tę funkcję w systemie, przejdź do modułu [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Automatyczne ustalanie dla optymalizacji planowania*. (Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona)

## <a name="manually-firm-planned-orders"></a>Ręczne ustalanie planowanych zamówień

Aby ręcznie ustalić zamówienia planowane, należy znaleźć i wybrać zamówienia planowane, które mają zostać ustalone, a następnie ręcznie proces ustalania.

1. [Otwórz stronę z listą zamówień planowanych](approved-planned-order.md#view-planned-orders).
1. Aby znaleźć szukane planowane zamówienia, filtrując i sortując listę, użyj pól **Filtr**, **Plan** i nagłówków kolumn.
1. Zaznacz pole wyboru przy każdym zamówieniu planowanym, które chcesz ustalić. Jeśli chcesz ustalić wszystkie planowane zamówienia, które są obecnie wymienione na stronie (na podstawie zastosowanych filtrów), pomiń ten krok.
1. W okienku akcji kliknij jeden z następujących przycisków:

    - **Ustal** — ustalenie tylko wybranych zamówień planowanych.
    - **Ustal wszystko** — ustalenie wszystkich zamówień planowanych, które są obecnie wymienione na stronie (na podstawie zastosowanych filtrów), niezależnie od zaznaczonych pól wyboru. Ta opcja może być przydatna w przypadku ustalania wielu zamówień planowanych.

1. W oknie dialogowym **Ustalanie** na skróconej karcie **Parametry** ustaw następujące pola. (Wiele z tych pól ma wartości domyślne z karty **Standardowa aktualizacja** na stronie **Parametry planowania głównego**).

    - **Aktualizacja zaznaczenia** — Umożliwia wybranie zasad dotyczących zaznaczania zapasów, które będą używane podczas ustalania zamówień planowanych.
    - **Zatrzymaj ustalanie w przypadku wystąpienia błędu** — ustaw dla tej opcji wartość *Tak*, aby zatrzymać ustalanie wszystkich wybranych zamówień planowanych w przypadku wystąpienia błędu w jednym z nich. Dla tej opcji musi być ustawiona wartość *Nie*, jeśli w opcji **Równoległe ustalanie** jest ustawiona wartość *Tak*.
    - **Równoległe ustalanie** – Ta opcja jest dostępna tylko w przypadku, gdy w systemie jest włączona [funkcja *Równoległe ustalanie zamówień planowanych*](#enable-features) i jeśli wybrano co najmniej dwa zamówienia planowane do ustalenia. Ustaw dla niej wartość *Tak*, aby równolegle uruchamiać procesy ustalania. Równoległe ustalanie może zwiększyć wydajność.
    - **Liczba wątków** – Ta opcja jest dostępna tylko w przypadku, gdy w systemie jest włączona [funkcja *Równoległe ustalanie zamówień planowanych*](#enable-features) i jeśli dla opcji **Równoległe ustalanie** wybrano wartość *Tak*. Wprowadź liczbę wątków do zastosowania w celu równoległego przeprowadzania procesu ustalania. Aby uzyskać więcej informacji na temat używania tej opcji w planowaniu głównym, zobacz temat [Poprawa wydajności planowania głównego](../master-planning-performance.md#number-of-threads).

        > [!NOTE]
        > Wartość *0* (zero) w polu **liczba wątków** wydłuża czas wykonywania planowania głównego. Dlatego zalecamy, aby zawsze określić wartość większą niż 0 w tym polu.

    - **Grupuj według dostawców** – Ustaw tę opcję na wartość *Tak*, aby podczas ich grupowania pogrupować planowane zamówienia zakupu i utworzyć jedno zamówienie zakupu dla każdego dostawcy. Alternatywą jest utworzenie jednego zamówienia zakupu, w którym każdemu planowanemu zamówieniu odpowiadałby jeden wiersz.
    - **Grupowanie wg grupy kupców** — Ustawienie tej opcji na *Tak* spowoduje, że planowane zamówienia zakupu zostaną pogrupowane w celu utworzenia jednego zamówienia zakupu łączącego dostawcę i grupę kupców. Aby skorzystać z tej opcji, należy też ustawić opcję **Grupuj wg dostawców** na *Tak*.
    - **Grupuj według umów zakupu** – ustaw tę opcję na wartość *Tak*, aby zgrupować planowane zamówienia zakupu, które mają tego samego dostawcę co istniejące umowy zakupu i utworzyć jedno zamówienie zakupu na umowę zakupu. Ta opcja jest włączona automatycznie, gdy włączono opcję **Grupuj według dostawców**. Aby użyć przycisku **Grupuj według umowy zakupu**, na stronie **Parametry planowania głównego** opcja *Znajdź umowę zakupu* musi mieć wartość **Tak**.
    - **Grupuj według okresów** (w sekcji **Zamówienia zakupu**) — umożliwia wybór okresu, według którego mają być grupowane planowane zamówienia zakupu. Aby skorzystać z tej opcji, należy też zaznaczyć opcję **Grupuj wg dostawcy**.
    - **Grupuj według okresów** (w sekcji **Przeniesienia**) — umożliwia wybór okresu, według którego mają być grupowane planowane przeniesienia. Zamówienia zostaną pogrupowane na podstawie wartości **Z magazynu** i **Do magazynu**.

    > [!NOTE]
    > Każda z opcji „Grupuj wg” powoduje, że system konwertuje każde planowane zamówienie na wiersz w pojedynczym zamówieniu zakupu, które jest wynikiem grupowania.

    ![Skrócona karta Parametry w oknie dialogowym Ustalanie.](./media/manual-firming.png "Skrócona karta Parametry w oknie dialogowym Ustalanie")

1. Na skróconej karcie **Uruchom w tle** skonfiguruj zadanie, tak aby działało w trybie wsadowym. Jednak w przypadku ręcznego ustalania nie ma sensu konfigurowanie harmonogramu cyklicznego. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management. Jednak w przypadku ręcznego ustalania zadanie wsadowe będzie przetwarzać tylko aktualnie wybrane zamówienia planowane. Nie będzie przetwarzać żadnych zamówień, które pasują do filtrów, które są obecnie stosowane na stronie.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i wygenerować ustalone zamówienia.

## <a name="auto-firm-planned-orders"></a>Automatyczne ustalanie zamówień planowanych

Funkcja automatycznego ustalania umożliwia ustalanie zamówień planowanych w ramach procesu planowania głównego. Można określić horyzont czasowy dla grup zapotrzebowania, pojedynczych towarów oraz kombinacji towarów i planów głównych. Następnie, podczas planowania głównego, zamówienia planowane będą automatycznie ustalane, jeśli data zamówienia znajduje się w podanym horyzoncie czasowym dla ustalania. Zamówienia planowane generowane przez optymalizację planowania oraz wbudowaną operację planowania głównego różnie postępują z datą zamówienia (to jest datą rozpoczęcia).

> [!NOTE]
> Aby możliwe było automatyczne ustalanie planowanych zamówień zakupu, towary muszą być skojarzone z dostawcą.
> 
> Zamówienia pochodne (czyli zamówienia podwykonawcze), które są ustalone, będą miały status *W trakcie przeglądu*, gdy włączone jest śledzenie zmian.

> [!IMPORTANT]
> Aby funkcja opisana w tej sekcji była dostępna dla funkcji Optymalizacja planowania, w systemie musi być włączona [funkcja *Automatyczne ustalanie dla optymalizacji planowania*](#enable-features), zgodnie z opisem na początku tego tematu. Automatycznego ustalania można zawsze używać z wbudowanym aparatem planowania głównego.

### <a name="auto-firming-with-planning-optimization-vs-the-built-in-planning-engine"></a>Automatyczne ustalanie z funkcją Optymalizacja planowania w porównaniu z wbudowanym aparatem planowania

Zarówno Optymalizacja planowania, jak i wbudowany aparat planowania, mogą być używane do automatycznego ustalania zamówień planowanych. Istnieją jednak pewne ważne różnice. Na przykład w optymalizacji planowania jest używana Data zamówienia (to znaczy Data rozpoczęcia) w celu ustalenia, które zamówienia planowane mają zostać ustalone, a wbudowany aparat planowania używa daty zapotrzebowania (czyli daty zakończenia). W poniższej tabeli podsumowano różnice.

| Funkcja | Optymalizacja planowania | Wbudowany aparat planowania |
|---|---|---|
| **Podstawa daty** | Automatyczne ustalanie jest oparte na dacie zamówienia (Data początkowa). | Automatyczne ustalanie jest oparte na dacie zapotrzebowania (Data końcowa). |
| **Czas realizacji** | Ponieważ Data zamówienia (Data początkowa) wyzwala akceptację, nie trzeba brać pod uwagę czasu realizacji w ramach horyzontu czasowego ustalania. | W celu zagwarantowania punktualnego ustalania zamówień horyzont czasowy ustalania musi być dłuższy niż czas realizacji. |
| **Zamówienia na bieżący tydzień** | Aby ustalić wszystkie zamówienia, które muszą się rozpoczynać w bieżącym tygodniu, horyzont czasowy ustalania musi wynosić jeden tydzień. | Aby ustalić wszystkie zamówienia, które muszą się rozpoczynać w bieżącym tygodniu, horyzont czasowy ustalania musi wynosić czas realizacji plus jeden tydzień. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Konfigurowanie automatycznego ustalania i horyzontu czasowego ustalania

Automatyczne ustalanie można włączyć, przypisując horyzont czasowy automatycznego ustalania dla odpowiedniej konfiguracji zapotrzebowania, zgodnie z opisem w dalszej części tej sekcji. Jeśli automatyczne ustalanie nie jest włączone dla żadnej konfiguracji zapotrzebowania lub planowanie zostało rozpoczęte z określonej strony, na przykład strony **Zapotrzebowania netto** dla zwolnionego produktu, proces automatycznego ustalania jest pomijany.

Opcje grupowania i zaznaczania dla automatycznego ustalania pobierają wartości z karty **Standardowa aktualizacja** na stronie **Parametry planowania głównego**.

Horyzont czasowy automatycznego ustalania jest definiowany przez liczbę dni określoną dla odpowiedniej konfiguracji zapotrzebowania. Automatyczne ustalanie można włączyć i horyzont czasowy można kontrolować w następujący sposób:

- Aby zdefiniować domyślny horyzont czasowy ustalania dla grupy zapotrzebowania, należy przejść do **Planowanie główne \> Ustawienia \> Zapotrzebowanie \> Grupy zapotrzebowania** i wybrać grupę zapotrzebowania. Następnie, na skróconej karcie w **Inne**, w polu **automatyczny horyzont czasowy akceptacji (dni)** wprowadź liczbę dni.
- Aby zastąpić ten horyzont czasowy ustalania, który został zdefiniowany dla grupy zapotrzebowania na określony towar, przejdź do **Zarządzanie informacjami o produktach \> Zwolnione produkty**. W okienku akcji wybierz opcję **Plan**, a następnie pozycję **Zapotrzebowanie na towary**. Na karcie **Ogólne** wybierz opcję **Zastąp horyzont czasowy**, a następnie w polu **automatyczny horyzont czasowy akceptacji (dni)** wprowadź liczbę dni.
- Aby zastąpić horyzont czasowy ustalania, który jest zdefiniowany dla grupy zapotrzebowania i zapotrzebowania na towary dla określonego planu głównego, należy przejść do **Planowanie główne \> Ustawienia \> Plany główne** i wybrać plan główny. Następnie, na skróconej karcie w **Horyzont czasowy w dniach**, ustaw opcję **Akceptacja** na wartość *Tak* wprowadź liczbę dni.

Jeśli dla wszystkich wcześniej wymienionych horyzontów czasowych zostanie ustawiona wartość *0* (zero), automatyczne ustalanie zostanie wyłączone dla odpowiednich towarów.

## <a name="firm-planned-orders-by-using-a-query"></a>Ustalanie zamówień planowanych przy użyciu zapytania

Ustalanie oparte na zapytaniu umożliwia planowanie ustalania na podstawie wcześniej zdefiniowanych kryteriów. W przeciwieństwie do automatycznego ustalania, proces ustalania oparty na zapytaniu umożliwia automatyczne ustalanie różnych podzestawów zamówień w różnych punktach w czasie. Ponadto można używać operacji ręcznych lub automatycznych do określania różnych typów zamówień planowanych. Można także sprawdzić w podglądzie, które zamówienia są wybierane na podstawie ustawień. W związku z tym można potwierdzić, że wybór spełnia oczekiwania.

Automatyczne ustalanie można łączyć z ustalanie opartymi na zapytaniu. Na przykład zadanie ustalania oparte na zapytanie ma przyszły horyzont czasowy dłuższy niż horyzont czasowy pasującej konfiguracji zapotrzebowania automatycznego ustalania. W związku z tym zadanie ustalania oparte na zapytaniu będzie przetwarzać jego zamówienia planowane przed uruchomieniem automatycznego ustalania. Dzięki temu można zaplanować zamówienia dla określonych dostawców inaczej niż zamówienia podobnych produktów od innych dostawców.

> [!IMPORTANT]
> Aby można było korzystać z funkcji opisanej w tej sekcji, [funkcja *Ustalanie zamówień planowanych z filtrowaniem*](#enable-features) musi być włączona w systemie, zgodnie z opisem na początku tego tematu.

Aby ustalić zamówienie planowane za pomocą procesu ustalania opartego na zapytaniu, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Uruchom \> Ustalanie zamówienia planowanego**.
1. W oknie dialogowym **Ustalanie zamówień planowanych**, na skróconej karcie **Parametry** ustaw podstawowe opcje przetwarzania, zaznaczania i grupowania. Te opcje działają w ten sam sposób, jak w oknie dialogowym **Ustalanie**. (Opisy znajdują się w poprzedniej sekcji) Następnie w sekcji **Plan** należy ustawić następujące pola, które są unikatowe w oknie dialogowym **Ustalanie zamówienia planowanego**:

    - **Plan** — umożliwia wybór planu głównego, który ma być stosowany podczas ustalania zamówień planowanych znalezionych przez to zapytanie.
    - **Dni naprzód horyzontu czasowego ustalania** — można określić, jak daleko w przyszłości mają być obliczane różne zapotrzebowania i inne aspekty w planowaniu głównym.
    - **Dni wstecz horyzontu czasowego ustalania** — można określić, jak daleko w przeszłości mają być obliczane różne zapotrzebowania i inne aspekty w planowaniu głównym.

    ![Skrócona karta Parametry w oknie dialogowym Ustalanie zamówienia planowanego.](./media/planned-order-firming-main-1.png "Skrócona karta Parametry w oknie dialogowym Ustalanie zamówienia planowanego")

1. Aby określić, które rekordy powinny zostać uwzględnione w zamówieniu, należy wybrać przycisk **Filtr** na skróconej karcie **Rekordy do uwzględnienia**. Zostanie wyświetlone standardowe okno dialogowe zapytania, w którym można definiować kryteria wyboru, kryteria sortowania i sprzężenia. Pola działają w ten sam sposób, jak działają w przypadku innych typów zapytań w module Supply Chain Management. Pola w tym miejscu są tylko do odczytu i pokazują wartości, które są powiązane z zapytaniem.

    ![Skrócona karta Rekordy do uwzględnienia w oknie dialogowym Ustalanie zamówienia planowanego.](./media/planned-order-firming-main-2.png "Skrócona karta Rekordy do uwzględnienia w oknie dialogowym Ustalanie zamówienia planowanego")

1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd zawartości ustalanego zamówienia wybranego na podstawie do tej pory wybranych ustawień. Zostanie wyświetlona jako komunikat lista zamówień planowanych, które zostaną ustalone. Ustawienia można dostosowywać zgodnie z potrzebą, dopóki w podglądzie nie zostanie wyświetlone ustalone zamówienie zgodnie z zamysłem.

    ![Przykład podglądu ustalonego zamówienia.](./media/planned-order-firming-preview.png "Przykład podglądu ustalonego zamówienia")

    > [!WARNING]
    > Ta funkcja spowoduje ustalenie wszystkich zamówień planowanych spełniających kryteria filtrowania. Bezkrytyczne ustalanie zamówień planowanych może spowodować, że będą tworzone niepożądane zamówienia zakupu i przeniesienia oraz zlecenia produkcyjne. Przed kontynuowaniem zawsze używaj przycisku **Podgląd**, aby sprawdzić poprawność uwzględnionych rekordów.

1. Na skróconej karcie **Uruchom w tle** skonfiguruj zadanie, tak aby działało w trybie wsadowym i/lub skonfiguruj harmonogram cykliczny. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i wygenerować ustalone zamówienia.

## <a name="track-firmed-orders"></a>Śledzenie ustalonych zamówień

Aby śledzić zamówienie planowane, które zostało ustalone, należy wykonać następujące kroki.

1. [Otwórz stronę z listą zamówień planowanych](approved-planned-order.md#view-planned-orders).
1. Otwórz lub wybierz planowane zamówienie, które chcesz śledzić.
1. W okienku akcji, na karcie **Widok** w grupie **Widok** wybierz **Historia ustalania**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
