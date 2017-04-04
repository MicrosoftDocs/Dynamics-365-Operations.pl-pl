---
title: "Organizowanie zasobów projektu"
description: "Ten temat zawiera informacje o finansowanie projektów."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Organizowanie zasobów projektu

Ten temat zawiera informacje o finansowanie projektów.

Jednym z wyzwań dla menedżerowie projektów i menedżerowie zasobów podczas etapu planowania projektu jest alokacja zasobów, gdzie należy ustalić i zarezerwować prawidłowego zasobu do pracy nad projektem. W programie Microsoft Dynamics 365 dla operacji zwiększenia możliwości dla projektów umożliwiają definiowanie ról, które są traktowane jako tymczasowe zasoby, które mogą być zarezerwowane dla konkretnego zaangażowania lub część o naszych zaręczynach. Ten rodzaj organizowania zasobów pozwala kierownikom projektów i menedżerom zasobów wykonywać następujące zadania:

-   Definiowanie roli posiadającej wymagane kompetencje, aby ułatwić dopasowywanie zasobów.
-   Role służy do definiowania początkowego zaangażowania harmonogram, który jest oparty na zarezerwowanych zasobów.
-   Szacowanie kosztów i określanie początkowego budżetu na podstawie ról i zasobów przypisanych do projektu.
-   Ról należy używać, aby oszacować liczbę rezerwacji zasobów, które są wymagane dla każdego zaangażowania.
-   Szacowanie liczby zasobów, które są wymagane dla całego cyklu życia projektu.
-   Projektowanie struktury podziału pracy (SPP) przy użyciu początkowych przypisań zasobów.

[![Cyklu życia projektu](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg) 

Jako przychody planowania projektu planowanych zasobów może być zastąpiony przez zasoby. Menedżer projektu można wrócić i służy do aktualizowania rezerwacji odpowiednich zasobów podczas żadnego z etapów projektu.

## <a name="set-up-project-resources"></a>Konfigurowanie zasobów projektu
Należy utworzyć kalendarz i skojarzyć go z pracownikiem. Kalendarz jest używany do planowania projektu i czasu pracy zasobów, które obecnie są zarezerwowane dla projektu. Podczas konfigurowania kalendarza kierownicy projektu mogą wykonywać bilansowanie zasobów jako część procesu optymalizacji zasobów. Na podstawie harmonogramu w kalendarzu można nakładać ograniczenia na zasoby. Można zdefiniować kalendarz na **kalendarze** strony. 

Po skonfigurowaniu pracownika jako zasób projektu można wybrać z pracowników, które pracuje w firmie, dla którego konfigurujesz zasobów lub wybrać pracowników z innych firm w obrębie organizacji. Są to zasoby międzyfirmowego. W poniższych procedurach opisano, jak skonfigurować pracownika jako zasób projektu w firmie i jak skonfigurować zasób projektu międzyfirmowego.

### <a name="set-up-a-worker-as-a-project-resource"></a>Konfigurowanie pracownika jako zasobu projektu

1.  Na **pracowników** strona w **pracowników** listy, wybierz pracownika, który dodajesz jako zasób projektu i otwórz rekord pracownika.
2.  W okienku akcji kliknij polecenie **projekt**&gt;**instalacji**&gt;**ustawienia projektu**.
3.  Wybierz kalendarz, a następnie zamknij stronę.

Można również określić domyślne projekty dla zasobu jako rodzaj wstępnego przypisania. Wstępnych przypisań można używać, gdy menedżer zasobów lub kierownik projektu wie z wyprzedzeniem, w których projektach zasób będzie pracował. Wstępne przypisania mogą być również oparte na wniosku inwestora projektu lub klienta. Aby wstępnie przypisać projekt, na stronie **Przypisz projekty** na karcie **Projekty** na liście **Pozostałe projekty** wybierz odpowiedni projekt.

### <a name="set-up-an-intercompany-resource"></a>Konfigurowanie zasobów międzyfirmowych

Po skonfigurowaniu pracownika jako zasobów międzyfirmowych, należy wypełnić pola konfiguracji w pożyczek firma i firma finansowania zewnętrznego. 

**W firmie pożyczek:**

1.  W usłudze Dynamics 365 dla operacji Sprawdź, czy firma pożyczek jest zaznaczone i następnie wykonaj procedurę powyżej, "Ustaw pracownika jako zasób projektu".
2.  Przejdź do ** księgi głównej **&gt; ** ustawienia księgowania **&gt;**księgowania międzyfirmowego**. Click **New**.
3.  W ** identyfikator podmiotu prawnego ** wybierz firma pożyczek. Wypełnij pozostałe pola, a następnie kliknij przycisk **zapisać**.
4.  Przejdź ** zarządzania projektami i księgowości **&gt; ** Instalator **&gt;**ceny ** &gt;**cenę transferową**.** **
5.  Na wytwarzanie cenę transferową ** formularza, kliknij przycisk **nowy**i w ** pożyczającego podmiotu prawnego ** wybierz odpowiednią firmę.
6.  Jeśli chcesz tylko pożyczki firmy finansowania zewnętrznego zasobu, który został utworzony na początku niniejszej sekcji w **zasobów** wybierz nazwę zasobu, który został utworzony. Jeśli chcesz udostępnić wszystkie zasoby w firmie do zaciągania firmy, zostawić ** zasobu ** pole puste.
7.  Przejdź do ** zarządzania projektami i księgowości **&gt; ** Instalator **&gt;**Zarządzanie projektami i ich księgowanie parametry**i na wytwarzanie międzyfirmowe ** Ustaw ** Włącz międzyfirmowe planowanie zasobów i kart czasu pracy ** pola do **tak**.

**W firmie finansowania zewnętrznego:**

1.  Przejdź do **zarządzania projektami i księgowości**&gt;**zasoby projektu**&gt;**Lista zasobów**.
2.  W filtrze wyszukiwania wprowadź nazwę zasobu, który został utworzony w poprzedniej procedurze dla pożyczek firmy zweryfikować, że nazwa znajduje się na liście zasobów firmy finansowania zewnętrznego.

## <a name="manage-resource-competencies"></a>Zarządzanie kompetencjami zasobów
Kompetencje zasobu są istotnym elementem zarządzania zasobami. Kompetencje mogą służyć jako podstawa do identyfikowania zasobów, które mają odpowiednią kombinację umiejętności, wykształcenia, certyfikacji i doświadczenia w projektach. Należy skonfigurować te informacje dla każdego zasobu i aktualizować je na bieżąco. W ten sposób można zmaksymalizować możliwości działania, gdy konkretne kompetencje zasobów są dopasowywane podczas przypisywania zasobów projektu. [![Przykładem umiejętności, certyfikatów, edukacji oraz doświadczenie w projekcie](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg) 

W poniższych procedurach opisano sposób konfigurowania niektórych kompetencji zasobu. 

Aby skonfigurować kompetencje pracownika, można użyć strony listy **Pracownicy** w module Zasoby ludzkie lub strony listy **Zasoby** w module Zarządzanie projektami i ich księgowanie. Dla poniższych procedur **pracowników** używane strony listy w zasobach ludzkich.

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
1.  Kliknij **zarządzania projektami i księgowości**&gt;**obszary robocze**&gt;**zarządzania projektami**.
2.  Kliknij przycisk **Nowy projekt** i wprowadź następujące wartości:
    -   **Typ projektu** - typu czas i materiały
    -   **Nazwa projektu** -XYZ uaktualnić Phase 2
    -   **Grupa projektów** -TM\_PWT
    -   **Identyfikator kontraktu projektu** -00000002
3.  Kliknij opcję **Utwórz projekt**.

### <a name="assign-a-resource-to-a-project"></a>Przypisywanie zasobu do projektu

1.  Kliknij **zasoby ludzkie**&gt;**pracowników**&gt;**pracowników**.
2.  Na liście **Pracownicy** wybierz rekord pracownika, dla którego skonfigurowano wcześniej kompetencje, i otwórz ten rekord.
3.  W okienku akcji na karcie **Projekt** w grupie **Ustawienia** kliknij opcję **Przypisz projekty**.
4.  Na stronie **Przypisania projektu weryfikacji zasobów** kliknij kartę **Projekty**.
5.  W **dodać projekt do wybranych projektów**, filtr w projekcie XYZ uaktualnić Phase 2
6.  W okienku **Pozostałe projekty** wybierz projekt, a następnie kliknij strzałkę, aby dodać go do okienka **Wybrane projekty**.
7.  Zamknij stronę.

W razie potrzeby można również przypisać kategorie do zasobu. Typem kategorii jest Koszt lub Przychód. To jest określane przez organizację. Jeśli nie ma przypisane kategorie dla zasobu, Dynamics 365 dla operacji będzie wyszukiwać domyślnej kategorii godzinowych cen kosztów i przychodów.

### <a name="set-up-project-resource-and-role-characteristics"></a>Konfigurowanie cech zasobów i ról w projekcie

Kierownik projektu może za pomocą funkcji organizowania zasobów projektu utworzyć role wymagane w projekcie. Role mogą być używane, gdy potwierdzone zasoby nie są jeszcze znane, podczas rezerwowania zasobów. Role mogą być tymczasowo zarezerwowane jako planowane zasoby, tak, aby można było kontynuować etapy planowania projektu. 

[![Przykład roli](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenariusz:** Firma Contoso została wynajęta do wykonania projektu rozliczanego według czasu i materiałów mającego zatwierdzony statut projektu. Młodszy kierownik projektu nadal opracowuje zakres projektu. Menedżer zasobów jest obecnie identyfikacji określonych zasobów, które będą przeznaczone do pracy nad nowym projektem. Jedną z ról, które wniosek sponsora projektu, z powodu charakteru projektu, jest menedżerem wyższego szczebla projektu. Menedżer zasobów musi nabyć nowy zasób i definiują rolę w systemie, w przypadku gdy Menedżer projektu młodszych wymaga informacji o zasobie podczas planowania projektu. 

Poniższe kroki pokazują jak Menedżer zasobów można skonfigurować roli menedżera projektu wyższego szczebla i skojarzyć z nią właściwości zasobu. Później rola może służyć do wyszukiwania dostępnych zasobów posiadających wymagane kompetencje.

1.  Kliknij **zarządzania projektami i księgowości**&gt;**instalacji**&gt;**zasobów**&gt;**ustawienia ról**.
2.  Kliknij przycisk **Nowy** i wprowadź następujące wartości:
    -   **Identyfikator roli** -starszy Kierownik projektu
    -   **Opis** -starszy Kierownik projektu
3.  Kliknij **Utwórz**.
4.  Wybierz rolę **Starszy kierownik projektu** i kliknij przycisk **Konfiguruj charakterystyki**.
5.  W polu **Typ charakterystyki** zaznacz opcję **Umiejętności**.
6.  W polu **Dostępne charakterystyki** wprowadź umiejętność, której szukasz.
7.  W polu **Typ charakterystyki** zaznacz opcję **Certyfikat**.
8.  W polu **Dostępne charakterystyki** wprowadź typ zaświadczenia, którego chcesz poszukać.
9.  Kliknij przycisk **OK** i zamknij stronę.

### <a name="assign-a-project-resource-to-a-project"></a>Przypisywanie zasobu projektu do projektu

1.  Kliknij **zarządzania projektami i księgowości**&gt;**wspólne**&gt;**projekty**&gt;**wszystkie projekty**i otworzyć **XYZ uaktualnić Phase 2** projektu.
2.  Na karcie **Zespół projektu i planowanie** kliknij przycisk **Dodaj**.
3.  W polu **Rola** zaznacz opcję **Członek zespołu**.
4.  Kliknij opcję **Rezerwuj z kalendarza**.
5.  Na stronie **Dostępność zasobów** kliknij opcję **Ustawienia widoku**.
6.  Na stronie **Dostosuj ustawienia widoku** wprowadź następujące wartości:
    -   **Format dla zakresu dat, widok** - dzienny
    -   **Wyświetlić opisy dostępności** - tak
    -   **Wyświetl pozostałą pojemność** - tak
7.  Na liście zasobów zaznacz zasób.
8.  Kliknij **twardy książki**&gt;**pełna pojemność**.
9.  Zamknij stronę.

### <a name="assign-a-resource-to-a-default-role"></a>Przypisywanie zasobu do roli domyślnej

Aby pomóc menedżerom projektu lub zasobów, można drążyć dalej na zasoby, które mogą być zarezerwowane dla projektu. Można skojarzyć domyślną rolę z istniejącym zasobem lub nowo pozyskanym zasobem. Na przykład gdy Daniel został zatrudniony, miał doświadczenia i umiejętności, aby pełnił rolę analityków biznesowych. Menedżer zasobów przypisani do tej roli jako rola domyślna Daniel. W związku z tym Menedżer zasobów dodane Daniel do puli analityków biznesowych, którzy są dostępne do pracy nad projektami. 

Podczas rezerwacji zasobów menedżerowie projektów można filtrować zasoby roli, które są dostępne do pracy nad projektami. Mogą wykorzystywać te informacje jako jedno z kryteriów wielowątkowej analizy decyzyjnej podczas rozdzielania zasobów. Mogą również dodać inne cechy zasobów do filtra w celu wyszukiwania zasobów, które mają określone umiejętności, wykształcenie i doświadczenie dla danego projektu. 

**Scenariusz:** zatwierdzonego projektu została uruchomiona i roli menedżera projektu starszy został zarezerwowany jako zasób planowanych podczas etapu planowania projektu. Menedżer zasobów pozyskał zasób mogący wypełniać rolę starszego kierownika projektu.

1.  Kliknij **zarządzania projektami i księgowości**&gt;**zasoby projektu**&gt;**Lista zasobów**.
2.  Na liście **Zasób** zaznacz pozycję **Daniel Goldschmidt**.
3.  Kliknij **zasobów serwera Project**&gt;**Zachowaj**&gt;**rolę zasobu**.
4.  Kliknij przycisk **Nowy** i wprowadź następujące wartości:
    -   **Skuteczne** - (data bieżąca)
    -   **Wygaśnięcia** - nigdy nie
    -   **Rolę** -starszy Kierownik projektu
5.  Kliknij przycisk **Zapisz** i zamknij stronę.
6.  Na karcie **Kompetencje** dodaj umiejętność **ProjectMgmt** i certyfikat **PMP**.

## <a name="set-up-role-based-pricing"></a>Konfigurowanie cen opartych na rolach
Wszystkie koszty, ceny sprzedaży i ceny transferowe można skonfigurować dla ról.

1.  Kliknij **zarządzania projektami i księgowości**&gt;**instalacji**&gt;**ceny**&gt;**cena sprzedaży (godzina)**.
2.  Click **New**.
3.  Wprowadź datę wejścia w życie.
4.  W kolumnie **Rola** zaznacz rolę.
5.  W kolumnie **Ceny** wprowadź cenę dla wybranej roli zasobu.

## <a name="form-a-project-team"></a>Formularz zespołu projektu
Aby użyć ról, które zostały wcześniej utworzone w projekcie, Menedżer projektu należy skojarzyć ról z projektem. Wiele ról mogą być przypisane do projektu, a 365 Dynamics dla operacji automatycznie etykiety skojarzone z tymi rolami podczas rezerwacji, aby uniknąć zamieszania. Na przykład jeśli Menedżer projektu wymaga trzech inżynierów oprogramowania, trzech ról inżynier oprogramowania, które programista 1, inżynier oprogramowania 2 i 3 jako ich etykiety inżynier oprogramowania są generowane automatycznie. Jeśli wcześniej skonfigurowano cechy roli, są one stosowane jako filtr podczas wyszukiwania zasobu. W razie potrzeby mogą być dodawane dodatkowe charakterystyki, aby bardziej zawęzić wyszukiwanie. 

Można również dostosować ustawienia widoku, aby lepiej widzieć dostępność zasobów. Istnieją opcje pokazywania dostępności w ujęciu godzinowym, dziennym, tygodniowym, miesięcznym, kwartalnym i rocznym. Dostępna jest także opcja pokazywania dostępnych i pozostałych zdolności produkcyjnych zasobów. Ta opcja jest przydatna dla zarządzania czasem podczas szacowania czasu dostępnego na działania lub czasu dostępności zasobów. 

Menedżer projektu można wybrać rolę na stronie i następnie wybierz jeśli ma dostępnych zasobów, który pasuje do wymogu, aby zarezerwować jakieś zasoby, aby pełnił rolę. Należy zwrócić uwagę, że zasoby nie muszą być zarezerwowane w tym momencie w fazie planowania. Po utworzeniu WBS ról można zastąpić obsługą zasobów dla projektu. Role są zastąpione przez zasoby w SPP, ustawienia zasobów automatycznie aktualizuje zespołu projektu aukcji i planowania. 

[![Liście zespołu projektu, zawierającym zarówno role i rzeczywistych zasobów](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Kierownik projektu ma różne opcje rezerwowania zasobu dla projektu, takie jak **Pozostałe zdolności produkcyjne**, **Pełne zdolności produkcyjne**, **Procent zdolności produkcyjnych** i **Określ godziny**. Te opcje rezerwacji można anulować w dowolnym momencie w razie zmiany przydziałów zasobów. Obsługiwane są dwa rodzaje rezerwacji:

-   **Ostatecznie zarezerwować** – rezerwacji zasobów została zatwierdzona i potwierdzone do pracy na zatrudnienie na czas określony.
-   **Miękkie książki** – rezerwacji zasobów został wstępnie ustawić do pracy na zatrudnienie na czas określony.

Poniżej znajduje się procedura wyjaśniająca tworzenie zespołu projektu.

### <a name="create-a-project-team"></a>Tworzenie zespołu projektu

1.  Na stronie listy **Wszystkie projekty** zaznacz projekt, a następnie kliknij przycisk **Edytuj**.
2.  Na **zespołu i planowania projektu** kartę w **Data zakończenia harmonogramu** wprowadź datę rozpoczęcia harmonogramu plus jeden miesiąc. Na przykład, jeśli data rozpoczęcia harmonogramu jest 24 czerwca 2017 (24-06-2017), wprowadź **24-07-2017**.
3.  Click **Add**.
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

**Synchronize resource capacity roll-ups**

Proces synchronizacji jest zaprojektowany do synchronizowania wszystkich informacji w kalendarzu zasobów. Informacje te obejmują dane kalendarza podstawowego o wszelkich zmianach w tabeli zdolności produkcyjnych kalendarza zasobów projektu. Jeśli w projekcie są dodawane nowe zasoby, synchronizacji pomaga zapewnić, że dostępne są informacje kalendarza zaktualizowane. Tę synchronizację można wykonać w dowolnym czasie. 

Zaleca się używanie procesu wsadowego. Odpowiednie opcje są dostępne podczas synchronizowania rezerwacji zdolności produkcyjnych.

-   Kliknij **zarządzania projektami i księgowości**&gt;**okresowo**&gt;**synchronizacji zdolności**&gt;**synchronizowanie rzutowania pojemności zasobów**.

| Opcja | opis                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tak    | Synchronizowanie wszystkich danych zasobów z informacjami w kalendarzu i kalendarzu podstawowym oraz zastępowanie wszystkich informacji w kalendarzu zdolności produkcyjnych zasobów w projekcie.                                                  |
| Nie     | Synchronizowanie danych zasobów na podstawie kodu przedziału dat oraz określonych dat rozpoczęcia i zakończenia. Ta opcja nie usuwa istniejących danych, a informacje aktualizuje tylko dla nowo dodanych zasobów. |

[![Proces synchronizacji](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Konfigurowanie ról w szablonach SPP
Kierownicy projektów mogą skonfigurować szablony SPP, które będą stosować podczas tworzenia SPP dla nowych projektów. Menedżerowie projektów mogą dodawać role, podczas tworzenia szablonu. Poniższa procedura umożliwia przypisywanie roli do template.* spp * **

1.  Kliknij **zarządzania projektami i księgowości**&gt;**instalacji**&gt;**projekty**&gt;**Szablony struktury podziału pracy**.
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
<td>Automatyczne dodawanie zaplanowanych zasobów przy użyciu ról skojarzonych z zadaniem. Dynamics 365 dla operacji automatycznie sugeruje planowanych zasobów za pomocą analizy decyzji wiele kryteriów, który jest oparty na rolach. Po skonfigurowaniu ról i nakładu pracy (w godzinach) dla zadań w SPP i zwolnieniu struktury kliknij przycisk <strong>Automatycznie generuj zespół</strong>. Wymagana liczba zaplanowanych zasobów zostanie dodana do SPP i karty <strong>Zespół projektu i planowanie</strong>.</td>
</tr>
<tr class="odd">
<td>Zasób (lista rozwijana)</td>
<td>Na stronie <strong>Uruchom formularz przypisania zasobu</strong> można wybrać zasoby do rezerwacji ostatecznych lub wstępnych na podstawie określonego czasu trwania. Można dostosować ustawienia widoku, aby zobaczyć i ustawić czas trwania działań zasobu. Można wybierać i przypisywać zasoby na poziomie pakietu prac za pomocą następujących opcji:
<ul>
<li><strong>Akceptuj</strong> — potwierdzenie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Anuluj</strong> — anulowanie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Przypisz automatycznie</strong> – w tej opcji wybiera dostępnych zasobów obsadzone z pasującą rolę do zaznaczonego zadania.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  Kliknij **zarządzania projektami i księgowości**&gt;**projekty**&gt;**wszystkie projekty**.
2.  Z listy wybierz projekt **Uaktualnianie XYZ faza 2**.
3.  Kliknij **Plan**&gt;**działalność**&gt;**struktury podziału pracy**.
4.  Kliknij przycisk **Nowy**, aby dodać następujące działania pierwszego poziomu do struktury podziału pracy:
    -   Inicjowanie
    -   Planowanie
    -   W trakcie
    -   Monitorowanie i kontrola
    -   Zamknij

5.  Ustawianie daty i wysiłku zrzut ekranu (godzin), jak pokazano poniżej. [![Ustawienie daty i nakładu](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)
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
16. Kliknij **Przypisz miękkie**&gt;**pełna pojemność**.
17. Kliknij przycisk **Zapisz** i zamknij stronę. 

> [!NOTE] 
> Nie otrzymasz ostrzeżenie, że określony zasób jest teraz 2, ponieważ liczba zasobów pozostaje na 1.
18. Na stronie **Struktury podziału pracy** sprawdź poprawność przypisania zasobów w SPP, a następnie kliknij przycisk **Zapisz**.

## <a name="resource-fulfillment-for-planned-resources"></a>Wykorzystanie planowanych zasobów
Kierownik projektu może zaplanować role wymaganych zasobów w projekcie. Menedżer zasobów będzie widział te zaplanowane zasoby jako żądania na stronie **Wykorzystanie zasobu** i może wtedy przypisywać faktyczne zasoby.

1.  Kliknij **zarządzania projektami i księgowości**&gt;**projekty**&gt;**wszystkie projekty**.
2.  Z listy wybierz projekt **Uaktualnianie XYZ faza 2**.
3.  Kliknij opcję **Projekt**.
4.  Kliknij przycisk **Edytuj**.
5.  Na **zespołu i planowania projektu** kartę, ** ** kliknij **Dodaj**.
6.  W oknie dialogowym **Dodaj role** wybierz rolę **Programista**.
7.  Kliknij **Utwórz**.
8.  Zamknij stronę projektu.
9.  Kliknij **zarządzania projektami i księgowości**&gt;**zasoby projektu**&gt;**realizacji zasobów**.
10. Dla projektu **Uaktualnianie XYZ faza 2** wybierz zasób **Programista 1**.
11. Wybierz pracownika, a następnie kliknij przycisk **Przypisz**.
12. Upewnij się, że wiersz **Programista 1** został usunięte dla projektu **Uaktualnianie XYZ faza 2**.
13. Na karcie **Zespół projektu i planowanie** w projekcie **Uaktualnianie XYZ faza 2** upewnij się, że pracownik wybrany w kroku 11 został dodany jako **Programista**.

## <a name="requests-for-project-resources"></a>Żądania dotyczące zasobów projektu
Z funkcji planowania zasobów projektu obsługuje tylko menedżerowie zasobów do dystrybucji zasobów obsadzone na zobowiązania lub projektów. Aby włączyć tę funkcję, należy wykonać następujące zadania lub upewnij się, że zostały one zakończone.

-   Ustaw sekwencje numerów.
-   Ustawianie zarządzania projektami i przepływów pracy rozliczania.
-   Włączanie zasobów przepływ pracy dla wniosku.

Po zostały zweryfikowane lub wykonane zadania powyżej, można wykonać następujące zadania, stosownie do potrzeb.

-   Utwórz żądanie zasobu z obsługą zasobu rezerwacji wstępnej.
-   Monitor zasobów żądania.
-   Spełnić żądania zasobów.
-   Żądania zasobu obsadzone od spp.
-   Rezerwowanie zasobów do projektu bez żądania obsadzone zasobów.

## <a name="monitor-project-teams"></a>Zespoły projektów monitora
1.  Kliknij **zarządzania projektami i księgowości**&gt;**projekty**&gt;**wszystkie projekty**.
2.  Kliknij na liście projektów kliknij łącze **Identyfikator projektu** dla projektu **Uaktualnianie XYZ faza 2**.
3.  Na skróconej karcie **Zespół projektu i planowanie** sprawdź poprawność wyświetlanych zasobów projektu.



