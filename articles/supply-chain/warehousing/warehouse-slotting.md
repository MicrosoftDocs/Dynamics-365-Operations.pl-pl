---
title: Rozpisywanie na przedziały w magazynie
description: Ten temat zawiera informacje o rozpisywaniu na przedziały w magazynie. Rozpisywanie na przedziały umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie Zamówione, Zarezerwowane lub Zwolnione. Ułatwia to kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 31b86837735ca16610a1d304eab611b12a6aceeb
ms.sourcegitcommit: be4b9d557511bbb43e71a93f2c3b23b5f1a4669d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "4627756"
---
# <a name="warehouse-slotting"></a>Rozpisywanie na przedziały w magazynie

[!include [banner](../includes/banner.md)]

Funkcje rozpisywania na przedziały w kilku magazynach ułatwia kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.

*Funkcja Rozpisywanie na przedziały* umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie *Zamówione*, *Zarezerwowane* lub *Zwolnione*. Wygenerowane zapotrzebowanie może być następnie stosowane do lokalizacji, które będą używane do pobierania, na podstawie ilości, jednostki, wymiarów fizycznych, stałych lokalizacji itd. Po ustaleniu planu rozpisania na przedziały można utworzyć pracę uzupełniającą w celu przeniesienia odpowiedniej ilości zapasów do poszczególnych lokalizacji.

Funkcja *Rozpisywanie na przedziały dla zamówień przeniesienia* umożliwia menedżerom magazynowym uzupełnianie lokalizacji pobrań na podstawie popytu na zamówieniach przeniesienia, które nie zostały jeszcze zwolnione do magazynu. Dzięki temu lokalizacje pobrania będą obejmowały wszystkie towary wymagane dla zamówień przeniesienia po ich zwolnieniu do magazynu. Ta funkcja wymaga również włączenia funkcji *Rozpisywania na przedziały w magazynie*.

Funkcja *Udoskonaleń alokacji rozpisywania na przedziały w magazynie* umożliwia dodanie opcji dla wierszy szablonu używanych przez funkcję *Rozpisywanie na przedziały w magazynie*. Opcja pozwala systemowi na uwzględnienie istniejących dostępnych zapasów w lokalizacji docelowej. W związku z tym dla rozpisywania na przedziały w magazynie może zostać wygenerowanych mniej uzupełnień zapasów. Funkcja *Udoskonaleń alokacji rozpisywania na przedziały w magazynie* wymaga także włączenia funkcji *Rozpisywanie na przedziały w magazynie*. Może być opcjonalnie używany z funkcją *Rozpisywanie na przedziały w magazynie dla zamówień przeniesienia*.

## <a name="turn-on-the-warehouse-slotting-features"></a>Włącz funkcje rozpisywania na przedziały w magazynie

Aby móc używać tych funkcji, należy je włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba. W razie potrzeby włącz następujące funkcje:

- Funkcja rozpisywania na przedziały w magazynie
- Rozpisywanie na przedziały w magazynie dla zamówień przeniesienia

    > [!IMPORTANT]
    > Aby ta funkcja była włączona, należy włączyć funkcję *Funkcja rozpisywania na przedziały w magazynie*.

- Ulepszenia alokacji rozpisywania na przedziały dla magazynu

    > [!IMPORTANT]
    > Aby ta funkcja była włączona, należy włączyć funkcję *Funkcja rozpisywania na przedziały w magazynie*.

## <a name="set-up-warehouse-slotting"></a>Konfigurowanie rozpisywania na przedziały w magazynie

Aby można było skorzystać z tej funkcji, należy skonfigurować następujące elementy w systemie:

- Warstwy jednostek miary rozpisywania na przedziały
- Kody dyrektyw
- Szablony rozpisywania na przedziały
- Dyrektywy lokalizacji

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

Następnie należy ustawić nagłówek szablonu, specyfikacje rozpisywania na przedziały w magazynie oraz dyrektywy lokalizacji, jak wyjaśniono w poniższych podsekcjach. Konfiguracja rozpisywania na przedziały dla zamówień przeniesienia przypomina konfigurację rozpisywania na przedziały dla zamówień sprzedaży, ale w polu **Typ zapotrzebowania** jest ustawiana wartość *Zamówienia przeniesienia*, a nie *Zamówienie sprzedaży*.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Konfigurowanie nagłówka dla szablonu Rozpisywanie na przedziały dla zamówienia sprzedaży

1. W nagłówku szablonu określ następujące wartości:

    - **Szablon rozpisywania na przedziały w magazynie:** _61_
    - **Opis:** _61_
    - **Typ popytu:** *Zamówienie sprzedaży*

        > [!NOTE]
        > Obecnie *Zamówienia sprzedaży* i *Zamówienia przeniesienia* są jedynymi obsługiwanymi typami popytu. *Zamówienia przeniesienia* może wybrać tylko wtedy, gdy jest włączona funkcja *Rozpisywanie na przedziały w magazynie dla zamówień przeniesienia*.

    - **Strategia popytu:** _Zamówione_

        Dostępne do konfiguracji w tym polu są następujące wartości:

        - **Zamówione** – pełna zamówiona ilość na zamówieniu sprzedaży powinna być traktowana jako zapotrzebowanie.
        - **Zarezerwowane** – należy brać pod uwagę zapotrzebowanie tylko dla wierszy zamówienia sprzedaży, które są zarezerwowane (fizyczne i zamówione).
        - **Zwolnione** — ilość zwolniona powinna być uznana za zapotrzebowanie.

    - **Magazyn:** _61_
    - **Zezwalaj, aby żądania w ramach grupy czynności korzystały z niezarezerwowanych ilości:** _Tak_

Można również określić kwerendę, aby zawęzić zakres ocenianych popytów.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Ustaw rozpisywanie na przedziały w magazynie dla każdego szablonu

Dla każdego tworzonego szablonu zamówienia sprzedaży należy wykonać poniższe kroki, aby dodać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie.

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
        - **Uwzględnić dostępne zapasy** — system powinien sprawdzać, czy dowolna lokalizacja docelowa zawiera niezarezerwowane ilości pozycji w wierszu zapotrzebowania. Jeśli ilość jest dostatecznie duża, aby zaspokoić co najmniej jedną jednostkę wiersza popytu, wygenerowany rekord planu rozpisywania na przedziały jest redukowany o dostępną ilość. Na przykład, jeśli popyt ma wielkość 10 przypadków, a dla jednego przypadku jest dostępny jeden przypadek, to znajdowane zapotrzebowanie będzie miało dziewięć przypadków. Jeśli popyt ma wielkość 10 przypadków, a każdy jest dostępny, to znajdowane zapotrzebowanie będzie miało 10 przypadków. Ta wartość jest dostępna tylko wtedy, gdy jest włączona funkcja *Ulepszenia alokacji rozpisywania na przedziały dla magazynu*.

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

> [!NOTE]
> Jeśli szablon rozpisywania na przedziały zawiera co najmniej jeden wiersz, w którym w polu **Przypisz kryterium gniazda** jest ustawiona wartość *Uwzględnić dostępne zapasy*, prowizje nie są już dozwolone dla żadnego wiersza w szablonie.

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
1. W polu **Numer sekwencyjny** zaakceptuj wartość domyślną.

##### <a name="configure-the-location-directives-fasttab"></a>Skonfiguruj skróconą kartę dyrektywy lokalizacji

1. Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Typ pracy:** _Pobranie_
    - **Oddział:** _6_
    - **Magazyn:** _61_
    - **Kod dyrektywy:** _Rozpisywanie na przedziały_

1. Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.

##### <a name="configure-the-lines-fasttab"></a>Skonfiguruj skróconą kartę Wiersze

1. Na skróconej karcie **Wiersze** kliknij przycisk **Nowe**, aby utworzyć nowy wiersz.
1. W nowym wierszu ustaw następujące wartości.

    - **Od ilości:** _0_
    - **Do ilości:** _1000000_

1. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.
1. Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Skonfiguruj skróconą kartę Dyrektywy akcji

1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby utworzyć wiersz.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Numer sekwencyjny:** Zaakceptuj wartość domyślną.
    - **Nazwa:** _Bulk_
    - **Strategia:** _Brak_

1. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.
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

W planie rozpisania na przedziały jest wyświetlana lokalizacja, do której przypisano każdy towar/ilość, niezależnie od tego, czy zastosowano przepełnienie, czy utworzono pracę i niezależnie od wiersza szablonu, który został użyty. *Popyt, którego nie udało się rozpisać, jest wyróżniony kolorem czerwonym.*

- W okienku akcji wybierz opcję **Plan rozpisania na przedziały**, aby wyświetlić wyniki.

> [!NOTE]
> - Procesy **Generuj popyt**, **Lokalizuj popyt** i **Wykonaj uzupełnianie zapasów** są teraz uruchamiane w piaskownicy. (Te procesy są dostępne w okienku akcji na stronie **Szablony rozpisywania na przedziały**.)
> - Procesy **Generuj popyt**, **Lokalizuj popyt** i **Wykonaj uzupełnianie zapasów** mają blokadę, aby upewnić się, że nie można ich zainicjować w tym samym czasie. W przeciwnym razie można usunąć używane dane.
> - Procesy **Generuj popyt** i **Lokalizuj popyt** wyświetlają ostrzeżenie, jeśli w wyniku uruchomienia nie zostały wygenerowane rekordy lub w rekordach brakuje informacji.
> - Po wybraniu opcji **Plan rozpisywania na przedziały**, strona nie zawiera przycisków **Nowy**, **Edytuj** i **Usuń** w okienku akcji, ponieważ nie można edytować źródła danych.
> - Po wybraniu opcji **Uruchom uzupełnienie** system sprawdza poprawność wybranego szablonu rozpisywania i procesów.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]