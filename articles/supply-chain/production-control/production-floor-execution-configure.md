---
title: Konfigurowanie interfejsu wykonania hal produkcyjnych
description: W tym artykule opisano sposób tworzenia jednej lub większej liczby konfiguracji dla interfejsu wykonywania pomieszczenia produkcyjnego. Po otwarciu interfejsu wykonania produkcji system automatycznie ładuje wybraną konfigurację i filtr zadania, które są właściwe dla przeglądarki i urządzenia. W konfiguracji ustawiane są zasady, które muszą być dostępne dla określonego użycia.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2a77924e6133158d538a3eb8365def92c9354b0e
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220371"
---
# <a name="configure-the-production-floor-execution-interface"></a>Konfigurowanie interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

Pracownicy hali produkcyjnej używają interfejsu wykonywania hali produkcyjnej do rejestrowania swojej codziennej pracy, na przykład kiedy rozpoczynają pracę, zgłaszają opinie o zadaniach, rejestrują czynności pośrednie i zgłaszają nieobecności. Te rejestracje stanowią podstawę śledzenia postępu i kosztu zleceń produkcyjnych oraz obliczania podstawy wypłat dla pracowników.

Po otwarciu interfejsu wykonania produkcji system automatycznie ładuje wybraną konfigurację i filtr zadania, które są właściwe dla przeglądarki i urządzenia. W konfiguracji ustawiane są zasady, które muszą być dostępne dla określonego użycia. Oto kilka przykładów użycia:

- W przypadku urządzenia w korytarzu w firmie pracownicy zarejestrują się w momencie wejścia do biura i logują się przed wyjściem z pracy.
- Na urządzeniu w hali operatorzy maszyn rejestrują, kiedy rozpoczynają i kończą pracę. Rejestrują również przerwy i czynności pośrednie.

W tym artykule opisano różne opcje konfigurowania interfejsu wykonywania produkcji dla każdego urządzenia, które jest w użyciu w witrynie.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Włączanie interfejsu wykonywania hal produkcyjnych i powiązanych opcjonalnych funkcji

Sam interfejs wykonywania hal produkcyjnych, a kilka opcjonalnych ustawień opisanych w tym artykule, musi być włączony w systemie, aby można było z nich skorzystać. Strona [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) umożliwia włączenie dowolnej funkcji lub wszystkich funkcji opisanych w poniższych podsekcjach, zgodnie z wymaganiami.

### <a name="the-production-floor-execution-interface"></a>Interfejs wykonania hal produkcyjnych

Jest to podstawowa funkcja opisana w tym artykule i jest niezbędna dla wszystkich innych funkcji wymienionych w tej sekcji. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Wykonanie hali produkcyjnej* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="generate-license-plates"></a>Generuj numery identyfikacyjne

Te funkcje sprawiają, że funkcjonalność numeru identyfikacyjnego jest dostępna dla interfejsu uruchomienia hali produkcyjnej. Jeżeli chcesz z nich skorzystać, włącz następujące funkcje w module [zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności):

1. *Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań*<br>(Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).
1. *Włącz automatyczną generację numeru identyfikacyjnego podczas zgłaszania wyrobów gotowych w urządzeniu karty zadań*<br>(Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).

### <a name="print-labels"></a>Drukuj etykiety

Te funkcje sprawiają, że funkcjonalność drukowania etykiet jest dostępna dla interfejsu uruchomienia hali produkcyjnej. Jeżeli chcesz z nich skorzystać, włącz następujące funkcje w module [zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności):

1. *Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań*<br>(Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).
1. *Drukowanie etykiety z menu Urządzenie karty zadań*<br>(Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).

### <a name="allow-locking-the-touch-screen"></a>Zezwalaj na blokowanie ekranu dotykowego

Ta funkcja umożliwia pracownikom blokowanie ekranu dotykowego, dzięki czemu możliwe jest jego obsługa.

Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli korzystasz z wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując *Funkcja blokowania urządzenia kart zadań i terminala kart zadań, aby można było je oczyścić* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funkcje zarządzania zasobami dla interfejsu wykonania hali produkcyjnej

Ta funkcja dodaje kartę Zarządzanie składnikami majątku do interfejsu wykonywania produkcji. Pracownicy mogą użyć tej karty, aby wybrać składnik majątku połączony z zasobem maszynowym, który jest w obrębie wybranego filtru listy zadań. Dla wybranego składnika majątku dla urządzenia pracownik może wyświetlić stan i kondycję składnika majątku z wartości liczników dla maksymalnie czterech wybranych liczników. Jeżeli chcesz skorzystać z tej funkcji, włącz następujące funkcje w [Zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Funkcje zarządzania zasobami dla interfejsu wykonania hali produkcyjnej*<br>(Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona).

### <a name="enable-job-search"></a>Włącz wyszukiwanie zadań

Ta funkcja umożliwia dodanie pola wyszukiwania do listy zadań. Pracownicy mogą znaleźć konkretną pracę, wpisując jej ID lub znaleźć wszystkie prace dla konkretnego zlecenia, wpisując ID zlecenia. Pracownicy mogą wprowadzać identyfikator za pomocą klawiatury lub skanując kod kreskowy. Jeżeli chcesz z niej skorzystać, włącz następujące funkcje w [Zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Wyszukiwanie zadań dla interfejsu wykonania hal produkcyjnych*<br>(Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona).

### <a name="enable-reporting-on-co-products-and-by-products"></a>Włącz raportowanie dotyczące produktów towarzyszących i produktów ubocznych

Ta funkcja umożliwia pracownikom raportowanie postępu w realizacji zamówień partii za pomocą interfejsu wykonywania hali produkcyjnej. Raportowanie to obejmuje raportowanie produktów towarzyszących i ubocznych. Aby używać tej funkcji, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Raport dotyczący produktów towarzyszących i ubocznych z interfejsu wykonania hal produkcyjnych*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>Włącz wyświetlanie pełnego numeru seryjnego, partii i numeru identyfikacyjnego

Ta funkcja zapewnia lepsze środowisko wyświetlania list numerów seryjnych, partii i numerów identyfikacyjnych w interfejsie wykonywania dla hali produkcyjnej. Wyświetlanie zmienia się z widoku karty z ograniczoną liczbą znaków do widoku listy, który zapewnia wystarczająco dużo miejsca, aby wyświetlić pełne wartości. Lista umożliwia również wyszukiwanie określonych liczb.

Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując *Pokaż pełne numery seryjne, partii i tablic rejestracyjnych w interfejsie wykonawczym hali produkcyjnej* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="enable-registering-of-material-consumption"></a>Włącz rejestrację zużycia materiałów

Ta funkcja umożliwia pracownikom używanie interfejsu wykonywania produkcji do rejestrowania zużycia materiałów, numerów partii i numerów seryjnych. Niektórzy producenci, szczególnie ci w przemyśle przetwórczym, muszą wyraźnie rejestrować ilość zużywanego materiału dla każdej partii lub zlecenia produkcyjnego. Na przykład pracownicy mogą używać wagi do zważenia ilości zużytego materiału podczas pracy. Aby zapewnić pełną identyfikowalność materiałów, organizacje te muszą również rejestrować numery partii, które zostały zużyte do wytworzenia każdego produktu.

Istnieją dwie wersje tej funkcji. Ta funkcja obsługuje tylko pozycje, dla których *nie* włączono obsługi procesów magazynowych (WMS). Inne obsługują pozycje, dla których *włączono* używanie usług WMS. Aby skorzystać z tej funkcji, włącz jedną lub obie z następujących funkcji w [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności), w zależności od tego, czy masz elementy, które są włączone dla WMS:

- *Rejestrowanie zużycia materiału w interfejsie wykonania hal produkcyjnych (inne niż WMS)*
- *Rejestrowanie zużycia materiału w interfejsie wykonania hal produkcyjnych (z obsługą WMS)*

> [!IMPORTANT]
> Można korzystać z funkcji innych niż WMS. Jednak w przypadku korzystania z programu WMS należy włączyć obie funkcje.

### <a name="enable-reporting-on-catch-weight-items"></a>Włącz raportowanie pozycji wagi połowu

Pracownicy mogą korzystać z interfejsu wykonywania hali produkcyjnej, aby zgłaszać postępy w zamówieniach partii dla pozycji wagi połowu. Zamówienia wsadowe są tworzone na podstawie formuł, które można zdefiniować w taki sposób, aby pozycje wagi połowu były pozycjami formuły, produktami towarzyszącymi i produktami ubocznymi. Formułę można także zdefiniować tak, aby zawierała wiersze formuły dotyczące składników, które zostały określone dla wagi catch. Pozycje w ilości catch używają dwóch jednostek miary do śledzenia zapasów: ilości catch i ilości magazynowej. Na przykład w branży spożywczej mięso pudełek można zdefiniować jako towar w ilości catch, gdzie ilość catch jest używana do śledzenia liczby pudełek, a ilość magazynowa jest używana do śledzenia wagi pudełek.

Aby używać tej funkcji, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Raport pozycji ilości efektywnej z interfejsu wykonania hal produkcyjnych*

### <a name="enable-the-my-day-dialog"></a>Włącz okno dialogowe „Mój dzień”

Okno dialogowe **Mój dzień** zapewnia pracownikom przegląd ich codziennych rejestracji i aktualnych sald płatnego czasu pracy, płatnych nadgodzin, nieobecności i płatnej nieobecności.

Aby używać tej funkcji, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Widok „Mój dzień” dla interfejsu wykonania hal produkcyjnych*

### <a name="enable-teams"></a>Włączanie zespołów

Kiedy kilku pracowników jest przydzielonych do tego samego zadania produkcyjnego, mogą oni tworzyć zespół. Drużyna może wyznaczyć jednego pracownika jako pilota. Pozostali pracownicy automatycznie stają się asystentami tego pilota. W powstałej w ten sposób drużynie tylko pilot musi zarejestrować status pracy. Ewidencja czasu pracy dotyczy wszystkich członków zespołu.

Aby używać tej funkcji, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Zespoły produkcyjne w interfejsie wykonania hal produkcyjnych*

### <a name="enable-additional-configuration-in-the-production-floor-execution-interface"></a>Włączenie dodatkowej konfiguracji w interfejsie wykonawczym hali produkcyjnej

Ta funkcja dodaje do strony **Konfiguracja wykonania hali produkcyjnej** ustawienia dla następujących funkcji:

- Automatycznie otwieraj okno dialogowe **Rozpocznij zadanie** po zakończeniu wyszukiwania.
- Automatycznie otwieraj okno dialogowe **Zgłoś postępy** po zakończeniu wyszukiwania.
- Wstępnie wypełnij pozostałą ilość w oknie dialogowym **Raport postępu**.
- Włącz korekty zużycia materiałów w oknie dialogowym **Raport o postępie**. (Ta funkcjonalność wymaga również funkcji *Rejestruj zużycie materiału na interfejsie wykonawczym hali produkcyjnej (nie-WMS)*).
- Włącz wyszukiwanie według ID projektu.

Informacje o tym, jak korzystać z tych ustawień, znajdują się w dalszej części tego artykułu.

Aby używać tej funkcji, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Dodatkowa konfiguracja w interfejsie wykonania hal produkcyjnych*


## <a name="work-with-production-floor-execution-configurations"></a>Praca z konfiguracjami wykonania hali produkcyjnej

Aby utworzyć i utrzymać konfiguracje wykonania hali produkcyjnej, przejdź do **Kontrola produkcji \> Konfiguracja \> Uruchomienie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**. Na stronie **Konfigurowanie interfejsu wykonania hal produkcyjnych** wyświetlana jest lista istniejących konfiguracji. Na tej stronie można wykonać następujące akcje:

- Wybierz dowolną konfigurację hali produkcyjnej znajdującą się w lewej kolumnie, aby ją wyświetlić i edytować.
- Wybierz **Nowy** w okienku akcji, aby dodać nową konfigurację do listy. Następnie w polu **Konfiguracja** wprowadź nazwę, aby zidentyfikować nową konfigurację. Wprowadzona tutaj nazwa musi być unikatowa wśród wszystkich konfiguracji i nie będzie można jej później edytować. Opcjonalnie: W polu **opis** opcjonalnie możesz wprowadzić opis konfiguracji.

Następnie skonfiguruj różne ustawienia dla wybranej konfiguracji, tak jak to opisano w kolejnych podrozdziałach.

### <a name="the-general-fasttab"></a>Skrócona karta Ogólne

Poniższe ustawienia są dostępne na skróconej karcie **Ogólne**.

- **Tylko wejścia i wyjścia** – dla tej opcji ustaw wartość *Tak*, aby utworzyć uproszczony interfejs, który zapewnia tylko funkcje rejestracji i wyrejestrowywania. To ustawienie wyłącza większość innych opcji dostępnych na tej stronie. Aby można było włączyć tę opcję, należy usunąć wszystkie wiersze ze skróconej karty **Wybór kart**.
- **Włącz wyszukiwanie** – ustaw tę opcję na wartość *Tak*, aby uwzględnić pole wyszukiwania na liście zadań. Pracownicy mogą znaleźć konkretną pracę, wpisując jej ID lub można znaleźć wszystkie prace dla konkretnego zlecenia, wpisując ID zlecenia. Pracownicy mogą wprowadzać identyfikator za pomocą klawiatury lub skanując kod kreskowy.
- **Włącz wyszukiwanie według ID projektu** – ustaw tę opcję na *Tak*, aby umożliwić pracownikom wyszukiwanie według ID projektu (oprócz ID zadania i ID zlecenia) w polu wyszukiwania interfejsu wykonawczego hali produkcyjnej. Możesz ustawić tę opcję na *Tak* tylko wtedy, gdy opcja **Włącz wyszukiwanie** jest również ustawiona na *Tak*.
- **Automatycznie otwieraj okno dialogowe startu** – kiedy ta opcja jest ustawiona na *Tak*, okno dialogowe **Rozpocznij pracę** jest automatycznie otwierane, kiedy pracownicy używają paska wyszukiwania, by znaleźć pracę.
- **Automatycznie otwieraj okno dialogowe Zgłoś postępy** – kiedy ta opcja jest ustawiona na *Tak*, okno dialogowe **Zgłaszanie postępu** jest automatycznie otwierane, kiedy pracownicy używają paska wyszukiwania, by znaleźć pracę.
- **Włącz dostosowanie materiału** – ustaw tę opcję na *Tak*, aby włączyć przycisk **Dostosuj materiał** w oknie dialogowym **Raport postępu**. Pracownicy mogą wybrać ten przycisk, aby dostosować zużycie materiału dla danego zadania.
- **Zgłoś ilość przy wyjściu** – wartość *Tak* powoduje, że pracownicy będą monitowani o raportowanie informacji zwrotnych dotyczących zadań w toku podczas wyrejestrowywania. Jeśli ustawiono wartość *Nie*, pracownik nie będzie monitowany.
- **Zablokuj pracownika** — Jeśli ta opcja ma wartość *Nie*, pracownicy są wylogowani natychmiast po dokonaniu rejestracji (np. nowego zadania). Interfejs powróci do strony logowania. Jeśli ta opcja jest ustawiona na wartość *Tak*, pracownicy pozostaną zalogowani do interfejsu wykonawczego hali produkcyjnej. Jednak pracownik może ręcznie wylogować się, aby inny pracownik mógł się zalogować, podczas gdy interfejs wykonywania na poziomie produkcyjnym nadal działa na tym samym koncie użytkownika systemu. Aby uzyskać więcej informacji o tych typach kont, zobacz, zobacz temat [Przypisani użytkownicy](config-job-card-device.md#assigned-users).
- **Użyj faktycznego czasu rejestracji** – Ustaw to na *Tak*, aby ustawić czas każdej nowej rejestracji na dokładny czas, w którym pracownik przesłał rejestrację. Jeśli ta opcja jest ustawiona na *Nie*, w zamian zostanie użyta godzina logowania. Zazwyczaj ustawienie to jest ustawione na *Tak*, jeśli włączono opcję **Zablokuj pracownika** i/lub opcję **Jeden pracownik** ustawioną na *Tak*, gdzie pracownik często pozostaje zalogowany przez dłuższy okres czasu.
- **Jeden pracownik** – Ustawienie tej opcji na wartość *Tak*, jeśli tylko jeden pracownik korzysta z każdego interfejsu wykonawczego na poziomie produkcyjnym, w którym ta konfiguracja jest aktywna. Po ustawieniu tej opcji na *Tak*, opcja **Blokowanie pracownika** jest automatycznie ustawiana na wartość *Tak*. Ponadto to ustawienie usuwa zapotrzebowanie (i zdolność) pracownika, który ma być zalogowany przy użyciu identyfikatora karty identyfikacyjnej (lub podobnego identyfikatora). Zamiast tego pracownik loguje się do Microsoft Dynamics 365 Supply Chain Management, używając konta użytkownika systemowego powiązanego z *pracownik zarejestrowany w czasie* (z tabeli *pracownicy*) i zostaje zalogowany do interfejsu wykonawczego hali produkcyjnej jako ten pracownik w tym samym czasie.
- **Zezwalaj na blokowanie ekranu dotykowego** – tę opcję należy wybrać *Tak*, aby umożliwić pracownikom zablokowanie ekranu dotykowego interfejsu wykonawczego hali produkcyjnej, aby mogli go oczyścić. Jeśli ta opcja jest ustawiona na *Tak*, do strony rejestracji zostanie dodany przycisk **Blokowanie ekranu ze względu na dezynfekcję**. Po wybraniu tego przycisku przez pracownika ekran dotykowy jest tymczasowo blokowany, aby zapobiec niezamierzonemu wprowadzaniu. Wyświetlany jest również czasomierz odliczania. Pracownik może następnie bezpiecznie oczyścić urządzenie i ekran. Po zakończeniu odliczania ekran dotykowy automatycznie odblokowuje ekran.
- **Czas trwania blokady ekranu** – gdy opcja **Zezwalaj na blokowanie ekranu dotykowego** jest ustawiona na *Tak*, ta opcja służy do określenia liczby sekund, kiedy ekran dotykowy powinien być zablokowany do oczyszczania. Czas trwania musi być liczbą od 5 do 120 sekund.
- **Generowanie numeru identyfikacyjnego** – ustawienie tej opcji na wartość *Tak*, aby generować nową tablicę rejestracyjną za każdym razem, gdy pracownik korzysta z interfejsu wykonawczego hali produkcyjnej, aby zgłosić gotowość. Numer identyfikacyjny jest generowany na podstawie sekwencji numerów ustawionej na stronie **Parametry zarządzania magazynem**. Po ustawieniu wartości opcji *Nie* pracownicy muszą określić istniejący numer identyfikacyjny podczas zgłaszania wyrobów gotowych.
- **Drukuj etykietę** – ustawienie tej opcji na wartość *Tak* powoduje Drukowanie etykiety numeru identyfikacyjnego, gdy pracownik używa interfejsu wykonawczego hali produkcyjnej do zgłaszania zakończenia. Konfiguracja etykiety jest ustawiana w obszarze marszruta dokumentów, zgodnie z opisem w [Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych](../warehousing/document-routing-layout-for-license-plates.md).

### <a name="the-tab-selection-fasttab"></a>Wybór karty na skróconej karcie

Użyj ustawień na skróconej karcie **Wybór karty**, aby wybrać, które karty powinien pokazywać interfejs wykonawczy hali produkcyjnej, gdy aktywna jest bieżąca konfiguracja. Możesz zaprojektować tyle zakładek, ile potrzebujesz, a następnie dodawać je i rozmieszczać według własnych potrzeb za pomocą przycisków na pasku narzędzi skróconej karty. Aby uzyskać informacje na temat projektowania kart i pracy z ustawieniami tutaj, zobacz [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md).

### <a name="the-report-progress-fasttab"></a>Skrócona karta Zgłaszanie postępu

Poniższe ustawienia są dostępne na skróconej karcie **Zgłaszanie postępu**.

- **Włącz dostosowanie materiału** – ustaw tę opcję na *Tak*, aby zawrzeć przycisk **Dostosuj materiał** w oknie dialogowym **Raport postępu**. Pracownicy mogą wybrać ten przycisk, aby dostosować zużycie materiału dla danego zadania.
- **Domyślna ilość pozostała** – ustaw tę opcję na *Tak*, aby w oknie dialogowym **Raport o postępie** wstępnie wypełnić oczekiwaną ilość pozostałą dla zadania produkcyjnego.

## <a name="clean-up-job-configurations"></a>Oczyszczanie konfiguracji zadań

Kiedy kierownik hali konfiguruje interfejs wykonawczy hali produkcyjnej, wybiera konfigurację i filtr zadań. Opcje te są przechowywane w tabeli odwołań w Supply Chain Management, a przeglądarka używa identyfikatora przechowywanego w lokalnym pliku cookie w celu znalezienia właściwego wiersza w tej tabeli. Tabela rejestruje również datę i godzinę ostatniego logowania pracownika na każdym urządzeniu.

Zadanie wsadowe okresowo oczyszcza wpisy w tabeli odwołań dla urządzeń, które nie zarejestrowały żadnych działań w ciągu ostatnich 60 dni. Wpisy można również czyścić ręcznie w dowolnym momencie, wykonując następujące kroki:

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**.
1. W okienku akcji wybierz opcję **Oczyść konfiguracje klientów**.
1. W oknie dialogowym **Oczyść konfigurację klientów** w polu **Liczba dni** ustaw liczbę dni nieaktywności (przed dniem dzisiejszym), które mają być brane pod uwagę. Wszystkie konfiguracje i rekordy logowania dla urządzeń, które nie były aktywne w tym czasie, zostaną usunięte.
1. Wybierz przycisk **OK**, aby oczyścić odpowiednie konfiguracje na podstawie **Liczby dni**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
