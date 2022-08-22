---
title: Wiekowanie pobierania z zapasów dla dyrektywy lokalizacji
description: W tym artykule wyjaśniono, jak używać strategii dyrektywy lokalizacji „pierwsze na wejściu, pierwsze na wyjściu” (FIFO) i „ostatnie na wejściu, pierwsze na wyjściu” (LIFO) podczas pobierania.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: fc4348f8207f4f6c8a0b694bc3e57beb29449a15
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219481"
---
# <a name="location-directive-inventory-picking-aging"></a>Wiekowanie pobierania z zapasów dla dyrektywy lokalizacji

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak używać strategii dyrektywy lokalizacji „pierwsze na wejściu, pierwsze na wyjściu” (FIFO) i „ostatnie na wejściu, pierwsze na wyjściu” (LIFO) podczas pobierania. Te strategie działają w połączeniu z datami wiekowania, które są rejestrowane dla lokalizacji w celu śledzenia, kiedy zapasy po raz pierwszy trafiły do magazynu. Funkcja *Wiekowanie pobierania z zapasów dla dyrektywy lokalizacji* używa daty w lokalizacji, aby ustalić wiekowanie. Funkcja *Stan lokalizacji w magazynie* aktualizuje datę w lokalizacji na podstawie daty ze numeru identyfikacyjnego.

Za pomocą strategii FIFO i LIFO można wysyłać zarówno towary śledzone wsadowo, jak i towary nieśledzone partiami, na podstawie daty wprowadzenia zapasów do magazynu. Ta możliwość może być szczególnie przydatna w przypadku nieśledzonych partii zapasów, gdy data wygaśnięcia nie jest dostępna do sortowania.

Gdy zapasy są najpierw odbierane lub tworzone w magazynie, system aktualizuje odpowiedni numer identyfikacyjny, tak aby data bieżąca była wyświetlana jako data wiekowania. Ta data jest następnie używana przez strategie dyrektywy lokalizacji do identyfikowania najstarszych lub najnowszych zapasów w magazynie. Jeśli zapasy są przenoszone do lokalizacji, która nie jest śledzona według numeru identyfikacyjnego, sama lokalizacja jest aktualizowana informacjami o przedawnieniu, a te informacje będą używane w strategiach.

## <a name="turn-on-the-feature"></a>Włączanie funkcji

Aby ta funkcja była dostępna, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) w kolejności:

1. *Stan lokalizacji w magazynie* (na podstawie wersji 10.0.29 ta funkcja jest domyślnie włączona. Aby uzyskać więcej informacji, zajrzyj do [Stan lokalizacji w magazynie](warehouse-location-status.md)).
1. *Wiekowanie pobierania z zapasów dla dyrektywy lokalizacji*

## <a name="feature-requirements"></a>Wymagania dotyczące funkcji

Aby można było używać tej funkcji, należy ustawić opcję **Włącz stan lokalizacji** na *Tak* dla każdego [profilu lokalizacji](tasks/create-location-profile.md) używanego do przechowywania zapasów. Aby skonfigurować tę opcję dla profilu lokalizacji, przejdź do **Zarządzanie magazynem \> Konfiguracja \> MagazynWarehouse \> Profile lokalizacji** i wybierz profil lokalizacji. Tę opcję można znaleźć na skróconej karcie **Ogólne**.

## <a name="feature-scenarios"></a>Scenariusze funkcji

Ta sekcja zawiera przykłady dotyczące konfigurowania strategii FIFO i LIFO oraz korzystania z nich.

> [!TIP]
> W tej sekcji znajdują się dwa scenariusze, jeden dla FIFO i jeden dla LIFO. W podanych procedurach przyjęto założenie, że obie scenariusze będą realizowane w kolejności. Zaleca się, aby były wykonywane obie scenariusze, co pozwala na uwzględnienie różnic między tymi dwoma strategiami.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tymi scenariuszami przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tych scenariuszy można również używać jako wskazówek dotyczących korzystania z danej funkcji podczas pracy w produkcji. Jednak w takim przypadku należy podstawić własne wartości dla każdego ustawienia opisanego w tym polu.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Konfiguracja scenariuszy

Dane demonstracyjne wymagają ustawień i korekt zapasów, które umożliwiają obsługę tych scenariuszy. Aby utworzyć dane magazynu wymagane do pracy z wykorzystaniem scenariuszy FIFO i LIFO, należy wykonać następujące kroki.

1. Zaloguj się do systemu, w którym są zainstalowane dane demonstracyjne i wybierz firmę **USMF**.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Z listy profilów lokalizacji wybierz opcję **PIĘTRO-05**.
1. Na skróconej karcie **Ogólne** ustaw opcje **Włącz stan lokalizacji** na *Tak*.
1. Wybierz opcję **Zapisz**.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. Z listy dyrektyw lokalizacji wybierz pozycję **63 Pobieranie konteneryzacji**.
1. Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** znajdź wiersz, gdzie pole **Identyfikator sekwencyjny** jest ustawione na *1* i wykonaj jeden z następujących kroków:

    - Jeśli konfigurujesz scenariusz FIFO, zmień wartość pola **Strategii** na *Wiekowanie lokalizacji FIFO*.
    - Jeśli konfigurujesz scenariusz LIFO, zmień wartość pola **Strategii** na *Wiekowanie lokalizacji LIFO*.

1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.
1. W oknie dialogowym kwerenda, na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz, a następnie określ następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Tabela pochodna:** *Lokalizacje*
    - **Pole:** *Identyfikator strefy*
    - **Kryteria:** *Piętro*

1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe zapytania.
1. Wybierz **Zapisz**, by zapisać zmiany w dyrektywie lokalizacji.
1. Na urządzeniu przenośnym lub w aplikacji *Dynamics 365 Supply Chain Management - Warehousing* na komputerze należy wykonać następujące kroki, aby usunąć istniejące zapasy z lokalizacji w magazynie w celu ich obsługi:

    1. Zaloguj się do magazynu *63*, używając odpowiedniego identyfikatora użytkownika i hasła.
    1. W menu głównym wybierz opcję **Jakość**.
    1. W menu **Zarządzanie jakością** wybierz **Odpadki**.
    1. Na stronie **Odpadki** zaznacz pole **LOC/LP**, a następnie wprowadź *63\_1*.
    1. Wybierz **Enter** lub **OK**.
    1. Potwierdź szczegóły **Odpadki** dla **Korekty**, wybierając **Enter** lub **OK**.

    Po skorygowaniu stanu zapasów w numerze identyfikacyjnym zostanie wyświetlony komunikat „praca wykonana”.

    Te kroki pozostawiają zapasy w dwóch lokalizacjach w danych demonstracyjnych. Każda lokalizacja ma inną datę wiekowania. Dla lokalizacji *FL-001* data wiekowania wynosi 15 kwietnia 2017, a lokalizacja *FL-002* ma datę wiekowania 29 stycznia 2017. W obu lokalizacjach znajdują się elementy *A0001*.

    Aby wyświetlić te dane, przejdź do **Zarządzanie zapasami \> Zapytania i raporty \> Lista dostępnych**, a następnie filtruj w magazynie *63* pozycję *A0001*. W wierszach, w których pole **Lokalizacja** jest ustawione na *FL-001* lub *FL-002*, wybierz wiersz mający dodatnią wartość **Zapasów fizycznych**, a następnie w okienku akcji wybierz opcję **Transakcje**. W polu **Data fizyczna** zostanie wyświetlona data odpowiadająca jednej z wyżej wymienionych dat wiekowania.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>Scenariusz 1: Konfigurowanie i używanie przedawnienia lokalizacji FIFO

Strategia FIFO znajduje lokalizację, która zawiera najstarszą datę wiekowania, oraz przydziela pobieranie na podstawie tej daty wiekowania.

1. Jeśli jeszcze tego nie zrobiono, należy [przygotować przykładowe dane](#demo-set-up) wymagane w tym scenariuszu.
1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-001*.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *63*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. To zawiera pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**. W tym wierszu zamówienia ustaw pole **Numer pozycji** na wartość *A0001* oraz pole **Ilość** na *1*.
1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną zamówioną ilość pozycji z zapasów z wybranego magazynu.
1. Zamknij stronę **Rezerwacja**.
1. Na stronie **Zamówienie sprzedaży** w okienku akcji na karcie **Magazyn** wybierz grupę **Akcje** i wybierz **Zwolnij do magazynu**. Zostanie wyświetlony komunikat. System tworzy wysyłkę, dodaje ją do nowego ładunku i tworzy wymaganą pracę.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** w menu **Magazyn** wybierz opcję **Szczegóły pracy**, aby otworzyć pracę utworzoną dla tego zamówienia sprzedaży. Zwróć uwagę, że wiersz, w którym wartość **Typ pracy** to *Pobranie*, wskazuje wartość **Lokalizacja** jako *FL-002*. Ta lokalizacja zawiera numer identyfikacyjny, który ma najstarszą datę wiekowania (FIFO).
1. Wybierz **Magazyn \> Szczegóły wysyłki**.
1. Na skróconej karcie **Ogólne** zauważ identyfikator grupy czynności, aby można było z niej skorzystać w scenariuszu 2.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>Scenariusz 2: Konfigurowanie i używanie przedawnienia lokalizacji LIFO

Strategia LIFO znajduje lokalizację, która zawiera najnowszą datę wiekowania, oraz przydziela pobieranie na podstawie tej daty wiekowania. W scenariuszu 2 zostanie wyedytowana konfiguracja scenariusza 1 (FIFO) i ponownie użyte zamówienie sprzedaży i grupy czynności, które zostały utworzone w tym scenariuszu.

1. Przed rozpoczęciem tego scenariusza należy skonfigurować i wykonać pełny scenariusz FIFO zgodnie z opisem w [poprzedniej sekcji](#fifo-demo). W tym scenariuszu będzie można ponownie użyć grupy czynności i większość ustawień utworzonych dla tego scenariusza.
1. Edytuj dyrektywę lokalizacji **63 Pobieranie konteneryzacji**, aby była używana strategia *Wiekowania lokalizacji LIFO*, jak to opisano w pierwszej części [Konfiguracja scenariuszy](#demo-set-up).

    Następnie zostanie zmodyfikowana fala utworzona dla zamówienia sprzedaży w scenariuszu 1, dzięki czemu jest używana strategia *Wiekowania lokalizacji LIFO*.

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz i otwórz grupę czynności, która zawiera zamówienie utworzone dla scenariusza FIFO.
1. W okienku akcji na karcie **Praca** wybierz opcję **Anuluj**, aby anulować pracę utworzoną dla scenariusza FIFO.
1. W okienku akcji na karcie **Grupa czynności** w grupie **Grupa czynności** wybierz opcję **Przetwórz**.
1. Po zakończeniu przetwarzania w okienku akcji na karcie **Grupa czynności**, w grupie **Informacje pokrewne** wybierz opcję **Praca**, aby otworzyć utworzoną pracę dla tej grupy czynności.
1. Na stronie **Praca** na karcie **Omówienie** powinny być dwa wiersze. Znajdź wiersz, w którym pole o nazwie **Stan pracy** ma wartość *Otwarte*.
1. Zwróć uwagę, że wiersz, w którym wartość **Typ pracy** to *Pobranie*, wskazuje wartość **Lokalizacja** jako *FL-001*. Ta lokalizacja zawiera numer identyfikacyjny, który ma najnowszą datę wiekowania (LIFO).

W tych scenariuszach można było zobaczyć, jak strategia wiekowania lokalizacji kieruje pracę do lokalizacji zapasów, w której znajdują się najstarsze lub najnowsze zapasy, w zależności od wybranej strategii.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
