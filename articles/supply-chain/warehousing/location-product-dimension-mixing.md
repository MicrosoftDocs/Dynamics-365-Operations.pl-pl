---
title: Mieszanie wymiarów produktów w lokalizacji
description: Ten temat zawiera informacje dotyczące mieszania rozmiarów produktów w lokalizacji. Ta funkcja profilu lokalizacji pomaga poprawić zarządzanie lokalizacjami, gdy używane są różne warianty produktu lub produkty mają różne wymiary – np. w branży modowej. Dzięki temu można określić, czy konfiguracje, kolory, style i rozmiary mogą być mieszane dla określonego profilu lokalizacji, czy dozwolony jest np. tylko jeden z tych wymiarów lub jakieś połączenie możliwości, które można umieścić w tej samej lokalizacji.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 28f59052a74b6d8b263c7a8a8b6061f2c4b34c89
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831297"
---
# <a name="location-product-dimension-mixing"></a>Mieszanie wymiarów produktów w lokalizacji

[!include [banner](../includes/banner.md)]

Mieszanie wymiarów produktów w lokalizacji to funkcja profilu lokalizacji pomagająca poprawić zarządzanie przestrzenią, gdy używane są różne warianty produktu lub produkty mają różne wymiary – np. w branży modowej. Dzięki temu można określić, czy konfiguracje, kolory, style i rozmiary mogą być mieszane dla określonego profilu lokalizacji, czy dozwolony jest np. tylko jeden z tych wymiarów lub jakieś połączenie możliwości, które można umieścić w tej samej lokalizacji.

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a>Włącz funkcję mieszania różnych wymiarów produktów w lokalizacji

Aby móc używać funkcji mieszania wymiarów produktów w lokalizacji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Mieszanie różnych wymiarów produktów w lokalizacji*

## <a name="setup"></a>Konfiguracja

Z każdą lokalizacją w magazynie musi być skojarzony profil lokalizacji opisujący jej właściwości. Dlatego po skonfigurowaniu działania funkcji wszystkie lokalizacje korzystające z tego samego profilu lokalizacji będą mogły korzystać z możliwości mieszania wymiarów produktów w lokalizacji.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>Konfiguruj profile lokalizacji, aby umożliwić mieszanie wymiarów produktu

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. Z listy profilów lokalizacji wybierz opcję **BULK**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** ustaw opcję **Włącz mieszanie wymiarów produktów w lokalizacji** na *Tak*.

    > [!NOTE]
    > Tę opcję można ustawiać na *Tak* tylko wtedy, gdy wartość opcji **Zezwalaj na towary mieszane** jest ustawiona na *Nie*.

1. Na skróconej karcie **Zezwalaj na mieszanie wymiarów produktów** ustaw opcję **Rozmiar** na *Tak*. W scenariuszu opisanym w tym temacie mieszanie może być wykonane tylko dla produktów mających różne **Rozmiary**. Dostępne są także inne opcje.
1. Wybierz opcję **Zapisz**.

### <a name="create-a-new-product-master-and-product-variants"></a>Stwórz nowy produkt główny i jego warianty

1. Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**.
1. W okienku akcji wybierz opcję **Nowa**, aby utworzyć nowy produkt główny.
1. W wyświetlonym oknie dialogowym **Nowy produkt** można ustawić następujące wartości:

    - **Typ produktu:** *Przedmiot*
    - **Podtyp produktu:** *Produkt główny*
    - **Numer produktu:** *B0001*
    - **Nazwa produktu:** *B0001 Rozmiar*
    - **Wymiar grupy produktu:** *Rozmiar*
    - **Technologia konfiguracji:** *Wariant predefiniowany*

1. Kliknij przycisk **OK**.
1. Na stronie **Szczegóły produktu** na skróconej karcie **Ogólne** należy określić następujące wartości:

    - **Automatyczne generowanie wariantów** *Tak*
    - **Grupa rozmiarów:** *CASUALDHIR*

1. Aby wyświetlić wstępnie zdefiniowane warianty, w okienku akcji wybierz opcję **Warianty produktu**.

    Zostanie wyświetlona strona **Warianty produktu**, a w polu zostanie wyświetlona lista wariantów z konfiguracji grupy rozmiarów.

### <a name="release-products-to-the-usmf-company"></a>Zwalnianie produktów do firmy USMF

1. W okienku akcji wybierz pozycję **Zwalnianie produktów**.
1. Na stronie **Wybierz produkty do zwolnienia** potwierdź, że numer produktu *B0001* znajduje się na liście, a następnie wybierz przycisk **Dalej**.
1. Wybierz przycisk **Dalej**, aby potwierdzić warianty produktu do zwolnienia.
1. Na stronie **Wybierz firmy do których ma nastąpić zwolnienie** wybierz pozycję *USMF*, a następnie wybierz przycisk **Dalej**, aby potwierdzić wybór.
1. Na stronie **Potwierdzenie wyboru** wybierz przycisk **Zakończ**, aby dokończyć zwalnianie.

    Zostanie wyświetlony komunikat „Operacja zakończona”.

### <a name="update-a-released-product-in-the-usmf-company"></a>Aktualizowanie zwolnionego produktu w firmie USMF

1. Należy się upewnić, że użytkownik jest zalogowany do firmy **USMF**.
1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Produkty \> Zwolnione produkty**, aby zakończyć tworzenie zwolnionego produktu.
1. Znajdź i wybierz numer pozycji *B0001*, aby otworzyć stronę **Szczegóły zwolnionego produktu**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** upewnij się, że w polu **Grupa modeli towaru** ustawiono wartość *FIFO*.
1. W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Grupy wymiarów**.
1. Ustaw następujące wartości:

    - **Grupa wymiarów magazynowania:** *Towar*
    - **Grupa wymiarów śledzenia:** *Brak*

1. Kliknij przycisk **OK**.
1. W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Hierarchia rezerwacji**.
1. W polu **Hierarchia rezerwacji** wybierz wartość *Domyślne*, a następnie kliknij przycisk **OK**.
1. Na skróconej karcie **Ogólne** w sekcji **Administracja** zwróć uwagę, że wybory zostały zaktualizowane.
1. Na skróconej karcie **Zakup** w polu **Cena** wprowadź wartość *10*.
1. Na skróconej karcie **Zarządzanie kosztami** w polu **Grupa pozycji** wprowadź *Audio*.
1. Na skróconej karcie **Zakup** w polu **Cena** wprowadź wartość *10*.
1. Na skróconej karcie **Magazyn** w polu **Identyfikator grupy sekwencji jednostek** wprowadź wartość *ea*.
1. Wybierz opcję **Zapisz**.

### <a name="create-a-location-directive"></a>Tworzenie dyrektywy lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym panelu, w polu **Typ zlecenia pracy** zaznacz opcję *Zamówienia zakupu*.
1. Z listy wybierz dyrektywę lokalizacji o nazwie *24 PO Direct*.
1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** *1*

        Nowy wiersz powinien znajdować się przed poprzednio istniejącym wierszem. Aby wprowadzić zmianę, użyj przycisków **Przenieś w górę** i **Przenieś w dół** na pasku narzędzi lub zmień wartość w polu **Numer sekwencyjny** istniejącego wiersza na *2*.

    - **Nazwa:** *Umieść w profilu lokalizacji zbiorczej BULK*
    - **Stałe użycie lokalizacji:** *Stałe i niestałe lokalizacje*
    - **Zezwalaj na ujemne zapasy:** *Wyczyść to pole wyboru (=Nie)*
    - **Partia włączona:** *Wyczyść to pole wyboru (=Nie)*
    - **Strategia:** *Brak*

1. Gdy nowy wiersz jest wciąż zaznaczony, wybierz polecenie **Edytuj kwerendę** powyżej siatki.
1. W polu dialogowym kwerendy, na karcie **Zakres** wybierz przycisk  **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Tabela pochodna:** *Lokalizacje*
    - **Pole:** *Identyfikator profilu lokalizacji*
    - **Kryteria:** *BULK*

1. Kliknij przycisk **OK**.
1. Na stronie **Dyrektywy lokalizacji** w okienku akcji wybierz **Zapisz**, aby zapisać nową dyrektywę lokalizacji.

> [!NOTE]
> Na skróconej karcie **Akcje dyrektywy lokalizacji** w polu **Strategia**, jeśli wykorzystywana jest strategia lokalizacji *Konsolidacja*, konfiguracja skróconej karty **Dozwolone mieszanie wymiarów produktów** znajdującej się w **Profilach lokalizacji** zostanie nadpisane, a przedmioty będą umieszczane w tej samej lokalizacji, nawet jeśli takie zachowanie nie jest dozwolone przez konfigurację.

### <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć element menu służący do sortowania.
1. W nagłówku ustaw następujące wartości:

    - **Nazwa elementu menu:** *Wiersz zamówienia zakupu – przyjęcie*
    - **Nazwa:** *Wiersz zamówienia zakupu – przyjęcie*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Nie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Proces tworzenia pracy:** *Przyjęcie i umieszczenie wierszy zamówienia zakupu*
    - **Generuj numer identyfikacyjny:** *Tak*

1. Wybierz opcję **Zapisz**.

### <a name="configure-the-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Z listy menu wybierz opcję **Przychodzące**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na liście **Dostępne menu i elementy menu** znajdź i zaznacz **Wiersz zamówienia zakupu – przyjęcie**.
1. Wybierz przycisk Strzałka w prawo, aby przenieść **Wiersz zamówienia zakupu – przyjęcie** do listy **Struktura menu**. W ten sposób dodasz nowy element menu do wybranego menu.
1. Wybierz opcję **Zapisz**.

## <a name="scenario"></a>Scenariusz

Ten scenariusz pokazowy prezentuje, jak dwa różne warianty produktów mogą być umieszczane w tej samej lokalizacji, gdy profil lokalizacji nie zezwala na towary mieszane, ale jest włączona funkcja *Mieszania wymiarów produktów w lokalizacji*. W takim przypadku, używane kryterium to **Rozmiar**.

Przed rozpoczęciem należy się upewnić, że w magazynie *24* znajdują się puste lokalizacje, w których jest używany profil lokalizacji zbiorczej *BULK*.

### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

Użytkownik utworzy zamówienie zakupu z trzema wierszami: dwa wiersze dla tego samego numeru produktu, ale różne warianty **Rozmiaru** oraz trzeci wiersz dla innego produktu, który nie ma wariantów.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:

    - **Konto dostawcy:** *1001*
    - **Magazyn:** *24*

1. Kliknij przycisk **OK**.
1. Utworzono zamówienie zakupu, a w wierszach skróconej karty **Wiersze zamówienia zakupu** jest dodawany nowy wiersz. Zanotuj numer zamówienia zakupu.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *B0001*
    - **Rozmiar** *L*
    - **Ilość:** *2*

1. Wybierz polecenie **Dodaj wiersz** ponad siatką, dodaj drugi wiersz zamówienia zakupu i określ następujące wartości:

    - **Numer pozycji:** *B0001*
    - **Rozmiar** *XL*
    - **Ilość:** *2*

1. Wybierz polecenie **Dodaj wiersz**, dodaj trzeci wiersz zamówienia zakupu i określ następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *1*

1. Wybierz opcję **Zapisz**.

### <a name="receive-purchase-order-lines-in-the-warehouse-management-mobile-app"></a>Odbiór wierszy zamówienia zakupu w aplikacji Warehouse Management

1. Zaloguj się do aplikacji Warehouse Management jako użytkownik, który jest uruchomiony dla magazynu *24*.
1. Wybierz menu **Przychodzące**.
1. Wybierz **Wiersz zamówienia zakupu – przyjęcie**.
1. Zaznacz pole **PONUM**, a następnie wprowadź numer zamówienia zakupu.
1. Potwierdź swój wpis, wybierając przycisk Potwierdź ( ✔ ) u dołu strony.
1. Umożliwia wprowadzenie numeru wiersza z otrzymanego zamówienia zakupu. Zaznacz pole **LINENUM**, a następnie za pomocą konsoli numerycznej wprowadź wartość *1*.
1. Potwierdź wpis.
1. Umożliwia wprowadzenie ilości, która ma zostać odebrana. Kliknij przycisk **+** dwa razy, aby zwiększyć wartość w polu **Ilość** do wartości *2*.
1. Zarejestruj wpis, wybierając przycisk ( ✔ ) u dołu strony, a następnie potwierdź swój wpis, wybierając ponownie przycisk ( ✔ ).
1. Umożliwia wyświetlanie informacji na stronie **Zamówienia zakupu: Umieść**. Na tej stronie jest wyświetlona praca, która została utworzona dla działania umieszczenia (praca 1).

    Zostanie wyświetlona lokalizacja odebranego towaru, numer identyfikacyjny, towar, rozmiar oraz ilość zakończonego zadania **Wiersz zamówienia zakupu – przyjęcie**.

1. Potwierdź pracę umieszczenia.
1. Powtórz kroki od 4 do 11 dla wiersza zamówienia zakupu 2. Jednak w kroku 8 należy określić ilość równą *1*.

    Nowa praca umieszczenia (Praca 2) jest tworzona dla tej samej lokalizacji co Praca 1.

1. Znowu powtórz kroki od 4 do 11 dla wiersza zamówienia zakupu 2. Jednak w kroku 8 należy określić pozostałą ilość równą *1*.

    Nowa praca umieszczenia (Praca 3) jest tworzona dla tej samej lokalizacji co Praca 1 i 2. To zachowanie występuje, ponieważ jest używana strategia dyrektywy lokalizacji *Konsolidacja*, a na skróconej karcie **Dozwolone mieszanie wymiarów** w konfiguracja **Profilu lokalizacji** *Bulk* pozwala na mieszanie wariantu **Rozmiar** w danej lokalizacji.

1. Powtórz kroki od 4 do 11 dla wiersza zamówienia zakupu 3. W kroku 8 określ ilość równą *1* dla towaru o numerze *A0001*.

    Nowa praca odłożenia (Praca 4) jest tworzona dla innej lokalizacji niż lokalizacja używana dla wierszy zamówienia zakupu 1 i 2. To zachowanie występuje, ponieważ profil lokalizacji nie zezwala na produkty mieszane, ale pozwala na tworzenie mieszanych wymiarów tego samego produktu głównego.

1. Wybierz przycisk menu u góry strony (czasami nazywany przyciskiem Hamburger lub Hamburger), a następnie wybierz opcję **Anuluj**, aby zamknąć **Wiersz zamówienia zakupu – przyjęcie**.

> [!TIP]
> Ten scenariusz można powtórzyć, ale zmienić wartość **Rozmiar** - *Nie* na skróconej karcie **Zezwalaj na mieszanie wymiarów produktów** w profilu **Profile lokalizacji** zbiorczej *BULK*, tak aby żaden z wymiarów produktu nie mógł być mieszany. W takim przypadku po odebraniu zamówienia zakupu każdy wariant produktu zostanie umieszczony w nowym miejscu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]