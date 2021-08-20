---
title: Drukowanie etykiety grupy czynności
description: W tym temacie opisano drukowanie etykiet w grupie czynności i opisano sposób jego konfigurowania.
author: perlynne
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 3040406af731e2e35fff456804f893108e7eb896bfa0132082986c09ad128952
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777678"
---
# <a name="wave-label-printing"></a>Drukowanie etykiety grupy czynności

[!include [banner](../includes/banner.md)]

Drukowanie etykiet w grupie czynności jest alternatywnym podejściem do drukowania etykiet przez wprowadzenie nowej metody, która umożliwia tworzenie i drukowanie etykiet bezpośrednio z szablonu grupy czynności w trakcie wykonywania czynności typu grupy czynności. Dlatego etykiety będą już dostępne, zanim pracownicy uruchomili zlecenie produkcyjne na urządzeniu przenośnym. Pracownicy mogą następnie dołączać wymagane etykiety podczas pobierania, a nie po ich pobraniu.

Drukowanie etykiet w postaci grupy czynności jest używane w języku programowania Zebra (ZPL) do tworzenia układów etykiet. Układ etykiety jest podzielony na trzy sekcje (nagłówek, treść i stopka), co pozwala na tworzenie etykiet z powtarzającą się strukturą. Szablony etykiet grupy czynności informują system, który układ etykiety ma być używany. Użytkownicy mogą określać, która drukarka jest używana. Mogą również drukować etykiety na kilku drukarkach w tym samym czasie, w zależności od potrzeb. Na stronie **Historia etykiet grupy czynności** wyświetlany jest rekord wszystkich etykiet utworzonych za pomocą tej konfiguracji.

Etykiety można drukować i sortować na podstawie nagłówków pracy, można drukować etykiety podziału dla każdego nagłówka pracy, a także drukować etykiety zawartości kontenerów, etykiety przypadków i inne podobne etykiety.

> [!NOTE]
> Ta funkcja nie zastępuje istniejącej funkcji drukowania etykiet opartej na marszrucie dokumentów.

W przypadku drukowania etykiet grupy czynności dostępne są następujące udoskonalenia:

- Drukowanie etykiet zgodnie z liczbą kartonów w jednym wierszu pracy bez używania konteneryzacji. („Karton” oznacza jednostkę wyznaczoną w wierszach grupy sekwencji jednostek.)
- Umożliwia drukowanie kilku różnych sekwencji etykiet (np. etykiet kartonowych i palet).
- Uwzględnij wyliczenie etykiet (na przykład 1/124, 2/124,... 124/124) i zdefiniuj zakres wyliczenia (na przykład wiersz pracy, wiersz ładunku lub wysyłka).
- Utwórz i wydrukuj identyfikator list przewozowy na etykietach przed wygenerowaniem list przewozowy.
- Utwórz unikatowy numer kontenera wysyłkowego dla każdego kartonu (SSCC) i umieść go na każdej etykiecie.
- Umożliwia tworzenie sekwencji numerów zgodnych z GS1 dla identyfikatorów list przewozowych i kodów SSCC.
- Umożliwia ponowne wydrukowanie etykiet z obu urządzeń przenośnych i klienta wzbogaconego.
- Unieważnij etykiety (na przykład w krótkich scenariuszach pobrania) i wydrukuj je ponownie.
- Czyszczenie historii etykiety grupy czynności.
- Udoskonalenia układów rozsyłania dokumentów są udostępniane między układami rozsyłania dokumentów i układami etykiet grupy czynności. (Aby uzyskać więcej informacji, należy zapoznać się z tematem [Układ rozsyłania dokumentów dla numerów identyfikacyjnych](../warehousing/document-routing-layout-for-license-plates.md) .)

Te udoskonalenia zwiększają efektywność tworzenia etykiet kartonowych przed wyłożeniem na palety. Są one szczególnie korzystne dla firm dostarczanych do dużych sprzedawców, którzy automatycznie potwierdzają pokwitowania zamówień, skanując poszczególne kartony osobno.

> [!NOTE]
> Scenariusze konfiguracji opisane w tym temacie można zaimplementować oddzielnie lub w połączeniu, zależnie od wymagań biznesowych systemu. Istnieje możliwość projektowania kilku szablonów etykiet grupy czynności, które działają w sekwencji (jak w scenariuszu 3). Na przykład w scenariuszu 1 można drukować etykiety kartonów i scenariusz 2, aby drukować etykiety palet (jeśli palety w magazynie są różne w rozmiarach i składzie).

## <a name="turn-on-the-wave-label-printing-feature"></a>Włączanie funkcji drukowania etykiet grupy czynności

Aby móc używać funkcji *Drukowanie etykiet grupy czynności*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Drukowanie etykiet grup czynności*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>Scenariusz 1: Drukowanie etykiet grupy czynności, w którym jest generowana pojedyncza etykieta grupy czynności

W tym scenariuszu przedstawiono sposób, w jaki firma może drukować etykiety wysyłkowe dla dużego sprzedawców, które automatycznie potwierdzają pokwitowania zamówień, skanując każdy karton z osobna.

Ten scenariusz pokazuje przepływ końcowy na koniec.

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Upewnij się, że metoda etykiet grupy czynności jest dostępna

Może być konieczne ponowne wygenerowanie metod przetwarzania grupy czynności, aby można było udostępnić metodę drukowania etykiet grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.
1. Potwierdź, że **waveLabelPrinting** jest na liście. Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.

### <a name="configure-a-wave-template"></a>Skonfiguruj szablon grupy czynności

Szablony grupy czynności umożliwiają łączenie konkretnych instancji metod grupy czynności z odpowiednim szablonem etykiety grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. Wybierz szablon grupy czynności, na przykład **Domyślna 62-godzinna wysyłka**.
1. Na skróconej karcie **Metody** należy przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.
1. W kolumnie **Wybrane metody** wybierz metodę **Drukowania etykiet grupy czynności** i określ w polu **Kod kroku grupy czynności** wartość *PrintLabel*. Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Tworzenie układu etykiety grupy czynności

Układ etykiety decyduje o tym, jakie informacje są drukowane na etykiecie i w jaki sposób. W tym miejscu należy wprowadzić kod ZPL, który zostanie wysłany do drukarki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy etykiety grupy czynności**.
1. Dodaj rekord z następującymi ustawieniami:

    - **Identyfikator układu etykiety:** *Karton*
    - **Opis:** *Karton (SSCC)*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.

    Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**. W tym miejscu można skonfigurować dynamiczną część etykiety.

1. Dodaj wiersz z następującymi ustawieniami:

    - **Identyfikator wiersza:** *WaveLabel*
    - **Nazwa tabeli wierszy:** *WHSWaveLabel*
    - **Pozycja początkowa wiersza:** *0*

        To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.

    - **Wysokość wiersza:** *0*

        To pole definiuje wysokość każdego wiersza (w punktach) zgodnie ze standardem ZPL. Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych. Ponieważ w tym przykładzie występuje tylko jeden wiersz, można nadać mu wartość *0* (zero).

    - **Liczba wierszy na stronę:** *1*

        To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.

        > [!NOTE]
        > Ta konfiguracja spowoduje wydrukowanie osobnej etykiety ZPL dla każdego rekordu w tabeli etykiety grupy czynności.

1. Zamknij stronę.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Typ pracy*
    - **Kryteria:** *Pobranie*

    To zapytanie zapewnia, że na etykiecie będą drukowane tylko wiersze pracy typu pobranie, a nie typy wierszy pracy.

1. Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.
1. Zamknij okno dialogowe edytora zapytań.
1. Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**. W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka. Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści. Oto przykład.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki. Oto przykład.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety. Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii. Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.

Twoja etykieta jest teraz gotowa do użycia.

### <a name="create-a-wave-label-type"></a>Tworzenie typu etykiety grupy czynności

Typy etykiet grupy czynności służą do łączenia szablonów etykietek grupy czynności z jednostkami w wierszach grup sekwencji jednostek.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Typy etykiety grupy czynności**.
1. Dodaj typ etykiety grupy zynności z następującymi ustawieniami:

    - **Typ etykiety:** *Karton*
    - **Opis:** *Karton*

### <a name="set-up-unit-sequence-groups"></a>Ustaw grupy sekwencji jednostek

Następnie skonfiguruj grupę sekwencji jednostek dla typu etykiety grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Grupy sekwencji jednostek**.
1. Wybierz grupę **Każde Pudełko PL**.
1. W przypadku wiersza **Pudełko** należy określić wartość w polu **Typ poziomu grupy czynności** na *Karton*.

### <a name="create-a-wave-label-template"></a>Tworzenie szablonu etykiety grupy czynności

Następnie utwórz szablon etykiety grupy czynności dla typu etykiety grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Szablony etykiety grupy czynności**.
1. Dodaj szablon poziomu grupy czynności i określ następujące wartości w nagłówku:

    - **Nazwa szablonu etykiety:** *Etykiety kartonu*
    - **Opis:** *Etykiety kartonu*
    - **Kod kroku grupy czynności:** *PrintLabel*
    - **Magazyn:** *62*

1. Na skróconej karcie **Ogólne** należy określić wartość w polu **Typ etykiety grupy czynności** na *Karton*.
1. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj nowy wiersz o następujących ustawieniach:

    - **Identyfikator układu etykiety:** *Karton*
    - **Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.
    - **Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**. Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wysyłki*
    - **Tabela pochodna:** *Wysyłki*
    - **Pole:** *Numer konta*
    - **Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.

    Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.

1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edytora zapytań dla całego szablonu etykiety.
1. W oknie dialogowym edytora zapytań na karcie **Sortowanie** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Odwołanie do identyfikatora wiersza ładunku (identyfikator rekordu)*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Zostanie wyświetlone okno komunikatu z monitem o potwierdzenie operacji resetowania grup. Wybierz przycisk **Tak**, aby kontynuować.
1. W okienku akcji wybierz opcję **Grupa szablonu etykiety grupy czynności**.
1. W oknie dialogowym **Grupa szablonów etykiety grupy czynności** wybierz wiersz, w którym pole **Nazwa pola odwołania** ma wartość *Odwołanie do identyfikatora wiersza ładunku*, a następnie zaznacz pole wyboru **Identyfikator kompilacji etykiety** dla tego wiersza.

    > [!NOTE]
    > Ten Instalator utworzy jedną sekwencję etykiet („Karton 1 z X”) dla każdego wiersza ładunku w rzucie, niezależnie od konfiguracji grupowania pracy. Tę sekwencję etykiet można wydrukować w układzie etykiety.

### <a name="configure-number-sequence-extensions"></a>Konfigurowanie sekwencji identyfikatorów

Rozszerzenia sekwencji identyfikatorów kontrolują zgodność GS1 z określonymi sekwencjami identyfikatorów. Ta konfiguracja jest opcjonalna dla bieżącego scenariusza. Aby uzyskać więcej informacji i instrukcji konfiguracyjnych, zobacz [Konfigurowanie rozszerzeń sekwencji identyfikatorów](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Utwórz zamówienie sprzedaży i zwolnij je do magazynu

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *62*

1. Dodaj dwa wiersze zamówienia sprzedaży o następujących ustawieniach:

    - Wiersz zamówienia sprzedaży 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *9024*
        - **Jednostka:** *Każdy* (9024 Każdy = 376 Pudełko = 47 Paleta)

    - Wiersz zamówienia sprzedaży 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *9016*
        - **Jednostka:** *Każdy* (9016 Każdy = 322 Pudełko = 46 Paleta)

    > [!NOTE]
    > Podane tu towary i ilości są tylko przykładami. Muszą one mieć zdefiniowaną wcześniej zdefiniowaną jednostkę, dlatego dla nich musi zostać zdefiniowana odpowiednia konwersja jednostek z *Każdy* na *Pudełko* na *Paleta* oraz musi mieć zapas w magazynie *62*. Aby uzyskać więcej informacji, zajrzyj do [Jednostka miary i zasady składowania](unit-measure-stocking-policies.md).

1. Wybierz wiersz zamówienia sprzedaży 1. W sekcji **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacje**.
1. Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii** i zamknij stronę.
1. Powtórz kroki 4 i 5 dla wiersza zamówienia sprzedaży 2.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Występują wówczas następujące zdarzenia:

    - System przetwarza utworzoną wysyłkę za pomocą szablonu, który zawiera krok drukowania etykiety. Układ etykiety zostanie użyty do zdefiniowania formatu etykiety, a jego wynikiem będzie etykieta drukowana na drukarce wybranej w szablonie etykiety.
    - Etykiety grupy czynności są generowane i drukowane. Liczba etykiet będzie równa liczbie kartonów (w tym przykładzie 376 etykiet pudełek dla linii 1 i 322 etykiet pudełek dla linii 2).
    - Nowy identyfikator list przewozowy jest generowany dla wysyłek. Jeśli skonfigurowano rozszerzenia sekwencji identyfikatorów, identyfikatory etykiet grupy czynności są zgodne z formatem numerów **SSCC-18**. 

Etykiety grupy czynności można przeglądać i ponownie drukować z następujących stron. W okienku akcji na każdej stronie na karcie **Wysyłki**, w grupie **Informacje pokrewne** wybierz **Etykiety grupy czynności**.

- Wszystkie wysyłki \> Szczegóły wysyłki
- Wszystkie ładunki \> Szczegóły ładunku
- Wszystkie grupy czynności
- Etykiety grup czynności
- Historia etykiet grupy czynności

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>Scenariusz 2: Drukowanie etykiety grupy czynności do konteneryzacji (bez rekordów etykiet grupy czynności)

Ten scenariusz umożliwia drukowanie etykiet grup czynności w przypadku używania konteneryzacji do automatycznego dzielenia towarów na kartony i dlatego nie wymagają rekordu etykiety grupy czynności. W tym przypadku identyfikator kontenera pełni rolę symbolu zastępczego dla SSCC.

Oto główne różnice między tym scenariuszem a scenariuszem 1:

- **Szablony etykiet grupy czynności:** Nie będzie można wybrać typu etykiety grupy czynności w szablonie etykiety grupy czynności i nie będzie wymagane grupowanie kompilacji etykiet. W przeciwnym razie zostanie skonfigurowany szablon etykiety grupy czynności i łącze do szablonu grupy czynności w taki sam sposób, jak opisano w scenariuszu 1. Aby nie można było wygenerować etykiet grupy czynności, należy pozostawić pustą etykietę grupy czynności.
- **Układy etykiet grupy czynności:** Skonfiguruj ustawienia wiersza układu etykiety grupy czynności dla wierszy pracy zamiast rekordów etykiet. Należy skonfigurować ustawienie wiersza dla układu etykiety, używając tabeli **WHSWorkLine** zamiast tabeli **WHSWaveLabel**. Ustawienie **Wiersze na stronę** określa liczbę wierszy, jaką będzie miała sekcja treści. 

Ta konfiguracja jest również odpowiednia dla scenariuszy biznesowych, w których wiele różnych elementów jest pakowanych w jedno oznaczone pudełko lub na paletę, a ten proces pakowania można zdefiniować przez tworzenie pracy (na przykład praca grupowana według wysyłki).

Ten scenariusz pokazuje przepływ końcowy na koniec.

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Upewnij się, że metoda etykiet grupy czynności jest dostępna

Może być konieczne ponowne wygenerowanie metod przetwarzania grupy czynności, aby można było udostępnić metodę drukowania etykiet grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.
1. Potwierdź, że **waveLabelPrinting** jest na liście. Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.

### <a name="set-up-a-wave-template"></a>Konfigurowanie szablonu grupy czynności

Szablony grupy czynności umożliwiają łączenie konkretnych instancji metod grupy czynności z odpowiednim szablonem etykiety grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. Wybierz szablon grupy czynności, na przykład **Konteneryzacja 63**.
1. Na skróconej karcie **Metody** należy przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.
1. W kolumnie **Wybrane metody** wybierz metodę **Drukowania etykiet grupy czynności** i określ w polu **Kod kroku grupy czynności** wartość *PrintLabel*. Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Tworzenie układu etykiety grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy etykiety grupy czynności**.
1. Dodaj rekord z następującymi ustawieniami:

    - **Identyfikator układu etykiety:** *Karton*
    - **Opis:** *Karton (SSCC)*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.

    Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**. W tym miejscu można skonfigurować dynamiczną część etykiety.

1. Dodaj wiersz z następującymi ustawieniami:

    - **Identyfikator wiersza:** *WorkLine*
    - **Nazwa tabeli wierszy:** *WHSWorkLine*
    - **Pozycja początkowa wiersza:** *500*

        To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.

    - **Wysokość wiersza:** *-50*

        To pole definiuje wysokość każdego wiersza. Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych.

    - **Liczba wierszy na stronę:** *5*

        To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.

        > [!NOTE]
        > Ta konfiguracja będzie drukowała kilka etykiet ZPL dla pracy, gdzie każda strona może zawierać do pięciu wierszy pracy. Jeśli na przykład zostanie wydrukowana etykieta dla kontenera, który ma 12 wierszy, drukowane będą trzy etykiety. Aby wydrukować oddzielną etykietę dla każdego wiersza pobrania, należy nadać tej wartości wartość *1*.

1. Zamknij stronę.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Typ pracy*
    - **Kryteria:** *Pobranie*

1. Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.
1. Zamknij okno dialogowe edytora zapytań.
1. Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**. W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka. Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści. Oto przykład.

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki. Oto przykład.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety. Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii. Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.

Twoja etykieta jest teraz gotowa do użycia.

### <a name="create-a-wave-label-template"></a>Tworzenie szablonu etykiety grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Szablony etykiety grupy czynności**.
1. Dodaj szablon poziomu grupy czynności i określ następujące wartości w nagłówku:

    - **Nazwa szablonu etykiety:** *Etykiety kontenera*
    - **Opis:** *Etykiety kontenerów*
    - **Kod kroku grupy czynności:** *PrintLabel*
    - **Magazyn:** *63*

1. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj wiersz o następujących ustawieniach:

    - **Identyfikator układu etykiety:** *Kontener*
    - **Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.
    - **Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**. Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wysyłki*
    - **Tabela pochodna:** *Wysyłki*
    - **Pole:** *Numer konta*
    - **Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.

    Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.

### <a name="configure-number-sequence-extensions"></a>Konfigurowanie sekwencji identyfikatorów

Rozszerzenia sekwencji identyfikatorów kontrolują zgodność GS1 z określonymi sekwencjami identyfikatorów. Ta konfiguracja jest opcjonalna dla bieżącego scenariusza. Aby uzyskać więcej informacji i instrukcji konfiguracyjnych, zobacz [Konfigurowanie rozszerzeń sekwencji identyfikatorów](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Utwórz zamówienie sprzedaży i zwolnij je do magazynu

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *63*

1. Dodaj pięć wierszy zamówienia sprzedaży:

    - Wiersz zamówienia sprzedaży 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *10*

    - Wiersz zamówienia sprzedaży 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *20*

    - Wiersz zamówienia sprzedaży 3:

        - **Numer pozycji:** *L0006*
        - **Ilość:** *20*

    - Wiersz zamówienia sprzedaży 4:

        - **Numer pozycji:** *L0100*
        - **Ilość:** *40*

    - Wiersz zamówienia sprzedaży 5:

        - **Numer pozycji:** *L0101*
        - **Ilość:** *50*

    > [!NOTE]
    > Podane tu towary i ilości są tylko przykładami. Muszą mieć zapasy w określonym magazynie.

1. Wybierz wiersz zamówienia sprzedaży 1. W sekcji **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacje**.
1. Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii** i zamknij stronę.
1. Powtórz kroki 4 i 5 dla każdego dodatkowego wiersza zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Występują wówczas następujące zdarzenia:

    - System przetwarza utworzoną wysyłkę za pomocą szablonu, który zawiera krok drukowania etykiety. Układ etykiety zostanie użyty do zdefiniowania formatu etykiety, a jego wynikiem końcowym będzie etykieta z pięcioma wierszami drukowana na drukarce wybranej w szablonie etykiety.
    - Nowy identyfikator list przewozowy jest generowany dla wysyłek. Jeśli skonfigurowano rozszerzenia sekwencji identyfikatorów, identyfikatory etykiet grupy czynności są zgodne z formatem numerów **SSCC-18**. 

Etykiety te można ponownie wydrukować, przechodząc do **Zarządzanie magazynem \> Zapytania i raporty \> Historia etykiet grupy czynności**.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>Scenariusz 3: Drukowanie etykiety grupy czynności w przypadku etykiet wielowarstwowych

W tym scenariuszu przedstawiono sposób korzystania z funkcji drukowania etykiet grupy czynności, gdy procesy magazynowania wymagają kilku różnych warstw na etykietach wysyłkowych. Na przykład może być konieczne wydrukowanie oddzielnych etykiet dla kartonów i palet, a etykieta podziału może być drukowana dla całej wysyłki. Etykiety podziału to osobny typ etykiety, który może być używany jako separator między rolkami i kontenerami, takimi jak etykiety dla identyfikatora wysyłki i kodu kreskowego, dzięki czemu można łatwo posortować etykiety po wydrukowaniu.

Główna różnica między konfiguracją tego scenariusza a konfiguracją scenariusza 1, oprócz faktu, że etykiety podziału są włączone, to czy wiele typów etykiet grupy czynności musi być skojarzonych z szablonami etykiet i wierszy grup sekwencji jednostek. Aby wykonać tę konfigurację, należy skonfigurować następujące elementy w tym scenariuszu:

- **Metody przetwarzania grupy czynności:** Doszablonu grupy czynności należy oznaczyć metodę etykietowania metodą „powtarzalne” (czyli więcej razy), a następnie określić różne kody etapów.
- **Szablony etykiet grupy czynności:** Konfiguruje się szablony etykiet grupy czynności i łączy je z szablonem grupy czynności. Każdy szablon etykiety grupy czynności ma własny typ etykiety.
- **Układy etykiet grupy czynności:** Zostaną utworzone różne układy etykiet grupy czynności. Dla każdej „warstwy” etykiet zostanie oddzielny układ etykiety, a także układ etykiety podziału.

Ten scenariusz pokazuje przepływ końcowy na koniec.

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.

### <a name="set-up-a-wave-process-method"></a>Konfigurowanie metody przetwarzania grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.
1. Potwierdź, że **waveLabelPrinting** jest na liście. Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.
1. W przypadku metody **waveLabelPrinting** zaznacz pole wyboru **Spraw, aby metoda była powtarzalna**.

### <a name="set-up-a-wave-template"></a>Konfigurowanie szablonu grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
2. Wybierz szablon grupy czynności, na przykład **Domyślna 62-godzinna wysyłka**.
3. Na skróconej karcie **Metody** należy przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.
4. W kolumnie **Wybrane metody** przypisz wartość **Kod kroku grupy czynności**, np. *Karton*, do metody **Drukowanie etykiet grup czynności**. Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).
5. Należy ponownie przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.
6. W kolumnie **Wybrane metody** przypisz inną wartość **Kod kroku grupy czynności**, np. *Paleta*, do drugiej metody **Drukowanie etykiet grup czynności**. Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Tworzenie trzech układów etykiety grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy etykiety grupy czynności**.
1. Dodaj rekord z następującymi ustawieniami:

    - **Identyfikator układu etykiety:** *Karton*
    - **Opis:** *Karton (SSCC)*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.

    Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**. W tym miejscu można skonfigurować dynamiczną część etykiety.

1. Dodaj wiersz z następującymi ustawieniami:

    - **Identyfikator wiersza:** *WaveLabel*
    - **Nazwa tabeli wierszy:** *WHSWaveLabel*
    - **Pozycja początkowa wiersza:** *0*

        To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.

    - **Wysokość wiersza:** *0*

        To pole definiuje wysokość każdego wiersza (w punktach) zgodnie ze standardem ZPL. Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych. Ponieważ w tym przykładzie występuje tylko jeden wiersz, można nadać mu wartość *0* (zero).

    - **Liczba wierszy na stronę:** *1*

        To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.

        > [!NOTE]
        > Ta konfiguracja spowoduje wydrukowanie osobnej etykiety ZPL dla każdego rekordu w tabeli etykiety grupy czynności.

1. Zamknij stronę.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Typ pracy*
    - **Kryteria:** *Pobranie*

    To zapytanie zapewnia, że na etykiecie będą drukowane tylko wiersze pracy typu pobranie, a nie typy wierszy pracy.

1. Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**. 
1. Zamknij okno dialogowe edytora zapytań.
1. Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**. W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka. Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści. Oto przykład.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki. Oto przykład.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety. Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii. Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.

1. Pierwsza etykieta jest teraz gotowa do użycia.
1. Dodaj drugi rekord układu z następującymi ustawieniami:

    - **Identyfikator układu etykiety:** *Paleta*
    - **Opis:** *Paleta*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.

    Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**. W tym miejscu można skonfigurować dynamiczną część etykiety.

1. Dodaj wiersz z następującymi ustawieniami:

    - **Identyfikator wiersza:** *WaveLabel*
    - **Nazwa tabeli wierszy:** *WHSWaveLabel*
    - **Pozycja początkowa wiersza:** *0*

        To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.

    - **Wysokość wiersza:** *0*

        To pole definiuje wysokość każdego wiersza (w punktach) zgodnie ze standardem ZPL. Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych. Ponieważ w tym przykładzie występuje tylko jeden wiersz, można nadać mu wartość *0* (zero).

    - **Liczba wierszy na stronę:** *1*

        To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.

        > [!NOTE]
        > Ta konfiguracja powoduje wydrukowanie osobnej etykiety ZPL dla każdego rekordu w tabeli etykiety grupy czynności.

1. Zamknij stronę.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Typ pracy*
    - **Kryteria:** *Pobranie*

    To zapytanie zapewnia, że na etykiecie będą drukowane tylko wiersze pracy typu pobranie, a nie typy wierszy pracy.

1. Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.
1. Zamknij okno dialogowe edytora zapytań.
1. Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**. W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka. Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści. Oto przykład.

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki. Oto przykład.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety. Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii. Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.

1. Druga etykieta jest teraz gotowa do użycia.
1. Dodaj trzeci rekord układu z następującymi ustawieniami:

    - **Identyfikator układu etykiety:** *Podział*
    - **Opis:** *Etykieta podziału*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**. W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod ZPL dla wymaganego nagłówka. Oto przykład.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Tym razem żadna treść nie jest wymagana. W tym celu wystarczy wprowadzić wymagany tekst w **Sekcji stopki**. Oto przykład.

    ```plaintext
    ^XZ
    ```

    Trzecia etykieta jest teraz gotowa do użycia.

    > [!NOTE]
    > Trzecia etykieta jest etykietą podziału, która będzie używana jako separator między rolkami etykiet.

### <a name="create-two-wave-label-types"></a>Tworzenie dwóch typów etykiety grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Typy etykiety grupy czynności**.
1. Dodaj rekord z następującymi ustawieniami:

    - **Typ etykiety:** *Karton*
    - **Opis:** *Karton*

1. Dodaj drugi rekord z następującymi ustawieniami:

    - **Typ etykiety:** *Paleta*
    - **Opis:** *Paleta*

### <a name="set-up-unit-sequence-groups"></a>Ustaw grupy sekwencji jednostek

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Grupy sekwencji jednostek**.
1. Wybierz lub utwórz grupę **Każde Pudełko PL**.
1. W przypadku wiersza **Pudełko** należy określić wartość w polu **Typ poziomu grupy czynności** na *Karton*.
1. W przypadku wiersza **Numer identyfikacyjny** należy określić wartość w polu **Typ poziomu grupy czynności** na *Paleta*.

### <a name="create-wave-label-templates"></a>Tworzenie szablonów etykiety grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Szablony etykiety grupy czynności**.
1. Dodaj szablon etykiety z następującymi ustawieniami:

    - **Nazwa szablonu etykiety:** *Etykiety kartonu*
    - **Opis:** *Etykiety kartonu*
    - **Kod kroku grupy czynności:** *Karton*
    - **Magazyn:** *62*

1. Na skróconej karcie **Ogólne** w polu **Typ etykiety grupy czynności** wybierz wartość, np. *Karton*.
1. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj wiersz o następujących ustawieniach:

    - **Identyfikator układu etykiety:** *Karton*
    - **Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.
    - **Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**. Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wysyłki*
    - **Tabela pochodna:** *Wysyłki*
    - **Pole:** *Numer konta*
    - **Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.

    Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.

1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edytora zapytań dla całego szablonu etykiety.
1. W oknie dialogowym edytora zapytań na karcie **Sortowanie** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Odwołanie do identyfikatora wiersza ładunku (identyfikator rekordu)*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Dodaj drugi wiersz z następującymi ustawieniami:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Identyfikator wysyłki*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Zostanie wyświetlone okno komunikatu z monitem o potwierdzenie operacji resetowania grup. Wybierz przycisk **Tak**, aby kontynuować.
1. W okienku akcji wybierz opcję **Grupa szablonu etykiety grupy czynności**.
1. W oknie dialogowym **Grupa szablonów etykiety grupy czynności** dla wiersza, w którym w polu **Nazwa pola odwołania** jest ustawiona wartość *Identyfikator wysyłki*, należy określić następujące wartości:

    - **Drukuj etykietę podziału:** To pole wyboru należy zaznaczyć.
    - **Identyfikator układu etykiety:** Umożliwia wybór etykiety podziału. (Na przykład wybierz opcję układ etykiety *Podziału* utworzoną wcześniej w tym scenariuszu.)
    - **Nazwa drukarki:** Wybierz drukarkę dla etykiety podziału. (Zazwyczaj w celu rozdzielania przeniesień etykiet należy wybrać tę samą drukarkę, która została wybrana na skróconej karcie **Szczegóły szablonu etykiety grupy czynności**. Możliwe są jednak inne scenariusze.)

1. W wierszu, w którym pole **Nazwy pola odwołania** ma wartość *Odwołanie do identyfikatora wiersza ładunku*, zaznacz pole wyboru **Identyfikator kompilacji etykiety**.

    > [!NOTE]
    > Ten Instalator utworzy jedną sekwencję etykiet („Karton 1 z X”) dla każdego wiersza ładunku w rzucie, niezależnie od konfiguracji grupowania pracy. Tę sekwencję etykiet można wydrukować w układzie etykiety. Ponadto etykiety różnych wysyłek będą oddzielone wybraną etykietą podziału.

1. Wybierz **OK**, aby zamknąć okno dialogowe **Grupa szablonu etykiety grupy czynności**.
1. Dodaj drugi szablon etykiety z następującymi ustawieniami:

    - **Nazwa szablonu etykiety:** *Etykiety palety*
    - **Opis:** *Etykiety palety*
    - **Kod kroku grupy czynności:** *Paleta*
    - **Magazyn:** *62*

1. Na skróconej karcie **Ogólne** w polu **Typ etykiety grupy czynności** wybierz wartość, np. *Paleta*.
1. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj wiersz o następujących ustawieniach:

    - **Identyfikator układu etykiety:** *Paleta*
    - **Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.
    - **Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy. Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**. Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wysyłki*
    - **Tabela pochodna:** *Wysyłki*
    - **Pole:** *Numer konta*
    - **Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.

    Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań. 

1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edytora zapytań dla całego szablonu etykiety.
1. W oknie dialogowym edytora zapytań na karcie **Sortowanie** dodaj wiersz o następujących ustawieniach:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Odwołanie do identyfikatora wiersza ładunku (identyfikator rekordu)*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Dodaj drugi wiersz z następującymi ustawieniami:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Identyfikator wysyłki*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Zostanie wyświetlone okno komunikatu z monitem o potwierdzenie operacji resetowania grup. Wybierz przycisk **Tak**, aby kontynuować.
1. W okienku akcji wybierz opcję **Grupa szablonu etykiety grupy czynności**.
1. W oknie dialogowym **Grupa szablonów etykiety grupy czynności** dla wiersza, w którym w polu **Nazwa pola odwołania** jest ustawiona wartość *Identyfikator wysyłki*, należy określić następujące wartości:

    - **Drukuj etykietę podziału:** To pole wyboru należy zaznaczyć.
    - **Identyfikator układu etykiety:** Umożliwia wybór etykiety podziału. (Na przykład wybierz opcję układ etykiety *Podziału* utworzoną wcześniej w tym scenariuszu.)
    - **Nazwa drukarki:** Wybierz drukarkę dla etykiety podziału. (Zazwyczaj w celu rozdzielania przeniesień etykiet należy wybrać tę samą drukarkę, która została wybrana na skróconej karcie **Szczegóły szablonu etykiety grupy czynności**. Możliwe są jednak inne scenariusze.)

1. W wierszu, w którym pole **Nazwy pola odwołania** ma wartość *Odwołanie do identyfikatora wiersza ładunku*, zaznacz pole wyboru **Identyfikator kompilacji etykiety**.

    > [!NOTE]
    > Ten Instalator utworzy jedną sekwencję etykiet („Karton 1 z X”) dla każdego wiersza ładunku w rzucie, niezależnie od konfiguracji grupowania pracy. Tę sekwencję etykiet można wydrukować w układzie etykiety. Ponadto etykiety różnych wysyłek będą oddzielone wybraną etykietą podziału.

### <a name="configure-number-sequence-extensions"></a>Konfigurowanie sekwencji identyfikatorów

Rozszerzenia sekwencji identyfikatorów kontrolują zgodność GS1 z określonymi sekwencjami identyfikatorów. Ta konfiguracja jest opcjonalna dla bieżącego scenariusza. Aby uzyskać więcej informacji i instrukcji konfiguracyjnych, zobacz [Konfigurowanie rozszerzeń sekwencji identyfikatorów](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Utwórz zamówienie sprzedaży i zwolnij je do magazynu

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *62*

1. Dodaj dwa wiersze zamówienia sprzedaży:

    - Wiersz zamówienia sprzedaży 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *9024*
        - **Jednostka:** *Każdy* (9024 Każdy = 376 Pudełko = 47 Paleta)

    - Wiersz zamówienia sprzedaży 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *9016*
        - **Jednostka:** *Każdy* (9016 Każdy = 322 Pudełko = 46 Paleta)

    > [!NOTE]
    > Podane tu towary i ilości są tylko przykładami. Muszą one mieć zdefiniowaną wcześniej zdefiniowaną jednostkę, dlatego dla nich musi zostać zdefiniowana odpowiednia konwersja jednostek z *Każdy* na *Pudełko* na *Paleta* oraz musi mieć zapas w magazynie *62*. Aby uzyskać więcej informacji, zajrzyj do [Jednostka miary i zasady składowania](unit-measure-stocking-policies.md).

1. Wybierz wiersz zamówienia sprzedaży 1. W sekcji **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacje**.
1. Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii** i zamknij stronę.
1. Powtórz kroki 4 i 5 dla wiersza zamówienia sprzedaży 2.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Występują wówczas następujące zdarzenia: 

    - System przetwarza utworzoną wysyłkę za pomocą szablonu, który zawiera krok drukowania etykiety. Układ etykiety zostanie użyty do zdefiniowania formatu etykiety, a jego wynikiem będzie etykieta drukowana na drukarce wybranej w szablonie etykiety.
    - Etykiety grupy czynności są generowane i drukowane. Liczba etykiet będzie równa liczbie kartonów (w tym przykładzie 376 etykiet pudełek dla wiersza 1, 322 etykiet pudełek dla wiersza 2, 47 etykiet PL dla wiersza 1, 47 etykiet PL dla wiersza 2 i dwie etykiety podziału, które mają identyfikator przesyłki).
    - Nowy identyfikator list przewozowy jest generowany dla wysyłek. Jeśli skonfigurowano rozszerzenia sekwencji identyfikatorów, identyfikatory etykiet grupy czynności są zgodne z formatem numerów **SSCC-18**. 

Etykiety grupy czynności można przeglądać i ponownie drukować z następujących stron:

- Wszystkie wysyłki \> Szczegóły wysyłki
- Wszystkie ładunki \> Szczegóły ładunku
- Wszystkie grupy czynności
- Etykiety grup czynności
- Historia etykiet grupy czynności

W przypadku większości tych stron można znaleźć odpowiednią funkcję, zaznaczając odpowiednie **Etykiety grupy czynności** w grupie **Informacje pokrewne** na karcie **Wysyłki** w okienku akcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Ponowne drukowanie i unieważnianie etykiet grupy czynności](reprint-and-void-wave-labels.md)
- [Planowanie drukowania etykiety grupy czynności podczas grupy czynności](configure-task-based-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
