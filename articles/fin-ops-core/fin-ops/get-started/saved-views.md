---
title: Zapisane widoki
description: W tym artykule opisano sposób korzystania z funkcji zapisanych widoków.
author: jasongre
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 571a4f403da0d20256f788c791cab273827c91b5
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799499"
---
# <a name="saved-views"></a>Zapisane widoki

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

[!INCLUDE [PEAP](../../../includes/peap-1.md)]

## <a name="introduction"></a>Wprowadzenie

Personalizacja odgrywa ważną rolę w umożliwieniu użytkownikom i organizacjom optymalizacji doświadczenia użytkownika stosownie do ich potrzeb. Aby uzyskać szczegółowe informacje dotyczące personalizacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).

Tradycyjna personalizacja pozwala użytkownikom mieć tylko jeden zestaw personalizacji na stronę. Funkcja **Zapisane widoki** rozwijaja personalizację na kilka ważnych sposobów:

- Widoki umożliwiają użytkownikom posiadanie więcej niż jednego nazwanego zestawu personalizacji na formularz i ich szybkie przełączanie stosownie do potrzeb. Umożliwia to użytkownikowi tworzenie wielu zoptymalizowanych widoków strony, z których każdy jest dostosowany do potrzeb wykonywania określonego zadania biznesowego. 
- Widoki utworzone dla określonych typów stron mogą również zawierać filtry dodane przez użytkownika lub kryteria sortowania, które umożliwiają użytkownikom szybkie odtworzenie często filtrowanych zestawów danych. Więcej szczegółów znajduje się w sekcji [Jakie strony obsługują widoki](saved-views.md#what-pages-support-views). 
- Widoki mogą być publikowane dla użytkowników w określonych rolach zabezpieczeń i określonych firmach. Dlatego każdy użytkownik, który ma określoną rolę i dostęp w określonej firmie, może uzyskać dostęp do tego widoku i korzystać z niego, nawet jeśli ten użytkownik ma uprawnienia do personalizacji. Ta możliwość publikowania pozwala organizacjom na definiowanie firmowych, standardowych widoków zoptymalizowanych pod kątem ich działalności. Więcej informacji zawiera sekcja [Zarządzanie personalizacjami na poziomie organizacyjnym za pomocą widoków](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).
- W przeciwieństwie do tradycyjnej personalizacji widoki nie są automatycznie zapisywane, gdy użytkownik wykonuje jawne personalizacje lub filtruje listę. Jawne zapisy są wymagane, aby zapewnić użytkownikom elastyczność tworzenia widoku przed lub po wprowadzeniu zmian skojarzonych z tym widokiem. To wymaganie zapewnia również, że definicje widoków nie zostaną przypadkowo zmienione przez filtry lub personalizacje, które nie są przeznaczone do długotrwałego użytku. Elementy, które system automatycznie zapisuje jako część typowego wykorzystania strony (na przykład szerokości kolumn lub stan rozwiniętych lub zwiniętych sekcji), zostaną zapisane dla każdego widoku.
- Widoki można dodawać do obszarów roboczych jako kafelki, listy lub łącza. Dlatego filtrowany zbiór danych może być układany w obszarze roboczym, a użytkownicy mogą kojarzyć zbiór personalizacji, które są odpowiednie dla tego zbioru danych z kafelkiem lub łączem.

## <a name="switching-between-views"></a>Przełączanie między widokami

Po udostępnieniu widoków dla środowiska w górnej części każdej strony obsługującej widoki będzie znajdować się zwinięty element sterujący selektora widoku, który zawiera nazwę bieżącego widoku.

Istnieją dwa warianty wielkości selektora widoków: 

- **Duże selektory widoków** - strony z dobrze widoczną listą będą miały duży selektor widoków z kilku powodów. Co najważniejsze, większy selektor widoku wskazuje strony, na których widok może zawierać filtry i sortowanie zdefiniowane przez użytkownika. Ponieważ filtry i sortowanie są zawarte w widokach, większy rozmiar selektora jest również uzasadniony, ponieważ nazwy widoków będą często najlepszym opisem danych wyświetlanych na ekranie, a oczekuje się, że użytkownicy będą częściej przełączać się między widokami na tych typach stron. Grupowanie w siatce może być także zapisane w widokach na stronie z dużymi selektorami widoków. 
    
    [![Selektor widoku obsługujący modyfikacje kwerend w widoku.](./media/views-largeViewSelector.png)](./media/views-largeViewSelector.png)

- **Małe selektory widoków** - Wszystkie inne strony pełnoekranowe (z wyjątkiem obszarów roboczych i pulpitu nawigacyjnego) mają mniejszy selektor widoku, który pojawia się obok podpisu strony. Widoki na tych stronach obejmują tylko personalizacje, a nie filtry zdefiniowane przez użytkownika. Na tych stronach podpis lub tytuł rekordu często są najważniejszymi informacjami w górnej części strony. Mniejszy rozmiar selektora widoku odzwierciedla również niższą częstotliwość przełączania widoku, której oczekuje się na tych stronach. 
    
    [![Mały selektor widoku, który nie obsługuje modyfikacji zapytań w widoku.](./media/views-smallViewSelector.png)](./media/views-smallViewSelector.png)
 
Wybór nazwy widoku powoduje otwarcie selektora widoku i wyświetlenie listy dostępnych widoków tej strony.

Jeśli funkcja **Ulepszona obsługa osób prawnych dla zapisanych widoków** jest włączona, selektor widoków pokazuje dostępne widoki w dwóch sekcjach. W pierwszej sekcji są przedstawiane wszystkie widoki specyficzne dla bieżącej firmy, a w drugiej widoki dostępne dla wszystkich firm. Pierwsza sekcja jest widoczna tylko wtedy, gdy istnieją widoki specyficzne dla firmy dla strony.

- **Widok standardowy** - widok **Standardowy** jest gotowym widokiem strony bez zastosowania personalizacji.
- **Widoki osobiste** - widoki bez kłódki przedstawiają widoki osobiste danego użytkownika. Są to widoki utworzone przez tego użytkownika lub otrzymane przez niego od administratora.
- **Zablokowane widoki** - niektóre widoki (na przykład widok **Standardowy** i wszystkie widoki opublikowane w roli) mają obok nich symbol kłódki w selektorze widoków. Ten symbol wskazuje, że nie można edytować tych widoków. Jednak zmiany, które odzwierciedlają użycie strony, są zapisywane automatycznie. Te zmiany obejmują zmiany szerokości kolumny siatki oraz zmiany stanu rozwiniętego lub zwiniętego skróconej karty. Jeśli użytkownik ma uprawnienia do personalizacji, może jednak utworzyć widok osobisty oparty na zablokowanym widoku używając akcji **Zapisz jako**.
- **Nowe widoki** - opublikowane widoki, które nie zostały jeszcze otwarte, są wyróżnione iskrą na lewo od nazwy widoku.

Aby przełączyć się do innego widoku, najpierw należy otworzyć selektor widoku, a następnie wybrać widok, który ma zostać załadowany. 

## <a name="creating-and-modifying-views"></a>Tworzenie i modyfikowanie widoków

W przeciwieństwie do tradycyjnej personalizacji widoki nie są automatycznie zapisywane, gdy użytkownik personalizuje stronę lub gdy użytkownik stosuje filtr do listy lub ją sortuje. Do zapisania tych zmian w widoku wymagana jest jawna akcja. Ten wymóg zapewnia użytkownikom elastyczność tworzenia widoku przed lub po wprowadzeniu zmian skojarzonych z tym widokiem. Ponadto gwarantuje, że definicje widoków nie zostaną przypadkowo zmienione przez filtry jednorazowe lub personalizacje. Zwróć uwagę, że typowe elementy wykorzystania strony (na przykład szerokości kolumn lub stan rozwinięty lub zwinięty sekcji) są automatycznie zapisywane w bieżącym widoku, nawet w przypadku zablokowanych widoków.

Aby upewnić się, że aktualny stan widoku jest znany, gdy zaczynasz zmieniać widok przez personalizację lub filtrowanie, obok nazwy bieżącego widoku pojawi się gwiazdka (\*). Ten symbol wskazuje, że oglądana jest niezapisany, zmodyfikowana wersja tego widoku.

[![Niezapisane zmiany w widoku.](./media/views-unsavedChanges.png)](./media/views-unsavedChanges.png)

Jeśli chcesz zapisać te zmiany, wykonaj następujące kroki.

1. Wybierz nazwę widoku, aby otworzyć selektor widoku.
2. Aby zmodyfikować istniejący widok, wybierz **Zapisz**. Zauważ, że ta akcja nie jest dostępna w widokach zablokowanych. 
3. Aby utworzyć nowy widok:

    1. Wybierz opcję **Zapisz jako**. 
    2. W okienku **Zapisz widok jako** wprowadź nazwę oraz, opcjonalnie, opis widoku.
    3. Jeśli ten widok ma być domyślnym widokiem, wybierz pozycję **Przypnij jako domyślny**. Więcej informacji o widokach domyślnych zawiera następna sekcja [Zmienianie widoku domyślnego](#changing-the-default-view). 
    4. Jeśli włączona jest funkcja **Usprawniona obsługa zapisanych widoków dla firmy**, możesz wybrać, czy ten widok ma być dostępny dla wszystkich podmiotów prawnych, czy tylko dla ich części.
    5. Wybierz opcję **Zapisz**.

## <a name="changing-the-default-view"></a>Zmienianie domyślnego widoku

Widok domyślny to widok, który system próbuje otworzyć po pierwszym otwarciu strony. Należy ustawić widok domyślny na widok, którego spodziewasz się najczęściej używać. 

> [!NOTE]
> - W podstawowej funkcji **Zapisane widoki** istnieje jeden globalny widok domyślny dla wszystkich firm. Jeśli zmienisz widok domyślny, ten widok zostanie domyślnie otwarty, niezależnie od firmy, w której się znajdujesz.
> - Gdy włączona jest funkcja **Ulepszona obsługa zapisanych widoków osób prawnych**, każda osoba prawna może mieć własny widok domyślny dla każdej strony.

Aby zmienić domyślny widok strony, wykonaj następujące czynności:

1. Przełącz się na widok, który jest używany jako domyślny. 
2. Wybierz nazwę widoku, aby otworzyć selektor widoku. 
3. Naciśnij przycisk **Więcej**, a następnie wybierz opcję **Przypnij jako domyślny**.

Podczas tworzenia nowego widoku (przy użyciu akcji **Zapisz jako**) można też ustawić nowy widok jako domyślny, włączając opcję **Przypnij jako domyślny** przed zapisaniem widoku.

> [!WARNING]
> W niektórych przypadkach zapytanie skojarzone z widokiem domyślnym nie jest uruchamiane przy pierwszym otwarciu strony. Na przykład, jeśli otworzysz stronę za pomocą kafelka, zapytanie kafelka zostanie uruchomione niezależnie od zapytania skojarzonego z widokiem domyślnym. Ponadto, jeśli otworzysz stronę z widokiem **Standardowym**, który ma już zdefiniowane zapytanie, oryginalne zapytanie zostanie uruchomione zamiast zapytania widoku domyślnego. W takim przypadku otrzymasz komunikat informacyjny, gdy widok zostanie załadowany za pomocą wbudowanej akcji, która pozwala załadować zapytanie domyślnego widoku bezpośrednio. Jeśli użytkownik przełączy widoki po załadowaniu strony, zapytanie o widok powinno być możliwe do uruchomienia zgodnie z oczekiwaniami. 

## <a name="managing-personal-views"></a>Zarządzanie widokami osobistymi

Okno dialogowe **Zarządzaj moimi widokami** zawiera podstawowe funkcje obsługi widoków osobistych i kolejności widoków w selektorze widoków. Jeśli chcesz otworzyć tę stronę, wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków, wybierz opcję **Więcej**, a następnie wybierz opcję **Zarządzaj moimi widokami**.

Jeśli jest włączona funkcja **Usprawniona obsługa zapisanych widoków dla firmy**, w sekcji **Moje widoki** okna dialogowego **Zarządzaj moimi widokami** są wyświetlane dostępne widoki dla strony w sekcjach. Wszystkie widoki specyficzne dla bieżącej firmy są pokazywane w osobnej sekcji. Sekcja **Widoki globalne** jest zawsze wyświetlana, dzięki czemu można zarządzać widokami dostępnymi dla strony we wszystkich firmach. 

Dostępny zestaw akcji dla listy dostępnych widoków tej strony jest następujący.

- **Zmień widok domyślny** - aby wybrany widok został widokiem domyślnym tej strony, należy użyć opcji **Przypnij jako domyślny**. Jeśli jest włączona funkcja **Obsługa importowania firmy dla zapisanych widoków** w sekcji **Globalne widoki** można ustawić widok jako domyślny dla bieżącej firmy lub wszystkich firm.
- **Zmień kolejność widoków** - za pomocą akcji **Przenieś w górę** i **Przenieś w dół** można zmienić kolejność widoków na liście.
- **Zmień nazwę widoku** - akcja **Zmień nazwę** pozwala zmienić nazwę wybranego widoku osobistego. W przypadku widoków zablokowanych ta akcja jest wyłączona. 
- **Usuń widok** - akcja **Usuń** umożliwia trwałe usunięcie wybranego widoku z danej strony. Jeśli widok został usunięty, nie można go odtworzyć.

Zmiany wprowadzone w tym oknie dialogowym zaczną obowiązywać po naciśnięciu przycisku **Aktualizuj**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Zarządzanie personalizacjami na poziomie organizacyjnym za pomocą widoków

W tej sekcji opisano sposób pewne różnice w zarządzaniu personalizacją z i bez funkcji **Zapisanych widoków**, co ułatwia zapoznanie się z zapisanymi widokami w celu usprawnienia zarządzania personalizacjami na poziomie organizacyjnym.

Bez widoków administratorzy musieli zastosować zestaw personalizacji strony do użytkownika lub grupy użytkowników za pomocą strony Personalizacja. Jeśli ci użytkownicy mieli uprawnienia do personalizacji, personalizacje zostały zastosowane do tej strony. Nie było jednak możliwe zakazanie użytkownikom dalszego personalizowania strony, czyli organizacja nie mogła sprawić, aby jej użytkownicy mieli spójny interfejs użytkownika. Jeśli dowolny z tych użytkowników nie miał uprawnień do personalizacji, personalizacje wysłane mu przez administratora nie były ładowane. Ponadto, jeśli w organizacji zostali zatrudnieni nowi użytkownicy, administratorzy musieli im ręcznie załadować zestaw personalizacji. Nie było automatycznego mechanizmu określania pewnego zestawu personalizacji, który powinien być dostępny dla użytkownika w danej roli.

Przy użyciu funkcji **Zapisanych widoków** zarządzanie organizacyjne personalizacjami jest znacznie łatwiejsze, głównie ze względu na możliwość publikowania widoków w grupach użytkowników. Po opublikowaniu widoku każdy użytkownik, który ma jedną z zdefiniowanych ról zabezpieczeń ma dostęp do określonych firm, może wyświetlać ten widok i korzystać z niego, nawet jeśli ten użytkownik nie ma dostępu do personalizacji. Pomimo że każdy użytkownik ma kopię opublikowanego widoku, do której są stosowane elementy użycia strony żaden użytkownik nie może zapisać jawnych personalizacji lub aktualizacji kwerendy w opublikowanym widoku. Innymi słowy, opublikowane widoki są zablokowane. Ponadto, jeśli nowi użytkownicy mają przypisane role w firmach, dla których widoki zostały opublikowane, będą automatycznie widzieli widoki skojarzone z ich rolami i firmami. Administrator nie wymaga żadnych dodatkowych akcji. Podobnie, jeśli użytkownicy zmienią role w organizacji lub mają dostęp do różnych firm, mogą nie mieć już dostępu do widoków, które zostały wcześniej opublikowane. Administrator nie musi wykonywać żadnych dodatkowych działań.

Aktualizacje opublikowanego widoku mogą być łatwo dystrybuowane użytkownikom przez ponowne opublikowanie widoku do odpowiednich ról zabezpieczeń i firm.

Możliwość publikowania umożliwia organizacjom definiowanie standardowych widoków firmowych zoptymalizowanych pod kątem ich działalności skierowanych do użytkowników mających określone role zabezpieczeń.

## <a name="publishing-views"></a>Publikowanie widoków

Podczas procesu publikowania można przypisać widoki do co najmniej jednej roli zabezpieczeń dla co najmniej jednej firmy. Dlatego każdy użytkownik, który ma dostęp do firmy i który jest przypisany do jednej z tych ról, może uzyskiwać dostęp do widoków i korzystać z nich. Jednak użytkownik nie może edytować widoków. Domyślnie administratorzy systemu mają uprawnienia do akcji **Publikuj** w menu rozwijanym selektora widoku. Jednak inni zaufani użytkownicy w organizacji mogą mieć również dostęp do możliwości wyświetlania publikacji za pośrednictwem nowych ról **Administratora zapisanych widoków**.

Aby opublikować widok, należy wykonać następujące kroki:

1. Utwórz i zapisz osobistą kopię widoku, który chcesz opublikować. 
2. Po załadowaniu tego widoku wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków. 
3. Naciśnij przycisk **Więcej**, a następnie wybierz opcję **Publikuj**. Zostanie otwarte okno dialogowe **Publikowanie**.
4. Wprowadź nazwę widoku. Wpisaną nazwę użytkownicy otrzymujący ten widok będą widzieć w selektorach widoku. Nazwy opublikowanych widoków strony muszą być unikatowe. Nazwy publikowanych widoków nie mogą się powtarzać, nawet jeśli są stosowane do różnych list ról lub firm.
5. Jeśli jest włączona funkcja **Obsługa tłumaczeń dla widoków organizacyjnych**, można dodawać tłumaczenia dla swojej nazwy widoku w wielu językach wymaganych przez organizację, wybierając przycisk **Tłumaczenia** obok pola **Nazwa**. Nazwa widoku będzie wyświetlana użytkownikom w ich bieżącym języku. Można również ustawić język domyślny, aby określić tłumaczenie, które będzie wyświetlane użytkownikom, dla których są uruchomione języki bez zdefiniowanego tłumaczenia.
5. Opcjonalnie: wprowadź opis widoku, dzięki czemu użytkownicy otrzymujący ten widok mogą lepiej zrozumieć jego przeznaczenie. 
6. Określ, czy widok powinien być publikowany jako widok domyślny dla wybranych użytkowników. Gdy widok zostanie ustawiony jako widok domyślny, użytkownicy zobaczą go następnym razem, gdy otworzą stronę docelową. Zostanie zmieniony jeden domyślny widok globalny każdego docelowego użytkownika. Jednak użytkownicy nadal będą mogli zmieniać swój widok domyślny po jego opublikowaniu.

    > [!NOTE]
    > Podczas publikowania widoku jako widoku domyślnego należy pamiętać o następującym zachowaniu:
    >
    > - Jeśli widok jest publikowany jako domyślny dla niektórych lub wszystkich firm, zachowanie jest następujące:
    >
    >    - Jeśli jest włączona tylko podstawowa funkcja **Zapisane widoki**, pojedynczy globalny widok domyślny będzie zmieniany dla każdego docelowego użytkownika. 
    >    - Jeśli jest włączona funkcja **Usprawniona obsługa zapisanych widoków dla firmy** i opublikujesz widok dla podzbioru firm, domyślny widok dla tych firm będzie zmieniany dla każdego docelowego użytkownika.
    >
    > - Jeśli użytkownik ma role, w których wiele widoków jest opublikowanych jako widok domyślny, ostatni opublikowany widok będzie używany jako widok domyślny użytkownika. 
    > - Publikowanie nie będzie działać dla przypisań ról wykonanych przy użyciu grup AAD. 

8. Dodaj role zabezpieczeń odpowiadające użytkownikom, do których skierowany jest ten widok. 
9. Określ, czy chcesz opublikować widok dla ról podrzędnych każdej wybranej roli zabezpieczeń. Jeśli tak, zaznacz pole wyboru **Uwzględnij role podrzędne** w wierszu odpowiednich ról zabezpieczeń. Należy zauważyć, że to pole wyboru jest niedostępne w przypadku ról, które nie mają ról podrzędnych.
10. Dodaj firmy, dla których ten widok powinien być dostępny. 

    > [!NOTE]
    > Podczas publikowania widoku dla określonej firmy, ale bez publikowania widoku jako widoku domyślnego, należy wziąć pod uwagę następujące zachowanie:
    >
    > - Jeśli jest włączona tylko podstawowa funkcja **Zapisane widoki**, w selektorze widoku użytkownika dla strony początkowo będzie wyświetlany tylko widok dla określonych firm. Jednak po załadowaniu widoku po raz pierwszy będzie on zawsze wyświetlany w selektorze widoków użytkownika dla strony, niezależnie od firmy.
    > - Jeśli jest włączona funkcja **Usprawniona obsługa zapisanych widoków dla firmy**, w selektorze widoku będzie zawsze pokazywany tylko widok dla określonych firm.

11. Wybierz opcję **Publikuj**.

W niektórych środowiskach może upłynąć trochę czasu (do godziny), zanim użytkownicy zobaczą opublikowany widok.

## <a name="modifying-a-published-view"></a>Modyfikowanie opublikowanego widoku

Po opublikowaniu widoku może się okazać, że użytkownik chce go zmienić. Chociaż nie można wprowadzać zmian w samych opublikowanych widokach, ponieważ są one zablokowane dla wszystkich użytkowników (w tym tych, którzy je opublikowali), to można ponownie opublikować widok, aby dokonać jego aktualizacji.

Jeśli zmiany, które mają zostać wprowadzone do opublikowanego widoku, obejmują tylko parametry publikowania (nazwa i opis widoku lub role zabezpieczeń, dla których jest publikowany widok), należy wykonać następujące czynności:

1. Przełącz się na opublikowany widok z parametrami, które chcesz zaktualizować. 
2. Wybierz opcję **Publikuj ponownie** z menu rozwijanego selektora widoku. Jeśli korzystasz z wersji 10.0.12 lub wcześniejszej, musisz wybrać opcję **Publikuj**, a następnie **Tak**, aby zaktualizować istniejący widok.
3. Zaktualizuj nazwę, opis, role zabezpieczeń i firmy tego widoku. 
4. Wybierz opcję **Publikuj**. Jeśli początkowo zaznaczono ten opublikowany widok jako widok domyślny, będzie on ponownie widokiem domyślnym dla użytkowników po ponownym opublikowaniu. 

Jeśli zmiany w publikowanym widoku obejmują modyfikacje personalizacji lub filtrów skojarzonych z widokiem, należy wykonać następujące czynności.

1. Załaduj opublikowany widok, który chcesz zmienić. 
2. Wprowadź wymagane zmiany w lokalnej wersji roboczej.
3. Wybierz opcję **Publikuj ponownie** z menu rozwijanego selektora widoku.
4. Wybierz opcję **Tak**, aby wskazać, że chcesz opublikować widok wraz z niezapisanymi zmianami. 
5. Dostosuj parametry publikowania, które wymagają korekty, a następnie wybierz opcję **Publikuj**. 

## <a name="managing-published-views"></a>Zarządzanie opublikowanymi widokami

Podobnie jak w przypadku zarządzania widokami osobistymi okno dialogowe **Zarządzaj moimi widokami** oferuje użytkownikom z uprawnieniami do publikowania podstawowe możliwości kontroli nad opublikowanymi widokami tej strony (oprócz ich widoków osobistych). Jeśli chcesz otworzyć tę stronę, wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków, wybierz opcję **Więcej**, a następnie wybierz opcję **Zarządzaj moimi widokami**.

Chociaż wszyscy użytkownicy mają kartę **Moje widoki**, która przedstawia ich osobiste widoki, użytkownicy, którzy mają uprawnienia do publikowania, mają również kartę **Widoki organizacji**, która zawiera wszystkie opublikowane i niepublikowane widoki tej strony. Ponieważ kilku użytkowników może publikować widoki, ważne jest, aby móc zarządzać pełną listą opublikowanych widoków, nawet jeśli nie jesteś użytkownikiem, który opublikował dany widok.

Dostępny zestaw akcji dla listy wszystkich opublikowanych widoków strony jest następujący. 

- **Publikuj ponownie** – akcja **Publikuj ponownie** umożliwia ponowne opublikowanie widoku po zmianie parametrów publikowania (nazwa, opis, role zabezpieczeń).
- **Publikuj** — za pomocą akcji **Publikuj** można opublikować widok, który jest obecnie nieopublikowany. 
- **Cofnięcie publikowania** — aby widok stał się nieaktywny, należy skorzystać z akcji **Cofnięcia publikowania**. Widok będzie nadal dostępny w systemie, ale użytkownicy nie będą widzieć go w selektorze widoków do momentu ponownego opublikowania widoku.
- **Zapisz jako osobisty** – za pomocą akcji **Zapisz jako osobiste** można utworzyć osobistą kopię opublikowanego widoku. Ta możliwość ułatwia zapoznanie się z zawartością widoku, który nie został opublikowany dla Ciebie lub który nie został jeszcze opublikowany. Można go również wykorzystać do edytowania i ponownego publikowania widoku.
- **Usuń** – akcja **Usuń** umożliwia trwałe usunięcie opublikowanego lub nieopublikowanego widoku. Ta akcja również powoduje usunięcie widoku dla wszystkich użytkowników w systemie. Usunięcie opublikowanych widoków obowiązuje po wybraniu przycisku **Zapisz**. Usuniętego widoku nie można odzyskać. 

## <a name="managing-views-globally"></a>Zarządzanie widokami globalnie

Chociaż niektóre funkcje zarządzania znajdują się na każdej stronie, jak wskazano w tym artykule, **administratorzy systemu** i **administratorzy zapisanych widoków** mogą bardziej kompleksowo zarządzać widokami systemu za pośrednictwem strony **Personalizacji**. W szczególności ta strona zawiera następujące sekcje i możliwości: 

- **Opublikowane widoki** – Ta sekcja zawiera listę wszystkich widoków opublikowanych dla organizacji. W tym miejscu można ponownie opublikować widok po skorygowaniu ról zabezpieczeń lub firm, dla których jest wyświetlany widok. Możesz także eksportować, usuwać lub cofać publikację widoków. Można skorzystać z opcji **Zapisz jako osobisty**, aby utworzyć osobistą kopię widoku, co pozwoli na zaktualizowanie widoku lub uzyskanie lepszego zrozumienia jego zawartości. 
- **Nieopublikowane widoki** — Ta sekcja zawiera listę wszystkich widoków organizacji w systemie, które nie są obecnie publikowane. Te widoki najczęściej wchodzą w skład systemu poprzez możliwości importu. Te widoki można publikować, eksportować i usuwać. Akcja **Szybkie publikowanie** dodana w wersji 10.0.12 umożliwia publikowanie wielu widoków z tej sekcji w jednej akcji za pomocą istniejących konfiguracji ról zabezpieczeń i firm. Można skorzystać z opcji **Zapisz jako osobisty**, aby utworzyć osobistą kopię tych widoków, co pozwoli na uzyskanie lepszego zrozumienia ich zawartości.
- **Widoki osobiste** — Ta sekcja zawiera listę widoków, które zostały utworzone przez użytkowników w systemie. Możesz teraz opublikować widok osobisty w organizacji lub skopiować jeden lub więcej z tych widoków do innego użytkownika. Te widoki można również eksportować i usuwać wedle potrzeb.
- **Ustawienia użytkownika** — umożliwia wybranie użytkownika, który ma być przeglądany, lub dostosowanie możliwości używania personalizacji dla całego systemu lub konkretnych stron odwiedzonych przez użytkownika. Użytkownik może przeglądać i korzystać z personalizacji użytkownika w systemie. Można również usunąć wszystkie personalizacje dla tego użytkownika lub zresetować objaśnienia funkcji dla użytkownika. Jeśli objaśnienia funkcji zostaną zresetowane, wszystkie wyskakujące okienka, które wprowadziły nowe funkcje i które poprzednio zwolnił użytkownik, pojawią się ponownie, gdy użytkownik napotka te funkcje następnym razem.
- **Ustawienia systemu** — ta opcja pozwala tymczasowo wyłączyć personalizacje dla wszystkich użytkowników w systemie. W takim przypadku żadne personalizacje nie są stosowane do żadnego użytkownika, a wszystkie strony są resetowane do stanu domyślnego. W przypadku ponownego włączenia personalizacji wszystkie personalizacje zostaną zastosowane ponownie. Można również trwale usunąć wszystkie personalizacje dla wszystkich użytkowników w systemie. Nie jest możliwe odzyskanie personalizacji, które zostały usunięte. Dlatego przed wykonaniem tego zadania należy koniecznie wyeksportować wszystkie personalizacje, które potem możesz chcieć zaimportować.

Użytkownicy, którzy mają dostęp do strony **Personalizacje**, mogą również importować widoki osobiste lub organizacji za pomocą przycisku **Importuj widoki** w okienku akcji. W przypadku widoków organizacyjnych możesz wybrać opcję **Opublikuj natychmiast**, aby udostępnić widoki użytkownikom bez dodatkowej jawnej publikacji.

## <a name="known-issues"></a>Znane problemy

Aby zapoznać się z listą znanych problemów z zapisanymi widokami, zobacz [Tworzenie formularzy, które w pełni wykorzystują zapisane widoki](../../dev-itpro/user-interface/understanding-saved-views.md).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Jak włączyć zapisane widoki w środowisku?

> [!NOTE]
> Funkcja **zapisanych widoków** wymaga włączenia systemu personalizacji w aplikacjach finansowych i operacyjnych. Jeśli personalizacja jest wyłączona dla całego środowiska, widoki zostaną wyłączone nawet po wykonaniu poniższych kroków. 

Funkcję **Zapisane widoki** można włączać i wyłączać za pomocą zarządzania funkcjami w dowolnym środowisku. Po włączeniu zapisane widoki zostaną włączone we wszystkich kolejnych sesjach użytkowników.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Co się dzieje z istniejącymi personalizacjami, gdy są włączone widoki? 

Po włączeniu widoków wszelkie istniejące personalizacje użytkownika i formularza są zapisywane w nowym widoku o nazwie **Mój widok**, który jest automatycznie ustawiany jako widok domyślny. Ma to na celu zapewnienie spójnego środowiska użytkownika przed włączeniem widoków i po nim, z wyjątkiem formantu selektora widoków wyświetlanego w formularzach.

### <a name="what-pages-support-views"></a>Jakie strony obsługują widoki? 

Widoki są dostępne dla większości, ale nie wszystkich stron. Dokładnie rzecz biorąc, widoki są obecnie dostępne na wszystkich stronach pełnoekranowych, z wyjątkiem pulpitów nawigacyjnych. Wyświetlanie obsługi obszarów roboczych jest dostępne za pośrednictwem obsługi **zapisanych widoków dla obszarów roboczych**. Większość stron niepełnoekranowych, które zawierają rozwijane okna dialogowe, odnośniki i ulepszone podglądy, obecnie nie obsługuje widoków. Obsługa wyświetlania okien dialogowych jest dostępna za pośrednictwem funkcji **Obsługa zapisanych widoków dla okien dialogowych**.

### <a name="who-is-allowed-to-publish-views"></a>Kto ma prawo do publikowania widoków?

Tylko administratorzy systemu i użytkownicy przypisani do roli **Administratora zapisanych widoków** mają prawa do publikowania widoków. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Dlaczego nie można zapisać filtrów w widoku? 

Istnieje kilka przyczyn uniemożliwiających zapisanie filtru w widoku: 

- Strona może nie obsługiwać zapisywania filtrów w ramach definicji widoku. Tylko strony z dużymi selektorami widoku umożliwiają zapisywanie personalizacji i modyfikacji kwerend w postaci widoku. Więcej informacji znajduje się w sekcji **Przełączanie widoków**. 
- Ta strona może nie obsługiwać poprawnie widoków, ponieważ może całkowicie zignorować kwerendę widoku lub może działać na tymczasowej tabeli, której dane nie są trwałe. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Jakie dane są widoczne podczas odwiedzania strony?

W przypadku stron z niewielkimi selektorami widoku (w widoku można zapisywać tylko personalizacje), podczas odwiedzania strony będą widoczne te same dane. 

W przypadku stron z dużymi selektorami widoku zarówno (personalizacje i kwerendy mogą być zapisywane w widoku) zostaną wyświetlone zazwyczaj dane połączone z kwerendą skojarzoną z widokiem domyślnym. Istnieją dwa główne wyjątki:

- Jeśli przejdziesz do strony z kafelka, kwerenda kafelka zostanie wykonana niezależnie od kwerendy skojarzonej z domyślnym widokiem. Jeśli utworzono ten kafelek po włączeniu widoków, zaznaczenie kafelka spowoduje otwarcie strony z widokiem skojarzonym z tym kafelkiem.
- Jeśli przejdziesz do strony i ten punkt wejścia zawiera kwerendę, pierwotna kwerenda będzie początkowo wykonywana zamiast kwerendy domyślnego widoku. W takim przypadku podczas ładowania widoku zostanie wyświetlony komunikat informacyjny. Można to również potwierdzić, przełączając się do tego widoku po załadowaniu strony, ponieważ wtedy kwerenda widoku powinna zostać bezwzględnie wykonana.

### <a name="why-is-a-view-that-was-published-for-a-specific-legal-entity-visible-in-all-legal-entities"></a>Dlaczego widok, który został opublikowany dla określonej firmy, jest widoczny we wszystkich firmach?

Jeśli publikujesz widok dla określonej firmy, ale bez publikowania widoku jako widoku domyślnego, zachowanie jest następujące:

- Jeśli jest włączona tylko podstawowa funkcja **Zapisane widoki**, w selektorze widoku użytkownika dla strony początkowo będzie wyświetlany tylko widok dla określonych firm. Jednak po załadowaniu widoku po raz pierwszy będzie on zawsze wyświetlany w selektorze widoków użytkownika dla strony, niezależnie od firmy. To zachowanie występuje, ponieważ użytkownicy uzyskują własną osobistą kopię opublikowanego widoku po jego załadowaniu, a widoki osobiste są widokami globalnymi.
- Jeśli jest włączona funkcja **Usprawniona obsługa zapisanych widoków dla firmy**, w selektorze widoku będzie zawsze pokazywany tylko widok dla określonych firm. To zachowanie występuje, ponieważ funkcja umożliwia łączenie widoków (w tym widoków osobistych) z określonymi firmami.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

