---
title: Identyfikatory produktów
description: Ten temat zawiera informacje o różnych typach identyfikatorów produktów i wyjaśnia, jak można dodawać identyfikatory produktów w danych produktów.
author: cvocph
manager: AnnBe
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductEntityIdentifierCode
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 68be63370eca0089649c47de0ba0bc9bd335b905
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250608"
---
# <a name="product-identifiers"></a>Identyfikatory produktów 

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o różnych typach identyfikatorów produktów i wyjaśnia, jak można dodawać identyfikatory produktów w danych produktów.

Pracując z produktami na wydziale produkcji lub w magazynie w Microsoft Dynamics EPR lub Microsoft Dynamics CRM, trzeba mieć dobrą strategię identyfikowania tych produktów i wariantów produktów.

## <a name="unique-product-numberproduct-id"></a>Unikatowy numer produktu/identyfikator produktu

W Dynamics 365 Supply Chain Management podstawowym identyfikatorem produktu jest numer produktu (czyli unikatowy identyfikator produktu). Ten numer może być generowane automatycznie przez mechanizm numeracji albo ręcznie łączony z produktem. Dla wariantów produktów numery można definiować za pomocą szablonu nazewnictwa produktów.

W wielu przypadkach numer produktu nie jest pierwotnie tworzony w Dynamics 365 Supply Chain Management. Zamiast tego jest kojarzony z produktem w systemie zarządzania cyklem życia produktu (PLM) lub systemie zarządzania danymi produktów (PDM). W takim przypadku są używane jednostki danych do importowania produktów i wariantów produktów. Supply Chain Management korzysta z numerów we wszystkich operacjach.

Podczas wdrażania programu Supply Chain Management należy zwrócić szczególną uwagę na strategię numerowania produktów. Dobry system numerowania usprawnia logistykę i pomaga uniknąć błędów. Dobry identyfikator produktu zawiera maksymalnie 15 znaków. Najlepiej, aby miał nie więcej niż 10 znaków i zawierał maksymalnie 5 znaków klasyfikujących. Można również używać aliasów do szybkiego wyszukiwania. Alias jest dodatkową nazwę reprezentującą klasyfikacje produktu.

Jeśli jest używany Common Data Service, numer produktu w module Supply Chain Management jest także numerem produktu w formularzu Common Data Service. Warianty produktów są synchronizowane z usługą Common Data Service jako odrębne produkty.

## <a name="item-number-and-product-dimensions"></a>Numer towaru i wymiary produktu

Numer towaru to identyfikator produktu używany przez konkretną firmę. Najlepiej, jeśli numer towaru jest taki sam, jak numer produktu. Jeśli nazewnictwo różni się w poszczególnych firmach, trudno jest śledzić produkt w całym łańcuchu dostaw i trzeba wprowadzić uciążliwe procesy zmiany etykiet i tworzenia odniesień. Dla zgodności ze starszymi wersjami (to znaczy z Microsoft Dynamics AX 2009 i wcześniejszymi) zachowaliśmy ten model. Jednak zalecamy, aby w miarę możliwości eliminować identyfikatory specyficzne dla firm, a zamiast tego stosować unikatowy numer produktu jako podstawowy identyfikator.

Ponadto wariant produktu nie może być niepowtarzalnie identyfikowany przez numer towaru. Zawsze wymaga on kombinacji numeru towaru i wszystkich wymiarów produktu zdefiniowanych w produkcie głównym. Ten wymóg może stać się kłopotliwy i spowalniać proces identyfikowania. Również z tego powodu zalecamy, aby stosować unikatowy numer produktu zamiast numeru towaru w każdym przypadku, gdy tylko jest to możliwe.

Nadal na wielu stronach numer towaru i wymiary produktu są podstawowymi identyfikatorami. Jednak w wyszukiwaniach można używać numerów produktów. W oknie **Sprzedaż i marketing** &gt; **Ustawienia** &gt; **Wyszukiwanie** &gt; **Parametry wyszukiwania** można zmienić ustawienia wyszukiwania, tak aby główna strategia wyszukiwania opierała się na używaniu numerów produktów zamiast numerów towarów. Jeśli w opcji **Włącz odnośniki na potrzeby wyszukiwania produktów** zaznaczysz wartość **Tak**, w wynikach wyszukiwania będą wyświetlane nie tylko produkty główne, ale również warianty produktów. Aby uzyskać więcej informacji, zobacz [Wyszukiwanie produktów i wariantów produktów podczas wprowadzania zamówień](search-products-product-variants.md).

Ponadto będzie można wyszukiwać i filtrować według numeru produktu, nazwy i opisu produktu oraz identyfikatorów wymiarów produktu ustawionych w wariancie produktu. Po wybraniu wariantu zostanie zaznaczony powiązany numer towaru i wszystkie identyfikatory wymiarów produktu. W związku z tym można łatwiej znaleźć i wybrać odpowiedni wariant. To ustawienie jest stanowczo zalecane, jeśli jako podstawowych identyfikatorów produktów używasz wariantów produktów i unikatowych numerów produktów. Jedynym wyjątkiem może być branża modowa, gdzie procesy biznesowe często wymagają wybrania produktu głównego przed wybraniem wariantu. Należy dokładnie ocenić efekty działania tej opcji przed przystąpieniem do wdrażania system numerowania.

## <a name="product-name-and-description"></a>Nazwa i opis produktu

Nazwa opis i produktu to identyfikatory produktu, które są czytelne dla człowieka i mogą być przechowywane w wielu językach. Domyślnie klient rozwiązania Supply Chain Management pokazuje wszystkie informacje o produktach w domyślnym języku firmy, a nie w języku użytkownika. Jednakże przetłumaczone nazwy i opisy produktów są używane w całej komunikacji z klientami i dostawcami. Tłumaczenia są oparte na kodach języków ustawionych na kontach odbiorców i dostawców.

Dla wariantów produktów nazwy produktów można generować za pomocą szablonu nazewnictwa produktów. Ponieważ nie istnieje wymóg, aby nazwy produktów były niepowtarzalne, może istnieć wiele produktów o tej samej nazwie.

## <a name="product-and-item-search-names"></a>Nazwy wyszukiwania produktów i towarów

Supply Chain Management oferuje pomocniczy alias dla produktów, a także dla towarów (zwolnionych produktów). Ten alias nie musi być unikatowy i można go zmienić po utworzeniu produktu lub wariantu produktu. Zalecamy, aby używać aliasu do wyszukiwania produktów według kategorii. Aliasy umożliwiają szybkie wyszukiwanie, szczególnie w procesach sprzedaży i zakupu.

Alias może także zawierać identyfikator produktu odbiorcy lub dostawcy albo jakiś inny zewnętrzny identyfikator produktu, jeżeli ten zewnętrzny identyfikator jest podstawowym kryterium wyszukiwania produktu.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Zewnętrzne identyfikatory produktów (identyfikatory odbiorców i dostawców)

Dla zwolnionych produktów można przechowywać numery, nazwy i opisy towarów używane przez odbiorcę lub dostawcę. Odwołania są wyświetlane w zewnętrznych dokumentach, takich jak zamówienia sprzedaży, zamówień zakupu, dokumentów dostawy i faktury. W bieżącej wersji programu Supply Chain Management odwołania zewnętrzne nie są pokazywane na stronach podstawowych operacji. Jedynym wyjątkiem jest numer towaru dostawcy. Ten numer jest wyświetlany w oknie dialogowym **Informacje o produktach**, jeśli dla zwolnionego produktu zdefiniowano domyślnego dostawcę.

Zewnętrzne identyfikatory produktów można przechowywać z podziałem na zwolnione produkty, warianty zwolnionych produktów, odbiorców lub grupy odbiorców albo dostawców lub grupy dostawców.

Na stronie **Zwolnione produkty** wykonaj jedną z następujących czynności.

- W przypadku odbiorców na karcie **Sprzedaż** w grupie **Informacje pokrewne** wybierz opcję **Zewnętrzny opis pozycji**.
- W przypadku dostawców na karcie **Zakup** w grupie **Informacje pokrewne** wybierz opcję **Zewnętrzny opis pozycji**.

Na stronie **Zewnętrzne opisy pozycji** można skojarzyć numer towaru odbiorcy lub dostawcy ze zwolnionym produktem. To skojarzenie należy wykonać dla każdej firmy. Można zarejestrować informacje wymienione poniżej. Niestety, etykiety nieco wprowadzają w błąd w bieżącej wersji programu Supply Chain Management. Jednakże etykiety te mogą się zmienić w przyszłej wersji.

| Pole | Odnośne informacje o odbiorcy | Odnośne informacje o dostawcy |
|-------|------------------------------------|----------------------------------|
| Numer pozycji zewnętrznej | Numer towaru odbiorcy | Numer towaru dostawcy |
| opis | Nazwa, którą odbiorca łączy z towarem | Nazwa, którą dostawca łączy z towarem |
| Zewnętrzny tekst pozycji | Opis nadany towarowi przez odbiorcę | Opis nadany towarowi przez dostawcę |

Jeżeli wielu odbiorców lub dostawców używa tych samych numerów towarów (jak na przykład w przypadku skojarzenia zakupu lub grupy sieci sprzedaży), można utworzyć grupy odbiorców lub dostawców, aby uprościć zarządzanie zewnętrznymi informacjami o produktach.

- Dla grup odbiorców przejdź do okna **Sprzedaż** &gt; **Ustawienia** &gt; **Pozycje** &gt; **Zewnętrzny opis pozycji**, aby utworzyć i obsługiwać grupy i pokrewne numery towarów. Aby skojarzyć odbiorców z grupą, przejdź do okna **Rozrachunki z odbiorcami** &gt; **Odbiorcy** &gt; **Wszyscy odbiorcy**, a następnie na skróconej karcie **Ustawienia domyślne zamówienia sprzedaży** określ wartość w polu **Pozycja — Grupa odbiorców**.
- Dla grup dostawców przejdź do okna **Zaopatrzenie i sourcing** &gt; **Ustawienia** &gt; **Grupa zewnętrznych opisów pozycji**, aby utworzyć i obsługiwać grupy i pokrewne numery towarów. Aby skojarzyć dostawców z grupą, przejdź do okna **Rozrachunki z dostawcami** &gt; **Dostawcy** &gt; **Wszyscy dostawcy**, a następnie na skróconej karcie **Ustawienia domyślne zamówienia zakupu** określ wartość w polu **Pozycja — Grupa dostawców**.
 
## <a name="bar-codes"></a>Kody kreskowe

Jeśli chcesz używać skanera kodów kreskowych do identyfikowania produktów, identyfikator produktu musi spełniać wymagania używanego standardu kodów kreskowych. W związku z tym kody kreskowe zwykle nie zawierają numeru produktu jako takiego, ale numer wygenerowany specjalnie dla wybranej technologii kodów kreskowych. Można przechowywać wiele kodów kreskowych z podziałem na typy kodów kreskowych. Można nawet skojarzyć ten sam kod kreskowy z wieloma produktami, a następnie wybrać faktyczne aktywne skojarzenie podczas skanowania kodu kreskowego.

Przed zdefiniowaniem kodów kreskowych można zdefiniować jedną lub więcej konfiguracji kodów kreskowych. Konfiguracje kodów kreskowych mogą pomagać w ocenie, czy kody kreskowe przestrzegają wymaganych zasad i w związku z tym mogą być skutecznie drukowane i skanowane. Można także przechowywać specjalne kody kreskowe dla określonych ilości produktu.

Zalecamy, aby używać konfiguracji kodów kreskowych do obsługi globalnych numerów jednostek handlowych (GTIN) lub europejskich kodów towarowych (EAN).

W celu obsługi kodów kreskowych na stronie **Zwolnione produkty** na karcie **Zarządzanie zapasami** w grupie **Magazyn** wybierz opcję **Kody kreskowe**.

## <a name="gtin-codes"></a>Numery GTIN

W handlu elektronicznym jest bardzo ważne, aby wszystkie strony posługiwały się wspólnym językiem i odnosiły do produktów przy użyciu wspólnego zestawu identyfikatorów. Z tego względu niektóre branże opierają się na używaniu [GTIN](https://www.gs1.org/id-keys/gtin), który jest globalnym systemem numeracji towarów wykorzystującym kody kreskowe GS1.

Zaleca się, aby zachować numer GTIN jako kod kreskowy. Jednak można także przechowywać je na stronie **Pozycja — numer GTIN**. Aby otworzyć tę stronę, na stronie **Zwolnione produkty** na karcie **Zarządzanie zapasami** w grupie **Magazyn** wybierz opcję **Numery GTIN**. Należy zwrócić uwagę, że numer GTIN nie jest przechowywany jako numer globalny. Zamiast tego jest zarządzany przez firmę.

W programie Supply Chain Management definiuje się warianty opakowań w operacjach magazynowych poprzez definiowanie określonych jednostek miary. Na przykład towar może być przechowywany w sztukach, pakietach po 6 sztuk, w zasobnikach po 18 sztuk lub w pełnych paletach. Konkretna jednostka miary zostanie zdefiniowana dla każdego z tych wariantów opakowań. Ponieważ numer GTIN jest zwykle powiązany z jednostką opakowania produktu, na stronie **Pozycja — numer GTIN** można przechowywać wiele kodów GTIN dla każdego produktu i jednostki miary. Jednak w danej firmie nie można użyć tego samego kodu GTIN więcej niż jeden raz, tzn. ustawić go dla różnych towarów lub wariantów produktu.

Aby zarządzać **numerami GTIN**, na stronie **Zwolnione produkty** na karcie **Zarządzanie zapasami** w grupie **Magazyn** wybierz opcję **GTIN**.

## <a name="external-codes"></a>Kody zewnętrzne

Kody zewnętrzne można definiować dla wielu jednostek. Na przykład można zdefiniować kody zewnętrzne w celu identyfikowania produktów i zwolnionych produktów. Te kody zewnętrzne mogą służyć do skojarzenia kodów statystycznych lub kodów podatków ze zwolnionymi produktami i zwolnionymi wariantami produktów. Kody zewnętrzne są definiowane z podziale na firmy i typy kodów. Muszą być mieć unikatowe wartości firmy, typu kodu i odwołania do tabeli.

Niestety, nie istnieje standardowa funkcja umożliwiająca wyszukiwanie produktów według kodów zewnętrznych.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Jednostki danych używane do importowania i eksportowania identyfikatorów produktów

| Nazwa podmiotu | Identyfikatory importu | Identyfikatory eksportu | Komentarze |
|-------------|--------------------|--------------------|----------|
| Produkty wer. 2 | Numer produktu, alias produktu, nazwa produktu, opis produktu | Numer produktu, alias produktu, nazwa produktu, opis produktu | W zależności od ustawień jednostki oraz ustawień mechanizmu numerowania produktów numer produktu może być tworzony automatycznie podczas importu. |
| Warianty produktu | Numer produktu, alias produktu, nazwa produktu, opis produktu | Numer produktu, alias produktu, nazwa produktu, opis produktu | W zależności od szablonu nazewnictwa produktów numer produktu może być tworzony automatycznie w czasie importu. Jednak można zaimportować dowolny unikatowy numer produktu, a ten numer produktu nie musi być zgodny ze strukturą szablonów nazewnictwa produktów. |
| Tłumaczenia produktu | Nazwa produktu, opis produktu | Nazwa produktu, opis produktu | Ta jednostka zastępuje dowolny język. Należy zauważyć, że w przypadku zastąpienia nazwy lub opisu podstawowego języka osoby prawnej zmieniają się nazwa i opis samego produktu. |
| Zwolnione produkty (wersja 2) | Numer towaru, numer produktu, alias towaru| Numer towaru, numer produktu, alias towaru, alias produktu, nazwa produktu | Ta jednostka może sprawiać problemy, jeśli podczas tworzenia nowych zwolnionych produktów są używane numeracje. Obie numeracje — **Numer towaru** i **Numer produktu** — wywierają wpływ. Jednak numeracja **Numer towaru** dotyczy konkretnej firmy, natomiast numeracja **Numer produktu** jest globalna. Z tego względu nie zalecamy korzystania z numeracji **Numer towaru** podczas wdrażania nowych zwolnionych produktów. Oczywiście gdy jednostka jest używana do zwalniania istniejącego produktu, numer produktu musi być nadany w jednostce. Aby uzyskać więcej informacji, zobacz rozdział „Numeracje produktów i towarów” w tym temacie. |
| Zwolnione warianty produktu | Numer towaru, wymiary produktu, numer produktu | Numer produktu, alias produktu, nazwa produktu, opis produktu, wymiary produktu | Podobnie jak jednostka **Warianty produktu**, ta jednostka może być stosowana do tworzenia nowych produktów, które są zgodne z szablonem nazewnictwa produktów lub używają własnych numerów produktu dla wariantów. |
| Zewnętrzny opisy towaru dla odbiorców | Numer towaru u odbiorcy, nazwa towaru u odbiorcy, opis odbiorcy, konto odbiorcy | Numer towaru u odbiorcy, nazwa towaru u odbiorcy, opis odbiorcy, konto odbiorcy | Grupę odbiorców (na przykład zrzeszenie kupców) można zagregować w jedną grupę za pomocą jednostki **Grupy odbiorców — zewnętrzny opis pozycji**. |
| Zewnętrzny opis pozycji dla dostawców | Numer towaru u dostawcy, nazwa towaru u dostawcy, opis dostawcy, konto dostawcy | Numer towaru u dostawcy, nazwa towaru u dostawcy, opis dostawcy, konto dostawcy | Grupę dostawców (na przykład zrzeszenie sprzedawców lub branżową organizację) można zagregować w jedną grupę za pomocą jednostki **Grupy dostawców — zewnętrzny opis pozycji**. |
| Kod kreskowy towaru | Kod kreskowy | Kod kreskowy | Należy zauważyć, że podczas importu trzeba utworzyć odwołanie do konfiguracji kodów kreskowych zdefiniowanej w systemie docelowym. Odwołania do importowanych kodów kreskowych są weryfikowane względem konfiguracji kodów kreskowych i odrzucane, jeśli kody kreskowe nie spełniają wymagań zdefiniowanych w tej konfiguracji kodów kreskowych. |
| Kody zewnętrzne dla zwolnionych produktów | Kod zewnętrzny | Kod zewnętrzny, klasy kodów zewnętrznych, numer towaru | Kody zewnętrzne są powiązane z firmami. Podczas importu trzeba utworzyć odwołanie do zdefiniowanej klasy kodów. Do importowania klas kodów służy jednostka **Klasy kodów zewnętrznych dla zwolnionych produktów**. |
| Kody zewnętrzne dla zwolnionych wariantów produktów | Kod zewnętrzny | Kod zewnętrzny, klasy kodów zewnętrznych, numer towaru, wymiary produktu | Kody zewnętrzne są powiązane z firmami. Podczas importu trzeba utworzyć odwołanie do zdefiniowanej klasy kodów. Do importowania klas kodów służy jednostka **Klasy kodów zewnętrznych dla zwolnionych produktów**. Ta jednostka odwołuje się do wariantów produktu według numeru towaru i wymiarów produktu. |
| Kody zewnętrzne zwolnionych wariantów produktu według numeru identyfikacyjnego produktu | Kod zewnętrzny | Kod zewnętrzny, klasy kodów zewnętrznych, numer produktu | Kody zewnętrzne są powiązane z firmami. Podczas importu trzeba utworzyć odwołanie do zdefiniowanej klasy kodów. Do importowania klas kodów służy jednostka **Klasy kodów zewnętrznych dla zwolnionych produktów**. Ta jednostka odwołuje się do wariantów produktu według numeru produktu ustawionego w wariancie. (Od następnego głównego wydania) |
| Numer GTIN | Nie dotyczy | Nie dotyczy | Aktualnie nie istnieje konkretna jednostka służąca do importowania i eksportowania kodów GTIN. Zalecamy, aby do tych celów używać jednostki **Kod kreskowy towaru**. |
| Jednostka Identyfikator usługi danych wspólnych jednostki Produkt | Nie dotyczy | Numer towaru, alias towaru, alias produktu, numer towaru u dostawcy, numer towaru u odbiorcy, kody zewnętrzne, kody GTIN, kody kreskowe | Ta jednostka konsoliduje wszystkie identyfikatory w jeden model danych, tak aby można było używać jednego interfejsu do łatwego eksportowania wszystkich identyfikatorów i powiązanych z nimi typów. Użyj jednostki **Kod identyfikujący jednostkę Produkt**, aby wyeksportować kody i opisy identyfikatorów. Użyj jednostki **Identyfikator zakresu jednostki Produkt**, aby do identyfikatora wyeksportować dodatkowe informacje o zakresie, takie jak strona, firma, ilość lub jednostka. |

### <a name="product-and-item-number-sequences"></a>Numeracje produktów i towarów

Można zdefiniować dwie różne sekwencje numerów:

- Numeracja **Numer produktu** określająca globalny numer produktu
- Numeracja **Numer towaru** określająca numeru towarów w konkretnych firmach

> [!NOTE]
> Numeru towaru należy używać jako osobnego identyfikatora tylko wtedy, gdy przenosisz różne firmy z różnych źródeł mających różne systemy numerowania. Należy zawsze próbować używać identyfikatora produktu, który jest unikatowy we wszystkich firmach. W związku z tym w numeracji **Numer towaru** należy w opcji **Ręcznie** ustawiać wartość **Tak**. W ten sposób numer towaru będzie naśladował numer produktu podczas tworzenia. Jeśli program Supply Chain Management nie jest głównym systemem, w którym są tworzone nowe numery produktów, należy w opcji **Ręcznie** ustawić wartość **Tak** dla obu numeracji **Numer towaru** i **Numer produktu**.

Jeśli do tworzenia produktów używasz jednostki **Zwolniony produkt wer. 2**, wiele ustawień może wpływać na sposób używania numeracji do tworzenia numeru produktu i numeru towaru:

- Ustawienia numeracji **Numer produktu**
- Ustawienia numeracji **Numer towaru**
- Mapowanie numeru towaru 
- Mapowanie numeru produktu

Poniższa tabela zawiera przegląd wyników importu i ręcznego tworzenia przy określonych kombinacjach ustawień numeracji i mapowania pól.

| Numeracja Numer produktu | Numeracja Numer towaru | Mapowanie numeru towaru | Mapowanie numeru produktu | Wynik importu jednostki | Wynik ręcznego tworzenia | Wniosek |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Ręcznie = Nie | Ręcznie = Nie | Brak mapowania | Brak mapowania | Numery produktów używają numeracji **Numer produktu**. Numery towarów używają numeracji **Numer towaru**. | Numery produktów używają numeracji **Numer produktu**. Numery towarów używają numeracji **Numer towaru**. | Tych ustawień można używać, jeśli są potrzebne inne numery dla produktów i towarów. Jednak nie zalecamy stosowania różnych numerów dla towarów i produktów. |
| Ręcznie = Nie | Ręczne = Tak | Wygeneruj automatycznie | Brak mapowania | Numery produktów i numery towarów używają numeracji **Numer towaru**. | Numery produktów i numery towarów używają numeracji **Numer produktu**. | Te ustawienia nie są zalecane. Funkcje importu i ręcznego tworzenia działają różnie. |
| Ręcznie = Nie | Ręczne = Tak | Brak mapowania | Brak mapowania | Numery produktów i numery towarów używają numeracji **Numer produktu**. | Numery produktów i numery towarów używają numeracji **Numer produktu**. | Te ustawienia są zalecane, jeżeli produkty powinny mieć spójne automatyczne numerowanie niezależnie od tego, czy jest używany import, czy ręczne tworzenie. |
| Ręczne = Tak | Nie dotyczy | Nie dotyczy | Wygeneruj automatycznie | Pojawia się komunikat o błędzie „Nie można wykryć numeracji”. | Według numeracji **Numer towaru** | To ustawienie nie jest obsługiwane dla importu. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Identyfikator jednostki Produkt (eksport wszystkich identyfikatorów produktów)

Model Identyfikator jednostki Produkt został utworzony, aby w wersji 1.0 usługi CDS umożliwić obsługę wszystkich identyfikatorów używanych do odwoływania się do produktu. Aby uprościć to zadanie, wszystkie identyfikatory są agregowane do jednej globalnej tabeli identyfikatorów, dzięki czemu mogą zostać wyeksportowane jako jeden model. Należy zauważyć, że ta wersja usługi CDS nie używa modelu identyfikatorów produktów. Z tego względu jednostka **Jednostka Identyfikator usługi danych wspólnych jednostki Produkt** i ten proces mają ograniczone praktyczne zastosowanie i prawdopodobnie ulegną zmianie w przyszłości.

Tabela identyfikatorów produktów jest globalną tabelą wypełnianą na podstawie wszystkich tabel odwołań głównej firmy za pomocą cyklicznego zadania wsadowego. Należy wybrać firmę i hierarchię kategorii produktów jako definicję globalnego zakresu produktów głównych. Generowanie globalnej tabeli identyfikatorów produktów jest ograniczone do produktów zwalnianych do wybranej firmy oraz produktów będących elementami członkowskimi hierarchii produktów wybranej dla roli **Usługa danych wspólnych** w hierarchii kategorii produktów.

W tym procesie zakłada się, że dane produktów głównych są przechowywane głównie w jednej centralnej firmie. (Jednak ta firma może być firmą wirtualną używaną wyłącznie do przechowywania globalnych danych głównych).

Wykonaj następujące kroki, aby skonfigurować środowisko.

1. Wybierz hierarchię kategorii dla usługi CDS. Jeśli na stronie **Skojarzenia ról hierarchii kategorii** żadna hierarchia nie jest skojarzona z rolą **Usługa danych wspólnych**, należy utworzyć nowe skojarzenie. Wybierz rolę **Usługa danych wspólnych**, a następnie skojarz hierarchię kategorii reprezentującą portfolio produktów, które powinno być synchronizowane z usługą CDS.
2. Wybierz firmę dla globalnych danych głównych produktów. Na stronie **Parametry modułu Zarządzanie informacjami o produktach** na karcie **Atrybuty produktu** zaznacz główną firmę, w której są głównie przechowywane identyfikatory produktów i towarów.
3. Zdefiniuj typy kodów i kody identyfikatorów, które powinny zostać wyeksportowane. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Kody identyfikujące produkty**. Aby wygenerować typy kodów identyfikatorów, wybierz opcję **Generuj kody**. Wpis kodu typu zostanie wygenerowany dla każdego typu identyfikatora znalezionego w wybranej firmie.

    Należy zwrócić uwagę, że dla kodów kreskowych typ kodu jest generowany dla każdej konfiguracji kodów kreskowych. W przypadku kodów zewnętrznych typ kodu jest generowany dla każdej klasy kodów zewnętrznych.

    Teraz można zarządzać listą typów kodów. Można zmienić kod, nazwę i opis. Ponadto można usuwać typy kodów. Usunięte typy kodów nie będą używane do wypełniania globalnych tabel identyfikatorów jednostek Produkt.

4. Po zakończeniu definiowania typów kodów identyfikatorów produktów można utworzyć identyfikatory w tabeli globalnej poprzez wykonanie zadania **Tworzenie identyfikatorów jednostki Produkt** dostępnego na stronie **Kody identyfikujące jednostki Produkt**. Zadanie należy uruchomić w trybie wsadowym. To zadanie powinno być skonfigurowane jako okresowe zadanie wsadowe, tak aby tabela była wypełniana wraz z pojawianiem się nowych wpisów.

Teraz można używać jednostek danych **Jednostka Identyfikator usługi danych wspólnych jednostki Produkt**, **Kody identyfikujące jednostki Produkt** i **Zakres identyfikatora jednostki Produkt** do eksportowania identyfikatory do dowolnych systemów docelowych.

## <a name="related-topic"></a>Powiązany temat

[Wyszukiwanie produktów i wariantów produktów podczas wprowadzania zamówień](search-products-product-variants.md)
