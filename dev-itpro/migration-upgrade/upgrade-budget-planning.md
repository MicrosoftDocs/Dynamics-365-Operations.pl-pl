---
title: "Uaktualnienie funkcjonalności planowania budżetu"
description: "Istnieją znaczne różnice funkcjonalności planowania budżetu między programami Microsoft Dynamics AX 2012 i Microsoft Dynamics 365 for Finance and Operations. Niektóre funkcje nie zostały uaktualnione i dlatego wymagają zmiany konfiguracji. W tym temacie wyjaśniono, co trzeba ponownie skonfigurować, oraz opisano nowe funkcje, które trzeba wziąć pod uwagę po wykonaniu uaktualnienia."
author: twheeloc
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: ryansand
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 83e93df3284760c46cb95b931f32cc9990ef2db1
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Uaktualnienie funkcjonalności planowania budżetu
<a id="upgrade-budget-planning" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Istnieją znaczne różnice funkcjonalności planowania budżetu między programami Microsoft Dynamics AX 2012 i Microsoft Dynamics 365 for Finance and Operations. Niektóre funkcje nie zostały uaktualnione i dlatego wymagają zmiany konfiguracji. W tym temacie wyjaśniono, co trzeba ponownie skonfigurować, oraz opisano nowe funkcje, które trzeba wziąć pod uwagę po wykonaniu uaktualnienia.  

W programie Microsoft Dynamics 365 for Finance and Operations funkcjonalność planowania budżetu ma wiele ulepszeń, które nie były dostępne w systemie Microsoft Dynamics AX 2012. W tym temacie opisano zmiany, które muszą wprowadzić użytkownicy dokonujący uaktualnienia. Wskazano także nowe funkcje, które należy wziąć pod uwagę w procesie uaktualniania. Ze względu na zakres zmian nie będzie można otworzyć żadnych istniejących planów budżetu, dopóki nie zostaną wprowadzone zmiany opisane w tym temacie. Raporty powinny jednak działać bez konieczności wprowadzania dodatkowych zmian.

## Omówienie zmian
<a id="overview-of-changes" class="xliff"></a>
Wprowadzono wiele istotnych zmian w module Budżetowanie w programie Finance and Operations. Te zmiany służą temu, aby planowanie budżetu było łatwiejsze do skonfigurowania i pozwalało bardziej wykorzystywać już istniejące elementy, co powinno ograniczyć ilość czynności konfiguracyjnych i konserwacyjnych wykonywanych co roku. Następujące obszary systemu AX 2012 nie istnieją już w programie Finance and Operations:

-   Szablony planu budżetu (Konfiguracja planowania budżetu)
-   Foldery planu budżetu (Konfiguracja planowania budżetu)
-   Ograniczenia scenariusza (Konfiguracja planowania budżetu)
-   Szablony reguł etapów planowania budżetu (Proces planowania budżetu)
-   Pola macierzy szablonów arkuszy
-   Kreator szablonów planowania budżetu w programie Microsoft Excel

Niektóre nowe koncepcje nie są bezpośrednim uaktualnieniem poprzedniej funkcjonalności. W związku z tym należy dokonać pewnych zmian konfiguracyjnych. W poniższych sekcjach opisano rozwiązania, które zastąpiły elementy na powyższej liście.

### Kolumny
<a id="columns" class="xliff"></a>

Kolumny są nową koncepcją, która zastępuje sekcje szablonu programu Excel, a także pola macierzy. Kolumny mogą reprezentować okres, miesiąc, kwartał, rok lub cały czas. Odwołanie do czasu jest dynamiczne. Wskazuje ono względny okres lub roku w odniesieniu do procesu budżetu. Na przykład kolumna **Poprzedni rok Styczeń** odwołuje się do okresu obrachunkowego 1 w roku -1. Kolumna jest specyficzna dla scenariusza planu budżetu, takiego jak wartości rzeczywiste lub żądanie budżetu.

### Układy
<a id="layouts" class="xliff"></a>

Układy są nową koncepcją zastępującą szablon programu Excel. Układy zawierają kolumny określające, które dane budżetowe lub rzeczywiste i okresy mają być pokazywane. Układy są również współużytkowane przez aplikację kliencką i dodatek programu Excel. Z tego względu obsługa przez użytkownika podczas wprowadzania lub wyświetlania danych w aplikacji klienckiej Finance and Operations jest lepsza niż obsługa w systemie AX 2012. Przy wprowadzaniu danych w aplikacji klienckiej Finance and Operations nie ma już ograniczenia do wyświetlania i wprowadzania w jednym scenariuszu w widoku transakcji. Zamiast tego widok porównania pozwala łatwo wyświetlać i wprowadzać kwoty dla wielu okresów i kont w tym samym czasie. Układy można również zdefiniować tak, aby pozwalały wprowadzać i wyświetlać waluty, komentarze i inne dane opcjonalne. Układy pozwalają również określić, które wymiary księgowe i opisy wymiarów mają być wyświetlane. Układy zawierają również ograniczenia scenariuszy określające, które kolumny w szablonie mogą być edytowane i które kolumny powinny być dostępne w programie Excel. Po zdefiniowaniu układu jest dla niego generowany szablon. Ten szablon z kolei tworzy odpowiedni szablon programu Excel. Następnie można edytować szablon programu Excel, aby umieścić w nim więcej formuł i formatowania, a następnie przekazać go ponownie. Układy są następnie przypisywane do każdej reguły etapu na stronie **Proces planowania budżetu**. W efekcie układy zastępują szablony, które były przypisywane i używane w podobny sposób.

### Procesy planowania budżetu
<a id="budget-planning-processes" class="xliff"></a>

Procesy planowania budżetu są w większości takie same, jak w systemie AX 2012. Najważniejszą zmianą jest zastąpienie szablonów układami. Jeśli jakiekolwiek procesy zostały wcześniej zakończone w systemie AX 2012, zostaną zaktualizowane do stanu „w toku”, tak aby można było wprowadzić w nich zmiany. Należy przypisać układy do wszystkich reguł etapów, aby określać, które scenariusze i okresy będą wyświetlane po otwarciu planu w aplikacji klienckiej. Układy decydują również, które szablony programu Excel są otwierane poza programem Dynamics 365 for Finance and Operations, tak aby można było wyświetlić budżet. **Domyślna struktura konta** to nowe pole wymagane w oknie Proces planowania budżetu. Dla każdego procesu planowania budżetu należy przypisać podstawową strukturę konta, która powinna być używana do budżetowania.

### Załączniki
<a id="attachments" class="xliff"></a>

W systemie AX 2012 dokumenty uzasadnienia były zapisywane w folderze załączników. Żadne wcześniejsze dokumenty uzasadnienia nie są uaktualniane. Obecnie dokumenty uzasadnienia są przechowywane w bazie danych. Jeśli te informacje powinny być zapisywane w uaktualnionej wersji, można przekazać końcowe dokumenty uzasadnienia dla każdego planu jako załącznik, używając przycisku za pomocą **Uzasadnienie** w okienku akcji. W systemie AX 2012 arkusze programu Excel dla każdego planu budżetu były tworzone na podstawie szablonu. W programie Finance and Operations we wszystkich planach jest otwierana kopia układu. Jednak nie są zapisywane żadne modyfikacje pliku programu Excel. Wszelkie formuły i informacje pomocnicze, których użyto indywidualnie dla poszczególnych planów, muszą zostać dodane poprzez komentarze, uzasadnienie lub inny proces uzupełniający.

## Konfigurowanie środowiska uaktualnionego z systemu AX 2012
<a id="configuring-an-upgraded-environment-from-ax-2012" class="xliff"></a>
Aby pomóc użytkownikom dobrać sposób konfigurowania uaktualnionego systemu, poniżej przedstawiono przykład uaktualnienia procesu budżetu opartego na danych demonstracyjnych z systemu AX 2012. Utworzono domyślne dane konfiguracyjne kolumn, aby ułatwić proces uaktualniania. Możesz zaktualizować lub usunąć te dane domyślne, jeśli nie spełniają Twoich wymagań dotyczących konfiguracji. **Uwaga:** Istnieją nowe pola wymagane, które nie zostaną ustawione w systemie. Jeśli zablokujesz się na stronie, takiej jak **Konfiguracja planowania budżetu**, i nie możesz z niej wyjść, zamknij przeglądarkę i otwórz ją ponownie na innej stronie, która pozwoli wprowadzić szczegóły w odpowiedniej kolejności. Istnieją wymagane pola, które jeszcze nie są ustawione. W związku z tym mogą wystąpić problemy, dopóki wszystkie ustawienia nie zostaną skonfigurowane, a wymagane pola wypełnione. W tym temacie wyjaśniono, jak wypełnić te pola zgodnie z wymaganiami. Oto niektóre wymagane pola:

-   Strona **Proces planowania budżetu**: pole **Domyślna struktura konta**
-   Strona **Proces planowania budżetu**: pole **Układ** na skróconej karcie **Reguły i układy etapu planowania budżetu**

### Definiowanie kolumn i układów
<a id="define-columns-and-layouts" class="xliff"></a>

1.  Na stronie **Konfiguracja planowania budżetu** kliknij kartę **Kolumny**. W ramach uaktualnienia nowe kolumny są tworzone automatycznie na podstawie Twoich wierszy planu budżetu. Kolumny używają teraz dat dynamicznych, gdzie czas i rok są przesunięte względem roku obrachunkowego zdefiniowanego w procesie planowania budżetu. **Uwaga:** Ze względów wydajnościowych podczas uaktualniania zakłada się, że wszystkie cykle budżetu reprezentują lata kalendarzowe, a nie obrachunkowe. Jeśli używasz lat obrachunkowych, trzeba wprowadzić modyfikacje zapewniające prawidłowe mapowanie kolumn na ich rok obrachunkowy. Na przykład następujące elementy istniały w systemie AX 2012:
    -   Scenariusze planu budżetu: Wartości rzeczywiste, Podstawa, Żądanie budżetu, Budżet zatwierdzony
    -   Wiersze planu budżetu dla wszystkich scenariuszy w roku 2017, a wartości rzeczywiste dla lat 2017 i 2016

    W programie Finance and Operations zostaną utworzone następujące kolumny:
    | Nazwa kolumny    | Scenariusz planu budżetu | Okres kolumny | Przesunięcie roku |
    |----------------|----------------------|--------------------|-------------|
    | Sty Scenariusz 1 | Wartości rzeczywiste              | 1                  | 0           |
    | Sty Scenariusz 2 | Podstawa             | 1                  | 0           |
    | Sty Scenariusz 3 | Żądanie budżetu       | 1                  | 0           |
    | Sty Scenariusz 4 | Budżet zatwierdzony      | 1                  | 0           |
    | Sty Scenariusz 5 | Wartości rzeczywiste              | 1                  | -1          |
    | Lut Scenariusz 1 | Wartości rzeczywiste              | 1                  | 0           |
    | ...            | ...                  | ...                | ...         |

    W tym przykładzie kolumna o nazwie **Sty Scenariusz 1** jest tworzona dla najnowszych znalezionych danych transakcji planu budżetu, gdy istnieją transakcje w styczniu. Podobna kolumna jest tworzona dla każdego scenariusza zawierającego dane. Po utworzeniu kolumn dla wszystkich okresów w danym roku są tworzone kolumny dla poprzednich lat.
2.  Nazwy i opisy kolumn oraz inne szczegóły można zmienić ręcznie w aplikacji klienckiej lub poprzez wykonanie zbiorczej aktualizacji przy użyciu dodatku programu Excel odwołującego się do jednostki danych kolumn planu budżetu. Wszystkie filtry, które zostały wcześniej ustawione dla pól macierzy, teraz są ustawione w kolumnach.
3.  Utwórz nowy układ planu budżetu. Układ wskazuje kilka kolumn definiujących widok, który będzie wyświetlany w programie Excel i aplikacji klienckiej. Układ wymaga, aby najpierw określić zestaw wymiarów księgowych w celu wskazania, które wymiary finansowe można wprowadzać. Po określeniu zestawu wymiarów kliknij przycisk **Opisy** i wybierz opisy wymiarów, które mają zostać umieszczone w układzie.
4.  Na skróconej karcie **Elementy układu** kliknij przycisk **Dodaj** i dla każdego wiersza dodaj metadane, takie jak waluta, komentarz lub klasa budżetu, która przyporządkowuje wiersze przychodów wierszom wydatków. Następnie dodaj kolumny dla przedziału czasu oraz scenariusze, które mają zastosowanie do tego cyklu i etapu budżetu. Te zmiany można wprowadzać ręcznie w aplikacji klienckiej lub przy użyciu dodatku programu Excel odwołującego się do jednostki danych elementów układu planu budżetu.
5.  Dla każdego elementu układu określ, czy kolumnę można modyfikować oraz czy kolumna ma być wyświetlana także w skoroszycie programu Excel dla tego układu. **Uwaga:** Dla planów historycznych można rozważyć układ, który pokazuje 12 miesięcznych kolumn dla każdego scenariusza planu budżetu w tym procesie.

### Aktualizacja procesów planowania budżetu pod kątem używania odpowiedniego układu na każdym etapie budżetu
<a id="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage" class="xliff"></a>

1.  Na stronie **Proces planowania budżetu** zaznacz proces, który chcesz skonfigurować.
2.  W okienku akcji kliknij przycisk **Edytuj**.
3.  Określ domyślną strukturę konta dla tego procesu budżetu. **Domyślna struktura konta** to nowe pole wymagane, które trzeba ustawić.
4.  Na skróconej karcie **Reguły i układy etapu planowania budżetu** w polu **Układu** zaznacz układ, który został wcześniej skonfigurowany i jest odpowiedni dla tego etapu.
5.  Kontynuuj wybieranie tego samego lub innych układów dla różnych etapów planowania budżetu, a następnie zapisz wprowadzone zmiany.

## Dodatkowe funkcje, które należy wziąć pod uwagę w procesie budżetowania
<a id="additional-features-to-consider-in-your-budgeting-process" class="xliff"></a>
### Obszar roboczy Planowanie budżetu
<a id="budget-planning-workspace" class="xliff"></a>

Ten obszar jest przeznaczony dla właściciela budżet i poszczególnych współautorów budżetu. Zawiera łącza do wszystkich dokumentów budżetu wymagających uwagi. Są tu również raporty i kluczowe wskaźniki wydajności (KPI) dotyczące procesu budżetu. Administrator budżetu może na stronie **Parametrach budżetowania** zdefiniować bieżący proces planowania budżetu dla wszystkich użytkowników. Na karcie **Ustawienia obszaru roboczego** skrócona karta **Planowanie budżetu** zawiera pole, gdzie można wybrać proces planowania budżetu.

### Alternatywne układy
<a id="alternate-layouts" class="xliff"></a>

„Alternatywne układy” to nowa funkcja, która umożliwia wyświetlanie planów w różnych układach. Jako opcje do wyboru można udostępnić jeden lub więcej układów. Wtedy plan budżetu można wyświetlać w układzie miesięcznym lub kwartalnym. Alternatywne układy definiuje się na skróconej karcie **Reguły i układy etapu planowania budżetu** na stronie **Proces planowania budżetu**.

### Punkty kontrolne budżetu
<a id="budget-milestones" class="xliff"></a>

W ramach procesu budżetu konieczna jest znajomość kluczowych dat i terminów. Daty można teraz konfigurować tak, aby miały opisy. Użytkownicy funkcji budżetowania zobaczą te opisy po otwarciu budżetów w celu edytowania lub wyświetlenia przypisanych im elementów i zadań.

### Kopiowanie z alokacji planu budżetu
<a id="copy-from-budget-plan-allocation" class="xliff"></a>

Nowa metoda alokacji umożliwia dystrybucję z planu nadrzędnego do planu podrzędnego bez konieczności przechodzenia przez pośredni poziom w hierarchii. Ta metoda jest szczególnie przydatna dla użytkowników, którzy wcześniej tworzyli wymiary finansowe tylko na potrzeby dystrybucji i zatwierdzania budżetów.

### Generowanie planów budżetu z nowych źródeł budżetu
<a id="generating-budget-plans-from-new-budget-sources" class="xliff"></a>

Następujące opcje zostały dodane jako procesy okresowe. Umożliwiają one generowanie planu budżetu przy użyciu istniejących danych z innego modułu jako punktu wyjściowego:

-   Generuj plan budżetu na podstawie prognozy popytu
-   Generuj plan budżetu na podstawie prognozy dostaw
-   Generuj plan budżetu na podstawie projektu
-   Generuj planu budżetu na podstawie rejestru budżetu

### Bardziej rozbudowane śledzenie kwot
<a id="more-complete-tracking-of-amounts" class="xliff"></a>

W systemie AX 2012 moduł planowania budżetu zawierał jedną kwotę planu przechowywaną dla każdej wartości. W programie Finance and Operations model danych został rozszerzony. Teraz dla każdej wartości są dostępne kwoty w walucie rozliczeniowej, walucie transakcji i walucie raportowania. Podczas uaktualniania te nowe kolumny są wypełniane automatycznie dla istniejących danych.

### Nie konwertuj waluty w agregacji
<a id="do-not-convert-currency-in-aggregation" class="xliff"></a>

Zwykle gdy plan podrzędny jest agregowany do poziomu nadrzędnego, kwoty są automatycznie przeliczane z waluty transakcji na walutę rozliczeniową organizacji. Jeśli w opcji **Nie konwertuj waluty w agregacji** ustawisz wartość **Nie**, zagregowane kwoty pozostają w oryginalnej walucie. W efekcie ta opcja umożliwia dokładniejsze wprowadzanie korekt, na które wpływają wahania kursów wymiany.

### Spoglądanie wstecz od planu budżetu do innych modułów wnoszących wkład do budżetu
<a id="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget" class="xliff"></a>

Plany budżetu mogą być generowane na podstawie prognoz popytu lub podaży, projektów i innych obszarów. Zapytanie Plany budżetu według zestawu wymiarów zawiera kilka opcji, które pozwalają wykonywać zapytania w celu identyfikowania danych będących źródłem planu budżetu.

### Zastępowanie lub dołączanie do planu harmonogramów alokacji
<a id="overwrite-or-append-to-plan-for-allocation-schedules" class="xliff"></a>

Jeśli istnieje wiele źródeł kwot wymagających rozdzielenia (dystrybucji), można określić, że kwoty powinny być addytywne. W takim wypadku nie zastępują one żadnych istniejących kwot. Zamiast tego są dołączane do istniejących kwoty.

### Domyślny zestaw wymiarów finansowych dla konfiguracji planowania budżetu
<a id="default-financial-dimension-set-for-budget-planning-configuration" class="xliff"></a>

Strona **Konfiguracja planowania budżetu** zawiera teraz pole, w którym można określić domyślny zestaw wymiarów finansowych. Mimo że to pole jest opcjonalne, może być wymagane dla niektórych zapytań. Może być również obowiązkowe, jeśli chcesz grupować raporty lub filtrować grupy raportów według zestawów wymiarów.

### Jednostki danych
<a id="data-entities" class="xliff"></a>

Dodano kilka jednostek danych umożliwiających szybkie wdrażanie funkcjonalności planowania budżetu. Jednostki te pozwalają również wprowadzać wiele zmian za pomocą programu Excel. Dzięki temu nie trzeba tworzyć pojedynczo elementów w aplikacji klienckiej. Oto lista nowych jednostek danych:

-   Nazwa podmiotu
-   Parametry budżetu
-   Parametr planu budżetu
-   Scenariusze planu budżetu
-   Etapy planu budżetu
-   Etap przepływu pracy planu budżetu
-   Harmonogramy alokacji planu budżetu
-   Alokacje etapów planu budżetu
-   Priorytety planu budżetu
-   Kolumny planu budżetu
-   Elementy układu planu budżetu





