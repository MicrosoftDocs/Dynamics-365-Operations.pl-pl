---
title: Drogi i operacje
description: "Ten temat zawiera informacje o marszrut i operacji. Trasy definiuje proces wytwarzania produktów lub wariantów produktu. W procesie produkcji i kolejności, w jakiej te kroki należy wykonać w to opisano poszczególne kroki (operacji). Dla każdego kroku trasy definiuje również zasobów wymaganych operacji, czas przezbrojenia wymagane i w czasie wykonywania, i obliczania kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Drogi i operacje

Ten temat zawiera informacje o marszrut i operacji. Trasy definiuje proces wytwarzania produktów lub wariantów produktu. W procesie produkcji i kolejności, w jakiej te kroki należy wykonać w to opisano poszczególne kroki (operacji). Dla każdego kroku trasy definiuje również zasobów wymaganych operacji, czas przezbrojenia wymagane i w czasie wykonywania, i obliczania kosztów.

<a name="overview"></a>Przegląd
--------

Marszruta opisuje kolejność operacji, które jest wymagane w celu wyprodukowania produktów lub wariantów produktu. Dla każdej operacji trasy definiuje zasobów operacje, które są wymagane, czas, który jest wymagany do ustawiania i wykonywania operacji i obliczania kosztów. Można użyć tej samej trasie do wytwarzania produktów wielu, lub można zdefiniować unikatową trasę dla każdego produktu lub wariantu produktu. Można nawet mieć wiele tras dla tego samego produktu. W takim przypadku trasy, która jest używana zależy od czynników takich jak ilość, jaka musi zostać wyprodukowana. Definicja usługi Microsoft Dynamics 365 dla operacji marszruty składa się z czterech oddzielnych elementów, które ze sobą, opisują proces produkcji:

-   **Trasa** – trasy definiuje strukturę procesu produkcji. Innymi słowy definiuje kolejność operacji.
-   **Operacja** — operacja identyfikuje nazwany krok na trasie, takich jak **zestawu**. Ta sama operacja może wystąpić w wielu tras i może mieć numery różnych operacji.
-   **Relacja operacji** — relacji operacji definiuje właściwości operacyjnych operacji, takich jak czasu przezbrajania i czasu procesu, kategorie kosztów, parametry zużycia i wymagań dotyczących zasobów. Relacja operacji umożliwia operacyjne właściwości operacji różna, w zależności od trasy, która operacja jest używany w lub produktów, które są produkowane.
-   **Wersja marszruty** — wersja marszruty określa trasę, która jest używana do produkcji produktów lub wariantów produktu. Wersje marszruty umożliwiają trasy ponowne wykorzystanie wszystkich produktów lub zmianom w czasie. Umożliwiają one również różne trasy do być użyte do produkcji tego samego produktu. W takim przypadku trasy, która jest używana zależy od czynników, takich jak lokalizacja lub ilość, jaka musi zostać wyprodukowana.

## <a name="routes"></a>Marszruty
Marszruta opisuje kolejność operacji, który jest używany do produkcji produktów lub wariantów produktu. Każda operacja jest przypisany numer operacji i operacji następnika. Kolejność operacji tworzy sieć tras, która może być reprezentowany przez ukierunkowanych wykresu, który ma jeden lub więcej punktów początkowych i jeden punkt końcowy. W usłudze Dynamics 365 dla operacji trasy są rozróżniane na podstawie typu Struktura. Są dwa typy tras prostych tras i trasy sieci. W parametry kontroli produkcji można określić, czy mogą być używane tylko proste trasy lub czy bardziej złożonych sieci trasy mogą być używane.

### <a name="simple-routes"></a>Prostych tras

Prosty trasa jest sekwencyjnie, a istnieje tylko jeden punkt początkowy dla marszruty.  

[![Simple route](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Jeśli zostanie włączone tylko proste trasy w parametry kontroli produkcji, Dynamics 365 dla operacji automatycznie generuje numery operacji (10, 20, 30 i tak dalej) podczas definiowania trasy.

### <a name="route-networks"></a>Sieci tras

Jeśli włączysz bardziej złożonych sieci tras w parametry kontroli produkcji, można zdefiniować tras, które mają wiele punktu początkowego i operacje, które mogą być wykonywane równolegle.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Uwagi:**

-   Każda operacja może mieć operację tylko jeden następnika, a całą trasę musi kończyć się w jednej operacji.
-   Nie ma żadnej gwarancji, że wielu operacji, które mają tę samą operację następnika (na przykład operacji 30 i 40 na powyższej ilustracji) będzie być rzeczywiście wykonywane równolegle. Dostępności i wydajności zasobów mogą stanowić ograniczenia w taki sposób, że operacje są planowane.
-   0 (zero) nie można używać jako numeru operacji. Ten numer jest zarezerwowany i jest używana do określenia, że ostatniej operacji w marszrucie ma żadnej operacji następnika.

### <a name="parallel-operations"></a>Równoległych operacji

Czasami połączenie wielu zasobów operacje, które mają różne charakterystyki jest wymagane w celu wykonania operacji. Działalność montażową prowadzoną może na przykład wymagać maszyny, narzędzia i jednego pracownika dla każdego z dwóch maszyn do nadzorowania operacji. W tym przykładzie mogą być modelowane przy użyciu operacji równoległych, gdzie jedna operacja jest wyznaczony jako podstawowy operacja i innymi są wtórne.  

[![Trasa, która ma operacje główne oraz dodatkowe](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Zazwyczaj operacji głównej reprezentuje zasób w wąskim gardle i decyduje o tym, czas jednostkowy operacji podrzędnych. Jednak podczas planowania obejmujące ograniczone zdolności produkcyjne, zasoby, które są planowane dla zarówno operacji głównej, jak i dodatkowych operacji musi być dostępna i wolnych mocy produkcyjnych w tym samym czasie.  

Zarówno operacji głównej, jak i dodatkowych operacji musi mają ten sam numer operacji (30 na powyższej ilustracji).  

W poprzednim przykładzie zapotrzebowanie dla operacji głównej (30) to komputer, wymagania dotyczące zasobów dla operacji podrzędnych (30' i 30'') są narzędzia a pracownikiem. Pięćdziesiąt procent obciążenia pomaga zagwarantować zaplanowane pracownik może nadzorować dwa komputery w tym samym czasie.

### <a name="approval-of-routes"></a>Zatwierdzenie marszrut

Trasa muszą zostać zatwierdzone, zanim będzie można używać w procesie planowania i produkcji. Zatwierdzenie wskazuje, że projektowaniem tras została ukończona. Takie same zwolniony produkt albo wariant zwolnionego produktu może mieć wiele tras zatwierdzone. Zazwyczaj zatwierdzania marszruty występuje po zatwierdzeniu pierwszej wersji istotnego szlaku. Jednak w niektórych przedsiębiorstw scenariuszy, zatwierdzania marszruty i wersji marszruty są oddzielne działania, które może obejmować właścicieli różnych procesów.  

Każda trasa może być zatwierdzone lub niezatwierdzone oddzielnie. Należy jednak zauważyć, że trasa jest niezatwierdzony, wszystkie wersje marszruty również są niezatwierdzone. W parametry kontroli produkcji można określić, czy trasy mogą być niezatwierdzone, i można zmienić zatwierdzonych marszrut.  

Jeśli dziennik musi przechowywać zapisy którzy zatwierdzą każdej trasy, może wymagać podpisów elektronicznych dla zatwierdzania marszruty. Użytkownicy będą musieli potwierdzić swoją tożsamość za pomocą [podpisu elektronicznego](/dynamics365/operations/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Rozwiązanie Operations
Operacja to krok w procesie produkcji. W usłudze Dynamics 365 dla operacji każda operacja ma identyfikator i prosty opis. Następujące tabele przedstawiono przykłady typowych operacji w warsztacie.

| Operacja  | opis        |
|------------|--------------------|
| PipeCut    | Cięcie rur       |
| TIGweld    | Spawanie TIG        |
| JigAssy    | Giga zestawu       |
| Kontrola | Kontrola jakości |

Właściwości operacyjnych operacji, takich jak czasu przezbrajania i czasu procesu, wymagań dotyczących zasobów, informacji o kosztach i kalkulacji zużycia, są określone na relacji operacji. (Aby uzyskać więcej informacji o relacjach operacji, zobacz następną sekcję).

## <a name="operation-relations"></a>Relacje operacji
Następujące właściwości operacyjnych operacji są utrzymywane na relacji operacji:

-   Kategorie kosztu
-   Parametry zużycia
-   Czas przetwarzania
-   Ilości przetwarzania
-   Zapotrzebowanie na zasoby
-   Uwagi i instrukcje

Można zdefiniować wiele relacji operacji tej samej operacji. Jednak każda relacja operacji jest specyficzne dla jednej operacji i przechowuje właściwości, które są specyficzne dla trasy, zwolniony produkt lub zestaw zwolnionych produktów, które są związane z grupy towarów. W związku z tym ta sama operacja może służyć w wielu tras, które mają różne właściwości operacyjnych. Łatwiej można ponadto zachować dane główne, jeśli używasz standardowych operacji, które mają takie same właściwości działania, bez względu na trasę, która jest używana i produktu, który jest wytwarzany. Zakres relacji operacji jest zdefiniowany za pomocą **kod towaru**, **przedmiotu relacji**, **rozesłać kodu** i **rozesłać relacji** właściwości, jak pokazano w poniższej tabeli.

| Kod pozycji | Relacja produktu         | Kod marszruty | Relacja do marszruty   | Zakres relacji operacji                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabela     | &lt;Identyfikator towaru&gt;       | Marszruta      | &lt;Identyfikator marszruty&gt; | Właściwości operacyjnych operacji, gdy jest używany w marszrucie gdzie **numer marszruty**=&lt;rozesłać ID&gt; do produkcji zwolnionego produktu gdzie **kod towaru,**=&lt;identyfikator elementu&gt;.                                                                                                                        |
| Tabela     | &lt;Identyfikator towaru&gt;       | Wszystko        |                  | Domyślne właściwości operacyjnych operacji, gdy jest używany do produkcji zwolnionego produktu gdzie **kod towaru,**=&lt;identyfikator elementu&gt;. Innymi słowy te właściwości operacyjnych stosuje, gdy nie ma żadnych relacji operacji specyficznych dla zwolnionego produktu.                                     |
| Grupa     | &lt;Identyfikator grupy towarów&gt; | Marszruta      | &lt;Identyfikator marszruty&gt; | Właściwości operacyjnych operacji, gdy jest używany w marszrucie gdzie **numer marszruty**=&lt;rozesłać ID&gt; do produkcji zwolnionych produktów, które są skojarzone z grupy towarów &lt;grupy identyfikator elementu&gt;, chyba że istnieje relacja operacji specyficznych dla zwolnionego produktu.                         |
| Grupa     | &lt;Identyfikator grupy towarów&gt; | Wszystko        |                  | Domyślne właściwości operacyjnych operacji, gdy jest używany do produkcji zwolnionych produktów, które są skojarzone z grupy towarów &lt;grupy identyfikator elementu&gt;, chyba że istnieje bardziej konkretne relacji operacji.                                                                                                  |
| Wszystko       |                       | Marszruta      | &lt;Identyfikator marszruty&gt; | Domyślne właściwości operacyjnych operacji, gdy jest używany w marszrucie gdzie **numer marszruty**=&lt;rozesłać ID&gt;. Innymi słowy te właściwości operacyjnych stosuje, gdy nie ma żadnych relacji operacji dla tej trasy, które są specyficzne dla jednej zwolnionego produktu lub związany z nim element grupy. |
| Wszystko       |                       | Wszystko        |                  | Domyślne właściwości operacyjnych operacji. Te właściwości operacyjnych stosuje się gdy bardziej konkretne relacji operacji nie istnieje.                                                                                                                                                                |

Można również określić, że relacja operacji jest specyficzne dla witryny. W ten sposób działania właściwości operacji mogą się różnić, w zależności od lokalizacji (witryna), gdzie jest wykonywana. Dla produktów skonfigurowane można również określić różne właściwości operacyjnych dla każdej konfiguracji produktu.  

Relacje operacji daje dużą elastyczność podczas definiowania trasy. Ponadto możliwość definiowania właściwości domyślnych pomaga zmniejszyć ilość danych podstawowych, które należy zachować. Jednak ta elastyczność oznacza również, że musisz być świadomy kontekstu, który można modyfikować relacji operacji w.  

**Uwaga:** ponieważ operacyjne właściwości są przechowywane w relacji operacji dla operacji na trasie, wszystkie wystąpienia tej samej operacji (na przykład zgromadzenie) mają samego czasu przezbrajania, czasu procesu, wymagania dotyczące zasobów i tak dalej. W związku z tym jeśli dwa wystąpienia operacji musi występować w tej samej trasie, ale mają różne czasy, należy utworzyć dwa odrębne operacje, takie jak Assembly1 i Assembly2.

### <a name="modifying-product-specific-routes"></a>Modyfikowanie trasy specyficzne dla produktu

Po otwarciu **trasa** strona z **zwolnione szczegółów produktu** strony, są wyświetlane w wersji marszruty, które są skojarzone z wybranym zwolnionego produktu. W tym kontekście, dla każdej operacji 365 Dynamics dla operacji zawiera właściwości operacyjnych od relacji operacji najtrafniej odpowiadającego wersji marszruty. Można zauważyć, że zawiera listę operacji **kod towaru** i **rozesłać kod** właściwości z relacji operacji. W związku z tym można określić, które relacji operacji zostaną uwzględnione.  

Na **trasa** stronę, można zmodyfikować właściwości operacyjnych operacji, takich jak czas jednostkowy lub kategorii kosztów. Wprowadzone zmiany są przechowywane na relacji operacji, która jest specyficzna dla marszruty i zwolnionego produktu, do których odwołuje się w bieżącej wersji marszruty. Jeśli relacja operacji, który jest wyświetlany nie jest specyficzne dla trasy i zwolnionego produktu, zanim wprowadzone zmiany są przechowywane, system tworzy kopię relacji operacji. Ta kopia *jest* specyficzne dla marszruty i zwolnionego produktu. W związku z tym wprowadzone zmiany nie mają wpływu na pozostałe drogi lub zwolnionych produktów. Aby sprawdzić, które relacji operacji jest modyfikowany na **trasa** strona, spójrz na **kod towaru** i **rozesłać kod** pól.  

Można także ręcznie utworzyć operację, która jest specyficzna dla marszruty i zwolnionego produktu za pomocą **Kopiuj i Edytuj relację** funkcji.  

**Uwaga:** Jeśli dodać nową operację do trasy na **trasa** stronę, relacji operacji jest tworzony tylko dla bieżącego zwolnionego produktu. Dlatego jeśli trasa jest również używany do produkcji innych produktów zwolnione, nie relacji operacji mających zastosowanie będzie istnieć dla tych zwolnionych produktów i nie jest już używana trasa dla tych zwolnionych produktów.

### <a name="maintaining-operation-relations-per-route"></a>Utrzymywanie kontaktów z operacji / marszrutę

Po otwarciu **szczegółów marszruty** strona z **trasy** strony listy pojawi się lista wszystkich relacji operacji, które mają zastosowanie do wybranej marszruty. W związku z tym można łatwo sprawdzić, właściwości operacyjnych, które są używane dla jakich produktów. Można zmodyfikować domyślne wartości właściwości i wartości właściwości specyficzne dla produktu.  

Po dodaniu nowej relacji operacji na **szczegółów marszruty** strony, **rozesłać kod** jest automatycznie ustawiane na **trasa**i **rozesłać relacji** pole jest ustawione na numer marszruty bieżącej marszruty.

### <a name="maintaining-operation-relations-per-operation"></a>Utrzymywanie kontaktów z operacji dla operacji

Od **operacji** stronę, można otworzyć **relacji operacji** strony. Na tej stronie można zmodyfikować wszystkie relacje operacji dla określonej operacji. Można nawet modyfikować relacje operacji, które zawierają wartości domyślne.  

Jeśli Twoja firma używa standardowych operacji i parametrów operacyjnych są takie same we wszystkich produktach i procesach, **relacji operacji** strona zapewnia wygodny sposób utrzymania domyślne właściwości operacyjne tych operacji.

### <a name="applying-operation-relations"></a>Stosowanie relacji operacji

W niektórych przypadkach 365 Dynamics dla operacji musi znaleźć właściwości operacyjnych dla operacji. Na przykład podczas tworzenia zamówienia zakupu, właściwości operacyjnych każdego działania muszą zostać skopiowane z relacji operacji do marszruty produkcji. W takich sytuacjach 365 Dynamics dla operacji wyszukiwania stosunków odpowiedniej operacji z najbardziej charakterystyczną kombinację do najmniej szczegółowej kombinacji.  

Kiedy 365 Dynamics dla operacji wyszukiwania dla relacji operacji najbardziej odpowiednie dla zwolnionego produktu, zgodny z Identyfikatorem towaru zwolnionego produktu relacji operacji jest preferowany nad relacji operacji, która dopasowań grupy towarów identyfikator. Z kolei relacji operacji zgodny z Identyfikatorem grupy towaru jest preferowany przez domyślne relacji operacji. Wyszukiwanie jest wykonywane w następującej kolejności:

1.  **Kod towaru**=**tabeli** i **przedmiotu relacji**=&lt;identyfikator elementu&gt;
2.  **Kod towaru**=**grupy** i **przedmiotu relacji**=&lt;identyfikator grupy towaru&gt;
3.  **Kod towaru**=**wszystkie**
4.  **Kod marszruty**=**trasa** i **rozesłać relacji**=&lt;identyfikator marszruty&gt;
5.  **Kod marszruty**=**wszystkie**
6.  **Konfiguracja**=&lt;identyfikator konfiguracji&gt;
7.  **Configuration**=
8.  **Witryna**=&lt;Identyfikatora witryny&gt;
9.  **Site**=

W związku z tym operację stosuje się tylko jeden raz dla każdej trasy. Jeśli operacja występuje wiele razy w tej samej trasie, wszystkie wystąpienia tej operacji będą miały tej samej relacji operacji i nie będzie mógł mieć różne właściwości (na przykład uruchomić razy) w przypadku każdego wystąpienia.

## <a name="route-versions"></a>Wersje marszruty
Aby uwzględnić zmiany w produkcji produktów lub zapewniają większą kontrolę nad procesem produkcji są używane wersje marszruty. Określają one, które trasy powinny służyć podczas określonego zwolniony produkt lub wariant zwolniony produkt jest wytwarzany. Następujące ograniczenia można użyć do zdefiniowania, w którym trasa jest używana dla zwolnionego produktu:

-   Wymiary produktu (rozmiar, kolor, styl lub konfiguracji)
-   Ilość produkcji
-   Zakład produkcyjny
-   Data produkcji

Gdy w przypadku wytwarzania produktu w określonej lokacji, w określonej ilości, lub w danym okresie, można oznaczyć jako domyślnej wersji marszruty określonej wersji marszruty. Należy jednak zwrócić uwagę, że tylko jedną aktywną trasę dla danego produktu zwolniony i podany zestaw ograniczeń jest dozwolone.  

W przypadku parametry kontroli produkcji można wymagać podania zawsze okres ważności wersji marszruty.

### <a name="approval-of-route-versions"></a>Zatwierdzenie wersji marszruty

Przed użyciem wersji marszruty w planowaniu lub procesu produkcyjnego, muszą zostać zatwierdzone. Po zatwierdzeniu wersji marszruty można zatwierdzić związanym z marszruty. Należy jednak pamiętać, że wersja marszruty mogą być zatwierdzane tylko wtedy, gdy drogi również została zatwierdzona.

### <a name="activating-the-default-route-version"></a>Aktywowanie wersji marszruty domyślnej

Podczas aktywacji wersji marszruty można wyznaczyć go jako użyje domyślnej wersji marszruty wzorca, planowanie, lub który będzie służyć do tworzenia zleceń produkcyjnych. Może mieć tylko jedna aktywna wersja marszruty dla danego zestawu warunków ograniczających (na przykład, okres, witryny lub ilości). Jeśli wersja, że próbujesz uaktywnić powoduje konflikt z wersją już jest aktywne, zostanie wyświetlony komunikat o błędzie. Aby zapobiec niejednoznaczne aktywacji, należy następnie albo Dezaktywuj powodujące konflikt wersji lub zmodyfikować ograniczenia (zwykle okres) w wersji marszruty.

### <a name="electronic-signatures"></a>Podpisy elektroniczne

Jeśli dziennik musi przechowywać zapisy którzy zatwierdza i uaktywnia każdej wersji marszruty, można zażądać podpisów elektronicznych dla tych zadań. Użytkownicy, którzy zatwierdzić i aktywować wersje marszrut będą musieli potwierdzić swoją tożsamość za pomocą [podpisu elektronicznego](/dynamics365/operations/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Zmiany produktu, który używa zarządzania sprawami

Produkt Zmień wielkość liter, zatwierdzania i Aktywacja nowych lub zmienionych tras i wersje marszruty daje łatwym sposobem wyświetlenia przeglądu ograniczeń wersji marszruty. Można zatwierdzić i aktywować wszystkie trasy, które odnoszą się do określonej zmiany w jednej operacji i Udokumentowanie wyników w przypadku zmiany produktu.

## <a name="maintaining-routes"></a>Obsługiwanie marszrut
W zależności od wymagań biznesowych może być w stanie zmniejszyć nakład, który jest wymagany w celu utrzymania swoje definicje procesów.

### <a name="making-routes-independent-of-resources"></a>Dokonywanie trasy niezależnie od zasobów

W wielu systemach operacji zasobu lub grupy zasobów, które należy wykonać operację należy określić w marszrucie. Jednak w usłudze Dynamics 365 dla operacji, można zdefiniować zestaw wymagań, które zasób operacje muszą spełnić, aby mieć zastosowanie dla operacji. W związku z tym nie ma ustalonych aż operacja ma się odbyć określonych operacji zasobu lub grupy zasobów, która powinna być używana. Ta funkcja jest szczególnie przydatna, gdy masz wiele pracowników i maszyn, które można wykonać tę samą operację.  

Na przykład określisz, że operacja wymaga zasobu operacje z **maszyny** typu, który ma **tłoczenia** możliwości 20 ton. Podczas planowania operacji aparat planowania następnie rozwiąże te wymagania do określonych operacji zasobu lub grupy zasobów. Ponieważ można określić tylko te wymagania, zamiast powiązanie operacji określonej maszyny, masz większą elastyczność. Dodatkowo konserwacja jest łatwiejsze, gdy zasoby są przenoszone lub są dodawane nowe zasoby.  

Aby uzyskać więcej informacji na temat różnych rodzajów wymagań dotyczących zasobów i sposobu ich używania, zobacz zapotrzebowań na zasoby operacji i [możliwości zasobów](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Udostępnianie trasy między witrynami

Jeśli produkują tego samego produktu w więcej niż jednym miejscu produkcji i kroki do wytworzenia produktu są takie same na wszystkich stronach, można zaprojektować często udostępnionego trasę, która jest używana we wszystkich witrynach produkcji. Aby utworzyć trasę udostępnionych, nie określenia witryny sama marszruta. Jednakże nadal należy utworzyć wersji marszruty, który kojarzy udostępnioną trasę z produktu w każdej lokacji.  

Również należy się upewnić, nie wymagają określonych operacji zasobów lub grup zasobów dla wymagań zasobów dla każdej operacji w marszrucie, ale zamiast tego są wyrażone w postaci właściwości wymaganych zasobów. Następnie będzie można przypisać zasoby odpowiednie operacje z witryny, że produkcja jest planowana na aparat planowania. Na przykład jeśli istnieje niewielka różnica w czasie wykonywania lub czas przezbrajania dla określonej operacji jest specyficzne dla lokacji, można określić te informacje poprzez dodanie relacji dodatkowych operacji dla tej witryny.  

W pełni wykorzystać zalety trasy udostępnione, należy również użyć zużycia zasobów na odpowiednie zestawienie komponentów (BOM). Po ustawieniu flagi zużycia zasobu w wierszu BOM, Magazyn i lokalizacji, w której surowce powinny być spożywane z wynika z zasobów operacji, która operacja jest zaplanowana na. W związku z tym magazynu i lokalizacja nie trzeba ustalona, do momentu rzeczywistego planowania produkcji. W ten sposób można tworzyć zarówno BOM i marszruty niezależnie od fizycznej lokalizacji, gdzie produkt jest wytwarzany.

### <a name="standard-operation-relations"></a>Relacje operacji standardowych

Jeśli Twoja firma korzysta z operacji standardowych w całej produkcji i jeśli istnieje niewielki lub żaden zmienność czasu przezbrajania, czasu pracy, Obliczanie zużycia, obliczanie kosztów, i itd., może się wiązać z tworzenie domyślne relacje operacji dla wszystkich operacji. W takim przypadku należy unikać tworzenia relacji operacji, które są specyficzne dla każdej trasy lub zwolnionego produktu.  

Spłacająca również express zapotrzebowania na zasoby pod względem umiejętności i możliwości, swoje trasy niezależne od witryny, może pomóc zachować bieżące utrzymanie procesów biznesowych do minimum.  

Kiedy użyjesz tej metody, **relacji operacji** strona staje się swoje główne miejsce docelowe dla utrzymania czasy i inne właściwości.

### <a name="resource-specific-process-times"></a>Czas procesu określonych zasobów

Jeśli nie określisz operacji zasobu lub grupy zasobów w ramach wymagań zasobów dla operacji, pasujące zasoby mogą działać przy różnych prędkościach. W związku z tym czas potrzebny do przetwarzania operacji może się różnić. Aby rozwiązać ten problem, można użyć **formuła** w relacji operacji, aby określić, jak czas procesu jest obliczany. Dostępne są następujące opcje:

-   **Standard** — (opcja domyślna) używa tylko pola z relacji operacji i pomnożony przez ilość zamówienia, co określony czas jednostkowy obliczenia.
-   **Pojemność** – obliczenie obejmuje **zdolności** pola zasobu operacje. W związku z tym czas jest zależny od zasobu. Wartość, która jest określona w operacji zasobu jest zdolności produkcyjne na godzinę. Wartość ta jest mnożona przez ilość zamówienia i **współczynnik** wartość z relacji operacji.
-   **Partia** — wielkość partii jest obliczana przy użyciu informacji z relacji operacji. Numer partii, i w związku z tym czas procesu może następnie zostać obliczona na podstawie ilości w zamówieniu.
-   **Partia zasobów** — ta opcja jest zasadniczo taka sama, jak **partii** opcji. Jednak obliczenie obejmuje **partii zdolności** pola zasobu operacje. W związku z tym czas jest zależny od zasobu.


<a name="see-also"></a>Informacje dodatkowe
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


