---
title: Grupowanie szablonów grup czynności
description: Grupowanie szablonów grupy czynności umożliwia systemowi korzystanie z ustawień szablonu grupy czynności w celu określenia, na podstawie zdefiniowanych kryteriów, sposobu podziału zwolnionych wierszy i przypisania ich do nowych lub istniejących grup czynności. Ta funkcja może być przydatna w magazynach, w których grupy czynności są tworzone na podstawie określonych kryteriów, w przypadku gdy kierownicy preferują automatyczne, a nie ręczne, tworzenie grup czynności.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: a48e6a81299badf4b811e1cf905beb06099e5a24
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335984"
---
# <a name="wave-template-grouping"></a>Grupowanie szablonów grup czynności

[!include [banner](../includes/banner.md)]

Grupowanie szablonów grupy czynności umożliwia systemowi korzystanie z ustawień [szablonu grupy czynności](tasks/configure-wave-processing.md) w celu określenia, na podstawie zdefiniowanych kryteriów, sposobu podziału zwolnionych wierszy i przypisania ich do nowych lub istniejących grup czynności. Ta funkcja może być przydatna w magazynach, w których grupy czynności są tworzone na podstawie określonych kryteriów, w przypadku gdy kierownicy preferują automatyczne, a nie ręczne, tworzenie grup czynności. Umożliwia systemowi dodanie każdej nowo zwolnionej wysyłki do pierwszej grupy czynności, która ma odpowiednie wartości pól grupowania. Jeśli nie zostanie znaleziony żadne trafienie, system utworzy nową podstawę dla nowej wysyłki.

> [!IMPORTANT]
> Grupowanie szablonów grupy czynności nie jest obsługiwane w przypadku typów pracy *pobieranie surowca produkcyjnego* lub *pobieranie Kanban*. Jest to spowodowane tym, że grupowanie grupy czynności jest oparte na wysyłkach, a te typy prac nie używają wysyłek.

## <a name="turn-on-the-wave-template-grouping-feature"></a>Włączanie funkcji grupowania szablonów grupy czynności

Aby móc używać funkcji *Grupowania szablonów grupy czynności*, należy ją włączyć dla systemu. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Grupowania szablonów grupy czynności*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Ustawienie szablonu grupy czynności do korzystania z szablonu grupowania grupy czynności

Aby udostępnić grupowanie szablonów grupy czynności, należy wykonać poniższe kroki w celu skonfigurowania [szablonu grupy czynności](tasks/configure-wave-processing.md).

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. W lewym okienku wybierz szablon grupy czynności do ustawienia. Jeśli chcesz później przejść przez scenariusz w tym artykule korzystając z danych demonstracyjnych, wybierz szablon **62 Domyślna wysyłka**.
1. Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Automatyczne tworzenie grupy czynności:** *Tak*
    - **Przypisz do otwartych grup czynności:** *Tak*
    - **Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu:** *Nie*

1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe kwerendy.
1. W oknie dialogowym kwerenda, na karcie **Sortowanie**, przejrzyj kryteria sortowania i upewnij się, że istnieje reguła obejmująca pole, którego chcesz użyć do grupowania grup czynności.

    Jeśli pracujesz przy użyciu danych demonstracyjnych w ramach scenariusza, należy dodać wiersz o następujących wartościach:

    - **Tabela:** *Wysyłki*
    - **Tabela pochodna:** *Wysyłki*
    - **Pole:** *Usługa przewozowa*

        > [!NOTE]
        > Po wybraniu tej wartości może zostać wyświetlony następujący komunikat: „Usługa przewoźnika nie jest polem indeksu. Czy na pewno chcesz dodać sortowanie według tego kryterium?” Wybierz opcję **Tak**, aby dodać sortowanie.

    - **Kierunek wyszukiwania:** *Rosnąco*

1. Wybierz przycisk **OK**, aby zapisać zmiany i zamknąć okno dialogowe kwerendy.
1. W okienku akcji wybierz opcję **Grupowanie szablonu grupy czynności**.
1. Na stronie **Grupowanie szablonów grupy czynności** zaznacz pole wyboru **Grupuj według** dla każdego wiersza, który ma być używany do grupowania wierszy zamówienia w grupy zamówień w zależności od potrzeb. Jeśli przygotowujesz się do pracy w ramach scenariusza przy użyciu danych demonstracyjnych, zaznacz pole wyboru **Grupuj według** dla wiersza *Usługi przewoźnika*.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę **Grupowanie szablonów grupy czynności**.
1. Wybierz **Zapisz**, żeby zapisać szablon.

## <a name="scenario"></a>Scenariusz

Ta sekcja zawiera skrypt, z którego można się dowiedzieć, jak działa ta funkcja i jak jej używać.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tego scenariusza można również używać jako wskazówek dotyczących danej funkcji podczas pracy w produkcji. Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.

### <a name="scenario-wave-template-grouping"></a>Scenariusz: Grupowanie szablonów grup czynności

W tym scenariuszu przedstawiono sposób użycia grupowania szablonów grupy czynności w celu automatycznego tworzenia wielu grup czynności na podstawie kryteriów grupowania zdefiniowanych w szablonie grupy czynności. W tym scenariuszu szablon grupy czynności jest konfigurowany w systemie w celu utworzenia jednej grupy czynności dla każdej usługi przewozowej.

Przed rozpoczęciem Przygotuj szablon grupy czynności, tak jak opisano to sekcji [Konfigurowanie szablonu grupy czynności, aby korzystać z funkcji grupowania szablonów grup czynności](#set-up-template) wcześniej w tym artykule. Jeśli użytkownik będzie pracować z danymi demonstracyjnymi w tym scenariuszu, należy pamiętać o użyciu wartości danych demonstracyjnych, które są sugerowane w tej procedurze. Ta konfiguracja umożliwia grupowanie grup czynności zgodnie z usługą przewoźnika ustawioną dla każdego zamówienia sprzedaży.

#### <a name="create-sales-order-1"></a>Utwórz zamówienie sprzedaży 1

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-004*.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.
1. Nowe zamówienie sprzedaży jest otwierane w widoku **Wiersza**. Zanotuj numer zamówienia sprzedaży.
1. Przełącz do widoku **nagłówka**.
1. Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:

    - **Przewoźnik:** *Transport lotniczy*
    - **Usługa przewozowa:** *Lotnicza*

1. Przełącz się z powrotem do widoku **Wiersz**.
1. W sekcji **Wiersze zamówienia sprzedaży** kliknij przycisk **Dodaj wiersze**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *2*

1. Zaznacz nowy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia. Należy zanotować numer identyfikacyjny grupy czynności oraz wysyłki.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Wyświetl grupę czynności, która została utworzona na podstawie zamówienia sprzedaży 1

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz identyfikator grupy czynności, która została utworzona na podstawie zamówienia sprzedaży.
1. Wybierz łącze identyfikatora grupy czynności, aby otworzyć stronę szczegółów.
1. Należy zauważyć, że wysyłka została dodana do skróconej karty **Wierszy grupy czynności**.

#### <a name="create-sales-order-2"></a>Utwórz zamówienie sprzedaży 2

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-005*.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.
1. Nowe zamówienie sprzedaży jest otwierane w widoku **Wiersza**. Zanotuj numer zamówienia sprzedaży.
1. Przełącz do widoku **nagłówka**.
1. Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:

    - **Przewoźnik:** *Przenoszenie kwiatów*
    - **Usługa przewozowa:** *Standard*

1. Przełącz się z powrotem do widoku **Wiersz**.
1. W sekcji **Wiersze zamówienia sprzedaży** kliknij przycisk **Dodaj wiersze**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *1*

1. Zaznacz nowy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia. Należy zanotować numer identyfikacyjny grupy czynności oraz wysyłki. Zauważ, że identyfikator grupy czynności jest różny od identyfikatora grupy czynności dla pierwszego zamówienia sprzedaży.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>Wyświetl grupę czynności, która została utworzona na podstawie zamówienia sprzedaży 2

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz identyfikator grupy czynności, która została utworzona na podstawie drugiego zamówienia sprzedaży.
1. Wybierz łącze identyfikatora grupy czynności, aby otworzyć stronę szczegółów.
1. Należy zauważyć, że wysyłka została dodana do skróconej karty **Wierszy grupy czynności**.

Dla tej wysyłki utworzono nową grupę czynności, ponieważ używa ona innej usługi przewozowej niż pierwsze zamówienie sprzedaży.

#### <a name="create-sales-order-3"></a>Utwórz zamówienie sprzedaży 3

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-006*.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.
1. Nowe zamówienie sprzedaży jest otwierane w widoku **Wiersza**. Zanotuj numer zamówienia sprzedaży.
1. Przełącz do widoku **nagłówka**.
1. Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:

    - **Przewoźnik:** *Transport lotniczy*
    - **Usługa przewozowa:** *Lotnicza*

1. Przełącz się z powrotem do widoku **Wiersz**.
1. W sekcji **Wiersze zamówienia sprzedaży** kliknij przycisk **Dodaj wiersze**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *1*

1. Zaznacz nowy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia. Należy zanotować numer identyfikacyjny grupy czynności oraz wysyłki. Wysyłka została przypisana do istniejącej grupy czynności w pierwszym zamówieniu sprzedaży.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Wyświetl grupy czynności dla zamówień sprzedaży 1 i 3

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz identyfikator grupy czynności, która została utworzona na podstawie trzeciego zamówienia sprzedaży.
1. Wybierz łącze identyfikatora grupy czynności, aby otworzyć stronę szczegółów.
1. Należy zauważyć, że wysyłka została dodana do skróconej karty **Wierszy grupy czynności** wraz z wysyłką dla pierwszego zamówienia sprzedaży.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]