---
title: Generowanie skonsolidowanych sprawozdań finansowych
description: W tym temacie opisano różne scenariusze, w których mogą być generowane skonsolidowane sprawozdania finansowe.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 55c5d02ca4e487782f020aa5eb85e6ebb36d4ce8
ms.sourcegitcommit: 9b4c3fff2f30006b7bb491ef6ffe89d41bcbfa11
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2019
ms.locfileid: "1863707"
---
# <a name="generate-consolidated-financial-statements"></a>Generowanie skonsolidowanych sprawozdań finansowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano różne scenariusze, w których mogą być generowane skonsolidowane sprawozdania finansowe.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Konsolidacje jednopoziomowe i wielopoziomowe w różnych firmach
Najprostszą metodą konsolidowania za pomocą aplikacji Raportowanie finansowe jest używanie drzew raportowania do agregowania danych ze wszystkich firm, które mają ten sam plan kont i okresy obrachunkowe. Poniżej przedstawiono ogólne czynności w ramach konsolidowania przy użyciu drzewa raportowania.

1. Utworzenie definicji wiersza, a następnie upewnienie się, że wszystkie odpowiednie konta ze wszystkich firm są uwzględnione w wierszach.
2. Utworzenie definicji kolumny obejmującej wszystkie kolumny, które są wymagane w tworzonym raporcie.
3. Utworzenie drzewa raportowania zawierającego węzeł raportowania dla każdej firmy uwzględnionej w skonsolidowanych raportach.

> [!TIP]
> Aby uzyskać więcej informacji na temat tworzenia i zarządzania definicjami wierszy, definicjami kolumn i drzewami raportowania, zobacz [Składniki raportu finansowego](../../dev-itpro/analytics/financial-report-components.md).

Ilustracja poniżej przedstawia sposób wykorzystania definicji drzewa raportowania w module Raportowanie finansowe do zidentyfikowania każdej firmy, która będzie konsolidowana.

![Definicja drzewa raportowania](./media/reporting-tree-definition.png "Definicja drzewa raportowania")

Jak pokazuje skonsolidowany raport na poniższej ilustracji, używając drzewa raportowania razem z definicją raportu, można wyświetlić każdą firmę osobno. Skonsolidowane kwoty są wyświetlane na poziomie podsumowania.

![Poziom podsumowania skonsolidowanych kwot](./media/consolidate-amount-summary-level.png "Poziom podsumowania skonsolidowanych kwot")

Można również utworzyć wielopoziomowe drzewo raportowania, które zawiera dowolną potrzebną liczbę poziomów. Na poniższej ilustracji przedstawiono definicję wielopoziomowego drzewa raportowania akumulowanego według regionów świata.

![Definicja wielopoziomowego drzewa raportowania akumulowanego według regionów](./media/multilevel-reporting-tree-definition-roll-ups-worldwide-region.png "Definicja wielopoziomowego drzewa raportowania akumulowanego według regionów")

Na poniższej ilustracji przedstawiono definicję wielopoziomowego drzewa raportowania akumulowanego według funkcji.

![Definicja wielopoziomowego drzewa raportowania akumulowanego według funkcji](./media/multilevel-reporting-tree-definition-roll-ups-by-function.png "Definicja wielopoziomowego drzewa raportowania akumulowanego według funkcji")

### <a name="viewing-companies-side-by-side"></a>Wyświetlanie firm obok siebie
Wielu klientów preferuje raporty, w których firmy są wyświetlane obok siebie, a kolumna pokazuje skonsolidowaną sumę. Ten format jest łatwy do osiągnięcia po utworzeniu drzewa raportowania. Poniżej przedstawiono ogólne czynności, jakie należy wykonać w celu wyświetlenia firm obok siebie w skonsolidowanych sprawozdaniach finansowych.

1. Utworzenie definicji kolumny zawierającej kolumnę **Wymiar finansowy** dla każdej firmy.
2. Użycie pola **Jednostka raportowania** w celu wybrania drzewa i jednostki raportowania dla każdej kolumny.
3. Opcjonalnie: Dodanie nagłówków i kolumn sum.

Poniższa ilustracja pokazuje definicję kolumny w formacie wyświetlania obok siebie.

![Definicja kolumny w formacie wyświetlania obok siebie](./media/column-definition-side-by-side-format.png "Definicja kolumny w formacie wyświetlania obok siebie")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Konsolidacje wykorzystujące struktury organizacyjne tworzone na podstawie firm
Hierarchie organizacyjne, które zawierają wymiary lub firmy, dynamicznie tworzą definicje drzew raportowania w aplikacji Raportowanie finansowe. Prostym sposobem usprawnienia konsolidacji jest dodanie hierarchii organizacyjnej do raportu w module Raportowanie finansowe. Na podstawie daty raportu aplikacja Raportowanie finansowe wybierze hierarchię organizacyjną na dzień wejścia w życie lub wcześniej, jak pokazano na poniższej ilustracji.

![Dynamiczne tworzenie definicji drzewa raportowania](./media/dynamically-create-reporting-tree-definitions.png "Dynamiczne tworzenie definicji drzewa raportowania")

## <a name="consolidations-that-involve-eliminations"></a>Konsolidacje obejmujące eliminacje
Częstym składnikiem procesu konsolidacji są transakcje eliminacji. W tym przykładzie podczas konsolidacji jest eliminowanych pięć kont: 142600, 211400, 401420, 401180 i 510820. Firmy mogą inaczej skonfigurować swoje konta międzyfirmowe. Na przykład niektóre firmy ustawiają ostatnią cyfrę jako 9, jeśli konto jest używane w transakcjach międzyfirmowych. Niezależnie od wybranej metody znajomość kont międzyfirmowych pozwala wyświetlać eliminacje w skonsolidowanych sprawozdaniach finansowych.

Na poniższej ilustracji przedstawiono definicję kolumny dla skonsolidowanego rachunku zysków i strat. Dla każdej firmy za pomocą filtru wymiaru zdefiniowano trzy międzyfirmowe konta wynikowe. Kolumna D zawiera konta eliminacji tylko dla firmy USMF, a kolumna E zawiera eliminacje tylko dla firmy DEMF. Obie kolumny — D i E — są skonfigurowane tak, aby **nie** były drukowane w sprawozdaniu finansowym.

![Definicja kolumny w skonsolidowanym rachunku zysków i strat](./media/column-definition-consolidated-income-statement.png "Definicja kolumny w skonsolidowanym rachunku zysków i strat")

Podczas generowania raportu kwoty eliminacji są obliczane w kolumnach F, G i H, a następnie sumowane w kolumnie I. Kolumna J pokazuje kwoty skonsolidowane. Te skonsolidowane kwoty wykluczają eliminacje dla firm USMF, USRT i DEMF.

> [!TIP]
> Utwórz drugi raport, który pokazuje tylko wpisy eliminacji, i używaj go w grupie raportów zawierającej Twój skonsolidowany raport. Dzięki temu będziesz mieć wszystkie informacje niezbędne do tworzenia wszystkich potrzebnych wpisów w arkuszach.

Ilustracja poniżej przedstawia skonsolidowany raport.

![Skonsolidowany raport rachunku zysków i strat](./media/consolidated-report-income-statement.png "Skonsolidowany raport rachunku zysków i strat")

Bez względu na fakt, czy używasz kont, wymiarów, czy obu tych obiektów, moduł Raportowanie finansowe pozwala wyfiltrować wpisy eliminacji przy użyciu funkcji filtrowania wymiarów.

## <a name="minority-interest"></a>Udział mniejszościowy
Firma może być właścicielem tylko pewniej części innej firmy. W takiej sytuacji podczas tworzenia skonsolidowanego raportu ważne jest, aby uwzględnić tylko procent, którego firma jest właścicielem. Aplikacja Raportowanie finansowe oferuje wiele sposobów wyświetlania udziału mniejszościowego, w zależności od preferencji użytkownika. Jednym ze sposobów jest używanie procentowej akumulacji w definicji raportu drzewa. Innym sposobem jest pokazanie udziału mniejszościowego jako osobnego wiersza w raporcie.

### <a name="using-the-reporting-tree-definition"></a>Używanie definicji drzewa raportowania
W definicji drzewa raportowania wprowadź procent własności w kolumnie **Zestawienie (%)** (kolumna H), jak pokazano na poniższej ilustracji. Podczas generowania raportu ta wartość procentowa będzie używana do obliczania kwoty skonsolidowanej. W tym przykładzie Contoso jest właścicielem tylko 80 procent firmy Contoso Niemcy. W kolumnie **Zestawienie (%)** można wprowadzić wartość **80** lub **,8**, a do poziomu skonsolidowanego zostanie zaliczony udział 80 procent.

> [!NOTE]
> Ten procent własności można zastosować do dowolnej jednostki raportowania, nie tylko do poziomu firmy. 

![Używanie wartości procentowej w definicji drzewa raportowania](./media/Using-reporting-tree-definition-percentage.png "Używanie wartości procentowej w definicji drzewa raportowania")

Podczas generowania raportu raport o firmie Contoso Niemcy będzie pokazywał 100-procentowy udział w kwocie sprzedaży, a 80 procent kwoty zostanie przydzielone i akumulowane na skonsolidowanym poziomie sprzedaży.

Jeśli firma jest właścicielem mniej niż 1% innej firmy, można zaznaczyć pole wyboru **Zezwalaj na zestawienie poniżej 1%** na karcie **Opcje dodatkowe** na stronie **Ustawienia raportu**, jak pokazano na poniższej ilustracji. W tym przypadku wartości w kolumnie **Zestawienie (%)** w drzewie raportowania będą traktowane jako mniejsze niż 1%. Na przykład jeśli wpiszesz **,8**, do poziomu skonsolidowanego zostanie zakumulowana wartość 0,8 procenta, a nie 80%. Alternatywnie ten sam efekt można uzyskać poprzez pozostawienie wyczyszczonego pola wyboru **Zezwalaj na zestawienie poniżej 1%**, a wpisanie wartości **,008** w kolumnie **Zestawienie (%)**.

![Opcje konfigurowania raportowania](./media/reporting-setting-options.png "Opcje konfigurowania raportowania")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>Wyświetlanie własności jako oddzielnego wiersza w raporcie skonsolidowanym
Inną opcją przedstawiania udziału mniejszościowego jest wykazywanie 100 procent spółki zależnej w każdym wierszu w raporcie, ale odjęcie części przypadającej na udział niekontrolujący od dochodu netto.

Jak pokazano na poniższej ilustracji, do obliczania udziału mniejszościowego w raportach finansowych można użyć instrukcji **IF THEN ELSE** i ograniczenia kolumny w definicji wiersza.

![Wyświetlanie własności jako oddzielnego wiersza w skonsolidowanym raporcie](./media/Showing-ownership-separate-row-consolidated-report.png "Wyświetlanie własności jako oddzielnego wiersza w skonsolidowanym raporcie")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Wiele planów kont w różnych firmach
Często różne firmy mają różne plany kont, ale mimo to chcą generować skonsolidowane sprawozdania finansowe. W takiej sytuacji aplikacja Raportowanie finansowe może służyć do konsolidowania danych, co pozwoli wygenerować skonsolidowane sprawozdania finansowe. Poniżej przedstawiono ogólne czynności, jakie należy wykonać w celu konsolidowania, gdy w firmach istnieją różne plany kont.

1. Utworzenie definicji wiersza mającej wiele połączeń z wymiarami finansowymi. Powinno istnieć jedno połączenie dla każdego planu kont.
2. Użycie ograniczenia jednostki raportowania w definicji kolumny w celu przypisania każdej firmy do odpowiedniej kolumny.


W każdym wierszu w definicji wiersza można dodać wiele łączy do wymiarów finansowych dla każdego unikatowego planu kont firmy. Na poniższej ilustracji firma USMF używa zbioru kont podanego w pierwszej kolumnie **Łącze do wymiarów finansowych** (kolumna J), a firma DEMF używa kont z drugiej kolumny **Łącze do wymiarów finansowych** (kolumna K).

> [!TIP]
> Aby uzyskać więcej informacji o komórce **Łącze do wymiarów finansowych**, zobacz Określanie komórki Łącze do wymiarów finansowych.

![Pierwsze łącze od zbioru kont do wymiarów finansowych](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Pierwsze łącze od zbioru kont do wymiarów finansowych")

W drzewie raportowania można określić, które łącze do wymiarów finansowych z definicji wiersza ma być używane dla każdej firmy. Wybierz definicję wiersza w kolumnie E, a następnie wybierz odpowiednie łącze wiersza w kolumnie F, jak pokazano na poniższej ilustracji.

![Używane łącze do wymiarów finansowych z definicji wiersza](./media/link-financial-dimensions-row-definition-used.png "Używane łącze do wymiarów finansowych z definicji wiersza")

> [!TIP]
> Podczas tworzenia łączy do wymiarów finansowych należy użyć opisu do identyfikowania firm, do których stosuje się każde łącze. W ten sposób można łatwiej wybrać właściwą firmę podczas tworzenia drzewa raportowania. W definicji kolumny pole **Jednostka raportowania** pozwala ograniczyć każdą kolumnę do jednostki drzewa raportowania, dzięki czemu można wyświetlać dane obok siebie. Jeśli nie wskażesz konkretnej firmy w kolumnie, zostaną wyświetlone skonsolidowane dane wszystkich firm.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Różne kalendarze obrachunkowe w różnych firmach
Różne firmy mogą mieć różne kalendarze obrachunkowe, ale mimo to podlegać obowiązkowi generowania skonsolidowanych sprawozdań finansowych. Istnieją dwa sposoby konsolidowania, gdy w firmach istnieją różne okresy obrachunkowe:

- Utworzenie definicji kolumny oraz użycie okresu i roku w celu przypisania odpowiednich okresów dla każdej firmy.
- W oknie **Ustawienia** \> **Inne** \> **Opcje dodatkowe** określ, czy chcesz konsolidować przy użyciu daty zakończenia okresu, czy numer okresu.

Podczas projektowania definicji kolumny dla wielu firm mających różne okresy obrachunkowe trzeba rozważyć, która firma zostanie przypisana do pola **Nazwa firmy** w definicji raportu. Kalendarz obrachunkowy tej firmy będzie stanowić podstawowy kalendarz obrachunkowy w definicji raportu. Na przykład w poniższej tabeli przedstawiono konfigurację okresów obrachunkowych dla firm USMF i INMF. W raportach skonsolidowanych chcesz używać kalendarza obrachunkowego firmy USMF. Kolumna „Mapowanie” pokazuje odnośne okres i rok dla każdej firmy, jeśli raport jest generowany na dzień 30 czerwca 2018 r.

| Firma   | Rok obrachunkowy                                  | Mapowanie                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Rok obrachunkowy, od 1 lipca do 30 czerwca          | Okres 12, rok obrachunkowy 2018 | 
| INMF      | Rok kalendarzowy, od 1 stycznia do 31 grudnia | Okres 6, rok obrachunkowy 2018  |

Na poniższej ilustracji firma USMF jest określona w polu **Nazwa firmy** w definicji raportu. W związku z tym kalendarz obrachunkowy firmy USMF będzie stanowić podstawowy kalendarz obrachunkowy. W tym przykładzie podczas generowania raportu na dzień 30 czerwca 2018 r. firma USMF będzie używać okresu PODSTAWOWY, który jest zdefiniowany jako okres 12 w definicji raportu. Firma INMF będzie używać okresu PODSTAWOWY- 6, czyli okresu 6. Obie kolumny będą zawierały dane dla czerwca 2018 r.

![Okres podstawowy raportu](./media/report-base-period.png "Okres podstawowy raportu")

Poniższa ilustracja pokazuje opcje w definicji raportu pozwalające wybrać, czy do konsolidacji jest używany numer okresu, czy data zakończenia okresu.

![Opcje w definicji raportu dotyczące wyboru numeru okresu](./media/options-report-definition-period-number.png "Opcje w definicji raportu dotyczące wyboru numeru okresu")

## <a name="business-unit-consolidations"></a>Konsolidacje jednostek biznesowych
W tym temacie dotąd skupialiśmy się na używaniu definicji drzewa raportowania i hierarchii organizacyjnych w aplikacji Raportowanie finansowe na potrzeby konsolidacji. Drzewa raportowania można także używać do tworzenia raportów konsolidacyjnych jednostek biznesowych, takich jak raporty o sprzedaży lub działalności na całym świecie. Raporty te są typowym wymaganiem. Aby je utworzyć, zaznacz firmę i wymiar dla każdej jednostki, dla której chcesz dokonać konsolidacji. Na przykład na poniższej ilustracji akumulacja dla jednostek biznesowych odbywa się przez powtarzanie każdej firmy w kolumnie **Firma** (kolumna A) oraz identyfikowanie grupy wartości wymiaru Dział dla każdej firmy w kolumnie **Wymiary** (kolumna D).

![Raporty konsolidacyjne jednostek biznesowych](./media/business-unit-consolidation-reports.png "Raporty konsolidacyjne jednostek biznesowych")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Konsolidacje obejmujące różne waluty raportowania
Moduł Raportowanie finansowe oferuje większą elastyczność podczas przeglądania danych rzeczywistych, budżetowych oraz z zakresu kontroli i planowania budżetu w wielu walutach. Dzięki wprowadzeniu kluczowych danych konfiguracyjnych nie trzeba wykonywać żadnych dodatkowych czynności konfiguracyjnych w aplikacji Raportowanie finansowe w celu wyświetlania jakichkolwiek raportów, w dowolnej walucie, w dowolnym momencie, dla dowolnego użytkownika.

### <a name="prerequisites"></a>Wymagania wstępne
W celu poprawnego obliczania przeliczonych sald moduł Raportowanie finansowe wymaga, aby kategoria **Konto dochodów zatrzymanych** była przypisana do konta dochodów zatrzymanych na liście **Konto główne**. Moduł Raportowanie finansowe nie obsługuje księgowania na koncie dochodów zatrzymanych. Jeśli transakcje są księgowane na koncie dochodów zatrzymanych, przeliczone salda nie będą prawidłowo obliczane. Zalecamy, aby użytkownicy skonfigurowali dodatkowe konto dochodów zatrzymanych w celu księgowania korekt na koncie dochodów zatrzymanych.

Na koncie głównym na skróconej karcie **Raportowanie finansowe** dla każdego konta należy skonfigurować pola **Typ kursu wymiany dla raportowania finansowego** i **Typ przeliczania waluty**, jak pokazano na ilustracji poniżej. To zadanie można wykonać osobno dla każdego konta lub też można użyć szablonów kont w celu łatwiejszego rozpowszechnienia zmian.

- W polu **Typ kursu wymiany dla raportowania finansowego** wybierz typ kursu wymiany zawierający waluty i kursy wymiany, której chcesz zastosować do konta. Ta tabela walut i kursów wymiany zostanie zastosowana do rzeczywistych danych w aplikacji Raportowanie finansowe.
- W polu **Typ przeliczania waluty** wybierz metodę obliczania kursu wymiany dla konta. Ta metoda będzie stosowana do danych rzeczywistych i budżetowych w module Raportowanie finansowe.

![Konta główne w aplikacji Raportowanie finansowe](./media/Financial-reporting-main-accounts.png "Konta główne w aplikacji Raportowanie finansowe")

W przypadku danych budżetu, kontroli budżetu i planowania budżetu typ kursu wymiany definiuje się na stronie **Księga**. Ta tabela będzie używana do ściągania kursów wymiany na podstawie typu przeliczania waluty przypisanego do konta.

### <a name="currency-translation-methods"></a>Metody przeliczania waluty
Istnieją cztery opcje obliczania kursów wymiany w module Raportowanie finansowe:

- **Średnia ważona** — ta metoda jest używana najczęściej dla kont wynikowych. Wykorzystuje następujący wzór:

    (kurs wymiany x liczba dni obowiązywania) / dni w okresie

- **Średnia** — ta metoda jest używana alternatywnie dla kont wynikowych. Wykorzystuje następujący wzór:

    suma kursów wymiany ÷ liczba kursów wymiany

- **Waluta** — ta metoda jest używana najczęściej dla kont bilansowych. Używanym kursem wymiany jest kurs z dnia nie późniejszego niż dzień wygenerowania raportu lub kolumny w aplikacji Raportowanie finansowe.
- **Data transakcji** — ta metoda jest używana w przypadku kont środków trwałych. Używany kurs wymiany pochodzi z dnia nabycia środka trwałego. Jeśli kurs nie jest wprowadzony dla danego dnia, zostanie użyty kurs wcześniejszy, wprowadzony najbliższej daty nabycia środka trwałego.

### <a name="report-designer-options-for-currency-translation"></a>Opcje Projektanta raportów służące do przeliczania walut
W aplikacji Raportowanie finansowe każdy raport może być prezentowany przy użyciu dowolnej liczby walut raportowania. Następujące pola w definicji raportu obsługują tę funkcjonalność:

- Sekcja **Informacje dotyczące walut** na stronie **Definicja raportu**. Ta część przedstawia walutę, w jakiej są wyświetlane wartości podczas generowania raportu.
- Nowe pole wyboru **Uwzględnij wszystkie waluty raportowania**. Gdy to pole wyboru jest zaznaczone, raport w każdej walucie raportowania zostanie dodany do kolejki raportów po wygenerowaniu raportu w walucie funkcjonalnej firmy. Jeśli to pole wyboru jest wyczyszczone, nadal można wybrać walutę raportowania w przeglądarce sieci Web. W takim przypadku waluta raportowania będzie przetwarzana tylko wtedy, gdy zostanie wybrana.

Opcje w definicji raportu pozwalają łatwo przeliczać walutę raportu na wszystkie waluty raportowania. Dzięki temu można wyeliminować powtarzające się definicje raportów, które różnią się jedynie używaną walutą. Jeśli potrzebujesz raportu, który pokazuje wiele walut obok siebie, można nadal używać pola **Opcja wyświetlania waluty** na stronie **Definicja kolumny** w celu przeliczania tylko tej kolumny raportu na alternatywną walutę raportowania.

### <a name="currency-translation-adjustment"></a>Korekta przeliczenia waluty
Korekta przeliczenia waluty (CTA) to różnica między kwotami według kursów używanych do obliczania kont bilansowych a kwotami po kursach używanych dla kont rachunku wyników. Różnica spowoduje, że bilans przestanie mieć równe wartości po obu stronach. W aplikacji Raportowanie finansowe CTA można obliczać na dwa sposoby:

- Użycie strony **Korygowanie zaokrągleń** w definicji wiersza, jak pokazano na poniższej ilustracji.

    ![Korekty zaokrągleń w ramach korygowania przeliczenia walut](./media/Currency-translation-adjustment-rounding-adjustments.png "Korekty zaokrągleń w ramach korygowania przeliczenia walut")

    Gdy określisz wiersz mający pokazywać korektę zaokrąglenia (CTA), wiersz sumy aktywów, wiersz sumy zobowiązań i kapitału własnego oraz zadowalającą wartość progową, aplikacja Raportowanie finansowe będzie obliczać różnicę i umieszczać ją w żądanym wierszu. Zostanie utworzony wiersz o nazwie **Korygowanie zaokrągleń** i będzie wyświetlany podczas przechodzenia do szczegółów, jak pokazano na poniższej ilustracji.

    ![Wyświetlanie korekty zaokrąglenia w trakcie przechodzenia do szczegółów](./media/rounding-adjustment-drill-down.png "Wyświetlanie korekty zaokrąglenia w trakcie przechodzenia do szczegółów")

- Umieszczenie wszystkich kont — od aktywów po wydatki — w granicach zakresu/ Jak pokazano na poniższej ilustracji, różnica będzie tą samą kwotą, co wartość korekty zaokrąglenia (CTA). W związku z tym można jej używać jako sumy kontrolnej w celu uzyskania pewności, że strona korekty zaokrąglenia nie uwzględnia żadnych pominiętych sald kont.

    ![Kontrola formularza korekty zaokrąglenia](./media/rounding-adjustment-form-check.png "Kontrola formularza korekty zaokrąglenia")

### <a name="balance-calculation-approach"></a>Metoda obliczania salda
Aby uzyskać prawidłowo przeliczone kwoty podczas używania walut, aplikacja Raportowanie finansowe wykorzystuje następujące metody obliczania sald:

- **Średnia ważona i Średnia** — każdy okres jest obliczany według swojej średniej ważonej, a następnie sumowany według kolumn takich jak kwartał czy okres od początku roku.
- **Historyczne** — każde konto, które używa metody przeliczania historycznego, zawsze wraca do daty transakcji. Jeśli z transakcją jest skojarzona data nabycia, to właśnie ona jest używana do ustalenia kursu wymiany. Każdy okres jest następnie sumowany i zapisywany, aby przyspieszyć obliczanie.
- **Bieżący** — kolumny obliczane i kolumny sum, takie jak kolumny kwartału i okresu od początku roku, są obliczane po kursie kasowym określonym w kolumnie lub w raporcie. Na przykład kolumna **Kwartał 1** będzie używać kursu z 31 marca, jeśli jest używany rok kalendarzowy.

## <a name="additional-resources"></a>Dodatkowe zasoby

Aby uzyskać więcej informacji o konsolidacjach i przeliczaniu walut, zobacz temat nadrzędny tego tematu — [Konsolidacje finansowe i przeliczenia walut](./financial-consolidations-currency-translation.md).

Aby uzyskać więcej informacji na temat sposobu wprowadzania szczegółowych informacji o konsolidacji w trybie online, zobacz [Konsolidacja online](./consolidate-online.md).
