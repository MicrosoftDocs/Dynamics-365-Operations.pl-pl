---
title: "Nowości i zmiany w programie Dynamics 365 for Operations w wersji 1611 (listopad 2016)"
description: "W tym temacie opisano nowe oraz zmienione funkcje dostępne w programie Dynamics 365 for Operations w wersji 1611."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 53c51ec1be145c72ff5090666399ac4ea113e5df
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016"></a>Nowości i zmiany w programie Dynamics 365 for Operations w wersji 1611 (listopad 2016)

[!include [banner](../includes/banner.md)]

W tym temacie opisano nowe oraz zmienione funkcje dostępne w programie Dynamics 365 for Operations w wersji 1611.

<a name="cost-accounting"></a>Rachunek kosztów
---------------

<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Definiowanie wymiarów składników kosztów i importowanie elementów członkowskich wymiarów składników kosztów.</td>
<td>Składniki kosztów są używane w module Rachunek kosztów do dzielenia kosztów na kategorie i dokumentowania przepływu kosztów. Podstawowe składniki kosztów są importowane za pomocą łącznika danych programu Microsoft Dynamics 365 for Operations w celu pobrania danych kont głównych bezpośrednio z programu Operations lub za pomocą standardowego łącznika danych i wtedy dane kont głównych można pobrać za pośrednictwem programu Microsoft Excel z systemu źródłowego o dowolnym innym typie. Po zaimportowaniu kont głównych do modułu Rachunek kosztów są one używane jako elementy członkowskie wymiarów składników kosztów. Podrzędne składniki kosztów są definiowane przez użytkownika i wykorzystywane w alokacjach w celu dokumentowania przepływu kosztów.</td>
</tr>
<tr class="even">
<td>Mapowanie wymiarów składników kosztów.</td>
<td>Jeśli ze względu na ustawowe wymogi księgowości konta główne nie mogą być udostępniane między firmami należącymi do organizacji, można je zmapować po zaimportowaniu do modułu Rachunek kosztów i w ten sposób uzyskać całościowy obraz w całej organizacji.</td>
</tr>
<tr class="odd">
<td>Definiowanie wymiarów obiektów kosztów i importowanie elementów członkowskich wymiarów obiektów kosztów.</td>
<td>Obiekty kosztów to obiekty dowolnego typu, do których są przypisywane koszty. Typowymi obiektami kosztów są produkty, projekty, zasoby, działy, centra kosztów i regiony geograficzne. Można użyć łącznika danych programu Microsoft Dynamics 365 for Operations w celu pobrania wymiarów finansowych i wartości z programu Operations albo standardowego łącznika danych i wtedy wymiary oraz wartości można pobrać za pośrednictwem programu Microsoft Excel z systemu źródłowego o dowolnym innym typie. Na przykład jeśli jako wymiar obiektu jest używany wymiar finansowy Centrum kosztu, wszystkie importowane centra kosztów będą elementami członkowskimi wymiaru obiektu kosztu.</td>
</tr>
<tr class="even">
<td>Definiowanie i importowanie wymiarów statystycznych.</td>
<td>Elementy członkowskie wymiarów statystycznych są mierzone w jednostkach niepieniężnych, takich jak roboczogodziny, liczba pracowników i powierzchnie. Są one używane w zestawieniach lub jako podstawa dla alokacji i dystrybucji.</td>
</tr>
<tr class="odd">
<td>Tworzenie szablonów dostawców miar statystycznych.</td>
<td>Szablon dostawcy miar statystycznych służy do przekształcania danych programu Dynamics 365 for Operations na miary statystyczne. Szablon jest następnie łączony z wybranym elementem członkowskim wymiaru statystycznego. Szablony są wstępnie filtrowane, tak aby wyświetlały tylko tabele skojarzone z wymiarami finansowymi.</td>
</tr>
<tr class="even">
<td>Tworzenie ksiąg rachunku kosztów.</td>
<td>Księga rachunku kosztów jest niezależną księgą, który używa własnego kalendarza i waluty. Odgrywa ważną rolę w przetwarzaniu wszystkich transakcji kosztowych. Na przykład księga rachunku kosztów klasyfikuje koszty na podstawie własnych składników kosztów i agreguje koszty na podstawie własnych wymiarów obiektów. Można utworzyć dowolną liczbę ksiąg rachunku kosztów potrzebną do sprawozdawczości zarządczej z różnych perspektyw.</td>
</tr>
<tr class="odd">
<td>Tworzenie jednostek kontroli kosztów.</td>
<td>Jednostki kontroli kosztów tworzą strukturę kosztów i definiują przepływ kosztów w księdze rachunku kosztów. Muszą być powiązane z wymiarami obiektów kosztów, aby reprezentowały wymiary obiektów kosztów w księdze.</td>
</tr>
<tr class="even">
<td>Przetwarzanie zapisów księgi głównej.</td>
<td>Aby mierzyć faktyczne efekty działań, trzeba mieć dane. Dane są importowane za pomocą łączników definiowanych dla księgi rachunku kosztów. W trakcie przetwarzania zapisów księgi głównej dane są importowane stopniowo.</td>
</tr>
<tr class="odd">
<td>Przetwarzanie wpisów budżetu.</td>
<td>Aby mierzyć realizację budżetu, trzeba mieć dane. Dane są importowane za pomocą łączników definiowanych dla księgi rachunku kosztów. W trakcie przetwarzania wpisów budżetu dane są importowane stopniowo.</td>
</tr>
<tr class="even">
<td>Tworzenie i stosowanie zasad zachowania kosztów.</td>
<td>Zasady zachowania kosztów służą do klasyfikowania kosztów jako stałych, zmiennych lub półzmiennych. Zasady są oparte na regułach i mają daty obowiązywania. Domyślnie wszystkie koszty są oznaczone jako niesklasyfikowane do momentu zastosowania zasady zachowania kosztów i obliczenia skutków reguły. Po obliczeniu koszty są klasyfikowane.</td>
</tr>
<tr class="odd">
<td>Śledzenie kosztów.</td>
<td>Aby ułatwić zrozumienie wpływu zasad kosztów, moduł Rachunek kosztów pozwala prześledzić koszty do ich wartości źródłowych i miejsc zastosowania zasad. Ta funkcja zapewnia pełne ustalenie takich informacji, jak czas wystąpienia kosztów, typy zaistniałych kosztów i zastosowane reguły zachowanie kosztów.</td>
</tr>
<tr class="even">
<td>Definiowanie hierarchii wymiarów.</td>
<td>Można tworzyć hierarchie wymiarów dla celów kategoryzacji lub klasyfikowania. Na przykład można zdefiniować hierarchię kategoryzacji opartą na wymiarze elementu kosztu i jego elementach członkowskich. Alternatywnie można zdefiniować hierarchię klasyfikacji opartą na wymiarze obiektu kosztu i jego elementach członkowskich. Struktury raportowania są używane w następujących sytuacjach:
<ul>
<li>Definiowanie alokacji, stawek kosztów i zasad kumulacji kosztów.</li>
<li>Wyświetlanie zestawień przy użyciu obszaru roboczego.</li>
<li>Definiowanie uprawnień wyświetlania zagregowanych danych.</li>
<li>Wyświetlanie danych w programie Excel.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tworzenie zestawień, które mogą być wyświetlane w obszarze roboczym.</td>
<td>Obszar roboczy umożliwia uzyskanie szybkiego przeglądu kosztów rzeczywistych i zabudżetowanych oraz odchyleń. Można filtrować dane według okresu lub poziomu kosztów. Obszar roboczy jest przeznaczony dla menedżerów odpowiedzialnych za kontrolę kosztów. Jest zgodny z regułami dostępu zdefiniowanymi dla hierarchii wymiarów.</td>
</tr>
<tr class="even">
<td>Tworzenie raportów za pomocą programu Excel. <strong>Uwaga:</strong> Potrzebny jest program Microsoft Excel 2016.</td>
<td>Można wyeksportować dane modułu Rachunek kosztów bezpośrednio do programu Excel za pomocą obiektów danych, a następnie używać tabel przestawnych programu Microsoft do tworzenia raportów.</td>
</tr>
</tbody>
</table>

## <a name="expense-management"></a>Zarządzanie wydatkami

| Co można zrobić                                                            | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Zmiana przypisania transakcji dokonanych kartą kredytową przez byłych pracowników.                     | Czasami, gdy pracownik zakończy zatrudnienie, jego konto w usłudze Active Directory Domain Services (AD DS) jest wyłączane podczas importowania aktywnych transakcji kartą kredytową, które muszą zostać zaliczone w koszty. Wcześniej nie można było przypisać pełnomocnika, który wprowadziłby wydatki, ani dołączyć transakcji kartą kredytową do raportu z wydatków. Teraz można użyć strony **Transakcje karty kredytowej**, aby zmienić przypisanie pracownika dla każdej transakcji kartą kredytową, której powiązany pracownik zakończył zatrudnienie. Po zmianie przypisania transakcji kartą kredytową transakcję można wybrać dla raportu o wydatkach i opłacić za pomocą zwykłego procesu uiszczania należności wykazanych w raporcie z wydatków. |
| Zmiana informacji o wydatkach kartą kredytową dla pracowników oczekujących i byłych. | Teraz można zmieniać dane kart kredytowych w module Zarządzanie wydatkami dla pracowników oczekujących i byłych. Poprzednio dane wydatków kartą kredytową można było zmieniać tylko dla aktywnych pracowników.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Kopiowanie raportu o wydatkach.                                                    | Można skopiować istniejący wydatek podczas tworzenia nowego wydatku w tym samym raporcie o wydatkach. Raport z wydatków i wszystkie inne powiązane wydatki zapłacone inaczej niż kartą kredytową można skopiować do nowego raportu o wydatkach. Nadal należy wykonać wszelkie wymagane podziały na pozycje i dołączyć wymagany paragon, zgodnie z obowiązującymi zasadami dotyczącymi wydatków i kategoriami. Aby dodać transakcje kartą kredytową do raportu o wydatków, wybierz opcję dodania nieuzgodnionych wydatków.                                                                                                                                                                                                                        |
| Zbiorcza edycja wydatków.                                                        | Niektóre transakcje kartami kredytowymi mogą nie być mapowane na kategorie wydatków lub być niepoprawnie mapowane podczas importowania. W takich przypadkach pracownicy muszą ręcznie zmienić powiązaną kategorię wydatku. Teraz zarządzając nieuzgodnionymi wydatkami, można zbiorczo edytować kategorię wydatku dla wybranych wydatków. Ponadto podczas zarządzania wybranymi wydatkami zawartymi w określonym raporcie z wydatków można zbiorczo edytować projekt i dodatkowe informacje.                                                                                                                                                                                    |
| Zmiana kursu wymiany transakcji kartą kredytową.                     | Rzeczywisty kurs wymiany używany dla transakcji kartą kredytową może się różnić od kursu wymiany ustawionego w systemie. Uprzednio pracownicy nie mogli zmieniać kursów wymiany dla żadnych transakcjami kartami kredytowymi, które zostały zaimportowane do modułu Zarządzanie wydatkami. Teraz na stronie **Parametry zarządzania wydatkami** można ustawić parametr, który pozwoli zmieniać kurs wymiany dla transakcji kartami kredytowymi.                                                                                                                                                                                                                                            |
| Konfigurowanie zaświadczenia antykorupcyjnego dla wydatków.                            | Niektórzy pracownicy organizacji mogą współpracować z urzędnikami i niektóre wydatki powstałe w ramach tej współpracy mogą być traktowane jako przekupstwo. W module Zarządzanie wydatkami można teraz skonfigurować zaświadczenie antykorupcyjne, które będzie wyświetlane dla wybranych kategorii wydatków, takich jak wydatki na restauracje i prezenty. Pracownik musi wskazać, czy wydatek objęty funkcją zaświadczenia antykorupcyjnego spełnia kryteria określone w zasadach organizacji.                                                                                                                                                                                     |
| Blokada ręcznego wprowadzania wydatków w określonych kategoriach wydatków.          | Kategorię wydatków można skonfigurować tak, aby reprezentowała transakcję kartą kredytową, w której nie można zmienić kategorii. Przykładem jest opłata za opóźnioną spłatę zadłużenia na karcie kredytowej. Teraz można skonfigurować umożliwiający wydatki będą tworzone tylko za pomocą importu kategorii wydatków. Ta funkcja uniemożliwia pracownikom ręczne tworzenie wydatków w tej kategorii. Ponadto nie zezwala na zmianę kategorii w transakcjach, które zostały zaimportowane i używają tej kategorii.                                                                                                                                                                                   |
| Dołączanie paragonu do wielu wydatków.                                     | Paragon przekazany do modułu Zarządzanie wydatkami może być związany z wieloma wydatkami. Wcześniej paragon związany z wieloma wydatkami trzeba było przekazywać osobno dla każdego wydatku. Teraz do wydatku można dołączyć paragon, który został już przekazany i dołączony do innego wydatku w tym samym raporcie z wydatków. Ponadto jeśli przekażesz paragon do nagłówka raportu o wydatkach, można wybrać jeden lub więcej wierszy, do których paragon zostanie dołączony.                                                                                                                                                                                        |
| Tworzenie wydatków z datami przyszłymi.                                              | Podczas kopiowania na przykład raportu z wydatków datą transakcji dla wydatku może być przyszła data. Poprzednie wersje nie zezwalały na przyszłe daty wydatków. Teraz można tworzyć i zapisywać wydatki, które mają daty w przyszłości. Jednakże nie można przesyłać takich wydatków.                                                                                                                                                                                                                                                                                                                                                                                 |
| Konfigurowanie podatków od wydatków dla województwa.                              | W niektórych krajach/regionach wydatki poniesione w różnych stanach/prowincjach/województwach itd. mogą podlegać różnym stawkom podatkowym. Teraz można utworzyć konfiguracje podatków od wydatków na poziomie województwa, a nie tylko kraju/regionu. Jeśli na stronie **Konfiguracja podatku** pole **Województwo** pozostanie puste, grupa podatków ma zastosowanie do wszystkich województw w określonym kraju/regionie.                                                                                                                                                                                                                                       |
| Konfigurowanie typów kart kredytowych dla wydatków.                                          | Wcześniej nie było żadnej strony, gdzie można byłoby tworzyć nowe typy kart kredytowych (Visa, MasterCard, AMEX itd.) przeznaczone do używania w module Zarządzanie wydatkami. Teraz można utworzyć typy kart kredytowych przeznaczone do używania w module Zarządzanie wydatkami. Strona znajduje się w obszarze **Ustawienia** w sekcji **Obliczenia i kody**.                                                                                                                                                                                                                                                                                                                                                 |
| Definiowanie wielopoziomowego przepływu pracy zatwierdzania raportów z wydatków.                 | Nowy przepływ pracy raportów o wydatkach obsługuje proces wielopoziomowego zatwierdzania. Pracownicy wprowadzają tymczasowe i ostateczne osoby zatwierdzające osoby zatwierdzające podczas tworzenia raportu z wydatków. Następnie przepływ pracy kieruje raport z wydatków najpierw do tymczasowej osoby zatwierdzającej. Gdy raport o wydatkach zostanie zatwierdzony na tym poziomie, przepływ pracy kieruje go do ostatecznych osób zatwierdzających, które dokonają zatwierdzenia końcowego.                                                                                                                                                                                                                                                                                          |
| Tworzenie i obsługa wydatków, które nie są dołączone do raportu z wydatków.    | Teraz można tworzyć wydatki i nimi zarządzać (na przykład przez dołączanie lub uszczegóławianie paragonów albo przypisywanie gości) bez uprzedniego utworzenia raportu z wydatków. Jeden lub więcej wydatków można wybrać i dodać do nowego raportu z wydatków w celu przesłania do zatwierdzenia. W ścieżce **Zarządzanie wydatkami** &gt; **Moje wydatki** &gt; **Wydatki** znajduje się nowa strona do zarządzania wydatkami.                                                                                                                                                                                                                                                       |

## <a name="financial-management"></a>Zarządzanie finansami
<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Śledzenie wyceny środków trwałych przy użyciu koncepcji pojedynczej „księgi”.</td>
<td>Wcześniej były używane dwa oddzielne typy wyceny do śledzenia wartości środków trwałych: modele ewidencji i księgi amortyzacji. W bieżącej wersji te dwie koncepcje zostały scalone w jedną koncepcję wyceny o nazwie „księgi”. Księgi mają wszystkie funkcje zarówno modeli ewidencji, jaki i ksiąg amortyzacji. Można na przykład wyłączyć księgowanie w księdze głównej. Księgi, których zapisy są księgowane w księdze głównej, są zazwyczaj używane na potrzeby firmowej sprawozdawczości finansowej. Księgi, których pozycje nie są księgowane w księdze głównej, mogą być używane na potrzeby sprawozdawczości podatkowej.</td>
</tr>
<tr class="even">
<td>Wykonywanie zamknięcia księgi głównej na koniec roku dla wielu firm.</td>
<td>W celu przyspieszenia procesu zamknięcia roku można teraz uruchomić proces dla wielu firm równocześnie ze wspólnej strony zamknięcia roku. Można zdefiniować grupy firm wraz z ustawieniami, które powinny zostać zachowane po przejściu do nowego roku. Wprowadzono również inne użyteczne ulepszenia w procesie zamknięcia roku.</td>
</tr>
<tr class="odd">
<td>Korzystanie z ulepszeń procesu przeszacowania w walucie obcej w księdze głównej.</td>
<td>Wprowadzono następujące udoskonalenia w procesie księgi głównej dotyczącym przeszacowania w walucie obcej:
<ul>
<li>Do konta głównego dodano typ kursu wymiany. Typ kursu wymiany jest teraz używany do określania kursu wymiany podczas przeszacowywania w walucie. W razie niezdefiniowania kursu wymiany proces w dalszym ciągu używa typu kursu wymiany określonego w księdze.</li>
<li>Teraz można łatwiej wybrać zakres kont głównych i walut, dla których ma zostać wykonany proces przeszacowania.</li>
<li>Przeszacowanie można wykonać dla wielu firm.</li>
<li>Teraz system przechowuje historię każdego wykonanego procesu przeszacowania, tak jak w przypadku procesów przeszacowania w modułach Rozrachunki z odbiorcami (AR) i Rozrachunki z dostawcami (AP).</li>
<li>Po uruchomieniu procesu można teraz wyświetlić podgląd wyników przeszacowania. Podgląd pokazuje wyniki w odniesieniu do wszystkich firm objętych procesem. Następnie można zaksięgować wszystkie firmy lub tylko ich część z poziomu okna podglądu. Wyniki w podglądzie można również wyeksportować do programu Excel.</li>
</ul></td>
</tr>
<tr class="even">
<td>Wyświetlanie transakcji dodatkowych warstw księgowania.</td>
<td>Na stronie listy <strong>Bilans próbny</strong> i w raporcie <strong>Zestawienie wymiarów</strong> można teraz wybierać dodatkowe warstwy księgowania, które zostały dodane do księgi głównej. Po wybraniu dodatkowych warstw księgowania korekty w tych warstwach księgowania są uwzględniane w saldzie na stronie listy lub w raporcie.</td>
</tr>
<tr class="odd">
<td>Dołączenie dokumentacji instruktażowej do szablonu zamknięcia okresu finansowego.</td>
<td>Poprzednio dokumentację można było dołączyć po zakończeniu zadania. Na przykład można było dołączyć wygenerowany raport. Teraz można dołączyć również dokument instruktażowy do szablonu. Dokument zostanie wtedy skopiowany do każdego zadania w harmonogramie okresu finansowego, tak aby właściciel zadania mógł wyświetlić instrukcje dotyczące sposobu jego wykonania.</td>
</tr>
<tr class="even">
<td>Tworzenie konfiguracji księgowania międzyfirmowego ze wspólnej strony.</td>
<td><strong>Strona konfiguracji księgowania międzyfirmowego</strong> jest teraz udostępniona, dzięki czemu wszyscy w organizacji mogą definiować wszystkie pary firm mogących zawierać między sobą transakcje. Ponadto można teraz wprowadzić transakcję w firmie źródłowej, ale nie w kierunku od firmy docelowej. Jeśli dowolna firma może inicjować transakcję międzyfirmową, muszą być określona obie strony transakcji. W związku z tym firma docelowa jest również konfigurowana jako firma źródłowa.</td>
</tr>
<tr class="odd">
<td>Przesyłanie dokumentów uzasadnienia planów budżetu.</td>
<td>Dla wszelkich wnioskowanych kwot budżet można utworzyć szablon uzasadnienia jako dokumentację uzupełniającą. Użytkownicy mogą wypełniać szczegóły szablonu i dołączać szablon do planu budżetu, co pozwoli używać go w procesie zatwierdzania.</td>
</tr>
<tr class="even">
<td>Włączanie zaawansowanych reguł dla wpisów do rejestru budżetu.</td>
<td>Jeśli w księdze głównej skonfigurowano reguły zaawansowane, mogą one być używane do nowych wpisów i przeniesień w rejestrze budżetu.</td>
</tr>
<tr class="odd">
<td>Korzystanie z rozszerzonej widoczności działań fakturowania zaliczkowego.</td>
<td>Nowa strona listy <strong>Otwarte przedpłaty</strong> zawiera migawkę stanu działań fakturowania zaliczkowego. Strona dostarcza działowi rozrachunków z dostawcami informacji o zamówieniach zakupu mających pozostałe wartości z przedpłat wymagające zafakturowania, zafakturowane wartości wymagające zapłaty i zapłacone wartości faktur wymagające zastosowania do standardowych faktur. Ponadto usprawnienia mechanizmu automatycznego stosowania zapłaconych faktur zaliczkowych do standardowych faktur pomagają pracownikom odpowiedzialnym za fakturowanie sprawniej wprowadzać dane.</td>
</tr>
<tr class="even">
<td>Korzystanie z obszaru roboczego <strong>Fakturowanie w portalu współpracy z dostawcami</strong>.</td>
<td>Nowy obszar roboczy <strong>Fakturowanie</strong> dostępny w obszarze <strong>Portal współpracy z dostawcami</strong> umożliwia zewnętrznym dostawcom bezpieczny dostęp do danych ich własnych faktur. Na przykład dostawcy widzą, czy faktury zostały zapłacone, i mogą przesłać swoje faktury. Ta zmiana umożliwia bardziej skuteczną i bieżącą komunikację z dostawcami zewnętrznymi. W efekcie osoby zajmujące się fakturowaniem mogą płynniej pracować.</td>
</tr>
<tr class="odd">
<td>Przełączanie firm podczas wprowadzania faktur.</td>
<td>Wprowadzone ulepszenia sprawiają, że pracownicy wprowadzający faktury wielu firm mogą szybko zmieniać firmy z poziomu stron fakturowania. Funkcja oszczędza czas pracownikom wprowadzającym faktury, ponieważ nie muszą oni już wylogowywać się z bieżącej firmy i logować do innej. Użytkownicy mogą zmieniać firmę podczas wprowadzania danych na obu stronach — <strong>Globalny arkusz faktur</strong> i <strong>Faktury od dostawcy</strong>.</td>
</tr>
<tr class="even">
<td>Obsługa elektronicznych plików w amerykańskim programie składania zintegrowanej federalnej/stanowej deklaracji podatkowej 1099</td>
<td>Gdy jest włączony klucz konfiguracji <strong>Stany Zjednoczone</strong>, proces przesyłanie dokumentów 1099 drogą elektroniczną zawiera dodatkowe funkcje zgodności z przepisami amerykańskiej administracji skarbowej dla programu składania zintegrowanych federalnych/stanowych deklaracji podatkowej. Program pozwala urzędom skarbowym elektroniczne przesyłać informacje z otrzymanych deklaracji podatkowych do uczestniczących stanów.</td>
</tr>
<tr class="odd">
<td>Ulepszenia w zakresie rozliczeń.</td>
<td>Ulepszenia pomagają pracownikom obsługującym płatności sprawniej dokonywać rozliczeń, ponieważ mogą oni pozwolić na rozliczanie wielu niezaksięgowanych płatności względem tej samej faktury.</td>
</tr>
<tr class="even">
<td>Widok międzyfirmowy.</td>
<td>Pracownicy zajmujący się centralną obsługą płatności mogą teraz wyświetlać zaległe faktury we wszystkich firmach. Obszary robocze <strong>Płatności dostawcy</strong> i <strong>Płatności odbiorcy</strong> teraz oferują lepszy podgląd i kontrolę nad zaległymi fakturami poprzez umożliwienie wyświetlania i filtrowania w granicach wszystkich firm należących do hierarchii organizacyjnej centralnej obsługi płatności.</td>
</tr>
<tr class="odd">
<td>Korzystanie z obszaru roboczego <strong>Zarządzanie bankami</strong>.</td>
<td>Nowy obszar roboczy <strong>Zarządzanie bankami</strong> ułatwia śledzenie kont bankowych i sald dla firm. Informacje o bieżących i oczekujących saldach są dostępne natychmiast dla wszystkich kont, a także można przechodzić od sald do szczegółowych załączników transakcji. Dodatkowo można wyświetlić dane historycznych sald dla każdego konta bankowego albo podsumowanie wszystkich kont bankowych w firmie, w widokach krótkoterminowym i długoterminowym. Można uzyskać lepszy wgląd w uzgodnienia konta bankowego, ponieważ data ostatniego uzgodnienia jest zgłaszana dla każdego konta bankowego oraz istnieje wskaźnik uzgodnień będących w toku.</td>
</tr>
<tr class="even">
<td>Import elektronicznych wyciągów bankowych dla wszystkich firm w jednym kroku.</td>
<td>Teraz można zaimportować elektroniczne wyciągi bankowe dla wszystkich firm w jednym kroku. Pliki wyciągów bankowych mogą zawierać zestawienia z wielu kont bankowych i firm, a pliki ZIP mogą zawierać wiele plików wyciągów bankowych. Za pomocą jednego procesu importu można rozpocząć uzgadnianie wszystkich zgłoszonych kont bankowych we wszystkich firmach. Ta funkcja pomaga oszczędzić czas, ponieważ nie trzeba przełączać się między firmami i importowaniem różnych wyciągów. Można również automatycznie uruchomić reguły uzgadniania dla wszystkich importowanych wyciągów w każdej firmie.</td>
</tr>
<tr class="odd">
<td>Śledzenie wyceny.</td>
<td>Jeden środek trwały może mieć wiele wycen według różnych standardów księgowych, a opcjonalnie powiązane z nim transakcje mogą być księgowane w księdze głównej. Uprzednio wyceny były śledzone za pomocą modeli ewidencji lub ksiąg amortyzacji. Teraz można śledzić te wyceny, zwane obecnie księgami, przy użyciu wspólnego zestawu arkuszy, zapytań i raportów. Ujednolicone środowisko obsługi upraszcza wdrożenie i zmniejsza liczbę interfejsów wymaganych przez procesy okresowe.</td>
</tr>
<tr class="even">
<td>Korzystanie z ulepszeń w zakresie międzyfirmowych sesji księgowania amortyzacji.</td>
<td>Teraz można uruchamiać sesję księgowania amortyzacji środków trwałych we wszystkich firmach na jednej stronie. Można również automatycznie księgować arkusze po ich utworzeniu. Operacje tworzenia i księgowania arkuszy można wysłać do przetwarzania wsadowego, tak aby amortyzacja była wykonywana w tle. Te ulepszenia poprawiają efektywność, ponieważ nie trzeba uruchamiać osobnych sesji księgowania amortyzacji dla każdej firmy. Ponadto umożliwiają lepsze centralne zarządzanie środkami trwałymi.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Zarządzanie kapitałem ludzkim

| Co można zrobić                                                                                | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tworzenie arkuszy wydajności.                                                                  | Przed rozpoczęciem swojej okresowej oceny często zbierasz informacje na temat działań lub zdarzeń, które przyczyniły się do Twojego sukcesu zawodowego w badanym okresie. Możesz dodać wpis do swojego arkusza wydajności w celu udokumentowania tych działań i zdarzeń. Można też połączyć te działania i zdarzenia z przeglądem wydajności w celu przekazania dodatkowych informacji osobie oceniającej.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Tworzenie bardziej szczegółowych celów.                                                                    | Masz większą kontrolę nad treścią ustawianych celów. Można tworzyć miary dla celów, łączyć wpisy arkusza wydajności z miarami oraz dołączać i przeglądać dokumenty. Można zapisywać cele jako szablony i używać ich ponownie, co przyspiesza konfigurowanie.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Tworzenie bardziej szczegółowych przeglądów wydajności.                                                      | Przeglądy wydajności, zwane formalnie dyskusjami, są teraz wystarczająco elastyczne, aby obsługiwać schemat ciągłego przekazywania informacji zwrotnych i bardziej formalne metody oceny. Można pobierać aktywne cele i publikować o nich komentarze oraz dodawać sekcje do oceny swoich kompetencji. Dostępne są dodatkowe sekcje, gdzie można dodawać i wyświetlać miary, wpisy arkusza wydajności, załączniki i podpisy odnoszące się do oceny (przeglądu).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Kojarzenie dodatkowych hierarchii stanowisk z przepływami pracy.                                      | Przepływ pracy można skojarzyć z hierarchią stanowisk. Można również modyfikować etapy przepływu pracy w celu zoptymalizowania procesu zatwierdzania, tak aby pasował on do wymagań firmy. W związku z tym można zdefiniować skuteczną strukturę zatwierdzania, która pasuje do różnych relacji służbowych stosowanych w organizacji.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Obsługa przepływu pracy wprowadzania osobistych numerów identyfikacyjnych (PIN) w portalu samoobsługi pracowników etatowych. | Funkcjonalność przepływu pracy w zarządzaniu kadrami (HR) została rozszerzona i teraz obejmuje obsługę numerów PIN. W celu poprawy wydajności pracownicy mogą sami dodawać i edytować swoje numery PIN. Jednak pracownicy działu kadr mogą weryfikować dokładność i kompletność tych informacji przed ich dodaniem do rekordu pracownika.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Tworzenie szablonów celów i używanie na potrzeby dodawania nowych celów.                                          | Można tworzyć szablony dla celów, które są wspólne dla wielu pracowników w firmie. Z szablonu pracownicy mogą dodawać swoje własne cele, menedżerowie cele swoich zespołów, a personel działu kadr może dodawać cele dla pracowników w całej firmie.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Tworzenie grup celów i używanie ich na potrzeby dodawania nowych celów.                                             | Można dodać szablony celów do grupy, a następnie użyć grupy do utworzenia jednego lub więcej celów dla pracownika, zespołu, stanowiska, działu lub całej firmy.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Większa kontrola nad procesem przeglądu (oceny).                                                     | Można używać przepływu pracy do kontrolowania procesu oceny. Można tworzyć szablony przeglądu i używać ich do tworzenia ocen. Można również dodawać klasyfikacje punktowe do oceny.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Używanie okresów przeglądu do definiowania ram czasowych oceny.                                    | Można zdefiniować przedział czasu dla przeglądu wydajności, a daty rozpoczęcia i zakończenia przeglądu zostaną wprowadzane automatycznie. Jednak w razie potrzeby można zmienić te domyślne daty.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Dostęp do pięciu nowych pakietów zawartości usługi Power BI dla zasobów ludzkich                                     | Nowe pakiety zawartości umożliwiają działom i kadr kierownikom ds. kadr analizowanie następujących parametrów: Metryki pracowników • Podział demograficzny według wieku, płci i stanu cywilnego • Porównywanie wskaźników rotacji rok do roku i wyświetlanie listy powodów, które pracownicy podawali jako powody opuszczenia organizacji • Wyświetlanie listy otwartych stanowisk, a także porównywanie stanowisk otwartych do obsadzonych Wynagrodzenia i świadczenia • Porównywanie pracowników akordowych i etatowych • Wyświetlanie liczby pracowników zarejestrowanych na dostępne świadczenia • Wyświetlanie pracowników według typu zatrudnienia Rekrutacja • Analiza kandydatów na podstawie liczby kandydatów, ich pochodzenia i stanowisk, o które się ubiegają Szkolenie organizacyjne • Rejestracje na kursy według lokalizacji • Frekwencja na kursach według stanu • Lista pracowników zarejestrowanych na kursy Kompetencje i rozwój pracownika etatowego • Lista umiejętności posiadanych przez pracowników • Podział typów umiejętności według członków zespołów |

## <a name="localizations"></a>Lokalizacje
<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dostępne są zlokalizowane wersje dla 18 dodatkowych krajów:
<ul>
<li>Austria</li>
<li>Belgia</li>
<li>Brazylia</li>
<li>Chiny</li>
<li>Czechy</li>
<li>Estonia</li>
<li>Finlandia</li>
<li>Węgry</li>
<li>Włochy</li>
<li>Łotwa</li>
<li>Litwa</li>
<li>Norwegia</li>
<li>Polska</li>
<li>Arabia Saudyjska</li>
<li>Hiszpania</li>
<li>Szwecja</li>
<li>Szwajcaria</li>
<li>Tajlandia</li>
</ul>
Następujące kraje wymagają również przetłumaczenia modułu Handel detaliczny. Tłumaczenia dla tych krajów nie zostały wykonane i zaplanowane je na 1 poł. 2017 roku:
<ul>
<li>Brazylia</li>
<li>Czechy</li>
<li>Estonia</li>
<li>Węgry</li>
<li>Łotwa</li>
<li>Litwa</li>
<li>Malezja</li>
<li>Polska</li>
<li>Szwecja</li>
</ul></td>
<td>Program Dynamics 365 for Operations jest dostępny w 18 kolejnych krajach. W ramach naszych działań w kierunku ułatwienia i lepszej konfigurowalności przetłumaczonych elementów funkcje ustawowej sprawozdawczości elektronicznej zostały przekonwertowane na konfiguracje raportowania elektronicznego (ER), a niektóre ustawowe raporty usług Microsoft SQL Server Reporting Services (SSRS) zostały przekonwertowane na konfiguracje ER używające szablonów programu Excel. Te przekonwertowane funkcje wymieniono poniżej w tabeli.</td>
</tr>
<tr class="even">
<td>Japonia — Grupowanie środków trwałych podczas drukowania formularza 26 i dołączonych do niego tabel.</td>
<td>Formularz 26 należy przesłać do każdego miasta, w którym działa firma. Aby zmniejszyć pracochłonność podczas drukowania formularza 26, środki trwałe można automatycznie grupować i sortowane według lokalizacji.</td>
</tr>
<tr class="odd">
<td>Japonia — Wyświetlanie kwot przyspieszonej i dodatkowej amortyzacji w profilu.</td>
<td>Profil może zapewnić dokładne szacunki kwot przyspieszonej i dodatkowej amortyzacji.</td>
</tr>
<tr class="even">
<td>Japonia — Stopniowe obliczanie zaliczki na podatek.</td>
<td>Rząd japoński wymaga, aby zaliczka na podatek była obliczana stopniowo, na podstawie kwoty płatności.</td>
</tr>
<tr class="odd">
<td>Japonia — Import pliku kodów pocztowych dla określonych dużych budynków firmowych.</td>
<td>Plik kodów pocztowych wymagany urzędowo dla określonych dużych budynków firmowych można zaimportować do systemu. Następnie adres można wygenerować na podstawie kodów pocztowych.</td>
</tr>
<tr class="even">
<td>Japonia — Konfigurowanie okresu bezczynności środków trwałych.</td>
<td>Okresy bezczynności pozwalają użytkownikom wstrzymać amortyzację środków trwałych w ustalonym przedziale czasu. Ta funkcja jest wymagana ustawowo.</td>
</tr>
<tr class="odd">
<td>Europa — Konfigurowanie numeru rejestracji płatnika podatku od wartości dodanej (VAT) dla adresu podmiotu przy użyciu struktury identyfikatora rejestracji.</td>
<td>Można skonfigurować numer rejestracji VAT dla adresu strony za pomocą struktury identyfikatora rejestracji i nowej kategorii rejestracji <strong>Identyfikator VAT</strong>.</td>
</tr>
<tr class="even">
<td>Finlandia — Konfigurowanie numeru celnego odbiorcy dla adresu podmiotu przy użyciu struktury identyfikatora rejestracji.</td>
<td>Można skonfigurować numer celny odbiorcy cła dla adresu strony za pomocą struktury identyfikatora rejestracji i nowej kategorii rejestracji <strong>Identyfikator odbiorcy cła</strong>.</td>
</tr>
<tr class="odd">
<td>Francja — Drukowanie faktur dla odbiorców w układzie charakterystycznym dla Francji.</td>
<td>Wydruk faktury dla odbiorcy jest dostosowany do wymagań specyficznych dla Francji.</td>
</tr>
<tr class="even">
<td>Francja — Wymuszanie chronologicznego numerowania dokumentów według okresów obrachunkowych.</td>
<td>W celu spełnienia wymagań specyficznych dla Francji dotyczących numerowania faktur dla odbiorców można ustawić numerację faktur dla odbiorców z podziałem na okresy obrachunkowe.</td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Austrii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format XML listy sprzedaży do krajów UE dla Austrii</li>
<li>Format Intrastat dla Austrii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Austrii</li>
<li>Format płatności poleceniem zapłaty ISO20022 dla Austrii</li>
<li>Austriacki format EDIFACT PAYMUL</li>
<li>Deklaracja VAT dla Austrii</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Belgii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format BLWI dla Belgii</li>
<li>Lista sprzedaży do UE w formacie XML dla Belgii</li>
<li>Raport środków trwałych dla Belgii</li>
<li>Format Intervat dla Belgii</li>
<li>Format Intrastat dla Belgii</li>
<li>Raport obrotów z faktur dla Belgii</li>
<li>Format eksportu transakcji księgi dla Belgii</li>
<li>Format płatności SWIFT do dostawcy dla Belgii</li>
<li>Format importu wyciągów bankowych CODA dla Belgii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Belgii</li>
<li>Format płatności poleceniem zapłaty ISO20022 dla Belgii</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Brazylii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>SP GIA dla Brazylii</li>
<li>ST GIA dla Brazylii</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Czech — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format XML listy sprzedaży do krajów UE dla Czech</li>
<li>Format Intrastat dla Czech</li>
<li>Deklaracja VAT dla Czech</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Chin — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format raportu o wiekowaniu dla odbiorców dla Chin</li>
<li>Format raportu analizy kwot należnych od odbiorcy dla Chin</li>
<li>Format raportu o wiekowaniu dla dostawców dla Chin</li>
<li>Format raportu analizy kwot należnych dostawcy dla Chin</li>
<li>Format analizy wiekowania płatności należności dla Chin</li>
<li>Format raportu o saldzie dla odbiorców dla Chin</li>
<li>Format raportu o saldzie konta księgowego dla Chin</li>
<li>Format raportu o saldzie dla dostawców dla Chin</li>
<li>Plik GBT dla Chin</li>
<li>Format pliku eksportu w systemie Golden Tax</li>
<li>Format raportu odchylenia zużycia produkcji dla Chin</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Estonii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format XML listy sprzedaży do krajów UE dla Estonii</li>
<li>Format Intrastat dla Estonii</li>
<li>Zestawienie przeklasyfikowania zapasów dla Estonii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Estonii</li>
<li>Raport powiadomień o saldach dostawców/odbiorców dla Estonii</li>
<li>Deklaracja VAT dla Estonii</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Finlandii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format tekstowy listy sprzedaży do krajów UE dla Finlandii</li>
<li>Format Intrastat dla Finlandii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Finlandii</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Węgier — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format XML listy sprzedaży do krajów UE dla Węgier</li>
<li>Format Intrastat dla Węgier</li>
<li>Uproszczony format Intrastat dla Węgier</li>
<li>Format eksportu listy faktur dla Węgier</li>
<li>Deklaracja VAT dla Węgier</li>
<li>Deklaracja VAT z podziałem na pozycje dla Węgier</li>
<li>Zestawienie magazynowe dla Węgier</li>
<li>Format płatności MultiCash dla Węgier</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Włoch — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format Intrastat dla Włoch</li>
<li>Format faktury za projekt dla Włoch</li>
<li>Format faktury sprzedaży dla Włoch</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Włoch</li>
<li>Format płatności poleceniem zapłaty ISO20022 dla Włoch</li>
<li>Format zapłaty z tytułu inkasa RIBA dla Włoch</li>
<li>Krajowy raport transakcji podatkowych dla Włoch</li>
<li>Raport czarnej listy dla Włoch</li>
<li>Raport Modello770 dla Włoch</li>
<li>Roczne sprawozdanie podatkowe dla Włoch</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Łotwy — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Raport o użyciu blankietów kasowych (LV)</li>
<li>Format XML listy sprzedaży do krajów UE dla Łotwy</li>
<li>Format XML korekt listy sprzedaży do krajów UE dla Łotwy</li>
<li>Format Intrastat (A) dla Łotwy</li>
<li>Format Intrastat (B) dla Łotwy</li>
<li>Lista inwentaryzacji zapasów dla Łotwy</li>
<li>Zestawienie inwentaryzacji zapasów dla Łotwy</li>
<li>Przesunięcie magazynowe dla Łotwy</li>
<li>Dokument dostawy dla przeniesienia wewnętrznego dla Łotwy</li>
<li>Dokument przeklasyfikowania zapasów dla Łotwy</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Łotwy</li>
<li>Deklaracja VAT dla Łotwy</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Litwy — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format XML listy sprzedaży do krajów UE dla Litwy</li>
<li>Format Intrastat dla Litwy</li>
<li>Zestawienie magazynowe dla Litwy</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Litwy</li>
<li>Raport z uzgodnień między dostawcami i odbiorcami dla Litwy</li>
<li>Deklaracja VAT dla Litwy</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Norwegii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format ponaglenia dla Norwegii</li>
<li>Format płatności AutoGiro dla Norwegii</li>
<li>Format płatności od odbiorcy AvtaleGiro dla Norwegii</li>
<li>Format płatności od odbiorcy eFaktura dla Norwegii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Norwegii</li>
<li>Format płatności NETS dla Norwegii</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Polski — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format Intrastat dla Polski</li>
<li>Dokumenty magazynowe dla Polski</li>
<li>Dokument przeklasyfikowania zapasów dla Polski</li>
<li>Format płatności MultiCash dla Polski</li>
<li>Format płatności zagranicznych MultiCash dla Polski</li>
<li>Raport potwierdzenia saldach dostawców/odbiorców dla Polski</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Arabii Saudyjskiej — konfiguracje raportowania elektronicznego</td>
<td>Format alokacji opłat dodatkowych w akredytywie bankowej dla Arabii Saudyjskiej</td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Hiszpanii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format tekstowy listy sprzedaży do krajów UE dla Hiszpanii</li>
<li>Format Intrastat dla Hiszpanii</li>
<li>Format faktury za projekt dla Hiszpanii</li>
<li>Format faktury sprzedaży dla Hiszpanii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Hiszpanii</li>
<li>Format płatności poleceniem zapłaty ISO20022 dla Hiszpanii</li>
<li>Format hiszpańskiego rejestru VAT</li>
<li>Format podsumowanie hiszpańskiego rejestru VAT</li>
<li>Eksport deklaracji 347 do formatu ASCII dla Hiszpanii</li>
<li>Raport o deklaracji 347 dla Hiszpanii</li>
</ul></td>
</tr>
<tr class="even">
<td>Tłumaczenie dla Szwecji — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format Intrastat dla Szwecji</li>
<li>Format płatności od odbiorcy Bankgirot Autogiro dla Szwecji</li>
<li>Format płatności dla dostawcy Bankgirot dla Szwecji</li>
<li>Format płatności SWIFT do dostawcy dla Szwecji</li>
<li>Format eksportu SIE dla Szwecji</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Szwecji</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tłumaczenie dla Szwajcarii — konfiguracje raportowania elektronicznego</td>
<td><ul>
<li>Format płatności DebitDirect dla Szwajcarii</li>
<li>Format płatności poleceniem zapłaty LSV dla Szwajcarii</li>
<li>Format płatności poleceniem przelewu ISO20022 dla Szwajcarii</li>
<li>Format płatności poleceniem zapłaty ISO20022 dla Szwajcarii</li>
<li>Format importu wyciągów bankowych ESR dla Szwajcarii</li>
</ul></td>
</tr>
<tr class="even">
<td>Niemcy — Eksport płatności dostawcy w formacie DTAZV</td>
<td>Niemcy wymagają specyfikacji DTAZV z formatem zagranicznym. Jest to komunikat polecenia przelewu (płatności dla dostawcy) zgodny ze specyfikacją płatności transgranicznych z Niemiec na konto w banku zagranicznym lub w banku krajowym, ale w obcej walucie. 
</td>
</tr>
</tbody>
</table>

### <a name="electronic-reporting"></a>Raportowanie elektroniczne

| Co można zrobić                                                                                                                                                                                                                                                                                     | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurowanie raportów modułu ER w celu wstawiania danych w kilku formatach z magazynu zarządzania dokumentami do generowanych komunikatów elektronicznych.                                                                                                                                                              | Raporty modułu ER mogą wstawiać dane do komunikatów elektronicznych generowanych z magazynu zarządzania dokumentami. W związku z tym załączniki dokumentu biznesowego można dodawać do elektronicznych komunikatów generowanych dla tego dokumentu, zgodnie z wymogami prawnymi. Obecnie załączniki te można dodać w formacie MIME do generowanego komunikatu XML. Alternatywnie załączniki można dodawać w formacie Base64 do generowanego komunikatu binarnego.                                                                      |
| Konfigurowanie raportów modułu ER w celu generowania dokumentów elektronicznych w formacie programu Excel, Microsoft Word lub PDF.                                                                                                                                                                                                      | Jedna konfiguracja umożliwia raportom modułu ER generowanie dokumentów elektronicznych w trzech różnych formatach: arkusza OpenXML (Excel), Word i XML Forms Data Format (XFDF) (PDF). Użytkownicy mogą wybrać format przez dodanie szablonu formatu do raportu modułu ER jako dokument programu Excel, Word lub PDF.                                                                                                                                                                                                                                                                       |
| Konfigurowanie raportów modułu ER w celu wstawiania danych do nagłówków i stopek dokumentów elektronicznych generowanych w formacie arkusza OpenXML oraz do kontrolowania podziałów na strony.                                                                                                                               | Raporty modułu ER mogą wprowadzać dane biznesowe do nagłówków i stopek stron oraz kontrolować miejsca wstawiania podziałów stron. Dlatego raporty mogą wspierać statyczne górne i dolne sekcje stron generowanych dokumentów elektronicznych. Mogą także wspierać określone stronicowanie tych dokumentów, tak aby były zgodne z wymogami prawnymi.                                                                                                                                                                                                             |
| Konfigurowanie miejsca docelowego raportów modułu ER w taki sposób, aby dane wyjściowe były wysyłane jako wiadomości e-mail oraz aby można było używać danych biznesowych i logiki modułu ER (wyrażeń) do określania w czasie wykonywania adresu e-mail, który ma być używany.                                                                                                    | Wcześniej podczas konfigurowania miejsca docelowego modułu ER adres e-mail adresata danych wyjściowych można było zdefiniować w czasie projektowania. Teraz można skonfigurować wyrażenie w formacie modułu ER. To wyrażenie można wybrać w lokalizacji docelowej jako źródło adresu e-mail osobno dla każdej konfiguracji formatu i każdego składnika danych wyjściowych (folderu lub pliku). W związku z tym podczas generowania raportu modułu ER każdy tworzony plik może być wysyłany do innego adresata, a adres e-mail można zdefiniować na podstawie logiki modułu ER i danych biznesowych. |
| Konfigurowanie miejsca docelowego raportów modułu ER w taki sposób, aby dane wyjściowe były wysyłane do folderu programu Microsoft SharePoint jako nowy nazwany plik lub nowa wersja istniejącego pliku oraz aby danych biznesowych można było używać w strukturze programu Microsoft Power BI jako zestawu danych lub jako raportu.                 | Teraz podczas konfigurowania raportów modułu ER można łatwo (bez pisania kodu źródłowego) przygotować wnioskowane dane biznesowe, tak aby mogły być używane przez strukturę programu Power BI. Podczas generowania tych raportów modułu ER można dostarczyć strukturze narzędzia Power BI odpowiednie dane biznesowe i/lub raporty programu Excel, które są już dostępne. Jeżeli zaplanujesz sesje generowania raportów w trybie cyklicznym, istnieje możliwość zaplanowania wymuszonego wysyłania danych biznesowych z programu Dynamics 365 for Operations do programu Power BI w celu obsługi harmonogramu aktualizacji raportów narzędzia Power BI.                             |
| Konfigurowanie raportów modułu ER w celu używania już wygenerowanej części dokumentu elektronicznego jako źródła danych do generowania pozostałej części tego dokumentu.                                                                                                                                             | Można tak skonfigurować raporty modułu ER tworzące dane wyjściowe w formacie tekstowym, aby zliczały wiersze dokumentu. Te informacje mogą być następnie używane w innych częściach dokumentu do tworzenia wierszy zawierających szczegóły podsumowań. Informacje podsumowujące (sumy i liczby) mogą być obliczane i drukowane na generowanych dokumentach elektronicznych, bez konieczności dodatkowego przekształcania danych. W związku z tym ta funkcja poprawia wydajność generowania raportów i ułatwia przyszłe zarządzanie skonfigurowanym formatem ER.    |
| Konfigurowanie raportów modułu ER w celu określenia rozszerzenia nazwy pliku dla dokumentów elektronicznych generowanych w formacie tekstowym.                                                                                                                                                                                 | Można tak skonfigurować raporty modułu ER, aby generowały dane wyjściowe w formacie tekstowym możliwym do zapisania jako plik z określonym rozszerzeniem. Oprócz domyślnego rozszerzenia .txt można skonfigurować rozszerzenia takie jak .csv i .prn, zgodnie ze specyfikacją formatu.                                                                                                                                                                                                                                                                             |
| Tworzenie nowych raportów modułu ER opartych na określonej wersji modelu ER.                                                                                                                                                                                                                          | Wcześniej podczas tworzenia nowego formatu ER można było użyć tylko najnowszej wersji wybranego modelu ER jako lokalizacji źródła danych tego formatu. Teraz można wybrać dowolną dostępną wersję wybranego modelu ER. Ta funkcja umożliwia obsługę raportów modułu ER w bieżącym roku i równolegle zaprojektowanie nowej wersji modelu ER dla następnego roku.                                                                                                                                                                                          |
| Przeszukiwanie źródeł danych i formatów/modeli na podstawie tekstu lub wybranego artefaktu za pomocą jednego kliknięcia. Aktywne rozwiązywanie konfliktów związanych ze zmianą bazy i rozwiązywanie konfliktów między konfiguracjami. Konfigurowanie raportów modułu ER w celu tworzenia wielu komunikatów sprawdzania poprawności dla błędów wykrytych do czasu zatrzymania generowania raportu. | Kilka udoskonaleń dotyczących środowiska użytkownika w strukturze ER pomaga użytkownikom efektywniej i łatwiej posługiwać się modułem ER.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Wyświetlanie obszaru roboczego **ER** w raportach programu Power BI.                                                                                                                                                                                                                                                      | Użytkownicy mogą skonfigurować stronę **Obszar roboczy ER**, tak aby zawierał nowe elementy menu i aktywne kafelki pozwalające uruchamiać raporty programu Power BI.                                                                                                                                                                                                                                                                                                                                                                                                                       |

## <a name="payroll"></a>Lista płac
<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfigurowanie rekordów płac i przetwarzanie listy płac za pomocą funkcji odpowiadających funkcjom modułu <strong>Lista płac</strong> w programie Microsoft Dynamics AX 2012 R3.</td>
<td>Teraz można skonfigurować i przetwarzać amerykańską listę płac przy użyciu zestawu funkcji odpowiadającego zestawowi funkcji w systemie AX 2012 R3.
<ul>
<li>Można skonfigurować cykle i okresy płac, cykle i okresy pracy, kody zarobków i grupy kodów zarobków, harmonogramy, typy urlopów i plany naliczania świadczeń.</li>
<li>Można także konfigurować obowiązkowe odliczenia na świadczenia i podatki oraz rejestrować informacje płacowe dla stanowisk i pracowników do celów sprawozdawczości i analizy.</li>
<li>Można także konfigurować i zarządzać potrąceniami dla zajęć wierzytelności i poboru podatków oraz dla wszelkich powiązanych opłat administracyjnych.</li>
</ul></td>
</tr>
<tr class="even">
<td>Monitorowanie i realizowanie procesu okresów płac za pomocą nowego obszaru roboczego <strong>Zarządzanie listą płac</strong>.</td>
<td>Teraz można łatwo monitorować przetwarzanie listy płac. W jednym oknie administratorzy listy płac widzą sprawozdania o zarobkach i wynagrodzeniach, którymi muszą się zająć, tak aby sesja obliczania wynagrodzeń została wykonana w całości i bez błędów. Obszar roboczy <strong>Zarządzanie listą płac</strong> pozwala użytkownikom monitorować i uruchamiać całościowe procesy z jednego miejsca.</td>
</tr>
<tr class="odd">
<td>Generowanie plików płatności dodatnich na potrzeby kontroli listy płac.</td>
<td>Istnieje nowe rozszerzenie funkcji płatności dodatnich w module Zarządzanie gotówką i bankami dotyczące płatności dla listy płac. W całym podstawowym procesie dodano osobne elementy menu umożliwiające obsługę izolowanej konfiguracji specyficznej dla listy płac. Funkcjonalność jest taka sama, jak w podstawowej funkcji płatności dodatnich wprowadzonej w aplikacji Microsoft Dynamics AX w wersji 7.0.1 (maj 2016 roku). Ze względu na to rozszerzenie dane listy płac są całkowicie odizolowane od pozostałych transakcji płatności dodatnich. Ta izolacja pomaga zagwarantować, że tylko użytkownicy listy płac mogą uzyskać dostęp i wyświetlać dane powiązane z listy płac.</td>
</tr>
<tr class="even">
<td>Importowanie wierszy sprawozdania o zarobkach z zewnętrznego źródła przy użyciu nowej jednostki danych Wiersz sprawozdania o zarobkach.</td>
<td>Ważna nowa jednostka danych pozwala na integrację z zewnętrznymi systemami obliczania czasu i dochodów. Jednostka danych importuje wiersze sprawozdania o zarobkach i wykonuje te same domyślne operacje, które użytkownik wprowadził bezpośrednio w sprawozdaniu o zarobkach. Po zaimportowaniu wiersze są automatycznie kojarzone z odpowiednim dokumentem sprawozdania o zarobkach. Jeśli odpowiedni dokument sprawozdania o zarobkach nie istnieje, zostanie utworzony automatycznie.</td>
</tr>
</tbody>
</table>

## <a name="planning-and-scheduling"></a>Planowanie i harmonogram

| Co można zrobić                                                                                                                                                                                                      | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurowanie domyślnych ustawień zamówień sprzedaży i zakupu w oparciu o dowolny aktywny wymiar produktu w produkcie głównym. W związku z tym można zdefiniować domyślne ustawienia zamówień dla jednostki magazynowej (SKU) lub częściowej SKU. | Można określić domyślne ustawienia zamówień, które będą stosowane do wymiaru produktu lub kombinacji wymiarów produktu. **Przykład** Sprzedajesz produkt o nazwie Koszulka polo. Ten produkt jest dostępny w dwóch kolorach: zielonym i niebieskim. Jest on również dostępny w dwóch rozmiarach: małym i średnim. Kolor i Rozmiar są aktywnymi wymiarami produktu dla koszulki polo. Można zablokować zakupy wszelkich zielonych koszulek polo, niezależnie od ich rozmiaru. |

## <a name="product-master-data"></a>Dane produktu głównego
<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfigurowanie wszystkich domyślnych ustawień zamówień oraz ustawień zamówień specyficznych dla oddziałów w tym samym czasie, na jednej stronie.</td>
<td>Ta funkcja zapewnia lepszy podgląd ustawień towaru.</td>
</tr>
<tr class="even">
<td>Tworzenie nazewnictwa dla numerów wariantów produktów.</td>
<td>W numerach wariantów produktu można umieścić elementy takie jak wymiary produktu, atrybuty i znaki. Podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu można szybko znaleźć konkretny wariant produktu.</td>
</tr>
<tr class="odd">
<td>Wyszukiwanie produktów i wariantów produktów w scenariuszach sprzedaży i zakupu.</td>
<td>Podczas tworzenia wiersza sprzedaży lub wiersza zakupu można wyszukiwać produkty przy użyciu wymiarów produktów oraz dowolnych numerów produktów, z wyjątkiem globalnych numerów jednostki handlowej (GTIN) i kodów kreskowych. To wyszukiwanie jest wyszukiwaniem pełnotekstowym, które zastępuje istniejące wyszukiwanie „Zaczyna się od” używane na listach wyszukiwania zakupu i sprzedaży. Ta funkcja umożliwia znajdowanie grup produktów, które mają podobne właściwości, lub pojedynczych produktów, które mają unikatowe cechy. Aby włączyć tę funkcję, należy zaznaczyć parametr <strong>Włącz odnośniki na potrzeby wyszukiwania produktów</strong> na stronie <strong>Parametry wyszukiwania</strong>.</td>
</tr>
<tr class="even">
<td>Określanie wariantu produktu bezpośrednio podczas tworzenia transakcji sprzedaży lub zakupu. Alternatywnie można na liście wybrać prawidłowe kombinacje wymiarów.</td>
<td>Ta funkcja usprawnia pracę. <strong>Przykład</strong> Sprzedajesz produkt o nazwie Koszulka polo. Ten produkt jest dostępny w dwóch kolorach: zielonym i niebieskim. Jest on również dostępny w dwóch rozmiarach: małym i średnim. Kolor i Rozmiar są aktywnymi wymiarami produktu dla koszulki polo. Podczas wprowadzania wiersza sprzedaży dla koszulki polo o małym rozmiarze i zielonym kolorze nie trzeba wprowadzać danych w polach <strong>Numer pozycji</strong>, <strong>Kolor</strong> ani <strong>Rozmiar</strong>. Wiersz można utworzyć za pomocą jednej z następujących czynności:
<ul>
<li>W polu <strong>Numer pozycji</strong> wprowadź numer wariantu produktu, wartość koloru lub rozmiar. W wynikach wyszukiwania znajdź określony wariant, który chcesz sprzedawać, i utwórz wiersz sprzedaży.</li>
<li>W polu <strong>Numer pozycji</strong> wpisz numer towaru. Przejdź do dowolnego pola wymiaru produktu. W wynikach wyszukiwania <strong>Wymiar produktu</strong> zostaną wyświetlone wszystkie zwolnione kombinacje wymiarów, które dotyczą koszulki polo. W jednym kroku można wybrać wariant produktu, który chcesz sprzedawać.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Określanie, czy numery produktów są wyświetlane na stronach transakcyjnych.</td>
<td>Strony transakcyjne, takie jak strony zamówień sprzedaży lub zamówień zakupu, zawierają tylko pola <strong>Numer pozycji</strong> i <strong>Nazwa produktu</strong>. Aby wyświetlić pole <strong>Numer produktu</strong>, zaznacz parametr <strong>Pokaż numery produktów w formularzach</strong> w obszarze <strong>Parametry modułu Zarządzanie informacjami o produktach</strong>.</td>
</tr>
</tbody>
</table>

## <a name="project-management-and-accounting"></a>Zarządzanie projektami i ich księgowanie

| Co można zrobić                                                                                                           | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Używanie opcji wyboru później podczas księgowania propozycji faktur w partii.                                                            | Księgowi projektu mogą skonfigurować zadanie wsadowe, które będzie automatycznie pobierać propozycje faktur do zaksięgowania, jeśli te propozycje spełniają kryteria określone w zadaniu wsadowym. Ta funkcja zwiększa automatyzację księgowania faktur, ponieważ zadanie wsadowe może działać w sposób ciągły i automatycznie pobierać propozycje do zaksięgowania. |
| Tworzenie analiz w aplikacji Power BI Desktop.                                                                                     | Analizę biznesowej (BI) danych projektów i zasobów można łatwo tworzyć w aplikacji Power BI Desktop.                                                                                                                                                                                                       |
| Używanie przedpłat do zamówień zakupu i ich poprawne uwzględnianie w procesie szacowania projektu.                               | W przypadku zamówień zakupu dla projektów należy przetworzyć przedpłaty, zanim niektóre płatności można zwolnić do dostawców. Te faktury zaliczkowe są teraz wyświetlane w procesie szacowania/uznawania projektów typu **Stała cena**.                                                                                           |
| Dostęp i zarządzanie szacunkami kosztów i przychodów oraz zapotrzebowaniami na towary bezpośrednio z zadania w strukturze podziału pracy (WBS). | Można zarządzać szacunkami kosztów, szacunkami przychodów i zapotrzebowaniami na towary dla określonego zadania WBS w oknie dialogowym szczegółów tego zadania w widoku planowania WBS.                                                                                                                                                                 |
| Wybieranie źródła finansowania w arkuszach opłat.                                                                                    | Jeśli umowa na projekt zawiera wiele źródeł finansowania, można wybrać jedno konkretne źródło finansowania podczas księgowania opłat. Jeśli nie wybierzesz określonego źródła finansowania, do przydzielenia opłat będą używane reguły finansowania podane w umowie.                                                                   |
| Otwieranie zestawień projektów w programie Excel.                                                                                         | Nowe jednostki danych dla aktualizacji ksiąg i budżetów umożliwiają otwieranie danych zestawień projektów w programie Excel i tworzenie analiz za pomocą funkcji programu Excel.                                                                                                                                                                           |
| Używanie tylko jednego klucza konfiguracji do włączania funkcji zarządzania projektami i ich księgowania (PMA).                       | Klucze konfiguracji dotyczące projektów zostały zastąpione przez jeden klucz konfiguracji Projekt, który powoduje włączenie funkcji PMA.                                                                                                                                                                                                       |

## <a name="retail-and-commerce"></a>Handel detaliczny i inny
### <a name="advanced-warehouse-management-in-a-retail-store"></a>Zaawansowane zarządzanie magazynem w sklepie sieci sprzedaży

Sprzedawcy detaliczni mogą używać rozwiązania zaawansowanego zarządzania magazynem (WHS) w swoich sklepach oraz na jego potrzeby wprowadzać wymagane aktualizacje bieżących funkcji punktu sprzedaży (POS). Procesy na urządzeniu podręcznym powinny działać w sklepie tak samo, jak w każdym innym magazynie. Wszystkie bieżące procesy magazynu sklepu sieciowego i wszystkie procesy punktu sprzedaży, które tworzą lub aktualizują transakcje magazynowe, są aktualizowane, tak aby używały konkretnych wymagań dla magazynów z obsługą WHS.

| Co można zrobić                                                                       | Dlaczego to jest ważne                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wykorzystywanie punktu sprzedaży do wyszukiwania dostępnych zapasów w sklepach z obsługą WHS.                     | Podczas wyszukiwania zapasów proces powinien działać tak samo, jak wcześniej. Wyszukiwanie powinno zwracać dostępne ilości na poziomie magazynu i nie powinno brać pod uwagę wymiarów lokalizacji, stanu zapasów ani numeru identyfikacyjnego. |
| Wykorzystywanie punktu sprzedaży do przetwarzanie przyjęć produktów dla zamówień przeniesienia w sklepie obsługującym WHS. | Dla sklepów i towarów z obsługą WHS można przyjmować towary z zamówień przeniesienia w punkcie sprzedaży. Użytkownik powinien mieć możliwość wyboru lokalizacji, w których będą wykonywane przyjęcia, oraz wprowadzania numerów identyfikacyjnych, co pozwoli automatycznie wypełniać wiersze przyjęć.    |
| Wykorzystywanie punktu sprzedaży do przetwarzanie przyjęć produktów dla zamówień zakupu w sklepie obsługującym WHS. | Dla sklepów i towarów z obsługą WHS można przyjmować towary z zamówień zakupu w punkcie sprzedaży. Użytkownik powinien mieć możliwość wyboru lokalizacji, w których będą wykonywane przyjęcia, oraz wprowadzania numerów identyfikacyjnych, co pozwoli automatycznie wypełniać wiersze przyjęć.    |
| Wykorzystywanie punktu sprzedaży do przetwarzania wysyłki produktów z sklepu obsługującego WHS.               | Dla sklepów i towarów z obsługą WHS można rejestrować przeniesienia z punktu sprzedaży. Użytkownik powinien mieć możliwość wyboru źródłowych lokalizacji wysyłki, stan zapasów powinien być generowany automatycznie, a numery identyfikacyjne powinny być ignorowane.         |

### <a name="enable-seamless-omni-channel-commerce"></a>Korzystanie z bezproblemowego handlu wielokanałowego.

Bezproblemowy handel wielokanałowy odnosi się do zarządzania i przetwarzania zamówień obejmującego sklepy tradycyjne, sklepy internetowe, biura obsługi i urządzenia komórkowe. W tej wersji dokonaliśmy następujących zmian w tym obszarze:

-   Ulepszenia dotyczące publikowania ofert sklepów internetowych.
-   Nowa komórkowa aplikacja dla konsumentów, która ułatwia znajdowanie produktów, zarządzanie klientami i zakupy przez Internet.

| Co można zrobić                                                                                                                                                                                                                                                                   | Dlaczego to jest ważne                                                                                                                                                            |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konsument: Bieżąca wersja aplikacji konsumenckiej zawiera następujące funkcje: wyszukiwanie produktów, przeglądanie kategorii, dodawanie do koszyka i obsługa kasowa gości. Sprzedawcy detaliczni mogą również dodawać ikonografię swoich marek do aplikacji, a następnie stosować ją do swoich aplikacji sklepów dla systemów Android i iOS. | Sprzedawcy detaliczni mogą łatwo tworzyć aplikacje dla konsumentów, które umożliwiają osobom będącym gośćmi (nie zarejestrowanymi użytkownikami) przeglądanie, wyszukiwanie produktów i wysyłanie produktów z urządzeń przenośnych.                      |
| Listy życzeń klientów w sklepach internetowych.                                                                                                                                                                                                                             | Niezależni dostawcy oprogramowania (ISV) mogą używać formantu listy życzeń, aby umożliwić użytkownikom tworzenie wielu list w sklepach internetowych i zarządzanie nimi, a także wyświetlanie/używanie tych list w punkcie sprzedaży. |
| Asynchroniczne tworzenie odbiorców w sklepach internetowych.                                                                                                                                                                                                                  | Dostawcy ISV mogą teraz tworzyć konta klientów nawet wtedy, gdy usługa Commerce Data Exchange: Real-time Service jest niedostępna.                                                                        |
| Publikowanie produktów w kanałach z programu Retail Server do sklepów innych producentów.                                                                                                                                                                                                           | Program Retail Server obsługuje teraz uwierzytelnianie między usługami. Dostawcy ISV mogą korzystać z funkcji publikowania produktów w kanałach z programu Retail Server do zewnętrznych sklepów.               |

### <a name="extensibility"></a>Możliwości rozszerzania

-   Projekty środowiska uruchomieniowego Commerce Runtime (CRT) są teraz odizolowane od zestawu SDK modułu Retail.
-   Łatwiejsze wdrażanie i obsługa za pomocą modułowych pakietów składników Microsoft i pakietów dostawców ISV dla punktu sprzedaży, modułów Retail Server i płatności, baz danych oraz stacji sprzętowych.

| Co można zrobić                                                                                                                 | Dlaczego to jest ważne                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CRT/Retail Server: Sprzedawcy detaliczni i dostawcy ISV mogą rozszerzać funkcjonalność środowiska CRT za pomocą mechanizmów przechwytywania komunikatów. Zmiany wewnątrz kodu źródłowego nie są już obsługiwane. | Aby umożliwić ustawiczną integrację i wdrażanie, należy całkowicie unikać modyfikowania kodu źródłowego programu. Ponadto umożliwi to łatwe pobieranie poprawek bez konieczności scalania kodu ani specjalnego wdrażania składników środowiska CRT. |

### <a name="personalized-product-recommendations"></a>Spersonalizowane rekomendacje produktów

| Co można zrobić                                                                                                                                                                                                                                                                        | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wyświetlanie spersonalizowanych rekomendacje produktów w wielu miejscach bezpośredniej interakcji w punkcie sprzedaży (POS) w celu określenia, czym odbiorca może być zainteresowany, w oparciu o jego historię zakupów, towary na liście ich życzeń oraz towary, które inni podobni odbiorcy kupowali w sklepach internetowych i tradycyjnych. | U sprzedawców detalicznych z dużymi katalogami spersonalizowane rekomendacje pomagają odbiorcom znajdować ciekawe inne produkty, a sprzedawcom umożliwiają bardziej przemyślaną obsługę odbiorców. Eksponując produkty ukierunkowane na zainteresowania i nawyki zakupowe odbiorców, rekomendacje produktów mogą pomóc sprzedawać dodatkowe produkty oraz wzmacniać lojalność odbiorców. W programie Microsoft Dynamics 365 for Retail funkcjonalność rekomendacji produktów bazuje na usługach Cognitive Services i aparacie uczenia maszynowego Microsoft Azure. |

### <a name="pos-task-recorder"></a>Rejestrator zadań w punkcie sprzedaży

| Co można zrobić                                                                                                                                                                                                  | Dlaczego to jest ważne                                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sprzedawcy detaliczni mogą używać rejestratora zadań w punkcie sprzedaży do generowania materiałów szkoleniowych, diagramów narzędzia do modelowania procesów biznesowych (BPM) i zawartości Pomocy w celu poprawy wydajności pracy oraz lepszego analizowania i projektowania aplikacji. | Aby umożliwić ustawiczną integrację i wdrażanie, należy całkowicie unikać modyfikowania kodu źródłowego programu. Ponadto umożliwi to łatwe pobieranie poprawek bez konieczności scalania kodu ani specjalnego wdrażania składników środowiska CRT. |
| Pomoc w czasie rzeczywistym w punkcie sprzedaży.                                                                                                                                                                                           | Kasjer/menedżer może uzyskiwać pomoc w czasie rzeczywistym w punkcie sprzedaży na temat procesów biznesowych bez przełączania kontekstu.                                                                                                           |

### <a name="store-system-providing-a-seamless-on-premises-store-experience"></a>System sklepu: zintegrowana funkcjonalność sklepu stacjonarnego

System sklepu to opcja wdrożeniowa dla sprzedawców detalicznych, która pomaga wykonywać szereg operacji sklepowych w sklepie tradycyjnym, publicznej chmurze Microsoft lub prywatnej chmurze klienta. W tym wydaniu zakres ogranicza się do wewnętrznych operacji sklepowych. W celu lepszej obsługi środowisk, gdzie istnieją wolne lub niestabilne połączenia sieciowe, trzeba udostępnić sprzedawcom detalicznym opcję wdrożenia bazy danych kanału i programu Retail Server w sklepie. Wtedy będą mogli kontynuować realizację swoich podstawowych scenariuszy biznesowych nawet przy braku łączności z centralą (HQ). Na podstawie informacji zebranych różnymi metodami, w tym dyskusji z zespołem inżynieryjnym, wyników ankiet wśród klientów i analizy konkurentów, zidentyfikowaliśmy następujący zakres rozwiązania jako najlepiej pasujący do potrzeb naszych docelowych klientów:

-   System sklepu jest dostępny jako samoobsługowy pakiet.
-   Domyślna instalacja to kompletne gotowe rozwiązanie, ale jest możliwe wdrażanie niestandardowe.
-   Łatwe wdrażanie/samodzielna obsługa.
-   Program Retail Server i baza danych sklepu są instalowane w sklepie, razem z usługą Async Client.
-   Program Retail Server w sklepie komunikuje się bezpośrednio z serwerem obiektów aplikacji (AOS) w centrali należącym do systemu sklepu.
-   Obsługa scenariuszy sieci wewnątrzterminalowej w przypadku, gdy nie ma łączności z centralą.
-   Moduły Retail Modern POS i Cloud POS zawsze komunikują się z serwerem Retail Server w sklepie.
-   Obsługa modułów Retail Modern POS i Cloud POS w razie braku łączności z centralą.
-   Obsługa baz danych offline specyficznych dla modułu Retail Modern POS (izolowanych dla każdego wystąpienia modułu Retail Modern POS) w przypadku, gdy nie ma łączności z centralą.
-   Uwierzytelnianie odbywa się między usługami tylko dla systemu sklepu.
-   Wywołania usług Real-time Service nie są obsługiwane w przypadku braku łączności z Internetem.
-   Bezpośrednia łączność modułu Retail Modern POS z bazą danych kanału nie jest obsługiwana.
-   Możliwość telemetrii/monitorowania.

| Co można zrobić                                                                                                                                       | Dlaczego to jest ważne                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Sprzedawca detaliczny pobiera samoobsługowego instalatora systemu sklepu ze strony bazy danych kanału w module centrali w systemie Dynamics AX oraz pobiera plik konfiguracji.   | Sprzedawca detaliczny można bezproblemowo pobrać samoobsługowy pakiet.                                          |
| Sprzedawca detaliczny instaluje system sklepu z samoobsługowego instalatora.                                                                                 | Sprzedawca detaliczny może zainstalować system sklepu z pakietu samoobsługowego.                                |
| Menedżer IT konfiguruje system sklepu w programie Dynamics 365 for Operations (bazę danych kanału, profil kanału, sklep i pakiet instalacyjny).             | Menedżer IT może łatwo i skutecznie skonfigurować system sklepu.                                       |
| Sprzedawca detaliczny używa modułu Retail Modern POS w lokalnym sklepie i może wykonywać operacje w czasie rzeczywistym, takie jak obsługa kart upominkowych, gdy istnieje łączność. | Sprzedawca detaliczny może wykonywać operacje w czasie rzeczywistym z poziomu systemu sklepu, gdy ma łączność z Internetem.                |
| Sprzedawca detaliczny może synchronizować dane lokalnego systemu sklepu w centralą zawsze, gdy istnieje połączenie.                                                      | Sprzedawca detaliczny może synchronizować dane z i do systemu sklepu, gdy ma łączność z Internetem.                              |
| Sprzedawca detaliczny może mieć bezpieczną komunikację między lokalnym systemem sklepu a centralą.                                                                 | Sprzedawca detaliczny może bezpiecznie komunikować się z poziomu systemu sklepu, gdy ma łączność z Internetem.                     |
| Kierownik działu IT i dział operacyjny Microsoft mogą monitorować lokalny system sklepu i składać o nim sprawozdania (zmiany w zakresie diagnostyki i raportowania).                   | Kierownik działu IT i dział operacyjny Microsoft mogą bezpiecznie monitorować lokalny system sklepu i sprawnie rozwiązywać problemy. |

### <a name="universal-windows-platform-app-for-retail-modern-pos"></a>Aplikacja Retail Modern POS na platformę uniwersalną systemu Windows

Obecnie moduł Retail Modern POS jest dostępny tylko jako aplikacja systemu Windows 8.1 na komputery stacjonarne i tablety, a moduł Cloud POS jako usługa do przeglądarek na komputerach stacjonarnych i tabletach. W tej wersji moduł Retail Modern POS jest przekształcany na aplikację zgodną z platformą uniwersalną systemu Windows. Ta zmiana umożliwi uruchamianie modułu Retail Modern POS na wszelkich urządzeniach z systemem Windows 10 (komputerach stacjonarnych, tabletach i telefonach), a nawet przełączanie między widokami na urządzeniach obsługujących standard Continuum.

| Co można zrobić                                                   | Dlaczego to jest ważne                                                                                     |
|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Włączanie ważnych funkcji punktu sprzedaży dla małych urządzeń. | Funkcje modułu Retail POS są dostępne dla telefonów i innych niewielkich (przenośnych) urządzeń wyposażonych w system Windows 10. |

## <a name="supply-chain-management"></a>Zarządzanie łańcuchem dostaw
### <a name="consignment-inventory"></a>Zapasy konsygnacyjne

| Co można zrobić                                                                                                                                                                | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dostawca może przechowywać surowce w magazynie odbiorcy. Odbiorca może odraczać faktyczny zakup do czasu, aż surowce są wymagane do produkcji. | Utrzymywanie zapasów surowców może powodować poważne koszty. Korzystając z funkcji zapasów konsygnacyjnych, dostawca może przechowywać surowce w magazynie odbiorcy. Odbiorca może wtedy odraczać faktyczny zakup do czasu, aż surowce są wymagane do produkcji. Surowce są zamawiane i przyjmowane przy użyciu zamówienia uzupełnienia zapasów konsygnacyjnych. To zamówienie uzupełnienia rejestruje fizyczne transakcje, ale nie ma wpływu na księgę główną. Aby odróżniać między pozycjami magazynowymi należącymi do odbiorców i dostawców, można używać wymiaru zapasów właściciela. Zmiana własności zapasów jest obsługiwana przez proces arkusza, który zarządza przeniesieniem własności surowców z dostawcy na odbiorcę. Ten proces inicjuje tworzenie zamówienia zakupu i dokumentu przyjęcia produktów. **Uwaga:** Ta funkcja jest ograniczona do konsygnacji przychodzącej surowców do produkcji. Nie jest zintegrowana z modułami zarządzania magazynem (WHS) i zarządzanie transportem (TMS). |
| Dostawca może uzyskiwać informacje o ilości zapasów konsygnacyjnych przesyłanych do odbiorcy.                                                                      | Aby zafakturować odbiorcę, dostawca potrzebuje informacji o surowcach zakupionych z zapasów konsygnacyjnych i o dacie zakupu. Dostawca może również monitorować dostępne zapasy w siedzibie odbiorcy, używając do tego interfejsu współpracy z dostawcami.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Przenoszenie zapasów należących do dostawcy za pomocą arkusza przeniesień.                                                                                                                       | Aby śledzić fizyczne położenie zapasów będących własnością dostawcy, trzeba mieć możliwość rejestrowania położenia w systemie. Za pomocą arkusza przeniesień można rejestrować fizyczne przesunięcia zapasów, takie jak przesunięcie z jednej lokalizacji w magazynie do innej lokalizacji w tym samym magazynie.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Korygowanie zapasów należących do dostawcy za pomocą arkusza inwentaryzacji.                                                                                                                     | Ważne jest, aby ilość dostępnych zapasów zapisana w systemie była taka sama, jak fizycznie istniejące zapasy. Zapasy należące do dostawcy można korygować w górę i w dół przy użyciu procesów inwentaryzacji, takich jak procesy korekty ilości i procesy arkusza inwentaryzacji.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Uzyskiwanie dodatkowych informacji o obsłudze konsygnacji w programie Dynamics 365 for Operations.                                                                                                         | Aby uzyskać więcej informacji o obsłudze procesów konsygnacji, zobacz tematy [Konsygnacja](../../supply-chain/inventory/consignment.md), [Konfigurowanie konsygnacji](../../supply-chain/inventory/set-up-consignment.md), [Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych (przewodnik po zadaniu)](../../supply-chain/inventory/tasks/create-consignment-replenishment-order.md) i [Zmiana własności zapasów konsygnacyjnych w oparciu o zapotrzebowanie produkcyjne](../../supply-chain/inventory/tasks/change-ownership-consignment.md).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

### <a name="vendor-collaboration-previously-known-as-the-vendor-portal"></a>Portal współpracy z dostawcami (znany wcześniej jako portal dostawców)

| Co można zrobić                                                                      | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dostawcy mogą reagować na każdy wiersz zamówienia zakupu i sugerować zmiany.           | W niektórych przypadkach dostawcy chcą zaakceptować niektóre wiersze zamówienia zakupu, a inne odrzucić. Teraz dostawcy mogą zarządzać indywidualnymi wierszami zamówień zakupu. Każdy wiersz można odrzucić, zaakceptować lub zaakceptować ze zmianami. Na przykład dostawcy mogą zmieniać datę dostawy, dzielić dostawę i ilości lub sugerować alternatywne towary.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Dostawcy mogą zarządzać danymi osób kontaktowych.                                 | Dostawcy mogą przechowywać i aktualizować dane osób kontaktowych dla swoich firm. Informacje te obejmują imiona i nazwiska, adresy e-mail i numery telefonów. Dostęp do tej funkcji jest udzielany za pomocą dedykowanej roli zabezpieczeń.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Udostępnianie dostawcom dokumentów powiązanych z zamówieniami zakupu.                    | Gdy należy udostępnić dokument dostawcy, np. dokument o wymaganiach, wygodnie jest połączyć dokument z odpowiednim zamówieniem zakupu. Dostawca może wtedy udostępnić notatki i załączniki odbiorcy poprzez połączenie dokumentu ze swoją odpowiedzią na zamówienie zakupu. Zarządzanie dokumentami to bazowa struktura pomocnicze, a dostawcom mogą być udostępniane tylko notatki i załączniki, które są sklasyfikowane jako „zewnętrzne”.                                                                                                                                                                                                                                                                                                                              |
| Inicjowanie obsługi nowych użytkowników u dostawców.                                                          | Jeżeli dostawcy korzystają z interfejsu współpracy z dostawcami, mogą w prosty sposób wnioskować o nowe konta użytkowników, gdy nowe kontakty potrzebują dostępu do portalu współpracy z dostawcami. Specjaliści ds. zaopatrzenia mogą składać wnioski o konta użytkowników dla osób kontaktowych w organizacji dostawcy. Osoba kontaktowa u dostawcy, która już jest użytkownikiem dodanym w portalu współpracy z dostawcami, również może przesyłać tego typu wnioski. Ten wniosek powoduje ostatecznie utworzenie w programie Dynamics 365 for Operations nowego użytkownika, który ma role zabezpieczeń specyficzne dla dostawcy. Umożliwia również wysyłanie wniosku do portalu B2B Microsoft Azure o zainicjowanie obsługi użytkownika poprzez dodanie nowego konta użytkownika w usłudze Azure Active Directory (Azure AD). Dostawcy mogą także prosić o zdezaktywowanie określonych kont użytkowników u dostawcy oraz o zmodyfikowanie ról zabezpieczeń. |
| Uzyskiwanie dodatkowych informacji o obsłudze współpracy z dostawcami w programie Dynamics 365 for Operations. | Aby uzyskać więcej informacji o współpracy z dostawcami, zobacz [Współpraca z zewnętrznymi dostawcami](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md), [Współpraca dostawców z odbiorcami](../../supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations.md), [Zarządzanie użytkownikami portalu współpracy z dostawcami](../../supply-chain/procurement/manage-vendor-collaboration-users.md), [Konfigurowanie i obsługa współpracy z dostawcami](../../supply-chain/procurement/set-up-maintain-vendor-collaboration.md) oraz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).                                                         |

### <a name="intercompany-order-processing"></a>Przetwarzanie zamówień międzyfirmowych

<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Definiowanie — bezpośrednio w wierszach zamówienia sprzedaży — źródła popytu i sposobu jego zaspokojenia. <strong>Przykład</strong> Utwórz wiersz zamówienia sprzedaży i jako typ dostawy określ dostawę bezpośrednią. Główny dostawca zostanie dodany do wiersza zamówienia sprzedaży jako punkt pozyskiwania.</td>
<td>Przepływ operacji zbierania zamówień został znacznie udoskonalony. Teraz można zdefiniować — bezpośrednio w wierszach zamówienia sprzedaży — źródła popytu i sposobu jego zaspokojenia. Już nie trzeba czekać, aż wszystkie wiersze zostaną dodane do zamówienia sprzedaży. Nowe opcje w wierszach zamówienia sprzedaży pozwalają określić typ dostawy podczas określania dostawcy. Po skojarzeniu dostawcy z wierszami zamówienia sprzedaży są tworzone łańcuchy zamówień dla dostawy od dostawcy.
<ul>
<li>Dostawcą może być dostawca międzyfirmowy wykorzystujący wewnętrzne zamówienie zakupu i zamówienie sprzedaży albo dostawca zewnętrzny, który wykorzystuje zewnętrzne zamówienie zakupu.</li>
<li>Typem dostawy może być <strong>Dostawa bezpośrednia</strong> lub <strong>Zapasy</strong>. Typ dostawy <strong>Zapasy</strong> wskazuje, że dostawca powinien dostarczać do lokalnych zapasów, zanim nastąpi wysyłka do odbiorcy.</li>
</ul></td>
</tr>
<tr class="even">
<td>Tworzenie promesy zamówienia bezpośrednio z wierszy zamówienia sprzedaży. <strong>Przykład</strong> Utwórz wiersz zamówienia sprzedaży, który jest zaspokajany przez dostawcę międzyfirmowego. Wyjdź z wiersza. Daty dostaw zostaną obliczone na podstawie dostępności w firmie zaopatrującej.</td>
<td>Podczas tworzenia wierszy zamówienia sprzedaży wykorzystujących nowe informacje o pozyskiwaniu daty dostawy są obliczane zgodnie z formantem <strong>Data dostawy</strong>. Na przykład jeśli jest wybrany dostawca międzyfirmowy, jest obliczana dostępność w firmie zaopatrującej. W ten sposób łańcuchy zamówień są tworzone automatycznie razem z wierszami zamówienia sprzedaży. Ta funkcja pomaga zagwarantować, że daty dostawy będą widoczne w firmie zaopatrującej, dzięki czemu profile dostępności zapasów (ATP) mogą obsługiwać przewidywany popyt bezpośrednio w trakcie tworzenia zamówień sprzedaży.</td>
</tr>
<tr class="odd">
<td>Przeglądanie dostępności produktów we wszystkich lokalizacjach zaopatrzenia i wybieranie najlepszej opcji zaopatrzenia.</td>
<td>Strona <strong>Dostawy alternatywne</strong> została przeprojektowana i teraz dostarcza cennych informacji o wszystkich zatwierdzonych dostawcach wewnętrznych i zewnętrznych. Informacje te obejmują opcje pozyskiwania dla zaopatrzenia przez dostawców. Po wybraniu metody dostawy system obliczy wykonalne daty dostaw. Można bezproblemowo wybrać opcję najlepszą dla odbiorcy i zastosować ją do każdego wiersza zamówienia sprzedaży.</td>
</tr>
</tbody>
</table>

### <a name="warehouse-enhancements-for-high-volume-distribution-centers"></a>Ulepszenia w obsłudze magazynu dla centów dystrybucyjnych o dużej przepustowości

| Co można zrobić                                                              | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tworzenie pracy po spakowaniu towarów w stacji pakowania.               | Ta funkcja jest przydatna, gdy istnieją dodatkowe procesy po pracy ręcznego pakowania (np. paletyzacja, kontrola jakości, konsolidacja wysyłek lub zmiany na rampach załadunkowych). Nowy typ pracy **Pobieranie zapakowanych kontenerów** umożliwia modelowanie tych zadań za pomocą osobnych wierszy pracy. Teraz można tak modelować stacje pakowania, aby generować pracę po zapakowaniu. Ta praca może służyć do organizowania przesunięcia spakowanych zapasów.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Grupowanie kontenerów w stacji pakowania.                                     | Ta funkcja umożliwia grupowane wielu opakowań w jednym kontenerze lub pod jednym numerem identyfikacyjnym w stacji pakowania. Na przykład operator sklepu internetowego/hurtowni może zgrupować 100 osobnych opakowań w jeden kontener (np. paletę lub klatkę). Ten kontener można następnie przenieść, przygotować lub załadować za pomocą jednej instrukcji pracy, którą wygeneruje pracownik poprzez zeskanowanie jednego kodu kreskowego (numeru identyfikacyjnego) dla grupowego kontenera. Ta funkcja minimalizuje liczbę transakcji pracy potrzebnych do przeniesienia wielu mniejszych spakowanych kontenerów. Aby uzyskać więcej informacji, patrz [Tworzenie elementu menu urządzenia mobilnego dla konsolidacji na podstawie numerów identyfikacyjnych (przewodnik po zadaniu)](../../supply-chain/warehousing/tasks/create-mobile-device-license-plate-consolidation.md).                                                                                                                                                                                                                                                                                                                                                                                            |
| Tworzenie zasady zwalniania spakowanych kontenerów.                               | Pracy wyzwalana zwolnieniem kontenera może być tworzona automatycznie lub ręcznie. W opcji automatycznej praca jest generowana podczas zamykania kontenera przy użyciu dyrektywy lokalizacji i struktury szablonu pracy. W przypadku zwolnienia ręcznego pakowacz może określić, czy praca ma być wygenerowana dla jednego kontenera, czy grupy kontenerów. Ta funkcja ogranicza ryzyko, że zamknięte kontenery zostaną pobrane i przeniesione, zanim będą gotowe do przeniesienia ze stacji pakowania. Umożliwia także grupowe zwalnianie niesterowane przez system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Zmiana alokacji dla pobierania w niedomiarze.                                                   | Dodano obsługę procesów pobierania w niedomiarze, aby pomóc pracownikowi, który nie można pobrać towarów, a chce zrealizować zamówienie, gdy wymagany towar jest dostępny w innej lokalizacji. Istnieje możliwość używania procesu automatycznej zmiany alokacji, który wykorzystuje te same dyrektywy lokalizacji do pobrania towarów, jeśli są one dostępne w innej lokalizacji. Alternatywnie w przypadku ręcznej zmiany alokacji na urządzeniu przenośnym jest wyświetlana lista lokalizacji wraz z dostępnymi ilościami. Pracownik magazynu może wtedy wybrać lokalizację, z której zapasy mają zostać użyte. Te dwie metody można ustawić indywidualnie lub połączyć w jedno polecenie w menu pracownika magazynu. W przypadku używania ręcznej zmiany alokacji pracownik magazynu może pobrać ilości towaru będącego w niedomiarze z kilku lokalizacji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze (przewodnik po zadaniu)](../../supply-chain/warehousing/tasks/set-up-short-picking-item-reallocation.md).                                                                                                                                                                                          |
| Przenoszenie zapasów, z którymi jest powiązana praca.                             | Teraz można przenosić zapasy, z którymi jest powiązana praca. Ta funkcja może być przydatna, jeśli na przykład pracownik chce opróżnić część miejsca w doku rozładunkowym i zarejestrowane palety, które oczekują na odłożenie, przenieść do innej lokalizacji rozładunkowej. Dok zostanie opróżniony i może przyjąć dodatkowe towary, a przeniesione zapasy zostaną zaktualizowane nowymi informacjami o odłożeniu. Ta funkcja może także służyć do zwalniania miejsca w lokalizacjach pobrania poprzez przeniesienie zapasów mających powiązaną pracę i utworzenie miejsca na uzupełniające zapasy. Można jej również używać do przenoszenia ładunków między lokalizacjami pośrednimi bez utraty wygenerowanej pracy załadunku. W ten sposób funkcja pomaga zoptymalizować czas potrzebny na załadowanie przyjeżdżających ciężarówek. Można przenosić zapasy zarezerwowane dla zamówień sprzedaży, wydań do zamówień przeniesienia, przyjęć do zamówień przeniesienia i zamówień zakupu. Przesunięcie nie będzie możliwe, jeśli spowodowałoby podział wierszy. Na przykład jeśli masz wiersz pracy dla 100 sztuk towaru, nie można przenieść tylko 30 sztuk tego towaru do innej lokalizacji. |
| Scalanie numerów identyfikacyjnych mających powiązaną pracę.                    | Można scalać numery identyfikacyjne, z którymi jest powiązana praca wychodząca. Na przykład jeżeli pobranie zostało podzielone na kilka fragmentów pracy, warto zezwolić na scalenie towarów pod numerami identyfikacyjnymi po dostarczeniu do lokalizacji pośredniej. Towary pod numerami identyfikacyjnymi można konsolidować tylko wtedy, gdy znajdują się w tej samej lokalizacji, należą do tego samego ładunku i mają te same informacje o wysyłce.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Zamrażanie pracy pobierania skojarzonej z uzupełnieniem zapasów na poziomie wiersza. | Teraz można zamrozić pracę na poziomie wiersza zamiast na poziomie nagłówka, tak aby pracownicy mogli realizować wiersze pobrania, które nie są zamrożone przez uzupełnienie zapasów popytu. W związku z tym hurtownik, który ma duże zamówienia sprzedaży, lub sprzedawca detaliczny, który ma duże zamówienia sprzedaży albo zamówienia przeniesienia dla uzupełnienia zapasów, może zezwolić na rozpoczęcie pracy pobierania dla wszystkich wierszy, które nie są przedmiotem pracy uzupełniania zapasów. Następnie prace pobierania i uzupełniania zapasów można wykonywać równolegle. Tę funkcję można skonfigurować w taki sposób, aby można było wybierać, czy zamrażanie ma się odbywać na poziomie nagłówka, czy wiersza. Można także używać obu tych metod i utworzyć szablon pracy dla każdej metody. Konfiguracja nagłówka/wiersza jest ustawiana w szablonach pracy, ale można ją zmieniać bezpośrednio w wygenerowanej pracy.                                                                                                                                                                                                                                                                                                                                                                      |
| Anulowanie pracy za pomocą urządzenia przenośnego.                                      | Teraz za pomocą urządzenia przenośnego można anulować pracę, która zawiera lub nie zawiera uzupełniania zapasów popytu. Wcześniej trzeba było używać pełnego klienta. Aby włączyć tę funkcję, należy dla urządzenia przenośnego utworzyć element menu, w którym jest tryb ustawiony na **Pośrednie**, a kod działania na **Anuluj pracę**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="warehouse-operation-enhancements"></a>Ulepszenia w dziedzinie obsługi magazynu

| Co można zrobić                    | Dlaczego to jest ważne                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modelowanie różnych typów kontenerów.   | W magazynie mogą być używane różne typy kontenerów w celu optymalizacji składowania i z innych przyczyn. Nowa jednostka Typ kontenera ma fizyczne cechy typu kontenera (pojemnika). Teraz można skojarzyć numery identyfikacyjne z określonym typem kontenera i używać limitów składowania w lokalizacjach. Na przykład można użyć tej funkcji do kontrolowania liczby palet (lub innych typów kontenerów) w konkretnej lokalizacji. Typy kontenerów zostały również dodane do grup sekwencji jednostek w celu dodania domyślnych typów kontenerów dla procesu przyjmowania towarów. Typy kontenerów mogą być używane dla dyrektyw lokalizacji przychodzących i wychodzących. Mogą być również używane w widoku dostępnych zapasów, aby pomóc określić, jak wiele typów kontenerów znajduje się obecnie na stanie. Aby uzyskać więcej informacji, zobacz wpis na blogu [Używanie numerów identyfikacyjnych skojarzonych z typem kontenera do sterowania procesami zarządzania magazynem](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/). Mimo iż ten wpis na blogu opisuje aktualizację systemu Microsoft Dynamics AX 2012, ta sama obsługa została dodana do programu Dynamics 365 for Operations.                                                                                                                                                                                                                                                                                                                         |
| Wycofywanie wysyłek.                 | W magazynie trzeba mieć możliwość postępowania z późnymi zmianami. Na przykład niektóre towary mogą być uszkodzone, więc nie można ich wydać. Albo odbiorca może wysłać późną prośbę o anulowanie lub zmianę zamówienia. W programie Dynamics 365 for Operations można wycofać (wystornować) wysyłkę. Można anulować dokument dostawy, a później zaktualizować go o właściwe ilości. Podobnie w procesie przychodzącym można anulować dokument przyjęcia produktów i następnie utworzyć zaktualizowaną wersję.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Używanie palet zawierających mieszane towary. | Teraz można przyjąć i zarejestrować paletę „mieszaną”. Paleta mieszana zawiera różne towary, które są umieszczane na jednej palecie dla jednego lub kilku zamówień zakupu albo wierszy. Wszystkie rejestracje można zsumowywać pod jeden docelowy numer identyfikacyjny. Ten proces jest realizowany za pośrednictwem urządzenia przenośnego w magazynie. Na przykład gdy paleta mieszanych towarów przybywa do magazynu, pracownik przyjmujący identyfikuje towary i ich ilości na palecie, po czym paleta jest przenoszona do dedykowanych lokalizacji odłożenia. Lokalizacje odłożenia są identyfikowane przez szablony pracy i dyrektywy lokalizacji. Jeśli lokalizacje odłożenia są rozproszone między kilka towarów mających zdefiniowane stałe lokalizacje, ta funkcja tworzy tyle wierszy pracy, ile jest różnych towarów na mieszanej palecie. Ta funkcja pozwala szybciej i bardziej elastycznie rejestrować i odkładać otrzymane palety z mieszanymi towarami. Aby uzyskać więcej informacji, zobacz wpis na blogu [Odbieranie i rejestrowanie palety z mieszanymi wierszami dokumentów źródłowych przy użyciu jednego numeru identyfikacyjnego](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) oraz informacje o obsłudze mieszanych palet zawarte w [zapowiedzi naszej ostatniej zbiorczej aktualizacji](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Mimo iż ten wpis na blogu opisuje aktualizację systemu AX 2012, ta sama obsługa została dodana do programu Dynamics 365 for Operations. |

### <a name="minor-feature-enhancements-in-supply-chain-management"></a>Drobne ulepszenia funkcji w module Zarządzanie łańcuchem dostaw

<table>




<thead>
<tr class="header">
<th>Co można zrobić</th>
<th>Dlaczego to jest ważne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Używanie nowych jednostek danych do importowania i eksportowania danych.</td>
<td>Dane można importować i eksportować przy użyciu następujących jednostek danych:
<ul>
<li>Faktura za fracht</li>
<li>Dostępne zapasy razem według magazynu i stanu zapasów</li>
<li>Opłaty za zapasy</li>
<li>Oferta</li>
</ul></td>
</tr>
<tr class="even">
<td>Używanie rozszerzonego formantu wykresu Gantta do opracowywania interaktywnych scenariuszy planowania.</td>
<td>Rozszerzony formant wykresu Gantta umożliwia opracowywanie nowych interaktywnych scenariuszy planowania oraz udostępnianie rozszerzonych interfejsów API, których można używać do dostosowywania wyglądu działań. Poniżej przedstawiono wybrane nowe interfejsy API:
<ul>
<li>Przeciąganie w pionie i upuszczanie działań</li>
<li>Dodawanie/usuwanie działań</li>
<li>Wyświetlanie podglądu zarezerwowanych okresów na pasku podsumowania</li>
<li>Zmiana koloru i stylu obramowań działań</li>
<li>Zmiana koloru, stylu i tła tekstu w siatce</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ulepszenia w zakresie obsługi materiałów i planowania zasobów.</td>
<td>Wprowadzono kilka udoskonaleń w kwestii obsługi materiałów i planowania zasobów:
<ul>
<li>Zapas czasu dla rozchodu jest teraz obsługiwane, gdy towar jest dostępny.</li>
<li>Zastępowanie daty dostawy podczas ustalania zamówień planowanych.</li>
<li>Określanie, że realizacja zamówień ma priorytet nad zapasem bezpieczeństwa.</li>
<li>Uniemożliwianie planowania zamówień planowanych w okresach przeszłych.</li>
</ul></td>
</tr>
<tr class="even">
<td>Raportowanie rzeczywistego zużycia w produkcji i wyświetlanie stanu zapasów.</td>
<td>Można wyświetlić rzeczywiste zużycie w produkcji. Ponadto nowe pole wyboru <strong>Wyświetl stan zapasów</strong>, które dodano do opcji <strong>Przesunięcie</strong> w elemencie menu <strong>Tworzenie pracy</strong>, umożliwia wyświetlanie stanu zapasów.</td>
</tr>
<tr class="odd">
<td>Obliczanie wagi objętości, gdy stawki przewoźnika bazują na wadze objętości.</td>
<td>Dodano nowy aparat stawek TMS oparty na wadze objętości, dzięki czemu można obliczyć wagę objętości.</td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Nowości i zmiany](whats-new-changed.md)




