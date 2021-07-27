---
title: Tworzenie zamówień przeniesienia z aplikacji magazynu
description: W tym temacie opisano sposób tworzenia i przetwarzania zamówień przeniesienia z funkcji aplikacji Warehouse Management
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: fe5983d40033c0cd15674815067eaa969e97d38b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343632"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Tworzenie zamówień przeniesienia z aplikacji magazynu

[!include [banner](../includes/banner.md)]

Ta funkcja umożliwia pracownikom magazynu tworzenie i przetwarzanie zamówień przeniesienia bezpośrednio z poziomu aplikacji Warehouse Management. Pracownik rozpoczyna od wybrania magazynu docelowego i może skanować jeden lub więcej numerów identyfikacyjnych za pomocą aplikacji, aby dodać je do zamówienia przeniesienia. Gdy pracownik magazynu wybierze **Zakończ zamówienie**, zadanie wsadowe utworzy wymagane zamówienie przeniesienia i wiersze zamówienia na podstawie dostępnych zapasów zarejestrowanych dla tych numerów identyfikacyjnych.

## <a name="enable-the-create-transfer-orders-from-the-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Włączanie tworzenia zamówień przeniesienia z funkcji aplikacji magazynowej

Aby móc używać tej funkcji, musi zostać włączona w systemie razem z warunkami wstępnymi. Administratorzy mogą skorzystać ze strony [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby.

1. Najpierw włącz funkcję [zdarzeń aplikacji magazynu procesów](warehouse-app-events.md), która jest widoczna w obszarze [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) jako:
    - **Moduł** - Zarządzanie magazynem
    - **Nazwa funkcji** - Przetwarzanie zdarzeń aplikacji magazynu
1. Następnie włącz funkcję *Utwórz zamówienia przeniesienia z poziomu aplikacji magazynowej*, która jest widoczna jako:
    - **Moduł** - Zarządzanie magazynem
    - **Nazwa funkcji** — tworzenie i przetwarzanie zamówień przeniesienia z aplikacji magazynowej
1. Aby zautomatyzować przetwarzanie wydań wychodzących, należy również włączyć funkcję [Potwierdź wychodzące wysyłki z zadań wsadowych](confirm-outbound-shipments-from-batch-jobs.md). Ta funkcja jest wyświetlana jako:
    - **Moduł** - Zarządzanie magazynem
    - **Nazwa funkcji** — potwierdzanie wychodzących wysyłek z zadań wsadowych

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Konfigurowanie elementu menu urządzenia przenośnego do tworzenia zamówień przeniesienia

Poniżej przedstawiono ogólne wskazówki dotyczące konfigurowania elementu menu urządzenia przenośnego do tworzenia zamówienia przeniesienia. W zależności od wymagań biznesowych dotyczących poziomu automatyzacji, który ma być ustawiany, gdy użytkownicy tworzą zamówienia przeniesienia z produkcji, zostaną włączone różne konfiguracje. Scenariusz w tym dokumencie opisuje taką konfigurację.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Wybierz pozycję **Nowy**, aby dodać nową pozycję menu. Następnie wprowadź następujące ustawienia, aby rozpocząć:

    - **Nazwa elementu menu** — przypisz nazwę w takiej postaci, w jakiej powinna się ona pojawiać w Supply Chain Management.
    - **Tytuł** — przypisz nazwę menu w takiej postaci, w jakiej powinna się pojawić w aplikacji Warehouse Management.
    - **Tryb** — wybierz ustawienie *Pośrednie* (ta pozycja menu nie utworzy pracy).
    - **Kod działania** — wybierz ustawienie *Utwórz zamówienia przeniesienia na podstawie numerów identyfikacyjnych*, aby umożliwić pracownikom magazynowym tworzenie zamówienia przeniesienia na podstawie jednego lub większej liczby zeskanowanych numerów identyfikacyjnych.

1. Użyj ustawienia **Zasady tworzenia wierszy zamówienia przeniesienia**, aby określić sposób tworzenia wierszy zamówienia przeniesienia dla tego elementu menu. Linie zostaną utworzone/zaktualizowane na podstawie dostępnych zapasów zarejestrowanych dla zeskanowanych numerów identyfikacyjnych. Wybierz jedną z następujących wartości:

    - **Brak rezerwacji** — wiersze zamówienia przeniesienia nie zostaną zarezerwowane.
    - **Numer identyfikacyjny z rezerwacją wiersza** — wiersze zamówienia przeniesienia zostaną zarezerwowane i będzie używana opcja strategii opartej na numerze identyfikacyjnym, w której są przechowywane odpowiednie identyfikatory numerów identyfikacyjnych skojarzonych z wierszami zamówień. Dlatego wartości identyfikatora zlokalizowanego numeru identyfikacyjnego mogą być używane jako część procesu tworzenia pracy dla wierszy zamówienia przeniesienia.

1. Aby w razie potrzeby bardziej zautomatyzować proces wysyłki wychodzących zamówień przeniesienia można skorzystać z ustawienia **Zasady wysyłki wychodzącej**. Gdy pracownik wybierze przycisk **Zakończ zamówienie**, aplikacja utworzy zdarzenie aplikacji magazynowej *Zakończ zamówienie*”, które zapisze wartość wybraną tutaj w polu **Zasady wysyłki wychodzącej**” dla każdego wiersza w bieżącym zamówieniu przeniesienia. Później, gdy kolejka zdarzeń jest przetwarzana przez zadanie wsadowe w celu utworzenia zamówienia przeniesienia, wartość przechowywana w tym polu może zostać odczytana przez zadanie wsadowe i dlatego może ona określać sposób przetwarzania każdego wiersza przez zadanie. Wybierz jedną z następujących opcji:

    - **Brak** — nie jest wykonywane automatyczne przetwarzanie.
    - **Zwolnienie do magazynu** — automatyzuje proces zwolnienia do magazynu.
    - **Potwierdzenie wysyłki** — automatyzuje proces potwierdzenia wysyłki.
    - **Zwolnienie i potwierdzenie wysyłki** — automatyzuje zarówno zwolnienie do magazynu, jak i proces potwierdzenia wysyłki.

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>Dodawanie elementu menu urządzenia przenośnego do menu

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Wybierz opcję **Edycja**.
1. Wybierz istniejące menu po wybraniu nowego elementu menu w obszarze **Dostępne menu i elementy menu**. Dodaj element menu, wybierając przycisk ze strzałką w prawo.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Tworzenie zamówienia przeniesienia na podstawie numerów identyfikacyjnych

Aplikacja Warehouse Management ma prosty proces tworzenia zamówień przeniesienia na podstawie numerów identyfikacyjnych. W tym celu pracownik wykonuje następujące czynności, korzystając z aplikacji Warehouse Management:

1. Utwórz zamówienie przeniesienia i określ magazyn docelowy.
1. Wybierz każdy numer identyfikacyjny do wysłania.
1. Wybierz opcję **Zakończ zamówienie**.

>[!NOTE]
> Wielu pracowników może przypisywać numery identyfikacyjne przeznaczone dla tego samego zamówienia przeniesienia za pomocą przycisku **Wybierz zamówienie przeniesienia**, aby wybrać istniejący, nieprzetworzony numer zamówienia przeniesienia z kolejki zdarzeń aplikacji magazynowej. Aby uzyskać informacje na temat wyszukiwania wartości numerów zamówień przeniesienia, zobacz temat [Informacje o zdarzeniach aplikacji magazynowej](#inquire-the-warehouse-app-events).

## <a name="example-scenario"></a>Przykładowy scenariusz

Ten scenariusz umożliwia przegląd procesu tworzenia i automatycznego przetwarzania zamówień przeniesienia na podstawie dostępnych zapasów zarejestrowanych w wybranych numerach identyfikacyjnych.

Aby zrealizować ten scenariusz przy użyciu sugerowanych wartości, należy pracować w systemie z zainstalowanymi danymi demonstracyjnymi i wybrać firmę *USMF* przed rozpoczęciem.

W tym scenariuszu zakłada się, że włączono już funkcje [Tworzenie i przetwarzanie zamówień przeniesienia z funkcji aplikacji magazynowej](#enable-create-transfer-order-from-warehouse-app) i [przetwarzanie zdarzeń aplikacji magazynowej](warehouse-app-events.md).

Oprócz konfiguracji tworzenia zamówienia przeniesienia w elementach menu urządzeń przenośnych należy również skonfigurować i włączyć obsługę dodatkowych szablonów, dyrektyw lokalizacji i zadań wsadowych.

### <a name="example-scenario-blueprint"></a>Przykładowy plan scenariusza

Użytkownik jest sprzedawcą detalicznym i ma wiele numerów identyfikacyjnych, z których każda zawiera różne towary umieszczone w określonym miejscu w jednym z magazynów (*Magazyn 51*). Użytkownik chce włączyć proces, który umożliwi pracownikom tworzenie zamówienia przeniesienia do innego magazynu (*Magazyn 61*) dla zbioru zeskanowanych numerów identyfikacyjnych. Zamówienie przeniesienia zostanie automatycznie wysłane i zaktualizowane dopiero po zidentyfikowaniu ostatniego numeru identyfikacyjnego zamówienia.

![Przykład automatycznego przetwarzania zamówienia przeniesienia.](media/create-transfer-order-from-app-example.png "Przykład automatycznego przetwarzania zamówienia przeniesienia")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Tworzenie elementu menu urządzenia przenośnego do tworzenia zamówień przeniesienia

W tej sekcji opisano sposób tworzenia nowego elementu menu urządzenia przenośnego do tworzenia zamówień przeniesienia. Ustaw opcję **Tryb** na *Pośredni* i **Kod działania** na *Utwórz zamówienia przeniesienia na podstawie numerów identyfikacyjnych*.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa elementu menu** wprowadź nazwę *Utwórz ZP*.
1. W polu **Tytuł** wprowadź opis *Utwórz ZP*.
1. W polu **Tryb** wybierz opcję *Pośredni*.
1. W polu **Kod działania** wybierz opcję *Utwórz zamówienie przeniesienia na podstawie numerów identyfikacyjnych*.
1. W obszarze **Zasady tworzenia wierszy zamówień** wybierz opcję *Numer identyfikacyjny z rezerwacją wiersza*.
1. W obszarze **Zasadach wysyłki wychodzącej** wybierz opcję *Zwolnienie i potwierdzenie wysyłki*.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Wybierz opcję **Edycja**.
1. Wybierz istniejące menu menu **Zapasy** , a następnie nowy elementu menu w obszarze **Dostępne menu i elementy menu**. Dodaj element menu do menu **Zapasy**, wybierając przycisk ze strzałką w prawo.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Konfigurowanie szablonów pracy do automatycznego przetwarzania i przerywania pracy przez zlokalizowany numer identyfikacyjny

W tej sekcji opisano sposób włączania szablonu pracy w celu automatycznego przetwarzania pracy utworzonej przez szablon podczas zwalniania grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W polu **Typ zlecenia pracy** wybierz pozycję *Wydanie przeniesienia*.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy szablon pracy.
1. W polu **Szablon pracy** wprowadź *51 Automatyczne przetwarzanie numeru identyfikacyjnego*.
1. W polu **Opis szablonu pracy** wprowadź *51 Automatyczne przetwarzanie numeru identyfikacyjnego*.
1. Zaznacz pole wyboru **Przetwarzaj automatycznie**. Należy zaznaczyć tę opcję, aby można było przetwarzać dowolne kroki automatyzacji.
1. W danych demonstracyjnych istnieje już szablon pracy *51 Przeniesienie*, edytuj pole **Numer kolejny** tak, aby nowy szablon pracy miał niższy numer kolejny niż istniejący szablon pracy *51*.
1. Wybierz opcję **Zapisz** na pasku narzędzi, aby włączyć skróconą kartę **Szczegóły szablonu pracy**.
1. Na skróconej karcie **Szczegóły szablonu pracy** wybierz opcję **Nowy** na pasku narzędzi. Dodasz dwa wiersze.
1. W polu **Typ pracy** zaznacz opcję *Pobierz*.
1. W polu **Identyfikator klasy pracy** wybierz pozycję *TransfOut*.
1. Wybierz opcję **Nowy** na pasku narzędzi **Szczegóły szablonu pracy**.
1. W polu **Typ pracy** zaznacz opcję *Odłożenie*.
1. W polu **Identyfikator klasy pracy** wybierz pozycję *TransfOut*.
1. Wybierz opcję **Zapisz**, aby włączyć pole **Kod dyrektywy**.
1. W wierszu **Typ pracy** *Odłożenie* wybierz pozycję **Kod dyrektywy** *Brama dokowa*. Upewnij się, że ten nowy szablon pracy ma najniższy **Numer kolejny**.
1. Na pasku narzędzi wybierz opcję **Edytuj kwerendę**, aby otworzyć edytor kwerend.
1. Na karcie **Zakres** wybierz **Dodaj**.
1. W dodanym wierszu, w obszarze **Pole** wybierz *Magazyn*.
1. W polu **Kryteria** wybierz opcję *51*.
1. Wybierz kartę **Sortowanie**.
1. Wybierz opcję **Dodaj** i ustaw opcję **Pole** na *Identyfikator zlokalizowanego numeru identyfikacyjnego*. Zaznaczenie tego pola spowoduje włączenie na pasku narzędzi przycisku **Podziały nagłówka pracy**.
1. Wybierz **OK**, a następnie **Tak**, aby zresetować grupowanie i powrócić do strony **Szablony pracy**.
1. Wybierz **Podziały nagłówka pracy** i włącz ustawienie **Grupuj według tego pola** dla opcji **Identyfikator zlokalizowanego numeru identyfikacyjnego** i zamknij.

> [!NOTE]
> Nie wszystkie ustawienia mogą być przetwarzane automatycznie, na przykład dla towarów w ilości efektywnej i na potrzeby mieszanych wymiarów śledzenia.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Konfigurowanie dyrektyw lokalizacji dla strategii opartej na numerze identyfikacyjnym

W tej sekcji opisano sposób konfigurowania procesu pobrania dyrektywy lokalizacji w celu użycia strategii **Oparta na numerze identyfikacyjnym**.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. Wybierz opcję **Edycja**.
1. W nagłówku listy nawigacji wybierz **Typ zlecenia produkcyjnego** *Wydanie przeniesienia*.
1. Z listy nawigacji wybierz istniejącą dyrektywę lokalizacji **51 Pobranie ZP**.
1. Na skróconej karcie **Wiersze** zaznacz pole wyboru **Zezwalaj na podział**.
1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz nowej akcji.
1. W polu **Nazwa** wpisz *Oparta na NI*.
1. W polu **Strategia** wybierz *Oparta na numerze identyfikacyjnym*. Ta akcja wymaga najniższego numeru kolejnego.
1. Wybierz **Zapisz** na pasku narzędzi.
1. Wybierz ikonę **Odśwież stronę** z paska narzędzi.
1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz *TOPick*.
1. Na pasku narzędzi **Akcje dyrektywy lokalizacji** wybierz opcję **Przenieś w dół**, aby zmienić numer kolejny na większy niż numer właśnie utworzonego działania *Oparta na NI*.

> [!NOTE]
> Strategia oparta na numerach identyfikacyjnych będzie próbować zarezerwować i utworzyć pracę pobrania w odniesieniu do lokalizacji przechowujących żądane numery identyfikacyjne, które zostały skojarzone z wierszami zamówienia przeniesienia. Jeśli nie jest to możliwe, a mimo to chcesz utworzyć pracę pobrania, wróć do innej strategii dotyczącej akcji dyrektywy lokalizacji i wyszukaj zapasy w innym obszarze magazynu, w zależności od potrzeb procesu biznesowego.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Umożliwia konfigurowanie zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowych

W tej sekcji opisano sposób konfigurowania zaplanowanego zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowej.

1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie zdarzeń aplikacji magazynu**.
2. W oknie dialogowym włącz opcję **Przetwarzanie wsadowe** w sekcji **Uruchom w tle**.
3. Wybierz opcję **Cykl** i skonfiguruj zadanie wsadowe do przetwarzania na podstawie interwału potrzebnego dla firmy.
4. Wybierz przycisk **OK**, aby powrócić do głównego okna dialogowego.
5. Wybierz **OK** w głównym oknie dialogowym, aby dodać zadanie do kolejki przetwarzania wsadowego.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Ustawianie zadań wsadowych w celu automatycznego zwalniania zamówień przeniesienia

W tej sekcji opisano sposób konfigurowania zaplanowanego zadania wsadowego w celu zwolnienia zamówień przeniesienia oznaczonych jako „gotowe do zwolnienia”.

1. Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Automatyczne zwalnianie zamówień przeniesienia**.
1. W oknie dialogowym rozwiń sekcję **Rekordy do uwzględnienia**.
1. Wybierz **Filtr** w sekcji **Rekordy do uwzględnienia**.
1. Na stronie zapytania **WHSTransferAutoRTWQuery**, karta **Zakres**, wybierz opcję **Dodaj**, aby dodać nowy wiersz do zapytania.
1. W polu **Tabela** nowego wiersza wybierz menu rozwijane i wybierz tabelę **Przenieś zwolnienie linii do magazynu**.
1. Z menu rozwijanego **Pole** wybierz **Zasady wysyłki wychodzącej**.
1. W polu **Kryteria** wybierz opcję **Zwolnienie i potwierdzenie wysyłki**.
1. W wierszu, gdzie opcja **Pole** jest ustawiona na wartość *Z magazynu*, w polu **Kryterium** wybierz opcję *51*.
1. Wybierz przycisk **OK**, aby powrócić do głównego okna dialogowego.
1. Rozwiń sekcję **Uruchom w tle**, aby skonfigurować przetwarzanie wsadowe.
1. Włącz opcję **Przetwarzanie wsadowe** w sekcji **Uruchom w tle**.
1. Wybierz opcję **Cykl** i skonfiguruj zadanie wsadowe do przetwarzania na podstawie interwału potrzebnego dla firmy.
1. Wybierz przycisk **OK**, aby powrócić do głównego okna dialogowego.
1. Wybierz **OK** w głównym oknie dialogowym, aby dodać zadanie wsadowe do kolejki przetwarzania wsadowego.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>Konfigurowanie zadania wsadowego „Przetwarzanie wysyłek wychodzących”

W tej sekcji opisano sposób konfigurowania zaplanowanego zadania wsadowego w celu uruchomienia potwierdzenia wysyłki wychodzącej dla ładunków gotowych do wysłania dotyczących wierszy zamówienia przeniesienia, które są „gotowe do wysyłki".

1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie przesyłek wychodzących**.
1. Rozwiń sekcję **Rekordy do uwzględnienia**.
1. Wybierz **Filtry**.
1. W kwerendzie **WHSLoadShipConfirm** wybierz kartę **Sprzężenia**.
1. Rozwiń hierarchię tabel, tak rozwinąć kategorie **Ładunki** i **Szczegóły ładunku**.
1. Kliknij tabelę **Szczegóły ładunku**.
1. Wybierz przycisk **Dodaj sprzężenie tabeli**.
1. Na liście relacji tabeli odfiltruj lub wyszukuj w kolumnie **Relacja** pozycję *Wiersze zamówienia przeniesienia (odwołanie)*.
1. Ustaw fokus na relacji tabeli na liście, a następnie naciśnij przycisk **Wybierz**.
1. Wybierz tabelę **Wiersze zamówienia przeniesienia**.
1. Wybierz przycisk **Dodaj sprzężenie tabeli**.
1. Na liście relacji tabeli odfiltruj lub wyszukuj w kolumnie **Relacja** pozycję *Odwróć przeniesienie dodatkowych pól (Identyfikator rekordu)*.
1. Ustaw fokus na relacji tabeli na liście, a następnie naciśnij przycisk **Wybierz**.
1. Kliknij kartę **Zakres**.
1. W tabelach kwerendy **Zakres** ustawisz trzy zakresy kryteriów kwerendy. Wybierz przycisk **Dodaj**, aby dodać drugi wiersz.
1. Dodaj zakres dla tabeli **Ładunki**. Ustaw **Pole** na *Stan ładunku* i **Kryteria** na *Załadowane*.
1. Dodaj kolejny zakres dla tabeli **Odwróć przeniesienie dodatkowych pól**. Ustaw **Pole** na *Zasady wysyłki wychodzącej* i **Kryteria** na *Zwolnienie i potwierdzenie wysyłki*.
1. Dodaj kolejny zakres dla tabeli **Szczegóły ładunku**. Ustaw **Pole** na *Odwołanie* i **Kryteria** na *Wysyłka zamówienia przeniesienia*.
1. Wybierz przycisk **OK**, aby powrócić do głównego okna dialogowego.
1. Rozwiń sekcję **Uruchom w tle**.
1. Włącz **Przetwarzanie wsadowe**.
1. Wybierz opcję **Cykl** i skonfiguruj zadanie wsadowe do przetwarzania na podstawie interwału potrzebnego dla firmy.
1. Wybierz przycisk **OK**, aby powrócić do głównego okna dialogowego.
1. Wybierz **OK** w głównym oknie dialogowym, aby dodać zadanie wsadowe do kolejki przetwarzania wsadowego.

> [!NOTE]
> Aby uzyskać więcej informacji, zajrzyj do formularza [Potwierdź wysyłki wychodzące z zadań wsadowych](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Przetwarzanie przykładu „Tworzenie zamówienia przeniesienia z poziomu aplikacji magazynowej”

### <a name="add-on-hand-on-a-license-plate"></a>Dodawanie stanu zapasów do numeru identyfikacyjnego

Jako punkt wyjścia w tym scenariuszu potrzebny będzie numer identyfikacyjny zawierający fizycznie dostępne zapasy.

| Towar | Magazyn | Stan zapasów | Lokalizacja | Numer identyfikacyjny | Ilość |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Dostępna | LP-010 | LP10 | 1 |
| A0002 | 51 | Dostępna | LP-010 | LP10 | 2 |

Dodaj ilość dostępnych fizycznie zapasów przy użyciu następujących wartości:

> [!NOTE]
> Konieczne będzie utworzenie numeru identyfikacyjnego i użycie lokalizacji, które umożliwiają przewóz mieszanych towarów, takich jak LP-010.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Tworzenie i przetwarzanie zamówień przeniesienia z aplikacji magazynowej

1. Otwórz aplikację i zaloguj się jako użytkownik *51*. Bieżącym magazynem użytkownika będzie 51.
1. Wybierz element menu **Utwórz ZP** z lokalizacji menu, do której go dodano podczas konfiguracji.
1. Rozpocznij tworzenie zamówienia przeniesienia przez wprowadzenie magazynu docelowego (magazynu docelowego) w polu **Magazyn**, wprowadź *61*. Nowe zamówienie przeniesienia zostanie zrealizowane z bieżącego magazynu 51 (magazynu źródłowego) do magazynu docelowego *61*.
1. Kliknij przycisk **OK**.
1. Zeskanuj identyfikator numeru identyfikacyjnego w polu **Numer identyfikacyjny**. Wprowadź numer identyfikacyjny zapasów dodany we wcześniejszym kroku, *LP10*.
1. Kliknij przycisk **OK**.
1. Wybierz przycisk menu, a następnie wybierz opcję **Zakończ zamówienie**, aby sfinalizować tworzenie zamówienia przeniesienia w aplikacji magazynowej.

W tym przykładzie używane są dwa **zdarzenia aplikacji magazynowych** (*Tworzenie zamówienia przeniesienia* i *Zakończ zamówienie przeniesienia*).

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Uzyskiwanie informacji o zdarzeniach aplikacji magazynowej

Komunikaty dotyczące kolejki zdarzeń i zdarzeń generowane przez aplikację Warehouse Management można przeglądać, przechodząc do **Zarządzanie magazynem \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Zdarzenia aplikacji magazynu**.

Komunikaty zdarzenia *Tworzenie zamówienia przeniesienia* uzyskają stan *Oczekujące*, co oznacza, że zadanie wsadowe **Przetwarzanie zdarzeń aplikacji magazynowej** nie będzie odbierać i przetwarzać komunikatów zdarzeń. Jeśli komunikat zdarzenia zostanie zaktualizowany do stanu *W kolejce*, zadanie wsadowe przetworzy zdarzenia. Będzie to mieć miejsce w tym samym czasie co tworzenie zdarzenia *Zakończ zamówienie przeniesienia* (gdy pracownik wybierze przycisk **Zakończ zamówienie** w aplikacji Warehouse Management). Po przetworzeniu komunikatów o zdarzeniach *Tworzenia zamówienia przeniesienia* stan jest aktualizowany na *Zakończone* lub *Niepowodzenie*. Jeśli stan *Zakończ zamówienie przeniesienia* zostanie zmieniony na *Zakończone*, wszystkie powiązane ze sobą zdarzenia zostaną usunięte z kolejki.

Ponieważ **Zdarzenia aplikacji magazynowej** dotyczące tworzenia danych zamówienia przeniesienia nie będą przetwarzane przez zadanie wsadowe, zanim komunikat zostanie zaktualizowany do stanu *W kolejce*, trzeba będzie wyszukać żądane numery zamówień przeniesienia jako część pola **Identyfikator**. Pole **Identyfikator** znajduje się w nagłówku strony **Zdarzenia aplikacji magazynowej**.

W ramach przetwarzania zdarzenia magazynu tworzenie wiersza zamówienia przeniesienia może się nie powieść. W takim przypadku stan komunikatu zdarzenia jest aktualizowany do *Niepowodzenie* i można skorzystać z informacji **dziennika przetwarzania wsadowego**, aby dowiedzieć się, dlaczego i podjąć działania w celu rozwiązania problemów.

Typowe problemy mogą być związane z brakującą konfiguracją procesu, np. z brakującym magazynem tranzytowym dla zdarzenia *Tworzenie zamówienia przeniesienia*. W takim przykładzie można dodać magazyn tranzytowy do magazynu wysyłki i skorzystać z opcji **Resetuj** w celu zmiany stanu wszystkich komunikatów zdarzeń aplikacji magazynowej z *Niepowodzenie* na *W kolejce*, co oznacza, że zadanie wsadowe będzie przetwarzać komunikaty zdarzeń ponownie po dokonaniu korekty danych konfiguracyjnych.

W środowiskach produkcyjnych wyjątki będą bardziej powiązane z procesem, np. żądanie numeru identyfikacyjnego, który w czasie przetwarzania zadania wsadowego jest pusty i dlatego nie są tworzone wiersze zamówienia przeniesienia. Ten komunikat zdarzenia zakończonym niepowodzeniem można usunąć za pomocą opcji **Usuń** albo można dodać wymagane fizyczne zapasy do numeru identyfikacyjnego i użyć opcji **Resetuj** dla wszystkich powiązanych komunikatów zdarzeń.

Aby uzyskać więcej informacji, zobacz temat [Przetwarzania zdarzeń aplikacji magazynowej](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>Kolejne czynności dotyczące przetwarzania przykładowego scenariusza

Podczas tego scenariusza zaszły następujące zdarzenia:

1. Za pomocą aplikacji Warehouse Management wybrano element menu, w którym jest używany kod działania **Tworzenie zamówienia przeniesienia z numerów identyfikacyjnych**.
1. W aplikacji został wyświetlony monit o wybranie magazynu docelowego dla zamówienia przeniesienia. Magazyn źródłowy jest zawsze tym, który jest obecnie zalogowany pracownik.
1. W przypadku wybrania magazynu docelowego system zarezerwował numer identyfikacyjny dla nadchodzącego zamówienia przeniesienia (na podstawie kolejnych numerów zamówień przeniesienia zdefiniowanych w systemie), ale nie utworzył jeszcze zamówienia przeniesienia.
1. Podczas skanowania numeru identyfikacyjnego *LP10* zawierającego dostępne zapasy, które powinny zostać przeniesione do nowego magazynu **zdarzenie aplikacji magazynowej** zostało dodane do kolejki zdarzeń w celu późniejszego przetworzenia. Zdarzenie magazynu zawierało szczegółowe informacje dotyczące skanowania, w tym numer zamierzonego zamówienia przeniesienia.
1. W aplikacji Warehouse Management po wybraniu przycisku **Zakończ zamówienie** zostało utworzone nowe zdarzenie aplikacji magazynowej **Zakończ zamówienie przeniesienia** oraz powiązane z nim zdarzenie, a opcja **Tworzenie zamówienia przeniesienia** zmieniło stan na **W kolejce**.
1. W zapleczu **Zadanie wsadowe Przetwarzaj zdarzenia aplikacji magazynowej** pobrało zdarzenie **W kolejce**, a następnie zebrało dostępne zapasy związane z zeskanowanym numerem identyfikacyjnym. Na podstawie stanu dostępnych zapasów utworzono rekord rzeczywistego zamówienia przeniesienia i powiązane wiersze. Zadanie wypełniło również pole **Zasady wysyłki wychodzącej** dla zamówienia przeniesienia z wartością opartą na konfiguracji *Zwolnienie i potwierdzenie wysyłki* i powiązało numer identyfikacyjny z wierszami strategii **Oparta na numerze identyfikacyjnym**.
1. Na podstawie wartości pola **Zasady wysyłki wychodzącej** kwerenda **zadanie wsadowe Automatyczne zwalnianie zamówień przeniesienia** zwolniło zamówienie przeniesienia do magazynu wysyłki. Z powodu konfiguracji używanych funkcji **Szablon grupy czynności**, **Szablon pracy** i **Dyrektywy lokalizacji** praca wykorzystała procesy automatyczne, co spowodowało aktualizację **Stan ładunku** na *Załadowane*.
1. **Zadanie wsadowe Przetwarzanie wysyłek wychodzących** jest wykonywane dla ładunku, co powoduje wysłanie zamówienia przeniesienia i wygenerowanie wcześniejszego zawiadomienia o wysyłce (ASN).
1. Harmonogram wszystkich tych zdarzeń zależy od ustawień **Cykl** dla utworzonych zadań wsadowych.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="mobile-device-menu-item-setup"></a>Konfigurowanie elementu menu urządzenia przenośnego

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>Dlaczego nie widzę opcji „Utwórz zamówienie przeniesienia z numeru identyfikacyjnego” na liście rozwijanej elementu menu działania?

Funkcja *Tworzenie i przetwarzanie zamówień przeniesienia z aplikacji magazynowej* musi być włączona. Aby uzyskać więcej informacji, zobacz temat [Włączanie tworzenia zamówień przeniesienia z aplikacji magazynowej](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-management-mobile-app-processes"></a>Procesy aplikacji mobilnej Zarządzanie magazynem

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>Dlaczego nie widzę przycisku menu „Zakończ zamówienie"?

Do zamówienia przeniesienia musi być przypisany co najmniej jeden numer identyfikacyjny.

#### <a name="can-several-warehouse-management-mobile-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>Czy kilku użytkowników aplikacji Warehouse Management może jednocześnie dodawać numery identyfikacyjne do tego samego zamówienia przeniesienia?

Tak, kilku pracowników magazynu może skanować numery identyfikacyjne w tym samym zamówieniu przeniesienia.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>Czy ten sam numer identyfikacyjny może zostać dodany do różnych zamówień przeniesienia?

Nie, w danym momencie numer identyfikacyjny może być dodany tylko do jednego zamówienia przeniesienia.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>Czy po wybraniu przycisku „Zakończ zamówienie” można dodać więcej numerów identyfikacyjnych dla tego zamówienia przeniesienia?

Nie, do zamówienia przeniesienia ze zdarzeniem aplikacji magazynowej **Zakończ zamówienie przeniesienia** nie można dodać kolejnych numerów identyfikacyjnych.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-management-mobile-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>Jak można znaleźć istniejące zamówienia przeniesienia, które mają być używane za pośrednictwem przycisku „Wybierz zamówienie przeniesienia” w aplikacji Warehouse Management, jeśli zamówienie nie zostało jeszcze utworzone w systemie wewnętrznej bazy danych?

Obecnie nie można wyszukiwać zamówień przeniesienia w aplikacji, ale można znaleźć numery zamówień przeniesienia na stronie **Zdarzenia aplikacji magazynowej**. Aby uzyskać więcej informacji, zobacz temat [Informacje o zdarzeniach aplikacji magazynowej](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-management-mobile-app"></a>Czy można ręcznie wybrać numer zamówienia przeniesienia, który ma być używany w aplikacji Warehouse Management?

Obsługiwane są tylko automatycznie generowane numery zamówień przeniesienia za pośrednictwem sekwencji numerów.

### <a name="background-processing"></a>Przetwarzanie w tle

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>Jak należy czyścić rekordy w tabelach komunikatów kolejek zdarzeń aplikacji magazynowej?

Można je wyświetlić i zachować na stronie **Zdarzenia aplikacji magazynowej**. Aby uzyskać więcej informacji, zobacz temat [Informacje o zdarzeniach aplikacji magazynowej](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>Dlaczego zamówienie przeniesienia „Data przyjęcia” nie jest aktualizowane zgodnie z konfiguracją „Kontrola daty dostawy"?

Zamówienia przeniesienia są tworzone bez użycia funkcji **Kontrola daty dostawy**.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>Czy mogę wykorzystać numer identyfikacyjny, w którym dostępne są fizyczne ujemne zapasy?

Funkcja obsługuje tylko dodatnie fizyczne ilości na stanie na poziomie numeru identyfikacyjnego, ale można mieć fizyczne ujemne ilości na stanie na wyższych poziomach magazynu i stanu magazynowego podczas przypisywania numerów do zleceń transferu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]