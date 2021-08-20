---
title: Uzupełnianie zapasów na podstawie progu w strefie
description: W przypadku zapasów uzupełniających dla strefy używana jest minimalna/maksymalna (min./maks.) strategia uzupełniania zapasów, ale system ocenia całe strefy magazynowe, a nie tylko poszczególne lokalizacje. Dzięki temu kierownik magazynu może szybko rozpoznać, kiedy w strefie pobrania są wymagane dodatkowe zapasy.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4dde844d38448b2de5c5e0c9b2da4a16405f83c0d72f3a20b9e29afe84d322ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743489"
---
# <a name="zone-threshold-replenishment"></a>Uzupełnianie zapasów na podstawie progu w strefie

[!include [banner](../includes/banner.md)]

W przypadku zapasów uzupełnianych dla strefy używana jest minimalna/maksymalna (min./maks.) strategia [uzupełniania](replenishment.md) zapasów, ale system ocenia całe strefy magazynowe, a nie tylko poszczególne lokalizacje. Dzięki temu kierownik magazynu może szybko rozpoznać, kiedy w strefie pobrania są wymagane dodatkowe zapasy.

Ustawienia tej funkcji są podobne do ustawień uzupełniania w oparciu o lokalizację. Jednak podczas konfigurowania szablonu dla minimalnego/maksymalnego uzupełnienia zapasów można również określić, czy próg ma być oceniany według lokalizacji, czy dla każdej strefy. W przypadku skonfigurowania oceny opartej na strefach należy dodać określone strefy do zapytania wyboru strefy.

Podobnie jak w przypadku minimalnych/maksymalnych uzupełnień na podstawie lokalizacji, minimalne/maksymalne uzupełnienie w strefie jest oparte na konfiguracji minimalnego progu zapasów, który wyzwala tworzenie zlecenia pracy uzupełniania dla wybranych towarów. Ta praca uzupełnienia zapasów spowoduje zwiększenie ilości zapasów do określonego progu maksymalnego dla strefy.

> [!NOTE]
> Proces uzupełniania zapasów strefy dla wariantów produktów nie jest obsługiwany w bieżącej wersji.


W przeciwieństwie do minimalnych/maksymalnych uzupełnień na podstawie lokalizacji, wartość minimalna/maksymalna dla uzupełniania zapasów w strefie nie wymaga ustalonych lokalizacji, aby ocenić, czy lokalizacje powinny przechowywać określony towar. W związku z tym zapasy uzupełniające strefy umożliwiają korzystanie z minimalnych/maksymalnych uzupełnień, nawet jeśli nie utworzono żadnych stałych lokalizacji dla każdego wariantu towaru lub towaru w magazynie. Jeśli ilość w strefie spadnie poniżej określonego progu minimalnego, tworzone jest zlecenie pracy uzupełnienia. Dyrektywy lokalizacji określają lokalizację, do której należy wprowadzić zapasy.

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>Włącz funkcję Uzupełnianie zapasów na podstawie progu w strefie

Aby móc używać funkcji *Uzupełniania zapasów na podstawie progu w strefie*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Uzupełnianie zapasów na podstawie progu w strefie*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Konfigurowanie uzupełniania zapasów w strefie

Aby skonfigurować uzupełniania zapasów w strefie, należy skonfigurować kilka części systemu. W tej sekcji przedstawiono różne ustawienia oraz dostępne wartości danych demonstracyjnych, które można wprowadzić, aby wykonać czynności wykonywane w scenariuszu na końcu tego tematu.

### <a name="set-up-directive-codes"></a>Konfigurowanie kodów dyrektyw

[Kody dyrektyw](control-warehouse-location-directives.md) pozwalają na dokładniejsze określenie szablonu lokalizacji, który jest używany w szablonie pracy. Każdy kod określa wspólną wartość, do której można się odwoływać podczas konfigurowania każdego typu szablonu.

#### <a name="view-and-edit-directive-codes"></a>Wyświetlanie i edytowanie kodów dyrektyw

Aby wyświetlić lub edytować kody dyrektyw, przejdź do **Zarządzanie magazynem \> Konfiguracja \> Kody dyrektyw**.

#### <a name="prepare-demo-data-directive-codes"></a>Przygotowywanie kodów dyrektyw w danych demonstracyjnych

W tym przykładzie przedstawiono sposób przygotowania kodu dyrektywy. Jeśli planowane jest korzystanie z scenariusza na końcu tego tematu, należy skorzystać z przedstawionych tu wartości danych demonstracyjnych. W przeciwnym razie należy skorzystać z własnych wartości.

1. Wybierz firmę **USMF** do pracy z danymi demonstracyjnymi.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kody dyrektyw**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Kod dyrektywy:** _Uzupeł. stref._
    - **Opis dyrektywy:** _Uzupełnienie zapasów strefy_

1. Wybierz **Zapisz**, aby zapisać nowy kod.

### <a name="set-up-replenishment-templates"></a>Ustaw szablony uzupełniania zapasów

[Szablony uzupełniania zapasów według ilości min./maks.](tasks/set-up-min-max-replenishment-process.md) są podstawowym mechanizmem utrzymywania optymalnego poziomu zapasów w lokalizacjach pobrania. W tych szablonach należy skonfigurować reguły, które będą używane do uzupełniania zapasów w magazynie. Uzupełnienie, do którego mogą być używane szablony, w tym uzupełnienie w oparciu o strefy.

#### <a name="view-and-edit-replenishment-templates"></a>Umożliwia wyświetlanie i edytowanie szablonów uzupełniania

Szablon uzupełniania zapasów jest zestawem reguł, które sterują tym, kiedy i jak zapasy są uzupełniane w lokalizacji. Wybranie szablonu umożliwia kontrolowanie czasu i sposobu uzupełniania zapasów. Aby oglądać lub edytować szablony uzupełniania zapasów, wybierz **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów**.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Przygotowywanie demonstracyjnego szablonu uzupełniania danych

W tym przykładzie przedstawiono sposób przygotowania szablonu uzupełniania. Jeśli planowane jest korzystanie z scenariusza na końcu tego tematu, należy skorzystać z przedstawionych tu wartości danych demonstracyjnych. W przeciwnym razie należy skorzystać z własnych wartości.

1. Wybierz firmę **USMF** do pracy z danymi demonstracyjnymi.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów**.
1. Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać nowy wiersz do siatki **Przegląd**.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

    - **Szablon uzupełnienia:** _strefa min./maks. uzupeł_
    - **Opis::** _Uzupełnienie zapasów strefy min./maks._
    - **Typ uzupełnienia:** _minimum lub maksimum_

1. Wybierz opcję **Zapisz**.
1. Gdy nowy wiersz jest nadal zaznaczony w siatce **Przeglądu**, wybierz opcję **Nowy** nad siatką **Szczegóły szablonu uzupełnienia**, aby dodać wiersz skojarzony z właśnie utworzonym szablonem uzupełnienia zapasów *strefy min./maks.*
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** Wpisz _1_.
    - **Opis:** Wpisz _Wybierz uzupełnienie strefy_.
    - **Jednostka uzupełnienia:** Wybierz pozycję _ea_.
    - **Typ żądania:** pozostaw to pole puste.
    - **Kod dyrektywy:** To pole łączy się z szablonem uzupełniania zapasów za pomocą dyrektywy lokalizacyjnej. Wybierz wcześniej utworzony demonstracyjny kod dyrektywy danych (_strefa uzupeł_).
    - **Szablon pracy:** Pozostaw to pole puste.
    - **Ilość minimalna:** W tym polu jest ustawiana ilość, jaka będzie wyzwalać uzupełnianie zapasów. Wprowadź _50_.
    - **Maksymalna ilość:** W tym polu jest ustawiana maksymalna ilość towaru, która może być obecna w strefie. Wytworzona praca uzupełniająca spowoduje zwiększenie zapasów do tej ilości. Wprowadź _150_.
    - **Jednostka:** W tym polu jest ustawiana jednostka dla wartości minimalnej i maksymalnej. Wybierz _ea_.
    - **Przyrost popytu:** Wybierz opcję _Zaokrąglaj w górę_.
    - Zaznacz pole wyboru **Uzupełnij zapasy w pustych stałych lokalizacjach**.
    - Zaznacz pole wyboru **Uzupełniaj tylko stałe lokalizacje**.
    - **Tryb zapytania o produkt:** Wybierz _Zapytanie o produkt_.
    - **Zakres progu uzupełnienia zapasów:** to pole określa, czy szablon powinien oceniać według strefy, czy według konkretnej lokalizacji. Wybierz opcję _Strefa_.
    - **Magazyn:** Wybierz _61_.

1. Wybierz opcję **Wybierz produkty** powyżej siatki **Szczegóły szablonu uzupełnienia zapasów**.
1. W polu dialogowym **Zapytanie dot. produktu**, na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** _pozycje_
    - **Tabela pochodna:** _pozycje_
    - **Pole:** _numer pozycji_
    - **Kryteria:** _A0001_

1. Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.
1. Wybierz opcję **Wybierz strefy do uzupełnienia** powyżej siatki **Szczegóły szablonu uzupełnienia zapasów**.
1. W polu dialogowym **Zapytanie dot. strefy**, na karcie **Zakres**, dodaj wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** _strefa magazynowa_
    - **Tabela pochodna:** _strefa magazynowa_
    - **Pole:** _Identyfikator strefy_
    - **Kryteria:** _FLOOR_

1. Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.

### <a name="set-up-location-directives"></a>Ustaw dyrektywy lokalizacji

W przeciwieństwie do minimalnych/maksymalnych uzupełnień na podstawie lokalizacji, min./maks. uzupełnienie strefy wymaga skonfigurowania dyrektyw lokalizacji pobrania i lokalizacji odłożenia, ponieważ system ocenia całą strefę, a nie tylko lokalizację pobrania dla pracy wychodzącej.

#### <a name="view-and-edit-location-directives"></a>Przeglądanie i edytowanie dyrektyw lokalizacji

Aby wyświetlić lub edytować dyrektywy lokalizacji, przejdź do **Zarządzania magazynem \> Konfiguracja \> Dyrektywy lokalizacji**.

Aby zapoznać się z przykładami, w których można skorzystać z ustawień w celu utworzenia wymaganej dyrektywy dotyczącej pobrania i dyrektyw lokalizacji, należy zapoznać się z następną sekcją.

#### <a name="prepare-demo-data-location-directives"></a>Przygotowywanie danych demonstracyjnych dyrektyw lokalizacji

Aby przygotować dane demonstracyjne do użycia w scenariuszu na końcu tego tematu, należy utworzyć dwie dyrektywy lokalizacji: jedną do pobrania i jedną do umieszczenia.

##### <a name="create-a-replenishment-pick-directive"></a>Tworzenie dyrektywy pobierania uzupełniania zapasów

1. Wybierz firmę **USMF** do pracy z danymi demonstracyjnymi.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym okienku w polu **Typ zlecenia produkcyjnego** ustaw wartość na _uzupełnienie_.
1. W okienku akcji wybierz opcję **Nowa**, aby utworzyć nową dyrektywę.
1. Ustaw następujące wartości:

    - **Numer sekwencyjny:** Zaakceptuj wartość domyślną.
    - **Nazwa:** Wprowadź _pobranie w strefie_.
    - **Typ pracy:** Wybierz _Pobranie_.
    - **Placówka:** Wybierz _6_.
    - **Magazyn:** Wybierz _61_.
    - Pole **Kod dyrektywy:** należy pozostawić puste.
    - **Wiele jednostek SKU:** ustaw tą wartość na _Nie_.

1. Wybierz opcję **Zapisz**, aby utworzyć dyrektywę, w której skonfigurowano dotychczasowe ustawienia.
1. Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** Wpisz _1_.
    - **Ilość od:** Podaj _0_.
    - **Ilość do:** Podaj _10000000_.
    - **Jednostka:** pozostaw to pole puste.
    - **Znajdź ilość:** Wybierz opcję _Brak_.
    - Zaznacz lub wyczyść pole wyboru **Ogranicz według jednostki:**.
    - **Zaokrąglaj w górę do jednostki:** Wyczyść to pole wyboru.
    - **Znajdź ilość opakowań:** Wyczyść to pole wyboru.
    - Zaznacz pole wyboru **Zezwalaj na podział:**.

1. Wybierz **Zapisz**, aby zapisać nowy wiersz.
1. Gdy nowy wiersz jest wciąż zaznaczony w siatce **Wiersze**, wybierz opcję **Nowy** w skróconej karcie **Działania dyrektywy lokalizacji**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** Wpisz _1_.
    - **Nazwa:** Wprowadź _pobranie z partii_.
    - **Stałe użycie lokalizacji:** Wybierz _Stałe i niestałe lokalizacje_.
    - **Zezwalaj na ujemne zapasy:** Wyczyść to pole wyboru.
    - **Partia włączona:** Wyczyść to pole wyboru.
    - **Strategia:** Wybierz opcję _Brak_.

1. Wybierz **Zapisz**, aby zapisać nowe działanie.
1. Podczas gdy nowa akcja jest wciąż zaznaczona, wybierz polecenie **Edytuj zapytanie** powyżej siatki **Działania dyrektywy lokalizacji**.
1. Zostanie wyświetlone okno dialogowe zapytania, w którym można wybrać lokalizacje, z których będą wykonywane uzupełnienia zapasów. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** _Lokalizacje_
    - **Tabela pochodna:** _Lokalizacje_
    - **Pole:** _Identyfikator strefy_
    - **Kryteria:** _BULK_

1. Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.
1. Wybierz **Zapisz**, by zapisać dyrektywę lokalizacji.

##### <a name="create-a-replenishment-put-directive"></a>Tworzenie dyrektywy odkładania uzupełniania zapasów

1. Na stronie **Dyrektywy lokalizacji** w lewym okienku upewnij się, że pole **Typ zlecenia pracy** jest nadal ustawiony na _uzupełnienie_.
1. W okienku akcji wybierz opcję **Nowa**, aby utworzyć kolejną dyrektywę.
1. Ustaw następujące wartości:

    - **Numer sekwencyjny:** Zaakceptuj wartość domyślną.
    - **Nazwa:** Wprowadź _oddanie w strefie_.
    - **Typ zlecenia pracy:** Wybierz opcję _Odłóż_.
    - **Placówka:** Wybierz _6_.
    - **Magazyn:** Wybierz _61_.
    - **Kod dyrektywy:** Wybierz _strefa uzupełnień_, aby połączyć tę dyrektywę lokalizacji z szablonem uzupełnienia, który został utworzony wcześniej, przy użyciu utworzonego wcześniej kodu.
    - **Wiele jednostek SKU:** ustaw tą wartość na _Nie_.

1. Wybierz opcję **Zapisz**, aby utworzyć dyrektywę, w której skonfigurowano dotychczasowe ustawienia.
1. Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** Wpisz _1_.
    - **Ilość od:** Podaj _0_.
    - **Ilość do:** Podaj _10000000_.
    - **Jednostka:** pozostaw to pole puste.
    - **Znajdź ilość:** Wybierz opcję _Brak_.
    - Zaznacz lub wyczyść pole wyboru **Ogranicz według jednostki:**.
    - **Zaokrąglaj w górę do jednostki:** Wyczyść to pole wyboru.
    - **Znajdź ilość opakowań:** Wyczyść to pole wyboru.
    - Zaznacz pole wyboru **Zezwalaj na podział:**.

1. Wybierz **Zapisz**, aby zapisać nowy wiersz.
1. Gdy nowy wiersz jest wciąż zaznaczony w siatce **Wiersze**, wybierz opcję **Nowy** w skróconej karcie **Działania dyrektywy lokalizacji**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** Wpisz _1_.
    - **Nazwa:** Wprowadź _oddanie w strefie_.
    - **Stałe użycie lokalizacji:** Wybierz _Stałe i niestałe lokalizacje_.
    - **Zezwalaj na ujemne zapasy:** Wyczyść to pole wyboru.
    - **Partia włączona:** Wyczyść to pole wyboru.
    - **Strategia:** Wybierz _Konsolidacja_.

1. Wybierz **Zapisz**, aby zapisać nowe działanie.
1. Podczas gdy nowa akcja jest wciąż zaznaczona, wybierz polecenie **Edytuj zapytanie** powyżej siatki **Działania dyrektywy lokalizacji**.
1. Zostanie wyświetlone okno dialogowe zapytania, w którym można wybrać lokalizację do uzupełnienia. To powinna być ta sama strefa, która jest określona w szablonie uzupełnienia. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** _Lokalizacje_
    - **Tabela pochodna:** _Lokalizacje_
    - **Pole:** _Identyfikator strefy_
    - **Kryteria:** _FLOOR_

1. Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.
1. Wybierz **Zapisz**, by zapisać dyrektywę lokalizacji.

## <a name="scenario"></a>Scenariusz

Ta sekcja zawiera przykładowy scenariusz przedstawiający sposób pracy z tą funkcją.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Przygotuj przykładowe dane wymagane dla scenariusza z przykładu

Przed rozpoczęciem pracy nad scenariuszem należy aktywować przykładowe dane i skonfigurować funkcję zgodnie z opisem w tej sekcji i w poprzednich sekcjach tego tematu.

#### <a name="use-the-usmf-legal-entity"></a>Użyj firmy USMF

Aby pracować z tymi scenariuszami przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

#### <a name="prepare-additional-sample-data"></a>Przygotowywanie dodatkowych przykładowych danych

Po wybraniu firmy **USMF** dodaj dodatkowe przykładowe dane, które są wymagane, zgodnie z opisem w sekcji [konfiguracji uzupełnienia w strefie](#setup), opisanej wcześniej w tym temacie.

#### <a name="check-your-on-hand-inventory"></a>Sprawdzanie dostępnych zapasów

Należy wykonać poniższe kroki, aby upewnić się, że w systemie znajduje się wystarczająca ilość zapasów do obsługi scenariusza przykładowego.

1. Upewnij się, że istnieją dostępne zapasy dla pozycji *A0001* w dwóch różnych lokalizacjach w strefie pobrania (*FLOOR*), które są określone w szablonie uzupełnienia zapasów. Jednak suma zapasów powinna być mniejsza niż wymagana ilość minimalna (*50*), która jest określona w szablonie uzupełnienia. W ten sposób można symulować sposób obliczania w całej strefie, a nie tylko dla jednej lokalizacji. **Korzystaj z dowolnego procesu magazynowego, aby skorygować zapasy**.
1. Upewnij się, że istnieje wystarczająca ilość zapasów dla pozycji *A0001* w lokalizacji zbiorczej określonej w dyrektywie pobrania strefy, w której praca uzupełniająca powinna pobierać towary ze strefy o identyfikatorze *BULK*. Suma zapasów powinna być większa niż wymagana ilość maksymalna (*150*), która jest określona w szablonie uzupełnienia.
1. Opcjonalne, ale zalecane: Aby utworzyć arkusz korekt zapasów, należy wykonać następujące kroki:

    1. Kliknij kolejno opcje **Zarządzanie zapasami \> Wpisy w arkuszu \> Towary \> Korekta zapasów**.
    1. Wybierz pozycję **Nowy**.
    1. W oknie dialogowym **Tworzenie arkusza magazynowego** w polu **Magazyn** wybierz pozycję *61*.
    1. Kliknij przycisk **OK**.
    1. Na skróconej karcie **Wiersze arkusza** użyj przycisku **Nowe**, aby dodać trzy wiersze do siatki, należy określić następujące wartości. Po zakończeniu konfigurowania każdego wiersza wybierz opcję **Zapisz**.

        - **Wiersz 1:**

            - **Numer pozycji:** *A0001*
            - **Oddział:** *6*
            - **Magazyn:** *61*
            - **Lokalizacja:** *02A01R1S1B*
            - **Numer identyfikacyjny:** Wybierz istniejący numer identyfikacyjny na liście lub Utwórz nowy numer identyfikacyjny.
            - **Ilość:** *1000*

        - **Wiersz 2:**

            - **Numer pozycji:** *A0001*
            - **Oddział:** *6*
            - **Magazyn:** *61*
            - **Lokalizacja:** *07A01R2S1B*
            - **Numer identyfikacyjny:** Wybierz istniejący numer identyfikacyjny na liście lub Utwórz nowy numer identyfikacyjny.
            - **Ilość:** *15*

        - **Wiersz 3:**

            - **Numer pozycji:** *A0001*
            - **Oddział:** *6*
            - **Magazyn:** *61*
            - **Lokalizacja:** *07A01R1S1B*
            - **Numer identyfikacyjny:** Wybierz istniejący numer identyfikacyjny na liście lub Utwórz nowy numer identyfikacyjny.
            - **Ilość:** *10*

    1. W okienku akcji wybierz pozycję **Weryfikacja**. Rozwiąż wszelkie znalezione błędy przed przejściem do następnego kroku.
    1. W okienku akcji wybierz opcję **Księguj**, aby zaksięgować zapasy w magazynie.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Przykładowy scenariusz: Uruchom min./maks. uzupełnienie na podstawie strefy

Po ustawieniu wszystkich przykładowych danych dotyczących wymagań wstępnych można uruchomić uzupełnianie, wykonując następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Uzupełnienie \> Uzupełnienia zapasów**.
1. W oknie dialogowym **Uzupełnianie** w skróconej karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**.
1. W oknie dialogowym **Informacje** na karcie **Zakres** dokonaj edycji domyślnego wiersza tabeli w następujący sposób:

    - **Tabela:** Wybierz _Szablony uzupełniania zapasów_.
    - **Tabela pochodna:** Wybierz _Szablony uzupełniania zapasów_.
    - **Pole:** Wybierz _Szablon uzupełniania zapasów_.
    - **Kryteria:** Wybierz _min./maks. wartość strefy uzupeł_. Ten szablon uzupełnienia zapasów jest szablonem utworzonym podczas przygotowywania danych demonstracyjnych tego scenariusza.

1. Wybierz **OK**, zapisać zapytanie i cofnąć się do oka dialogowego **Uzupełnianie zapasów**.
1. Wybierz **OK**, aby uruchomić szablon uzupełnienia zapasów.

Zlecenie uzupełniania zapasów jest teraz tworzone, aby pobierać zapasy ze strefy *BULK* i odnawiać je w strefie *FLOOR*.

## <a name="notes-and-tips"></a>Notatki i porady

Oto kilka uwag i porad dotyczących pracy z tą funkcją:

- Aby skonfigurować pracę uzupełniania zapasów, która przechodzi do żądanej strefy, można połączyć wiersze szablonu uzupełnienia i dyrektywy lokalizacji, korzystając z jednej z następujących metod:

    - Edytowanie kwerendy nagłówka dyrektywy lokalizacji i filtrowanie wybranych wierszy szablonu uzupełnienia zapasów.
    - Użycia kodu dyrektywy w wierszu szablonu uzupełniania zapasów oraz sparowania go z dyrektywą lokalizacji odłożenia.

- Jeśli są używane lokalizacje dynamiczne, praca uzupełniająca zostanie utworzona dla pierwszej dostępnej lokalizacji lub dla lokalizacji, która już zawiera zapasy, jeśli dla akcji dyrektywy lokalizacji skonfigurowano stosowanie strategii **Konsolidacja**.
- Jeśli są używane stałe lokalizacje, a nie strefy, należy użyć [standardowego minimalnego/maksymalnego uzupełnienia zapasów](tasks/set-up-min-max-replenishment-process.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]