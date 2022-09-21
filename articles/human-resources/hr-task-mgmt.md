---
title: Zarządzanie zadaniami
description: W tym artykule wyjaśniono funkcje zarządzania zadaniami, które są dostępne w Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 29b547ff4f55b572ab774e7e70949ec8cb53ef42
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445902"
---
# <a name="task-management"></a>Zarządzanie zadaniami

[!INCLUDE [PEAP](../includes/peap-1.md)]

Zarządzanie zadaniami pozwala ci tworzyć zadania, które muszą być wykonane, aby zatrudnić (onboard), zakończyć (offboard) i przenieść (transition) pracowników. Zarządzanie zadaniami wykorzystuje koncepcję list kontrolnych. Lista kontrolna to lista zadań do wykonania w trakcie onboardingu, offboardingu lub przejścia. Zarządzanie zadaniami wykorzystuje listy kontrolne do grupowania zadań i przypisywania ich osobom lub grupom. Funkcjonalność list kontrolnych dla onboardingu, offboardingu i przejść jest podobna.

## <a name="checklist-overview"></a>Przegląd list kontrolnych

Lista kontrolna to grupa zadań. Listy kontrolne dają ci elastyczny sposób grupowania zadań i mogą być ponownie wykorzystane (na przykład, gdy zatrudniasz kolejnych pracowników). Możesz stworzyć tyle list kontrolnych, ile potrzebujesz, i możesz przypisać te same zadania do wielu list kontrolnych.

### <a name="examples"></a>Przykłady

Poniższe przykłady pokazują, jak listy kontrolne mogą być wykorzystane w procesie onboardingu. Ponieważ jednak funkcjonalność list kontrolnych dla onboardingu, offboardingu i przejścia jest podobna, informacje te odnoszą się także do procesów offboardingu i przejścia.

W ramach procesu onboardingu specjaliści ds. zasobów ludzkich (HR) mogą tworzyć zadania, które będą śledzić postępy w onboardingu nowych i niedawno zatrudnionych pracowników. Ponieważ proces wprowadzania pracownika na stanowisko może się różnić w zależności od jego stanowiska lub lokalizacji geograficznej, możesz stworzyć wiele list kontrolnych, aby dostosować je do różnych sytuacji związanych z zatrudnianiem pracowników.

**Przykład 1**

Każdy pracownik, który jest zatrudniony w Stanach Zjednoczonych musi wykonać takie zadania jak wypełnienie formularzy podatkowych u źródła. Jednak zadania takie jak przydzielanie samochodu służbowego mogą dotyczyć tylko kadry kierowniczej. W tym przypadku mogą zostać utworzone dwie listy kontrolne: **Pracownicy z USA** oraz **Tylko pracownicy wykonawczy**. Następnie, gdy w Stanach Zjednoczonych zatrudniany jest menedżer średniego szczebla, wybierana jest lista kontrolna **Pracownicy z USA**. Jednak kiedy członek kadry kierowniczej jest zatrudniany w Stanach Zjednoczonych, wybiera się obie listy kontrolne, aby upewnić się, że wszystkie wymagane zadania związane z wprowadzeniem do służby zostały wykonane.

**Przykład 2**

Firma zatrudnia zarówno pracowników sezonowych, jak i stałych pracowników pełnoetatowych. Chociaż niektóre zadania (takie jak sprawdzenie czasu przybycia nowego pracownika) dotyczą pracowników obu typów, niektóre dodatkowe zadania dotyczą tylko regularnych pracowników pełnoetatowych. W tym przypadku możesz stworzyć dwie listy kontrolne. Obie listy kontrolne zawierają zadania, które odnoszą się zarówno do pracowników sezonowych, jak i etatowych, ale tylko jedna lista kontrolna zawiera zadania specyficzne dla etatowych pracowników.

## <a name="task-management-workspace"></a>Obszar roboczy Zarządzanie zadaniami

Obszar roboczy **Zarządzanie zadaniami** zawiera listę wszystkich zadań, które zostały przypisane do osób w procesach onboardingu, offboardingu i przejścia. Aby wyświetlić zadania dla danego procesu, wybierz odpowiednią zakładkę w lewym górnym rogu: **Onboarding**, **Offboarding** lub **Przejścia**. Domyślnie tylko HR-owcy mają dostęp do przestrzeni roboczej **Zarządzanie zadaniami**.

Zakładka **Onboarding** zawiera listę **Rozpoczęcie wkrótce**, na której znajdują się nowo zatrudnieni pracownicy oraz listę **Niedawno zatrudnieni**, na której znajdują się ostatnio zatrudnieni pracownicy. Na obu listach możesz wybrać tylko jednego pracownika. Kiedy wybierzesz pracownika, po prawej stronie pojawią się wszystkie zadania, które są związane z jego onboardingiem. Zakładka **Onboarding** zawiera również listę **Wszystkich zadań**, która pokazuje wszystkie zadania dla wszystkich przychodzących lub niedawno zatrudnionych pracowników. Na koniec zawiera listę zaległych zadań oraz listę zadań, które są przypisane do aktualnego użytkownika.

Zakładka **Offboarding** zawiera listę pracowników, którzy odchodzą z firmy oraz listę pracowników, którzy już odeszli z firmy. Na obu listach możesz wybrać tylko jednego pracownika. Kiedy wybierzesz pracownika, po prawej stronie pojawią się wszystkie zadania, które są związane z jego offboardingiem. Zakładka **Offboarding** zawiera również listę **Wszystkich zadań**, która pokazuje wszystkie zadania dla wszystkich wychodzących pracowników lub tych, którzy upuścili pracę niedawno. Na koniec zawiera listę zaległych zadań oraz listę zadań, które są przypisane do aktualnego użytkownika.

Zakładka **Przejścia** zawiera listę **Wszystkich zadań**, która pokazuje wszystkie zadania dla wszystkich pracowników, którzy będą zmieniać pozycje lub którzy ostatnio je zmieniali. Znajduje się tam również lista zadań zaległych oraz lista zadań, które są przypisane do danego użytkownika.

Na wszystkich trzech zakładkach asystenci i menedżerowie HR mogą wykonywać następujące czynności:
- Zastosuj listę kontrolną wobec pracownika
- Aktualizowanie stanu zadania
- Przydziel ponownie zadanie
- Zaktualizuj termin wykonania zadania

> [!NOTE]
> Domyślnie zakładka **Onboarding** pokazuje pracowników, którzy zostali zatrudnieni w ciągu ostatnich siedmiu dni. Aby zmienić to ustawienie, na stronie **Parametry zasobów ludzkich**, w zakładce **Ogólne**, w polu **Ostatnie zatrudnienia** wpisz przedział czasowy. Informacje w liście **Ostatnio zatrudnieni** mogą być wyświetlane dla określonej liczby dni, miesięcy lub lat. Na przykład, aby wyświetlić listę pracowników, którzy byli zatrudnieni w ciągu ostatnich 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**.
> Na stronie **Parametry zasobów ludzkich** możesz również zaktualizować zakres dat dla list wychodzących i odchodzących pracowników, które są widoczne w zakładce **Zwalnianie z pracy**. Te ustawienia dotyczą również obszaru roboczego **Zarządzanie personelem**.

## <a name="setting-up-tasks"></a>Ustawianie zadań

Możesz tworzyć zadania pojedynczo, a następnie wykorzystywać je w wielu listach kontrolnych. Aby utworzyć zadanie, na stronie **Ustawienia onboardingu**, w zakładce **Zadania** wybierz **Nowe**.

Utworzone zadanie można przypisać do wielu list kontrolnych, wybierając zadanie, a następnie wybierając polecenie **Zastosuj do list kontrolnych** w menu.

Alternatywnie możesz dodawać zadania bezpośrednio do listy kontrolnej. Aby dodać zadanie do listy kontrolnej, na stronie **Konfiguracja onboardingu**, w zakładce **Lista kontrolna**, albo stwórz nową listę kontrolną, do której dodasz zadanie, albo dodaj zadanie do istniejącej listy kontrolnej.

Aby edytować zadanie w bibliotece, wybierz polecenie **Edytuj** w menu Biblioteka zadań. Jeśli zadanie jest skojarzone z listami kontrolnymi, zostaną one wyświetlone na stronie **Edytuj zadanie**. Jeśli chcesz, aby zadania z dowolnej listy kontrolnej były aktualizowane przy użyciu edycji, wybierz te listy kontrolne w sekcji **Zastosuj do list kontrolnych**.

Aby usunąć zadania z biblioteki, wybierz opcję **Usuń**. Jeśli zadanie jest skojarzone z listą kontrolną, ta akcja nie spowoduje usunięcia zadania z tej listy kontrolnej. Zadanie musi zostać usunięte z listy kontrolnej w osobnej akcji.

> [!NOTE]
> Jeśli dodasz zadanie bezpośrednio do listy kontrolnej, nie będziesz mógł go użyć ponownie w innych listach kontrolnych.

Poniższa tabela opisuje pola, które są dostępne, gdy tworzysz zadanie za pomocą jednej z tych metod.

| Pole           | Opis |
|-----------------|-------------|
| Zadanie            | Wprowadź nazwę zadania. |
| Opis     | Wprowadź opis zadania. |
| Opcjonalnie        | Określ, czy zadanie jest opcjonalne i czy ma charakter wyłącznie informacyjny. |
| Łącze zadania       | Wpisz adres URL zewnętrznej strony internetowej lub konkretnej strony w aplikacji, na której użytkownik powinien wykonać zadanie. Więcej informacji można znaleźć w sekcji [Linki do zadań](#task-links). |
| Typ przypisania | Zadania mogą być przypisane do konkretnego pracownika, stanowiska lub grupy stanowisk, przełożonego pracownika, którego dotyczą (czyli pracownika, który jest częścią procesu włączania do zespołu, wyłączania z zespołu lub procesu przejścia) lub pracownika, którego dotyczą. Wybierz rodzaj zadania. Aby uzyskać więcej informacji, zobacz sekcję [Rodzaje przydziałów](#assignment-types) poniżej. |
| Przypisane do     | Wybierz konkretnego pracownika, stanowisko lub grupę stanowisk, do których chcesz przypisać zadanie. |
| Osoba kontaktowa  | Określ osobę, z którą należy się kontaktować w razie pytań dotyczących zadania. |
| Przesunięcie terminu | Określ liczbę dni przed lub po dacie zaokrętowania, zakończenia lub przejścia, w których zadanie ma zostać wykonane. Więcej informacji znajdziesz w sekcji [Daty wykonania zadań i pole przesunięcia daty wykonania](#task-due-dates-and-the-due-date-offset-field). |
| Instrukcje    | Wprowadź instrukcje dotyczące wykonania zadania. Więcej informacji można znaleźć w sekcji [Instrukcje](#instructions). |

### <a name="task-links"></a>Linki do zadań

Łącze do zadania stanowi łącze do zewnętrznej strony internetowej lub strony w aplikacji Dynamics 365. Możesz określić link zadania, jeśli osoba, która jest przypisana do zadania, powinna przejść do konkretnej strony internetowej lub konkretnej strony w aplikacji Dynamics 365, aby wykonać to zadanie. Kiedy tworzysz łącze do zadania, możesz wybrać jedną z poniższych opcji:

- **Pozycja menu** – Jeśli wybierzesz tę opcję, zostanie wyświetlona lista wszystkich stron w aplikacji Dynamics 365. Wybierz stronę z listy.
- **URL** – Jeśli wybierzesz tę opcję, wpisz adres URL strony internetowej, na którą chcesz, aby weszła osoba, która jest przypisana do tego zadania. Podana strona może być stroną, która nie jest częścią aplikacji Dynamics 365.
- **Szczegóły dotyczące pracownika** – w przypadku wybrania tej opcji wybierz jedną z następujących opcji:

    - **Akcje samoobsługi pracowników** – Ta opcja pokazuje listę stron, które są dostępne w **samoobsłudze pracowników**. Użyj go, jeśli zadanie, które zostało przydzielone włączanemu pracownikowi, musi zostać wykonane w **Samoobsłudze pracownika**. Na przykład, jeśli chcesz, aby pracownik wprowadził swoje osobiste dane kontaktowe, wybierz **Akcje samoobsługi pracowników**, a następnie wybierz **Dane osobowe i Informacje osobiste&gt;**.
    - **Akcje zarządzania pracownikiem** – Ta opcja pokazuje listę stron, które są związane z rekordem pracownika, ale nie są dostępne dla niego. Na przykład, jeśli chcesz, aby właściciel zadania wprowadził informacje specyficzne dla przyjmowanego pracownika, takie jak informacje o wynagrodzeniu, wybierz **Akcje zarządzania pracownikami**, a następnie wybierz **Wynagrodzenie&gt;Stałe wynagrodzenie**.

### <a name="assignment-types"></a>Typy przypisań

Kiedy pracownik jest zatrudniany, zwalniany lub przenoszony, można wybrać jedną lub więcej list kontrolnych. Po wybraniu listy kontrolnej i zakończeniu procesu zatrudniania, zakończenia lub przeniesienia, tworzone są zadania, które są przypisywane do użytkowników, aby śledzić postępy.

Kiedy tworzone jest zadanie, jest ono przypisywane do konkretnego użytkownika. Użytkownik, do którego przypisane jest zadanie, zależy od typu przypisania, który został wybrany dla tego zadania. W polu **Typ przydziału** są dostępne następujące wartości:

- **Pracownik** — przypisanie zadania do określonego pracownika. Po wybraniu tej wartości, wybierz pracownika w polu **Przypisany do**.
- **Stanowisko** — przypisanie zadania do określonego stanowiska. Po wybraniu tej wartości, wybierz stanowisko w polu **Przypisany do**.

    Na przykład, informatyk zawsze będzie odpowiedzialny za przygotowanie laptopa dla nowego pracownika. W tym przypadku, kiedy tworzysz zadanie konfiguracji laptopa, wybierz **Posadę** jako typ zadania, a następnie wybierz **Inżyniera IT** jako pozycję. Następnie, gdy pracownik jest zatrudniany i lista kontrolna jest przypisywana, zadanie konfiguracji laptopa jest przydzielane temu pracownikowi, który jest na stanowisku inżyniera IT w momencie wprowadzania akcji zatrudniania.

- **Grupa** — zadanie jest przypisywane do grupy stanowisk (grupa przypisań). Po wybraniu tej wartości, wybierz grupę w polu **Przypisany do**. Więcej informacji zawiera sekcja [Ustawianie grup przypisania (Opcja)](#setting-up-assignment-groups-optional).
- **Menedżer** — przypisanie zadania do menedżera pracownika, który jest zatrudniany, ukończył zatrudnienie lub był przenoszony.

    > [!IMPORTANT]
    > Kiedy lista kontrolna jest stosowana, jeśli żadna pozycja nie jest aktualnie przypisana do zatrudnionego, zakończonego lub przeniesionego pracownika, nie można ustalić kierownika. W tym przypadku zadanie jest przypisane do właściciela listy kontrolnej. Aby uzyskać więcej informacji, przejrzyj sekcję [Tworzenie list kontrolnych](#setting-up-checklists).

- **Pracownik** — przyporządkuj pracownika, który jest zatrudniany, rozwiązywany lub przenoszony.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Daty wykonania zadań i pole przesunięcia daty wykonania

Daty wymagalności zadań są oparte na dacie rozpoczęcia zatrudnienia, dacie zakończenia lub dacie przejścia. Niektóre zadania muszą być wykonane przed datą rozpoczęcia pracy przez pracownika, podczas gdy inne mogą być wykonane po niej. Podczas definiowania zadania w polu **Przesunięcie daty wymagalności od daty docelowej** wprowadzisz datę rozpoczęcia, datę zakończenia lub datę przejścia. Na przykład informatyk musi przygotować laptopa dla nowego pracownika na dwa dni przed datą jego rozpoczęcia pracy. W tym przypadku, kiedy tworzysz zadanie konfiguracji laptopa, ustaw pole **Przesunięcie terminu** na **-2**. Jeśli więc data rozpoczęcia pracy przez pracownika przypada na 5 maja, zadanie będzie miało termin wykonania 3 maja.

> [!NOTE]
> Terminy mogą zostać zmienione po utworzeniu zadania.

Terminy są obliczane na podstawie kalendarza, który jest powiązany z listą kontrolną. Aby uzyskać więcej informacji, przejrzyj sekcję [Tworzenie list kontrolnych](#setting-up-checklists).

### <a name="instructions"></a>Instrukcje

Złożone zadania mogą wymagać wielu kroków lub osoba, która je wykonuje, może być zmuszona do dostarczenia dodatkowych informacji. W polu **Instrukcje** możesz wpisać instrukcje lub dodatkowe informacje, które pomogą osobie przypisanej do danego zadania w jego wykonaniu.

## <a name="setting-up-checklists"></a>Tworzenie list kontrolnych

Lista kontrolna to grupa zadań. Możesz stworzyć tyle list kontrolnych, ile potrzebujesz, i możesz przypisać te same zadania do wielu list kontrolnych.

Aby utworzyć nowe zadanie z listy kontrolnej, wybierz pozycję **Nowe** na pasku menu **Zadania**. Podczas tworzenia nowego zadania można zaznaczyć opcję dodania go do biblioteki zadań, dzięki czemu będzie można je udostępnić na wielu listach kontrolnych. Zadanie można dodać do biblioteki tylko wtedy , gdy w opcji **Zastosuj zadanie do biblioteki** jest ustawiona wartość **Tak**. W przypadku dodania zadania do biblioteki zadań można je jednocześnie dodać do innych list kontrolnych, wybierając te listy kontrolne w sekcji **Zastosuj do list kontrolnych**. Jeśli zadanie nie zostanie dodanie do biblioteki, będzie ono istnieć tylko na liście kontrolnej, w których zostało utworzone.

Aby z listy kontrolnej edytować zadanie, wybierz pozycję **Edytuj**. Jeśli zadanie jest skojarzone z listami kontrolnymi, zostaną one wyświetlone na stronie **Edytuj zadanie**. Jeśli chcesz, aby zadania z innych list kontrolnych były aktualizowane przy użyciu edycji, wybierz te listy kontrolne w sekcji **Zastosuj do list kontrolnych**.

Aby usunąć zadania z listy kontrolnej, wybierz pozycję **Usuń**. Ta akcja usuwa zadania tylko z listy kontrolnej. Nie są one usuwane z biblioteki zadań. Aby usunąć zadanie z biblioteki, przejdź na stronę biblioteki zadań i wybierz pozycję **Usuń**.

Kiedy tworzysz listę kontrolną, określasz jej właściciela i kalendarz.

Jeśli pole **Typ przydziału** dla zadania jest ustawione na **Posada**, **Menadżer** lub **Grupa**, ale nie można określić konkretnej osoby na podstawie typu przydziału, zadanie zostanie przypisane do właściciela listy kontrolnej. Oto kilka przykładów sytuacji, w których zadania będą przypisane do właściciela listy kontrolnej:

- Pracownikowi, który jest zatrudniany lub z którym rozwiązuje się umowę, nie jest przypisane żadne stanowisko. Ponieważ pracownik nie ma przydzielonego stanowiska, nie można ustalić jego kierownika.
- Pole **Typ przydziału** jest ustawione na **Stanowisko**, ale w momencie tworzenia zadania żaden pracownik nie jest przypisany do tego stanowiska. Na przykład, zadanie **Ustawienie laptopa** jest przypisane do pozycji numer 000876 (**Specjalista ds. wsparcia technicznego**). W momencie zatrudniania pracownika, żaden pracownik nie jest przypisany do pozycji 000876. W związku z tym zostanie utworzone zadanie dla właściciela listy kontrolnej.
- Pole **Typ przydziału** jest ustawione na **Grupa**, ale w momencie tworzenia zadania żaden pracownik nie jest przypisany do tego stanowiska w grupie.

Kalendarz określony dla listy kontrolnej jest używany do obliczania terminu wykonania zadań wchodzących w skład tej listy. Dni robocze i niepracujące definiuje się w ustawieniach kalendarza. Przy obliczaniu terminu wykonania zadań uwzględnia się dni robocze, a wyklucza się dni wolne od pracy. Do dni niepracujących zalicza się weekendy i święta. 

Po utworzeniu kalendarza jest on kojarzony z szablonem listy kontrolnej. W ten sposób termin wykonania każdego zadania z listy kontrolnej jest obliczany w ten sam sposób. Możesz ustawić wiele kalendarzy, ale z każdą listą kontrolną może być związany tylko jeden kalendarz.

## <a name="setting-up-assignment-groups-optional"></a>Ustawianie grup przypisania (Opcjonalnie)

Czasem za zadanie odpowiedzialna jest grupa osób. Na przykład, grupa pracowników IT może być odpowiedzialna za przygotowanie laptopów dla nowo zatrudnionych.

Aby utworzyć grupę przypisania, wykonaj poniższe kroki.

1. Na stronie **Przypisanie grupy** wybierz opcję **Nowe**.
1. Wprowadź nazwę (na przykład **Laptop IT**) i opis dla grupy.
1. Wybierz opcję **Zapisz**.
1. Na skróconej karcie **Członkowie** wybierz pozycję **Dodaj**.
1. W polu **Stanowiska** wybierz wszystkie stanowiska odpowiedzialne za zadanie.

Po utworzeniu grupy zadań jest ona dostępna do wyboru, gdy tworzone jest zadanie. Aby wybrać konkretną grupę do zadania, musisz wybrać **Grupę** w **Typie przydziału**. Grupa, którą utworzyłeś, będzie wtedy dostępna do wyboru w polu **Przypisany do**.

> [!IMPORTANT]
> Jeśli zadanie jest przypisane do grupy, zostaje ono oznaczone jako **Zrealizowane**, gdy jedna osoba z grupy je wykona. Zadania są tworzone w momencie zatrudnienia, zakończenia lub przejścia. Są one tworzone dla użytkowników, którzy są przypisani do pozycji wchodzących w skład grupy.

## <a name="setting-up-task-groups-optional"></a>Ustawianie zadań przypisania (Opcjonalnie)

Proces onboardingu, offboardingu czy przejścia może obejmować wiele zadań. Aby ułatwić przypisanie wszystkich wymaganych zadań do listy kontrolnej, możesz utworzyć opcjonalne grupy zadań, aby skategoryzować powiązane zadania. Na przykład działy kadr, IT i płac muszą wykonać określone zadania, aby zatrudnić nowego pracownika. Dlatego tworzysz następujące grupy zadaniowe: **HR**, **IT** oraz **Lista płac**. Następnie, kiedy tworzysz zadanie, możesz powiązać z nim jedną z tych grup zadań.

Kiedy chcesz dodać zadanie do listy kontrolnej, możesz filtrować listę zadań według grupy zadań, do której jest przypisane dane zadanie. Na przykład, kiedy tworzysz szablon listy kontrolnej, możesz filtrować listę tak, aby pokazywane były tylko te zadania IT, które są przypisane do grupy zadań **IT**. Dzięki temu możesz mieć pewność, że wybierane są tylko odpowiednie zadania IT.

## <a name="using-checklists"></a>Korzystanie z list kontrolnych

Kiedy pracownik jest zatrudniany, zwalniany lub przenoszony, można wybrać jedną lub więcej list kontrolnych. Terminy zadań i przydziały pracowników są tworzone po zakończeniu procesu zatrudniania, zakończenia lub przejścia. Na przykład, gdy wybierzesz przycisk **Zatrudnij** lub **Zatrudnij i dodaj szczegóły**, zadania zostaną utworzone dla poszczególnych osób, w oparciu o typ zadania.

Termin wykonania jest przypisany do każdego zadania przez dodanie lub odjęcie przesunięcia terminu wykonania od daty rozpoczęcia pracy przez pracownika. Więcej informacji znajdziesz w sekcji [Daty wykonania zadań i pole przesunięcia daty wykonania](#task-due-dates-and-the-due-date-offset-field).

Jeśli używasz akcji personalnych, zadania są tworzone w momencie wybrania przycisku **Zakończ** lub zatwierdzenia akcji.

W przestrzeni roboczej **Zarządzanie zadaniami** możesz zastosować listę kontrolną do pracownika, wybierając go na stronie listy prostej lub stronie szczegółów, a następnie wybierając **Zastosuj listę kontrolną**. Wartość pola **Data docelowa** zostanie użyta do obliczenia terminu wykonania zadań. Zazwyczaj data docelowa powinna odpowiadać dacie zatrudnienia, zakończenia lub przejścia pracownika.

Możesz również zastosować listę kontrolną do pracownika, otwierając jego stronę **Pracownik** i wybierając **Listy kontrolne** z menu.

## <a name="completing-tasks"></a>Wykonanie zadania

Na stronie **Samoobsługa pracownika** pracownik może zobaczyć wszystkie zadania, które są mu przypisane. Dla każdego przydzielonego zadania wyświetlane są wartości **Zadanie**, **Opis**, **Instrukcje** oraz **Osoba kontaktowa**. Dodatkowo, dla każdego zadania pracownik może otworzyć powiązaną stronę zewnętrzną lub powiązaną stronę w aplikacji Dynamics 365.

Zadania mogą być również wyświetlane na domyślnym pulpicie nawigacyjnym. Aby wyświetlić zadania na domyślnym pulpicie nawigacyjnym:
1. Przejdź do **opcji użytkownika — preferencje – zarządzanie zadaniami** 
2. Wybierz **Wyświetl zadania na domyślnym panelu** na **Wł**.  

>[!Note] 
>Funkcja **Zarządzanie zadaniami** musi być włączona w **Zarządzaniu funkcjami**, aby opcja była wyświetlana w **Opcjach użytkownika**.

Zadania mogą być oznaczone jako **w toku**, **anulowane** lub **ukończone**. Jeśli zadanie było przypisane do grupy, zostaje ono oznaczone jako **Zrealizowane**, gdy jedna osoba z grupy je wykona.

Zadania mogą być także ponownie przydzielane.
