---
title: Przeszukuj dane za pomocą objazdów aplikacji mobilnej Warehouse Management
description: W tym artykule opisano, jak skonfigurować elementy menu urządzenia mobilnego z zapytaniem o dane i używać ich jako części objazdów.
author: perlynne
ms.date: 08/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c3ea53379badb3cb2ed71b7f102956d71c3f047a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220571"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Przeszukuj dane za pomocą objazdów aplikacji mobilnej Warehouse Management

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Wprowadzenie funkcji

Dzięki możliwości skanowania kodów kreskowych aplikacja mobilna Warehouse Management umożliwia łatwe i dokładne przechwytywanie danych w ramach procesów magazynowych. Jednak czasami kody kreskowe ulegają uszkodzeniu i stają się nieczytelne lub wymagane dane mogą nie występować jako kod kreskowy w przepływach procesów biznesowych. W tych przypadkach ręczne wprowadzanie danych może zająć dużo czasu, a nawet spowodować przechwycenie niepoprawnych danych. Wyniki można zmniejszyć i zmniejszyć poziom usług.

Korzystając z elastycznego procesu zapytań o dane, pracownicy mogą łatwo wyszukiwać wymagane informacje w ramach przepływów wbudowanej aplikacji mobilnej Warehouse Management i stosować opcje filtrowania, dzięki czemu wyświetlane są tylko istotne dane. W związku z tym wybór ręczny jest szybsze i dokładniejsze.

Na przykład w przepływie przyjmowania zamówienia zakupu numer zamówienia zakupu jest wymagany, aby dopasować je do stanu zapasów, które docierają. W ramach tego procesu można łatwo skonfigurować elementy menu w celu wyświetlenia listy kart z odpowiednimi numerami zamówień zakupu. W ten sposób można kontynuować przepływ odbierania, używając szybkiego wyboru punktu do wybrania. Ten artykuł zawiera przykładowe scenariusze, ale tej funkcji można używać także w dowolnych lub wszystkich przepływach aplikacji mobilnej Warehouse Management.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Włączanie funkcji przepływu informacji o danych i jej wymagań wstępnych

Aby można było używać funkcji opisanych w tym artykule, należy wykonać następującą procedurę, aby włączyć wymagane funkcje.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**. (Aby uzyskać więcej informacji na temat korzystania z obszaru roboczego **Zarządzanie funkcjami**, zobacz [Omówienie zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Włącz funkcję, która jest wymieniona w następujący sposób:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcji:** *instrukcje kroków aplikacji magazynu*

    Ta funkcja jest warunkiem koniecznym dla funkcji *Przepływ zapytań o dane w aplikacji Warehouse management*. Aby uzyskać więcej informacji na temat funkcji *Instrukcje krok po kroku aplikacji Warehouse*, patrz [Dostosowywanie tytułów i instrukcji krok po kroku dla aplikacji mobilnej Warehouse Management](mobile-app-titles-instructions.md).

1. Włącz funkcję, która jest wymieniona w następujący sposób:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcjonalności:** *Obejścia aplikacji do zarządzania magazynem*

    Ta funkcja jest warunkiem koniecznym dla funkcji *Przepływ zapytań o dane w aplikacji Warehouse management*. Aby uzyskać więcej informacji na temat funkcji *Objazdy aplikacji do Warehouse management*, zobacz [Konfigurowanie objazdów dla kroków w elementach menu urządzenia mobilnego](warehouse-app-detours.md).

1. Jeśli funkcja *Objazdy aplikacji do zarządzania magazynem* nie była jeszcze włączona, zaktualizuj nazwy pól w aplikacji mobilnej Warehouse Management, przechodząc do **Zarządzanie magazynem \> Konfiguracja \> Urządzenie mobilne \> Nazwy pól aplikacji Warehouse** i wybierając **Utwórz konfigurację domyślną**. Powtórz poprzedni krok dla każdej osoby prawnej (firmy), w której korzystasz z aplikacji mobilnej Warehouse Management. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie pól aplikacji mobilnej Warehouse Management](configure-app-field-names-priorities-warehouse.md).
1. Włącz funkcję, która jest wymieniona w następujący sposób:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcji:** *Przepływ zapytania o dane aplikacji Warehouse Management*

    Ta funkcja jest opisana w tym artykule.

## <a name="example-scenarios"></a>Przykładowe scenariusze

W tym artykule wykorzystano przykładowe scenariusze, aby pokazać, w jaki sposób można użyć funkcji *Przepływ zapytań o dane aplikacji do Warehouse management* w celu usprawnienia przepływu potwierdzeń zakupu. W scenariuszach są wykorzystywane standardowe przykładowe dane, które obejmują przepływ o nazwie *Przyjmij zakup*. Ten przepływ rozpoczyna się od monitu o zidentyfikowanie numeru zamówienia zakupu, z które będą oni otrzymywać. Aby ułatwić pracownikom identyfikację zamówienia zakupu, ulepszysz pierwszą stronę przepływu, dodając następujące nowe opcje zapytania jako [objazdy](warehouse-app-detours.md):

- **Poszukaj po nazwisku odbiorcy według dostawców** — otwórz stronę z monitem o wprowadzenie nazwy dostawcy lub części nazwy dostawcy. Można używać symboli wieloznacznych. Na przykład, jeśli pracownik oczekuje dzisiaj dostawy przychodzącej od dostawcy, który zawiera *Tailspin* w nazwie, może wprowadzić **Tail\***, aby wyświetlić zestaw kart dla otwartych zamówień zakupu, które zawierają to tekst. Każda karta zawiera kilka pól, które zawierają informacje o każdym zamówieniu zakupu. Oprócz nazwy dostawcy można zaprojektować karty tak, aby zawierały numer konta dostawcy, datę dostawy i stan dokumentu.
- **Odszukaj zamówienia zakupu na dzisiaj** — otwórz stronę, na których pracownicy nie będą monitować o wprowadzanie danych, a zamiast tego będą wyświetlać wstępnie skonfigurowane filtry (takie jak dzisiejsza data). Na tej stronie jest następnie zestaw kart, które są zgodne z filtrem. Pracownicy kontynuują, wybierając kartę dla zamówienia zakupu, w którym mają rejestrować pozycje magazynowe.
- **Poszukaj pozyskanych towarów według towarów** — otwórz stronę, na przykład monituj pracowników o zeskanowanie kodu słupkowego dowolnego towaru w magazynie. Następnie w przepływie jest wymieniona lista wszystkich otwartych zamówień zakupu zawierających wiersze zeskanowanego kodu towaru. Aby pokryć sytuacje, w których nie można odczytać kodu słupkowego, można dodać do tej strony kolejne wyszukiwanie kodu, na którym pracownicy będą szukali kodów towarów w określonym zamówieniu zakupu.

W każdym przypadku pracownik identyfikuje zamówienie zakupu, wybierając kartę, a następnie jest zwracany na pierwszą stronę, która zawiera wybrany numer zamówienia zakupu. Pracownik może następnie kontynuować przepływ rejestracji pozycji dla zapasów przychodzących.

## <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby przepracować przykładowe scenariusze opisane w tym artykule, musisz być w systemie, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę *USMF* przed rozpoczęciem.

## <a name="configure-the-mobile-device-menu-items"></a>Konfigurowanie menu urządzenia przenośnego

Aby utworzyć każdą z nowych opcji kwerendy, które należy dodać do pierwszej strony przepływu, należy skonfigurować ją jako element menu urządzenia przenośnego. Później opcje kwerendy zostaną udostępnione jako objazdy w przepływie *odbierania zakupów*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>Utwórz element menu „Szukaj pozyskanych towarów według dostawców”

Aby utworzyć **pozycję menu Wyszukiwania pozyskanych towarów** według dostawców, należy wykonać następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać element menu urządzenia mobilnego.
1. Ustaw następujące wartości dla nowej pozycji menu:

    - **Nazwa pozycji menu:** *Szukaj pozyskanych towarów według dostawców*
    - **Tytuł:** *Wyszukaj zamówienie według dostawcy*
    - **Tryb:** *Pośrednie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Kod działania:** *zapytanie o dane*
    - **Użyj przewodnika po procesach:** *Tak* (ta wartość jest zaznaczona automatycznie)
    - **Nazwa tabeli:** *PurchTable* (na tej tabeli mają być wyszukiwania numerów zamówień zakupu)

1. W okienku akcji wybierz opcję **Edytuj kwerendę**, aby zdefiniować kwerendę opartą na wybranej tabeli podstawowej (w tym przypadku jest to tabela zamówień zakupu).
1. W edytorze zapytań na karcie **Zakres** dodaj następujące wiersze do siatki.

    | Tabela | Tabela pochodna | Pole | Kryterium |
    |---|---|---|---|
    | Zamówienia zakupu | Zamówienia zakupu | Stan zamówienia zakupu | Otwarte zamówienie |
    | Zamówienia zakupu | Zamówienia zakupu | Data dostawy | (dayRange(-10,10)) |
    | Zamówienia zakupu | Zamówienia zakupu | Nazwa dostawcy | |

1. Kliknij przycisk **OK**.

    W tym przykładzie nowy element menu jest skonfigurowany tak, aby można było znaleźć otwarte zamówienia zakupu, które powinny być docierane w każdej chwili w okresie od 10 dni w przeszłości do 10 dni w przyszłości.

    W kwerendzie kolumna **Kryteria** dla *nazwy* dostawcy była pusta. W związku z tym pracownicy będą mogli określać tę wartość w trakcie używania aplikacji mobilnej Warehouse Management.

    Aby określić sposób sortowania listy, można ustawić sortowanie na **karcie Sortowanie**.

1. Oprócz zdefiniowania kwerendy należy wybrać pola, które będą wyświetlane na kartach na stronie listy zapytań. Dlatego w okienku akcji wybierz **Lista pól**.
1. Na stronie **Lista pól** ustaw następujące wartości:

    - **Wyświetl pole 1:** *PurchId* (to pole będzie wyświetlane jako nagłówek każdej karty)
    - **Pole wyświetlane 2:** *PurchStatus*
    - **Pole wyświetlane 3:** *PurchName*
    - **Pole wyświetlane 4:** *OrderAccount*
    - **Pole wyświetlane 5:** *DeliveryDate*
    - **Pole wyświetlania 6:** *displayDocumentStatus()* (Ta wartość jest metodą wyświetlania, co wskazuje „()” na końcu)

1. Na okienku akcji wybierz opcję **Zapisz**. Następnie zamknij stronę.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Utwórz pozycję menu „Wyszukaj zamówienia zakupu na dziś”

Aby utworzyć **pozycję menu Wyszukiwania pozyskanych towarów na dziś**, należy wykonać następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać element menu urządzenia mobilnego.
1. Ustaw następujące wartości dla nowego elementu:

    - **Nazwa pozycji menu:** *Szukaj pozyskanych towarów na dziś*
    - **Tytuł:** *Wyszukaj zamówienia na dzisiaj*
    - **Tryb:** *Pośrednie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Kod działania:** *zapytanie o dane*
    - **Użyj przewodnika po procesach:** *Tak* (ta wartość jest zaznaczona automatycznie)
    - **Nazwa tabeli:** *PurchTable* (na tej tabeli mają być wyszukiwania numerów zamówień zakupu)

1. W okienku akcji wybierz opcję **Edytuj kwerendę**, aby zdefiniować kwerendę opartą na wybranej tabeli podstawowej (w tym przypadku jest to tabela zamówień zakupu).
1. W edytorze zapytań na karcie **Zakres** dodaj następujące wiersze do siatki.

    | Tabela | Tabela pochodna | Pole | Kryterium |
    |---|---|---|---|
    | Zamówienie zakupu | Zamówienie zakupu | Stan zamówienia zakupu | Otwarte zamówienie |
    | Zamówienie zakupu | Zamówienie zakupu | Data dostawy | (Day(0)) |

1. Kliknij przycisk **OK**.

    W tym przykładzie nowy element menu jest skonfigurowany tak, aby można było znaleźć otwarte zamówienia zakupu, które zgodnie z oczekiwaniami będą docierać dzisiaj.

    Aby określić sposób sortowania listy, można ustawić sortowanie na **karcie Sortowanie**.

1. Oprócz zdefiniowania kwerendy należy wybrać pola, które będą wyświetlane na kartach na stronie listy zapytań. Dlatego w okienku akcji wybierz **Lista pól**.
1. Na stronie **Lista pól** ustaw następujące wartości:

    - **Wyświetl pole 1:** *PurchName* (to pole będzie wyświetlane jako nagłówek każdej karty)
    - **Pole wyświetlane 2:** *PurchId*
    - **Pole wyświetlane 3:** *PurchStatus*
    - **Pole wyświetlane 4:** *DlvMode*
    - **Pole wyświetlane 5:** *DlvTerm*
    - **Pole wyświetlane 6:** *OrderAccount*
    - **Pole wyświetlania 7:** *VendorName()* (Ta wartość jest metodą wyświetlania, co wskazuje „()” na końcu)

1. Na okienku akcji wybierz opcję **Zapisz**. Następnie zamknij stronę.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>Utwórz pozycję menu „Wyszukaj zamówienia zakupu według pozycji”

Aby utworzyć **pozycję menu Wyszukiwania pozyskanych towarów** według pozycji, należy wykonać następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać element menu urządzenia mobilnego.
1. Ustaw następujące wartości dla nowego elementu:

    - **Nazwa pozycji menu:** *Szukaj pozyskanych towarów według pozycji*
    - **Tytuł:** *poszukaj poos według pozycji*
    - **Tryb:** *Pośrednie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Kod działania:** *zapytanie o dane*
    - **Użyj przewodnika po procesach:** *Tak* (ta wartość jest zaznaczona automatycznie)
    - **Nazwa tabeli:** *PurchLine* (użytkownik chce szukać numerów zamówień zakupu na podstawie numeru towaru przy użyciu danych wiersza)

1. W okienku akcji wybierz opcję **Edytuj kwerendę**, aby zdefiniować kwerendę opartą na wybranej tabeli podstawowej (w tym przypadku tabeli wierszy zamówienia zakupu, ale możesz użyć dowolnych wartości, które są powiązane z nagłówkiem, przystępując do *PurchTable*).
1. W edytorze zapytań na karcie **Zakres** dodaj następujące wiersze do siatki.

    | Tabela | Tabela pochodna | Pole | Kryterium |
    |---|---|---|---|
    | Wiersze zamówienia zakupu | Wiersze zamówienia zakupu | Stan wiersza | Otwarte zamówienie |
    | Wiersze zamówienia zakupu | Wiersze zamówienia zakupu | Data dostawy | (dayRange(-10,10)) |
    | Wiersze zamówienia zakupu | Wiersze zamówienia zakupu | Numer towaru | |

1. Kliknij przycisk **OK**.

    W tym przykładzie nowy element menu jest skonfigurowany tak, aby znajdować otwarte wiersze zamówienia zakupu, które mają dotrzeć w dowolnym momencie od 10 dni w przeszłości do 10 dni w przyszłości.

    W kwerendzie kolumna **Kryteria** dla *Numer przedmiotu* była pusta. W związku z tym pracownicy będą mogli określać tę wartość w trakcie używania aplikacji mobilnej Warehouse Management.

    Aby określić sposób sortowania listy, można ustawić sortowanie na **karcie Sortowanie**.

1. Oprócz zdefiniowania kwerendy należy wybrać pola, które będą wyświetlane na kartach na stronie listy zapytań. Dlatego w okienku akcji wybierz **Lista pól**.
1. Na stronie **Lista pól** ustaw następujące wartości:

    - **Wyświetl pole 1:** *PurchId* (Ta wartość pola będzie używana jako nagłówek dla każdej karty)
    - **Pole wyświetlane 2:** *VendAccount*
    - **Pole wyświetlane 3:** *PurchQty*
    - **Pole wyświetlane 4:** *PurchUnit*
    - **Pole wyświetlane 5:** *PurchStatus*

1. Na okienku akcji wybierz opcję **Zapisz**. Następnie zamknij stronę.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Dodaj nowe pozycje menu urządzenia mobilnego do menu

Trzy nowe elementy menu urządzenia przenośnego są teraz gotowe do dodania do menu urządzenia przenośnego. To zadanie musi zostać wykonane, zanim elementy menu będą mogły być używane jako część procesu objazdu. W tym przykładzie trzeba utworzyć nowy podmenu i dodać do niego nowe elementy menu.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Ustaw następujące wartości w nagłówku nowego rekordu:

    - **Nazwa:** *Zapytanie*
    - **Opis:** *Uzyskiwanie informacji*

1. W siatce **Dostępne menu i elementy menu** znajdź i wybierz pierwszy z elementów menu urządzenia mobilnego, które właśnie utworzyłeś. Wybierz przycisk strzałki w prawo, aby przenieść wybraną pozycję menu na listę **Struktura menu**.
1. Powtórz poprzedni krok dla pozostałych dwóch nowych elementów menu.
1. W okienku listy po lewej stronie wybierz **menu Główne**.
1. Z listy **Dostępne menu i elementy menu** przewiń do sekcji **Menu** i wybierz nowe menu **Zapytanie**. Wybierz przycisk strzałki w prawo, aby przenieść wybraną pozycję menu na listę **Struktura menu**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>Skonfiguruj objazdy w krokach urządzenia mobilnego

Aby ukończyć konfigurację, musisz teraz użyć konfiguracji objazdu na stronie **Kroki dotyczące urządzenia mobilnego**, aby dodać trzy nowe pozycje menu urządzenia mobilnego do istniejącego kroku identyfikacji zamówienia w procesie *Odbiór zakupu*.

1. Wybierz kolejno opcje **Warehouse management \> Ustawienia > Urządzenie przenośne \> Kroki urządzenia przenośnego**.
1. W polu **Filtr** wprowadź nazwę *PONum*. Następnie z listy rozwijanej wybierz pozycję *Identyfikator kroku: „PONum"*.
1. W trakcie wybierania rekordu w siatce wybierz opcję **Dodaj konfigurację kroku** w okienku akcji. W wyświetlonym rozwijanym oknie dialogowym ustaw pole **Pozycja menu**, aby znaleźć i wybrać *Zakup odbiór*. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Na skróconej karcie szczegółów nowej konfiguracji kroku (**Zakup do otrzymania: PONum**) na skróconej karcie **Dostępne objazdy (pozycje menu)** za pomocą menu wybierz pozycję **Dodaj** na pasku narzędzi.
1. W oknie dialogowym **Dodaj objazd** znajdź i wybierz wcześniej utworzony element menu **Wyszukaj zamówienia zakupu według dostawcy**.
1. Wybierz **przycisk OK**, aby zamknąć okno dialogowe i dodać wybrany element menu do listy objazdów.
1. Wybierz nowy objazd, a następnie wybierz pola **Wybierz do wysłania** na pasku narzędzi.
1. W oknie dialogowym **Wybierz pola do wysłania** nie dodawaj niczego do sekcji **Wyślij od odbioru**, ponieważ nie chcesz przekazywać żadnych wartości do elementu menu objazdu. Jednak w sekcji **Przywróć z wyszukiwania POS** według dostawców ustaw następującą wartość dla pustego wiersza, który już został dodany tam:

    - **Kopiuj z wyszukiwania pos według dostawców:** *zamówienie zakupu*
    - **Wklej do odbioru zakupu:** *zamówienie zakupu*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Powtórz kroki od 4 do 9 dla pozostałych dwóch nowych elementów menu (**Poszukaj zamówienia na dzisiaj** i **Poszukaj zamówienia według pozycji**). Jeśli chodzi o pozycję menu **Wyszukaj zamówienia zakupu według dostawcy**, nie chcesz wysyłać żadnych danych do tych objazdów, ale chcesz zwrócić numer zamówienia zakupu.
1. Zamknij stronę.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Wypróbuj proces przyjmowania zakupów, który zawiera zapytanie o dane w ramach objazdu

Aby przetestować konfigurację nowej aplikacji mobilnej, należy wykonać następujące kroki.

1. Umożliwia utworzenie kilku zamówień zakupu z wierszami dla magazynu 51.
1. Przejdź do urządzenia przenośnego lub emulatora, na którym uruchomiono aplikację Warehouse Management, i zaloguj się do magazynu 51, używając *51* jako identyfikatora użytkownika i *1* jako hasła.
1. W menu aplikacji mobilnej wybierz opcję **Przychodzące,** a następnie **Odbierz zakup**.

    Powinna to być strona z trzema nowymi elementami menu.

    ![Przyjęcie na zakup przy użyciu numeru zamówienia zakupu.](media/wma-purchase-receive-po-num-with-detours.png "Przyjęcie na zakup przy użyciu numeru zamówienia zakupu")

1. Spróbuj użyć różnych możliwości i zwróć uwagę, że numer zamówienia zakupu można wysłać, wybierając jedną z kart na liście.

    ![Przyjęcie na zakup przy użyciu wyszukiwania zamówienia zakupu według dostawcy, przykład 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Przyjęcie na zakup przy użyciu wyszukiwania zamówienia zakupu według dostawcy, przykład 1")

    ![Przyjęcie na zakup przy użyciu wyszukiwania zamówienia zakupu według dostawcy, przykład 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Przyjęcie na zakup przy użyciu wyszukiwania zamówienia zakupu według dostawcy, przykład 2")

> [!TIP]
> Zamiast uruchamiać przepływ odbierania, wykonując wyszukiwanie z pozycji menu **Odbiór zakupu**, możesz zacząć od przepływu zapytania (**Główne \> Zapytanie \> Wyszukaj PO według dostawcy**) i wywołaj objazd, aby uruchomić żądany przepływ, wybierając jedną z kart z listy. Aby skorzystać z tego podejścia, możesz zdefiniować objazd na stronie **Kroki dotyczące urządzenia mobilnego** dla kroku, który ma wartość **Identyfikator kroku** *GenericDataInquiryList*. Ponieważ ten przepływ jest przepływem objazdowym, nie możesz wywołać z niego kolejnych objazdów. Dlatego po przejściu na przykład do ekranu wprowadzania numeru pozycji wyszukiwanie nie będzie na nim dostępne, ponieważ system obecnie obsługuje tylko jeden poziom objazdów.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
