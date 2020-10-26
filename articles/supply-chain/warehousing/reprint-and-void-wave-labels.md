---
title: ponowne drukowanie i unieważnienie etykiet grup czynności
description: W tym temacie wyjaśniono sposób unieważnienia i ponownego drukowania istniejących etykiet grupy czynności.
author: GarmMSFT
manager: PJacobse
ms.date: 07/09/2020
ms.topic: reprint-and-void-wave-labels
ms.service: dynamics-ax-applications
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 0b831361631aa66712813706eaa4ff3339683868
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986654"
---
# <a name="reprint-and-void-wave-labels"></a>ponowne drukowanie i unieważnienie etykiet grup czynności

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zarządzania etykietami generowanymi przez przetwarzanie grup czynności. (Aby uzyskać szczegółowy opis i instrukcje dotyczące konfiguracji, należy zapoznać się z tematem [Konfiguruj drukowanie etykiet grupy czynności](../warehousing/configure-wave-label-printing.md).)

Etykiety grupy czynności można ponownie wydrukować w dowolnym momencie. Na przykład może być konieczne wydrukowanie pojedynczej etykiety, jeśli istniejąca etykieta została utracona lub zniszczona. Alternatywnie pracownik magazynu lub przełożony musi mieć możliwość ponownego wydrukowania całej etykiety, jeśli liczba i/lub skład całej serii etykiet grupy czynności uległ zmianie (np. ze względu na niedobory w magazynie lub inne przyczyny). Często, nawet jeśli tylko liczba kartonów uległa zmianie, cały rzut musi zostać wydrukowany w celu zachowania dokładnej liczby w sekcji „Karton X z Y” każdej etykiety.

Funkcja ponownego drukowania etykiet grupy czynności obsługuje następujące funkcje:

- Umożliwia ponowne wydrukowanie etykiet z aplikacji magazynowania i klienta wzbogaconego.
- Anuluj etykiety i jednocześnie je ponownie drukuj. (Na przykład, możliwość unieważnienia etykiet jest osadzana w krótkich scenariuszach pobierania.)
- Czyszczenie historii etykiety grupy czynności.

W tym temacie przedstawiono zbiór scenariuszy przedstawiających, za pomocą przykładów, sposób pracy z funkcją ponownego drukowania etykiet grupy czynności.

> [!IMPORTANT]
> Aby pracować w scenariuszach przedstawionych w tym temacie, należy najpierw włączyć i skonfigurować odpowiednie funkcje drukowania grupy czynności, tak jak to opisano w temacie [Konfiguruj drukowanie etykiet grupy czynności](../warehousing/configure-wave-label-printing.md). Niektóre scenariusze w tym temacie wymagają również, aby najpierw przejść przez scenariusze w tym temacie, aby wygenerować wstępnie wymagane dane przykładowe.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>Scenariusz 1: ponowne drukowanie etykiet od klienta sieci Web

Etykiety grupy czynności można przeglądać i ponownie drukować z następujących stron. W okienku akcji na każdej stronie na karcie **Wysyłki**, w grupie **Informacje pokrewne** wybierz **Etykiety grupy czynności**.

- Wszystkie wysyłki \> Szczegóły wysyłki
- Wszystkie ładunki \> Szczegóły ładunku
- Wszystkie grupy czynności
- Etykiety grup czynności
- Historia etykiet grupy czynności

Aby ponownie wydrukować etykietę grupy czynności na kliencie sieci Web, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz etap, z którego chcesz ponownie wydrukować etykiety.
1. W okienku akcji na karcie **Grupa czynności** w grupie **Drukuj** wybierz opcję **Etykiety grup czynności**.
1. Wykonaj jedną lub obie z następujących czynności:

    - Aby ponownie wydrukować etykietę, w polu **Nazwa drukarki** wybierz drukarkę. (Należy pozostawić to pole puste, jeśli chcesz zaktualizować szczegóły etykiety grupy czynności bez konieczności ponownego drukowania etykiety.)
    - Aby zaktualizować etykietę, zaznacz pole wyboru **Aktualizuj szczegóły etykiety grupy czynności**. (Pozostaw to pole wyboru wyczyszczone, jeśli chcesz tylko ponownie wydrukować poprzednią etykietę.)

    > [!NOTE]
    > Za każdym razem, gdy etykieta grupy czynności jest drukowana lub ponownie drukowana, jej dane są konwertowane za pomocą odpowiedniego układu etykietek, a wszystkie symbole zastępcze są zastępowane wartościami rzeczywistymi. Ciąg wynikowy jest przechowywany jako rekord w historii etykiet grupy czynności. Jeśli pole wyboru **Aktualizuj szczegóły etykiety grupy czynności** jest wyczyszczone, zapisane dane języka programowania Zebra (ZPL) są używane podczas ponownego drukowania etykiety. Jeśli zaznaczono pole wyboru **Aktualizuj szczegóły etykiety grupy czynności**, generowany jest nowy ciąg. Istniejące etykiety grupy czynności są również ponownie obliczane, a wszystkie nadmiarowe etykiety (na przykład, jeśli powiązane z nimi wiersze pracy zostały anulowane lub zmodyfikowane) są oznaczane jako **Unieważnione** i nie są ponownie drukowane.

1. Wybierz przycisk **OK**, aby potwierdzić wybór opcji.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>Scenariusz 2: ponowne drukowanie etykiet z aplikacji magazynowania

Ten scenariusz zazwyczaj ma zastosowanie, jeśli wystąpiła utrata lub uszkodzenie etykiety. Przedstawia on przykład, w jaki sposób skonfigurować elementy menu urządzeń przenośnych, które pozwolą pracownikom ponownie drukować jedną i wiele etykiet. Następnie pokazano sposób używania tych nowych elementów menu podczas pracy z urządzeniem przenośnym.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>Ustaw wymagane elementy menu i menu dla urządzenia przenośnego

Aby umożliwić pracownikom ponowne wydrukowanie etykiet z urządzenia przenośnego, należy skonfigurować elementy menu w celu udostępnienia tych funkcji, a następnie dodać te pozycje do menu aplikacji magazynowej.

#### <a name="create-new-mobile-device-menu-items"></a>Utwórz nowe elementy menu w urządzeniu przenośnym

Wykonaj poniższe kroki, aby utworzyć nową kolekcję elementów menu służących do ponownego drukowania etykiet z aplikacji magazynowania.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Utwórz element menu i określ dla niego następujące wartości:

    - **Nazwa elementu menu:** *Ponownie drukuj jedną etykietę grupy czynności*
    - **Tytuł:** *Ponownie drukuj jedną etykietę grupy czynności*
    - **Tryb:** *Pośrednie*
    - **Kod działania:** *Ponownie drukuj jedną etykietę grupy czynności*

1. Utwórz drugi element menu i określ dla niego następujące wartości:

    - **Nazwa elementu menu:** *Ponownie drukuj etykiety (pozycja)*
    - **Tytuł:** *Ponownie drukuj etykiety grupy czynności (pozycja)*
    - **Tryb:** *Pośrednie*
    - **Kod działania:** *Ponownie drukuj wiele etykiet grupy czynności*
    - **Wyświetl filtr grupowania listy prac:** *Tak*
    - **Pole grup systemowych:** *ShipmentID*
    - **Etykieta grup systemowych:** *Identyfikator wysyłki*
    - **Tryb drukowania:** *Produkt*

1. W okienku akcji wybierz opcję **Lista pól**, aby otworzyć stronę, na której możesz wybrać pola, które będą wyświetlane, aby pomóc pracownikom w zidentyfikowaniu właściwego rolki etykiety.
1. Można wyświetlić maksymalnie siedem pól. Listy rozwijane służą do wybierania pola wyświetlanego w poszczególnych dostępnych stanowiskach. Pozostaw wszystkie pola, które nie są wymagane jako puste. 

    Oto przykład:

    - **Pole wyświetlane:** *LabelItemId*
    - **Pole wyświetlane 2:** *LabelItemName*
    - **Pole wyświetlane 3:** *InventQty*
    - **Pole wyświetlane 4:** *LabelUnitId*

1. Zamknij stronę.
1. Utwórz trzeci element menu i określ dla niego następujące wartości:

    - **Nazwa elementu menu:** *Ponownie drukuj etykiety (Wyliczenie)*
    - **Tytuł:** *Ponownie drukuj etykiety grupy czynności (Wyliczenie)*
    - **Tryb:** *Pośrednie**
    - **Kod działania:** *Ponownie drukuj wiele etykiet grupy czynności*
    - **Wyświetl filtr grupowania listy prac:** *Tak*
    - **Pole grup systemowych:** *ShipmentID*
    - **Etykieta grup systemowych:** *Identyfikator wysyłki*
    - **Tryb drukowania:** *Wyliczenie*

1. W okienku akcji wybierz opcję **Lista pól**, a następnie użyj list rozwijanych, aby wybrać pola, które będą wyświetlane, aby pomóc pracownikom w zidentyfikowaniu odpowiedniej rolki etykiety (na przykład *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* i *NumberOfLabels*).
1. Zamknij stronę.
1. Utwórz czwarty element menu i określ dla niego następujące wartości:

    - **Nazwa elementu menu:** *Ponownie drukuj etykiety (według ostatniego)*
    - **Tytuł:** *Ponownie drukuj etykiety grupy czynności (według ostatniego)*
    - **Tryb:** *Pośrednie*
    - **Kod działania:** *Ponownie drukuj wiele etykiet grupy czynności*
    - **Wyświetl filtr grupowania listy prac:** *Tak*
    - **Pole grup systemowych:** *ShipmentID*
    - **Etykieta grup systemowych:** *Identyfikator wysyłki*
    - **Tryb drukowania:** *Ostatni dobry identyfikator etykiety grupy czynności*

1. W okienku akcji wybierz opcję **Lista pól**, a następnie użyj list rozwijanych, aby wybrać pola, które będą wyświetlane, aby pomóc pracownikom w zidentyfikowaniu odpowiedniej rolki etykiety (na przykład *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* i *NumberOfLabels*).
1. Zamknij stronę.

#### <a name="set-up-the-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

Aby dodać nowe elementy menu do menu aplikacji do magazynowania, należy wykonać poniższe kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Wybierz istniejące menu **Wychodzące**.
1. Na liście po lewej stronie odszukaj nowo utworzone elementy menu ponownego drukowania, a następnie za pomocą przycisku strzałki w prawo dodaj je do listy po prawej stronie.
1. Zamknij stronę.

### <a name="use-cases"></a>Przypadki użycia

W przedstawionych tu przypadkach użycia zamieszczono przykłady pokazujące sposób używania różnych elementów menu urządzeń przenośnych, które zostały skonfigurowane, aby pracownicy mogli ponownie drukować etykiety grupy czynności.

Przed rozpoczęciem pracy z tymi przypadkami użycia należy wprowadzić następujące wymagania wstępne:

- Muszą być zainstalowane dane demonstracyjne i należy wybrać firmę **USMF**.
- Drukowanie etykiet grupy czynności musi być skonfigurowane, a niektóre etykiety należy wygenerować, tak jak to opisano w temacie [Konfiguruj drukowanie etykiet grupy czynności](../warehousing/configure-wave-label-printing.md).

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>Przypadek użycia 2.1: Jedna etykieta grupy czynności jest porysowana i musi zostać wydrukowana ponownie.

1. Zaloguj się do aplikacji magazynowania jako użytkownik, który ma dostęp do magazynu *62*. (W standardowych danych demonstracyjnych można zalogować się, używając *62* jako identyfikatora użytkownika i *1* jako hasła.)
1. Przejdź do **Wychodzące \> Ponownie drukuj jedną etykietę grupy czynności**.
1. Wprowadź lub zeskanuj identyfikator etykiety grupy czynności.
1. Wybierz drukarkę, na której chcesz wydrukować ponownie.
1. Wybierz przycisk **OK**, aby zatwierdzić akcję.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>Przypadek użycia 2.2: Kilka etykiet dla pól tego samego towaru zostało uszkodzonych i trzeba je wydrukować ponownie. Każda etykieta ma kod kreskowy produktu, ale nie ma wyliczenia ani numeru SSCC.

1. Zaloguj się do aplikacji magazynowania jako użytkownik, który ma dostęp do magazynu *62*. (W standardowych danych demonstracyjnych można zalogować się, używając *62* jako identyfikatora użytkownika i *1* jako hasła.)
1. Przejdź do **Wychodzące \> Ponownie drukuj etykiety (pozycja)**.
1. Wprowadź lub zeskanuj identyfikator wysyłki.
1. Wybierz kafelek z poprawnymi rolkami etykiety, z których będzie się ponownie drukować.
1. Zeskanuj kod kreskowy produktu z istniejącej etykiety, aby potwierdzić, że wybrano poprawny wiersz.
1. Wprowadź liczbę etykiet do ponownego wydrukowania.
1. Wybierz drukarkę, na której chcesz wydrukować ponownie.
1. Wybierz przycisk **OK**, aby zatwierdzić akcję.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>Przypadek użycia 2.3: Kilka etykiet na pudełka nie zostało wydrukowanych z powodu zacięcia się drukarki. Ponieważ etykiety zawierają wyliczenie, można zdefiniować zakres kartonów do ponownego wydrukowania.

1. Zaloguj się do aplikacji magazynowania jako użytkownik, który ma dostęp do magazynu *62*. (W standardowych danych demonstracyjnych można zalogować się, używając *62* jako identyfikatora użytkownika i *1* jako hasła.)
1. Przejdź do **Wychodzące \> Ponownie drukuj etykiety (Wyliczenie)**.
1. Wprowadź lub zeskanuj identyfikator wysyłki.
1. Wybierz kafelek z poprawnymi rolkami etykiety, z których będzie się ponownie drukować.
1. Wprowadź pierwszy karton, dla którego chcesz ponownie wydrukować etykietę.
1. Wprowadź ostatni karton, dla którego chcesz ponownie wydrukować etykietę. Możesz również pozostawić to pole puste, aby wydrukować etykiety wszystkich kartonów po określonym pierwszym kartonie.
1. Wybierz drukarkę, na której chcesz wydrukować ponownie.
1. Wybierz przycisk **OK**, aby zatwierdzić akcję.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>Przypadek użycia 2.4: Kilka etykiet na pudełka nie zostało wydrukowanych z powodu zacięcia się drukarki. Ostatnia dobra etykieta ma identyfikator etykiety grupy czynności, który jest drukowany jako kod kreskowy.

1. Zaloguj się do aplikacji magazynowania jako użytkownik, który ma dostęp do magazynu *62*. (W standardowych danych demonstracyjnych można zalogować się, używając *62* jako identyfikatora użytkownika i *1* jako hasła.)
1. Przejdź do **Wychodzące \> Ponownie drukuj etykiety (według ostatniego)**.
1. Wprowadź lub zeskanuj identyfikator wysyłki.
1. Wybierz kafelek z poprawnymi rolkami etykiety, z których będzie się ponownie drukować.
1. Wprowadź lub zeskanuj identyfikator etykiety grupy czynności ostatniej dobrej etykiety grupy czynności. Aplikacja identyfikuje następną etykietę w sekwencji jako pierwszy karton, dla którego zostanie wydrukowana etykieta.
1. Wprowadź ostatni karton, dla którego chcesz ponownie wydrukować etykietę. Możesz również pozostawić to pole puste, aby wydrukować etykiety wszystkich kartonów po określonym pierwszym kartonie.
1. Wybierz drukarkę, na której chcesz wydrukować ponownie.
1. Wybierz przycisk **OK**, aby zatwierdzić akcję.

## <a name="scenario-3-short-pick-and-reprint"></a>Scenariusz 3: Krótkie pobranie i ponowne wydrukowanie

Przed rozpoczęciem pracy z tym scenariuszem użycia należy wprowadzić następujące wymagania wstępne:

- Muszą być zainstalowane dane demonstracyjne i należy wybrać firmę **USMF**.
- Drukowanie etykiet grupy czynności musi być skonfigurowane, a niektóre etykiety należy wygenerować, tak jak to opisano w temacie [Konfiguruj drukowanie etykiet grupy czynności](../warehousing/configure-wave-label-printing.md).

### <a name="set-up-work-exceptions"></a>Ustaw wyjątki pracy

Wyjątki pracy kontrolują zachowanie krótkiego pobrania. Wykonaj poniższe czynności, aby skonfigurować wyjątek pracy.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Wyjątki dotyczące pracy**.
1. Dodaj rekord z następującymi ustawieniami:

    - **Kod wyjątku pracy:** *krótkie pobranie i drukowanie*
    - **Typ wyjątku:** *krótkie pobranie*
    - **Sugeruj ponowne drukowanie etykiet grupy czynności:** *Tak*

### <a name="void-and-reprint-after-a-short-pick"></a>Unieważnij i ponownie wydrukuj po krótkim pobraniu

1. Zaloguj się do aplikacji magazynowania jako użytkownik, który ma dostęp do magazynu *62*. (W standardowych danych demonstracyjnych można zalogować się, używając *62* jako identyfikatora użytkownika i *1* jako hasła.)
1. Umożliwia otwarcie przepływu pracy dla zamówienia sprzedaży, które zostało utworzone podczas oryginalnego drukowania etykiet grupy czynności.
1. Wybierz opcję **Krótkie pobranie**.
1. Umożliwia wybranie kodu wyjątku pracy utworzonego dla tego scenariusza.
1. Jeśli wybrano poprawny wyjątek, pole wyboru **Unieważnij i ponownie drukuj** powinno być dostępne. Zaznacz to pole i potwierdź. Po potwierdzeniu, sekwencja rzutowania etykiet określona przez pole **Identyfikatora kompilacji etykiety** jest obliczana ponownie na podstawie zmienionej ilości w wierszu pracy. Następnie zostanie ponownie wydrukowana na określonej drukarce.
