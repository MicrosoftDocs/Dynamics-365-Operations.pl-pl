---
title: Definicje kolumn w raportach finansowych
description: "Ten artykuł zawiera informacje o definicjach kolumn. Definicja kolumny to składnik (blok konstrukcyjny) raportu, który określa zawartość kolumn raportu. Podobnie jak definicje wierszy, definicje kolumn podstawowych mogą być używane w wielu raportach."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter, Core
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: bf42b287e2e9235fd50f78a6fadc3f9efbd1fbe5
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="column-definitions-in-financial-reports"></a>Definicje kolumn w raportach finansowych

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o definicjach kolumn. Definicja kolumny to składnik (blok konstrukcyjny) raportu, który określa zawartość kolumn raportu. Podobnie jak definicje wierszy, definicje kolumn podstawowych mogą być używane w wielu raportach.

<a name="create-and-modify-a-column-definition"></a>Tworzenie i modyfikowanie definicji kolumny
-------------------------------------

Definicja kolumny może zawierać do dwóch do 255 kolumn.

### <a name="create-a-column-definition"></a>Tworzenie definicji kolumny

1.  W Projektancie raportów w okienku nawigacji kliknij **Definicje kolumn**.
2.  W menu **Plik** kliknij **Nowy**, a następnie kliknij polecenie **Definicja kolumny**.
3.  Dodaj zawartość definicji kolumny.

### <a name="open-a-column-definition"></a>Otwieranie definicji kolumny

1.  W Projektancie raportów w okienku nawigacji kliknij **Definicje kolumn**.
2.  Kliknij dwukrotnie definicję kolumny, aby ją otworzyć.

### <a name="add-a-column-to-a-column-definition"></a>Dodawanie kolumny do definicji kolumny

1.  W Projektancie raportów kliknij **Definicje kolumn**, a następnie otwórz definicje kolumny do zmodyfikowania.
2.  Wybierz kolumnę, w której chcesz wstawić nową kolumnę.
3.  W menu **Edycja** kliknij **Wstaw kolumnę**. Nowa kolumna pojawi się z lewej strony wybranej kolumny.

### <a name="delete-a-column-from-a-column-definition"></a>Usuwanie kolumny z definicji kolumny

1.  W Projektancie raportów kliknij **Definicje kolumn**, a następnie otwórz definicje kolumny do zmodyfikowania.
2.  Wybierz kolumnę do usunięcia.
3.  W menu **Edycja** kliknij **Usuń kolumnę**.

## <a name="contents-of-a-column-definition"></a>Zawartość definicji kolumny
Definicja kolumny zawiera następujące informacje:

-   Kolumny opisów dla definicji wiersza
-   Kolumny kwot, które wyświetlają dane finansowe z arkusza programu Microsoft Excel lub obliczenia oparte na innych danych w definicji kolumny
-   Formatowanie kolumn
-   Kolumny atrybutów

Te informacje są wyświetlane w następujących obszarach w definicji kolumny:

-   Obszar nagłówka definicji kolumn zawiera tekst nagłówka i formatowanie, które pojawia się w raporcie. Nagłówek może dotyczyć pojedynczej kolumny danych, może obejmować wiele kolumn lub może dotyczyć kolumn na zasadach warunkowych. Definicja kolumny może zawierać dowolną liczbę wierszy nagłówka kolumny. **Uwaga:** nagłówki kolumn dotyczą każdej kolumny danych w raporcie. Nagłówki raportu dotyczą całego raportu. Nagłówki raportu definiuje się na karcie **Nagłówki i stopki** w definicji raportu.
-   Wiersze szczegółów kolumny to wiersze w obszarze wierszy nagłówka w definicji kolumny. Wiersze szczegółów kolumny definiują informacje uwzględniona w raporcie. W poniższej tabeli wymieniono i opisano wiersze szczegółów kolumny.

    | Nazwa wiersza szczegółów kolumny                                                | Opis                                                                                            |
    |-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
    | Typ kolumny                                                           | (Wymagane) Umożliwia określenie typu danych w kolumnie.                                                     |
    | Kod księgi/Atrybut kategorii                                          | Umożliwia określenie informacji o danych finansowych dla kolumn typu **FD** i **ATTR**.                       |
    | Okres roku obrachunkowego Objęte okresy                                    | Umożliwia określenie informacji o danych finansowych dla kolumn typu **FD**.                                     |
    | Wzór                                                               | Umożliwia określenie formuły obliczania dla kolumn typu **CALC**.                                        |
    | Szerokość kolumny Dodatkowe odstępy przed kolumną Zmiana formatu Sterowanie wydrukiem | Umożliwia określenie specjalnych opcji formatu.                                                                        |
    | Ograniczenia kolumny                                                   | Umożliwia ograniczenie danych.                                                                                         |
    | Jednostka raportowania                                                        | Umożliwia ograniczenie kolumny, aby zawierała dane tylko dla określonej jednostki raportowania.                      |
    | Sposób wyświetlania waluty Filtr waluty                                      | Umożliwia formatowanie waluty.                                                                                       |
    | Filtr wymiaru                                                      | Umożliwia określenie filtru w celu ograniczenia danych do określonych jednostek raportowania danych finansowych.                           |
    | Filtr atrybutu                                                      | Umożliwia określenie filtru w celu ograniczenia danych finansowych.                                                       |
    | Data początkowa Data końcowa                                                   | Umożliwia ograniczenie danych finansowych do określonych dat.                                                         |
    | Uzasadnienie                                                         | Umożliwia wyrównanie do lewej, wyrównanie do środka lub wyrównanie do prawej tekst opisu, który jest określony w definicji wiersza. |

## <a name="column-restrictions-in-a-column-definition"></a>Ograniczenia kolumny w definicji kolumny
Za pomocą ograniczenia kolumny można określić sposób, w jaki definicja kolumny używa danych lub oblicza informacje. Można też ograniczyć kolumnę raportu do określonej jednostki lub określonych dat. **Uwaga:** Kod **Ograniczenie kolumny** zastępuje dowolne ustawienie powodujące konflikt, które jest przypisane do definicji wiersza.

### <a name="column-restrictions-cell"></a>Komórka ograniczenia kolumny

Komórka **Ograniczenia kolumny** może zawierać kody, które ograniczają lub wyłączają informacje, np. formatowanie wiersza, szczegóły i kwoty dla tej kolumny.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Dodawanie ograniczeń kolumny do definicji kolumny

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Ograniczenia kolumny** dla kolumny, którą chcesz ograniczyć.
3.  W oknie dialogowym **Ograniczenia kolumny** wybierz jeden lub więcej kodów z listy, a następnie kliknij **OK**.

### <a name="column-restriction-codes"></a>Kody ograniczenia kolumny

W poniższej tabeli opisano kody ograniczeń dotyczących kolumn.

| Kod ograniczenia kolumny | Opis                                                                                                                                                                                                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SU                      | Pominięcie podkreślenia dla kolumny, w której w definicji wiersza wprowadzono polecenie podkreślenia (**---**) lub polecenia podwójnego podkreślenia (**===**). Na przykład może to służyć do podkreślania kwot będących wynikiem obliczania wartości procentowych.                                                                        |
| ST                      | Pominięcie sumy, tak aby wyświetlane były tylko szczegóły w kolumnie (np. kolumna statystyk).                                                                                                                                                                                                                                      |
| SD                      | Pominięcie szczegółów, aby w kolumnie były widoczne tylko wiersze **TOT** i **CAL** wiersze (z definicji wiersza).                                                                                                                                                                                                                              |
| DR                      | Ograniczenie kwot w kolumnie **FD** do kwot po stronie debetowej.                                                                                                                                                                                                                                                                              |
| CR                      | Ograniczenie kwot w kolumnie **FD** do kwot po stronie kredytowej.                                                                                                                                                                                                                                                                             |
| ADJ                     | Ograniczenie kwot w kolumnie do kwot korekty okresu, jeśli te kwoty są dostępne.                                                                                                                                                                                                                                        |
| XAD                     | Ograniczenie kwot w kolumnie, tak aby kwoty korekty okresu były wykluczone.                                                                                                                                                                                                                                                     |
| PT                      | Ograniczenie kwot w kolumnie, tak aby tylko zaksięgowane transakcje były uwzględniane, jeśli transakcje te są dostępne.                                                                                                                                                                                                                 |
| UPT                     | Ograniczenie kwot w kolumnie, tak aby tylko niezaksięgowane transakcje były uwzględniane, jeśli transakcje te są dostępne. **Uwaga:** nie wszyscy dostawcy danych obsługują niezaksięgowane transakcje. Aby uzyskać więcej informacji, zobacz [Podręcznik integracji danych](http://go.microsoft.com/fwlink/?LinkID=162565) dla systemu Microsoft Dynamics ERP. |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Ograniczanie kolumny do jednostki raportowania

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Jednostka raportowania** dla kolumny, którą chcesz ograniczyć.
3.  W oknie dialogowym **Raportowania wyboru jednostki** na liście **Drzewo raportowania** wybierz drzewo.
4.  Rozwiń lub zwiń listy jednostek, wybierz jednostkę raportowania, a następnie kliknij **OK**.

## <a name="format-column-headers"></a>Formatowanie nagłówków kolumn
Można dodawać, modyfikowanie i usuwanie nagłówki, które pojawiają się u góry kolumn w raporcie. Można także skonfigurować warunkowe nagłówki obejmujące kilka kolumn, na podstawie pola **Okres** z definicji kolumn i pola **Okres podstawowy** z definicji raportu. Funkcja okresu podstawowego przyspiesza tworzenie raportów prognozy ciągłej.

### <a name="create-and-manage-column-headers"></a>Tworzenie nagłówków kolumn i zarządzanie nimi

Za pomocą okna dialogowego **Nagłówek kolumny** można dodawać, modyfikować i usuwać nagłówki, które pojawiają się u góry kolumn w raporcie. W poniższej tabeli opisano pola w tym oknie dialogowym **Nagłówek kolumny**.

| Pole                 | Opis                                                                                                                                                                                                                                                                                                              |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tekst nagłówka kolumny    | Ten tekst pojawia się w nagłówku kolumny. Możesz wpisać tekst bezpośrednio w tym polu lub kliknąć przycisk **Wstaw autotekst**, aby wybrać opcję aktualizacji nagłówka kolumny po każdym wygenerowaniu raportu. Aby uwzględnić wiele kodów autotekstu, kliknij ponownie przycisk **Wstaw autotekst**, a następnie kliknij inny kod na liście. |
| Opcje formatu        | Umożliwia zastosowanie formatowania w nagłówku kolumny, np. pole lub podkreślenie.                                                                                                                                                                                                                                                           |
| Rozszerz od Rozszerz do | Umożliwia zdefiniowanie kolumny lub kolumn, do których odnosi się tekst nagłówka.                                                                                                                                                                                                                                                            |
| Uzasadnienie         | Umożliwia określenie, jak tekst nagłówka powinien być wyrównany dla kolumny lub zakresu kolumn, które są określone w polach **Rozszerz od** i **Rozszerz do**.                                                                                                                                                               |

### <a name="create-a-column-header"></a>Tworzenie nagłówka kolumny

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę nagłówka.
3.  W oknie dialogowym **Nagłówek kolumny** wpisz tekst nagłówka kolumny. Alternatywnie, kliknij przycisk **Wstaw autotekst**, a następnie wybierz opcję.
4.  W polu **Opcje formatu** wybierz format dla nagłówka.
5.  W polu **Rozszerz od** wprowadź literę kolumny, od której nagłówek kolumny powinien się zaczynać. W polu **Rozszerz do** wprowadź literę kolumny, od której nagłówek kolumny powinien się kończyć.
6.  W obszarze **Uzasadnienie** można ustawić, czy tekst nagłówka kolumny powinien być wyrównany do lewej krawędzi, do środka lub do prawej krawędzi.
7.  Kliknij przycisk **OK**

### <a name="add-a-column-header-row"></a>Dodawanie wiersza nagłówka kolumny

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Zaznacz komórkę w wierszu nagłówka.
3.  W menu **Edycja** kliknij **Wstaw wiersz**. Nowy wiersz jest wstawiany nad wierszem wybranym w kroku 2. **Uwaga:**Jeśli masz cztery lub więcej wierszy nagłówków raportu w raporcie, nagłówki będą się nakładać po wyeksportowaniu raportu do arkusza programu Excel. Aby wyświetlić wszystkie nagłówki na raporcie, zwiększ górny margines w definicji raportu.

### <a name="delete-a-column-header-row"></a>Usuwanie wiersza nagłówka kolumny

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W wierszu nagłówka zaznacz komórkę do usunięcia.
3.  W menu **Edycja** kliknij **Usuń wiersz**.

### <a name="create-an-automatically-generated-header"></a>Tworzenie nagłówka generowanego automatycznie

Projektant raportów może automatycznie wygenerować nagłówki kolumn na podstawie kodów autotekstu. Kody autotekstu są wartościami zmiennymi, które są aktualizowane po każdym wygenerowaniu raportu. Każdy nagłówek kolumny może zawierać te kody, aby określać informacje raportu, które mogą być różne, np. daty czy numery okresów. W związku z tym jedna definicja kolumny może być używana w odniesieniu do wielu definicji raportu, okresów czasu i drzew raportowania. Ponieważ kody autotekstu opierają się na informacjach kalendarza z wierszy szczegółów definicji kolumny, są one obsługiwane tylko kolumn **CALC**, **FD** i **WKS**. Sposób wyświetlania kodu autotekstu w nagłówku kolumny ma wpływ na sposób wyświetlania informacji w raporcie. W oknie dialogowym **Nagłówek kolumny** kody autotekstu są wyświetlane z użyciem małych i wielkich liter. Dlatego w także w raporcie tekst jest wyświetlany przy użyciu małych i dużych liter. Na przykład w standardowym roku kalendarzowy kod **@CalMonthLong** rozwiązuje cyfrę **7** do miesiąca **Lipiec**. Jeśli nazwa miesiąca powinna być pisana dużymi literami (na przykład **LIPIEC**), wprowadź kod autotekstu dużymi literami w polu **Tekst nagłówka kolumny**. Na przykład wpisz **@CALMONTHLONG**. Można łączyć ze sobą kody i tekst. Na przykład można wprowadzić następujący tekst nagłówka: **Okres @FiscalPeriod-@FiscalYear od @StartDate do @EndDate**. Generowany nagłówek raportu będzie wyglądał mniej więcej tak: **Okres 1-02 od 01-01-2002 do 31-01-2002**. **Uwaga:** Format niektórych tekstów, np. długich dat, zależy od ustawień regionalnych na serwerze programu Dynamics 365 for Operations. Aby zmienić te ustawienia, kliknij przycisk **Start**, kliknij **Panel sterowania**, a następnie kliknij **Region i język**. W poniższej tabeli pokazano dostępne opcje autotekstu dla nagłówków kolumn.

| Opcja i kod autotekstu                | opis                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa miesiąca (@CalMonthLong)              | Pozwala drukować nazwę bieżącego miesiąca w nagłówku kolumny. Jeśli użytkownik zdecyduje się zaokrąglać kwoty w raporcie do tysięcy, milionów lub miliardów, lub jeśli szerokość kolumn w raporcie jest mniejsza niż 9 znaków, nazwa miesiąca jest skracana do pierwszych trzech liter. |
| Skrócona nazwa miesiąca (@CalMonthShort) | Pozwala drukować skróconą nazwę miesiąca dla wybranego okresu obrachunkowego.                                                                                                                                                                                                                          |
| Numer okresu (@FiscalPeriod)           | Pozwala drukować formularz liczbowy okresu obrachunkowego identyfikowanego dla tej kolumny. Jeżeli kolumna obejmuje wiele okresów, drukowany jest ostatni okres w zakresie.                                                                                                                                   |
| Opis okresu (@FiscalPeriodName)  | Pozwala drukować opis okresu obrachunkowego identyfikowanego w danych finansowych.                                                                                                                                                                                                                    |
| Rok obrachunkowy (@FiscalYear)               | Pozwala drukować rok obrachunkowy dla kolumny w postaci numerycznej.                                                                                                                                                                                                                                            |
| Rok kalendarzowy (@CalYear)                | Pozwala drukować rok kalendarzowy dla kolumny w postaci numerycznej.                                                                                                                                                                                                                                          |
| Data początkowa (@StartDate)                 | Pozwala drukować datę początkową kolumny.                                                                                                                                                                                                                                                             |
| Data końcowa (@EndDate)                     | Pozwala drukować datę końcową kolumny.                                                                                                                                                                                                                                                               |
| Nazwa jednostki z drzewa (@UnitName)         | Jeśli kolumna jest ograniczona do określonej jednostki z drzewa raportowania, ta opcja pozwala drukować nazwę jednostki w nagłówku kolumny.                                                                                                                                                                                     |
| Opis jednostki (@UnitDesc)            | Jeśli kolumna jest ograniczona do określonej jednostki z drzewa raportowania, ta opcja pozwala drukować opis jednostki w nagłówku kolumny.                                                                                                                                                                              |
| Kod księgi (@BookCode)                   | Pozwala drukować kod księgi określony w kolumnie.                                                                                                                                                                                                                                             |
| Pusty wiersz (@Blank)                     | Pozwala wstawić pusty wiersz w nagłówku kolumny.                                                                                                                                                                                                                                                       |

### <a name="create-a-conditional-spanning-header"></a>Tworzenie warunkowego nagłówka rozszerzonego

Nagłówki rozszerzone mogą obejmować kilka kolumn opartych na danych określonego okresu. Na przykład jeśli masz raport budżetu dla roku obrachunkowego i chcesz wyświetlać rzeczywiste budżety z poprzednich miesięcy razem z prognozowanymi budżetami przyszłych miesięcy, możesz użyć nagłówka rozszerzonego, aby automatycznie aktualizować nagłówek raportu. Podczas tworzenia warunkowych nagłówków rozszerzonych należy pamiętać o następujących sytuacjach:

-   Każdy warunek zatrzymania (pole **Rozszerz do**) dopasowany przed warunkiem rozpoczęcia (pole **Rozszerz od**) jest ignorowany. Na przykład kolumna B ma warunek rozszerzenia zdefiniowany jako BASE+1 do BASE, BASE jest w kolumnie C, a BASE+1 jest w kolumnie D. W takim przypadku warunek zatrzymania w kolumnie C jest ignorowany i drukowanie nagłówka zaczyna się w kolumnie D.
-   W przypadku określenia nagłówków kolumn, które nakładają się na siebie, zachodzą one na siebie po wydrukowaniu raportu. Raport jest generowany, ale następujące ostrzeżenie jest wyświetlane w polu **Stan kolejki raportu**: „Nagłówki kolumny BASE zachodzą na inne nagłówki kolumny mogą powodować nakładanie się tekstu”. Na przykład definicja nagłówka w kolumnie B to B do BASE +1, a definicja nagłówka w kolumnie D to BASE+1 do F. W takim przypadku nagłówki są drukowane jeden na drugim i są nieczytelne. Zawsze gdy w definicji **Rozszerz od/Rozszerz do** używana jest wartość BASE, należy wyświetlić wygenerowany raport, aby sprawdzić, czy nagłówki nie nakładają się.
-   Jeśli w definicji rozszerzenia zdefiniowana jest wartość BASE w kolumnie nieprzeznaczonej do drukowania (**NP**), jest ona ignorowana niezależnie od definicji kolumny. Zasadniczo ten scenariusz odpowiada sytuacji, w której nie ma definicji nagłówka kolumny.
-   W przypadku kolumn z drukowaniem warunkowym (**P&lt;B**, **P&gt;=B**) warunkowe nagłówki rozszerzone zachowują się tak samo, jak zwykłe definicje nagłówków kolumn. Na przykład jeśli warunek nie jest spełniony, wszelkie kolejne dopasowani kolumny dla warunku rozszerzenia sprawiają, że nagłówek jest drukowany.

#### <a name="create-a-conditional-spanning-header"></a>Tworzenie warunkowego nagłówka rozszerzonego

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę nagłówka.
3.  W oknie dialogowym **Nagłówek kolumny** wpisz tekst nagłówka kolumny. Alternatywnie, kliknij przycisk **Wstaw autotekst**, a następnie wybierz opcję.
4.   W polu **Opcje formatu** wybierz styl formatowania dla nagłówka.
5.  Określ okres w stosunku do okresu podstawowego, który jest określany podczas generowania raportu. W polach **Rozszerz od** i **Rozszerz do** wpisz jedną z następujących wartości: **BASE**, **BASE-X** lub **BASE+X**, gdzie X oznacza liczbę okresów z okresu podstawowego. Na przykład po wprowadzeniu **BASE** w polu **Rozszerz od** tekst warunkowego nagłówka rozszerzone kolumny zaczyna się w nagłówku kolumny, gdzie wartość **Okres podstawowy** z definicji raportu jest równy wartości **Okres** z definicji kolumny . Kończy się w kolumnie, która jest wskazana w polu **Rozszerz do**. W związku z tym jeśli rozszerzenie zostało zdefiniowane jako BASE do M i wartość **Okres podstawowy** w definicji raportu wynosi **4**, nagłówek zaczyna się w kolumnie, w której okres jest ustawiony na **4** i kończy się w kolumnie M. Nagłówki zaczynają się i rozpoczynają tylko w kolumnach przeznaczonych do drukowania.
6.  W obszarze **Uzasadnienie** można ustawić, czy tekst nagłówka kolumny powinien być wyrównany do lewej krawędzi, do środka lub do prawej krawędzi.
7.  Kliknij przycisk **OK**

#### <a name="example-of-a-conditional-spanning-header"></a>Przykład warunkowego nagłówka rozszerzonego

Phyllis tworzy raport dla dynamicznej prognozy sześciu miesięcy. Chce, aby słowo „Rzeczywiste” było drukowane nad kolumnami zawierającymi dane rzeczywiste, a słowo „Budżet” — nad kolumnami zawierającymi prognozy budżetu. Każdy kolejny generowany raport zawiera o jedną kolumnę z danymi rzeczywistymi więcej i o jedną kolumnę budżetu mniej. Chociaż Phyllis może zmodyfikować definicję kolumny ręcznie za każdym razem, gdy raport jest generowany, aby dopasować nagłówki, to aby przyspieszyć i uprościć tę procedurę, postanawia utworzyć warunkowe nagłówki rozszerzone, które będą automatycznie tworzyły nagłówki nad odpowiednimi kolumnami w każdym kolejnym raporcie. Phyllis otwiera Projektanta raportów, klika opcję **Definicja kolumny** w panelu nawigacyjnym i otwiera definicję kolumny dla raportu. Wpisuje następujące informacje. Wartość okresu podstawowego w definicji raportu wynosi 4.

|                     | A    | mld             | C             | D             | E             | P             | G             | H             | I             | J             | tys.             | W             | P             |
|---------------------|------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|
| Nagłówek 1            |      | Rzeczywista liczba        | Budżet        |               |               |               |               |               |               |               |               |               |               |
| Nagłówek 2            |      | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong |
| Nagłówek 3            |      |               |               |               |               |               |               |               |               |               |               |               |               |
| Typ kolumny         | DESC | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            |
| Kod/atrybut księgi |      | ACTUAL        | BUDGET2012    | ACTUAL        | BUDGET2012    | ACTUAL        | BUDGET2012    | ACTUAL        | BUDGET2012    | ACTUAL        | BUDGET2012    | ACTUAL        | BUDGET2012    |
| Rok obrachunkowy         |      | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          |
| Okres              |      | 1             | 1             | 2             | 2             | 3             | 3             | 4             | 4             | 5             | 5             | 6             | 6             |
| Objęte okresy     |      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      |
| Szerokość kolumna        | 30   | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            |
| Sterowanie wydrukiem       |      | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        |

Phyllis dwukrotnie klika komórkę nagłówka kolumny, aby otworzyć okno dialogowe **Nagłówek kolumny**, w którym wpisuje następujące informacje.

| Pole              | Wartość                 |
|--------------------|-----------------------|
| Tekst nagłówka kolumny | Rzeczywista                |
| Wstaw autotekst    | Nie zostanie dokonany żaden wybór. |
| Opcje formatu     | Pole                   |
| Uzasadnienie      | Nie zostanie dokonany żaden wybór. |
| Rozszerz od        | B                     |
| Rozszerz do          | BASE                  |
| Nagłówek budżetu      | BASE+1 do końcowej kolumny  |

Po zakończeniu wprowadzania informacji Phyllis klika **OK**. Dwukrotnie klika komórkę nagłówka w kolumnie C, aby otworzyć okno dialogowe **Nagłówek kolumny**, w którym wpisuje następujące informacje.

| Pole              | Wartość                 |
|--------------------|-----------------------|
| Tekst nagłówka kolumny | Budżet                |
| Wstaw autotekst    | Nie zostanie dokonany żaden wybór. |
| Opcje formatu     | Pole                   |
| Uzasadnienie      | Nie zostanie dokonany żaden wybór. |
| Rozszerz od        | C                     |
| Rozszerz do          | BASE+2                |

Teraz za każdym razem gdy jest generowany ten raport, słowo „Rzeczywiste” będzie drukowane nad kolumnami zawierającymi dane rzeczywiste, a słowo „Budżet” — nad kolumnami zawierającymi prognozy budżetu. Oprócz tego liczba kolumn będzie co miesiąc odpowiednio korygowana.

## <a name="apply-column-justification"></a>Stosowanie uzasadnienia kolumny
Komórka **Uzasadnienie** służy do zastosowania formatowania uzasadnienia do kolumny opisu w raporcie. Ta opcja dotyczy tylko opisów kolumn, a nie rzeczywistych wartości.

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Uzasadnienie**.
3.  Z listy wybierz jedną z następujących wartości:
    -   **Brak** — uzasadnione nie jest stosowane.
    -   **Do lewej** — opisy kolumn są wyrównywane do lewej krawędzi.
    -   **Środek** — opisy kolumn są wyrównywane do środka.
    -   **Do prawej** — opisy kolumn są wyrównywane do prawej krawędzi.

## <a name="add-special-formatting-options"></a>Dodawanie specjalnych opcji formatowania
W definicji kolumny wiersze szczegółów formatowania kolumn odnoszą się do specjalnego formatowania w zaznaczonych kolumnach. Mimo że niektóre z opcji **Sterowanie wydrukiem** i **Ograniczenia kolumny** odnoszą się do kolumn **FD**, to większość opcji dotyczy wszystkich typów kolumn. Formatowanie określone w definicji kolumny ma wyższy priorytet od formatowania określonego w definicji raportu. Jednak formatowanie określone w definicji wiersza ma wyższy priorytet od formatowania określonego w definicji kolumny. Następujące wiersze są traktowane jako wiersze formatowania:

-   Szerokość kolumny
-   Dodatkowe odstępy przed kolumną
-   Zmiana formatu/waluty
-   Sterowanie wydrukiem

### <a name="changing-the-column-width"></a>Zmiana szerokości kolumny

Komórka **Szerokość kolumny** określa liczbę znaków na potrzeby szerokość tej kolumny w drukowanym raporcie. Szerokość kolumny ma znaczenie dla kolumn zawierających kwoty (**CALC**, **WKS** lub **FD**), opisy (**DESC**) oraz wypełnienia (**FILL**). Domyślnie opcja **Autodopasowanie** opcja wybrana, więc szerokość każdej kolumny jest automatycznie dopasowywana do jej zawartości.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>Określ szerokości kolumny w raporcie

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W komórce **Szerokość kolumny** wpisz liczbę odstępów dla szerokości kolumny. Maksymalna szerokość każdej kolumny to 255 znaków (to obejmuje procenty, przecinku i nawiasy). Alternatywnie, aby włączyć w projektancie raportów opcję wybierania odpowiedniej szerokości kolumny na podstawie zawartości komórki, kliknij dwukrotnie komórkę **Szerokość kolumny**, a następnie **Autodopasowanie**.

### <a name="add-space-between-columns"></a>Dodawanie odstępu między kolumnami

Komórka **Dodatkowe odstępy przed kolumną** określa szerokość separatora przed jedną kolumną i kolumnami z nią sąsiadującymi w definicji kolumny. Ustawienie **Dodatkowe odstępy przed kolumną** dotyczy wszystkich wierszy szczegółów kolumny dla kolumny, ale nie wierszy nagłówka kolumny. Za pomocą tej opcji można oddzielać grupy kolumn lub dodawać kilka odstępów przed opisem, tak aby kolumna opisu była wcięta względem tytułów wyrównanych do lewej krawędzi w raporcie. Domyślna między poszczególnymi kolumnami są dwa odstępy. To ustawienie można zmienić na karcie **Ustawienia** w definicji raportu.

#### <a name="specify-the-space-between-columns"></a>Ustalanie odstępów między kolumnami

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W komórce **Dodatkowe odstępy przed kolumną** wpisz, ile odstępów chcesz wstawić pomiędzy kolumnami.

### <a name="specify-a-currency"></a>Wybór waluty

Komórka **Zmiana formatu/waluty** określa formatowanie wartości dziesiętnych, waluty i kwot procentowych w kolumnie. To formatowanie zastępuje wszelkie formatowanie określone w definicji raportu lub domyślnych ustawieniach systemu.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Przypisywanie zastąpienia waluty/formatu do kolumny raportu

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Zmiana formatu/waluty** w kolumnie kwoty.
3.  W oknie dialogowym **Zmiana formatu** wybierz opcje formatowania.

### <a name="add-a-print-control-code"></a>Dodawanie kodu sterowania wydrukiem

Komórka **Sterowanie wydrukiem** może zawierać kody zmieniające widok lub ustawienia drukowania kolumny. Dostępne są dwa rodzaje kodów sterowania: zwykłe kody sterowania wydrukiem i warunkowe kody sterowania wydrukiem.

#### <a name="regular-print-control-codes"></a>Zwykłe kody sterowania wydrukiem

| Kod sterowania wydrukiem | Przeliczanie walut                                     | Opis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|--------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Niedrukowane                                     | Pozwala wykluczyć kwoty w tej kolumnie z drukowanego raportu oraz z obliczeń. Aby uwzględnić kolumnie niedrukowaną, należy odwołać się do niej bezpośrednio w formule obliczania. Na przykład kolumna niedrukowana C jest uwzględniona w następującym obliczeniu: **B+C+D**. Nie jest ona jednak uwzględniona w następującym obliczeniu: **B:D**.                                                                                                                                          |
| XCR                | Zmienianie znaku, jeśli zwykłe saldo wiersza jest po stronie kredytowej | Utwórz budżet lub raport porównawczy, jeśli jakiekolwiek niekorzystne odchylenia (takie jak niedobór przychodów lub przekroczenie wydatków) ma zawsze wartość ujemną. Zastosuj ten kod do kolumny **CALC**, aby odwrócić znak kwoty w kolumnie, jeśli zwykłe saldo danego wiersza jest po stronie kredytowej (na co wskazuje **C** w kolumnie **Zwykłe saldo** w definicji wiersza). **Uwaga:** dla wierszy **TOT** i **CAL**, które zwykle uwzględniają saldo kredytu, należy pamiętać o wprowadzeniu litery **C** w kolumnie **Zwykłe saldo** w definicji wiersza. |
| X0                 | Pomijanie kolumny, jeśli występując same zera lub puste pola          | Wyklucz kolumnę **FD** z raportu, jeśli wszystkie komórki w tej kolumnie są puste lub zawierają zera.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| SR                 | Pomijanie zaokrąglania                               | Zapobiegaj zaokrąglaniu kwoty w tej kolumnie.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| XR                 | Pomijanie akumulacji                                 | Pomijaj akumulację. Jeśli raport używa trzeba raportowania, kwoty w tej kolumnie nie są akumulowane w następnych węzłach nadrzędnych.                                                                                                                                                                                                                                                                                                                                                                                                   |
| RP                 | Powtarzanie kolumny na każdej stronie                      | Powtórz określoną kolumnę na każdej stronie raportu. Na przykład można użyć kodu sterowania wydrukiem **RP**, aby uwzględnić kolumnę typu **ROW**, która wstawia kody wiersza na każdej stronie.                                                                                                                                                                                                                                                                                                                                           |
| WT                 |  Zawijanie tekstu                                      |  Jeśli tekst w kolumnie jest za długi, by zmieścić się w dostępnym miejscu, zawijaj tekst, by całość znalazła się w kolumnie.                                                                                                                                                                                                                                                                                                                                                                                                                            |

#### <a name="conditional-print-control-codes"></a>Kody warunkowego sterowania wydrukiem

| Kody warunkowego sterowania wydrukiem | opis                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (brak)                         | Usuwanie zaznaczenia warunkowego wydruku.                                                  |
| P&lt;B                         | Wyświetlenie określonej kolumny tylko wtedy, gdy okres jest krótszy niż okres podstawowy.             |
| P&gt;B                         | Wyświetlenie określonej kolumny tylko wtedy, gdy okres jest dłuższy niż okres podstawowy.             |
| P=B                            | Wyświetlenie określonej kolumny tylko wtedy, gdy okres jest równy okresowi podstawowemu.              |
| P&lt;=B                        | Wyświetlenie określonej kolumny tylko wtedy, gdy okres jest krótszy niż okres podstawowy lub równy okresowi podstawowemu. |
| P&gt;=B                        | Wyświetlenie określonej kolumny tylko wtedy, gdy okres jest dłuższy niż okres podstawowy lub równy okresowi podstawowemu. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Dodawanie kodów sterowania wydrukiem do kolumny raportu

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Sterowanie wydrukiem**.
3.  W oknie dialogowym **Sterowanie wydrukiem** wybierz kod na liście **Wybierz opcje sterowania wydrukiem**. Aby wybrać więcej niż jeden kod, przytrzymaj klawisz Ctrl i zaznaczaj kolejne kody.
4.  Wybierz opcję w polu **Opcje drukowania warunkowego**. Domyślnie wybrane jest ustawienie **(brak)**. W tym samym czasie może być wybrany tylko jeden kod drukowania warunkowego.
5.  Kliknij przycisk **OK**

> [!TIP]
> Można również wprowadzić kody drukowania bezpośrednio w komórce **Sterowanie wydrukiem**. Kolejne kody sterowania wydrukiem należy oddzielić przecinkami.


## <a name="column-types"></a>Typy kolumn
Typy danych zawartych w każdej kolumnie w raporcie określa wartość w wierszu **Typ kolumny** w definicji kolumny. Każda definicja kolumny musi zawierać co najmniej jedną kolumnę opisu (**DESC**) i jedną kolumnę kwoty (**FD**, **WKS** lub **CALC**). **Uwaga:** kody typów kolumn nie mają zastosowania do wszystkich systemów księgowych. Wybranie typu, który nie jest prawidłowy dla systemu księgowania, spowoduje, ze ta kolumna w raporcie będzie pusta.

### <a name="specify-a-column-type"></a>Określanie typu kolumny

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W odpowiedniej kolumnie kliknij dwukrotnie komórkę w wierszu **Typu kolumny**.
3.  Wybierz typ kolumny z listy. W poniższej tabeli opisano różne typy kolumn.
    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Kod typu kolumny</th>
    <th>Opis</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>FD</td>
    <td>Wyświetl dane finansowe lub dane z arkusza programu Excel podczas korzystania z kolumny <strong>Łącze do wymiarów finansowych</strong> lub kolumny <strong>Łącze do arkusza roboczego</strong> w definicji wiersza. Po wybraniu typu kolumny <strong>FD</strong>, domyślne ustawienia są automatycznie określane dla następujących wierszy:
    <ul>
    <li><strong>Kategoria kodu/atrybutu księgi:</strong> ACTUAL</li>
    <li><strong>Kategoria kodu/atrybutu księgi:</strong> ACTUAL</li>
    <li><strong>Rok obrachunkowy:</strong> BASE</li>
    <li><strong>Okres:</strong> BASE</li>
    <li><strong>Objęte okresy:</strong> PERIODIC</li>
    <li><strong>Szerokość kolumny:</strong> 14</li>
    </ul>
    Można zmieniać takie ustawienia domyślne.</td>
    </tr>
    <tr class="even">
    <td>CALC</td>
    <td>Pozwala wyświetlić wynik prostego lub złożonego obliczenia określonego w komórce <strong>Formuła</strong> Aby uzyskać więcej informacji, zobacz <a href="advanced-formatting-options-financial-reporting.md">Zaawansowane opcje formatowania w raportowaniu finansowym</a>.</td>
    </tr>
    <tr class="odd">
    <td>DESC</td>
    <td>Umożliwia wyświetlenie opisu wiersza z definicji wiersza. Mimo że kolumna opisu jest często pierwszą kolumną w raporcie, może zajmować dowolną pozycję.</td>
    </tr>
    <tr class="even">
    <td>ROW</td>
    <td>Umożliwia wyświetlanie kodów pojedynczego wiersza dla wierszy finansowych z kolumny <strong>Kod wiersza</strong> w definicji wiersza. Aby uzyskać więcej informacji, zobacz <a href="row-definitions-financial-reporting.md">Definicje wierszy w raportowaniu finansowym</a>.</td>
    </tr>
    <tr class="odd">
    <td>ACCT (kody kont)</td>
    <td>Umożliwia wyświetlenie wartości segmentów danych finansowych lub wartości wymiaru, które mają zastosowanie do każdego wiersza. W przypadku raportów szczegółów transakcji, drukowane jest konto w pełni kwalifikowane (na przykład <strong>110140-070-0101</strong>). Jeśli zakresy zostały określone w kolumnie <strong>Łącze do wymiarów finansowych</strong> w powiązanej definicji wiersza, zakres jest ujęty w nawiasy kwadratowe i jest traktowany jako pojedyncza wartość (na przykład <strong>[110140:110700]-070-[0101:0200]</strong>). Dla sprawozdań finansowych i raportów wysokiego poziomu, które są kombinacją kilku kont, drukowane jest łącze danych finansowych z definicji wiersza (na przykład <strong>1100:1200</strong>).</td>
    </tr>
    <tr class="even">
    <td>FILL</td>
    <td>Umożliwia wypełnienie komórki znakami ujętymi w pojedynczych cudzysłowach. Jeśli nie zostanie wprowadzony znak, kolumna jest pusta. Na przykład, aby wstawić w kolumnie wielokropek (...), należy wprowadzić <strong>FILL</strong> <strong>'.'</strong>.</td>
    </tr>
    <tr class="odd">
    <td>PAGE</td>
    <td>Umożliwia wstawienie pionowego podziału strony w raporcie. Kolumny będące na prawo od kolumny <strong>PAGE</strong> pojawiają się na innej stronie.</td>
    </tr>
    <tr class="even">
    <td>WKS</td>
    <td>Umożliwia wyświetlanie danych pobieranych z arkusza programu Excel. Po wybraniu typu kolumny <strong>WKS</strong>, domyślne ustawienia są automatycznie określane dla następujących wierszy:
    <ul>
    <li><strong>Rok obrachunkowy:</strong> PERIODIC</li>
    <li><strong>Okres:</strong> BASE</li>
    </ul>
    Można zmieniać takie ustawienia domyślne.</td>
    </tr>
    <tr class="odd">
    <td>ATTR</td>
    <td>Umożliwia wyświetlanie atrybutu konta lub transakcji w tej kolumnie, jeśli system księgowy obsługuje atrybuty. Atrybut, który musi mieć zastosowanie do jednego pełnego konta, pobiera podrzędne informacje o koncie lub transakcji z danych finansowych. Atrybuty na poziomie konta wyświetlają dane z konta, a atrybuty na poziomie transakcji wyświetlają dane, które były prawdziwe w chwili zaksięgowania transakcji. Wybranie opcji <strong>ATTR</strong> jako typu kolumny pozwala określić kategorię w wierszu szczegółów <strong>Kod księgi/Kategoria atrybutu</strong> w definicji kolumny.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Kolumna Wymiary finansowe

Następujące definicje wiersza **Definicja kolumny** dotyczą kolumn typu **FD** (kwoty z wymiarów finansowych).

#### <a name="book-codeattribute-category-cell"></a>Komórka Kod księgi/Kategoria atrybutu

Komórka **Kod księgi/Kategoria atrybutu** komórki określa kod księgi dla danych w **FD** kolumny. Definicja kolumny może uwzględnić wiele kolumn z danymi rzeczywistymi, budżetem i statystykami. Definicja kolumny może również wyświetlać różne okresy, np. bieżący lub od początku roku, oraz różne kwoty. Lista kodów księgi odzwierciedla opcje wartości rzeczywistych, budżetu i statystyk (niefinansowe), które zostały określone w danych finansowych.

#### <a name="fiscal-year-cell"></a>Komórka Rok obrachunkowy

Komórka **Rok obrachunkowy** określa rok obrachunkowy, który kolumna powinna uwzględniać. Rok może odnosić się do roku okresu podstawowego, który jest określany podczas generowania raportu. Dostępne są następujące opcje.

| Opcja  | Opis                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| BASE    | Umożliwia użycie roku podstawowego określonego w czasie tworzenia raportu.                                                                          |
| BASE+\# | Umożliwia użycie roku o określoną liczbę lat w przód od roku podstawowego. Na przykład, aby użyć trzeciego w kolejności roku po roku podstawowym, należy wpisać **BASE+3**. |
| BASE-\# | Umożliwia użycie roku o określoną liczbę lat wstecz od roku podstawowego. Na przykład, aby użyć poprzedniego roku, należy wpisać **BASE-1**.                 |
| \#      | Umożliwia wprowadzenie rzeczywistego roku obrachunkowego.                                                                                                |

#### <a name="period-cell"></a>Komórka Okres

Komórka **Okres** określa okres obrachunkowy, który kolumna powinna uwzględniać. Okres może odnosić się do okresu podstawowego, który jest określany podczas generowania raportu. Dostępne są następujące opcje.

| Opcja          | opis                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BASE            | Umożliwia użycie okresu podstawowego.                                                                                                                                                                                                                 |
| BASE+\#         | Umożliwia użycie okresu o określoną liczbę okresów w przód od okresu podstawowego. Na przykład, aby użyć trzeciego w kolejności okresu po okresie podstawowym, należy wpisać **BASE+3**.                                                                                               |
| BASE-\#         | Umożliwia użycie okresu o określoną liczbę okresów wstecz od okresu podstawowego. Na przykład, aby użyć poprzedniego okresu, należy wpisać **BASE-1**.                                                                                                                 |
| BASE-\#:BASE    | Umożliwia użycie wielu okresów od kilku okresów przed okresem podstawowym i z uwzględnieniem okresu podstawowego. Na przykład, aby użyć trzech poprzednich okresów wraz z okresem podstawowym, należy wpisać **BASE-3:BASE**                                                |
| BASE:BASE+\#    | Umożliwia użycie wielu okresów od okresu podstawowego przez kilka okresów po okresie podstawowym. Na przykład, aby użyć okresu podstawowego i kolejnych dwóch okresów, należy wpisać **BASE:BASE+2**.                                                  |
| BASE-\#:BASE+\# | Umożliwia użycie wielu okresów od kilku okresów przed okresem podstawowym do kilku okresów po okresie podstawowym. Na przykład, aby użyć trzech wcześniejszych okresów, okresu podstawowego i kolejnych dwóch okresów, należy wpisać **BASE-3:BASE+2**. |
| 1:BASE          | Umożliwia użycie wielu okresów od pierwszego okresu do okresu podstawowego.                                                                                                                                                                 |
| \#              | Pozwala zawsze używać okresu o określonym numerze. Nie zalecamy używania tej opcji, ponieważ ogranicza ona elastyczność definicji kolumny.                                                                                       |
| \#                                      : \#           | Pozwala zawsze używać zakresu okresów. Nie zalecamy używania tej opcji, ponieważ ogranicza ona elastyczność definicji kolumny.                                                                                    |

W każdej specyfikacji okresu można wyjść poza zakres roku obrachunkowego i można łączyć ze sobą lata i zakresy okresów. Na przykład można określić okresy jako **BASE-5** (co odpowiada sześciu okresom wstecz) i uruchomić raport z okresem podstawowym 2. W takim przypadku raport wyświetla dane dla pierwszych dwóch okresów określonego roku obrachunkowego i ostatnie cztery okresy poprzedniego roku obrachunkowego.

### <a name="specify-the-periods-for-an-fd-column"></a>Określanie okresów dla kolumny FD

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W kolumnie **FD** kliknij dwukrotnie komórkę w wierszu **Okres**, a następnie wybierz odpowiednią opcję z listy.
3.  Na pasku formuły powyżej okienka nawigacji lub w komórce **Okres** uzupełnij formułę. Zamień wszystkie znaki numeru (\#) na odpowiednią wartość.

#### <a name="periods-covered-cell"></a>Komórka Objęte okresy

Komórka **Objęte okresy** określa kwotę, jaka powinna być wyświetlana w kolumnie. Ta kwota jest uwarunkowana wartością w komórkach **Rok obrachunkowy** i **Okres** dla kolumny. Dostępne są następujące opcje.

| Opcja      | Opis                                                                 |
|-------------|-----------------------------------------------------------------------------|
| PERIODIC    | Służy do wyświetlania sumy działania dla bieżącego okresu lub okresów. |
| PERIODIC/BB | Służy do wyświetlania salda początkowego działania dla bieżącego okresu lub okresów.   |
| YTD         | Służy do wyświetlania sumy działania od początku roku.                               |
| YTD/BB      | Służy do wyświetlania salda początkowego od początku roku.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Określanie objętych okresów dla kolumny FD

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W kolumnie **FD** kliknij dwukrotnie komórkę w wierszu **Objęte okresy**, a następnie wybierz odpowiednią opcję z listy.

### <a name="attribute-filter-in-a-column-definition"></a>Filtr atrybutu w definicji kolumny

Atrybuty są wartościami danych finansowych, które pomogą dokładniej określić konta lub transakcje. Atrybuty kont obejmują **Składnik aktywów**, **Zobowiązanie**, **Przychód** i **Wydatek**. Atrybuty transakcji obejmują **Opisu transakcji** i **Data zastosowania transakcji**. Obsługa atrybutów może się różnić w zależności od systemu Microsoft Dynamics ERP. Komórka **Filtr atrybutu** ogranicza dane w kolumnie **FD** do określonych wartości lub zakresów dla kategorii atrybutów. Chociaż ta funkcja może być używana razem z kolumną **ATTR**, kolumna **ATTR** nie jest wymagana. W kolumnie **FD** występuje limit kont lub transakcji, które będą zawarte w raporcie na podstawie filtra atrybutu. **Uwaga:** aby wyświetlić atrybuty obsługiwane przez danych system ERP, należy zajrzeć do podręcznika integracji systemu.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Stosowanie filtra atrybutu dla kolumny FD w raporcie

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Filtr atrybutu** dla kolumny **FD**.
3.  W oknie dialogowym **Filtr atrybutu** kliknij dwukrotnie komórkę w kolumnie **Atrybut**, a następnie wybierz typ filtra.
4.  Aby jeszcze bardziej ograniczyć liczbę wyników, należy wprowadzić zakres w kolumnach **Od** i **Do**. Komórka **Od** musi zawierać wartość.
5.  Kliknij przycisk **OK**

#### <a name="example-of-an-attribute-filter"></a>Przykład filtra atrybutu

W poniższym przykładzie przedstawiono część opisu kolumny zawierającą atrybut konta w wierszu **Kod księgi/Kategoria atrybutu**. Filtr atrybutu dla tej kolumny określa zakres wartości, które mają być ujęte w raporcie.

|                              | I    | mld                    |
|------------------------------|------|----------------------|
| Typ kolumny                  | DESC | FD                   |
| Kod księgi/Atrybut kategorii |      | ACTUAL               |
| Rok obrachunkowy                  |      | BASE                 |
| Okres                       |      | 1:BASE               |
| Objęte okresy              |      | PERIODIC             |
| ...                          |      |                      |
| Szerokość kolumna                 | 30   |                      |
| ...                          |      |                      |
| Filtr atrybutu             |      |  Odwołanie=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>Filtr wymiaru w definicji kolumny

Filtr wymiaru służy do ograniczania kolumny **FD** do określonych wartości wymiaru. Filtr może zawierać jeden wymiar, zakres wymiarów lub grupę wymiarów. Filtr może również uwzględniać zestawy wartości wymiarów. Ponieważ wartości wymiarów mogą być różne, system oparty na wymiarach nie musi odpowiadać dokładnej długości. Filtr jest stosowane niezależnie od tego, czy raport obejmuje drzewo raportowania. Można użyć symbolu wieloznacznego (\* lub ?) w dowolnym miejscu. W przypadku określenia wielu kont należy rozdzielić je przecinkami, np.: +Konto=\[1200\], +Konto=\[1100\], Dział=\[01?\] Aby otrzymywać informacje o wszystkich działach dla wybranego konta, można wykluczyć wymiar Dział z filtra wymiaru. Na przykład oba z poniższych filtrów wymiarów są obsługiwane w taki sam sposób:

-   +Konto=\[1100\],Dział
-   +Konto=\[1100\]

Można także użyć dowolnej kombinacji znaków alfanumerycznych dla dokładnego dopasowywania i można zdefiniować wymiary częściowe. Na przykład **Lokalizacja = \[10\*\]** obejmuje wszystkie wartości wymiaru lokalizacji, które mają na początku wartość 10.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Stosowanie filtra wymiaru dla kolumny w raporcie

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Filtr wymiaru** dla kolumny **FD**.
3.  W oknie dialogowym **Wymiary** wpisz filtry, które mają być stosowane.
4.  Kliknij przycisk **OK**

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Formatowanie raportu z wieloma walutami w definicji kolumny

Raport z wieloma walutami może wyświetlać kwoty w walucie naturalnej (lokalnej), funkcjonalnej (domyślnej) lub w walucie raportowania. Waluta funkcjonalna dla firmy jest definiowana w systemie Microsoft Dynamics ERP. Nie należy mylić tego ustawienia ERP z ustawieniem opcji regionalnych systemu operacyjnego, w którym można skonfigurować domyślne symbole waluty używane w raportach. W definicji kolumny dostępne są następujące komórki dotyczące waluty:

-   **Sposób wyświetlania waluty** — pozwala określić typ waluty (naturalna, funkcjonalna lub raportowania) używany do wyświetlania transakcji. Ta funkcja jest czasami nazywana przeliczaniem waluty. Przeliczania waluty polega na raportowaniu kwot księgi głównej w walucie, która nie musi być walutą funkcjonalną firmy lub walutą, w której wprowadzono transakcję.
-   **Filtr waluty** — pozwala określić filtr waluty. W raporcie są wyświetlane tylko transakcje, które są wprowadzane w wybranej walucie.

> [!NOTE]
> W celu tworzenia raportów obejmujących wiele walut należy zaznaczyć pole wyboru **Uwzględniaj wszystkie waluty raportowania** na karcie **Raporty** w definicji raportu. Aby określić walutę funkcjonalną firmy, należy wykonać następujące czynności.

1.  W Projektancie raportów w menu **Firma** kliknij przycisk **Firmy**.
2.  W oknie dialogowym **Firmy** wybierz firmę, a następnie kliknij **Widok**.
3.  W oknie dialogowym **Przeglądanie firm**w obszarze **Opcje regionalne** można wyświetlić walutę zdefiniowaną dla wybranej firmy.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Określanie waluty w raporcie z wieloma walutami

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Sposób wyświetlania waluty** w odpowiedniej kolumnie **FD**, a następnie wybierz opcję wyświetlania informacji o walucie: **Waluta naturalna/pierwotna**, **Waluta funkcjonalna z informacjami o firmie**, lub waluta raportowania.
3.  Kliknij dwukrotnie komórkę **Filtr waluty** w odpowiedniej kolumnie **FD**, a następnie wybierz odpowiedni kod waluty na liście. W raporcie są wyświetlane tylko transakcje, które są wprowadzane w tej walucie.

> [!NOTE]
> Opisane tutaj opcje mogą się różnić, w zależności od systemu ERP. Więcej informacji można znaleźć w [dokumentacji systemu Microsoft ERP](https://www.microsoft.com/en-us/download/details.aspx?id=5916).

### <a name="example-for-currency-display-and-currency-filter-cells"></a>Przykład komórek Sposób wyświetlania waluty i Filtr waluty

Phyllis wybrała następujące waluty w definicji kolumny:

-   **Filtr waluty:** Jen
-   **Sposób wyświetlania waluty:** Funkcjonalna (USD)

Wybrany filtr waluty powoduje, że raport obejmuje tylko transakcje wprowadzone w jenach (JPY). Wybrany sposób wyświetlania waluty sprawia, że raport wyświetla te transakcje w walucie funkcjonalnej, czyli w dolarach amerykańskich (USD).

#### <a name="currency-filter-and-currency-display-combinations"></a>Kombinacje filtr waluty i sposobu wyświetlania waluty

W poniższej tabeli przedstawiono wyniki raportu, które mogą pojawić się dla różnych kombinacji opcji w komórkach **Sposób wyświetlania waluty** i **Filtr waluty** ze względu na wybrane opcje. Walutą funkcjonalną jest UDS.

| Komórka Sposób wyświetlania waluty                        | Komórka Filtr waluty | Wynik raportu                                                                                                                                                                                    |
|----------------------------------------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Waluta naturalna/pierwotna                 | **YEN**              | **Y6,000** — wynik pokazuje tylko transakcje, które zostały wprowadzone w JPY.                                                                                                                        |
| Waluta funkcjonalna na podstawie informacji o firmie | **YEN**              | **60 USD** — wynik pokazuje tylko transakcje, które zostały wprowadzone w JPY i wyświetla te transakcje w USD. **Uwaga:** kurs wymiany to w przybliżeniu 100 JPY za 1 USD.                    |
| Waluta funkcjonalna na podstawie informacji o firmie | Pusty                | **2310 USD\*\*** — wynik pokazuje wszystkie dane w walucie funkcjonalnej określonej w informacjach o firmie. **Uwaga:** ta kwota jest sumą wszystkich transakcji w walucie funkcjonalnej. |
| Waluta naturalna/pierwotna                 | Puste                | **2250 USD** — wynik pokazuje wszystkie kwoty w walucie, w której transakcja została przeprowadzona.                                                                                                 |

### <a name="calculation-column-in-a-column-definition"></a>Kolumna obliczania w definicji kolumny

Typ kolumny **CALC** w definicji kolumny obsługuje złożone obliczenia w komórce **Formuła** i może zawierać operatory **+**, **-**, **\*** i **/**, a także instrukcje **IF/THEN/ELSE**. Kolumna obliczeń może również odnosić się do dowolnej innej kolumny, a nawet do kolejnych kolumn. Ponadto kolumna obliczania może również zawierać rok obrachunkowy i okres do obsługi nagłówków dla kolumny. Formuła obliczania może zawierać do 1024 znaków. Aby wyrazić wynik obliczeń jako wartość procentową, należy użyć specjalnego zastąpienia formatu. **Uwaga:** wyniki formuł obliczania nie obejmują wartości w zakresach kolumn niedrukowanych. Na przykład formuła **A:D** drukuje **0** (zero), a formuła **A+B+C** dla wartości kolumn niedrukowanych oblicza wartości.

#### <a name="operators-in-calculation-columns"></a>Operatory w kolumnach obliczeń

Aby dodać, odjąć, pomnożyć lub podzielić kolumny, wpisz litery kolumn w kolejności obliczania, a następnie użyj odpowiedniego operatora, aby oddzielić poszczególne litery kolumn. W poniższej tabeli opisano operatory, których można używać w kolumnie obliczenia.

| Operator | Przykład obliczenia | opis                                                                                                                                                                                                                                    |
|----------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| +        | A+C                 | Dodawanie kwoty w kolumnie A do kwoty w kolumnie C.                                                                                                                                                                                          |
| :        | A:C A:C-D           | Dodawanie zakresu kolejnych kolumn. Na przykład formuła **A:C** dodaje sumy kolumn od A do C, a formuła **A:C-D** dodaje sumy kolumny od A do C, a następnie odejmuje kwotę w kolumnie D.                          |
| -        | A-C                 | Odejmowanie kwoty w kolumnie A od kwoty w kolumnie C. **Uwaga:** można też użyć znaku odejmowania (-), aby odwrócić znaki w kolumnie. Na przykład formuła **-A+B** pozwala dodać odwrotną wartość kwoty w kolumnie A do kwoty w kolumnie B. |
| \*       | A\*C                | Mnożenie kwoty w kolumnie A przez kwotę w kolumnie C.                                                                                                                                                                                     |
| /        | A/C                 | Dzielenie kwoty w kolumnie A przez kwotę w kolumnie C.                                                                                                                                                                                       |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Używanie formuły obliczania w definicji kolumny

1.  W Projektancie raportu otwórz definicję kolumny do zmodyfikowania.
2.  W odpowiedniej kolumnie **CALC** wpisz formułę w komórce **Formuła**.

#### <a name="complex-calculations"></a>Złożone obliczenia

Złożone obliczenia mogą zawierać dowolną kombinację odwołań do komórek, operatorów, wartości i poziomów zagnieżdżonych nawiasów. Na przykład, aby obliczyć średnią kolumn A i B, należy użyć formuły obliczania **((A+B)/2)**.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Określenie komórek raportu w obliczeniach kolumny

Można tworzyć odwołania do określonej komórki raportu, wprowadzając literę w kolumnie i kod wiersza. Na przykład **B.100** odwołuje się do wiersza kodu 100 w kolumnie B. Całą kolumnę można podzielić według kwoty komórki określonego raportu, który znajduje się w tej samej kolumnie. Na przykład obliczenia **B/B.100** oznacza, że wartość w kolumnie B powinna być podzielona przez wartość w wierszu kodu 100 w kolumnie B. Jeśli obliczenie odwołuje się do kolumny, która jest zależna od innej kolumny, najpierw jest rozwiązywana kolumna zależna. Jeśli kolumna odwołuje się do innej kolumny, która odwołuje się z powrotem do pierwszej kolumny, spowoduje to błąd odwołania cyklicznego. **Uwaga:** obliczenie może być niepoprawne, jeśli zmienisz priorytet obliczeń dla raportu. Priorytet obliczeń można ustawić dla karcie **Ustawienia** dla definicji raportu.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Mnożenie lub dzielenie kolumny według wiersza bazowego

Można utworzyć kolumnę, w której są wyświetlane wszystkie wartości w określonej kolumnie jako procent liczby bazowej. Można więc wyświetlić relacje między wierszami, takie jak procent wiersza sprzedaży lub odsetek wiersza sumy wydatków. Aby pomnożyć lub podzielić każdy wiersz w określonej kolumnie przez wiersz podstawowy, wpisz kolumnę, która ma zostać użyta do obliczeń, a następnie wpisz **\*BASEROW** lub **/BASEROW**. Na przykład wpisz **C\*BASEROW** lub **C/BASEROW**. **Uwaga:** jeżeli używasz obliczania wiersza podstawowego w definicji kolumn, upewnij się, że każda definicja wiersza, która jest używana z definicją kolumny, zawiera co najmniej jeden wiersz podstawowy do obliczeń.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Dzielenie kwoty w kolumnie przez liczbę okresów

Można podzielić kwotę w kolumnie przez określoną liczbę okresów. Na przykład formuła **B/Okresy** dzieli wartość w kolumnie B przez liczbę okresów w kolumnie B. Jeśli obliczenie obejmuje wiele kolumn, należy określić liczbę okresów, które zostać użyte w obliczeniach. Na przykład formuła **(B+C)/Okresy** dodaje kwoty w kolumnach B i C, a następnie dzieli wynik przez wartość okresu.

<a name="see-also"></a>Informacje dodatkowe
--------

[Definicje wierszy w raportowaniu finansowym](row-definitions-financial-reporting.md)

[Zaawansowane opcje formatowania w raportowaniu finansowym](advanced-formatting-options-financial-reporting.md)




