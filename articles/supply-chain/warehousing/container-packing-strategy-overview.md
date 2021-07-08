---
title: Strategie pakowania kontenerów
description: W tym temacie opisano różnice między strategiami pakowania kontenerów i podano przykłady.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292768"
---
# <a name="container-packing-strategies"></a>Strategie pakowania kontenerów

*Strategia pakowania kontenerów* to strategia, która umożliwia definiowanie alokacji towarów między kontenerami. W tym temacie wyjaśniono różnice pomiędzy strategiami *Pakowaniem do wszystkich otwartych pojemników* i *Pakowaniem tylko do bieżącego pojemnika*.

- **Zapakuj we wszystkie otwarte kontenery** — system musi sprawdzić wszystkie otwarte kontenery, które zostały już utworzone podczas cyklu konteneryzacji, aby upewnić się, że towar dopasuje się do jednego z nich. Podczas pakowania system sprawdza każdy towar w celu określenia, czy zmieści się w dowolnym z wcześniej utworzonych kontenerów. Jeśli przedmiot nie mieści się w istniejącym pojemniku, system tworzy nowy pojemnik i kontynuuje pracę aż do zakończenia pakowania całego zamówienia.

    Na przykład *n* zamówionych towarów wymaga konteneryzacji. W najgorszym przypadku, za każdym razem, gdy system przetwarza element, który nie pasuje do żadnego istniejącego pojemnika, wykona łącznie (\[(*n* – 1) × (*n* + 1)\] ÷ 2) sprawdzeń, aby ocenić, czy element pasuje do istniejących pojemników.

- **Zapakuj tylko do obecnego kontenera** — system musi sprawdzić tylko ostatnio utworzony pojemnik, aby upewnić się, że element się w nim zmieści. Podczas pakowania system sprawdza każdy element, aby określić, czy zmieści się do ostatnio utworzonego pojemnika. Jeśli przedmiot nie mieści się w istniejącym pojemniku, system tworzy nowy pojemnik i kontynuuje pracę aż do zakończenia pakowania całego zamówienia.

    Na przykład *n* zamówionych towarów wymaga konteneryzacji. W takim przypadku system będzie sprawdzać łącznie (*n* – 1) w celu sprawdzenia, czy towar mieści się w kontenerach.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Przykład przepływu strategii pakowania kontenerów

Ustawiono następujące elementy do konteneryzacji.

| Pozycja | Wymiary fizyczne (szerokość × wysokości × wysokości) | Masa |
|---|---|---|
| Kabel HDMI 6' | 1 × 1 × 1 | 1 |
| Kabel HDMI 12' | 2 × 1 × 1 | 1 |
| Kabel HDMI 18' | 3 × 1 × 1 | 2 |

Można również skonfigurować następujące pole, które będzie używane do pakowania.

| Kontener | Wymiary fizyczne (długość × szerokość × wysokość) | Masa | Objętość |
|---|---|---|---|
| Średnie pudełko | 6 × 3 × 2 | 10 | 100 |

Na koniec można skonfigurować zamówienie, które ma następujące produkty i ilości.

| Wiersz zamówienia sprzedaży | Ilość |
|---|---|
| Kabel HDMI 12' | 9 |
| Kabel HDMI 18' | 8 |
| Kabel HDMI 6' | 13 |

Poniższa tabela podsumowuje działanie konteneryzacji w przypadku użycia strategii *Pakuj do wszystkich otwartych kontenerów* oraz strategii *Pakuj tylko do bieżącego kontenera*.

| Zapakuj we wszystkie otwarte kontenery | Zapakuj do bieżącego kontenera |
|---|---|
| <p>Kabel HDMI 12':</p><ol><li>Tworzenie nowego typu kontenera, CONT0001.</li><li>Umieść 9 ea w kontenerze CONT0001.</li></ol> | <p>Kabel HDMI 12':</p><ol><li>Tworzenie nowego typu kontenera, CONT0001.</li><li>Umieść 9 ea w kontenerze CONT0001.</li></ol> |
| <p>Kabel HDMI 18':</p><ol><li>Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0001.</li><li>Tworzenie nowego typu kontenera, CONT0002.</li><li>Umieść 5 ea w kontenerze CONT0002.</li><li>Tworzenie nowego typu kontenera, CONT0003.</li><li>Umieść 3 ea w kontenerze CONT0003.</li></ol> | <p>Kabel HDMI 18':</p><ol><li>Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0001.</li><li>Tworzenie nowego typu kontenera, CONT0002.</li><li>Umieść 5 ea w kontenerze CONT0002.</li><li>Tworzenie nowego typu kontenera, CONT0003.</li><li>Umieść 3 ea w kontenerze CONT0003.</li></ol> |
| <p>Kabel HDMI 6':</p><ol><li>Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0001.</li><li>Umieść 1 ea w kontenerze CONT0001.</li><li>Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0002.</li><li>Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0003.</li><li>Umieść 4 ea w kontenerze CONT0003.</li><li>Tworzenie nowego typu kontenera, CONT0004.</li><li>Umieść 8 ea w kontenerze CONT0004.</li></ol> | <p>Kabel HDMI 6':</p><ol><li>Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0003.</li><li>Umieść 4 ea w kontenerze CONT0003.</li><li>Tworzenie nowego typu kontenera, CONT0004.</li><li>Umieść 9 ea w kontenerze CONT0004.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Przykładowy scenariusz: Pakowanie pojedynczych zamówień do jednego pojemnika

W tej sekcji przedstawiono scenariusz, w którym system jest skonfigurowany do konsolidacji wielu zamówień w jedną przesyłkę. Dlatego konteneryzacja będzie wykonywana z poziomu zamówienia sprzedaży, aby zapewnić, że każde zamówienie zawierające wiele produktów jest pakowane do własnego pojemnika.

Funkcja ta pozwala na obsługę scenariuszy, w których do każdego pojemnika należy zapakować tylko jedno zamówienie sprzedaży, tak aby centrum dystrybucyjne mogło przeładowywać pełne pojemniki pomiędzy sklepami detalicznymi. Oprócz scenariuszy dla handlu detalicznego (zamówienie na sklep detaliczny i wysyłka do centrum dystrybucji w celu cross-dockingu) technika ta jest również powszechnie stosowana w szczupłych łańcuchach dostaw (zamówienie sprzedaży na linię produkcyjną just-in-time).

Ten scenariusz pokazuje, jak można zmniejszyć liczbę pojemników, które są oceniane podczas pakowania, używając strategii *Pakować tylko do aktualnego kontenera* dla konteneryzacji.

### <a name="prerequisites"></a>Wymagania wstępne

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>Włącz funkcję Konsoliduj wysyłki w systemie

W tym scenariuszu jest używana funkcja *Konsoliduj wysyłki*. Jeśli ta funkcja nie jest jeszcze dostępna w systemie, należy ją włączyć za pomocą [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

#### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.

### <a name="inspect-or-create-container-types"></a>Sprawdzanie lub tworzenie typów kontenerów

Aby sprawdzić typy kontenerów lub utworzyć w razie potrzeby nowe typy kontenerów, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Typy kontenerów**.
1. Upewnij się, że każdy z poniższych typów kontenerów jest dostępny w danych demo. W razie potrzeby edytuj lub utwórz typy kontenerów.

    - Typ kontenera 1:

        - **Kod typu kontenera:** *Pudełko-duże*
        - **Opis:** *duże pudełko*
        - **Maksymalna waga netto:** *100*
        - **Objętość:** *400*
        - **Długość:** *4*
        - **Szerokość:** *10*
        - **Wysokość:** *10*

    - Typ kontenera 2:

        - **Kod typu kontenera:** *Pudełko-średnie*
        - **Opis:** *średnie pudełko*
        - **Maksymalna waga netto:** *50*
        - **Objętość:** *200*
        - **Długość:** *2*
        - **Szerokość:** *10*
        - **Wysokość:** *10*

    - Typ kontenera 3:

        - **Kod typu kontenera:** *Pudełko-małe*
        - **Opis:** *małe pudełko*
        - **Maksymalna waga netto:** *20*
        - **Objętość:** *100*
        - **Długość:** *1*
        - **Szerokość:** *10*
        - **Wysokość:** *10*

### <a name="inspect-or-create-container-groups"></a>Sprawdzanie lub tworzenie grup kontenerów

Aby sprawdzić grupy kontenerów lub utworzyć w razie potrzeby nowe grupy kontenerów, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Grupy kontenerów**.
1. Upewnij się, że każda z poniższych grup kontenerów jest dostępna w danych demo. Jeśli nie jest dostępna, wybierz pozycję **Nowa**, aby ją utworzyć.

    - **Identyfikator grupy kontenerów:** *Pudełka*
    - **Opis:** *rozmiary pudełek*

1. Na skróconej karcie **Szczegóły** dotyczącej grupy kontenerów *pudełek* upewnij się, że istnieją następujące wiersze. Jeśli nie, wybierz przycisk **Nowy**, aby go dodać.

    - Wiersz 1:

        - **Numer sekwencyjny:** *1*
        - **Typ kontenera:** *Pudełko-duże*
        - **Procent wykorzystania kontenera:** *100*

    - Wiersz 2:

        - **Numer sekwencyjny:** *2*
        - **Typ kontenera:** *Pudełko-średnie*
        - **Procent wykorzystania kontenera:** *100*

    - Wiersz 3:

        - **Numer sekwencyjny:** *3*
        - **Typ kontenera:** *Pudełko-małe*
        - **Procent wykorzystania kontenera:** *100*

### <a name="create-a-new-container-build-template"></a>Utwórz nowy szablon kompilacji kontenera

Aby utworzyć nowy szablon budowy kontenera, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Szablony kompilacji kontenerów**.
1. Wybierz opcję **Nowy**, aby utworzyć szablon kompilacji kontenera, który ma następujące ustawienia:

    - **Numer sekwencyjny:** *1*
    - **Identyfikator szablonu kontenera:** *pudełko*
    - **Identyfikator grupy kontenerów:** *Pudełka*
    - **Typy kwerend podstawowych:** *wiersz alokacji sprzedaży*
    - **Kod kroku grupy czynności:** *234*
    - **Zezwalaj na dzielenie pobrania:** *Tak*
    - **Strategia pakowania kontenerów:** *Pakowanie tylko do bieżącego kontenera*
    - **Pakuj według jednostki dyrektywy:** *Nie*

1. Gdy wiersz dla nowego szablonu jest nadal zaznaczony, wybierz **Edytuj zapytanie** w oknie akcji.
1. Zostanie wyświetlone standardowe okno dialogowe edycji zapytania. Na karcie **Sortowanie** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:

    - **Tabela:** *Tymczasowe transakcje pracy*
    - **Tabela pochodna:** *Tymczasowe transakcje pracy*
    - **Pole:** *Numer zamówienia*
    - **Kierunek wyszukiwania:** *Rosnąco*

    > [!IMPORTANT]
    > Aby uniknąć przechodzenia cyklicznie przez wszystkie pozostałe otwarte pojemniki i przyspieszyć proces sprawdzania jednego pojemnika na raz, oprócz sortowania według numeru porządkowego należy zastosować strategię *Pakuj tylko do bieżącego kontenera*. Ta kombinacja działa jak przerwa w szablonie pracy.

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Gdy wiersz dla nowego szablonu jest nadal zaznaczony, wybierz **Ograniczenia dotyczące mieszania kontenerów** w oknie akcji.

    Dodasz teraz ograniczenie, które umieści elementy z jednego zamówienia w jednym kontenerze. Przedmioty z innego zamówienia zostaną umieszczone w osobnym kontenerze.

1. Wybierz opcję **Nowy**, aby utworzyć ograniczenie mieszania, które ma następujące ustawienia:

    - **Tabela:** *Zamówienia sprzedaży*
    - **Wybierz pole:** *SalesId* (pole będzie wyświetlane w siatce jako *zamówienie sprzedaży*)

1. Wybierz przycisk **OK**, aby dodać ograniczenie.
1. Zamknij stronę.

### <a name="set-up-a-wave-template-for-containerization"></a>Konfigurowanie szablonu grupy czynności dla konteneryzacji

Aby skonfigurować szablon grupy czynności, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. W okienku listy w polu **Typ szablonu grupy czynności** ustaw wartość na *Wysyłka*.
1. Wybierz szablon **Konteneryzacji 63** na liście.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Metody** w kolumnie **Wybrane metody** znajdź następujący wiersz:

    - **Nazwa metody:** *konteneryzacja*
    - **Nazwa:** *Konteneryzacja*

1. Umożliwia ustawienie pola **Kodu kroku grupy czynności** dla tego wiersza na *234*.

### <a name="set-up-a-work-template"></a>Konfigurowanie szablonów pracy

Aby skonfigurować szablon pracy, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. Ustaw pole **Typ zlecenia pracy** na *Zamówienia sprzedaży*.
1. W siatce **Omówienie** znajdź i wybierz szablon roboczy, który powinien być użyty do pakowania pojedynczych zamówień na pojemnik. W tym scenariuszu wybierz szablon **63 Pobranie do kontenera**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. Zostanie wyświetlone standardowe okno dialogowe edycji zapytania. Dodaj następujące wiersze na karcie **Sortowanie**:

    - Wiersz 1:

        - **Tabela:** *Tymczasowe transakcje pracy*
        - **Tabela pochodna:** *Tymczasowe transakcje pracy*
        - **Pole:** *Identyfikator wysyłki*
        - **Kierunek wyszukiwania:** *Rosnąco*

    - Wiersz 2:

        - **Tabela:** *Tymczasowe transakcje pracy*
        - **Tabela pochodna:** *Tymczasowe transakcje pracy*
        - **Pole:** *Numer zamówienia*
        - **Kierunek wyszukiwania:** *Rosnąco*

    - Wiersz 3:

        - **Tabela:** *Tymczasowe transakcje pracy*
        - **Tabela pochodna:** *Tymczasowe transakcje pracy*
        - **Pole:** *Identyfikator kontenera*
        - **Kierunek wyszukiwania:** *Rosnąco*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Zostanie wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?” Wybierz przycisk **Tak**, aby kontynuować.
1. Gdy szablon **63 Pobierz do kontenera** jest nadal zaznaczony, wybierz **Nowe wiersze nagłówka roboczego** na panelu akcji.

    Teraz zastosujesz ustawienia, aby podzielić pracę w taki sposób, aby każdy pojemnik w zamówieniu był powiązany z jednym zleceniem roboczym.

1. Zaznacz pole wyboru **Grupuj według tego pola** dla każdego wiersza na stronie **podziału nagłówka pracy** (**Identyfikator wysyłki**, **Numer zamówienia** i **Identyfikator kontenera**).
1. Zamknij stronę.

### <a name="set-up-shipment-consolidation-policies"></a>Ustanowienie zasad konsolidacji przesyłek

Aby skonfigurować zasady konsolidacji przesyłek, należy wykonać poniższe kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.
1. W oknie listy w polu **Typ zasady** na *Zamówienia sprzedaży*.
1. Na liście zaznacz **Domyślną** zasadę.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Pola konsolidacji** na liście **Wybrane pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Numer zamówienia*.
1. Wybierz przycisk **usuń** ![Strzałka w lewo](media/backward-button.png), aby przenieść pole na listę **Pozostałe pola**.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-physical-dimensions-for-the-product"></a>Ustaw fizyczne wymiary produktu

Aby skonfigurować wymiary fizyczne dla produktów, które będą używane w tym scenariuszu, wykonaj następujące czynności.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt, dla którego pole **Kod pozycji** ma wartość *A0001*.
1. W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Magazyn** wybierz **Wymiary fizyczne**.
1. Na stronie **Wymiary fizyczne** powinien być wyświetlony następujący wiersz w siatce:

    - **Jednostka:** *pcs*
    - **Waga brutto:** *3,00*
    - **Szerokość:** *2,00*
    - **Głębokość:** *2,00*
    - **Wysokość:** *4,00*
    - **Objętość:** *16,00*

1. Zamknij stronę.
1. Wybierz produkt, dla którego pole **Kod pozycji** ma wartość *A0002*.
1. W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Magazyn** wybierz **Wymiary fizyczne**.
1. Na stronie **Wymiary fizyczne** powinien być wyświetlony następujący wiersz w siatce:

    - **Jednostka:** *pcs*
    - **Waga brutto:** *4,00*
    - **Szerokość:** *3,00*
    - **Głębokość:** *1,00*
    - **Wysokość:** *3,00*
    - **Objętość:** *9,00*

### <a name="create-sales-order-1"></a>Utwórz zamówienie sprzedaży 1

Aby utworzyć zamówienie sprzedaży, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Pojawia się okno dialogowe do tworzenia nowego zlecenia sprzedaży. Ustaw następujące wartości:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *63*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy sprzedaży:

    - Wiersz 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *2*

    - Wiersz 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *2*

1. Wybierz pierwszy wiersz, a następnie wybierz opcję **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii**. Następnie zamknij stronę.
1. Powtórz poprzednie dwa kroki dla drugiego wiersza.
1. Zamknij stronę.

### <a name="create-sales-order-2"></a>Utwórz zamówienie sprzedaży 2

Aby utworzyć drugie zlecenie sprzedaży, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Pojawia się okno dialogowe do tworzenia nowego zlecenia sprzedaży. Ustaw następujące wartości:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *63*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy sprzedaży:

    - Wiersz 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *4*

    - Wiersz 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *4*

1. Wybierz pierwszy wiersz, a następnie wybierz opcję **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii**. Następnie zamknij stronę.
1. Powtórz poprzednie dwa kroki dla drugiego wiersza.
1. Zamknij stronę.

### <a name="create-the-load"></a>Tworzenie obciążenia

Aby utworzyć obciążenie dla każdego zamówienia utworzonego w tym scenariuszu, a następnie zwolnić je do magazynu, należy wykonać następujące czynności.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. Na karcie **Wiersze sprzedaży** znajdź i wybierz wszystkie wiersze zamówienia sprzedaży w jednym z zamówień utworzonych dla tego scenariusza.
1. W okienku akcji na karcie **Popyt i podaż** w grupie **Dodaj** kliknij opcję **Do nowego transportu**. Wybrane linie zleceń są dodawane do nowego ładunku.
1. W oknie dialogowym **Przypisanie szablonu ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon ładunku, na przykład *Kontener 40'*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. W sekcji **Ładunki** znajdź i wybierz właśnie utworzony ładunek.
1. Wybierz **Zwolnienie \> Zwolnij do magazynu**.
1. Wybierz **OK** w oknie **Zwolnij do magazynu**, aby zwolnić wybrany ładunek do magazynu.

### <a name="verify-the-shipments-and-containers"></a>Weryfikowanie wysyłek i kontenerów

Następująca procedura umożliwia sprawdzenie utworzonych wysyłek. Użyj go do przejrzenia zamówienia, które utworzyłeś dla tego scenariusza, aby upewnić się, że uzyskałeś oczekiwane rezultaty.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Znajdź i wybierz wysyłkę utworzoną dla ładunku, który właśnie został zwolniony.
1. W okienku akcji otwórz kartę **Transport** i wybierz opcję **Wyświetl kontenery**.
1. Potwierdź, że pozycje z zamówień sprzedaży zostały skonteneryzowane do dwóch różnych pojemników.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konteneryzacja](wave-containerization.md)
