---
title: Przykładowe scenariusze inwentaryzacji ciągłej
description: Ten temat zawiera zbiór scenariuszy eksplorowania funkcji inwentaryzacji ciągłej rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 60be945035570634c572baaa37ae0d02e41dd0be
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674709"
---
# <a name="cycle-counting-example-scenarios"></a>Przykładowe scenariusze inwentaryzacji ciągłej

[!include [banner](../includes/banner.md)]

Ten temat zawiera zbiór scenariuszy eksplorowania funkcji inwentaryzacji ciągłej rozwiązania Microsoft Dynamics 365 Supply Chain Management. Najpierw opisano wymagania istniejącego środowiska Supply Chain Management. Następnie wyjaśniono, jak skonfigurować inwentaryzację ciągłą i opisano wszystkie etapy inwentaryzacji ciągłej. Kiedy skończysz, powinieneś dobrze rozumieć liczenie cykli, w tym inwentaryzacja ciągła sterowana, inwentaryzacja ciągła w ciemno, inwentaryzacja ciągła w miejscu, progi inwentaryzacji ciągłej i plany inwentaryzacji ciągłej.

## <a name="prerequisites"></a>Wymagania wstępne

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Każdy scenariusz w tym temacie odwołuje się do wartości i rekordów, które są zawarte w standardowych danych demonstracyjnych, które są dostarczane dla Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę (osobę prawną) na **USMF**.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>Włącz obsługę aplikacji mobilnej Warehouse Management

Aby korzystać z aplikacji mobilnej Warehouse Management, *w systemie muszą być włączone ustawienia użytkownika,* ikony i tytuły kroku nowej funkcji aplikacji magazynowej. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Ustawienia użytkownika, ikony i tytuły kroków dla nowej aplikacji magazynowej* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Przygotuj dane demonstracyjne do scenariuszy

Wykonaj poniższe kroki, aby sprawdzić, czy wszystkie dane demonstracyjne wymagane do scenariuszy są dostępne w firmie USMF w Twoim systemie. Utwórz wszystkie rekordy lub wartości, których brakuje.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.
1. W panelu zaznacz osobę **Julia Funderburk**.
1. Na skróconej karcie **Użytkownicy** wybierz wiersz z następującymi wartościami. Jeśli żaden istniejący wiersz nie ma tych wartości, utwórz go.

    - **Identyfikator użytkownika:** *61*
    - **Nazwa użytkownika** *WH61*
    - **Magazyn domyślny:** *61*
    - **Nazwa menu:** *Główne*

1. Na skróconej karcie **Praca** ustaw następujące wartości dla użytkownika *61*, jeśli jeszcze nie są one ustawione:

    - **Jest kierownikiem ds. inwentaryzacji ciągłej** *Nie*
    - **Maksymalny limit procentowy** *0*
    - **Maksymalny limit ilości** *0*
    - **Maksymalny limit wartości** *0*

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Pule pracy**.
1. Pule pracy są używane, aby segregować pracę magazynową na podstawie typu pracy (w tym przypadku pracy inwentaryzacji ciągłej). Upewnij się, że istnieje rekord, który ma następujące ustawienia:

    - **Identyfikator puli pracy:** *CycleCount*
    - **Opis:** *Inwentaryzacja ciągła*

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku listy wybierz rekord o nazwie *Inwentaryzacja ciągła*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go. Potwierdź lub ustaw następujące wartości dla rekordu:

    - **Nazwa elementu menu:** *Inwentaryzacja ciągła*
    - **Tytuł:** *Inwentaryzacja ciągła sterowana*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*
    - **Zarządzane przez:** *Zarządzane przez system* (Ta wartość wskazuje, że Supply Chain Management przydzieli pracownikowi identyfikator pracy Inwentaryzacji ciągłej).
    - **Wyświetl kolumnę Stan zapasów:** *Tak*

1. W okienku akcji wybierz pozycję **Inwentaryzacja ciągła**.
1. W oknie dialogowym **Inwentaryzacja ciągła na urządzeniu mobilnym** potwierdź lub ustaw następujące wartości:

    - **Wyświetl numer pozycji:** *Tak*
    - **Wyświetl numer identyfikacyjny:** *Tak*
    - **Liczba prób:** *1*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. W okienku listy wybierz rekord o nazwie *Inwentaryzacja ciągła w ciemno*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go. Potwierdź lub ustaw następujące wartości dla rekordu:

    - **Nazwa elementu menu:** *Inwentaryzacja ciągła w ciemno*
    - **Tytuł:** *Inwentaryzacja ciągła w ciemno*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*
    - **Zarądzane przez:** *Grupowanie inwentaryzacji ciągłej* — ta wartość oznacza, że pracownik może grupować identyfikatory prac inwentaryzacji ciągłej, które są specyficzne dla danej lokalizacji, strefy lub puli pracy.

1. W okienku akcji wybierz pozycję **Inwentaryzacja ciągła**.
1. W oknie dialogowym **Inwentaryzacja ciągła na urządzeniu mobilnym** potwierdź lub ustaw następujące wartości:

    - **Wyświetl numer pozycji:** *Nie*
    - **Wyświetl numer identyfikacyjny:** *Nie*
    - **Liczba prób:** *0*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. W okienku listy wybierz rekord o nazwie *Liczenie punktowe*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go. Potwierdź lub ustaw następujące wartości dla rekordu:

    - **Nazwa elementu menu:** *Liczenie punktowe*
    - **Tytuł:** *Inwentaryzacja punktowa*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Nie*
    - **Proces tworzenia pracy:** *Liczenie punktowe cykli* (Wartość ta wskazuje, że pracownik może w dowolnym momencie zliczać towary w lokalizacji w magazynie bez tworzenia pracy inwentaryzacji ciągłej. W celu wykonania inwentaryzacji ciągłej punktowej w lokalizacji pracownik wprowadza identyfikator lokalizacji).

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. W okienku listy wybierz rekord o nazwie *Zapasy*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go. Sprawdź czy w kolumnie **Struktura menu** pojawiają się następujące punkty menu liczenia cykli:

    - Inwentaryzacja ciągła
    - Inwentaryzacja ciągłą w ciemno
    - Inwentaryzacja punktowa

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Inwentaryzacja ciągła** ustaw następujące wartości:

    - **Domyślny typ korekty liczenia cykli:** *Inwentaryzacja ciągła* (Pole to określa typ dziennika, który jest księgowany podczas liczenia cykli).
    - **Domyślny identyfikator klasy roboczej liczenia cykli:** *CCount* (Pole to określa klasę roboczą, która jest używana do liczenia cykli).
    - **Domyślny priorytet pracy liczenia cykli:** *50* (Pole to określa priorytet, jaki ma praca liczenia cykli w stosunku do innych rodzajów pracy w magazynie. Wpisując liczbę, która jest niższa od liczby wpisywanej dla innych rodzajów prac, podnosisz priorytet prac związanych z liczeniem cykli).

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Typy korekty**.
1. Strona **Typy korekt** umożliwia tworzenie kodów dla różnych korekt typu in i out, które mogą wystąpić. Potwierdź, że istnieje rekord, który ma następujące ustawienia:

    - **Typ korekty zapasów:** *Inwentaryzacja cyklowa*
    - **Opis:** *Liczba cykli*
    - **Nazwa:** *ICnt*

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Konfiguracja magazynu**.
1. Na liście zaznacz magazyn *61*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go.
1. Na skrócone karcie **Magazyn** ustaw następujące wartości:

    - **Użyj procesu zarządzania magazynem:** *Tak* (ta wartość włącza magazyn dla procesów zarządzania magazynem)
    - **Zezwalaj na przesuwanie tablic rejestracyjnych podczas liczenia cykli:** *Tak* (Wartość ta umożliwia pracownikom przesuwanie tablic rejestracyjnych podczas liczenia cykli).

## <a name="scenario-1-guided-cycle-counting"></a>Scenariusz 1: wspomagana inwentaryzacja ciągła

Zanim zaczniesz inwentaryzację ciągłą, musisz stworzyć jakąś pracę. Ta praca poprowadzi przypisaną osobę przez magazyn, od lokalizacji do lokalizacji, w celu zakończenia zliczania ustawionego w pracy.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Automatyczne tworzenie pracy inwentaryzacji ciągłej — scenariusz 1

Aby utworzyć pracę inwentaryzacji ciągłej dla lokalizacji pozycji *01A02R2S2B* (BULK-06) w magazynie *61*, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Inwentaryzacja ciągła według lokalizacji**.
1. W oknie dialogowym **Tworzenie pracy inwentaryzacji ciągłej według lokalizacji** ustaw w polu **Identyfikator puli pracy** wartość *CycleCount*.
1. W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.
1. W oknie dialogowym edytora kwerend na karcie **Zakres** wykonaj następujące czynności:

    - W przypadku wiersza, w którym pole **Pole** ma wartość *Magazyn*, ustaw w polu **Kryteria** wartość *61*.
    - W przypadku wiersza, w którym pole **Pole** ma wartość *Lokalizacja*, ustaw w polu **Kryteria** wartość *01A02R2S2B*.

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Wybierz **przycisk OK**, aby zamknąć okno dialogowe **Tworzenie pracy inwentaryzacji ciągłej według lokalizacji**.

    Po zakończeniu procesu tworzenia pracy w centrum akcji pojawi się komunikat.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Znajdź nowo utworzoną pracę, ustawiając filtr w kolumnie **Identyfikator puli pracy**, aby znaleźć rekordy o wartości *CycleCount*.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Wykonaj automatyczne tworzenie pracy inwentaryzacji ciągłej — scenariusz 1

Po utworzeniu pracy inwentaryzacji ciągłej można wykonać tę pracę, zliczając towary w lokalizacji w magazynie, a następnie za pomocą urządzenia przenośnego wprowadzając wynik w Supply Chain Management. Wykonaj poniższe kroki, aby wykonać operację zliczania w aplikacji mobilnej Warehouse Management.

1. Zalogować się do aplikacji mobilnej Warehouse Management jako użytkownik roboczy, który został skonfigurowany w sekcji [Przygotowanie danych demonstracyjnych dla scenariuszy](#prepare-demo-data) wcześniej w tym temacie. W przykładzie w tym temacie użytkownik ma nazwę *Julia Funderburk* i jest ustawiony dla magazynu *61*. (Dane demonstracyjne USMF powinny umożliwiać zalogowanie się jako ten użytkownik, wprowadzając *61* jako identyfikator użytkownika i *1* jako hasło).
1. W menu głównym wybierz opcję **Zapasy**.
1. W menu **Zapasy** wybierz polecenie **inwentaryzacja ciągła sterowana**.
1. Zaznacz pole **Ilość**, wprowadź wartość *9* za pomocą klawiatury numerycznej, a następnie zaznacz przycisk znacznik wyboru – **OK**.
1. System oczekiwał wprowadzenia liczby 10 sztuk dla tej pozycji, lokalizacji i numeru identyfikacyjnego. W związku z tym zostaniesz poproszony o ponowne przeliczenie. Zaznacz pole **Ilość**, wprowadź znowu wartość *9* za pomocą klawiatury numerycznej, a następnie zaznacz przycisk znacznik wyboru – **OK**. Przy drugiej próbie liczba zostanie zaakceptowana.

    > [!NOTE]
    > Gdy system wykrył różnicę między oczekiwaną ilością na stanie a ilością wprowadzoną przez użytkownika, poprosił o powtórzenie liczenia, ponieważ pole **Liczba prób** jest ustawione na *1* w pozycji menu urządzenia przenośnego **Inwentaryzacja ciągła sterowana**. Użytkownik został skierowany do określonego numeru pozycji i numeru identyfikacyjnego, ponieważ zarówno opcja **Wyświetl numer pozycji**, jak i opcja **Wyświetl numer identyfikacyjny** są ustawione na *Tak* dla pozycji menu urządzenia przenośnego.

1. Wybierz **OK** (symbol znacznika wyboru).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Przegląd różnic inwentaryzacji ciągłej dla scenariusza 1

Aby przejrzeć różnice inwentaryzacji ciągłej, należy wykonać następujące kroki.

1. Powróć do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Znajdź i wybierz pracę inwentaryzacji, która przypominała Cię wcześniej. (Na przykład ustaw filtr na ekranie **Kolumna identyfikatora puli pracy** do znalezienia rekordów o wartości *CycleCount*). Zwróć uwagę, że pole **Stan pracy** dla tej pracy jest teraz ustawione na *Oczekujące na przegląd*.

    > [!NOTE]
    > Dla konta użytkownika, na którym wykonywano zliczanie, opcja **Przełożony autoryzacji ciągłej** jest ustawiona na *Nie*, a pola **Maksymalny limit procentowy**, **Maksymalny limit ilości** i **Maksymalny limit wartości** są ustawione na *0* (zero). W związku z tym wszystkie różnice w liczeniu, które zgłasza ten użytkownik, muszą być ręcznie zatwierdzone, a pole **Status pracy** dla powiązanej pracy jest ustawione na *Oczekuje na przegląd*. Jeśli zliczona wartość mieściłaby się w granicach odchylenia (określonych w polach **Maksymalny limit procentowy** lub **Maksymalny limit ilościowy** na stronie **Użytkownicy pracy**) lub jeśli opcja **Przełożony inwentaryzacji ciągłej** byłaby ustawiona na *Tak* dla użytkownika, praca zostałaby automatycznie zamknięta.

1. W okienku akcji na karcie **Praca** wybierz opcję **Inwentaryzacja ciągła**.
1. W okienku akcji wybierz pozycję **Potwierdź zliczanie**.

    Różnica jest księgowana za pomocą standardowego dziennika liczenia i tworzone jest nowe zlecenie pracy.

1. Na stronie **Transakcje inwentaryzacji ciągłej**, na panelu Akcja, wybierz **Praca pochodna**, aby znaleźć pracę, która została utworzona dla zatwierdzonej różnicy.

## <a name="scenario-2-blind-cycle-counting"></a>Scenariusz 2: inwentaryzacja ciągła w ciemno

Scenariusz ten wymaga, aby scenariusz 1 został już ukończony w systemie.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Automatyczne tworzenie pracy inwentaryzacji ciągłej — scenariusz 2

Zanim zaczniesz inwentaryzację ciągłą w ciemno, musisz stworzyć jakąś pracę. Aby utworzyć pracę inwentaryzacji ciągłej dla lokalizacji pozycji *01A02R2S2B* (BULK-06) w magazynie *61*, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Inwentaryzacja ciągła według produktu**.
1. W oknie dialogowym **Tworzenie pracy inwentaryzacji ciągłej według produktu** ustaw w polu **Identyfikator puli pracy** wartość *CycleCount*.
1. W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.
1. Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj 3 wiersze o następujących ustawieniach:

    - Wiersz 1:

        - **Tabela:** *pozycje*
        - **Pole:** *numer pozycji*
        - **Kryteria:** *L0101*

    - Wiersz 2:

        - **Tabela:** *Wymiary magazynowe*
        - **Pole:** *Magazyn*
        - **Kryteria:** *61*

    - Wiersz 3:

        - **Tabela:** *Wymiary magazynowe*
        - **Pole:** *Lokalizacja*
        - **Kryteria:** *01A02R2S2B*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. Wybierz **przycisk OK**, aby zamknąć okno dialogowe **Tworzenie pracy inwentaryzacji ciągłej według produktu**.

    Gdy proces tworzenia pracy zostanie zakończony, otrzymasz komunikat informacyjny.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Wykonaj automatyczne tworzenie pracy inwentaryzacji ciągłej — scenariusz 2

Po utworzeniu pracy związanej z liczeniem cykli należy wykonać poniższe kroki, aby wykonać pracę w aplikacji mobilnej Warehouse Management.

1. Zalogować się do aplikacji mobilnej Warehouse Management jako użytkownik roboczy, który został skonfigurowany w sekcji [Przygotowanie danych demonstracyjnych dla scenariuszy](#prepare-demo-data) wcześniej w tym temacie. W przykładzie w tym temacie użytkownik ma nazwę *Julia Funderburk* i jest ustawiony dla magazynu *61*. (Dane demonstracyjne USMF powinny umożliwiać zalogowanie się jako ten użytkownik, wprowadzając *61* jako identyfikator użytkownika i *1* jako hasło).
1. W menu głównym wybierz opcję **Zapasy**.
1. W menu **Zapasy** wybierz polecenie **inwentaryzacja ciągła w ciemno**.
1. Zaznacz pole **Identyfikator strefy**, wprowadź wartość *BULK06* i wybierz przycisk **OK** (przycisk wyboru).
1. Zaznacz pole **Produkt**, wprowadź wartość *L0101* i wybierz przycisk **OK** (przycisk wyboru).
1. Zaznacz pole **Numer identyfikacyjny**, wprowadź wartość *LP\_BULK\_06\_01* i wybierz przycisk **OK** (przycisk wyboru).
1. Zaznacz pole **Ilość**, wprowadź wartość *10* i wybierz przycisk **OK** (przycisk wyboru).

    > [!NOTE]
    > Mimo że system wykrył różnicę między oczekiwaną ilością na stanie a ilością zeskanowaną, nie poprosił o powtórne liczenie, ponieważ pole **Liczba prób** jest ustawione na *0* (zero) dla pozycji menu **Inwentaryzacja ciągła w ciemno** urządzenia przenośnego. Użytkownik został skierowany do zeskanowania określonego numeru pozycji i numeru identyfikacyjnego, ponieważ zarówno opcja **Wyświetl numer pozycji**, jak i opcja **Wyświetl numer identyfikacyjny** są ustawione na *Nie* dla pozycji menu urządzenia przenośnego.

1. Wybierz **OK** (symbol znacznika wyboru).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Przegląd różnic inwentaryzacji ciągłej dla scenariusza 2

Aby przejrzeć różnice inwentaryzacji ciągłej, należy wykonać następujące kroki.

1. Powróć do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ogólne \> Praca \> Praca inwentaryzacji ciągłej oczekuje na przegląd**.
1. W okienku akcji na karcie **Praca** wybierz opcję **Inwentaryzacja ciągła**.
1. W okienku akcji wybierz pozycję **Odrzuć zliczanie**.

    Ponieważ różnica w liczeniu została odrzucona, praca jest zamknięta.

## <a name="scenario-3-spot-cycle-counting"></a>Scenariusz 3: inwentaryzacja ciągła punktowa

W rekordzie zapasów jest dostępna ilość pozycji *L0101* w lokalizacji *01A02R2S2B*. Pracownik magazynu jest w lokalizacji *01A02R2S1B*. Chociaż ta lokalizacja powinna być pusta, jest pełna. Dlatego pracownik magazynu natychmiast dokonuje inwentaryzacji punktowej.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Wykonaj automatyczne tworzenie pracy inwentaryzacji ciągłej — scenariusz 3

Wykonaj poniższe kroki, aby wykonać operację zliczania w aplikacji mobilnej Warehouse Management.

1. Zalogować się do aplikacji mobilnej Warehouse Management jako użytkownik roboczy, który został skonfigurowany w sekcji [Przygotowanie danych demonstracyjnych dla scenariuszy](#prepare-demo-data) wcześniej w tym temacie. W przykładzie w tym temacie użytkownik ma nazwę *Julia Funderburk* i jest ustawiony dla magazynu *61*. (Dane demonstracyjne USMF powinny umożliwiać zalogowanie się jako ten użytkownik, wprowadzając *61* jako identyfikator użytkownika i *1* jako hasło).
1. W menu głównym wybierz opcję **Zapasy**.
1. W menu **Zapasy** wybierz polecenie **inwentaryzacja punktowa**.
1. Zaznacz pole **Lokalizacja**, wprowadź wartość *01A02R2S1B* i wybierz przycisk **OK** (przycisk wyboru).

    System wykrywa, że lokalizacja jest pusta w Supply Chain Management.

1. Wybierz pozycję **Dodaj numer LP lub produkt**.
1. Zaznacz pole **Produkt**, wprowadź wartość *L0101* i wybierz przycisk **OK** (przycisk wyboru).
1. Zaznacz pole **Numer identyfikacyjny**, wprowadź wartość *LP\_BULK\_06\_01* i wybierz przycisk **OK** (przycisk wyboru).
1. Zaznacz pole **Ilość**, wprowadź wartość *9* i wybierz przycisk **OK** (przycisk wyboru).

    Ponieważ system wykrył, że określony numer identyfikacyjny jest już dostępny w innej lokalizacji w Supply Chain Management, numer ten zostanie przeniesiony do bieżącej lokalizacji. W związku z tym system prosi o potwierdzenie przeniesienia.

1. Wybierz **OK** (symbol znacznika wyboru).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Przegląd różnic inwentaryzacji ciągłej dla scenariusza 3

Wykonaj poniższe kroki, aby przejrzeć wyniki liczenia.

1. Powróć do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ogólne \> Szczegóły pracy**.
1. Zaznacz pole wyboru **Pokaż zamknięte** u góry siatki.
1. Ustaw filtr kolumny **Typ zlecenia pracy** na *Przeniesienie magazynowe*.

    System automatycznie wykrył tę liczbę jako ruch zapasów. Ruch ten jest dozwolony, ponieważ opcja **Zezwalaj na ruch numerów identyfikacyjnych podczas liczenia cykli** jet ustawiona na *Tak* dla magazynu *61* na stronie **Magazyny**.

## <a name="scenario-4-define-cycle-count-thresholds"></a>Scenariusz 4: Definiowanie progów inwentaryzacji ciągłej

Jednym ze sposobów na stworzenie pracy inwentaryzacji ciągłej jest zastosowanie progów. Próg inwentaryzacji ciągłej wskazuje limit ilościowy lub procentowy dla pozycji magazynowych. Po przekroczeniu limitu progu, praca inwentaryzacji ciągłej jest tworzona automatycznie.

Na przykład w lokalizacji istnieje 60 sztuk towaru, dla którego próg inwentaryzacji ciągłej wynosi 40. Podczas transakcji zamówienia sprzedaży 25 sztuk jest pobieranych z lokalizacji i umieszczanych w lokalizacji pośredniej. Ponieważ nowa liczba sztuk (35) jest mniejsza niż ilość w progu, inwentaryzacja ciągła jest tworzona automatycznie dla lokalizacji.

Wykonaj poniższe kroki, aby ustawić progi inwentaryzacji ciągłej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Konfiguracja \> Inwentaryzacja ciągła \> Progi inwentaryzacji ciągłej**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć próg, i określ dla niego następujące wartości:

    - **Identyfikator progu inwentaryzacji ciągłej:** *L0101*
    - **Opis:** *Próg L0101*
    - **Ilość progu:** *2*
    - **Jednostka:** *EA*
    - **Próg zdolności produkcyjnej oparty na wartości procentowej:** *0,00*
    - **Typ progu inwentaryzacji ciągłej:** *Ilość*
    - **Przetworzyć inwentaryzację natychmiast:** *Tak*
    - **Dni między inwentaryzacją ciągłą:** *1*
    - **Identyfikator puli pracy:** *CycleCount*

1. W okienku akcji wybierz pozycję **Wybierz elementy**.
1. W oknie dialogowym zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Numer pozycji*. Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *L0101*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.

    Zdefiniowano próg inwentaryzacji ciągłej dla pozycji *L0101*.

Inwentaryzacja ciągła zostanie utworzona dla pozycji *L0101* w dowolnej lokalizacji, jeśli ilość dostępnych zapasów jest mniejsza niż 2, a data ostatniej inwentaryzacji dla tej lokalizacji nie jest dzisiejsza.

## <a name="scenario-5-define-cycle-count-plans"></a>Scenariusz 5: Definiowanie planów inwentaryzacji ciągłej

Plany inwentaryzacji ciągłej pozwalają zautomatyzować tworzenie pracy inwentaryzacji. Każdy plan zliczania cyklu można skonfigurować za pomocą określonych kwerend towarów i lokalizacji. Gdy zadanie wsadowe zostanie uruchomione, utworzy prace związane z inwentaryzacją dla wszystkich lokalizacji, które spełniają kryteria pozycji i lokalizacji (do maksymalnej liczby zliczeń określonej dla planu). Po utworzeniu pracy inwentaryzacji ciągłej wiersz tej pracy zawiera informacje o lokalizacji, która ma być inwentaryzowana. Zapasy na stanie, które są powiązane z tą lokalizacją nie są blokowane. Dlatego jest on dostępny do rezerwacji i przetwarzania wychodzącego, nawet jeśli istnieje otwarta praca liczenia.

Wykonaj poniższe kroki, aby ustawić plan inwentaryzacji ciągłej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Inwentaryzacja ciągła \> Plany inwentaryzacji ciągłej**.
1. W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać wiersz do siatki, a następnie ustawić następujące wartości:

    - **Identyfikator planu inwentaryzacji ciągłej:** *BULK06*
    - **Opis:** *Zliczanie lokalizacji dla BULK06*
    - **Identyfikator puli pracy:** *CycleCount*
    - **Maksymalna liczba inwentaryzacji ciągłych:** *10*
    - **Dni między inwentaryzacją ciągłą:** *10*
    - **Puste lokalizacje:** *wyklucz puste*
    - **Szablon pracy:** Pozostaw to pole puste.

1. W okienku akcji wybierz pozycję **Wybierz lokalizacje**.
1. Zostanie wyświetlone standardowe okno dialogowe edycji zapytania. Na karcie **Zakres** dodaj wiersz i ustawić dla niego następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Pole:** *Identyfikator strefy*
    - **Kryteria:** *BULK06*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.
1. W okienku akcji wybierz pozycję **Przetwórz inwentaryzację ciągłą**.
1. W okienku dialogowym **Plany inwentaryzacji cyklicznej** na skróconej karcie **Uruchom w tle ustaw** wartość opcji **Przetwarzanie wsadowe** na *Tak*.
1. Ustaw **Cykl**.
1. W oknie dialogowym **Definiowanie cyklu** skonfiguruj zadanie wsadowe w taki sposób, aby rozpoczynało się natychmiast i uruchamiane było co minutę, tak aby nie było daty zakończenia.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Ustawienie cyklu**.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Plany inwentaryzacji ciągłej**.

    Komunikat informuje, że zadanie zostało dodane do kolejki przetwarzania wsadowego.

1. Kliknij kolejno pozycje **Zarządzanie magazynem \> Wspólne \> Planowanie inwentaryzacji ciągłej**. Plan rozpoczyna się natychmiast i powoduje utworzenie pracy inwentaryzacji. Ze względu na to, że praca zliczania nie została zakończona, pole **Stan** ma wartość *W przetwarzaniu*. Po jednej minucie wartość w kolumnie **Suma cykli** zliczy się na *1*.

    > [!NOTE]
    > Praca inwentaryzacji ciągłej nie zostanie utworzona, jeśli liczba dni od ostatniej inwentaryzacji jest mniejsza niż wartość ustawiona dla pola **Dni między inwentaryzacją cykliczną** dla planu inwentaryzacji. Na przykład jeśli wartość ustawiona w polu **Dni między inwentaryzacją ciągłą** to *5*, praca inwentaryzacji ciągłej będzie tworzona co pięć dni. Jednak jeśli praca inwentaryzacji ciągłej zostanie wykonana w 3. dniu, następna praca inwentaryzacji ciągłej zostanie utworzona po 5 dniach od ostatniego wykonania pracy inwentaryzacji ciągłej, czyli w 8. dniu.

1. W okienku akcji wybierz opcję **Praca**, aby wyświetlić utworzoną pracę inwentaryzacji.
