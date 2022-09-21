---
title: Konfigurowanie zasad konsolidacji wysyłki
description: W tym artykule opisano sposób konfigurowania domyślnych i niestandardowych zasad konsolidacji wysyłki.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427990"
---
# <a name="configure-shipment-consolidation-policies"></a>Konfigurowanie zasad konsolidacji wysyłki

[!include [banner](../includes/banner.md)]

Proces konsolidacji wysyłki, który korzysta z zasad konsolidacji wysyłki umożliwia na automatyczną konsolidację wysyłki automatycznego i ręcznego zwalniania do magazynu. Po włączeniu tej funkcji należy skonfigurować zasady początkowe. Jeśli nie skonfigurowano żadnych zasad, każdy wiersz sprzedaży generuje osobną wysyłkę z pojedynczym wierszem ładunku.

W scenariuszach przedstawionych w tym artykule pokazano sposób konfigurowania domyślnych i niestandardowych zasad konsolidacji wysyłki.

> [!WARNING]
> W przypadku uaktualnienia rozwiązania Microsoft Dynamics 365 Supply Chain Management, w którym jest już w użyciu starsza funkcja konsolidacji wysyłki, konsolidacja może przestać działać zgodnie z oczekiwaniami, chyba że użytkownik postąpi zgodnie z poniższymi poradami.
>
> W instalacjach Supply Chain Management, dla których jest wyłączona funkcja *Zasad konsolidacji wysyłek*, można włączyć konsolidację wysyłek, używając ustawienia **Konsoliduj wysyłkę przy zwalnianiu do magazynu** dla poszczególnych magazynów. Ta funkcja jest obowiązkowa od wersji 10.0.29. Po włączeniu ustawienie **Konsoliduj wysyłkę podczas zwalniania do magazynu** zostanie ukryte, a funkcja zostanie zastąpiona *zasadami konsolidacji wysyłki* opisanymi w tym artykule. Każda zasada ustala reguły konsolidacji i zawiera zapytanie mające na celu kontrolę zastosowania zasad. Po pierwszym włączeniu tej funkcji na stronie **Zasady konsolidacji wysyłki** nie zostaną zdefiniowane żadne zasady konsolidacji wysyłek. Jeśli nie zdefiniowano żadnych zasad, system będzie używać starszego działania. Dlatego każdy istniejący magazyn będzie nadal przestrzegał ustawień **Wysyłki skonsolidowanej podczas zwalniania do magazynu**, nawet jeśli to ustawienie jest teraz ukryte. Jednak po utworzeniu co najmniej jednej zasady ustawienie **Konsolidacja wysyłek przy zwalnianiu do magazynu** nie ma już żadnego skutku, a funkcje konsolidacji są całkowicie kontrolowane przez zasady.
>
> Po zdefiniowaniu co najmniej jednej zasady konsolidacji wysyłki system będzie sprawdzać zasady konsolidacji za każdym razem, gdy zamówienie jest zwalniane do magazynu. System przetwarza zasady przy użyciu klasyfikacji zdefiniowanej przez wartości **Sekwencji zasad** poszczególnych zasad. Zastosowanie ma pierwsza zasada, w której zapytanie pasuje do nowego zamówienia. Jeśli żadne zapytanie nie pasuje do zamówienia, każdy wiersz zamówienia generuje osobną wysyłkę z pojedynczym wierszem ładunku. Dlatego, jak wyjścia awaryjnego, zalecamy utworzenie domyślnej zasady, która będzie stosowana dla wszystkich magazynów i grup według numeru zamówienia. Nadaj tej zasady najwyższą wartość **Sekwencji zasad**, aby była ona przetwarzana jako ostatnia.
>
> Aby odtworzyć starsze zachowanie, należy utworzyć zasady, które nie grupują się według numeru zamówienia i mają kryteria zapytania, które zawiera wszystkie odpowiednie magazyny.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Włączanie funkcji konfigurowania zasad konsolidacji wysyłki

Aby można było skorzystać z funkcji *zasad konsolidacji wysyłki*, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.29, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Zasady konsolidacji wysyłki* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a>Ustanowienie wstępnych zasad konsolidacji

Jeśli pracujesz z nowym systemem lub systemem, w którym po raz pierwszy włączona została funkcja *Zasady konsolidacji wysyłek*, wykonaj następujące kroki, aby skonfigurować początkowe zasady konsolidacji wysyłek.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. W okienku akcji wybierz pozycję **Utwórz konfigurację domyślną**, aby utworzyć następujące zasady:

    - Zasady określone jako *domyślne* dla typu zasad *Zamówienia sprzedaży*.
    - Zasady określone jako *domyślne* dla typu zasad *Wydanie przeniesienia*.
    - Zasady określone jako *CrossOrder* dla typu zasad *Wydanie przeniesienia*. (Ta zasada jest tworzona tylko wtedy, gdy istnieje co najmniej jeden magazyn ze starszej wersji ustawienia **Konsoliduj wysyłkę podczas zwalniania** do magazynu zostało włączone.)
    - Zasady określone jako *CrossOrder* dla typu zasad *Zamówienia sprzedaży*. (Ta zasada jest tworzona tylko wtedy, gdy istnieje co najmniej jeden magazyn ze starszej wersji ustawienia **Konsoliduj wysyłkę podczas zwalniania** do magazynu zostało włączone.)

    > [!NOTE]
    > - Obie zasady *CrossOrder* uwzględniają ten sam zestaw pól, co w przypadku wcześniejszej logiki. Jednakże uwzględniają one także pole numeru zamówienia. (To pole służy do konsolidowania wierszy w wysyłkach na podstawie czynników, takich jak magazyn, metoda transportu dostawy i adres).
    > - Obie zasady *Domyślnie* uwzględniają ten sam zestaw pól, co w przypadku wcześniejszej logiki. Jednakże uwzględniają one także pole numeru zamówienia. (To pole służy do konsolidowania wierszy w wysyłkach na podstawie czynników, takich jak numer zamówienia, magazyn, metoda transportu dostawy i adres).

1. Jeśli system wygenerował zasady *CrossOrder* dla typu zasad *Zamówienia sprzedaży*, wybierz je, a następnie w okienku akcji wybierz pozycję **Edytuj zapytanie**. W edytorze zapytań można sprawdzić, dla których magazynów poprzednio włączono ustawienie **Konsoliduj wysyłkę podczas zwalniania do magazynu**. W związku z tym te zasady odtworzą poprzednie ustawienia tych magazynów.
1. Dostosuj w razie potrzeby nowe zasady domyślne, dodając lub usuwając pola i/lub edytując zapytania. Można także dodać dowolną liczbę nowych potrzebnych zasad. Aby uzyskać przykłady dostosowywania i konfigurowania zasad, zobacz przykładowy scenariusz w dalszej części tego artykułu.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Scenariusz: konfigurowanie niestandardowych zasad konsolidacji wysyłki

W tym scenariuszu pokazano przykład, w jaki sposób skonfigurować niestandardowe zasady konsolidacji wysyłki, a następnie przetestować je przy użyciu danych demonstracyjnych. Zasady niestandardowe mogą obsługiwać złożone wymagania biznesowe, w przypadku których konsolidacja wysyłki zależy od kilku warunków. Dla wszystkich przykładowych zasad w dalszej części tego scenariusza uwzględniono dodatkowy krótki opis. Te przykładowe zasady należy skonfigurować w kolejności, która zapewnia ocenę zapytań z użyciem metody w stylu piramidy. (Mówiąc inaczej, zasady mające najwięcej warunków powinny być oceniane jako mające najwyższy priorytet).

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Ten scenariusz odnosi się do wartości i rekordów, które są zawarte w standardowych [danych demonstracyjnych](../../fin-ops-core/fin-ops/get-started/demo-data.md), które są dostarczane dla rozwiązania Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na *USMF*.

### <a name="prepare-master-data-for-this-scenario"></a>Przygotuj dane główne dla tego scenariusza

Aby można było przejść przez ćwiczenia w tym scenariuszu, musisz przygotować dane główne wymagane do filtrowania, co opisano w poniższych podsekcjach. (Te wymagania wstępne dotyczą również scenariuszy wymienionych w sekcji [Przykładowe scenariusze korzystania z zasad konsolidacji wysyłki](#example-scenarios).)

#### <a name="create-two-new-product-filter-codes"></a>Tworzenie dwóch nowych kodów filtrów produktów

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Filtry produktów \> Filtry produktów** i dodaj dwa filtry produktów:

    - Filtr produktów 1:

        - **Kod filtru:** *Łatwopalne*
        - **Tytuł filtru:** *Kod 4*

    - Filtr produktów 2:

        - **Kod filtru:** *Materiały wybuchowe*
        - **Tytuł filtru:** *Kod 4*

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz produkt o numerze pozycji *M9200*. (Wybrany produkt musi być włączony dla zaawansowanych procesów magazynu \[WMS\] i ten produkt jest wstępnie włączony dla procesów WMS w danych demonstracyjnych **USMF**).
1. Na skróconej karcie **Magazyn** w polu **Kod 4** ustaw wartość *Łatwopalne*.
1. Zamknij stronę.
1. Otwórz produkt o numerze pozycji *M9201*. (Ten produkt jest również wstępnie włączony dla procesów WMS w danych demonstracyjnych **USMF**).
1. Na skróconej karcie **Magazyn** w polu **Kod 4** ustaw wartość *Materiały łatwopalne*.
1. Zamknij stronę.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Tworzenie nowego trybu transportu dla dostawy

1. Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Tryb**.
1. Utwórz tryb transportu, który będzie używany w zapytaniach dotyczących konsolidacji, i nadaj mu nazwę *Trasy lotnicze*.
1. Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.
1. Utwórz przewoźnika z następującymi ustawieniami:

    - **Przewoźnik:** *Trasy lotnicze*
    - **Nazwa:** *Trasy lotnicze*
    - **Tryb:** *Trasy lotnicze*

1. Na skróconej karcie **Usługi** dla nowego przewoźnika dodaj wiersz z następującymi ustawieniami:

    - **Usługa przewozowa:** *Lotnicza*
    - **Metoda transportu:** *Lotniczy*

1. Na okienku akcji wybierz opcję **Zapisz**.

    > [!NOTE]
    > Po zapisaniu nowego przewoźnika pole **Tryb dostawy** dla nowego wiersza w siatce **Usługi** zostanie automatycznie ustawione na *Airwa-Air*. W przypadku użycia trybu dostawy *Airwa-Air* dla zamówienia sprzedaży tryb transportu *Trasy lotnicze* będzie używany dla pokrewnych wysyłek.

#### <a name="create-an-order-pool"></a>Tworzenie puli zamówień

1. Przejdź do pozycji **Sprzedaż i marketing \> Ustawienia \> Zamówienia sprzedaży \> Pule zamówień**.
1. Utwórz pulę zamówień, która będzie używana w zapytaniu dotyczącym konsolidacji. Ta pula zamówień powinna mieć następujące ustawienia:

    - **Pula:** wprowadź liczbę całkowitą, która nie jest jeszcze używana przez żadną inną pulę.
    - **Nazwa:** *ShipCons*

1. Przejdź do pozycji **Sprzedaż i marketing \> Odbiorcy \> Wszyscy odbiorcy**.
1. Otwórz odbiorcę z numerem konta *US-003*.
1. Na skróconej karcie **Ustawienia domyślne zamówienia sprzedaży** ustaw pole **Pula zamówień sprzedaży** na utworzoną właśnie pulę zamówień.
1. Zamknij stronę, a następnie powtórz kroki 4 i 5 dla odbiorcy o numerze konta *US-004*.

### <a name="create-example-policy-1"></a>Tworzenie przykładowych zasad 1

W tym przykładzie utworzysz zasady *Odbiorca i tryb*, które mogą być używane dla następujących przypadków biznesowych:

- Zasady spowodują utworzenie zapytania dotyczącego określonego konta odbiorcy (*US-001*) i trybu dostawy (*Airwa-Air*).
- Konsolidacja z otwartymi wysyłkami jest wyłączona.
- Konsolidacja jest przeprowadzana dla poszczególnych identyfikatorów zamówień. (Mówiąc inaczej, dla każdego zamówienia, magazynu itd. będą dostępne osobne wysyłki).

Aby utworzyć zasady konsolidacji wysyłki dla tego przypadku biznesowego, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. Ustaw pole **Typ zasad** na *Zamówienia sprzedaży*.
1. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć zasady z następującymi ustawieniami:

    - **Nazwa zasad:** *CustomerMode*
    - **Opis zasad:** *Konto odbiorcy i tryb dostawy*

1. Pozostaw opcję **Konsolidowanie z otwartymi wysyłkami** ustawioną na *Nie*.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Pola konsolidacji** na liście **Pozostałe pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Metoda dostawy*.
1. Wybierz przycisk **Dodaj** ![Strzałka w prawo.](media/forward-button.png) Kliknij przycisk , aby przenieść wybrane pole na listę **Wybrane pola**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** w siatce znajdź wiersz, w którym pole **Pole** zostało ustawione na *Konto odbiorcy*, i ustaw pole **Kryteria** dla tego wiersza na *US-001*.
1. Wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:

    - **Tabela:** *Wiersze zamówienia*
    - **Tabela pochodna:** *Wiersze zamówienia*
    - **Pole:** *Metoda dostawy*
    - **Kryteria:** *Airwa-Air*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

> [!NOTE]
> Dla tego przypadku biznesowego wiersze zamówienia dla odbiorcy *US-001* korzystającego z metody dostawy *Airwa-Air* nie będą konsolidowane między zamówieniami. Te zasady są przeznaczone do użycia jako pierwsza w sekwencji, w przypadkach, gdy dla danego odbiorcy są konsolidowane wysyłki dla wszystkich innych metod dostawy.

### <a name="create-example-policy-2"></a>Tworzenie przykładowych zasad 2

W tym przykładzie utworzysz zasady *Towary niebezpieczne*, które mogą być używane dla następujących przypadków biznesowych:

- Zasady spowodują utworzenie zapytania dotyczącego określonego kodu filtra (*niebezpieczne*) i trybu dostawy (*Airwa-Air*).
- Konsolidacja z otwartymi wysyłkami jest włączona.
- Konsolidacja jest przeprowadzana w ramach różnych zamówień. (Mówiąc inaczej, będą istnieć oddzielne wysyłki dla poszczególnych kont, magazynów itd., ale tylko w grupie pozycji określonej w zapytaniu).

Aby utworzyć zasady konsolidacji wysyłki dla tego przypadku biznesowego, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. Ustaw pole **Typ zasad** na *Zamówienia sprzedaży*.
1. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć zasady z następującymi ustawieniami:

    - **Nazwa zasad:** *Typ pozycji*
    - **Opis zasad:** *Konsolidowanie tego samego typu pozycji w zamówieniach*

1. Ustaw opcję **Konsolidowanie z otwartymi wysyłkami** na *Tak*.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Pola konsolidacji** na liście **Pozostałe pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Metoda dostawy*.
1. Wybierz przycisk **Dodaj** ![Strzałka w prawo.](media/forward-button.png) Kliknij przycisk , aby przenieść wybrane pole na listę **Wybrane pola**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytor zapytań na karcie **Sprzężenia** rozwiń węzeł i wybierz pozycję **Tabelę \> Załaduj szczegóły** w drzewie.
1. Wybierz pozycję **Dodaj sprzężenie tabeli**.
1. W wyświetlonej siatce relacji znajdź i wybierz wiersz, w którym pole **Relacja** zostało ustawione na *Numer pozycji magazynowej (numer pozycji)*, a następnie wybierz pozycję **Wybierz**. 
1. Na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:

    - **Tabela:** *Numer pozycji magazynowej*
    - **Tabela pochodna:** *Numer pozycji magazynowej*
    - **Pole:** *Kod 4*
    - **Kryteria:** *Łatwopalne*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

> [!NOTE]
> W tym przypadku biznesowym wszystkie wiersze zamówienia, w których pozycje mają określony kod filtru (czyli kod filtru z polem **Kod 4** ustawionym na *Łatwopalne*), zostaną skonsolidowane z innymi pozycjami tego samego typu w różnych zamówieniach. Jeśli istnieje otwarta wysyłka dla tego samego konta, magazynu i grupy pozycji, zostaną do niej dołączone nowe wiersze.

### <a name="create-example-policy-3"></a>Tworzenie przykładowych zasad 3

W tym przykładzie utworzysz zasady *Wymagania odbiorców*, które mogą być używane dla następujących przypadków biznesowych:

- Zasady spowodują wykonanie zapytania dotyczącego określonego konta odbiorcy.
- Konsolidacja z otwartymi wysyłkami jest włączona.
- Konsolidacja jest przeprowadzana między zamówieniami, ale opiera się na zapotrzebowaniach odbiorców. (Mówiąc inaczej, wiele zamówień zostanie pogrupowanych w wysyłki w oparciu o ten sam numer zapotrzebowania odbiorcy i jego magazyn).

Aby utworzyć zasady konsolidacji wysyłki dla tego przypadku biznesowego, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. Ustaw pole **Typ zasad** na *Zamówienia sprzedaży*.
1. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć zasady z następującymi ustawieniami:

    - **Nazwa zasad:** *CustomerOrderNo*
    - **Opis zasad:** *Konsolidowanie wierszy na podstawie zamówienia zakupu odbiorcy*

1. Ustaw opcję **Konsolidowanie z otwartymi wysyłkami** na *Tak*.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Pola konsolidacji** na liście **Pozostałe pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Zapotrzebowanie odbiorcy*.
1. Wybierz przycisk **Dodaj** ![Strzałka w prawo.](media/forward-button.png) Kliknij przycisk , aby przenieść wybrane pole na listę **Wybrane pola**.
1. Na liście **Pozostałe pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Metoda dostawy*.
1. Wybierz przycisk **Dodaj** ![Strzałka w prawo.](media/forward-button.png) Kliknij przycisk , aby przenieść wybrane pole na listę **Wybrane pola**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** zostało ustawione na *Konto odbiorcy*, i ustaw pole **Kryteria** dla tego wiersza na *US-001*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

> [!NOTE]
> W przypadku tego przypadku biznesowego wszystkie wiersze zamówienia, w których zamówienia sprzedaży mają ten sam numer zapotrzebowania odbiorcy, zostaną skonsolidowane w jedną wysyłkę, niezależnie od numeru zamówienia sprzedaży. (Numer zapotrzebowania odbiorcy jest używany jako numer zamówienia zakupu \[ZZ\] odbiorcy). Jeśli istnieje otwarta wysyłka dla tego samego konta, magazynu i zapotrzebowania odbiorcy, zostaną do niej dołączone nowe wiersze. Tych zasad można użyć, jeśli odbiorca wysyła dodatkowe wiersze zamówienia z tym samym numerem ZZ kilka razy w ciągu dnia i chce, aby wszystkie wiersze zostały zgrupowane w jednej wysyłce. (Mówiąc inaczej, będzie istnieć jeden list przewozowy i jeden dokument dostawy).

### <a name="create-example-policy-4"></a>Tworzenie przykładowych zasad 4

W tym przykładzie utworzysz zasady *Odbiorcy zezwalający na konsolidację*, które mogą być używane dla następujących przypadków biznesowych:

- Zasady będą wykonywać zapytania dotyczące konkretnej puli zamówień, aby identyfikować odbiorców, którzy akceptują wysyłki skonsolidowane.
- Konsolidacja z otwartymi wysyłkami jest wyłączona.
- Konsolidacja jest wykonywana w ramach różnych zamówień przy użyciu pól wybranych przez domyślne zasady CrossOrder (w celu zreplikowania poprzedniego pola wyboru **Konsolidowanie wysyłki podczas zwalniania do magazynu**).

- Regułę w zamówieniu sprzedaży można zastąpić, wybierając inną pulę zamówień.

Aby utworzyć zasady konsolidacji wysyłki dla tego przypadku biznesowego, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. Ustaw pole **Typ zasad** na *Zamówienia sprzedaży*.
1. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć zasady z następującymi ustawieniami:

    - **Nazwa zasad:** *Pula zamówień*
    - **Opis zasad:** *Konsolidowanie między zamówieniami na podstawie puli zamówień*

1. Pozostaw opcję **Konsolidowanie z otwartymi wysyłkami** ustawioną na *Nie*.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Pola konsolidacji** na liście **Pozostałe pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Metoda dostawy*.
1. Wybierz przycisk **Dodaj** ![Strzałka w prawo.](media/forward-button.png) Kliknij przycisk , aby przenieść wybrane pole na listę **Wybrane pola**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:

    - **Tabela:** *Zamówienia sprzedaży*
    - **Tabela pochodna:** *Zamówienia sprzedaży*
    - **Pole:** *Pula*
    - **Kryteria:** *ShipCons*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

> [!NOTE]
> W tym przypadku biznesowym wszystkie wiersze zamówienia, w których zamówienia sprzedaży należą do tej samej puli zamówień, zostaną skonsolidowane w jedną wysyłkę w zamówieniach sprzedaży dla tego samego konta, magazynu i trybu transportu dostawy. Zamiast puli zamówień można użyć dowolnego innego pola w celu odróżnienia grupy odbiorców i domyślnego użycia nagłówka zamówienia sprzedaży. Z tego podejścia można skorzystać, jeśli odbiorca, a nie magazyn, jest odpowiedzialny za potrzebę konsolidacji. (We wcześniejszej logice konsolidacji magazyn odpowiadał za potrzebę konsolidacji).

### <a name="create-example-policy-5"></a>Tworzenie przykładowych zasad 5

W tym przykładzie utworzysz zasady *Magazyny zezwalające na konsolidację*, które mogą być używane dla następujących przypadków biznesowych:

- Zasady będą wykonywać zapytania dotyczące konkretnej puli zamówień, aby identyfikować magazyny z możliwością konsolidowania wysyłek.
- Konsolidacja z otwartymi wysyłkami jest wyłączona.
- Konsolidacja jest wykonywana w ramach różnych zamówień przy użyciu pól wybranych przez domyślne zasady CrossOrder (w celu zreplikowania poprzedniego pola wyboru **Konsolidowanie wysyłki podczas zwalniania do magazynu**).

Zazwyczaj ten przypadek biznesowy można obsługiwać przy użyciu zasad domyślnych utworzonych w [Ustanowienie wstępnych zasad konsolidacji](#initial-policies). Można jednak również ręcznie utworzyć podobne zasady, wykonując poniższe kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. Ustaw pole **Typ zasad** na *Zamówienia sprzedaży*.
1. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć zasady z następującymi ustawieniami:

    - **Nazwa zasad:** *Zamówienia krzyżowe*
    - **Opis zasad:** *Konsolidacja krzyżowa zamówień dla wybranych magazynów*

1. Pozostaw opcję **Konsolidowanie z otwartymi wysyłkami** ustawioną na *Nie*.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Pola konsolidacji** w polu **Pozostałe pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Metoda dostawy*.
1. Wybierz przycisk **Dodaj** ![Strzałka w prawo.](media/forward-button.png) Kliknij przycisk , aby przenieść wybrane pole na listę **Wybrane pola**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** zostało ustawione na *Magazyn*, i ustaw pole **Kryteria** dla tego wiersza na *61, 63*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

### <a name="set-the-order"></a>Ustawianie kolejności

Po utworzeniu wszystkich zasad należy określić kolejność, w jakiej będą one stosowane. Aby korzystać z podejścia w stylu piramidy, w przypadku którego zasady z największą liczbą warunków są oceniane jako mające najwyższy priorytet, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. Ustaw pole **Typ zasad** na *Zamówienia sprzedaży*.
1. Wybierz każdą z wymienionych zasad w lewej kolumnie, a następnie użyj przycisków **Przenieś w górę** i **Przenieś w dół** w okienku akcji, aby uporządkować zasady w następującej kolejności:

    1. CustomerMode
    1. Typ pozycji
    1. CustomerOrderNo
    1. Pula zamówień
    1. Zamówienia krzyżowe
    1. Domyślna

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Przykładowe scenariusze korzystania z zasad konsolidacji wysyłki

Poniższe scenariusze ilustrują sposób korzystania z zasad konsolidacji wysyłki utworzonych podczas pracy z tym artykułem. Każdy scenariusz prowadzi użytkownika przez proces konsolidacji wysyłki, który korzysta z zasad konsolidacji wysyłki podczas automatycznego lub ręcznego zwalniania do magazynu:

- Scenariusz 1: [Konsolidowanie wysyłek podczas zwalniania ich do magazynu przy użyciu automatycznego zwalniania zamówień sprzedaży](../warehousing/consolidate-shipments-automatic.md)
- Scenariusz 2: [Konsolidowanie wysyłek, gdy zasady konsolidacji wysyłki są zastąpione na stronie zwalniania do magazynu](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scenariusz 3: [Konsolidowanie wysyłek przy użyciu polecenia Zwolnij do magazynu z pulpitu planowania wysyłki ładunku](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scenariusz 4: [Konsolidowanie wysyłek przy użyciu pulpitu konsolidacji wysyłki](../warehousing/consolidate-shipments-manual-workbench.md)
- Scenariusz 5: [Ręczne konsolidowanie wysyłek przy użyciu strony konsolidacji wysyłek](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zasad konsolidacji wysyłki](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
