---
title: Potwierdź i przenieś
description: W tym temacie objaśniono, jak korzystać z funkcji Potwierdź i przenieś, która pozwala na wysyłanie ładunku z magazynu przed ukończeniem pracy skojarzonej z tym ładunkiem.
author: mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 7b487684980f60112d9af6bea02672f7e919c834
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103596"
---
# <a name="confirm-and-transfer"></a>Potwierdź i przenieś

[!include [banner](../includes/banner.md)]

W tym temacie objaśniono, jak korzystać z funkcji *Potwierdź i przenieś*, która pozwala na wysyłanie ładunku z magazynu przed ukończeniem pracy skojarzonej z tym ładunkiem. Po otrzymaniu wysyłki, która zawiera wiersze ładunku, które nie zostały w pełni pobrane, monit o potwierdzenie użytkownika jest wyświetlany w celu podzielenia pozostałych ilości na nowe obciążenie lub anulowania niepełnych ilości.

Systemy skonfigurowane w taki sposób, aby umożliwić obsługę podziału ładunku, w których planowane i częściowo ładowane ładunki muszą zostać dostosowane z powodu nowych lub zmieniających się okoliczności.

Klient zawiera logikę umożliwiającą zamknięcie i potwierdzenie części ładunku, która zostało potwierdzona jako wysłane. Wszystkie pozostałe wysyłki i wiersze ładunku (w tym pełne lub częściowe ilości) są następnie przenoszone na nowo utworzony ładunek i wysyłkę, jeśli takie przeniesienie jest wymagane i jest możliwe w zgodzie z ustawieniami. Nowe wysyłki i ładunki są tworzone automatycznie na podstawie początkowych kryteriów dotyczących wysyłki i tworzenia ładunku, a ich atrybuty główne pozostają niezmienione. Istnieje także opcja automatycznego anulowania pozostałej ilości, jeśli zlecenie pracy nie zostało jeszcze utworzone, a użytkownik uważa anulowanie za niezbędne.

Ta funkcja obsługuje scenariusze, w których pełne obciążenie nie pasuje do pojedynczego pojazdu lub w przypadku gdy część ładunku powinna opuścić magazyn, zanim jego pozostała część będzie gotowa do wysyłki. W tych scenariuszach pozostałe produkty mogą zostać przeniesione do nowego ładunku i w związku z tym do nowego pojazdu. Ta funkcja może być używana w przypadku ładunków, które w innym przypadku wymagają wysyłki w ramach pełnego ładunku, dzięki czemu kierownicy transportu mogą rozwiązywać niestandardowe lub nieprzewidziane problemy.

Po podzieleniu ładunku funkcja *Potwierdź i prześlij* wykonuje następujące akcje:

- Nowe ładunki i wysyłki są tworzone w miarę potrzeby. Każdy ładunek lub wysyłka będzie miał większość takich samych atrybutów jak pierwotny ładunek lub wysyłka. Wyjątkiem jest stan ładunku, który zostanie ponownie obliczony na podstawie stanu pracy.
- Użytkownik jest informowany o utworzeniu nowego ładunku. Użytkownik jest również powiadamiany o identyfikatorach nowego ładunku.
- Wiersze ładunku, nagłówki pracy i wiersze pracy, które zostały podzielone, są aktualizowane przy użyciu nowych informacji o ładunku i wysyłce.
- W przypadku dzielenia całej wysyłki wysyłka jest zachowywana i aktualizowane są tylko odwołania do ładunku. Jeśli wysyłka musi zostać podzielona, tworzona jest nowa wysyłka.

Po anulowaniu pozostałych ilości, wiersze ładunku, które nie zostały pobrane i nie są z nimi skojarzone żadne nieanulowane prace, są usuwane z ładunku. Jeśli jakaś praca jest w toku, użytkownik może tylko podzielić ładunek. Pozostałe ilości nie mogą być anulowane.

Można dzielić tylko ładunki spełniające wszystkie następujące kryteria:

- Co najmniej jeden wiersz ładunku ma pobrane ilości.
- Stan ładunku jest mniejszy niż załadowany.
- Brak danych wiersza ładunku. (Te dane są tworzone w ramach konsolidacji numerów identyfikacyjnych w lokalizacji przemieszczania, a funkcja Potwierdź i prześlij nie obsługuje konsolidacji numeru identyfikacyjnego.)
- Żadne zapasy nie oczekują obecnie na pakowanie w lokalizacji pakowania. (Funkcja *potwierdzania i przenoszenia* nie obsługuje zapasów, które zostały odebrane do stacji pakowania, ale nie zostały jeszcze zapakowane, chyba że zapakowane kontenery zostaną umieszczone w lokalizacjach przemieszczania z utworzoną pracą załadunkową)

> [!NOTE]
> Ta funkcja różni się od funkcji transportu ładunku, która powinna być używana w magazynach, które nigdy nie mogą planować i tworzyć ładunków przed pobraniem, ale w ten sposób po zakończeniu pobierania zostanie załadowana dostępna przestrzeń transportowa.
>
> Należy korzystać z funkcji *Potwierdzania i przeniesienia* w sytuacjach, gdy ładunki są zwykle planowane i tworzone z wyprzedzeniem, a czasami występują wyjątki, w których ładunek nie mieści się na dostępny środek transportu (np. ciężarówkę).

## <a name="turn-the-confirm-and-transfer-feature-on-or-off"></a>Włączanie lub wyłączanie funkcji potwierdzania i przenoszenia

Aby korzystać z funkcji opisanej w tym temacie, w systemie musi być włączona funkcja *Potwierdź i przenieś*. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Potwierdź i przenieś* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-confirm-and-transfer"></a>Konfiguracja funkcji Potwierdź i przenieś

Aby można było skorzystać z funkcji *Potwierdź i przenieś*, należy ją włączyć we wszystkich odpowiednich szablonach ładunku. Ponadto, w zależności od wymagań użytkownika, można przygotować szablony pracy do obsługi tej funkcji. Jeśli użytkownik chce pracować w przykładowym scenariuszu przedstawionym w dalszej części tego tematu, należy skonfigurować system zgodnie z opisem w tej sekcji. (Ten scenariusz jest oparty na danych demonstracyjnych **USMF**).

### <a name="prepare-your-load-templates"></a>Przygotowywanie szablonów ładunku

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Ładunek \> Szablony ładunku**.
1. W okienku akcji wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Zaznacz pole wyboru **Zezwalaj na podział ładunku w polu Potwierdź wysyłkę** dla każdego istniejącego szablonu, w którym chcesz włączyć funkcję. Można też wybrać opcję **Nowy**, aby utworzyć nowy szablon i skonfigurować go zgodnie z potrzebami. Każdy ładunek utworzony za pomocą tego szablonu odziedziczy tę funkcję. (Jeśli pracujesz z danymi demonstracyjnymi **USMF**, włącz funkcję dla szablonu ładunku **Kontenera 20**.)

### <a name="prepare-your-work-templates"></a>Przygotowywanie szablonów pracy

Ta konfiguracja nie jest wymagana we wszystkich sytuacjach. Pokazany tutaj przykład gwarantuje, że praca może zostać przerwana przez wysyłkę do obsługi przykładowego scenariusza przedstawionego w dalszej części tego tematu. Istnieją również inne sposoby osiągnięcia tego rezultatu.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W siatce w górnej części strony wybierz istniejący szablon pracy, w którym chcesz skonfigurować funkcję *Potwierdź i przenieś*. (Jeśli pracujesz z danymi demonstracyjnymi **USMF**, wybierz szablon pracy **51 pobranie do etapu**). Możesz również utworzyć nowy szablon pracy.
1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe **Sprzedaż**.
1. W polu dialogowym **Sprzedaż** , na karcie **Sortowanie** wybierz przycisk **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Tymczasowe transakcje pracy*
    - **Tabela pochodna:** *Tymczasowe transakcje pracy*
    - **Pole:** *Identyfikator wysyłki*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe **Sprzedaż**.
1. Jeśli zostanie wyświetlony komunikat z informacją, że grupowanie zostanie zresetowane, wybierz opcję **Tak**, aby kontynuować.
1. W siatce w górnej części strony **Szablony pracy** wybierz edytowany właśnie szablon, a następnie w okienku akcji wybierz opcję **Podziały nagłówka pracy**.
1. W okienku akcji wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. W siatce ustaw następujące wartości:

    - **Nazwa tabeli:** *Tymczasowe transakcje pracy*
    - **Nazwa pola:** *Identyfikator wysyłki*
    - **Grupuj według tego pola:** To pole wyboru należy zaznaczyć.

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Zamknij stronę.

## <a name="scenario"></a>Scenariusz

W tym scenariuszu pokazano przykład, w którym proces pobierania nie został jeszcze zakończony, ale towary, które zostały wcześniej pobrane, muszą zostać załadowane na ciężarówkę i wysłane mimo to. W związku z tym użytkownik może podzielić niepobrane wiersze ładunku na nowy ładunek. Wszystkie relacje danych zostaną następnie automatycznie zaktualizowane.

> [!NOTE]
> Określone wartości opisane w tym scenariuszu są oparte na danych demonstracyjnych **USMF**. Zaleca się korzystanie z tych danych demonstracyjnych w przypadku prezentowania informacji lub uczenia się korzystania z tej funkcji. Jeśli nie korzystasz z danych demonstracyjnych **USMF**, w razie potrzeby zastąp własne wartości.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>Krok 1: Tworzenie ładunku z wieloma wierszami ładunku

Aby można było skorzystać z tej funkcji, musi istnieć ładunek zawierający wiele wierszy ładunku. Należy także, przed zwolnieniem zleceń do magazynu, upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach, które zostaną utworzone. Przejrzyj ustawienia dyrektywy lokalizacji (**Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**) i zanotuj lokalizacje pobrania używane do pobierania zamówień sprzedaży. Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub skorzystać z dowolnego innego przepływu.

Aby utworzyć poprawny ładunek, najpierw utwórz trzy zamówienia sprzedaży, wykonując następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe **Tworzenie zamówienia sprzedaży**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości (minimum):

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-004* (*Cave Wholesales*).
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *51*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. W siatce **Wierszy zamówienia sprzedaży** dodaj wiersz o następujących wartościach:

    - **Numer pozycji:** *M9200*
    - **Ilość:** *40*
    - **Jednostka:** *EA*

1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Aby otworzyć stronę **Rezerwacje**, w okienku akcji wybierz **Rezerwacja partii**.
1. Zarezerwuj zapasy w wierszu sprzedaży, a następnie zamknij stronę **Rezerwacja**.
1. Powtórz kroki od 1 do 4, aby dodać drugie zamówienie sprzedaży dla tego samego odbiorcy i magazynu.
1. Dodaj dwa wiersze sprzedaży o następujących wartościach. Po dodaniu każdego wiersza rezerwowanie zapasów jest wykonywane w sposób opisany w krokach od 6 do 8.

    - **Wiersz 1:** Ustaw pole **Kod towaru** na *M9200*, natomiast pole **Ilość** ustaw na *30*, a pole **Jednostka** na *ea*.
    - **Wiersz 2:** Ustaw pole **Kod towaru** na *M9201*, natomiast pole **Ilość** ustaw na *20*, a pole **Jednostka** na *ea*.

1. Powtórz kroki od 1 do 4, aby dodać trzecie zamówienie sprzedaży dla tego samego odbiorcy i magazynu.
1. Dodaj dwa wiersze sprzedaży o następujących wartościach. Po dodaniu każdego wiersza rezerwowanie zapasów jest wykonywane w sposób opisany w krokach od 6 do 8.

    - **Wiersz 1:** Ustaw pole **Kod towaru** na *M9201*, natomiast pole **Ilość** ustaw na *20*, a pole **Jednostka** na *ea*.
    - **Wiersz 2:** Ustaw pole **Kod towaru** na *M9202*, natomiast pole **Ilość** ustaw na *60*, a pole **Jednostka** na *ea*.

#### <a name="load-planning-workbench"></a>Warsztat planowania wysyłki ładunku

Pulpit planowania ładunku będzie używał identyfikatora szablonu ładunku do konstruowania wysyłek i zwolnienia wierszy zamówienia sprzedaży do magazynu.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. W polu **Magazyn** wybierz wartość *51*.

    Teraz utworzysz ładunek dla utworzonych właśnie zamówień sprzedaży.

1. Na karcie **Wiersze sprzedaży** w siatce wybierz wiersze sprzedaży dla nowych zamówień sprzedaży.
1. W okienku akcji na karcie **Popyt i podaż** w grupie **Dodaj** kliknij opcję **Do nowego transportu**.
1. W oknie dialogowym **Przydział szablonu ładunku**, w polu **Identyfikator szablonu ładunku** wybierz wartość *Kontener 20*.
1. Kliknij przycisk **OK**.
1. W sekcji **Ładowanie** strony **Pulpit planowania ładunku** znajdź w siatce nowo utworzony identyfikator ładunku dla magazynu *51*. Przewijaj zawartość do prawej, dopóki nie zobaczysz kolumny **Zezwalaj na dzielenie ładunku podczas wysyłki**. Pole wyboru powinno być zaznaczone dla ładunku.
1. Wybierz ładunek.
1. W menu **Zwolnij** nad siatką wybierz opcję **Zwolnij do magazynu**, aby utworzyć pracę.
1. Potwierdź w oknie dialogowym **Zwalnianie ładunku do magazynu**, że rekordy skrócona karta **Rekordy, które mają być uwzględnione** zawierają Identyfikator ładunku.
1. Kliknij przycisk **OK**.

    Może pojawić się komunikat o „Przetwarzaniu operacji”, gdy system tworzy wysyłki i pracę.

1. W sekcji **Ładowanie** na stronie **Pulpitu planowania ładunku**, obciążenie powinno teraz mieć stan *W grupie czynności*. Wybierz ładunek, a następnie w menu **Informacje pokrewne** nad siatką wybierz opcję **Szczegóły grupy czynności**, aby wyświetlić utworzone identyfikatory wysyłek. Po zakończeniu zamknij stronę **Grupy czynności**.
1. W sekcji **Ładowanie** na stronie **Pulpitu planowania ładunku** wybierz ładunek, a następnie w menu **Informacje pokrewne** nad siatką wybierz opcję **Szczegóły pracy**, aby wyświetlić pracę utworzoną dla zamówień sprzedaży.
1. Zanotuj utworzony identyfikator pracy. Może być konieczne przewinięcie w prawo, aby wyświetlić numer zamówienia sprzedaży i identyfikator wysyłki skojarzony z identyfikatorem pracy.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>Krok 2: Konfigurowanie przepływu wykonywania dla urządzeń przenośnych

Zadania urządzeń przenośnych wymagają wprowadzenia informacji przez użytkownika, takich jak identyfikator pracy lub identyfikator numeru identyfikacyjnego. W tych polach informacje te są zwykle udostępniane użytkownikom magazynu w postaci kodów kreskowych, które znajdują się w dokumentacji, pakowaniu lub na stojaku. Aby zakończyć etapy urządzenia przenośnego dla scenariuszy, należy się upewnić, że zostały zidentyfikowane identyfikatory pracy dla transakcji oraz identyfikatory numerów identyfikacyjnych dla towaru i lokalizacji w transakcjach.

1. Zaloguj się na urządzeniu przenośnym, używając identyfikatora użytkownika i hasła dla magazynu *51*.
1. Wybierz pozycję **Wychodzące**.
1. Wybierz **Pobranie sprzedaży**.
1. Użytkownik ma możliwość wprowadzenia identyfikatora pracy lub identyfikatora numeru identyfikacyjnego. Wprowadź identyfikator pracy dla pierwszego zamówienia sprzedaży, a następnie wybierz opcję **Wprowadź**.
1. W polu **Loc** wprowadź lokalizację wyświetlaną w celu potwierdzenia lokalizacji pobrania. Następnie wybierz opcję **Wprowadź**.
1. W polu **Num. id.** wprowadź identyfikator numeru identyfikacyjnego. Identyfikator numeru identyfikacyjnego musi być zgodny z towarem, magazynem i lokalizacją towaru, który jest pobierany z wybranej lokalizacji. Po zakończeniu wybierz przycisk **Wprowadź**.
1. W polu **Towar** wprowadź numer towaru, aby potwierdzić pobierany towar, a następnie wybierz opcję **Wprowadź**.
1. W polu **Ilość** wprowadź ilość towaru, aby potwierdzić pobierany towar, a następnie wybierz opcję **Wprowadź**.
1. W polu **Docelowy num. id.** wprowadź docelowy identyfikator numeru identyfikacyjnego. Docelowy numer identyfikacyjny są definiowane przez użytkownika. Pamiętaj o wprowadzeniu identyfikatora numeru identyfikacyjnego, który będzie łatwy do zapamiętania. Zaleca się użycie bieżącej daty i dwucyfrowej sekwencji (RRMMDD\#\#) jako formatu, np. *19112301*. Po zakończeniu wybierz przycisk **Wprowadź**.
1. Przejrzyj wyświetlane informacje. Te informacje są informacjami o *Pobieraniu*, które teraz zostaną danymi *Umieszczenia* dla transakcji umieszczenia. Po zakończeniu wybierz przycisk **Wprowadź**.

    - Zostanie wyświetlony komunikat **Praca zakończona**.

1. Powtórz kroki od 4 do 10 dla identyfikatora pracy drugiego zamówienia sprzedaży.

Następnym krokiem jest załadowanie dwóch pobranych numerów identyfikacyjnych na ciężarówkę.

1. Zaloguj się na urządzeniu przenośnym, używając identyfikatora użytkownika i hasła dla magazynu *51*.
1. Wybierz pozycję **Wychodzące**.
1. Wybierz **Ładowanie sprzedaży**.
1. Wprowadź zdefiniowany przez użytkownika identyfikator docelowego numeru identyfikacyjnego, który został utworzony dla pierwszego identyfikatora pracy w poprzedniej procedurze. Następnie wybierz opcję **Wprowadź**, aby umieścić docelowy numer identyfikacyjny w lokalizacji **ETAP**.
1. Wprowadź ponownie docelowy identyfikator numeru identyfikacyjnego, a następnie wybierz opcję **Wprowadź**, aby umieścić numer identyfikacyjny w lokalizacji **DRZWI**.
1. Powtórz kroki od 4 do 5 dla docelowego identyfikatora numeru identyfikacyjnego, który został utworzony dla drugiego identyfikatora pracy.

Dwa identyfikatory pracy zostaną teraz zamknięte (załadowane).

### <a name="step-3-confirm-the-outbound-shipment"></a>Krok 3: Potwierdzenie wysyłki wychodzącej

W tym kroku użytkownik potwierdzi dwa zamówienia sprzedaży i pracę, które zostały wykonane dla ładunku, aby wysłać pobrane towary ładunku i utworzyć nowy ładunek dla niepobranych towarów. Na stronie **Szczegóły ładunku** należy potwierdzić wysyłkę wychodzącą.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. W sekcji **Ładunki** w siatce wybierz wiersz dla utworzonego identyfikatora ładunku.
1. Wybierz łącze do identyfikatora ładunku, aby otworzyć stronę **Szczegółów ładunku**.
1. Na stronie **Szczegółów ładunku** w okienku akcji, na karcie **Wysyłka i odbiór**, w grupie **Potwierdź** wybierz opcję **Wysyłka wychodząca**, aby zainicjować potwierdzenie.
1. W oknie dialogowym **Potwierdzanie wysyłki** w **Metoda podzielenia ładunku w polu Potwierdź wysyłkę** wybierz opcję *Podziel ilość na nowy ładunek*.
1. Kliknij przycisk **OK**.

    Może się pojawić komunikat „Przetwarzanie operacji”.

    Otrzymasz komunikaty informacyjne wskazujące, że wysyłka ładunku została potwierdzona i że utworzono nowy ładunek na podstawie ilości podzielonej.

Odśwież stronę **Pulpitu planowania ładunku**, aby zobaczyć nowo utworzony ładunek.

Istnieje również możliwość potwierdzenia, że relacje transakcji zostały zaktualizowane w następujący sposób:

- Pozostałe (nieprzetworzone) wysyłki i wiersze wysyłki są aktualizowane przy użyciu nowego identyfikatora ładunku.
- Zamówienie sprzedaży jest połączone z nowym identyfikatorem ładunku.
- Oryginalny ładunek nie obejmuje pozostałych wierszy ładunku.
- Pozostała praca została zaktualizowana o nowy identyfikator ładunku.
- Grupa czynności pozostanie taka sama.
- Stan nowego ładunku jest poprawnie zaktualizowany. (Jeśli stanem pracy jest _W toku_, stan ładunku również powinien być _W toku_).

## <a name="notes-and-tips"></a>Notatki i porady

- Można również włączyć parametr **Zezwalaj na dzielenie ładunku podczas potwierdzania wysyłki** po utworzeniu parametru **Szablon łądunku**, który jest wyłączony, ale przed rozpoczęciem procesu ładowania. Przejdź do żądanego ładunku, a następnie włącz ten parametr w widoku nagłówka.
- Opcja **Podziału ilości na nowe obciążenie** działa również w przypadku, gdy niektóre nagłówki pozostałej pracy pozostałej mają stan *W toku*. Z tego względu można nadal korzystać z tych funkcji nawet wtedy, gdy pracownicy obsługują już zamówienia pobrania.
- Jeśli zostanie wybrana opcja **Anuluj niezrealizowaną ilość**, a istnieje praca pozostała mająca stan *Otwarte* lub *W toku*, zostanie wyświetlony następujący komunikat o błędzie: „Nie można anulować pozostałej ilości do załadunku. Dla ładunku istnieje praca”.
- W przypadku wybrania opcji **Anuluj niezrealizowaną ilość** w przypadku braku pracy pozostałej, ale w ładunku są niezwolnione wiersze ładunku, pojawia się następujący komunikat o błędzie: „Nie można potwierdzić wysyłki ładunku, ponieważ ilość towaru przekracza wartość procentową zdefiniowaną w ramach dostawy”. Aby uniknąć tego błędu, można ustawić wartość procentową **Niedoboru w dostawie** w niezwolnionym wierszu na 100 procent. Niezwolnione wiersze nie zostaną przeniesione do nowego ładunku, ale bieżący ładunek zostanie potwierdzony z użyciem opcji niedoboru w dostawie. W takim przypadku nie będzie można ponownie zwolnić oryginalnego zamówienia. Dlatego konieczne będzie obsłużenie go w inny sposób.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]