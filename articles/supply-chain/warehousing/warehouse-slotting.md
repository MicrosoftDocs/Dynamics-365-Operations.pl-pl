---
title: Rozpisywanie na przedziały w magazynie
description: Ten temat zawiera informacje o rozpisywaniu na przedziały w magazynie. Rozpisywanie na przedziały umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie Zamówione, Zarezerwowane lub Zwolnione. Ułatwia to kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.
author: mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: d9080f192db0c59b4b4bc74468491e86ba0b7471
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530358"
---
# <a name="warehouse-slotting"></a>Rozpisywanie na przedziały w magazynie

[!include [banner](../includes/banner.md)]

Rozpisywanie na przedziały umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie *Zamówione*, *Zarezerwowane* lub *Zwolnione*. Wygenerowane zapotrzebowanie może być następnie stosowane do lokalizacji, które będą używane do pobierania, na podstawie ilości, jednostki, wymiarów fizycznych, stałych lokalizacji itd. Po ustaleniu planu rozpisania na przedziały można utworzyć pracę uzupełniającą w celu przeniesienia odpowiedniej ilości zapasów do poszczególnych lokalizacji.

Ta funkcjonalność ułatwia kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.

## <a name="turn-on-the-warehouse-slotting-feature"></a>Włącz funkcję rozpisywania na przedziały w magazynie

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Rozpisywanie na przedziały w magazynie*

## <a name="set-up-warehouse-slotting"></a>Konfigurowanie rozpisywania na przedziały w magazynie

Aby można było skorzystać z tej funkcji, należy skonfigurować następujące elementy w systemie.

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Utwórz warstwy jednostki miary dla rozpisywania na przedziały w magazynie

Warstwy jednostek miary umożliwiają zgrupowanie wielu jednostek miary w celach rozpisywania na przedziały. Na przykład, jeśli wiele pudełek jest pobieranych z tego samego obszaru pobrania, można utworzyć jedną warstwę dla wszystkich rozmiarów. **Należy utworzyć wiersz dla każdej jednostki miary, która powinna być częścią warstwy.**

1. Przejdź do **Ustawień zarządzania \> Konfiguracji \> Uzupełniania \> Warstwa jednostki miary – rozpisywanie na przedziały w magazynie**.
1. Wybierz pozycję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Warstwa jednostki miary:** *EaBoxPl*
    - **Opis:** *Każde pudełko paleta*

1. Wybierz opcję **Zapisz**.
1. Na skróconej karcie **Jednostki miary** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Jednostka:** *Pudełko*
    - **Opis:** – zostaw to pole puste. Zostanie ono wypełnione automatycznie po zapisaniu zmian.
    - **Klasa jednostek:** *Ilość*

1. Kliknij przycisk **Nowe**, aby dodać drugi wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Jednostka:** *EA*
    - **Opis:** – zostaw to pole puste. Zostanie ono wypełnione automatycznie po zapisaniu zmian.
    - **Klasa jednostek:** *Ilość*

1. Kliknij przycisk **Nowe**, aby dodać trzeci wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Jednostka:** *PL*
    - **Opis:** – zostaw to pole puste. Zostanie ono wypełnione automatycznie po zapisaniu zmian.
    - **Klasa jednostek:** *Ilość*

1. Wybierz **Zapisz**, aby zapisać warstwę.

### <a name="create-a-directive-code-for-slotting"></a>Utwórz kod dyrektywy dla rozpisywania na przedziały w magazynie

Należy wybrać kod dyrektywy, który powinien być skojarzony z szablonem.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kody dyrektyw**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Kod dyrektywy** wprowadź *Rozpisywanie na przedziały w magazynie*.
1. W polu **Opis dyrektywy** wprowadź *Rozpisywanie na przedziały w magazynie*.

### <a name="set-up-slotting-templates"></a>Skonfiguruj szablony rozpisywania na przedziały w magazynie

Każdy szablon rozpisywania na przedziały w magazynie służy do sterowania sposobem przypisywania zapasów do lokalizacji dla określonego magazynu. Każdy szablon musi zawierać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie. Procedury przedstawione w tej sekcji służą do konfigurowania szablonów rozpisywania na przedziały w magazynie.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony rozpisywania na przedziały w magazynie**.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy szablon.

Następnie należy ustawić nagłówek szablonu, specyfikacje rozpisywania na przedziały w magazynie oraz dyrektywy lokalizacji, jak wyjaśniono w poniższych podsekcjach.

#### <a name="set-up-a-slotting-template-header"></a>Konfigurowanie nagłówka szablonu rozpisywania na przedziały w magazynie

1. W nagłówku szablonu określ następujące wartości:

    - **Szablon rozpisywania na przedziały w magazynie:** _61_
    - **Opis:** _61_
    - **Typ popytu:** *Zamówienie sprzedaży*

        Obecnie jedynym obsługiwanym typem popytu jest *Zamówienie sprzedaży*.

    - **Strategia popytu:** _Zamówione_

        Dostępne do konfiguracji w tym polu są następujące wartości:

        - **Zamówione** – pełna zamówiona ilość na zamówieniu sprzedaży powinna być traktowana jako zapotrzebowanie.
        - **Zarezerwowane** – należy brać pod uwagę zapotrzebowanie tylko dla wierszy zamówienia sprzedaży, które są zarezerwowane (fizyczne i zamówione).

    - **Magazyn:** _61_
    - **Zezwalaj, aby żądania w ramach grupy czynności korzystały z niezarezerwowanych ilości:** _Tak_

Można również określić kwerendę, aby zawęzić zakres ocenianych popytów.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Ustaw rozpisywanie na przedziały w magazynie dla każdego szablonu

Dla każdego tworzonego szablonu należy wykonać poniższe kroki, aby dodać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie.

1. Na skróconej karcie **Szczegółów dot. szablonu rozpisywania na przedziały w magazynie** wybierz opcję **Nowy**, aby utworzyć wiersz szablonu.
1. W nowym wierszu ustaw następujące wartości:

    - **Sekwencja:** _1_
    - **Opis:** _stała lokalizacja_
    - **Ilość minimalna:** _1_

        To pole określa minimalną ilość zapotrzebowania wymaganą dla danego wiersza.

    - **Ilość maksymalna:** _1000000_

        To pole określa maksymalna ilość zapotrzebowania, która jest prawidłowa dla danego wiersza.

    - **Jednostka:** pozostaw to pole puste.

        To pole definiuje jednostkę miary, do której odnoszą się ilości minimalne i maksymalne.

    - **Warstwa jednostki miary:** _EaBoxPl_

        To pole określa liczbę jednostek miary popytu, która jest prawidłowa dla danego wiersza. (Aby uzyskać więcej informacji, zobacz sekcję [Konwersje jednostki miary dla wariantów produktów](#unit-tiers) w tym temacie).

    - **Przypisz kryteria przedziału:** _Rozważona ilość_

        Dostępne do konfiguracji w tym polu są następujące wartości:

        - **Przyjmij wartość pustą** – system powinien założyć, że wszystkie lokalizacje w obszarze pobrania są puste i nie powinny sprawdzać tych lokalizacji w magazynie.
        - **Przyjmij ilość** – system powinien sprawdzić, czy lokalizacje w obszarze pobrania są puste i powinien przeskoczyć wszystkie lokalizacje, które nie są puste.

    - **Kod dyrektywy:** _Rozpisywanie na przedziały_

        To pole określa dyrektywę lokalizacji, która służy do wyszukiwania lokalizacji pobrania dla pracy uzupełniania zapasów.

    - **Lokalizacja przepełnienia:** Pozostaw to pole puste.

        To pole służy do definiowania lokalizacji, do której mają być przemieszczone zapasy, jeśli nie można odnaleźć lokalizacji dla ilości w trakcie przetwarzania wiersza.

    - **Zezwalaj na przeniesienie:** _Tak_

        Jeśli ta opcja jest ustawiona na *Tak*, to w przypadku, gdy nie można rozpisać popytu na przedziały, zostanie utworzone zlecenie pracy przeniesienia zapasów z lokalizacji, w której się znajdują, ale gdzie nic nie było rozpisane. Następnie szablon zostanie uruchomiony ponownie. Tym razem system ignoruje zapasy w lokalizacjach. Ta funkcja działa najlepiej, gdy w polu **Przypisz kryterium przedziału** jest ustawiona wartość _Rozważ ilość_.

    - **Stałe użycie lokalizacji:** _Tylko stałe lokalizacje produktu_

        Dostępne do konfiguracji w tym polu są następujące wartości:

        - **Lokalizacje stałe i niestałe** – system nie powinien ograniczać się do używania tylko stałych lokalizacji.
        - **Tylko stałe lokalizacje produktu** – system powinien rozważać tylko lokalizacje, które są stałymi lokalizacjami produktu.
        - **Tylko stałe lokalizacje wariantu produktu** – system powinien rozważać tylko lokalizacje, które są stałymi lokalizacjami wariantu produktu.

1. Wybierz opcję **Zapisz**.
1. Wybierz **Nowe**, aby utworzyć drugi wiersz szablonu.
1. W nowym wierszu ustaw następujące wartości:

    - **Sekwencja:** _2_
    - **Opis:** _Inne_
    - **Ilość minimalna:** _1_
    - **Ilość maksymalna:** _1000000_
    - **Jednostka:** pozostaw to pole puste.
    - **Warstwa jednostki miary:** _EaBoxPl_
    - **Przypisz kryteria przedziału:** _Rozważona ilość_
    - **Kod dyrektywy:** _Rozpisywanie na przedziały_
    - **Lokalizacja przepełnienia:** Pozostaw to pole puste.
    - **Zezwalaj na przeniesienie:** _Tak_
    - **Korzystaj ze stałych lokalizacji:** _Stałe i niestałe lokalizacje_

    W kwerendzie dla drugiego wiersza zostaną teraz określone kryteria, które zostaną użyte do określenia lokalizacji, do których można przekierować popyt na dany wiersz.

1. Znajdź wiersz, w którym pole o nazwie **Sekwencja** ma wartość *2*.
1. Wybierz **Edytuj zapytanie**.
1. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Tabela pochodna:** *Lokalizacje*
    - **Pole:** *Identyfikator profilu lokalizacji*
    - **Kryteria:** *Pick-06* (wybierz podwójny znak plus \[**++**\] w polu, aby rozwinąć listę, a następnie wybierz opcję *Pick-06* - *Miejsce pobrania 6*).

1. Kliknij przycisk **OK**.

#### <a name="set-up-location-directives"></a>Ustaw dyrektywy lokalizacji

Co najmniej jedna dyrektywa lokalizacji musi być skonfigurowana tak, aby obsługiwała pobrania rozpisania na przedziały. Procedury przedstawione w tej sekcji służą do skonfigurowania nowej *dyrektywy lokalizacji uzupełnienia* dla pobrań rozpisania na przedziały.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym panelu, w polu **Typ zlecenia pracy** zaznacz opcję *Uzupełnienia*.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku nowej dyrektywy lokalizacji w polu **Nazwa** wprowadź wartość *Przedział pobrania 61*.

##### <a name="configure-the-location-directives-fasttab"></a>Skonfiguruj skróconą kartę dyrektywy lokalizacji

1. Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Typ pracy:** _Pobranie_
    - **Oddział:** _6_
    - **Magazyn:** _61_
    - **Kod dyrektywy:** _Rozpisywanie na przedziały_

1. Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.

##### <a name="configure-the-lines-fasttab"></a>Skonfiguruj skróconą kartę Wiersze

1. Na skróconej karcie **Wiersze** kliknij przycisk **Nowe**, aby utworzyć nowy wiersz.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Od ilości:** _0_
    - **Do ilości:** _1000000_

1. Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Skonfiguruj skróconą kartę Dyrektywy akcji

1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby utworzyć wiersz.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Nazwa:** _Bulk_
    - **Strategia:** _Brak_

1. Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę**.

##### <a name="edit-the-query"></a>Edytuj kwerendę

1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.
1. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Tabela pochodna:** *Lokalizacje*
    - **Pole:** *Identyfikator strefy*
    - **Kryteria:** *Bulk* (wybierz podwójny znak plus \[**++**\] w polu, aby rozwinąć listę, a następnie wybierz opcję *Bulk*).

1. Kliknij przycisk **OK**.

## <a name="scenario"></a>Scenariusz

### <a name="set-up-the-scenario"></a>Konfiguracja scenariusza

W tym scenariuszu należy skorzystać z wbudowanych danych przykładowych i utworzyć rekordy opisane w tej sekcji.

#### <a name="use-the-usmf-sample-data"></a>Skorzystaj z przykładowych danych USMF

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

#### <a name="create-demand"></a>Utwórz popyt

Wykonaj poniższe kroki, aby utworzyć zapotrzebowanie, do którego będzie stosowane rozpisanie na przedziały.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz _US-007_.
1. W polu **Magazyn** wybierz wartość _61_.
1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Pozycja:** _L0101_
    - **Ilość:** _20_

1. Wybierz polecenie **Dodaj wiersz**, aby dodać nowy wiersz i określ następujące wartości:

    - **Pozycja:** _T0100_
    - **Ilość:** _8_

1. Wybierz opcję **Zapisz**.
1. Wybierz pozycję **Nowe**, aby utworzyć drugie zamówienie sprzedaży.
1. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz _US-008_.
1. W polu **Magazyn** wybierz wartość _61_.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Pozycja:** _T0100_
    - **Ilość:** _1_

1. Wybierz opcję **Zapisz**.

### <a name="walk-through-a-typical-slotting-scenario"></a>Przechodzenie przez typowy scenariusz rozpisania na przedziały

Po wykonaniu wszystkich wstępnie wymaganych elementów, zgodnie z opisem w poprzedniej sekcji, można wypróbować tę funkcję, wykonując poszczególne działania w tej sekcji.

#### <a name="generate-demand"></a>Generuj popyt

1. Przejdź do **Zarządzanie magazynem \> Ustawienia \> Uzupełnianie \> Szablony rozpisania na przedziały**, a następnie wybierz szablon rozpisania na przedziały, który został wcześniej utworzony.
1. W okienku akcji wybierz pozycję **Utwórz popyt**. To polecenie ocenia cały popyt w systemie, który odpowiada kwerendzie szablonu rozpisanie na przedziały. Łączne zapotrzebowanie dla wszystkich zamówień jest następnie konsolidowane w jeden wiersz na ilość/jednostka miary. Po zakończeniu procesu pojawi się komunikat informacyjny.

#### <a name="slotting-demand"></a>Popyt rozpisywany na przedziały

*Żądanie rozpisania na przedziały* pokazuje wyniki generowania popytu na podstawie konfiguracji szablonu rozpisania na przedziały.

- W okienku akcji wybierz opcję **Rozpisania na przedziały**, aby wyświetlić wyniki polecenia **Generuj popyt**. Można edytować wiersze popytu rozpisania na przedziały. Istnieje możliwość usunięcia wiersza, dodania nowego wiersza lub edytowania szczegółów.

> [!NOTE]
> Popyt można edytować ręcznie lub można go zaimportować z systemu zewnętrznego za pomocą funkcji zarządzania danymi. Wszystko, co znajduje się w popycie rozpisania na przedziały, będzie używane w następnym kroku, niezależnie od pochodzenia.

#### <a name="locate-demand"></a>Lokalizuj popyt

Po wygenerowaniu popytu musisz skorzystać z polecenia **Znajdź żądanie** w celu wygenerowania *planu rozpisania na przedziały*.

- W okienku akcji wybierz pozycję **Zlokalizuj popyt**. Proces rozpisania na przedziały jest uruchomiony. Po zakończeniu procesu pojawi się komunikat informacyjny.

#### <a name="slotting-plan"></a>Plan rozpisywania na przedziały

W planie rozpisania na przedziały jest wyświetlana lokalizacja, do której przypisano każdy towar/ilość, niezależnie od tego, czy zastosowano przepełnienie, czy utworzono pracę i niezależnie od wiersza szablonu, który został użyty. **Popyt, którego nie udało się rozpisać, jest wyróżniony kolorem czerwonym.**

- W okienku akcji wybierz opcję **Plan rozpisania na przedziały**, aby wyświetlić wyniki.

#### <a name="create-replenishment"></a>Uzupełnianie zapasów – skrzynie

Po utworzeniu planu rozpisania na przedziały należy utworzyć *Pracę uzupełniania zapasów* opartą na tym planie.

- W okienku akcji wybierz opcję **Uruchom uzupełnianie**. Po zakończeniu procesu pojawi się komunikat informacyjny. Ten komunikat wskazuje liczbę nagłówków utworzonych dla identyfikatora kompilacji pracy.

Dyrektywy lokalizacji, które będą używane, są identyfikowane na podstawie kodu dyrektywy określonego w każdym wierszu szablonu.

## <a name="tips"></a>Porady

### <a name="set-up-automatic-slotting"></a>Ustawienie automatycznego rozpisywania na przedziały w magazynie

Po umieszczeniu wszystkich wymaganych elementów można skonfigurować rozpisanie na przedziały do automatycznego uruchamiania, wykonując następujące kroki:

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Uzupełnienie \> Uruchomieni rozpisania na przedziały**.
1. Określ kroki rozpisania na przedziały, które mają być uruchomione. Wybierz co najmniej jeden z następujących kroków rozpisania na przedziały:

    - Generuj popyt
    - Lokalizuj popyt
    - Utwórz pracę uzupełniania zapasów

    > [!NOTE]
    > Kroki rozpisania na przedziały są wykonywane stopniowo. Jeśli chcesz wybrać opcję *Znajdź żądanie*, musisz najpierw wybrać opcję *Generuj popyt*.

1. Określ szablon rozpisania na przedziały, który ma być używany.
1. Wybierz cykliczność powtarzania automatycznego.

W przypadku ćwiczeń w tym scenariuszu **nie należy** ustawiać automatycznego rozpisania na przedziały.
