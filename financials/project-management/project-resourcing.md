---
title: "Organizowanie zasobów projektu"
description: "Ten temat zawiera informacje o organizowaniu zasobów projektu."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a7275e9ad8d655d0d2ee5ba90a792775dec0cf05
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# <a name="project-resourcing"></a>Organizowanie zasobów projektu

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o organizowaniu zasobów projektu.

Jednym z problemów kierowników projektów i menedżerów zasobów podczas etapu planowania projektu jest alokacja zasobów, gdzie muszą ustalić i zarezerwować właściwe zasoby do pracy nad projektem. W programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition funkcje organizowania zasobów projektów umożliwiają zdefiniowanie ról traktowanych jako zasoby tymczasowe, które można zarezerwować dla określonego projektu lub części projektu. Ten rodzaj organizowania zasobów pozwala kierownikom projektów i menedżerom zasobów wykonywać następujące zadania:

-   Definiowanie roli posiadającej wymagane kompetencje, aby ułatwić dopasowywanie zasobów.
-   Używanie ról do definiowania początkowego harmonogramu projektu opartego na zarezerwowanych zasobach.
-   Szacowanie kosztów i określanie początkowego budżetu na podstawie ról i zasobów przypisanych do projektu.
-   Używanie ról do szacowania liczby rezerwacji zasobów, które są wymagane dla każdego projektu.
-   Szacowanie liczby zasobów, które są wymagane dla całego cyklu życia projektu.
-   Projektowanie struktury podziału pracy (SPP) przy użyciu początkowych przypisań zasobów.

[![Cykl życia projektu](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg) 

Wraz z postępami planowania projektu zaplanowane zasoby można zastępować zasobami pracowników. Kierownik projektu może również wrócić i zaktualizować rezerwacje zasobów podczas dowolnego etapu projektu.

## <a name="set-up-project-resources"></a>Konfigurowanie zasobów projektu
Należy utworzyć kalendarz i skojarzyć go z pracownikiem. Kalendarz jest używany do planowania projektu i czasu pracy zasobów, które są zarezerwowane dla projektu. Podczas konfigurowania kalendarza kierownicy projektu mogą wykonywać bilansowanie zasobów jako część procesu optymalizacji zasobów. Na podstawie harmonogramu w kalendarzu można nakładać ograniczenia na zasoby. Kalendarz można zdefiniować na stronie **Kalendarze**. 

Podczas konfigurowania pracownika jako zasobu projektu można wybierać spośród pracowników pracujących w firmie, dla której konfigurujesz zasoby, lub spośród pracowników w innych firmach w organizacji. Są to zasoby międzyfirmowe. W poniższych procedurach opisano, jak skonfigurować pracownika jako zasób projektu w swojej firmie i jak skonfigurować międzyfirmowy zasób projektu.

### <a name="set-up-a-worker-as-a-project-resource"></a>Konfigurowanie pracownika jako zasobu projektu

1.  Na stronie **Pracownicy** na liście **Pracownicy** wybierz pracownika, którego chcesz dodać jako zasób projektu, i otwórz rekord tego pracownika.
2.  W okienku akcji kliknij kolejno opcje **Projekt** &gt; **Ustawienia** &gt; **Ustawienia projektu**.
3.  Wybierz kalendarz, a następnie zamknij stronę.

Można również określić domyślne projekty dla zasobu jako rodzaj wstępnego przypisania. Wstępnych przypisań można używać, gdy menedżer zasobów lub kierownik projektu wie z wyprzedzeniem, w których projektach zasób będzie pracował. Wstępne przypisania mogą być również oparte na wniosku inwestora projektu lub klienta. Aby wstępnie przypisać projekt, na stronie **Przypisz projekty** na karcie **Projekty** na liście **Pozostałe projekty** wybierz odpowiedni projekt.

### <a name="set-up-an-intercompany-resource"></a>Konfigurowanie zasobu międzyfirmowego

Podczas konfigurowania pracownika jako zasobu międzyfirmowego należy wypełnić pola konfiguracji w firmach wypożyczającej i pożyczającej. 

**W firmie wypożyczającej:**

1.  W usłudze Finance and Operations upewnij się, że firma wypożyczająca jest wybrana, a następnie wykonaj opisaną wyżej procedurę „Konfigurowanie pracownika jako zasobu projektu”.
2.  Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia księgowania** &gt; **Księgowanie międzyfirmowe**. Kliknij przycisk **Nowy**.
3.  W polu **Identyfikator firmy** wybierz firmę wypożyczającą. Wypełnij pozostałe pola, a następnie kliknij przycisk **Zapisz**.
4.  Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie **&gt; **Ustawienia **&gt; **Ceny ** &gt; **Cena transferowa**.** **
5.  W formularzu **Cena transferowa** kliknij przycisk **Nowy**, a następnie w polu **Firma pożyczająca** wybierz odpowiednią firmę.
6.  Jeśli chcesz firmie pożyczającej wypożyczyć tylko zasób utworzony na początku niniejszej sekcji, w polu **Zasób** zaznacz nazwę utworzonego zasobu. Jeśli chcesz udostępnić firmie pożyczającej wszystkie zasoby istniejące w firmie, zostaw pole **Zasób** puste.
7.  Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie projektami i ich księgowanie** i na karcie **Międzyfirmowe** ustaw w polu **Włącz międzyfirmowe planowanie zasobów i kart czasu pracy** wartość **Tak**.

**W firmie pożyczającej:**

1.  Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Zasoby projektu** &gt; **Lista zasobów**.
2.  W filtrze wyszukiwania wprowadź nazwę zasobu, który został utworzony w poprzedniej procedurze dla firmy wypożyczającej, aby sprawdzić, czy nazwa znajduje się na liście zasobów dla firmy pożyczającej.

## <a name="manage-resource-competencies"></a>Zarządzanie kompetencjami zasobów
Kompetencje zasobów są podstawowym elementem procesu zarządzania zasobami. Kompetencje mogą służyć jako podstawa do identyfikowania zasobów, które mają odpowiednią kombinację umiejętności, wykształcenia, certyfikacji i doświadczenia w projektach. Należy skonfigurować te informacje dla każdego zasobu i aktualizować je na bieżąco. W ten sposób można zmaksymalizować możliwości działania, gdy konkretne kompetencje zasobów są dopasowywane podczas przypisywania zasobów projektu. [![Przykłady umiejętności, certyfikacji, wykształcenia i doświadczenia w projektach](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg) 

W poniższych procedurach opisano sposób konfigurowania niektórych kompetencji zasobu. 

Aby skonfigurować kompetencje pracownika, można użyć strony listy **Pracownicy** w module Zasoby ludzkie lub strony listy **Zasoby** w module Zarządzanie projektami i ich księgowanie. W poniższych procedurach jest używana strona listy **Pracownicy** w module Zasoby ludzkie.

### <a name="set-up-competencies-certificates"></a>Konfigurowanie kompetencji: Certyfikaty

1.  Na stronie listy **Pracownicy** wybierz wiersz pracownika, dla którego dodajesz informacje o zaświadczeniach.
2.  W okienku akcji na karcie **Pracownik** w grupie **Kompetencje** kliknij opcję **Certyfikaty**.
3.  Kliknij przycisk **Nowy**.
4.  W polu **Typ certyfikatu** zaznacz opcję **PMP**.
5.  W polu **Data rozpoczęcia** zaznacz wartość **1.10.2015**.
6.  Kliknij przycisk **Zapisz** i zamknij stronę.

### <a name="set-up-competencies-skills"></a>Konfigurowanie kompetencji: Umiejętności

1.  Na stronie listy **Pracownicy** upewnij się, że pracownik użyty w poprzedniej procedurze nadal pozostaje zaznaczony. Następnie w okienku akcji na karcie **Pracownik** w grupie **Kompetencje** kliknij opcję **Umiejętności**.
2.  Kliknij przycisk **Nowy**.
3.  W polu **Umiejętności** zaznacz opcję **Zarządzanie projektami**.
4.  W polu **Poziom** zaznacz opcję **5 Ekspert**.
5.  W polu **Data poziomu** zaznacz wartość **14.1.2014**.
6.  W polu **Lata doświadczenia** wprowadź wartość **10**.
7.  Kliknij przycisk **Zapisz** i zamknij stronę.

## <a name="create-a-new-project"></a>Utwórz nowy projekt
1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Obszary robocze** &gt; **Zarządzanie projektami**.
2.  Kliknij przycisk **Nowy projekt** i wprowadź następujące wartości:
    -   **Typ projektu** — Czas i materiały
    -   **Nazwa projektu** — Uaktualnianie XYZ faza 2
    -   **Grupa projektów** — CM\_PWT
    -   **Identyfikator umowy dotyczącej projektu** — 00000002
3.  Kliknij opcję **Utwórz projekt**.

### <a name="assign-a-resource-to-a-project"></a>Przypisywanie zasobu do projektu

1.  Kliknij kolejno opcje **Zasoby ludzkie** &gt; **Pracownicy** &gt; **Pracownicy**.
2.  Na liście **Pracownicy** wybierz rekord pracownika, dla którego skonfigurowano wcześniej kompetencje, i otwórz ten rekord.
3.  W okienku akcji na karcie **Projekt** w grupie **Ustawienia** kliknij opcję **Przypisz projekty**.
4.  Na stronie **Przypisania projektu weryfikacji zasobów** kliknij kartę **Projekty**.
5.  W oknie **Dodaj projekt do wybranych projektów** wyfiltruj według projektu Uaktualnianie XYZ faza 2.
6.  W okienku **Pozostałe projekty** wybierz projekt, a następnie kliknij strzałkę, aby dodać go do okienka **Wybrane projekty**.
7.  Zamknij stronę.

W razie potrzeby można również przypisać kategorie do zasobu. Typem kategorii jest Koszt lub Przychód. To jest określane przez organizację. Jeśli zasób nie ma przypisanych żadnych kategorii, program Finance and Operations będzie szukał domyślnej kategorii cen godzinowych dla kosztów i przychodów.

### <a name="set-up-project-resource-and-role-characteristics"></a>Konfigurowanie cech zasobów i ról w projekcie

Kierownik projektu może za pomocą funkcji organizowania zasobów projektu utworzyć role wymagane w projekcie. Ról można używać, gdy potwierdzone zasoby są nadal nieznane podczas rezerwowania zasobów. Role mogą służyć do tymczasowego rezerwowania planowanych zasobów, tak aby można było kontynuować etapy planowania projektu. 

[![Przykład roli](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenariusz:** Firma Contoso została wynajęta do wykonania projektu rozliczanego według czasu i materiałów mającego zatwierdzony statut projektu. Młodszy kierownik projektu nadal opracowuje zakres projektu. Menedżer zasobów obecnie identyfikuje konkretne zasoby, które zostaną zarezerwowane do pracy nad nowym projektem. Jedną z ról wnioskowanych przez inwestora projektu ze względu na krytyczny charakter projektu jest starszy kierownik projektu. Menedżer zasobów musi pozyskać nowy zasób oraz zdefiniować rolę w systemie na wypadek, gdyby młodszy kierownik projektu potrzebował informacji o zasobie podczas planowania projektu. 

Poniższe kroki pokazują, jak menedżer zasobów może skonfigurować rolę starszego kierownika projektu i skojarzyć z nią cechy zasobu. Później rola może służyć do wyszukiwania dostępnych zasobów posiadających wymagane kompetencje.

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Zasoby** &gt; **Konfiguruj role**.
2.  Kliknij przycisk **Nowy** i wprowadź następujące wartości:
    -   **Identyfikator roli** — Starszy kierownik projektu
    -   **Opis** — Starszy kierownik projektu
3.  Kliknij **Utwórz**.
4.  Wybierz rolę **Starszy kierownik projektu** i kliknij przycisk **Konfiguruj charakterystyki**.
5.  W polu **Typ charakterystyki** zaznacz opcję **Umiejętności**.
6.  W polu **Dostępne charakterystyki** wprowadź umiejętność, której szukasz.
7.  W polu **Typ charakterystyki** zaznacz opcję **Certyfikat**.
8.  W polu **Dostępne charakterystyki** wprowadź typ zaświadczenia, którego chcesz poszukać.
9.  Kliknij przycisk **OK** i zamknij stronę.

### <a name="assign-a-project-resource-to-a-project"></a>Przypisywanie zasobu projektu do projektu

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Wspólne** &gt; **Projekty** &gt; **Wszystkie projekty** i otwórz projekt **Uaktualnianie XYZ faza 2**.
2.  Na karcie **Zespół projektu i planowanie** kliknij przycisk **Dodaj**.
3.  W polu **Rola** zaznacz opcję **Członek zespołu**.
4.  Kliknij opcję **Rezerwuj z kalendarza**.
5.  Na stronie **Dostępność zasobów** kliknij opcję **Ustawienia widoku**.
6.  Na stronie **Dostosuj ustawienia widoku** wprowadź następujące wartości:
    -   **Format widoku zakresu dat** — Dzień
    -   **Wyświetl opisy dostępności** — Tak
    -   **Wyświetlanie pozostałych zdolności produkcyjnych** — Tak
7.  Na liście zasobów zaznacz zasób.
8.  Kliknij kolejno opcje **Rezerwacje ostateczne** &gt; **Pełne zdolności produkcyjne**.
9.  Zamknij stronę.

### <a name="assign-a-resource-to-a-default-role"></a>Przypisywanie zasobu do roli domyślnej

Aby ułatwić pracę kierownikom projektów lub menedżerom zasobów, można przejść do dokładniejszych ustawień zasobów rezerwowanych dla projektu. Można skojarzyć domyślną rolę z istniejącym zasobem lub nowo pozyskanym zasobem. Na przykład kiedy Daniel był zatrudniany, miał doświadczenie i umiejętności niezbędne do roli analityka biznesowego. Menedżer zasobów przypisał tę rolę jako domyślną rolę Daniela. W związku z tym menedżer zasobów dodał Daniela do puli analityków biznesowych, którzy są dostępni do pracy w projektach. 

Podczas rezerwowania zasobów kierownicy projektów mogą filtrować zasoby z rolami dostępne do pracy w projektach. Mogą wykorzystywać te informacje jako jedno z kryteriów wielowątkowej analizy decyzyjnej podczas rozdzielania zasobów. Mogą również dodać inne cechy zasobów do filtra w celu wyszukiwania zasobów, które mają określone umiejętności, wykształcenie i doświadczenie dla danego projektu. 

**Scenariusz:** Rozpoczął się zatwierdzony projekt, a na etapie planowania projektu rola starszego kierownika projektu została zarezerwowana jako planowany zasób. Menedżer zasobów pozyskał zasób mogący wypełniać rolę starszego kierownika projektu.

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Zasoby projektu** &gt; **Lista zasobów**.
2.  Na liście **Zasób** zaznacz pozycję **Daniel Goldschmidt**.
3.  Kliknij kolejno opcje **Zasób projektu** &gt; **Obsługa** &gt; **Rola zasobu**.
4.  Kliknij przycisk **Nowy** i wprowadź następujące wartości:
    -   **Data wprowadzenia** — (bieżąca data)
    -   **Data wygaśnięcia** — Nigdy
    -   **Rola** — Starszy kierownik projektu
5.  Kliknij przycisk **Zapisz** i zamknij stronę.
6.  Na karcie **Kompetencje** dodaj umiejętność **ProjectMgmt** i certyfikat **PMP**.

## <a name="set-up-role-based-pricing"></a>Konfigurowanie cen opartych na rolach
Wszystkie koszty, ceny sprzedaży i ceny transferowe można skonfigurować dla ról.

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Ceny** &gt; **Cena sprzedaży (godzina)**.
2.  Kliknij przycisk **Nowy**.
3.  Wprowadź datę wejścia w życie.
4.  W kolumnie **Rola** zaznacz rolę.
5.  W kolumnie **Ceny** wprowadź cenę dla wybranej roli zasobu.

## <a name="form-a-project-team"></a>Tworzenie zespołu projektu
Aby korzystać z ról, które zostały wcześniej skonfigurowane w projekcie, kierownik projektu musi skojarzyć role z projektem. Można przypisać wiele ról w projekcie, a program Finance and Operations automatycznie znakuje te role podczas rezerwowania w celu uniknięcia nieporozumień. Na przykład jeśli kierownik projektu potrzebuje trzech inżynierów oprogramowania, następuje automatyczne wygenerowanie trzech ról inżyniera oprogramowania z etykietami Inżynier oprogramowania 1, Inżynier oprogramowania 2 i Inżynier oprogramowania 3. Jeśli wcześniej skonfigurowano cechy roli, są one stosowane jako filtr podczas wyszukiwania zasobu. W razie potrzeby mogą być dodawane dodatkowe charakterystyki, aby bardziej zawęzić wyszukiwanie. 

Można również dostosować ustawienia widoku, aby lepiej widzieć dostępność zasobów. Istnieją opcje pokazywania dostępności w ujęciu godzinowym, dziennym, tygodniowym, miesięcznym, kwartalnym i rocznym. Dostępna jest także opcja pokazywania dostępnych i pozostałych zdolności produkcyjnych zasobów. Ta opcja jest przydatna dla zarządzania czasem podczas szacowania czasu dostępnego na działania lub czasu dostępności zasobów. 

Kierownik projektu może wybrać rolę na stronie, a następnie — jeśli jest dostępny zasób spełniający zapotrzebowanie — zarezerwować zasób w celu wypełnienia roli. Należy zwrócić uwagę, że zasoby nie muszą być rezerwowane w tym momencie na etapie planowania. Podczas tworzenia SPP można zastąpić role zasobami pracowników dla projektu. Jeśli role zostaną zastąpione zasobami pracowników w SPP, konfiguracja zasobów automatycznie aktualizuje schemat i harmonogram zespołu projektu. 

[![Schemat zespołu projektu zawierający role i rzeczywiste zasoby](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Kierownik projektu ma różne opcje rezerwowania zasobu dla projektu, takie jak **Pozostałe zdolności produkcyjne**, **Pełne zdolności produkcyjne**, **Procent zdolności produkcyjnych** i **Określ godziny**. Te opcje rezerwacji można anulować w dowolnym momencie w razie zmiany przydziałów zasobów. Obsługiwane są dwa rodzaje rezerwacji:

-   **Rezerwacje ostateczne** — rezerwacja zasobu została zatwierdzona i potwierdzona do pracy nad projektem przez określony czas.
-   **Rezerwacje wstępne** — rezerwacja zasobu została wstępnie ustawiona do pracy nad projektem przez określony czas.

Poniżej znajduje się procedura wyjaśniająca tworzenie zespołu projektu.

### <a name="create-a-project-team"></a>Tworzenie zespołu projektu

1.  Na stronie listy **Wszystkie projekty** zaznacz projekt, a następnie kliknij przycisk **Edytuj**.
2.  Na karcie **Zespół projektu i planowanie** w polu **Zaplanuj datę rozpoczęcia** wprowadź datę rozpoczęcia harmonogramu plus jeden miesiąc. Na przykład jeśli datą początkową harmonogramu jest 24 czerwca 2017 r. (24.06.2017), wprowadź **24.07.2017**.
3.  Kliknij przycisk **Dodaj**.
4.  W okienku **Dodaj role do projektu** w polu **Role** wybierz opcję **Starszy kierownik projektu**.
5.  Kliknij opcję **Wymagane kompetencje**.
6.  Na stronie **Wybierz charakterystyki** są domyślnie zaznaczone cechy, które zostały wcześniej ustawione dla roli Starszy kierownik projektu. Kliknij przycisk **OK**
7.  Na stronie **Dodaj role do projektu** w polu **Liczba zasobów** wprowadź **1**.
8.  W polu **Zasób** w wynikach wyszukiwania będą widoczne wszystkie zasoby posiadające wymagane kompetencje. Zaznacz pozycję **Daniel Goldschmidt**, a następnie kliknij przycisk **Utwórz**.
9.  Na stronie **Projekt** kliknij przycisk **Dodaj**.
10. W okienku **Dodaj role do projektu** w polu **Role** wybierz opcję **Członek zespołu**. W polu **Liczba zasobów** wpisz **5**.
11. Kliknij **Utwórz**.
12. Na stronie **Projekty** kliknij opcję **Wykorzystaj zasób**.

## <a name="resource-capacity-synchronization"></a>Synchronizacja zdolności produkcyjnych zasobu
Procesy synchronizacji zasobów pomagają zagwarantować, że informacje kalendarza i kalendarza podstawowego są przekazywane do czynności planowania zasobów projektu. Jeśli kalendarz zostanie zmieniony, procesy dokonują wymaganych aktualizacji harmonogramów zasobów projektu. Procesy pomagają również zwiększyć wydajność, ponieważ informacje zasobach zawarte w kalendarzach są synchronizowane z wyprzedzeniem, tak aby aktualizacje informacji o zaplanowaniu zasobów były wykonywane szybciej. Zaleca się planowanie procesów jako zadanie wsadowe, a nie jednostkowe. W przeciwnym razie istnieje ryzyko, że ktoś może zapomnieć włącznych dat ostatniej synchronizacji. Jeśli nie są używane daty włączne, mogą występować przerwy podczas synchronizacji dat.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Synchronizacja kalendarza](./media/projectresourcing04-1024x471.jpg)

**Synchronizuj zestawienia zdolności produkcyjnych zasobów**

Proces synchronizacji jest zaprojektowany do synchronizowania wszystkich informacji w kalendarzu zasobów. Informacje te obejmują dane kalendarza podstawowego o wszelkich zmianach w tabeli zdolności produkcyjnych kalendarza zasobów projektu. Jeśli w projekcie są dodawane nowe zasoby, synchronizacja pomaga zapewnić dostępność zaktualizowanych informacji kalendarza. Tę synchronizację można wykonać w dowolnym czasie. 

Zaleca się używanie procesu wsadowego. Odpowiednie opcje są dostępne podczas synchronizowania rezerwacji zdolności produkcyjnych.

-   Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Okresowe** &gt; **Synchronizacja zdolności produkcyjnych** &gt; **Synchronizuj zestawienia zdolności produkcyjnych zasobów**.

| Opcja | opis                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tak    | Synchronizowanie wszystkich danych zasobów z informacjami w kalendarzu i kalendarzu podstawowym oraz zastępowanie wszystkich informacji w kalendarzu zdolności produkcyjnych zasobów w projekcie.                                                  |
| Nie     | Synchronizowanie danych zasobów na podstawie kodu przedziału dat oraz określonych dat rozpoczęcia i zakończenia. Ta opcja nie usuwa istniejących danych, a informacje aktualizuje tylko dla nowo dodanych zasobów. |

[![Proces synchronizacji](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Konfigurowanie ról w szablonach SPP
Kierownicy projektów mogą skonfigurować szablony SPP, które będą stosować podczas tworzenia SPP dla nowych projektów. Kierownicy projektów mogą dodawać role podczas tworzenia szablonów. Poniższa procedura umożliwia przypisanie roli do szablonu struktury podziału pracy.** **

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Projekty** &gt; **Szablony struktury podziału pracy**.
2.  Kliknij przycisk **Szczegóły** obok wybranego szablonu struktury podziału pracy.
3.  Wybierz zadanie na liście, a następnie w polu **Rola** wybierz rolę, którą chcesz przypisać do zadania.

### <a name="work-with-a-wbs"></a>Praca z SPP

Można utworzyć nową SPP albo skopiować SPP z istniejącego szablonu struktury podziału pracy. Kierownik projektu może łatwo zarządzać zasobami poprzez przypisywanie ról do nowych zadań w SPP. Role mogą być zastępowane po pozyskaniu zasobu lub po zidentyfikowaniu potwierdzonego zasobu do pracy nad zadaniem. Ta elastyczność umożliwia kierownikom projektów wykonywanie następujących zadań:

-   Identyfikacja liczby zasobów wymaganych dla pakietów prac w SPP.
-   Szacowanie kosztów projektów.
-   Określanie budżetu wstępnego.
-   Szacowanie czasu trwania działań na podstawie ról i zasobów.
-   Opracowanie pewnych planów zarządzania projektami na podstawie dostępnych informacji o projektach.

W SPP zostały dodane nowe opcje pomagające lepiej wykorzystywać funkcje organizowania zasobów.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opcja</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Przypisania zasobów</td>
<td>Wyświetlanie przydzielonych zasobów, dat, liczby godzin i typu rezerwacji dla zadań w SPP.</td>
</tr>
<tr class="even">
<td>Automatycznie generuj zespół</td>
<td>Automatyczne dodawanie zaplanowanych zasobów przy użyciu ról skojarzonych z zadaniem. Program Finance and Operations automatycznie sugeruje zaplanowane zasoby na podstawie wyników wielowątkowej analizy decyzyjnej opartej na rolach. Po skonfigurowaniu ról i nakładu pracy (w godzinach) dla zadań w SPP i zwolnieniu struktury kliknij przycisk <strong>Automatycznie generuj zespół</strong>. Wymagana liczba zaplanowanych zasobów zostanie dodana do SPP i karty <strong>Zespół projektu i planowanie</strong>.</td>
</tr>
<tr class="odd">
<td>Zasób (lista rozwijana)</td>
<td>Na stronie <strong>Uruchom formularz przypisania zasobu</strong> można wybrać zasoby do rezerwacji ostatecznych lub wstępnych na podstawie określonego czasu trwania. Można dostosować ustawienia widoku, aby zobaczyć i ustawić czas trwania działań zasobu. Można wybierać i przypisywać zasoby na poziomie pakietu prac za pomocą następujących opcji:
<ul>
<li><strong>Akceptuj</strong> — potwierdzenie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Anuluj</strong> — anulowanie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Przypisz automatycznie</strong> — ta opcji powoduje wybranie dostępnego zasobu pracownika z rolą pasującą do zaznaczonego zadania.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  Kliknij kolejno **Zarządzanie projektami i ich księgowanie** &gt; **Projekty** &gt; **Wszystkie projekty**.
2.  Z listy wybierz projekt **Uaktualnianie XYZ faza 2**.
3.  Kliknij kolejno opcje **Plan** &gt; **Działania** &gt; **Struktura podziału pracy**.
4.  Kliknij przycisk **Nowy**, aby dodać następujące działania pierwszego poziomu do struktury podziału pracy:
    -   Inicjowanie
    -   Planowanie
    -   W trakcie
    -   Monitorowanie i kontrola
    -   Zamknij

5.  Ustaw daty i nakład pracy (w godzinach), jak to przedstawiono w poniższym zrzucie ekranu.[![Ustawienie dat i nakładu pracy](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)
6.  Wybierz wiersz zadania **Inicjowanie**, a następnie w polu **Rola** wybierz opcję **Starszy kierownik projektu**.
7.  Kliknij przycisk **Publikuj**.
8.  W tym samym wierszu w polu **Zasoby** zaznacz element **Danielowi Goldschmidt**.
9.  Kliknij przycisk **Akceptuj**.
10. Wybierz wiersz zadania **Planowanie**, a następnie w polu **Rola** wybierz opcję **Analityk biznesowy**.
11. Kliknij kolejno opcje **Publikuj** i **Automatycznie generuj zespół**.
12. W wyświetlonym oknie dialogowym kliknij przycisk **Tak**.
13. W polu **Zasoby** sprawdź, czy wartość to **Analityk biznesowy 1**.
14. Dla zasobu **Analityk biznesowy 1** otwórz wyszukiwanie i kliknij przycisk **Uruchom formularz przypisania zasobów**.
15. Wybierz pracownika dla zadania.
16. Kliknij kolejno opcje **Przypisz wstępnie** &gt; **Pełne zdolności produkcyjne**.
17. Kliknij przycisk **Zapisz** i zamknij stronę. 

> [!NOTE] 
> Nie pojawi się ostrzeżenie, że określonym zasobem jest teraz 2, ponieważ liczba zasobów nadal wynosi 1.
18. Na stronie **Struktury podziału pracy** sprawdź poprawność przypisania zasobów w SPP, a następnie kliknij przycisk **Zapisz**.

## <a name="resource-fulfillment-for-planned-resources"></a>Wykorzystanie planowanych zasobów
Kierownik projektu może zaplanować role wymaganych zasobów w projekcie. Menedżer zasobów będzie widział te zaplanowane zasoby jako żądania na stronie **Wykorzystanie zasobu** i może wtedy przypisywać faktyczne zasoby.

1.  Kliknij kolejno **Zarządzanie projektami i ich księgowanie** &gt; **Projekty** &gt; **Wszystkie projekty**.
2.  Z listy wybierz projekt **Uaktualnianie XYZ faza 2**.
3.  Kliknij opcję **Projekt**.
4.  Kliknij przycisk **Edytuj**.
5.  Na karcie **Zespół projektu i planowanie** kliknij** **przycisk **Dodaj**.
6.  W oknie dialogowym **Dodaj role** wybierz rolę **Programista**.
7.  Kliknij **Utwórz**.
8.  Zamknij stronę projektu.
9.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Zasoby projektu** &gt; **Wykorzystanie zasobu**.
10. Dla projektu **Uaktualnianie XYZ faza 2** wybierz zasób **Programista 1**.
11. Wybierz pracownika, a następnie kliknij przycisk **Przypisz**.
12. Upewnij się, że wiersz **Programista 1** został usunięte dla projektu **Uaktualnianie XYZ faza 2**.
13. Na karcie **Zespół projektu i planowanie** w projekcie **Uaktualnianie XYZ faza 2** upewnij się, że pracownik wybrany w kroku 11 został dodany jako **Programista**.

## <a name="requests-for-project-resources"></a>Wnioski o zasoby projektu
Funkcja planowania zasobów projektu tylko pomaga menedżerom zasobów rozdzielać zasoby pracowników w projektach. Aby włączyć tę funkcję, należy wykonać następujące zadania lub upewnić się, że zostały one wykonane.

-   Ustaw sekwencje numerów.
-   Ustawianie przepływów pracy dla zarządzania projektami i ich księgowania.
-   Włączanie przepływu pracy żądań zasobów.

Po zweryfikowaniu wykonania lub wykonaniu powyższych zadań można stosownie do potrzeb wykonać następujące zadania.

-   Tworzenie wniosku o zasób w odniesieniu do zasobu pracownika z rezerwacją wstępną.
-   Monitorowanie wniosków o zasoby.
-   Realizacja wniosków o zasoby.
-   Wnioskowanie o zasób pracownika z SPP.
-   Rezerwowanie zasobów do projektu bez wnioskowania o zasób pracownika.

## <a name="monitor-project-teams"></a>Monitorowanie zespołów projektu
1.  Kliknij kolejno **Zarządzanie projektami i ich księgowanie** &gt; **Projekty** &gt; **Wszystkie projekty**.
2.  Kliknij na liście projektów kliknij łącze **Identyfikator projektu** dla projektu **Uaktualnianie XYZ faza 2**.
3.  Na skróconej karcie **Zespół projektu i planowanie** sprawdź poprawność wyświetlanych zasobów projektu.





