---
title: Zaawansowane tworzenie ładunku podczas grupy czynności
description: Ten artykuł zawiera informacje dotyczące zaawansowanego tworzenia ładunku podczas grupy czynności, które automatycznie przypisuje wysyłki do istniejących grup czynności w trakcie ich wykonywania. Dzięki temu można tworzyć znaczące ładunki odpowiadające ciężarówkom bez konieczności używania pulpitu planowania wysyłki ładunku.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod,WHSWaveTemplateTable,WHSLoadMixGroup,WHSLoadBuildTemplate, WHSWaveTableListPage, TMSLoadBuildTemplateApply, TMSLoadBuildTemplates, TMSLoadBuildTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c9d41645531fa4318289f32a564c34f0f92681df
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335864"
---
# <a name="advanced-load-building-during-wave"></a>Zaawansowane tworzenie ładunku podczas grupy czynności

[!include [banner](../includes/banner.md)]

Zaawansowanego tworzenie automatycznie przypisuje wysyłki do istniejących grup czynności w trakcie ich wykonywania. Dzięki temu można tworzyć znaczące ładunki odpowiadające ciężarówkom bez konieczności używania pulpitu planowania wysyłki ładunku. Ta funkcja jest przydatna w firmach, które chcą używać koncepcji ładunków do śledzenia i planowania wysyłki towarów w ciężarówkach lub na przyczepach, ale nie chcą ręcznie tworzyć codziennie tych ładunków.

Podczas przetwarzania grupy czynności system zwykle tworzy nowy ładunek dla każdej wysyłki, do której nie jest przypisane żadne obciążenie. Jeśli jednak jest włączona funkcja tworzenia zaawansowanego grup czynności ładunku, system przypisuje każdą nieprzypisana wysyłkę do istniejącego ładunku (jeśli istnieje odpowiednia opłata ładunku), a nowe ładunki są tworzone tylko wtedy, gdy jest to wymagane. Zaawansowane tworzenie grup czynności ładunku powoduje automatyczne utworzenie nowych ładunków na podstawie zdefiniowanych kryteriów.

Aby można było skorzystać z tej funkcji, należy skonfigurować system w następujący sposób:

- Utwórz *Szablony grupy czynności*, które zawierają nową metodę **buildLoads**. Ta metoda pozwala na zaawansowane tworzenie ładunków dla grup czynności, które korzystają z tych szablonów.
- Skonfiguruj *Szablony kompilacji ładunku*, z których każdy będzie połączony z określonym szablonem i metodą grupy czynności. Załaduj kontrolę szablonów kompilacji ładunku, które ładują wiersze ładunku (istniejące lub nowe), które znajdują się w ramach grupy czynności lub są dodawane. Można łączyć lub oddzielać wysyłki, opierając się na kryteriach, takich jak szablon ładunku, sprzęt i inne wartości pól w wierszu ładunku.
- Określ *grupy mieszanek ładunków* w celu określenia, które przedmioty powinny i nie powinny być łączone w pojedynczym ładunku. Można również określić, czy w ograniczeniu ma być generowane ostrzeżenie, czy błąd, oraz określić, czy należy ocenić ograniczenie objętościowe szablonu ładunku.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>Włącz zaawansowane tworzenie ładunku podczas grupy czynności w systemie

Aby można było korzystać z funkcji zaawansowanego tworzenia ładunku podczas grupy czynności, funkcja ta musi być włączona dla systemu. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** te funkcje widnieją jako:

- Funkcja tworzenia ładunku w grupie czynności:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcji:** *Funkcja tworzenia ładunku w grupie czynności*

- Kod kroku grupy czynności dotyczący całej organizacji:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcji:** *Kod kroku grupy czynności dotyczący całej organizacji*

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tym scenariuszem pokazowym przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tego scenariusza pokazowego można również używać jako wskazówek dotyczących tej funkcji podczas pracy w produkcji. Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Sprawdź, czy konfiguracja scenariusza zawiera wystarczające dostępne zapasy

Podczas pracy z danymi demonstracyjnymi **USMF** należy najpierw upewnić się, że system jest skonfigurowany tak, że w każdej lokalizacji pobrania znajduje się odpowiednia ilość zapasów. W przypadku tego scenariusza demonstracyjnego oczekuje się, że zapasy są dostępne w magazynie *62*:

- **A0001:** 10 sztuk
- **A0002:** 10 sztuk
- **M9200:** 10 ea

Do magazynu należy dodać pozycję **M9200**. Aby dodać towar, należy wykonać procedury opisane w poniższych podsekcjach.

#### <a name="create-a-new-license-plate-id"></a>Tworzenie nowego identyfikatora numeru identyfikacyjnego

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Lokalizacje**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nowym wierszu w polu **NUmer identyfikacyjny** wprowadź *LP6203*.
1. Wybierz opcję **Zapisz**.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Utwórz koszt standardowy dla pozycji M9200 w oddziale 6

1. Przejdź do **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.
1. Wyszukaj **M9200**.
1. Zaznacz wiersz towaru, a następnie w okienku akcji na karcie **Zarządzanie kosztami** w grupie **Konfiguracja** wybierz opcję **Cena towaru**.
1. Na stronie **Cena towaru** wybierz kartę **Oczekiwane ceny**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nowym wierszu ustaw następujące wartości:

    - **Typ ceny:** *Koszt planowany*
    - **Typ ceny:** *Koszt*
    - **Wersja:** *10*
    - **Oddział:** *6*
    - **Cena:** *1.60*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Aktywowanie oczekiwanych cen**.
1. Wybierz kartę **Aktywne ceny**, aby sprawdzić, czy dodano nowy koszt własny dla oddziału *6*.

#### <a name="create-inventory-in-warehouse-62"></a>Tworzenie zapasów w magazynie 62

1. Kliknij kolejno opcje **Zarządzanie zapasami** \> **Wpisy w arkuszu** \> **Towary** \> **Korekta zapasów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym **Tworzenie arkusza magazynowego** na skróconej karcie **Przegląd** w polu **Magazyn** wprowadź wartość *62*. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Zostanie otwarta strona **Korekty zapasów**. Na skróconej karcie **Wiersze arkusza** wybierz **Nowe**, aby dodać wiersz.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Numer pozycji:** *M9200*
    - **Lokalizacja:** *Bulk-003*
    - **Ilość:** Zmień wartość na *10*.

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji kliknij przycisk **Weryfikuj**, aby sprawdzić pod kątem błędów.
1. W oknie dialogowym **Arkusz sprawdzania** wybierz **OK**, aby rozpocząć sprawdzanie. Po zakończeniu sprawdzania zostanie wyświetlony komunikat.
1. W okienku akcji wybierz opcję **Księguj**, aby zaksięgować zmianę zapasów.
1. W oknie dialogowym **Księgowanie arkusza** wybierz **OK**, aby rozpocząć księgowanie. Po zakończeniu księgowania zostanie wyświetlony komunikat.

## <a name="set-up-advanced-wave-load-building"></a>Konfiguracja funkcji Zaawansowane tworzenie ładunku podczas grupy czynności

### <a name="regenerate-wave-process-methods"></a>Ponowne generowanie metod procesu grupy czynności

Może być konieczne ponowne wygenerowanie metod przetwarzania grupy czynności, aby można było udostępnić metodę tworzenia ładunku (**buildLoads**).

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Grupy czynności** \> **Metody procesów grupy czynności**.
2. Sprawdź, czy **buildLoads** znajduje się na liście. Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.

### <a name="set-up-wave-templates"></a>Konfigurowanie szablonów grupy czynności

Aby wykorzystać zalety zaawansowanego tworzenia podczas grupy czynności, należy dołączyć metodę **buildLoads** do każdego odpowiedniego [szablonu grupy czynności](tasks/configure-wave-processing.md).

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Grupy czynności** \> **Szablony grupy czynności**.
1. Wybierz typ szablonu grupy czynności.

    Jeśli pracujesz z danymi demonstracyjnymi **USMF**, wybierz szablon **62 Domyślna wysyłka**.

1. W okienku akcji wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Na skróconej karcie **Metody** w siatce **Pozostałe metody** wybierz metodę **buildLoads**.
1. Korzystaj z przycisku Strzałka w prawo, aby przesunąć metodę **twórzŁadunki** na siatkę **Wybrane metody**.
1. Aby przypisać wartość **Kodu kroku grupy czynności** dla metody **buildLoads**, należy najpierw utworzyć kod na stronie **Kodów etapów grupy czynności**. Można użyć dowolnej wymaganej wartości, ale należy ją zanotować, ponieważ będzie ona potrzebna później. Aby utworzyć kod **WSC2112**, należy skorzystać z poniższych kroków:

    1. W wierszu metody **buildLoads** kliknij prawym przyciskiem myszy strzałkę w dół w polu **Kod kroku grupy czynności**, a następnie wybierz polecenie **Wyświetl szczegóły**.
    1. Na stronie **Kod kroku grupy czynności** w okienku akcji wybierz **Nowa**.
    1. W polu **Kod dyrektywy grupy czynności** wprowadź *WSC2112*.
    1. W polu **Opis dyrektywy grupy czynności** wprowadź *WSC2112*.
    1. W polu **Typ kroku grupy czynności** wybierz opcję *Tworzenie ładunku*.

1. Wybierz przycisk **Zapisz** i zamknij stronę.
1. W wierszu metody **buildLoads** w polu **Kod kroku grupy czynności** wybierz kod, który został właśnie utworzony (**WSC2112**).
1. Na okienku akcji wybierz opcję **Zapisz**.

> [!NOTE]
> Kody etapów grupy czynności są kodami, które użytkownicy mogą konfigurować i stosować w celu łączenia określonych wystąpień metod grupy czynności z odpowiednimi szablonami. Szablony te obejmują szablony uzupełniania, konteneryzacji, drukowania etykiet, kompilowania i sortowania.
>
> Jeśli nie są używane kody etapów grupy czynności, użytkownicy muszą wprowadzać dowolny tekst, aby odwoływać się do określonego szablonu z instancji metody Wave. Tekst niezależny jest podatny na błędy, ponieważ użytkownicy muszą upewnić się, że tekst etapu grupy czynności dodawany dla konkretnej metody w szablonie grupy czynności jest dokładnie zgodny z tekstem kroku grupy czynności w szablonie docelowym.
>
> Kody etapów grupy czynności dla konkretnego typu kroku są konfigurowane na osobnej stronie. Dla każdej instancji metody etapów grupy czynności, która wymaga kodu kroku grupy czynności, należy wybrać kod etapu grupy rozwijanej. Wybór na liście rozwijanej zastępuje wprowadzanie tekstu swobodnego i pomaga zmniejszyć ryzyko i wpływ błędu człowieka. Kody ustawień służą do łączenia metody kroku grupy czynności w szablonie grupy czynności z docelowym szablonem metody.

### <a name="set-up-load-mix-groups"></a>Konfigurowanie grup mieszania ładunków

Grupy mieszania ładunku ustanawiają reguły dotyczące typów towarów, które można łączyć w pojedynczym ładunku. Można skonfigurować dowolną liczbę grup mieszania ładunków. Jednak, aby można było skorzystać z zaawansowanego tworzenia ładunków podczas grup czynności, musi istnieć co najmniej jeden. Aby utworzyć mieszaną grupę ładunku, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Ładunek** \> **Grupy mieszania ładunków**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć grupę ładunku.
1. W polu **Identyfikator grupy mieszania ładunku** wprowadź opisową nazwę nowej grupy subskrypcji.

    Jeśli pracujesz z danymi demonstracyjnymi **USMF**, określ następujące wartości:

    - **Identyfikator grupy mieszania ładunku:** *TV*
    - **Opis:** *TV*

1. W okienku akcji wybierz opcję **Zapisz**, aby **Kryteria grupy mieszania ładunku** były dostępne na skróconej karcie.
1. Na skróconej karcie **Kryteria grupy mieszania ładunku** wybierz opcję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu określ żądane wartości w każdym polu. Te wartości decydują o grupach towarów uwzględnianych przy połączeniu z ładunkiem.

    Jeśli pracujesz z danymi demonstracyjnymi **USMF**, wybierz opcję *TV&Video* w polu **Grupa towarów**.

1. W okienku akcji wybierz opcję **Zapisz**, aby **Ograniczenia grupy mieszania ładunku** były dostępne na skróconej karcie.
1. Na skróconej karcie **Ograniczenia grupy mieszania ładunku** wybierz opcję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu określ żądane wartości w każdym polu.

    Jeśli pracujesz z danymi demonstracyjnymi **USMF**, określ następujące wartości:

    - **Grupa pozycji:** *CarAudio*
    - **Ładowanie akcji kompilacji:** *Ogranicz* (ta wartość spowoduje, że elementy należące do grupy pozycji **RadioSamochodowe** nie będą mogły być w tym samym ładunku co towary należące do grupy elementów **TV i wideo**).

1. Kontynuuj pracę z regułami, dopóki nie dodasz wszystkich wymaganych kryteriów i ograniczeń dotyczących grupy mieszania ładunku.

Jeśli pracujesz z danymi demonstracyjnymi **USMF**, teraz możesz zakończyć tę konfigurację.

### <a name="set-up-load-build-templates"></a>Ustaw szablony tworzenia ładunku

Można skonfigurować dowolną liczbę szablonów tworzenia ładunków. Jednak, aby można było skorzystać z zaawansowanego tworzenia ładunków podczas grup czynności, musi istnieć co najmniej jeden. Aby utworzyć szablon procesu, wykonaj poniższe czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Ładunek** \> **Szablony tworzenia ładunków podczas grup czynności**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości.

    | Pole | opis | Wartość w danych demonstracyjnych USMF |
    |---|---|---|
    | Identyfikator sekwencyjny | Kolejność, w jakiej szablon będzie oceniany. | *1* |
    | Nazwa szablonu kompilowania ładunku | Podaj unikatowy identyfikator szablonu kompilowania ładunku. Należy wprowadzić nazwę szablonu, który został utworzony lub zaktualizowany wcześniej w tej konfiguracji. | *62 Domyślna wysyłka* |
    | Kod kroku grupy czynności | Podaj kod kroku grupy czynności służący połączeniu szablonu z metodą grupy czynności. Należy wprowadzić kod wybrany dla metody **buildLoads** podczas konfigurowania szablonu grupy czynności wcześniej w tej konfiguracji. | *WSC2112* |
    | Identyfikator szablonu ładunku | Wybierz szablon ładunku, który ma być używany podczas tworzenia nowych ładunków u względem którego będzie wykonywane dopasowywanie podczas przypisywania do istniejących ładunków. Szablon ładunku określa maksymalną wagę i objętość, które są dozwolone dla całego ładunku. | *Standardowy szablon ładunku* |
    | Sprzęt | Sprzęt, względem którego będzie wykonywane dopasowywanie podczas przypisywania do istniejących ładunków i który będzie wypełniany przez nowo tworzone ładunki. | To pole należy pozostawić puste. |
    | Identyfikator grupy łączenia ładunków | Wybierz grupę łączenia ładunków, która będzie używana, jeżeli towar jest dozwolony w ładunku. Grupa mieszania ładunku ustanawia reguły dotyczące typów towarów, które można łączyć w pojedynczym ładunku. Należy wybrać jedną z grup mieszania utworzonych wcześniej w tej konfiguracji. | *TV* |
    | Użyj otwartych ładunków | Wybierz, czy należy dodawać do istniejących otwartych ładunków. Dostępne są następujące opcje:<ul><li>**Brak** – nie dodawaj ładunków otwartych do żadnych istniejących ładunków.</li><li>**Dowolnie** – spowoduje dodawanie do dowolnych istniejących ładunków prawidłowych dla wiersza.</li><li>**Przypisane** – dodaje otwarte ładunki do ładunku przypisanego do grupy czynności.</li></ul> | *Jakikolwiek* |
    | Utwórz ładunki | Określ, czy mają być tworzone nowe ładunki, jeśli istniejące ładunki nie odpowiadają kryteriom. | Zaznaczone (= *Tak*) |
    | Zezwalaj na podział wiersza wysyłki | Określ, czy zezwolić na rozdzielanie wiersza ładunku między wiele ładunków, jeżeli jego pełna wartość przekracza maksymalną pojemność szablonu ładunku. | Zaakceptowane (= *Nie*) |
    | Sprawdź poprawność ograniczeń wolumetrycznych | Określ, czy po włączeniu tej opcji w procesie kompilowania ładunku będą sprawdzane masa i objętość podczas dodawania każdego wiersza ładunku, tak aby zapobiec przekroczeniu limitów wolumetrycznych ustawionych w szablonie ładunku. | Zaakceptowane (= *Nie*) |

1. W okienku akcji wybierz opcję **Zapisz**, aby udostępnić opcję **Edytuj kwerendę**.
1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.
1. W polu dialogowym kwerendy, na karcie **Sortowanie** wybierz przycisk  **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu określ reguły sortowania, których chcesz użyć. Na przykład, aby posortować wyniki wyszukiwania w kolejności rosnącej według numeru porządkowego, należy określić następujące wartości:

    - **Tabela:** *Szczegóły ładunku*
    - **Tabela pochodna:** *Szczegóły ładunku*
    - **Pole:** *Numer zamówienia*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Wybierz przycisk **OK**, aby zapisać zmiany i zamknąć okno dialogowe.
1. Na skróconej karcie **Podział według** ustaw reguły określające sposób podziału ładunku. Zazwyczaj może się zdarzyć, że pola niestandardowe zostały rozszerzone na wiersz ładunku, takie jak **Trasa**, **Podróż** lub **Bieg**. Na przykład, aby utworzyć jeden ładunek według numeru zamówienia, zaznacz pole wyboru **Podział według** dla wiersza zawierającego następujące wartości:

    - **Nazwa tabeli odwołań:** *Szczegóły ładunku*
    - **Nazwa pola odwołania:** *Numer zamówienia*

## <a name="scenario"></a>Scenariusz

W tym scenariuszu przedstawiono sposób, w jaki ustawienia opisane wcześniej w tym artykule wpływają na operacje magazynowe w trakcie przetwarzania zamówienia sprzedaży. W tym scenariuszu używane są dane demonstracyjne **USMF** wraz z innymi wartościami demonstracyjnymi, które są dostępne w tych instrukcjach konfiguracyjnych.

### <a name="create-sales-orders"></a>Tworzenie zamówień sprzedaży

1. Przejdź kolejno do pozycji **Sprzedaż i marketing** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.
1. Wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe **Tworzenie zamówienia sprzedaży**.
1. W oknie dialogowym ustaw następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-007*.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**. W tym nowym wierszu ustaw pole **Numer pozycji** na wartość *A0001* oraz pole **Ilość** na *1*.
1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii**.
1. Następnie kliknij przycisk **Zamknij** – (**X**), znajdujący się w prawym górnym rogu, aby powrócić do strony zamówienia.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**. System tworzy wysyłkę i dodaje ją do nowego ładunku, ponieważ żaden z istniejących ładunków nie zawiera wierszy ładunku o tym numerze zamówienia.

    Użytkownik otrzymuje wiadomość, która zawiera identyfikator grupy czynności oraz identyfikatory wysyłki i pracy utworzone dla tego zamówienia sprzedaży.

1. Aby potwierdzić szczegóły ładunku, wysyłki i pracy w wierszu sprzedaży, zaznacz wiersz, a następnie w menu **Magazyn** powyżej siatki wybierz pozycję **Szczegóły ładunku**, **Szczegóły dotyczące wysyłki** lub **Szczegóły pracy**.
1. W nowo utworzonym zamówieniu sprzedaży, na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kolejny wiersz.
1. W tym nowym wierszu ustaw pole **Numer pozycji** na wartość *A0002* oraz pole **Ilość** na *1*.
1. Powtórz wiersze od 6 do 9, aby zarezerwować wiersz i zwolnić go do magazynu. System tworzy **nową** wysyłkę dla dodanego wiersza. Jednak w przypadku korzystania z funkcji Zaawansowane tworzenie ładunku podczas grupy czynności system dodaje tę wysyłkę i wiersz ładunku do istniejącej grupy czynności. Jeśli nie używasz funkcji Zaawansowanego tworzenie ładunku podczas grupy czynności, system utworzy nowy ładunek dla wysyłki.
1. W nowo utworzonym zamówieniu sprzedaży, na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kolejny wiersz.
1. W tym nowym wierszu ustaw pole **Numer pozycji** na wartość *M9200* oraz pole **Ilość** na *1*.
1. Powtórz wiersze od 6 do 9, aby zarezerwować wiersz i zwolnić go do magazynu. Tak jak wcześniej, system tworzy **nową** wysyłkę dla dodanego wiersza. Ponieważ jednak przedmiot pochodzi z grupy towarów **CarAudio**, **nie spełnia ograniczeń ustawionych dla grupy mieszania ładunków**. Dlatego jest **dodawany do nowego ładunku**. Jeśli grupa mieszania ładunku nie zostałaby określona w szablonie kompilacji ładunku, ta wysyłka zostałaby dodana do pierwszego ładunku.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]