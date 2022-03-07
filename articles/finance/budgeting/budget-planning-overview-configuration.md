---
title: Omówienie planowania budżetu
description: W tym temacie opisano planowanie budżetu. Ten temat zawiera informacje na temat sposobu skonfigurowania planowania budżetu i procesów konfigurowania planowania budżetu.
author: panolte
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "17251"
- intro-internal
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 391f62f42e482f79420bbe1bbd4cec4930790229
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982072"
---
# <a name="budget-planning-overview"></a>Omówienie planowania budżetu

[!include [banner](../includes/banner.md)]

W tym temacie opisano planowanie budżetu. Ten temat zawiera informacje na temat sposobu skonfigurowania planowania budżetu i procesów konfigurowania planowania budżetu.

## <a name="overview-of-budget-planning"></a>Przegląd planowania budżetu

Organizacja może konfigurować planowanie budżetu, a następnie konfigurować procesy planowania budżetu, zgodnie z zasadami, procedurami i wymaganiami organizacji dotyczącymi przygotowania budżetu. Gdy rozumiesz pojęcia i terminologię używaną w usłudze Microsoft Dynamics 365 Finance, implementacja planowania budżetu w organizacji jest łatwiejsza i wydajniejsza.

### <a name="key-terms"></a>Kluczowe terminy

- **Procesy planowania budżetu** — procesy planowania budżetu decydują o sposobach aktualizowania, obiegu, przeglądania i zatwierdzania planów budżetu w hierarchii organizacyjnej Budżetowanie. Proces planowania budżetu jest połączony z cyklem budżetu i organizacją poprzez podmiot prawny.
- **Plany budżetu** — plany budżetu zawierają dane budżetu dla cyklu budżetu. Można używać wielu planów budżetu, które są używane do różnych celów. Planów budżetu można na przykład stosować do tworzenia kwot budżetu dla różnych jednostek organizacyjnych. Można je również stosować do porównań i podejmowania świadomych decyzji.
- **Scenariusze planu budżetu** — scenariusze planu budżetu definiują kategorie danych dla planów budżetu. Scenariusze planu budżetu definiuje się do obsługi klas walutowych i innych klas jednostki miary, takich jak ilość. Przykłady pieniężnych scenariuszy planu budżetu to m.in. P„oprzedni rok działu” i „Żądania działu”. Przykłady scenariuszy planu budżetu z ilościami to m.in. „Wywołania obsługi poprzedniego roku” i „Przeliczenia na pełne etaty (FTE)”.
- **Etapy planowania budżetu** — etapy planowania budżetu definiują kroki planu budżetu od początku do ostatecznego zatwierdzenia. Etapy planowania budżetu są organizowane w przepływy pracy dla planowania budżetu.
- **Przepływy pracy planowania budżetu** — przepływy pracy planowania budżetu obejmują i definiują etapy planowania budżetu. Przepływy pracy planowania budżetu są skojarzone z przepływami pracy budżetowania. Przepływy pracy Budżetowanie są zautomatyzowanymi i ręcznymi procesami, które przenoszą plany budżetu przez etapy planowania budżetu.

[![Terminologia związana z planowaniem budżetu.](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="typical-tasks"></a>Typowe zadania

Planowania budżetu można używać do wykonywania następujących zadań:

- Tworzenie planów budżetu w celu zdefiniowania oczekiwanego przychodu i rozchodów dla cyklu budżetu.
- Analizowanie i aktualizowanie planów budżetu dla wielu scenariuszy.
- Automatyczne wysyłanie planów budżetu, wraz z arkuszami, uzasadnieniami i innymi załącznikami, do przejrzenia i zatwierdzenia.
- Konsolidowanie wielu planów budżetu z niższego poziomu organizacji do jednego nadrzędnego planu budżetu na wyższym poziomie. Można również opracować pojedynczy plan budżetu na wyższym poziomie organizacji i zaalokować budżet do niższych poziomów.

Planowanie budżetu jest zintegrowane z innymi modułami. Pozwala to załączyć informacje z poprzednich budżetów, rzeczywistych wydatków, środków trwałych i zasobów ludzkich. Ponieważ planowanie budżetu jest także zintegrowane z programami Microsoft Excel i Microsoft Word, można użyć tych programów do pracy z danymi planowania budżetu. Na przykład, menedżer budżetu może wyeksportować wniosek budżetowy działu ze scenariusza planu budżetu do arkusza programu Excel. Dane można wtedy analizować, aktualizować i obrazować na wykresie w arkuszu, a następnie publikować z powrotem do wierszy planu budżetu.

## <a name="configuring-budget-planning"></a>Konfigurowanie planowania budżetu

Funkcja wprowadzona w Dynamics 365 Finance wersji 10.0.9 (kwiecień 2020) zawiera funkcję ułatwiającą poprawienie wydajności po użyciu przycisku **Publikuj** w celu zaktualizowania istniejących rekordów w programie Excel, a następnie opublikowania ich z powrotem na kliencie. Ta funkcja przyspiesza proces aktualizacji, a także zmniejsza prawdopodobieństwo, że aktualizacja zostanie zablokowana w przypadku jednoczesnej aktualizacji wielu rekordów. Aby zapewnić dostęp do tej funkcji, przejdź do obszaru roboczego **zarządzanie funkcją** i Włącz **optymalizację kwerendy planowania budżetu dla funkcji wydajności** w obszarze **budżetowanie**. Zaleca się włączenie tej funkcji.

Strona **Konfiguracja planowania budżetu** zawiera większość ustawień, które są wymagane do tworzenia planowania budżetu. W poniższych sekcjach opisano niektóre czynniki, o których trzeba pamiętać podczas konfigurowania planowania budżetu. Po zakończeniu konfiguracji można ustawić procesy planowania budżetu.

### <a name="budget-planning-schema-optional"></a>Schemat planowania budżetu (opcjonalnie)

Opcjonalnym, ale zalecanym pierwszym krokiem jest utworzenie schematu zawierającego procedury opracowywania budżetu organizacji. Metoda tworzenia takiego schematu jest dowolna.

Na poniższej ilustracji pokazano ogólny przykład, w którym dla różnych poziomów organizacji tworzone są oddzielne przepływy pracy. Dla każdego przepływu pracy definiowane są etapy, a do każdego etapu przypisywane są określone scenariusze z danymi budżetowymi. Wykonywane są zadania przenoszenia danych z jednego etapu do następnego. Na przykład kwoty mogą być przydzielane lub agregowane na różnych kontach, zatwierdzeniach lub innych dokumentach kontrolnych. W tej ilustracji kursywa oznacza scenariusz niedostępny do edycji na danym etapie lub dane archiwalne albo zatwierdzone na wcześniejszym etapie, które z tego powodu nie powinny być zmieniane.

[![Ogólny schemat planowania budżetu.](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

Na poniższej ilustracji widać przykład, gdzie centrala firmy szacuje kwoty podstawowe dla wstępnego budżetu i dystrybuuje jest do departamentów sprzedaży. Następnie działy sprzedaży prognozują i przesyłają prognozy z powrotem do centrali, gdzie menedżer budżetu agreguje je i dostosowuje. Na koniec menedżer budżetu wysyła skorygowane kwoty budżetu do dyrektora finansowego (CFO) w celu sprawdzenia, wprowadzenia ostatnich korekt i ostatecznego zatwierdzenia.

[![Przykład schematu planowania budżetu.](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

### <a name="organization-hierarchy-for-budget-planning"></a>Hierarchia organizacyjna dla planowania budżetu

Na stronie **Hierarchia organizacyjna** można określić hierarchię organizacyjną jako hierarchię planowania budżetu dla każdego procesu planowania budżetu. Hierarchia planowania budżetu nie musi pasować do standardowej hierarchii organizacyjnej, która jest używana do innych celów. Ponieważ ta hierarchia służy do agregowania i dystrybucji danych, można zaprojektować dla niej inną strukturę. W przykładowym schemacie działy sprzedaży są poniżej poziomu centrali obejmującego działy budżetu i finansowy. Ta struktura prawdopodobnie różni się od struktury służącej do zarządzania operacjami działów sprzedaży. Do każdego procesu planowania budżetu można przypisać tylko hierarchię organizacyjną.

Więcej informacji można znaleźć w temacie [Organizacje i hierarchie organizacyjne](../../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Zabezpieczenia użytkownika

Planowanie budżetu być realizowane według jednego z modeli zabezpieczeń definiujących uprawnienia użytkownika. Aby określić model zabezpieczeń, należy ustawić parametr planowania budżetu na stronie **Konfiguracji planowania budżetu**.

### <a name="budget-planning-workflows-stages"></a>Etapy przepływu pracy planowania budżetu

Przepływy pracy planowania budżetu są używane razem z przepływami pracy Budżetowanie do zarządzania, tworzenia i oceny planów budżetu.

Przepływ pracy planowania budżetu składa się z uporządkowanego zestawu etapów, przez które przechodzi planu budżetu. Każdy przepływ pracy planowania budżetu jest skojarzony z przepływem pracy budżetowanie. Przepływy pracy Budżetowanie to jeden z typów przepływów pracy, które są używane w całym systemie Dynamics 365 Finance. Kieruje plany budżetu, wraz z arkuszami, uzasadnieniami i załącznikami do odpowiednich komórek w organizacji w celu przejrzenia i zatwierdzenia.

Tworzenie przepływu pracy planowania budżetu odbywa się w sekcji **Etapy przepływu pracy** na stronie **Konfiguracja planowania budżetu**. Na tej stronie można wybrać etapy i przepływ pracy budżetowanie, które będą używane, a także skonfigurować dodatkowe ustawienia.

Dobrym rozwiązaniem jest utworzenie przepływu pracy planowania budżetu dla każdego poziomu hierarchii budżetowania. Następnie przypisuje się przepływ pracy budżetowanie, który zawiera elementy odpowiadające poszczególnym etapom w przepływie pracy planowania budżetu. W przykładowym schemacie pokazanym wcześniej w tym temacie jeden przepływ pracy planowania budżetu jest tworzony dla działów sprzedaży, a inny dla centrali. Przepływ pracy budżetowanie przesuwa plany budżetu przez kolejne etapy.

Przepływ pracy budżetowanie dla planowania budżetu tworzy się na stronie **Przepływy pracy Budżetowanie**. Ten proces przypomina proce tworzenia innych przepływów pracy. Na poniższe ilustracji pokazano przykład przepływu pracy dla centrali.

[![Przepływ pracy Budżetowanie dla planowania budżetu.](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

Typy przepływu pracy zawierają następujące elementy:

- Alokacja do działów handlowych i zestawienie ich przesłań
- Przegląd menedżera budżetu
- Zatwierdzenie CFO
- Wdrażane przemieszczania między poszczególnymi etapami przepływu pracy planowania budżetu

Przypisywanie przepływu pracy do poszczególnych przepływów pracy planowania budżetu odbywa się w sekcji **Etapy przepływu pracy** na stronie **Konfiguracja planowania budżetu**.

### <a name="parameters-scenarios-and-stages"></a>Parametry, scenariusze i etapy

Początkowe ustawienia na stronie **Konfiguracja planowania budżetu** pozwalają tworzyć bloki konstrukcyjne do późniejszych etapów konfiguracji:

- **Parametry** — definiują reguły zabezpieczeń, które mają być stosowane do planów budżetu i domyślne wymiary do używania przy wyświetlaniu kwot scenariuszy planu budżetu.
- **Scenariusze** — obejmują kategorie danych, które mają być stosowane dla planów budżetu. Scenariusze planu budżetu definiuje się do obsługi klas walutowych i innych klas jednostki miary, takich jak ilość. W planie budżetu scenariusze dotyczą jednej wersji danych planowania budżetu. Przykłady pieniężnych scenariuszy planu budżetu to m.in. „Sprzedaż w ubiegłym roku” i „Podpisane umowy”. Przykłady scenariuszy, w których używane są ilości to m.in. „Liczba wywołań sprzedaży” i „Przeliczenia na pełne etaty (FTE)”.
- **Etapy** — definiują czynności planu budżetu od jego początku do ostatecznego zatwierdzenia. Przykłady etapów planowania budżetu to m.in. „Akumulacja centrali”, „Kontrola CFO” i „Ostateczne”.

### <a name="allocation-schedules"></a>Harmonogramy alokacji

Podczas planowania budżetu można alokować kwoty lub ilości w wierszach planu budżetu z jednego scenariusza do innego scenariusza lub nawet do tego samego scenariusza. Na przykład można alokować kwoty lub ilości do tego samego scenariusza, jeśli trzeba zastosować zmiany do wymiarów finansowych lub dat, w tym scenariuszu kwot. Alokacja może odbywać się w ramach planu budżetu lub między dwoma planami budżetu.

Harmonogramy alokacji automatycznie alokują wiersze planu budżetu podczas przetwarzania przepływu pracy. Alokacje można wykonywać za pomocą dowolnej z metod dostępnych na liście **Metody alokacji**:

- **Alokuj między okresami** — klucz alokacji okresu jest używany do alokacji wierszy planu budżetu ze źródłowego scenariusza planu budżetu między okresami w scenariuszu docelowym.

    > [!NOTE]
    > Uwaga: Aby możliwa była alokacja między okresami, trzeba ustawić klucze alokacji okresów na stronie **Kategorie alokacji okresu**.

- **Alokuj do wymiarów** — przydzielanie wierszy planu budżetu następuje ze źródłowego scenariusza planu budżetu do wymiarów finansowych w scenariuszu docelowym.

    > [!NOTE]
    > Uwaga: Aby alokacja do wymiarów była możliwa, trzeba ustawić warunki alokacji budżetu na stronie **Warunki alokacji budżetu**.

- **Agreguj** — agregowanie wierszy planu budżetu następuje ze źródłowego scenariusza planu budżetu w powiązanych planach budżetu do docelowego scenariusza w nadrzędnym planie budżetu.
- **Dystrybuuj** — rozdzielanie wierszy planu budżetu następuje ze źródłowego scenariusza planu budżetu w nadrzędnym planie budżetu do docelowego scenariusza w skojarzonych planach budżetu.
- **Użyj reguł alokacji księgi** — rozdzielanie wierszy planu budżetu następuje ze źródłowego scenariusza planu budżetu do docelowego scenariusza planu budżetu na podstawie wybranej reguły alokacji księgi.
- **Kopiuj z planu budżetu** — można wybrać inny plan budżetu do użycia jako źródło alokacji.

### <a name="stage-allocations"></a>Alokacje etapu

Alokacje etapu umożliwiają automatyczną alokację wierszy planu budżetu podczas przetwarzania przepływu pracy. Gdy używane są alokacje etapów, wiersze planu budżetu w scenariuszu docelowym można tworzyć i modyfikować bez interwencji osoby, która przygotowała plan budżetu, lub osoby sprawdzającej.

Podczas konfigurowania alokacji etapu należy skojarzyć przepływ pracy planowania budżetu i etap z harmonogramem alokacji. Przepływ pracy planowania budżetu należy skojarzyć z przepływem pracy budżetowania korzystającym z zadania automatycznie wykonywanego przepływu pracy **Alokacja etapu planowania budżetu**. Gdy przepływ pracy osiągnie określony etap, alokacja jest wykonywana automatycznie. To wykonywane automatycznie zadanie może służyć do tworzenia wierszy planu budżetu w nowym scenariuszu.

W przykładowym schemacie, pokazanym wcześniej w tym temacie, alokacja służy do przenoszenia kwot z planu i scenariuszy budżetu na etapie „Podstawowy” w centrali do innego planu i scenariuszy budżetu na etapie „Szacowanie” w dziale sprzedaży. Poniższa ilustracja pokazuje odpowiednią sekcję przykładowego schematu.

[![Alokacja etapu.](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Ponadto w przykładowym schemacie agregacja jest wykonywana z planów i scenariuszy budżetu na etapie „Przesłano” w Dziale sprzedaży do nadrzędnego planu na etapie „Akumulacja” w Centrali. Poniższa ilustracja pokazuje odpowiednią sekcję przykładowego schematu.

[![Agregacja.](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Priorytety

Można opcjonalnie użyć priorytetów planu budżetu do definiowania kategorii o celów dla planów budżetu, które zostały skonfigurowane. Priorytety mogą być stosowane do organizowania, klasyfikowania i oceniania kilku planów budżetu. Na przykład można utworzyć budżet priorytet planowania dla zdrowia i bezpieczeństwa i następnie ocenić plany budżetu, które są przypisane do tego priorytetu. Można również przypisać numer do planów budżetu, aby wskazać ranking.

### <a name="columns-and-layouts"></a>Kolumny i układy

W planie budżetu wartości budżetu są wyświetlane w wierszach i kolumnach. Należy najpierw zdefiniować kolumny, a następnie należy utworzyć układ, aby zdefiniować sposób wyświetlania tych kolumn.

Aby zdefiniować kolumnę, należy wybrać scenariusz planu budżetu. Kwoty wiersza z tego scenariusza są również wyświetlane w planie budżetu. Można wybrać okres do filtrowania kwota i można także zastosować filtry oparte na koncie księgowym.

Podczas definiowania układu należy wybrać zestaw wymiarów księgi, aby utworzyć wiersze planu budżetu, które mają być pokazane, a następnie zaznaczyć kolumny jako elementy układu. Można utworzyć wiele układów, aby plan budżetu pokazywał żądane dane, które mają być dostępne na różnych etapach procesu planowania budżetu.

Oprócz kolumn dla kwot budżetu można zdefiniować kolumny dla pól projektu, proponowanego projektu, środków trwałych i proponowany środków trwałych z planu budżetu. Można także zdefiniować kolumnę dla pozycji budżetu. Ta opcja jest przydatna, gdy trzeba analizować budżety pracowników.

W przypadku przykładowego schematu można utworzyć kolumny scenariuszy „sprzedaż”, „kontrakty” i „Prognoza”. (Na poniższej ilustracji pokazano odpowiednią sekcję schematu.) Można następnie podzielić jeden lub wszystkie z tych scenariuszy na osobne kolumny dla każdego kwartału roku obrachunkowego, tak aby menedżer ds. sprzedaży w dziale mógł dokładnie wprowadzać kwoty prognozy dla każdego okresu.

[![Ilustracja sekcji schematu dodawania kolumn.](./media/columns.png)](./media/columns.png)

Można również określić, czy poszczególne elementy układu (kolumna) są dostępne do edycji i czy są one dostępne w jakimkolwiek szablonie arkusza utworzonego w tym układzie. W przykładowym schemacie w układzie używanym dla etapu „Szacowanie”, kolumny „Prognoza” są dostępne do edycji, a kolumny „Sprzedaż w poprzednim roku” i „Umowy” są tylko do odczytu.

> [!NOTE]
> Domyślnie będzie ograniczona do 36 kolumn, chyba że rozszerzysz planowanie budżetu zgodnie z krokami w [rozszerzanie układu planowania budżetu](./extending-budget-planning-layout.md).

### <a name="templates"></a>Szablony

W sekcji **Układy** strony **Konfiguracja planowania budżetu** można też generować, wyświetlać lub przesyłać szablony programu Excel dla każdego szablonu. Te szablony to skoroszyty, które są połączone z każdym planem budżetu, oferując dodatkowe analizy, wykresy i opcje wprowadzania danych.

Podczas generowania szablonu układ jest zablokowany i nie można go edytować. Ta blokada pomaga zapewnić, że format szablonu będzie zgodny z układem planu budżetu i zawierał te same dane. Po wygenerowaniu szablonu można go wyświetlić i edytować. Można na przykład dodać do szablonu wykresy lub dostosować jego wygląd.

> [!NOTE]
> Szablon należy zapisać w miejscu, do którego użytkownik ma dostęp, aby dało się go przesłać do układu po zakończeniu edycji. W ten sposób szablon będzie używany z planami budżetu, które używają układu.

### <a name="descriptions"></a>Opisy

W sekcji **Układy** możesz przypisać opisy, które służą do wyświetlania nazw wymiarów finansowych dostępnych w układzie. Na przykład organizacja może chcieć wyświetlić nazwę konta głównego obok numeru konta głównego w planie budżetu. Jednak może zaistnieć potrzeba pominięcia nazw innych wymiarów finansowych, aby uniknąć zazaśmiecania wyświetlania.

## <a name="setting-up-budget-planning-processes"></a>Konfigurowanie procesów planowania budżetu

Po zakończeniu konfigurowania planowania budżetu można skonfigurować procesy planowania budżetu na stronie **Proces planowania budżetu**. Procesy planowania budżetu to zestawy reguł, które decydują o sposobach aktualizowania, obiegu, przeglądania i zatwierdzania planów budżetu w hierarchii organizacyjnej Budżetowanie.

Dla każdego procesu planowania budżetu należy najpierw wybrać cykl budżetu i księgę. Każdy proces planowania budżetu jest związane tylko z jednym cyklem budżetu i jedną księgą. Można wtedy wybrać hierarchię organizacyjną budżetu na skróconej karcie **Administrowanie procesem planowania budżetu** i przypisać przepływ pracy planowania budżetu do wszystkich centrów kompetencyjnych w organizacji dostępnych w siatce.

Aby przypisać lub zmienić przepływ pracy planowania budżetu dla podobnych centrów kompetencyjnych, wybierz przycisk **Przypisz przepływ pracy**, a następnie wybierz typ organizacji jako cel i przepływ pracy planowania budżetu. Identyfikator przepływu pracy budżetowania skojarzony z każdym przepływem pracy planowania budżetu jest automatycznie dodawany do siatki.

Po zdefiniowaniu reguł etapów i szablonów na skróconej karcie **Reguły i układy etapu planowania budżetu**, można określić inny zestaw reguł i domyślnych układów dla każdego etapu planowania budżetu. Na przykład etap „szacowania” w dziale sprzedaży może zezwalać użytkownikom na modyfikowanie wierszy w planie budżetu, ale uniemożliwiać im dodawanie wierszy. Etap „Przesłano” może zezwolić użytkownikom na wyświetlanie wierszy, ale nie na dodawanie ani modyfikowanie, ponieważ praca na tym etapie została zakończona i zmiany planów budżetu muszą być zablokowane. Aby wybrać układy, które są dostępne dla planów budżetu, wybierz **Alternatywne układy**.

Opcjonalnie można wybrać priorytety planowania budżetu na skróconej karcie **Ograniczenia priorytetu planu budżetu**. Priorytety można następnie wybrać w planach budżetu.

Ostatnim krokiem jest aktywowanie procesu planowania budżetu za pomocą menu **akcje**. Nie można użyć procesu planowania budżetu, dopóki nie zostanie on aktywowany.

Menu **Akcje** można też użyć do utworzenia nowego procesu przez skopiowanie istniejącego procesu. Ta funkcja jest przydatna dla organizacji, które realizują ten sam przepływ procesu w każdym cyklu budżetowym przy niewielkich zmianach lub braku zmian.

Innym przydatnym poleceniem w menu **Akcje** jest **Wyświetlenie stanu procesu budżetu**. To polecenie graficznie pokazuje plany budżetu w procesie wraz z odpowiednimi danymi, takimi jak stan przepływu pracy planów, podsumowania według kwot i jednostki oraz przechodzenie jednym kliknięciem do samych planów budżetu.

[![Stan procesu planowania budżetu.](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
