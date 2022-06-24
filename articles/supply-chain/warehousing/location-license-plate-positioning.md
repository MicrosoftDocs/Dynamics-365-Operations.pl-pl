---
title: Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji
description: Funkcja Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji pozwala sprawdzić, gdzie w lokalizacji wielopaletowej znajduje się dany numer identyfikacyjny, np. gdy w lokalizacji używane są szafki na palety o podwójnej głębokości.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: e52b313e0a00c04edf9003aa6292146936f837d4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889436"
---
# <a name="location-license-plate-positioning"></a>Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji

[!include [banner](../includes/banner.md)]

Funkcja Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji pozwala sprawdzić, gdzie w lokalizacji wielopaletowej znajduje się dany numer identyfikacyjny, np. gdy w lokalizacji używane są szafki na palety o podwójnej głębokości.

Ta funkcja dodaje numer sekwencyjny do każdego numeru identyfikacyjnego, który jest umieszczany w lokalizacji przechowywania. Ten numer sekwencyjny służy do porządkowania numerów identyfikacyjnych w lokalizacji magazynu. Z tego względu funkcja ta inteligentnie obsługuje scenariusze, w których klienci korzystają z systemu stojaków i muszą znać, do celów pobrania, który numer identyfikacyjny jest zwrócony do przodu.

W tym artykule przedstawiono scenariusz, który pokazuje sposób konfigurowania i korzystania z funkcji.

## <a name="turn-the-location-license-plate-positioning-feature-on-or-off"></a>Włącz lub wyłącz funkcję pozycjonowania tablic rejestracyjnych lokalizacji

Aby korzystać z funkcji opisanej w tym artykule, w systemie musi być włączona funkcja *Położenie tablicy rejestracyjnej lokalizacji*. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Położenie tablicy rejestracyjnej lokalizacji* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="example-scenario"></a>Przykładowy scenariusz

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby przejść przez ten scenariusz przy użyciu określonych zaprezentowanych przykładowych danych i wartości, należy korzystać z systemu, w którym są zainstalowane standardowe dane przykładowe. Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="set-up-the-feature-for-this-scenario"></a>Skonfiguruj funkcję dla tego scenariusza

Wykonaj poniższe procedury, aby skonfigurować funkcję *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji* dla scenariusza przedstawionego w tym artykule.

#### <a name="location-profiles"></a>Profile lokalizacji

Funkcja musi być włączona w profilu lokalizacji dla każdej lokalizacji, w której będzie używana.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. Z listy profilów lokalizacji w lewym okienku wybierz opcję **BULK-06**.
1. Na skróconej karcie **Ogólne** zostały dodane dwie nowe opcje przez tą funkcję. Ustaw następujące wartości:

    - **Włącz funkcję Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji:** *Tak*

        Jeśli ta opcja jest ustawiona na wartość *Tak*, pozycja numeru identyfikacyjnego będzie utrzymywana dla numerów identyfikacyjnych w lokalizacji.

    - **Wyświetl pozycję num. id. urządzenia przenośnego:** *Tak*

        Jeśli ta opcja jest ustawiona na *Tak*, użytkownicy urządzeń przenośnych będą mogli wyświetlić pozycję numeru identyfikacyjnego w trakcie korekty i inwentaryzacji. Ustawienie tej opcji można zmienić tylko w przypadku, gdy funkcja jest włączona.

1. Wybierz opcję **Zapisz**.

#### <a name="location-directives"></a>Dyrektywy lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym okienku upewnij się, że pole **Typ zlecenia produkcyjnego** ma wartość *Zamówienia sprzedaży*.
1. Z listy dyrektyw lokalizacji wybierz pozycję **61 Zlecenie pobrania zamówienia sprzedaży**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Wiersze** wybierz wiersz mający wartość **Numeru sekwencyjnego** równą *2*.
1. Na skróconej karcie **Akcji dyrektywy lokalizacji** wybierz wiersz, który ma wartość **Nazwa** równą *Pobierz mniej niż paleta* (powinien to być jedyny wiersz), a następnie zmień **Wartość jego sekwencji** na *2*.
1. Powyżej siatki wybierz **Nowe**, aby dodać nowy wiersz dla dyrektywy akcji lokalizacji.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** *1*
    - **Nazwa:** *Pozycja pobrania 1*

1. Gdy nowy wiersz jest wciąż zaznaczony, wybierz polecenie **Edytuj kwerendę** powyżej siatki.
1. W edytorze zapytań wybierz kartę **Sprzężenia**.
1. Rozwiń opcję **Lokalizacje** na tabeli sprzężęnia, aby wyświetlić sprzężenie do tabeli **Wymiarów magazynowych**.
1. Rozwiń opcję **Wymiary magazynowe** na tabeli sprzężęnia, aby wyświetlić sprzężenie tabeli **Dostępne zapasy**.
1. Wybierz **Wymiary magazynowe**, a następnie wybierz opcję **Dodaj sprzężenie tabeli**.
1. Z listy tabel, które pojawiają się w kolumnie **Relacja**, wybierz **Numer identyfikacyjny (numer identyfikacyjny)**. Następnie wybierz opcję **Wybierz**, aby dodać **Numer identyfikacyjny** do sprzężenia tabeli **Wymiarów magazynowych**.
1. Póki **Numer identyfikacyjny** jest wciąż zaznaczony, wybierz opcję **Dodaj sprzężenie tabeli**.
1. Z listy tabel, które pojawiają się w kolumnie **Relacja**, wybierz **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji (numer identyfikacyjny)**. Następnie wybierz opcję **Wybierz**, aby dodać **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji** do sprzężenia tabeli **Wymiarów magazynowych**.

    ![Sprzężenia tabeli.](media/LpTableJoin.png "Sprzężenia tabeli")

1. Wybierz przycisk **OK**, aby potwierdzić zaktualizowane tabele sprzężone i zamknąć Edytor kwerend.
1. Na karcie skróconej **Akcje dyrektywy lokalizacji** ponownie kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.
1. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji*
    - **Tabela pochodna:** *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji*
    - **Pole:** *Stanowisko Num. id.*
    - **Kryteria:** *1*

    ![Nowy zakres.](media/LpPositionCriteria.png "Nowy zakres")

1. Wybierz przycisk **OK**, aby potwierdzić zmiany i zamknąć okno dialogowe kwerendy.

### <a name="set-up-sample-data-for-this-scenario"></a>Skonfiguruj przykładowe dane dla tego scenariusza

W tym scenariuszu użytkownik musi zalogować się do mobilnej aplikacji magazynowej, używając pracownika skonfigurowanego dla magazynu *61* w celu przeprowadzenia pracy. Użytkownik musi również wykonać transakcje.

Ponieważ funkcja *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji* dodaje nowy identyfikator dla położenia numeru identyfikacyjnego w lokalizacji, należy najpierw utworzyć pewne dane, które będą obsługiwały ten scenariusz.

#### <a name="spot-count-the-first-location"></a>Inwentaryzacja punktowa w pierwszej lokalizacji

1. Otwórz do mobilną aplikację magazynowania i zaloguj się jako użytkownik w magazynie *61*.
1. Przejdź do **Zapasy \> Inwentaryzacja punktowa**.
1. Na stronie **Inwentaryzacja punktowa**, w polu **Lokalizacja** określ wartość *01A01R1S1B*.
1. Kliknij przycisk **OK**.

    Na stronie zostanie wyświetlona wprowadzona lokalizacja. Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”

1. Wybierz opcję **Odśwież**, aby dodać licznik do lokalizacji.
1. W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję**, zaznacz pole **Pozycja**, a następnie wprowadź wartość *A0001*.
1. Kliknij przycisk **OK**.
1. W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję** wybierz pole **Num. id.**, a następnie wprowadź wartość *LP1001* (lub dowolny inny numer identyfikacyjny).

    Strona **Licznik cykli: Dodaj nowy num. id. lub pozycję** pokazuje **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji 1**.

1. Kliknij przycisk **OK**.

    Teraz należy określić ilość towaru, która znajduje się na numerze identyfikacyjnym.

1. Ustaw wartość w polu **Ilość** na *10*.
1. Kliknij przycisk **OK**.

    Na stronie zostanie wyświetlona wprowadzona lokalizacja. Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”

1. Wybierz opcję **Odśwież**, aby dodać kolejny licznik do lokalizacji.
1. W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję**, zaznacz pole **Pozycja**, a następnie wprowadź wartość *A0002*.
1. Kliknij przycisk **OK**.
1. W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję** wybierz **Num. id.**, a następnie wprowadź wartość *LP1002* (lub dowolny inny numer identyfikacyjny, pod warunkiem, że różni się on od numeru podanego wcześniej).
1. Zmień pozycję numeru identyfikacyjnego, ustawiając wartość pola **Pozycja num. id.** na *2*.
1. Kliknij przycisk **OK**.
1. Określ ilość towaru, która jest zliczana na podstawie numeru identyfikacyjnego, ustawiając wartość **Ilość** na *10*.
1. Kliknij przycisk **OK**.

    Na stronie zostanie wyświetlona wprowadzona lokalizacja. Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”

1. Kliknij przycisk **OK**.

Praca została zakończona.

#### <a name="spot-count-the-second-location"></a>Inwentaryzacja punktowa w drugiej lokalizacji

1. Na stronie **Inwentaryzacja punktowa**, w polu **Lokalizacja** określ wartość *01A01R1S2B*.
1. Kliknij przycisk **OK**.

    Na stronie zostanie wyświetlona wprowadzona lokalizacja. Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”

1. Wybierz opcję **Odśwież**, aby dodać licznik do lokalizacji.
1. W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję**, zaznacz pole **Pozycja**, a następnie wprowadź wartość *A0002*.
1. Kliknij przycisk **OK**.
1. W polu **Licznik cykli: Dodaj nowy num. id. lub pozycję** wybierz **Num. id.**, a następnie wprowadź wartość *LP1003* (lub dowolny inny numer identyfikacyjny, pod warunkiem, że różni się on od numerów podanych we wcześniejszej procedurze).

    Strona **Licznik cykli: Dodaj nowy num. id. lub pozycję** pokazuje **Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji 1**.

1. Kliknij przycisk **OK**.
1. Określ ilość towaru, która jest zliczana na podstawie numeru identyfikacyjnego, ustawiając wartość **Ilość** na *10*.
1. Kliknij przycisk **OK**.

    Na stronie zostanie wyświetlona wprowadzona lokalizacja. Wyświetlany jest tu również następujący komunikat: „Lokalizacja ukończona, dodać nowy num. id. lub element?”

1. Kliknij przycisk **OK**.

Praca została zakończona.

#### <a name="work-details"></a>Szczegóły pracy

> [!NOTE]
> Inwentaryzacje punktowe z poziomu aplikacji mobilnej tworzą plan inwentaryzacji ciągłej w Microsoft Dynamics 365. Praca wymaga przyjęcia tych inwentaryzacji przed zaksięgowaniem ich w magazynie.

1. Zaloguj się w Dynamics 365 Supply Chain Management.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Na karcie **Przegląd** odszukaj wiersze, które mają następujące wartości:

    - **Typ zlecenia pracy:** *Inwentaryzacja ciągła*
    - **Magazyn:** *61*
    - **Stan pracy:** *Oczekiwanie na przegląd*

    Dla tych wierszy powinny były zostać utworzone dwa identyfikatory pracy. Należy zaakceptować te zliczenia dla obu tych identyfikatorów pracy.

1. W siatce wybierz pierwszy identyfikator pracy dla zlecenia pracy *Inwentaryzacji ciągłej*.
1. W okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Inwentaryzacja ciągła**.

    Wyświetlane są dwa wiersze, po jednym dla każdego towaru i numeru identyfikacyjnego. Wartości w polach **Ilość zliczona**, **Lokalizacja**, **Numer identyfikacyjny** i **Pozycja** powinny odpowiadać wpisom zliczania utworzonym na urządzeniu przenośnym. Jeśli którekolwiek z tych pól nie są widoczne, wybierz opcję **Wyświetl wymiary** w okienku akcji, aby dodać je do siatki.

1. Wybierz oba wiersze.
1. W okienku akcji wybierz pozycję **Potwierdź zliczanie**.
1. Zostanie wyświetlony komunikat „Księgowanie arkusza”. Wybierz opcję **Szczegóły komunikatu**, aby wyświetlić numer zaksięgowanego arkusza.
1. Zamknij szczegóły komunikatu.
1. Odśwież stronę **Praca**.

    Pierwszy identyfikator pracy został zamknięty i nie jest już wyświetlany.

    > [!TIP]
    > Aby wyświetlić zamkniętą pracę, zaznacz pole wyboru **Pokaż zamknięte**, znajdujące się nad siatką.

    Teraz będziesz akceptować pracę dla numeru identyfikacyjnego w lokalizacji *01A01R1S2B*.

1. W zakładce **Przegląd** wybierz drugi identyfikator pracy dla zlecenia pracy *Inwentaryzacji ciągłej*.
1. W okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Inwentaryzacja ciągła**.

    Jest wyświetlany jeden wiersz dla pozycji i numeru identyfikacyjnego. Wartości w polach **Ilość zliczona**, **Lokalizacja**, **Numer identyfikacyjny** i **Pozycja** powinny odpowiadać wpisom zliczania utworzonym na urządzeniu przenośnym.

1. Wybierz wiersz.
1. W okienku akcji wybierz pozycję **Potwierdź zliczanie**.
1. Zostanie wyświetlony komunikat „Księgowanie arkusza”. Wybierz opcję **Szczegóły komunikatu**, aby wyświetlić numer zaksięgowanego arkusza.
1. Zamknij szczegóły komunikatu.
1. Odśwież stronę **Praca**.

    Drugi identyfikator pracy został zamknięty i nie jest już wyświetlany.

    > [!TIP]
    > Aby wyświetlić zamkniętą pracę, zaznacz pole wyboru **Pokaż zamknięte**, znajdujące się nad siatką.

#### <a name="on-hand-by-location"></a>Dostępne zapasy według lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Zapytania i raporty \> Dostępne zapasy według lokalizacji**.
1. Ustaw następujące wartości:

    - **Oddział:** *6*
    - **Magazyn:** *61*
    - **Odśwież we wszystkich lokalizacjach:** *Tak*

1. Należy zauważyć, że lokalizacja *01A01R1S1B* zawiera dwa numery identyfikacyjne:

    - **A0001**, gdzie pole **Pozycja num. id.** ma wartość *1*
    - **A0002**, gdzie pole **Pozycja num. id.** ma wartość *2*

1. Należy zauważyć, że lokalizacja *01A01R1S2B* zawiera jeden numer identyfikacyjny:

    - **A0002**, gdzie pole **Pozycja num. id.** ma wartość *1*

### <a name="sales-order-scenario"></a>Kryteria zamówień sprzedaży – scenariusz

Teraz, gdy funkcja *Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji* została skonfigurowana, a zapas został przemieszczony, należy utworzyć zamówienie sprzedaży w celu wygenerowania pracy pobrania, która będzie kierowała pracownika magazynu do pobrania *A0002* z lokalizacji magazynu, w której identyfikator palety znajduje się na pozycji *1*.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-004*
    - **Magazyn:** *61*

1. Kliknij przycisk **OK**.
1. Nowy wiersz zostanie dodany do siatki na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *1*

1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy dla wiersza zamówienia.
1. Zamknij stronę **Rezerwacja**.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.

    Użytkownik otrzymuje komunikat informacyjny, które zawiera identyfikator grupy czynności oraz identyfikatory wysyłki utworzone dla zamówienia sprzedaży.

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Magazyn** ponad siatką wybierz **Szczegóły pracy**.
1. Zostanie wyświetlona strona **Praca**, która została utworzona dla danego wiersza sprzedaży. Zanotuj pokazany identyfikator pracy.

### <a name="sales-picking-scenario"></a>Scenariusz pobrania sprzedaży

1. Otwórz mobilną aplikację magazynowania i zaloguj się jako użytkownik w magazynie *61*.
1. Przejdź do **Wychodzące \> Pobieranie sprzedaży**.
1. Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego**, zaznacz pole **Identyfikator**, a następnie wprowadź identyfikator pracy z wiersza sprzedaży.
1. Należy zauważyć, że praca pobrania kieruje się do pobrania *A0002* z lokalizacji *01A01R1S2B*. Zostanie wyświetlona ta instrukcja, ponieważ *A0002* znajduje się na numerze identyfikacyjnym znajdującym się w pozycji *1* w tej lokalizacji.

    ![Lokalizacja stanowiska 1.](media/LocationLicensePlatePositioning.png "Lokalizacja stanowiska 1")

1. Wprowadź identyfikator numeru identyfikacyjnego, który został utworzony dla danej lokalizacji, a następnie postępuj zgodnie z instrukcjami, aby pobrać zamówienie sprzedaży.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]