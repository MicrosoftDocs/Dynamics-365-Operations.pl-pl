---
title: "Organizowanie zasobów projektu"
description: "Ten temat zawiera informacje o organizowaniu zasobów projektu."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2d31a5dfd16a4404e19c6c9693dacecff6f2f064
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="project-resourcing"></a>Organizowanie zasobów projektu

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o organizowaniu zasobów projektu.

Jednym z problemów kierowników projektów i menedżerów zasobów podczas etapu planowania projektu jest alokacja zasobów, gdzie muszą ustalić i zarezerwować właściwe zasoby do pracy nad projektem. W programie Microsoft Dynamics 365 for Finance and Operations funkcje organizowania zasobów projektów umożliwiają zdefiniowanie ról traktowanych jako zasoby tymczasowe, które można zarezerwować dla określonego projektu lub części projektu. Ten rodzaj organizowania zasobów pozwala kierownikom projektów i menedżerom zasobów wykonywać następujące zadania:

- Definiowanie roli posiadającej wymagane kompetencje, aby ułatwić dopasowywanie zasobów.
- Używanie ról do definiowania początkowego harmonogramu projektu opartego na zarezerwowanych zasobach.
- Szacowanie kosztów i określanie początkowego budżetu na podstawie ról i zasobów przypisanych do projektu.
- Używanie ról do szacowania liczby rezerwacji zasobów, które są wymagane dla każdego projektu.
- Szacowanie liczby zasobów, które są wymagane dla całego cyklu życia projektu.
- Projektowanie struktury podziału pracy (SPP) przy użyciu początkowych przypisań zasobów.

[![Cykl życia projektu](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

Wraz z postępami planowania projektu zaplanowane zasoby można zastępować zasobami pracowników. Kierownik projektu może również wrócić i zaktualizować rezerwacje zasobów podczas dowolnego etapu projektu.

## <a name="set-up-project-resources"></a>Konfigurowanie zasobów projektu
Należy utworzyć kalendarz i skojarzyć go z pracownikiem. Kalendarz jest używany do planowania projektu i czasu pracy zasobów, które są zarezerwowane dla projektu. Podczas konfigurowania kalendarza kierownicy projektu wykonują bilansowanie zasobów jako część procesu optymalizacji zasobów. Na podstawie harmonogramu w kalendarzu można nakładać ograniczenia na zasoby. Kalendarz można zdefiniować na stronie **Kalendarze**.

Po skonfigurowaniu pracownika jako zasobu projektu można wybrać spośród pracowników, którzy pracują w firmie, dla której konfigurowane są zasoby. Można także wybrać pracowników z innych firm w organizacji. Ci pracownicy są określani jako zasoby międzyfirmowe.

W poniższych procedurach opisano, jak skonfigurować pracownika jako zasób projektu w swojej firmie i jak skonfigurować międzyfirmowy zasób projektu.

### <a name="set-up-a-worker-as-a-project-resource"></a>Konfigurowanie pracownika jako zasobu projektu

1. Na stronie **Pracownicy** na liście **Pracownicy** wybierz pracownika, którego chcesz dodać jako zasób projektu, i otwórz rekord tego pracownika.
2. W okienku akcji wybierz kolejno opcje **Projekt** &gt; **Ustawienia** &gt; **Ustawienia projektu**.
3. Wybierz kalendarz, a następnie zamknij stronę.

Można również określić domyślne projekty dla zasobu jako rodzaj wstępnego przypisania. Wstępnych przypisań można używać, gdy menedżer zasobów lub kierownik projektu wie z wyprzedzeniem, w których projektach zasób będzie pracował. Wstępne przypisania mogą być również oparte na wniosku inwestora projektu lub klienta. Aby wstępnie przypisać projekt, na stronie **Przypisz projekty** na karcie **Projekty** na liście **Pozostałe projekty** wybierz odpowiedni projekt.

### <a name="set-up-an-intercompany-resource"></a>Konfigurowanie zasobu międzyfirmowego

Podczas konfigurowania pracownika jako zasobu międzyfirmowego należy wypełnić pola konfiguracji w firmach wypożyczającej i pożyczającej.

**W firmie wypożyczającej**

1. W usłudze Finance and Operations upewnij się, że firma wypożyczająca jest wybrana, a następnie wykonaj procedurę z poprzedniej sekcji „Konfigurowanie pracownika jako zasobu projektu”.
2. Na stronie **Księgowanie międzyfirmowe** wybierz opcję **Nowe**.
3. W polu **Identyfikator firmy** wybierz firmę wypożyczającą. Wypełnij pozostałe pola, a następnie wybierz przycisk **Zapisz**.
4. Na stronie **Cena transferowa** wybierz opcję **Nowa**.
5. W polu **Firma pożyczająca** wybierz odpowiednią firmę.
6. Aby wypożyczyć firmie pożyczającej tylko zasób utworzony na początku niniejszej sekcji, w polu **Zasób** zaznacz nazwę utworzonego zasobu. Aby udostępnić firmie pożyczającej wszystkie zasoby firmy wypożyczającej, zostaw pole **Zasób** puste.
7. Na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** na stronie **Międzyfirmowe** ustaw w polu **Włącz międzyfirmowe planowanie zasobów i kart czasu pracy** wartość **Tak**.

**W firmie pożyczającej**

- Na stronie **Lista zasobów**, w filtrze wyszukiwania wprowadź nazwę zasobu, który został utworzony dla firmy wypożyczającej, aby sprawdzić, czy nazwa znajduje się na liście zasobów dla firmy pożyczającej.

## <a name="manage-resource-competencies"></a>Zarządzanie kompetencjami zasobów
Kompetencje zasobów są podstawowym elementem procesu zarządzania zasobami. Kompetencje mogą służyć jako podstawa do identyfikowania zasobów, które mają odpowiednią kombinację umiejętności, wykształcenia, certyfikacji i doświadczenia w projektach. Należy skonfigurować te informacje dla każdego zasobu i aktualizować je na bieżąco. W ten sposób można zmaksymalizować możliwości działania, gdy konkretne kompetencje zasobów są dopasowywane podczas przypisywania zasobów projektu.

[![Przykłady umiejętności, certyfikacji, wykształcenia i doświadczenia w projektach](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

W poniższych procedurach opisano sposób konfigurowania niektórych kompetencji zasobu.

Aby skonfigurować kompetencje pracownika, można użyć strony listy **Pracownicy** w module Zasoby ludzkie lub strony listy **Zasoby** w module Zarządzanie projektami i ich księgowanie. W poniższych procedurach jest używana strona listy **Pracownicy** w module Zasoby ludzkie.

### <a name="set-up-competencies-certificates"></a>Konfigurowanie kompetencji: Certyfikaty

1. Na stronie listy **Pracownicy** wybierz wiersz pracownika, dla którego chcesz dodać informacje o zaświadczeniach.
2. W okienku akcji na karcie **Pracownik** w grupie **Kompetencje** wybierz opcję **Certyfikaty**.
3. Wybierz opcję **Nowy**, a następnie w polu **Typ certyfikatu** wybierz opcję **PMP**.
4. W polu **Data rozpoczęcia** wybierz **1/10/2015**, a następnie wybierz opcję **Zapisz**.

### <a name="set-up-competencies-skills"></a>Konfigurowanie kompetencji: Umiejętności

1. Na stronie listy **Pracownicy** upewnij się, że pracownik użyty w poprzedniej procedurze nadal pozostaje zaznaczony. Następnie w okienku akcji na karcie **Pracownik** w grupie **Kompetencje** wybierz opcję **Umiejętności**.
2. Wybierz **Nowy**.
3. W polu **Umiejętności** zaznacz opcję **Zarządzanie projektami**.
4. W polu **Poziom** zaznacz opcję **5 Ekspert**.
5. W polu **Data poziomu** zaznacz wartość **14.1.2014**.
6. W polu **Lata doświadczenia** wprowadź wartość **10**.
7. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-a-new-project"></a>Utwórz nowy projekt
1. Na stronie **Zarządzanie projektem** wybierz opcję **Nowy projekt** i wprowadź następujące wartości:

    - **Typ projektu:** Czas i materiały
    - **Nazwa projektu:** Uaktualnianie XYZ faza 2
    - **Grupa projektów:** TM\_WIP
    - **Identyfikator umowy dotyczącej projektu:** 00000002

2. Wybierz opcję **Utwórz projekt**.

### <a name="assign-a-resource-to-a-project"></a>Przypisywanie zasobu do projektu

1. Na stronie **Pracownicy** na liście **Pracownicy** wybierz rekord pracownika, dla którego skonfigurowano wcześniej kompetencje, i otwórz ten rekord.
2. W okienku akcji na karcie **Projekt** w grupie **Ustawienia** wybierz opcję **Przypisz projekty**.
3. Na stronie **Przypisania projektu weryfikacji zasobów**, na karcie **Projekty**, w polu **Dodaj projekt do wybranych projektów** odfiltruj projekt **Uaktualnianie XYZ faza 2**.
4. W okienku **Pozostałe projekty** wybierz projekt, a następnie wybierz przycisk strzałki, aby dodać go do okienka **Wybrane projekty**.

Można również przypisać kategorie do zasobu według potrzeb. Typem kategorii jest **Koszt** lub **Przychód**. Typ kategorii jest określany przez organizację. Jeśli zasób nie ma przypisanych żadnych kategorii, program Finance and Operations wyszuka domyślną kategorię cen godzinowych dla kosztów i przychodów.

### <a name="set-up-project-resource-and-role-characteristics"></a>Konfigurowanie cech zasobów i ról w projekcie

Kierownik projektu może za pomocą funkcji organizowania zasobów projektu utworzyć role wymagane w projekcie. Ról można używać, jeżeli potwierdzone zasoby są nadal nieznane podczas rezerwowania zasobów. Role mogą służyć do tymczasowego rezerwowania planowanych zasobów, tak aby można było kontynuować etapy planowania projektu.

[![Przykład roli](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenariusz:** Firma Contoso została wynajęta do wykonania projektu rozliczanego według czasu i materiałów mającego zatwierdzony statut projektu. Młodszy kierownik projektu nadal opracowuje zakres projektu. Menedżer zasobów obecnie identyfikuje konkretne zasoby, które zostaną zarezerwowane do pracy nad nowym projektem. Ze względu na krytyczny charakter projektu jedną z ról wnioskowanych przez sponsora projektu jest starszy kierownik projektu. Menedżer zasobów musi pozyskać nowy zasób oraz zdefiniować rolę w systemie na wypadek, gdyby młodszy kierownik projektu potrzebował informacji o zasobie podczas planowania projektu.

Poniższe kroki pokazują, jak menedżer zasobów może skonfigurować rolę starszego kierownika projektu i skojarzyć z nią cechy zasobu. Później rola może służyć do wyszukiwania dostępnych zasobów posiadających wymagane kompetencje.

1. Na stronie **Konfiguruj role** wybierz opcję **Nowa** i wprowadź następujące wartości:

    - **Identyfikator roli:** Starszy kierownik projektu
    - **Opis:** Starszy kierownik projektu

2. Wybierz opcję **Utwórz**.
3. Wybierz rolę **Starszy kierownik projektu** i wybierz przycisk **Konfiguruj charakterystyki**.
4. W polu **Typ charakterystyki** zaznacz opcję **Umiejętności**.
5. W polu **Dostępne charakterystyki** wprowadź umiejętność, której chcesz poszukać.
6. W polu **Typ charakterystyki** zaznacz opcję **Certyfikat**.
7. W polu **Dostępne charakterystyki** wprowadź typ zaświadczenia, którego chcesz poszukać.

### <a name="assign-a-project-resource-to-a-project"></a>Przypisywanie zasobu projektu do projektu

1. Na stronie **Wszystkie projekty** wybierz projekt **Uaktualnianie XYZ faza 2**.
2. Na karcie **Zespół projektu i planowanie** wybierz przycisk **Dodaj**.
3. W polu **Rola** zaznacz opcję **Członek zespołu**.
4. Wybierz opcję **Rezerwuj z kalendarza**.
5. Na stronie **Dostępność zasobów** wybierz opcję **Ustawienia widoku**.
6. Na stronie **Dostosuj ustawienia widoku** wprowadź następujące wartości:

    - **Format widoku zakresu dat:** Dzień
    - **Wyświetl opisy dostępności:** Tak
    - **Wyświetlanie pozostałych zdolności produkcyjnych:** Tak

7. Na liście zasobów zaznacz zasób.
8. Wybierz opcję **Rezerwacje ostateczne** i **Pełne zdolności produkcyjne**.


### <a name="assign-a-resource-to-a-default-role"></a>Przypisywanie zasobu do roli domyślnej

Aby ułatwić pracę kierownikom projektów lub menedżerom zasobów, można przejść do dokładniejszych ustawień zasobów rezerwowanych dla projektu. Można skojarzyć domyślną rolę z istniejącym zasobem lub nowo pozyskanym zasobem. Na przykład kiedy Daniel był zatrudniany, miał doświadczenie i umiejętności niezbędne do roli analityka biznesowego. Menedżer zasobów przypisał tę rolę jako domyślną rolę Daniela. W związku z tym menedżer zasobów dodał Daniela do puli analityków biznesowych, którzy są dostępni do pracy w projektach.

Podczas rezerwowania zasobów kierownicy projektów mogą filtrować zasoby z rolami dostępne do pracy w projektach. Mogą wykorzystywać te informacje jako jedno z kryteriów wielowątkowej analizy decyzyjnej podczas rozdzielania zasobów. Mogą również dodać inne cechy zasobów do filtra w celu wyszukiwania zasobów, które mają określone umiejętności, wykształcenie i doświadczenie dla danego projektu.

**Scenariusz:** Rozpoczął się zatwierdzony projekt, a na etapie planowania projektu rola starszego kierownika projektu została zarezerwowana jako planowany zasób. Menedżer zasobów pozyskał zasób mogący wypełniać rolę starszego kierownika projektu.

1. Na stronie **Lista zasobów** zaznacz pozycję **Daniel Goldschmidt**.
2. Na stronie **Rola zasobu** wybierz opcję **Nowa** i wprowadź następujące wartości:

    - **Data wprowadzenia:** Wprowadź bieżącą datę.
    - **Data wygaśnięcia:** Wprowadź tekst **Nigdy**.
    - **Rola:** Wprowadź **Starszy kierownik projektu**.

3. Wybierz przycisk **Zapisz** i zamknij stronę.
4. Na karcie **Kompetencje** dodaj umiejętność **ProjectMgmt** i certyfikat **PMP**.

## <a name="set-up-role-based-pricing"></a>Konfigurowanie cen opartych na rolach
Wszystkie koszty, ceny sprzedaży i ceny transferowe można skonfigurować dla ról.

1. Na stronie **Cena sprzedaży — Godzina** wybierz opcję **Nowa** i wprowadź datę wejścia w życie.
2. W kolumnie **Rola** zaznacz rolę.
3. W kolumnie **Ceny** wprowadź cenę dla wybranej roli zasobu.

## <a name="form-a-project-team"></a>Tworzenie zespołu projektu
Aby korzystać z ról, które zostały wcześniej skonfigurowane w projekcie, kierownik projektu musi skojarzyć role z projektem. Do projektu można przypisać wiele ról. Aby uniknąć nieporozumień, rozwiązanie Finance and Operations automatycznie znakuje te role podczas rezerwowania. Na przykład jeśli kierownik projektu potrzebuje trzech inżynierów oprogramowania, następuje automatyczne wygenerowanie trzech ról inżyniera oprogramowania z etykietami **Inżynier oprogramowania 1**, **Inżynier oprogramowania 2** i **Inżynier oprogramowania 3**. Jeśli wcześniej skonfigurowano cechy roli, są one stosowane jako filtr podczas wyszukiwania zasobu. W razie potrzeby mogą być dodawane dodatkowe charakterystyki, aby bardziej zawęzić wyszukiwanie.

Można również dostosować ustawienia widoku, aby lepiej widzieć dostępność zasobów. Istnieją opcje pokazywania dostępności w ujęciu godzinowym, dziennym, tygodniowym, miesięcznym, kwartalnym i rocznym. Dostępna jest także opcja pokazywania dostępnych i pozostałych zdolności produkcyjnych zasobów. Ta opcja jest przydatna dla zarządzania czasem podczas szacowania czasu dostępnego na działania lub czasu dostępności zasobów.

Kierownik projektu może wybrać rolę na stronie, a następnie — jeśli jest dostępny zasób spełniający zapotrzebowanie — zarezerwować zasób w celu wypełnienia roli. Należy zwrócić uwagę, że zasoby nie muszą być rezerwowane w tym momencie na etapie planowania. Podczas tworzenia SPP można zastąpić role zasobami pracowników dla projektu. Jeśli role zostaną zastąpione zasobami pracowników w SPP, konfiguracja zasobów automatycznie aktualizuje schemat i harmonogram zespołu projektu.

[![Schemat zespołu projektu zawierający role i rzeczywiste zasoby](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Kierownik projektu ma różne opcje rezerwowania zasobu dla projektu, takie jak **Pozostałe zdolności produkcyjne**, **Pełne zdolności produkcyjne**, **Procent zdolności produkcyjnych** i **Określ godziny**. Te opcje rezerwacji można anulować w dowolnym momencie w razie zmiany przydziałów zasobów. Obsługiwane są dwa rodzaje rezerwacji:

- **Rezerwacje ostateczne** — rezerwacja zasobu została zatwierdzona i potwierdzona do pracy nad projektem przez określony czas.
- **Rezerwacje wstępne** — rezerwacja zasobu została wstępnie ustawiona do pracy nad projektem przez określony czas.

Poniżej znajduje się procedura wyjaśniająca tworzenie zespołu projektu.

### <a name="create-a-project-team"></a>Tworzenie zespołu projektu

1. Na stronie listy **Wszystkie projekty** zaznacz projekt, a następnie wybierz przycisk **Edytuj**.
2. Na karcie **Zespół projektu i planowanie** w polu **Zaplanuj datę rozpoczęcia** wprowadź datę rozpoczęcia harmonogramu plus jeden miesiąc. Na przykład jeśli datą początkową harmonogramu jest 24 czerwca 2017 r. (24.06.2017), wprowadź **24.07.2017**.
3. Wybierz opcję **Dodaj**.
4. W okienku **Dodaj role do projektu** w polu **Role** wybierz opcję **Starszy kierownik projektu**.
5. Wybierz opcję **Wymagane kompetencje**.
6. Na stronie **Wybierz charakterystyki** są domyślnie zaznaczone cechy, które zostały wcześniej ustawione dla roli Starszy kierownik projektu. Kliknij przycisk **OK**.
7. Na stronie **Dodaj role do projektu** w polu **Liczba zasobów** wprowadź **1**.
8. W polu **Zasób** w wynikach wyszukiwania będą widoczne wszystkie zasoby posiadające wymagane kompetencje. Zaznacz pozycję **Daniel Goldschmidt**, a następnie wybierz przycisk **Utwórz**.
9. Na stronie **Projekt** wybierz przycisk **Dodaj**.
10. W okienku **Dodaj role do projektu** w polu **Role** wybierz opcję **Członek zespołu**. W polu **Liczba zasobów** wpisz **5**.
11. Wybierz opcję **Utwórz**.
12. Na stronie **Projekty** wybierz opcję **Wykorzystaj zasób**.

## <a name="resource-capacity-synchronization"></a>Synchronizacja zdolności produkcyjnych zasobu
Procesy synchronizacji zasobów pomagają zagwarantować, że informacje dotyczące kalendarza i kalendarza podstawowego są przekazywane do czynności planowania zasobów projektu. Jeśli kalendarz zostanie zmieniony, procesy dokonują wymaganych aktualizacji harmonogramów zasobów projektu. Procesy pomagają także zwiększyć wydajność, ponieważ informacje o zasobie kalendarza są synchronizowane z wyprzedzeniem. Dlatego aktualizacje informacji o planowaniu zasobów są dokonywane szybciej. Zaleca się planowanie procesów jako zadanie wsadowe, a nie jednostkowe. W przeciwnym razie istnieje ryzyko, że ktoś może zapomnieć włącznych dat ostatniej synchronizacji. Jeśli nie są używane daty włączne, mogą występować przerwy podczas synchronizacji dat.

![Synchronizacja kalendarza](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Synchronizuj zestawienia zdolności produkcyjnych zasobów

Proces synchronizacji jest zaprojektowany do synchronizowania wszystkich informacji w kalendarzu zasobów. Informacje te obejmują dane kalendarza podstawowego o wszelkich zmianach w tabeli zdolności produkcyjnych kalendarza zasobów projektu. Jeśli w projekcie są dodawane nowe zasoby, synchronizacja pomaga zagwarantować dostępność zaktualizowanych informacji kalendarza. Tę synchronizację można wykonać w dowolnym czasie.

Zaleca się używanie procesu wsadowego. Odpowiednie opcje są dostępne podczas synchronizowania rezerwacji zdolności produkcyjnych.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Okresowe** &gt; **Synchronizacja zdolności produkcyjnych** &gt; **Synchronizuj zestawienia zdolności produkcyjnych zasobów**.
2. Ustaw opcje w następującej tabeli.

    | Opcja      | opis |
    |-------------|-------------|
    | Kod okresu | Opcjonalnie wybierz kod interwału daty księgi głównej w celu ustawienia daty rozpoczęcia i zakończenia procesu synchronizacji zestawień zdolności produkcyjnych zasobów. |
    | Rozpoczęcie  | Wprowadź datę rozpoczęcia procesu synchronizacji zestawienia zdolności produkcyjnych zasobów. |
    | Data zakończenia    | Wprowadź datę zakończenia procesu synchronizacji zestawienia zdolności produkcyjnych zasobów. |

[![Proces synchronizacji](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Konfigurowanie ról w szablonach SPP
Kierownicy projektów mogą skonfigurować szablony SPP, które będą stosować podczas tworzenia SPP dla nowych projektów. Kierownicy projektów mogą dodawać role podczas tworzenia szablonów. Poniższa procedura umożliwia przypisanie roli do szablonu struktury podziału pracy.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Projekty** &gt; **Szablony struktury podziału pracy**.
2. Wybierz przycisk **Szczegóły** obok wybranego szablonu struktury podziału pracy.
3. Wybierz zadanie na liście, a następnie w polu **Rola** wybierz rolę, którą chcesz przypisać do zadania.

### <a name="work-with-a-wbs"></a>Praca z SPP

Można utworzyć nową SPP albo skopiować SPP z istniejącego szablonu struktury podziału pracy. Kierownik projektu może łatwo zarządzać zasobami poprzez przypisywanie ról do nowych zadań w SPP. Role mogą być zastępowane po pozyskaniu zasobu lub po zidentyfikowaniu potwierdzonego zasobu do pracy nad zadaniem. Ta elastyczność umożliwia kierownikom projektów wykonywanie następujących zadań:

- Identyfikacja liczby zasobów wymaganych dla pakietów prac w SPP.
- Szacowanie kosztów projektów.
- Określanie budżetu wstępnego.
- Szacowanie czasu trwania działań na podstawie ról i zasobów.
- Opracowanie pewnych planów zarządzania projektami na podstawie dostępnych informacji o projektach.

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
<td>Automatyczne dodawanie zaplanowanych zasobów przy użyciu ról skojarzonych z zadaniem. Program Finance and Operations automatycznie sugeruje zaplanowane zasoby na podstawie wyników wielowątkowej analizy decyzyjnej opartej na rolach. Po skonfigurowaniu ról i nakładu pracy (w godzinach) dla zadań w SPP i po zwolnieniu struktury wybierz przycisk <strong>Automatycznie generuj zespół</strong>. Wymagana liczba zaplanowanych zasobów zostanie dodana do SPP i karty <strong>Zespół projektu i planowanie</strong>.</td>
</tr>
<tr class="odd">
<td>Zasób (lista rozwijana)</td>
<td>Na stronie <strong>Uruchom formularz przypisania zasobu</strong> można wybrać zasoby do rezerwacji ostatecznych lub wstępnych na podstawie określonego czasu trwania. Można dostosować ustawienia widoku, aby zobaczyć i ustawić czas trwania działań zasobu. Można wybierać i przypisywać zasoby na poziomie pakietu prac za pomocą następujących opcji:
<ul>
<li><strong>Akceptuj</strong> — potwierdzenie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Anuluj</strong> — anulowanie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Przypisz automatycznie</strong> — dostępny zasób pracownika mający pasującą rolę jest automatycznie wybierany i przypisywany do zaznaczonego zadania.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Na stronie **Wszystkie projekty** wybierz projekt **Uaktualnianie XYZ faza 2**.
2. Wybierz kolejno opcje **Plan** &gt; **Działania** &gt; **Struktura podziału pracy**.
3. Wybierz przycisk **Nowy**, aby dodać następujące działania pierwszego poziomu do struktury podziału pracy:

    - Inicjowanie
    - Planowanie
    - W trakcie
    - Monitorowanie i kontrola
    - Zamykanie

4. Ustaw daty i nakład pracy (godziny), jak pokazano na poniższej ilustracji.

    [![Ustawianie dat i nakładu pracy](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Wybierz wiersz zadania **Inicjowanie**, a następnie w polu **Rola** wybierz opcję **Starszy kierownik projektu**.
6. Wybierz opcję **Publikuj**.
7. W tym samym wierszu w polu **Zasoby** zaznacz element **Daniel Goldschmidt**, a następnie wybierz opcję **Akceptuj**.
8. Wybierz wiersz zadania **Planowanie**, a następnie w polu **Rola** wybierz opcję **Analityk biznesowy**.
9. Wybierz kolejno opcje **Publikuj** i **Automatycznie generuj zespół**.
10. W wyświetlonym oknie wiadomości wybierz przycisk **Tak**.
11. W polu **Zasoby** sprawdź, czy wartość to **Analityk biznesowy 1**.
12. Dla zasobu **Analityk biznesowy 1** otwórz wyszukiwanie i wybierz przycisk **Uruchom przypisanie zasobów###**. Następnie wybierz pracownika dla zadania.
13. Wybierz kolejno opcje **Przypisz wstępnie** &gt; **Pełne zdolności produkcyjne**.

    > [!NOTE] 
    > Nie pojawi się ostrzeżenie, że określonym zasobem jest teraz 2, ponieważ liczba zasobów nadal wynosi 1.

14. Na stronie **Struktury podziału pracy** sprawdź poprawność przypisania zasobów w SPP, a następnie wybierz przycisk **Zapisz**.

## <a name="resource-fulfillment-for-planned-resources"></a>Wykorzystanie planowanych zasobów
Kierownik projektu może zaplanować role wymaganych zasobów w projekcie. Menedżer zasobów będzie widział te zaplanowane zasoby jako żądania na stronie **Wykorzystanie zasobu** i może wtedy przypisywać faktyczne zasoby.

1. Na stronie **Wszystkie projekty** wybierz projekt **Uaktualnianie XYZ faza 2**.
2. Wybierz opcję **Projekt**, a następnie opcję **Edytuj**.
3. Na karcie **Zespół projektu i planowanie** wybierz przycisk **Dodaj**.
4. W oknie dialogowym **Dodaj role** wybierz rolę **Programista**.
5. Wybierz przycisk **Utwórz** i zamknij stronę projektu.
6. Na stronie **Wykorzystanie zasobu** wybierz pozycję **Programista 1** dla projektu **Uaktualnianie XYZ faza 2**.
7. Wybierz pracownika, a następnie wybierz przycisk **Przypisz**.
8. Upewnij się, że wiersz **Programista 1** został usunięte dla projektu **Uaktualnianie XYZ faza 2**.
9. Na karcie **Zespół projektu i planowanie** w projekcie **Uaktualnianie XYZ faza 2** upewnij się, że pracownik wybrany w poprzednim kroku został dodany jako **Programista**.

## <a name="requests-for-project-resources"></a>Wnioski o zasoby projektu
Funkcja planowania zasobów projektu tylko pozwala menedżerom zasobów rozdzielać zasoby pracowników w projektach. Aby włączyć tę funkcję, należy wykonać następujące zadania lub upewnić się, że zostały one wykonane:

- Ustaw sekwencje numerów.
- Ustawianie przepływów pracy dla zarządzania projektami i ich księgowania.
- Włącz przepływy pracy żądań zasobów

Po wykonaniu poprzedniego zadania można wykonać następujące zadania według potrzeb:

- Tworzenie wniosku o zasób w odniesieniu do zasobu pracownika z rezerwacją wstępną.
- Monitorowanie wniosków o zasoby.
- Realizacja wniosków o zasoby.
- Wnioskowanie o zasób pracownika z SPP.
- Rezerwowanie zasobów do projektu bez wnioskowania o zasób pracownika.

## <a name="monitor-project-teams"></a>Monitorowanie zespołów projektu
1. Na stronie **Wszystkie projekty** wybierz łącze **Identyfikator projektu** dla projektu **Uaktualnianie XYZ faza 2**.
2. Na skróconej karcie **Zespół projektu i planowanie** sprawdź poprawność wyświetlanych zasobów projektu.

