---
title: Grupy odłożenia
description: Grupy odłożenia umożliwiają w tym samym czasie pobieranie wielu numerów identyfikacyjnych, a następnie ich odłożenie w różnych lokalizacjach. Mogą być bardzo przydatne w firmach detalicznych, w których numery identyfikacyjne zazwyczaj nie są pełnymi paletami zapasów.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 559ca80976955d6328cb4d6b2020d5662460cef9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863658"
---
# <a name="putaway-clusters"></a>Grupy odłożenia

[!include [banner](../includes/banner.md)]

Grupy odłożenia umożliwiają w tym samym czasie pobieranie wielu numerów identyfikacyjnych, a następnie ich odłożenie w różnych lokalizacjach. Ten proces jest często nazywany *trasą objazdową*. Grupy odłożenia mogą być bardzo przydatne w firmach detalicznych, w których numery identyfikacyjne zazwyczaj nie są pełnymi paletami zapasów. 

## <a name="turn-the-cluster-putaway-feature-on-or-off"></a>Włącz lub wyłącz funkcję odkładania klastra

Aby korzystać z funkcji opisanej w tym artykule, w systemie musi być włączona funkcja *Funkcja odkładania klastra*. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Funkcja odkładania klastra* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="setup-for-the-example-scenario"></a>Konfiguracja scenariusza przykładowego

### <a name="cluster-profiles"></a>Profile grup

Profil grupy odłożenia określa miejsce, do którego trafia towar, na podstawie lokalizacji przypisanej do towaru w momencie przyjęcia. Jeśli wymagane są różne grupy, dla każdego elementu menu urządzenia przenośnego należy utworzyć inne grupy odłożenia.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Profile grup**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W widoku **Nagłówek** ustaw następujące wartości:

    - **Identyfikator profilu grupy odłożenia:** *Grupa odłożenia*
    - **Nazwa identyfikacyjna profilu grupy odłożenia:** *Grupa odłożenia*
    - **Typ grupy:** *Odłożenie*
    - **Numer sekwencyjny:** Zaakceptuj wartość domyślną.

1. Wybierz opcję **Zapisz**, aby wymagane pola na skróconej karcie **Ogólne** stały się dostępne.
1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Czas przypisania grupy:** *Przy odbiorze*

        To pole określa, czy grupa odkładania powinna być przypisywana natychmiast po odebraniu zapasów, czy też powinna być posortowana później.

    - **Reguła przypisania grupy:** *Ręcznie*

        To pole określa, czy przypisanie klastra powinno być określone automatycznie przez system, czy ręcznie przez użytkownika.

    - Pole **Kod dyrektywy:** należy pozostawić puste.
    - **Lokalizowanie grupy odłożenia:** *Odbiór*

        Dostępne są następujące wartości:

        - **Odbiór** – Lokalizacja jest znajdowana natychmiast po odbiorze.
        - **Zamknięcie grupy** — po zamknięciu grupy zostanie wyszukana lokalizacja.
        - **Sterowane przez użytkownika** — lokalizacja jest znajdowana, gdy numer identyfikacyjny jest pobierany z grupy do odłożenia. W takim przypadku podczas tworzenia pracy odłożenia nie jest określana żadna lokalizacja. Podczas samego odkładania użytkownik musi zeskanować numer identyfikacyjny lub identyfikator pracy, aby zainicjować krok odkładania. Następnie system znajduje ponownie lokalizację odkładania i informuje użytkownika, gdzie ma zostać umieszczona pobrana ilość.

    - **Grupa odkładania na użytkownika:** *Nie*

        To pole określa, czy każda grupa powinna być unikalna dla użytkownika, gdy grupy są przypisywane automatycznie. Jest dostępna tylko wtedy, gdy w polu **Reguła przypisania grupy** ustawiono wartość *Automatyczna*.

    - **Ograniczenie jednostki:** Pozostaw to pole puste.

        To pole określa jednostkę, która musi zostać odebrana, aby profil był ważny. Jeśli pole pozostanie puste, wszystkie jednostki będą obowiązywały.

    - **Przerwa jednostki roboczej**: *Pojedyncza*

        To pole określa, czy wszystkie zapasy powinny być konsolidowane (przy użyciu identyfikatora grupy i numeru identyfikacyjnego) na jeden numer identyfikacyjny, gdy grupa jest zamknięta, a także czy powinny być odłożone jako pojedynczy numer identyfikacyjny, czy też zostać odłączone od otrzymanych numerów identyfikacyjnych. To pole jest niedostępne, jeśli w polu **Znajdź grupę odłożenia** jest ustawiona wartość *Odbiór*.

    - **Grupa pozostaje jako nadrzędny numer identyfikacyjny:** *Nie*

        Jeśli ta opcja jest ustawiona na wartość *Tak*, po zakończeniu kroku wstawiania identyfikator klastra stanie się nadrzędną tablicą rejestracyjną, a wszystkie elementy w identyfikatorze klastra zostaną połączone z tym nadrzędnym numerem rejestracyjnym.

1. Na skróconej karcie **Sortowanie grup** można definiować kryteria sortowania odkładania. Wybierz na pasku narzędzi **Nowe** i określ następujące wartości:

    - **Numer sekwencyjny:** Zaakceptuj wartość domyślną.
    - **Nazwa pola:** *WMSLocationId*

        To pole definiuje pole, które ma być używane przez ten wiersz jako kryterium sortowania.

    - **Sortowanie:** *Rosnąco*

        To pole określa, czy sortowanie powinno odbywać się w porządku rosnącym czy malejącym.

1. Na skróconej karcie **Szablon grupy pracy** wybierz opcję **Nowy** na pasku narzędzi, aby dodać wiersz, a następnie określ dla niego następujące wartości:

    - **Typ zlecenia pracy:** *Zamówienie zakupu*
    - **Szablon pracy:** *61 bezpośrednie zamówienie zakupu*

1. W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Edytuj zapytanie**.
1. W oknie dialogowym **Grupa odłożenia**, na karcie **Zakres** wybierz **Dodaj**, aby dodać drugą linię do zapytania. Następnie zaktualizuj wiersze zapytania, jak pokazano w poniższej tabeli.

    | Tabela | Tabela pochodna | Pole | Kryterium |
    |---|---|---|---|
    | Roboczy | Roboczy | Magazyn | *61* |
    | Roboczy | Roboczy | Identyfikator pracy | To pole należy pozostawić puste. |

1. Wybierz **OK**, zapisać kwerendę i zamknąć okno dialogowe.
1. W okienku akcji wybierz **Zapisz** i zamknij stronę.

> [!IMPORTANT]
> Pola w profilu grupy, które są przyciemniane, gdy **Generuj identyfikator grupy** ma wartość *Tak*, są niedostępne i nie będą brane pod uwagę, gdy używana jest ta funkcja.

### <a name="mobile-device-menu-items"></a>Elementy menu urządzenia przenośnego

Dla tej funkcji są dostępne dwa nowe elementy menu urządzeń przenośnych. Element menu **Odbiór i sortowanie grupy** jest używany do sortowania odebranych zapasów w grupie odłożenia po otrzymaniu. Element menu **Grupa odłożenia** jest używany do odłożenia grupy po jej przypisaniu.

#### <a name="receive-and-sort-cluster"></a>Odbiór i sortowanie grupy

Umożliwia utworzenie nowego elementu menu urządzenia przenośnego służącego do odbierania zapasów i sortowania do grupy. Ta pozycja menu utworzy pracę przychodzącą po otrzymaniu zapasów, co oznacza, że pozycja menu odbioru będzie używana dla grup odkładania.

> [!NOTE]
> Element menu **Odbiór i sortowanie grupy** można używać z następującymi elementami menu odbioru:
>
> - Przyjęcie wiersza zamówienia zakupu
> - Przyjęcie pozycji z zamówienia zakupu
> - Odbierana pozycja ładunku

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W widoku **Nagłówek** ustaw następujące wartości:

    - **Nazwa elementu menu:** *Odbiór i sortowanie grupy*
    - **Nazwa:** *Odbiór i sortowanie grupy*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Nie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Proces tworzenia pracy:** *Przyjęcie pozycji z zamówienia zakupu*
    - **Generuj numer identyfikacyjny:** *Tak*
    - **Przypisz grupę odłożenia** *Tak*

        > [!NOTE]
        > Opcja **Przypisz grupę odłożenia** jest dostępna tylko dla jednoetapowego działania *Proces tworzenia pracy* w celu odbioru.

    Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

1. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="cluster-putaway"></a>Odłożenie klastra

Utwórz nowy element menu urządzenia przenośnego, aby umieścić grupę po jej przypisaniu.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W widoku **Nagłówek** ustaw następujące wartości:

    - **Nazwa elementu menu:** *Grupa odłożenia*
    - **Nazwa:** *Grupa odłożenia*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*

1. Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Grupa odłożenia*. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.
1. Na skróconej karcie **Klasy pracy** skonfiguruj prawidłową klasę roboczą dla tego elementu menu urządzenia przenośnego:

    - **Identyfikator klasy roboczej:** *Zakup*
    - **Typ zlecenia pracy:** *Zamówienie zakupu*

1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="mobile-device-menu"></a>Menu urządzeń przenośnych

Dodaj właśnie utworzone pozycje menu do menu przychodzącego aplikacji mobilnej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Z listy menu wybierz opcję **Przychodzące**.
1. Na liście **Dostępne menu i elementy menu** znajdź i zaznacz element menu **Odbiór i sortowanie grupy**.
1. Wybierz przycisk strzałki w prawo, aby przenieść wybraną pozycję menu na listę **Struktura menu**.
1. Za pomocą przycisku strzałki w górę lub w dół przenieś element menu w żądane miejsce w menu.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Powtórz kroki od 4 do 7, aby dodać pozostałe elementy menu:

    - Przypisz grupę
    - Odłożenie klastra

## <a name="example-scenario"></a>Przykładowy scenariusz

Ten scenariusz symuluje przetwarzanie grupy odłożenia.

### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:

    - **Konto dostawcy:** *1001*
    - **Magazyn:** *61*

1. Kliknij przycisk **OK**.

    Wyświetli się **Wszystkie zamówienia zakupu**.

1. Na stronie **Wszystkie zamówienia zakupu** na skróconej karcie **Wiersze zamówienia zakupu** użyj przycisku **Dodaj wiersz**, aby dodać następujące wiersze:

    - Wiersz zamówienia zakupu 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *10*

    - Wiersz zamówienia zakupu 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *20*

    - Wiersz zamówienia zakupu 3:

        - **Numer pozycji:** *M9215*
        - **Ilość:** *30*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Zanotuj numer zamówienia zakupu.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Odbierz zapasy i odłóż je z urządzenia mobilnego

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>Przyjmowanie i sortowanie zapasów w grupie

1. Zaloguj się do aplikacji Warehouse Management jako użytkownik, który jest ustawiony dla magazynu *61*.
1. W menu głównym wybierz opcję **Przychodzące**.
1. W menu **Przychodzące** wybierz opcję **Odbiór i sortowanie grupy**.
1. W polu **Ponum** wprowadź numer zamówienia zakupu.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Zaznacz pole **Pozycja**, a następnie wprowadź numer pozycji *A0001*, a następnie wybierz **OK**.
1. Zaznacz pole **Ilość**, wprowadź wartość *10* za pomocą klawiatury numerycznej, a następnie zaznacz przycisk znacznik wyboru.
1. Na stronie zadania **Ilość** wybierz **OK** (przycisk ze znakiem wyboru), aby potwierdzić wprowadzoną ilość.
1. Na stronie zadanie **Pozycja** wybierz przycisk **OK**, aby potwierdzić, że została wprowadzona pozycja *A0001*.
1. Zaznacz pole **Identyfikator grupy** i wprowadź wartość, aby przypisać identyfikator tworzonej grupy.

    Wprowadzony tutaj identyfikator będzie używany po otrzymaniu dwóch pozostałych pozycji na zamówieniu zakupu.

1. Kliknij przycisk **OK**.

    Zostanie wyświetlona strona zadania **Ponum** z komunikatem „Praca zakończona”.

    Pozycja *A0001* została odebrana w lokalizacji *RECV* i przypisana do identyfikatora grupy wprowadzonego w kroku 10.

1. Powtórz kroki od 4 do 11, aby otrzymać pozostałe dwa elementy z zamówienia i przypisz je do identyfikatora klastra:

    - Ilość *20* dla pozycji *A0002*
    - Ilość *30* dla pozycji *M9215*

#### <a name="close-the-cluster"></a>Zamknij grupę

Aby możliwe było odłożenie elementów w grupie, należy zamknąć grupę.

1. W Supply Chain Management, przejdź do **Zarządzanie magazynem \> Praca \> Wychodzące \> Grupy pracy**.
1. Na stronie **Grupy pracy** w sekcji **Grupa pracy** wyszukaj pole **Identyfikator grupy** odpowiadające wprowadzonemu wcześniej identyfikatorowi grupy.
1. Jeśli grupa nie jest wyświetlana, być może została już zamknięta. Aby ustalić, czy grupa została zamknięta, zaznacz pole wyboru **Pokaż zamkniętą pracę** i wyszukaj wprowadzony wcześniej identyfikator grupy. Następnie wykonaj jeden z następujących kroków:

    - Jeśli grupa została zamknięta, pomiń pozostałe kroki tej procedury i przejdź do następnej procedury, [Odłóż grupę](#put-the-cluster-away).
    - Jeśli grupa nie została zamknięta, wykonaj pozostałe kroki tej procedury, aby ręcznie zamknąć grupę. Następnie należy przejść do następujące sekcji.

1. W sekcji **Grupa pracy** wybierz wcześniej wprowadzony identyfikator grupy.
1. W okienku akcji wybierz opcję **Zamknij grupę**.

    Po zamknięciu grupy nie jest już wyświetlana w sekcji **Grupa pracy** (chyba że zaznaczono pole wyboru **Pokaż zamkniętą pracę**).

#### <a name="put-the-cluster-away"></a>Odłóż grupę

1. Zaloguj się do aplikacji Warehouse Management jako użytkownik, który jest ustawiony dla magazynu *61*.
1. W menu głównym wybierz opcję **Przychodzące**.
1. W menu **Przychodzące** wybierz **Grupa odłożenia**.
1. Wybierz **Identyfikator grupy** i wprowadź identyfikator grupy, który został wprowadzony wcześniej dla zamkniętej grupy.
1. Kliknij przycisk **OK**.

    Zostanie wyświetlona strona **Grupa odłożenia: Pobierz**. Pokazuje identyfikator grupy, lokalizację pobrania, elementy (zostanie wyświetlona wartość *Wiele*) oraz całkowitą ilość w grupie, która musi zostać pobrana.

1. Kliknij przycisk **OK**.

    Zostanie wyświetlona strona **Grupa odłożenia: Odłóż**. Instrukcje **Odłóż** identyfikują identyfikator grupy, lokalizację odłożenia, pozycje, ilość całkowitą oraz identyfikatory numerów identyfikacyjnych dla pozycji, które zostały odebrane w grupie.

    Masz standardowe opcje zastąpienia lub przejścia tego kroku.

    ![Strona Grupa odłożenia: Odłożenie.](media/Cluster_putaway-Put.png "Strona Grupa odłożenia: Odłożenie")

1. Wybierz **OK**, aby potwierdzić odłożenie grupy.

    Wyświetlany jest komunikat „Grupa zakończona”.

## <a name="notes-and-tips"></a>Notatki i porady

W przypadku, gdy identyfikator grupy staje się nadrzędnym numerem identyfikacyjnym dla zagnieżdżonej palety, pozycja jest automatycznie podawana podczas skanowania identyfikatora grupy. Nie trzeba skanować kolejnych numerów identyfikacyjnych, nawet jeśli dla generowania numerów identyfikacyjnych jest ustawiona wartość ręczna.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]